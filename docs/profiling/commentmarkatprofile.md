---
title: CommentMarkAtProfile | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- CommentMarkAtProfile
- CommentMarkAtProfileA
ms.assetid: 04294ca3-bf9c-4c76-86f1-898c2140de27
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 63bd01f6ad180c85e48c51925de094df94aaa335
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2018
---
# <a name="commentmarkatprofile"></a>CommentMarkAtProfile
Die `CommentMarkAtProfile`-Methode fügt der VSP-Datei einen Zeitstempelwert, eine numerische Markierung und eine Kommentarzeichenfolge hinzu. Der Zeitstempelwert kann verwendet werden, um externe Ereignisse zu synchronisieren. Damit die Markierung und der Kommentar eingefügt werden, muss die Profilerstellung für den Thread, der die Funktion CommentMarkAtProfile enthält, auf ON festgelegt sein.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
PROFILE_COMMAND_STATUS PROFILERAPI CommentMarkAtProfile (  
                                   __int64 dnTimestamp,  
                                   long lMarker,  
                                   LPCTSTR szComment);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dnTimestamp`  
  
 Eine ganze 64-Bit-Zahl, die einen Zeitstempelwert darstellt.  
  
 `lMarker`  
  
 Die numerische Markierung, die eingefügt werden soll. Die Markierung muss größer oder gleich 0 (null) sein.  
  
 `szComment`  
  
 Ein Zeiger auf die einzufügende Textzeichenfolge. Die Zeichenfolge muss einschließlich des NULL-Abschlusszeichens weniger als 256 Zeichen enthalten.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Die Funktion gibt mithilfe der **PROFILE_COMMAND_STATUS**-Enumeration einen Erfolg oder Fehler an. Einer der folgenden Werte kann zurückgegeben werden:  
  
|Enumerator|description|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Der Parameter ist kleiner oder gleich 0 (null). Diese Werte sind reserviert. Die Markierung und der Kommentar werden nicht aufgezeichnet.|  
|MARK_ERROR_MODE_NEVER|Der Profilerstellungsmodus wurde beim Aufruf der Funktion auf NEVER festgelegt. Die Markierung und der Kommentar werden nicht aufgezeichnet.|  
|MARK_ERROR_MODE_OFF|Der Profilerstellungsmodus wurde beim Aufruf der Funktion auf OFF festgelegt. Die Markierung und der Kommentar werden nicht aufgezeichnet.|  
|MARK_ERROR_NO_SUPPORT|In diesem Kontext werden keine Markierungen unterstützt. Die Markierung und der Kommentar werden nicht aufgezeichnet.|  
|MARK_ERROR_OUTOFMEMORY|Der Arbeitsspeicher war nicht verfügbar, um das Ereignis aufzuzeichnen. Die Markierung und der Kommentar werden nicht aufgezeichnet.|  
|MARK_TEXTTOOLONG|Die Zeichenfolge überschreitet die maximale Länge von 256 Zeichen. Die Kommentarzeichenfolge wurde abgeschnitten, und die Markierung und der Kommentar werden aufgezeichnet.|  
|MARK_OK|Bei Erfolg wird MARK_OK zurückgegeben.|  
  
## <a name="remarks"></a>Hinweise  
 Der Profilerstellungsstatus für den Thread, der die Funktion „Mark profile“ (Profil markieren) enthält, muss auf ON festgelegt sein, wenn Markierungen und Kommentare mit dem Mark-Befehl oder mit API-Funktionen (CommentMarkAtProfile, CommentMarkProfile, oder MarkProfile) eingefügt werden. Profilmarkierungen sind im Bereich global. Wenn beispielsweise eine Profilmarkierung in einen Thread eingefügt wird, kann diese verwendet werden, um den Anfang oder das Ende eines Datensegments in jedem Thread der VSP-Datei zu markieren.  
  
> [!IMPORTANT]
>  CommentMarkAtProfile-Methoden sollten nur mit der Instrumentierung verwendet werden.  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Funktionsinformationen  
  
|||  
|-|-|  
|**Header**|Enthält VSPerf.h|  
|**Bibliothek**|Verwendet VSPerf.lib|  
|**Unicode**|Als CommentMarkAtProfileW (Unicode) und CommentMarkAtProfileA (ANSI) implementiert.|  
  
## <a name="example"></a>Beispiel  
 Der folgende Code stellt die Verwendung des generischen CommentMarkAtProfile-Funktionsaufrufs dar. In diesem Beispiel wird vorausgesetzt, dass die Win32-Zeichenfolgenmakros und die Compilereinstellungen für ANSI verwendet werden, um zu bestimmen, ob der Code die ANSI-Funktion abruft.  
  
```cpp  
void ExerciseCommentMarkAtProfile(void)  
{  
    // Declare and initalize variables to pass to   
    // CommentMarkAtProfile.  The values of these   
    // parameters are assigned based on the needs   
    // of the code; and for the sake of simplicity  
    // in this example, the variables are assigned  
    // arbitrary values.  
    int64 timeStamp = 0x1111;  
    long markId = 01;  
    TCHAR * markText = TEXT("Exercising CommentMarkAtProfile...");  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare MarkOperationResult Enumerator.    
    // Holds return value from call to CommentMarkAtProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    markResult = CommentMarkAtProfile(  
        timeStamp,  
        markId,  
        markText);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("CommentMarkAtProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
    pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zu Profiler-APIs in Visual Studio (systemeigen)](../profiling/visual-studio-profiler-api-reference-native.md)