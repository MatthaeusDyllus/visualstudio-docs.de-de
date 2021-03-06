---
title: Korrigieren von nicht erkennbaren dynamischen Parametern in einem Webleistungstest in Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs, load tests
- load tests, walkthroughs
- load tests, correlating dynamic parameters
ms.assetid: 92dff25c-36ee-4135-acdd-315c4962fa11
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: bf719eec2b9695e6019cf78e16ec5018639a92ed
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="fix-non-detectable-dynamic-parameters-in-a-web-performance-test"></a>Korrigieren von nicht erkennbaren dynamischen Parametern in einem Webleistungstest

Manche Websites verwenden dynamische Parameter, um einige ihrer Webanforderungen zu verarbeiten. Ein dynamischer Parameter ist ein Parameter, dessen Wert bei jeder Ausführung der Anwendung neu generiert wird. Ein Beispiel für einen dynamischen Parameter ist eine Sitzungs-ID. Die Sitzungs-ID ändert sich normalerweise alle 5 bis 30 Minuten. Das Modul für die Webtestaufzeichnung und die Wiedergabe verarbeitet die geläufigsten Typen von dynamischen Parametern automatisch:

-   Dynamische Parameter, die in einem Cookiewert festgelegt werden. Das Webleistungstest-Modul verarbeitet diese automatisch während der Wiedergabe.

-   Dynamische Parameterwerte, die in ausgeblendeten Feldern auf HTML-Seiten festgelegt werden, z B. der ASP.NET-Ansichtszustand. Diese werden automatisch vom Rekorder verarbeitet, der dem Test Extraktionsregeln für ausgeblendete Felder hinzufügt.

-   Dynamische Parameterwerte, die als Abfragezeichenfolge und Formularbereitstellungsparameter festgelegt werden. Diese werden durch Erkennung dynamischer Parameter verarbeitet, nachdem Sie einen Webleistungstest aufgezeichnet haben.

Einige Typen dynamischer Parameter werden nicht erkannt. Ein unerkannter dynamischer Parameter führt dazu, dass der Webleistungstest bei der Ausführung fehlschlagt, da der dynamische Wert bei jeder Ausführung des Tests unterschiedlich ist. Damit diese Parameter korrekt verarbeitet werden, können Sie den dynamischen Parametern in Webleistungstests Extraktionsregeln manuell hinzufügen.

## <a name="create-and-run-a-web-app-with-dynamic-parameters"></a>Erstellen und Ausführen einer Web-App mit dynamischen Parametern

Zur Demonstration eines auffindbaren und eines nicht auffindbaren dynamischen Parameters erstellen wir eine einfache ASP.NET-Webanwendung, die über drei Webformulare mit einigen Steuerelementen und benutzerdefiniertem Code verfügt. An diesem Beispiel wird gezeigt, wie Sie die dynamischen Parameter isolieren und verarbeiten.

1.  Erstellen Sie ein neues ASP.NET-Projekt mit dem Namen "DynamicParamaterSample".

     ![Leeres ASP.NET-Webanwendungsprojekt erstellen](../test/media/web_test_dynamicparameter_aspproject.png "Web_Test_DynamicParameter_ASPProject")

2.  Fügen Sie ein Webformular mit dem Namen "Querystring.aspx" hinzu.

3.  Ziehen Sie in der Entwurfsansicht ein HiddenField-Steuerelement auf die Seite, und ändern Sie dann den Wert für die (ID)-Eigenschaft auf "HiddenFieldSessionID".

     ![„HiddenField“ hinzufügen](../test/media/web_test_dynamicparameter_hiddenfield.png "Web_Test_DynamicParameter_HiddenField")

