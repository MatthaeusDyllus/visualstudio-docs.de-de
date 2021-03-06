---
title: Erstellen einer Windows Forms-Toolbox-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- winforms
- toolbox
- windows forms
ms.assetid: 0be6ffc1-8afd-4d02-9a5d-e27dde05fde6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a7d5bae07d3596902f94417cda20c3d40feed2f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-windows-forms-toolbox-control"></a>Erstellen ein Windows Forms-Toolbox-Steuerelement
Die Elementvorlage für Windows Forms-Toolbox-Steuerelement, das in Visual Studio-Erweiterbarkeitstools (VS SDK) enthalten ist ermöglicht die Erstellung ein Steuerelements, das automatisch hinzugefügt wird, die **Toolbox** bei Installation der Erweiterung. In diesem Thema zeigt, wie Sie die Vorlage verwenden, um einen einfachen Zähler-Steuerelement zu erstellen, die Sie an andere Benutzer verteilen können.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Ab Visual Studio 2015, führen Sie Sie nicht Visual Studio-SDK aus dem Downloadcenter installieren. Sie ist als optionales Feature in Visual Studio-Setup aus. Sie können das VS-SDK auch später installieren. Weitere Informationen finden Sie unter [Installieren von Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-windows-forms-toolbox-control"></a>Erstellen ein Windows Forms-Toolbox-Steuerelement  
 Die Vorlage für Windows Forms-Toolbox-Steuerelement erstellt ein nicht definiertes Benutzersteuerelement und enthält alle Funktionen, die erforderlich ist, um das Steuerelement hinzufügen der **Toolbox**.  
  
#### <a name="create-an-extension-with-a-windows-forms-toolbox-control"></a>Erstellen Sie eine Erweiterung mit einer Windows Forms-Toolbox-Steuerelement  
  
1.  Erstellen Sie ein VSIX-Projekt mit dem Namen `MyWinFormsControl`. Sie finden die VSIX-Projektvorlage in die **neues Projekt** Dialogfeld unter **Visual c# / Erweiterbarkeit**.  
  
2.  Wenn das Projekt geöffnet wird, fügen einen **Windows Forms-Toolbox-Steuerelement** Elementvorlage, die mit dem Namen `Counter`. In der **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektknoten, und wählen Sie **hinzufügen / neues Element**. In der **neues Element hinzufügen** wechseln Sie zum Dialogfeld **Visual c# / Erweiterbarkeit** , und wählen Sie **Windows Forms-Toolbox-Steuerelement**  
  
3.  Dadurch wird ein Benutzersteuerelement, ein `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> zum Platzieren des Steuerelements in der **Toolbox**, und ein **Microsoft.VisualStudio.ToolboxControl** -Ressourceneintrag im VSIX-Manifest für die Bereitstellung.  
  
### <a name="building-a-user-interface-for-the-control"></a>Erstellen einer Benutzeroberfläche für das Steuerelement  
 Die `Counter` Steuerelement erfordert zwei untergeordneten Steuerelementen: eine <xref:System.Windows.Forms.Label> zum Anzeigen der aktuellen Anzahl und eine <xref:System.Windows.Forms.Button> auf die Anzahl der auf 0 zurückgesetzt. Keine weiteren untergeordneten Steuerelemente sind erforderlich, da der Zählerwert von Aufrufern programmgesteuert erhöht werden.  
  
##### <a name="to-build-the-user-interface"></a>So erstellen Sie die Benutzeroberfläche  
  
1.  In **Projektmappen-Explorer**, doppelklicken Sie auf Counter.cs, um sie im Designer zu öffnen.  
  
2.  Entfernen Sie die "klicken Sie hier!" **Schaltfläche** , ist standardmäßig enthalten, wenn Sie die Elementvorlage für Windows Forms-Toolbox-Steuerelement hinzufügen.  
  
3.  Aus der **Toolbox**, ziehen Sie eine `Label` Steuerelement und dann eine `Button` Steuerelement unterhalb der Entwurfsoberfläche angezeigt.  
  
4.  Größe des gesamten Benutzersteuerelements auf 150, 50 Pixel und zum Ändern der Größe der Schaltfläche zu steuern, auf 50 20 Pixel.  
  
5.  In der **Eigenschaften** Fenster, legen Sie die folgenden Werte für die Steuerelemente auf der Entwurfsoberfläche angezeigt.  
  
    |Steuerelement|Eigenschaft|Wert|  
    |-------------|--------------|-----------|  
    |`Label1`|**Text**|""|  
    |`Button1`|**Name**|btnReset|  
    |`Button1`|**Text**|Zurücksetzen|  
  
### <a name="coding-the-user-control"></a>Codieren des Benutzersteuerelements  
 Das `Counter` -Steuerelement macht folgende Elemente verfügbar: eine Methode zum Erhöhen des Zählerwerts, ein Ereignis, das immer dann ausgelöst wird, wenn der Zählerwert erhöht wird, eine `Reset` -Schaltfläche sowie drei Eigenschaften, mit denen die aktuelle Anzahl und der Anzeigetext gespeichert werden bzw. festgelegt wird, ob die `Reset` -Schaltfläche ein- oder ausgeblendet wird. Die `ProvideToolboxControl` Attribut bestimmt den Speicherort in der **Toolbox** der `Counter` -Steuerelement angezeigt wird.  
  
##### <a name="to-code-the-user-control"></a>Codieren des Benutzersteuerelements  
  
1.  Doppelklicken Sie auf das Formular, um den Load-Ereignishandler im Code-Fenster zu öffnen.  
  
2.  Erstellen Sie über die Ereignishandlermethode in der Steuerelementklasse eine ganze Zahl zum Speichern der Wert dieses Indikators und eine Zeichenfolge für den Anzeigetext gespeichert werden, wie im folgenden Beispiel gezeigt.  
  
    ```csharp  
    int currentValue;  
    string displayText;  
    ```  
  
3.  Erstellen Sie die folgenden Deklarationen für die öffentliche Eigenschaft ein.  
  
    ```csharp  
    public int Value {  
        get { return currentValue; }   
    }  
  
    public string Message {  
        get { return displayText; }  
        set { displayText = value; }  
    }  
  
    public bool ShowReset {  
        get { return btnReset.Visible; }  
        set { btnReset.Visible = value; }  
    }  
  
    ```  
  
     Aufrufer erreichen dieser Eigenschaften zum Abrufen und festlegen den Anzeigetext des Indikators und zum Anzeigen oder Ausblenden der `Reset` Schaltfläche. Aufrufer erhalten den aktuellen Wert der Read-only `Value` -Eigenschaft, aber sie können nicht den Wert direkt festlegen.  
  
4.  Platzieren Sie den folgenden Code in die `Load` -Ereignis für das Steuerelement.  
  
    ```csharp  
    private void Counter_Load(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = Message + Value;  
    }  
  
    ```  
  
     Festlegen der **Bezeichnung** Text in die <xref:System.Windows.Forms.UserControl.Load> Ereignis ermöglicht die Zieleigenschaften laden, bevor ihre Werte angewendet werden. Festlegen der **Bezeichnung** Text im Konstruktor ergibt ein leeres **Bezeichnung**.  
  
5.  Erstellen Sie die folgende öffentliche Methode, um den Zählerwert erhöht.  
  
    ```csharp  
    public void Increment()  
    {  
        currentValue++;  
        label1.Text = displayText + Value;  
        Incremented(this, EventArgs.Empty);  
    }  
  
    ```  
  
6.  Fügen Sie eine Deklaration für die `Incremented` Ereignis, um die Control-Klasse.  
  
    ```csharp  
    public event EventHandler Incremented;  
    ```  
  
     Dieses Ereignis reagieren auf Änderungen in den Wert des Indikators können Aufrufer Handler hinzufügen.  
  
7.  Zurück zur Entwurfsansicht, und doppelklicken Sie auf die `Reset` Schaltfläche zum Generieren der `btnReset_Click` Ereignishandler, und füllen Sie es darüber, wie im folgenden Beispiel gezeigt.  
  
    ```csharp  
    private void btnReset_Click(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = displayText + Value;  
    }  
  
    ```  
  
8.  Direkt über der Klassendefinition in der `ProvideToolboxControl` -Attributdeklaration, ändern Sie den Wert des ersten Parameters von `"MyWinFormsControl.Counter"` auf `"General"`. Dadurch wird der Name der Elementgruppe festgelegt, die das Steuerelement in der **Toolbox**hostet.  
  
     Das folgende Beispiel zeigt das `ProvideToolboxControl` -Attribut und die angepasste Klassendefinition.  
  
    ```csharp  
    [ProvideToolboxControl("General", false)]  
    public partial class Counter : UserControl  
    ```  
  
### <a name="testing-the-control"></a>Testen des Steuerelements  
 So testen Sie eine **Toolbox** steuern, testen Sie es zunächst in der Entwicklungsumgebung, und klicken Sie dann in einer kompilierten Anwendung zu testen.  
  
##### <a name="to-test-the-control"></a>So testen Sie das Steuerelement  
  
1.  Drücken Sie F5.  
  
     Dies erstellt das Projekt und öffnet eine zweite experimentelle Instanz von Visual Studio, die das Steuerelement installiert ist.  
  
2.  Erstellen Sie in der experimentellen Instanz von Visual Studio eine **Windows Forms-Anwendung** Projekt.  
  
3.  In **Projektmappen-Explorer**, doppelklicken Sie auf "Form1.cs", um sie im Designer zu öffnen, wenn er nicht bereits geöffnet ist.  
  
4.  In der **Toolbox**, `Counter` Steuerelement angezeigt werden soll, der **Allgemein** Abschnitt.  
  
5.  Ziehen Sie eine `Counter` in Ihr Formular, und wählen Sie es. Die `Value`, `Message`, und `ShowReset` Eigenschaften werden angezeigt, der **Eigenschaften** Fenster zusammen mit den Eigenschaften, die vom geerbt werden <xref:System.Windows.Forms.UserControl>.  
  
6.  Legen Sie die `Message`-Eigenschaft auf `Count:` fest.  
  
7.  Ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement auf das Formular, und legen Sie dann die Namen und Eigenschaften der Schaltfläche auf `Test`.  
  
8.  Doppelklicken Sie auf die Schaltfläche, um "Form1.cs" in der Codeansicht zu öffnen und einen Click-Ereignishandler zu erstellen.  
  
9. Rufen Sie in dem Click-Ereignishandler `counter1.Increment()`.  
  
10. In der Konstruktorfunktion, nach dem Aufruf von `InitializeComponent`, Typ `counter1``.``Incremented +=` , und drücken Sie dann zweimal die Registerkarte ".  
  
     Visual Studio generiert einen Handler auf Formularebene für die `counter1.Incremented` Ereignis.  
  
11. Markieren Sie die `Throw` -Anweisung in der Ereignishandler Typ `mbox`, und drücken Sie dann die Registerkarte zweimal, um ein Meldungsfeld aus dem Mbox Codeausschnitt zu generieren.  
  
12. Fügen Sie in der nächsten Zeile die folgenden `if` / `else` Block, um die Sichtbarkeit der Festlegen der `Reset` Schaltfläche.  
  
    ```csharp  
    if (counter1.Value < 5) counter1.ShowReset = false;  
    else counter1.ShowReset = true;  
    ```  
  
13. Drücken Sie F5.  
  
     Das Formular wird geöffnet. Die `Counter` -Steuerelement zeigt den folgenden Text.  
  
     **Anzahl: 0**  
  
14. Klicken Sie auf **Test**.  
  
     Der Zähler erhöht und die Visual Studio zeigt ein Meldungsfenster an.  
  
15. Das Meldungsfeld zu schließen.  
  
     Die **zurücksetzen** Schaltfläche wird ausgeblendet.  
  
16. Klicken Sie auf **Test** bis der Zähler erreicht **5** jedes Mal durch das Schließen der Nachricht, die Felder.  
  
     Die **zurücksetzen** Schaltfläche wird erneut angezeigt.  
  
17. Klicken Sie auf **Zurücksetzen**.  
  
     Der Leistungsindikator wird zurückgesetzt, um **0**.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Beim Erstellen eines **Toolbox** -Steuerelements erstellt Visual Studio eine Datei namens *Projektname*.vsix im Ordner „\bin\debug\“ des Projekts. Sie können das Steuerelement bereitstellen, indem Sie die VSIX-Datei in ein Netzwerk oder auf eine Website hochladen. Wenn ein Benutzer die VSIX-Datei öffnet, wird das Steuerelement installiert und in Visual Studio hinzugefügt **Toolbox** auf dem Computer des Benutzers. Alternativ können Sie die VSIX-Datei zum Hochladen der [Visual Studio Gallery](http://go.microsoft.com/fwlink/?LinkID=123847) Website aus, damit Benutzer diesen finden können, durch Navigieren der **Extras / Erweiterungen und Updates** Dialogfeld.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern von anderen Teilen von Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Erstellen eines WPF-Toolbox-Steuerelements](../extensibility/creating-a-wpf-toolbox-control.md)   
 [Erweitern von anderen Teilen von Visual Studio](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Grundlagen für das Entwickeln von Windows Forms-Steuerelementen](/dotnet/framework/winforms/controls/windows-forms-control-development-basics)