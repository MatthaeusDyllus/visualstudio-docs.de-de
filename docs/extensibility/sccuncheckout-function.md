---
title: SccUncheckout Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccUncheckout
helpviewer_keywords:
- SccUncheckout function
ms.assetid: 6d498b70-29c7-44b7-ae1c-7e99e488bb09
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c363da795e588963c234af05a856f3352a7b2815
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="sccuncheckout-function"></a>SccUncheckout-Funktion
Diese Funktion macht einen vorherigen Auscheckvorgang, wiederherstellen und den Inhalt der ausgewählten Datei oder Dateien in den Zustand vor dem Auschecken rückgängig. Alle an der Datei seit dem Auschecken vorgenommenen Änderungen gehen verloren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
SCCRTN SccUncheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 pvContext  
 [in] Datenquellen-Steuerelement-Plug-in-Context-Struktur.  
  
 hWnd  
 [in] Ein Handle für die IDE-Fenster, das das Quellsteuerelement-Plug-in als übergeordnetes Element für alle Dialogfelder verwenden kann, die es bereitstellt.  
  
 nFiles  
 [in] Anzahl der angegebenen Dateien in den `lpFileNames` Array.  
  
 lpFileNames  
 [in] Array der Namen von voll gekennzeichneter lokaler Pfad von Dateien für das Auschecken rückgängig gemacht.  
  
 fOptions  
 [in] Befehl Flags (nicht verwendet).  
  
 pvOptions  
 [in] Quellcodeverwaltungs-plug-in spezifischen Optionen.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Source Control-Plug-in-Implementierung dieser Funktion muss einen der folgenden Werte zurückgeben:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|SCC_OK|Auschecken rückgängig war erfolgreich.|  
|SCC_E_FILENOTCONTROLLED|Die ausgewählte Datei ist nicht unter quellcodeverwaltung.|  
|SCC_E_ACCESSFAILURE|Es wurde ein Problem, das Zugriff auf das Quellcodeverwaltungssystem, wahrscheinlich aufgrund eines Netzwerk-oder Konflikte. Eine Wiederholung wird empfohlen.|  
|SCC_E_NONSPECIFICERROR|Unspezifischen Fehlers. Rückgängig: Auschecken war nicht erfolgreich.|  
|SCC_E_NOTCHECKEDOUT|Der Benutzer besitzt nicht die Datei ausgecheckt.|  
|SCC_E_NOTAUTHORIZED|Der Benutzer ist nicht zulässig, um diesen Vorgang auszuführen.|  
|SCC_E_PROJNOTOPEN|Das Projekt wurde nicht aus der quellcodeverwaltung geöffnet.|  
|SCC_I_OPERATIONCANCELED|Der Vorgang wurde vor dem Abschluss abgebrochen.|  
  
## <a name="remarks"></a>Hinweise  
 Nach diesem Vorgang die `SCC_STATUS_CHECKEDOUT` und `SCC_STATUS_MODIFIED` Flags werden sowohl für die Dateien für die das Auschecken rückgängig durchgeführt wurde gelöscht werden.  
  
## <a name="see-also"></a>Siehe auch  
 [API-Funktionen von Quellcodeverwaltungs-Plug-Ins](../extensibility/source-control-plug-in-api-functions.md)