4.  Wechseln Sie zur Quellansicht für die Seite "Querystring", und fügen Sie den folgenden hervorgehobenen ASP.NET- und JavaScript-Code hinzu, mit dem die Pseudositzungs-ID für die dynamischen Parameter generiert wird:

    ```html
    <head runat="server">
    <title>JavaScript dynamic property correlation sample</title><script type="text/javascript" language="javascript">    <!--        function jScriptQueryString()         {            var Hidden = document.getElementById("HiddenFieldSessionID");            var sessionId = Hidden.value;            window.location = 'JScriptQuery.aspx?CustomQueryString=jScriptQueryString___' + sessionId;         }    //--></script>
    </head>
    <body>
        <form id="form1" runat="server">
        <div>
             <a name="QuerystringHyperlink" href="ASPQuery.aspx?CustomQueryString=ASPQueryString___<%= Session.SessionID %>">Dynamic querystring generated by ASP.net</a>         <br/>         <br/>         <a href="javascript:jScriptQueryString()">Dynamic querystring generated by javascript </a>
        </div>
        <asp:HiddenField ID="HiddenFieldSessionID" runat="server" />
        </form>
    </body>
    </html>
    ```

5.  Öffnen Sie die Datei "Querystring.aspx.cs", und fügen Sie der Page_Load-Methode folgenden hervorgehobenen Code hinzu:

    ```csharp
    public partial class Querystring : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            Session.Add("Key", "Value");HiddenFieldSessionID.Value = Session.SessionID;
        }
    }
    ```

6.  Fügen Sie ein zweites Webformular mit dem Namen "ASPQuery.aspx" hinzu.

7.  Ziehen Sie in der Entwurfsansicht eine Bezeichnung auf die Seite, und ändern Sie den Wert für ihre (ID)- Eigenschaft auf "IndexLabel".

     ![Bezeichnung zum Webformular hinzufügen](../test/media/web_test_dynamicparameter_label.png "Web_Test_DynamicParameter_Label")

8.  Ziehen Sie einen Link auf die Seite, und ändern Sie den Wert für seine Texteigenschaft auf "Back".

     ![Link zum Webformular hinzufügen](../test/media/web_test_dynamicparameter_hyperlink.png "Web_Test_DynamicParameter_Hyperlink")

9. Wählen Sie "(...)" für die NavigationURL-Eigenschaft.

     ![NavigateURL-Eigenschaft bearbeiten](../test/media/web_test_dynamicparameter_hyperlink_navurl.png "Web_Test_DynamicParameter_Hyperlink_NavURL")

     Wählen Sie "Querystring.aspx" aus.

     ![„Querystring.aspx“ als URL auswählen](../test/media/web_test_dynamicparameter_hyperlink_navurl2.png "Web_Test_DynamicParameter_Hyperlink_NavURL2")

10. Öffnen Sie die Datei "ASPQuery.aspx.cs", und fügen Sie der Page_Load-Methode folgenden hervorgehobenen Code hinzu:

    ```csharp
    protected void Page_Load(object sender, EventArgs e)
            {
                int index;            string qstring;            string dateportion;            string sessionidportion;            qstring = Request.QueryString["CustomQueryString"];            index = qstring.IndexOf("___");            dateportion = qstring.Substring(0, index);            index += 3;            sessionidportion = qstring.Substring(index, qstring.Length - index);            if (sessionidportion != Session.SessionID)            {                Response.StatusCode = 401;                IndexLabel.Text = "Failure!  Invalid querystring parameter found.";            }            else            {                IndexLabel.Text = "Success.  Dynamic querystring parameter was found.";            }            IndexLabel.Text += "<br>\r\n";
            }
    ```

11. Fügen Sie ein drittes Webformular mit dem Namen "JScriptQuery.aspx" hinzu.

     Ziehen Sie wie bei der zweiten Seite eine Bezeichnung auf das Formular, setzen Sie ihre (ID)-Eigenschaft auf "IndexLabel", ziehen Sie einen Link auf das Formular, und setzen Sie seine Texteigenschaft auf "Back" und seine NavigationURL-Eigenschaft auf "Querystring.aspx".

     ![Das dritte Webformular hinzufügen und konfigurieren](../test/media/web_test_dynamicparameter_addwebform3.png "Web_Test_DynamicParameter_AddWebForm3")

12. Öffnen Sie die Datei "JScriptQuery.aspx.cs", und fügen Sie der Page_Load-Methode folgenden hervorgehobenen Code hinzu:

    ```csharp
    protected void Page_Load(object sender, EventArgs e)
            {
                int index;            string qstring;            string dateportion;            string sessionidportion;            qstring = Request.QueryString["CustomQueryString"];            index = qstring.IndexOf("___");            dateportion = qstring.Substring(0, index);            index += 3;            sessionidportion = qstring.Substring(index, qstring.Length - index);            if (sessionidportion != Session.SessionID)            {                Response.StatusCode = 401;                IndexLabel.Text = "Failure!  Invalid querystring parameter found.";            }            else            {                IndexLabel.Text = "Success.  Dynamic querystring parameter was found.";            }            IndexLabel.Text += "<br>\r\n";
            }
    ```

13. Speichern Sie das Projekt.

14. Legen Sie im Projektmappen-Explorer "Querystring.aspx" als Startseite fest.

     ![Startseite auf „Querystring.aspx“ festlegen](../test/media/web_test_dynamicparameter_setstartpage.png "Web_Test_DynamicParameter_SetStartPage")

15. Drücken Sie STRG+F5, um die Webanwendung im Browser auszuführen. Kopieren Sie die URL. Sie benötigen sie bei der Aufzeichnung des Tests.

16. Probieren Sie Links aus. Sie sollten jeweils die Nachricht "Erfolg" anzeigen. dass der dynamische querystring-Parameter gefunden wurde.

     ![Web-App ausführen](../test/media/web_test_dynamicparameter_runapp.png "Web_Test_DynamicParameter_RunApp")

     ![Erfolg&#33;](../test/media/web_test_dynamicparameter_runapp2.png "Web_Test_DynamicParameter_RunApp2")

## <a name="create-a-web-performance-test"></a>Erstellen eines Webleistungstests

1.  Fügen Sie der Projektmappe ein Webleistungs- und Auslastungstestprojekts hinzu.

     ![Ein Webleistungs- und Auslastungstestprojekt hinzufügen](../test/media/web_test_dynamicparameter_addtestproject.png "Web_Test_DynamicParameter_AddTestProject")

2.  Ändern Sie den Namen von "WebTest1.webtest" auf "DynamicParameterSampleApp.webtest".

     ![Webleistungstest umbenennen](../test/media/web_test_dynamicparameter_renametest.png "Web_Test_DynamicParameter_RenameTest")

3.  Zeichnen Sie den Test auf.

     ![Webleistungstest aufzeichnen](../test/media/web_test_dynamicparameter_recordtest.png "Web_Test_DynamicParameter_RecordTest")

4.  Kopieren Sie die URL von der Website, die Sie testen, in den Browser.

     ![URL der zu testenden Website einfügen](../test/media/web_test_dynamicparameter_recordtest2.png "Web_Test_DynamicParameter_RecordTest2")

5.  Navigieren Sie durch die Webanwendung. Wählen Sie den Link "ASP.NET", den Link "Back" und dann den Link "Javascript" gefolgt vom Link "Back" aus.

     Die Webtestaufzeichnung zeigt die URL der HTTP-Anforderung und -Antwort an, während Sie durch die Webanwendung navigieren.

6.  Wählen Sie die STOP-TASTE in der Testaufzeichnung.

     Im Dialogfeld zum Erkennen von dynamischen Parametern erscheint eine Statusanzeige, die den Status der Parameterbestimmung in den empfangenen HTTP-Antworten zeigt.

7.  Der dynamische Parameter für "CustomQueryString" auf der Seite "ASPQuery" wird automatisch erkannt. Der dynamische Parameter für "CustomQueryString" auf der Seite "JScriptQuery" hingegen wird nicht erkannt.

     Wählen Sie OK, um Querystring.aspx eine Extraktionsregel hinzuzufügen und sie an die Seite „ASPQuery“ zu binden.

     ![Erkannten dynamischen Parameter höher stufen](../test/media/web_test_dynamicparameter_promotedialog.png "Web_Test_DynamicParameter_PromoteDialog")

     Die Extraktionsregel wird der ersten Anforderung von "Querystring.aspx" hinzugefügt.

     ![Zur Anforderung hinzugefügte Extraktionsregel](../test/media/web_test_dynamicparameter_autoextractionrule.png "Web_Test_DynamicParameter_AutoExtractionRule")

     Erweitern Sie die zweite Anforderung in der Anforderungsstruktur für „ASPQuery.aspx“. Sie sehen, dass der Wert von „CustomQueryString“ an die Extraktionsregel gebunden wurde.

     ![CustomQueryString, an Extraktionsregel gebunden](../test/media/web_test_dynamicparameter_autoextractionrule2.png "Web_Test_DynamicParameter_AutoExtractionRule2")

8.  Speichern Sie den Test.

## <a name="run-the-test-to-isolate-the-non-detected-dynamic-parameter"></a>Ausführen des Tests zur Isolierung des nicht erkannten dynamischen Parameters

1.  Führen Sie den Test aus.

     ![Webleistungstest ausführen](../test/media/web_test_dynamicparameter_runtest.png "Web_Test_DynamicParameter_RunTest")

2.  Die vierte Anforderung für die Seite "JScriptQuery.aspx" schlägt fehl. Wechseln Sie zum Webtest.

     ![Testergebnisse mit Fehler im dynamischen Parameter](../test/media/web_test_dynamicparameter_runresults.png "Web_Test_DynamicParameter_RunResults")

     Der Anforderungsknoten "JScriptQuery.aspx" wird im Editor markiert. Erweitern Sie den Knoten, und beachten Sie, dass der Teil „1v0yhyiyr0raa2w4j4pwf5zl“ von CustomQueryString dynamisch zu sein scheint.

     ![Vermuteter dynamischer Parameter in CustomQueryString](../test/media/web_test_dynamicparameter_runresults2.png "Web_Test_DynamicParameter_RunResults2")

3.  Kehren Sie zum Webleistungstest-Ergebnisviewer zurück, und wählen Sie die Seite "JScriptQuery.aspx" mit dem Fehler aus. Wählen Sie anschließend die Registerkarte für die Anforderungen, überprüfen Sie, ob das Kontrollkästchen "Unformatierte Daten anzeigen" deaktiviert ist, führen Sie einen Bildlauf nach unten durch, und wählen Sie die Schnellsuche für "CustomQueryString".

     ![Schnellsuche verwenden, um den dynamischen Parameter zu isolieren](../test/media/web_test_dynamicparameter_runresultsquckfind.png "Web_Test_DynamicParameter_RunResultsQuckFind")

4.  Da Sie den Test im Test-Editor überprüft haben, wissen Sie in diesem Fall, dass dem CustomQueryString-Parameter der Anforderung für „JScriptQuery.aspx“ der Wert `jScriptQueryString___1v0yhyiyr0raa2w4j4pwf5zl` zugewiesen wurde und dass der vermutete dynamische Teil „1v0yhyiyr0raa2w4j4pwf5zl“ ist. Entfernen Sie in der Dropdownliste "Suchen nach" den fehlerverdächtigen Teil der Suchzeichenfolge. Die Zeichenfolge sollte "CustomQueryString=jScriptQueryString___" lauten.

     Dynamischen Parametern werden in einer der Anforderungen vor der fehlerhaften Anforderung Werte zugewiesen. Aktivieren Sie daher das Kontrollkästchen "Suchrichtung nach oben", und wählen Sie "Weitersuchen", bis die vorangehende Anforderung für "Querystring.aspx" im Bereich "Anforderung" hervorgehoben wird. Dies sollte der Fall sein, nachdem Sie dreimal auf "Weitersuchen" geklickt haben.

     ![Schnellsuche verwenden, um den dynamischen Parameter zu isolieren](../test/media/web_test_dynamicparameter_runresultsquckfind4.png)

     Wie auf der Registerkarte "Antwort" und im zuvor implementierten JavaScript angezeigt wird, ist dem Abfragezeichenfolgen-Parameter "CustomQueryString" der Wert " jScriptQueryString___" zugewiesen, und zudem ist er mit dem zurückgegebenen Wert der sessionId-Variable verkettet.

    ```
    function jScriptQueryString()          {             var Hidden = document.getElementById("HiddenFieldSessionID");             var sessionId = Hidden.value;             window.location = 'JScriptQuery.aspx?CustomQueryString=jScriptQueryString___' + sessionId;          }

    ```

     Jetzt wissen Sie, wo der Fehler auftritt, und Sie wissen auch, dass Sie den Wert für "sessionId" extrahieren müssen. Da es sich bei dem Extraktionswert jedoch nur um Text handelt, müssen Sie den Fehler weiter isolieren, indem Sie nach einer Zeichenfolge zu suchen, in der der tatsächliche Wert von "sessionId" angezeigt wird. Im Code können Sie sehen, dass die sessionId-Variable dem von "HiddenFieldSessionID" zurückgegebenen Wert entspricht.

5.  Führen Sie eine Schnellsuche nach "HiddenFieldSessionID durch; deaktivieren Sie dabei das Kontrollkästchen "Suchrichtung nach oben", und wählen Sie die aktuelle Anforderung aus.

     ![Schnellsuche für HiddenFieldSession verwenden](../test/media/web_test_dynamicparameter_runresultsquckfindhiddensession.png "Web_Test_DynamicParameter_RunResultsQuckFindHiddenSession")

     Bei dem zurückgegebenen Wert handelt es sich nicht um die gleiche Zeichenfolge wie in der ursprünglichen Webleistungstest-Aufzeichnung. Für diesen Testlauf ist der zurückgegebene Wert "5w4v3yrse4wa4axrafykqksq"; in der ursprünglichen Aufzeichnung war der Wert "1v0yhyiyr0raa2w4j4pwf5zl". Da der Wert nicht mit der ursprünglichen Aufzeichnung übereinstimmt, wird der Fehler generiert.

6.  Da der dynamische Parameter in der ursprünglichen Aufzeichnung korrigiert werden muss, wählen Sie das aufgezeichnete Ergebnis auf der Symbolleiste aus.

     ![Aufgezeichnetes Ergebnis auswählen](../test/media/web_test_dynamicparameter_recordedresult.png "Web_Test_DynamicParameter_RecordedResult")

7.  Wählen Sie in den aufgezeichneten Ergebnissen die dritte Anforderung aus, d. h. die gleiche Querystringrequest.aspx-Anforderung, die Sie in den Testlaufergebnissen isoliert haben.

     ![Dieselbe Anforderung in den aufgezeichneten Ergebnissen auswählen](../test/media/web_test_dynamicparameter_recordedresultsselectnode.png "Web_Test_DynamicParameter_RecordedResultsSelectNode")

     Wählen Sie die Registerkarte "Antwort" aus, führen Sie einen Bildlauf nach unten aus, wählen Sie den ursprünglichen dynamischen Parameterwert "1v0yhyiyr0raa2w4j4pwf5zl" aus, den Sie zuvor isoliert haben, und fügen Sie eine Extraktionsregel hinzu.

     ![Eine Extraktionsregel für den dynamischen Parameter hinzufügen](../test/media/web_test_dynamicparameter_recordedresultaddextractionrule.png "Web_Test_DynamicParameter_RecordedResultAddExtractionRule")

     Die neue Extraktionsregel wird der Querystring.aspx-Anforderung hinzugefügt und erhält den Wert "Param0" zugewiesen.

     Wenn das Dialogfeld meldet, dass Entsprechungen für den extrahierten Text gefunden wurden, an die der Parameter gebunden werden kann, wählen Sie "Ja" aus.

     ![Erstellte Extraktionsregel](../test/media/web_test_dynamicparameter_addextractiondialog.png "Web_Test_DynamicParameter_AddExtractionDialog")

8.  Wählen Sie "Weitersuchen". Die erste Entsprechung ist diejenige, die geändert werden muss, nämlich der Parameter für "CustomQueryString" auf der Seite "JScriptQuery".

     ![Text für den Parameter suchen und ersetzen](../test/media/web_test_dynamicparameter_addextractionfindreplace.png "Web_Test_DynamicParameter_AddExtractionFindReplace")

9. Wählen Sie "Ersetzen".

     ![Text mit dem Parameter ersetzen](../test/media/web_test_dynamicparameter_addextractionfindreplace2.png "Web_Test_DynamicParameter_AddExtractionFindReplace2")

     Der QueryString-Parameter unter der JScriptQuery.aspx-Anforderung wird mit dem neuen Kontextparameter aktualisiert: CustomQueryString=jScriptQueryString___{{Param0}}.

     ![Auf QueryString angewendeter Parameter](../test/media/web_test_dynamicparameter_addextractionfindreplace3.png "Web_Test_DynamicParameter_AddExtractionFindReplace3")

10. Schließen Sie das Dialogfeld "Suchen und Ersetzen". Beachten Sie im Anforderungsbaum die ähnliche Struktur des erkannten dynamischen Parameters und des korrelierten nicht erkannten dynamischen Parameters.

     ![Gefundene und korrelierte dynamische Parameter](../test/media/web_test_dynamicparameter_conclusion.png "Web_Test_DynamicParameter_Conclusion")

11. Führen Sie den Test aus. Er wird nun ohne Fehler ausgeführt.

## <a name="qa"></a>Fragen und Antworten

### <a name="q-can-i-re-run-dynamic-parameter-detection-if-my-web-app-gets-modified"></a>F: Kann ich die Erkennung dynamischer Parameter erneut überprüfen, wenn meine Web-App geändert wurde?

 **A:** Ja, nach folgendem Verfahren:

1.  Wählen Sie auf der Symbolleiste die Schaltfläche "Dynamische Parameter auf Webtestparameter hochstufen".

     Nach Abschluss des Erkennungsprozesses (wenn dynamische Parameter erkannt werden) wird das Dialogfeld "Dynamische Parameter auf Webtestparameter hochstufen" angezeigt.

     Die dynamischen Parameter sind unter der Spalte Dynamische Parameter aufgeführt. Die Anforderungen, aus denen der dynamische Parameter extrahiert wird und an die er gebunden wird, werden unter Parameter aus Antwort extrahieren und An Anforderungsspalten binden aufgeführt.

     Wenn Sie im Dialogfeld "Dynamische Parameter auf Webtestparameter hochstufen" einen dynamischen Parameter wählen, werden zwei Anforderungen in der Anforderungsstruktur des Webleistungstest-Editors hervorgehoben. Die erste Anforderung ist die Anforderung, der die Extraktionsregel hinzugefügt wird. Die zweite Anforderung befindet dort, wo der extrahierte Wert gebunden wird.

2.  Aktivieren oder deaktivieren Sie das Kontrollkästchen neben den dynamischen Parametern, die Sie gern automatisch in Zusammenhang setzen möchten. Standardmäßig werden alle dynamischen Parameter überprüft.

### <a name="q-do-i-need-to-configure-visual-studio-to-detect-dynamic-parameters"></a>F: Muss ich Visual Studio konfigurieren, damit dynamische Parameter erkannt werden?

 **A:** Standardmäßig ist Visual Studio so konfiguriert, dass dynamische Parameter erkannt werden, wenn Sie einen Webleistungstest aufzeichnen. Wenn Sie Visual Studio-Optionen jedoch so konfiguriert haben, dass dynamische Parameter nicht erkannt werden, oder die getestete Webanwendung mit zusätzlichen dynamischen Parametern geändert wird, können Sie die [Erkennung dynamischer Parameter vom Webleistungstest-Editor ausführen](#FindingNonDetectableDynamicParamters_QA_ReRunDetection).