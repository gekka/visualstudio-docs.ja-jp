---
title: SccRename Function | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccRename
helpviewer_keywords:
- SccRename function
ms.assetid: b467ade6-a1db-4c0b-b60f-7850ec4f79eb
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 58a500fe775bb7837e6132bd918be63fb68b7fe2
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="sccrename-function"></a>SccRename Function
This function renames a file in the source control system.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
SCCRTN SccRename(  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName,  
   LPCSTR lpNewName  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 pvContext  
 [in] The source control plug-in context structure.  
  
 hWnd  
 [in] A handle to the IDE window that the source control plug-in can use as a parent for any dialog boxes that it provides.  
  
 lpFileName  
 [in] The fully qualified file name of the file being renamed.  
  
 lpNewName  
 [in] The fully qualified new name. If the directory path is different, then the file has moved from one subdirectory to another.  
  
## <a name="return-value"></a>Return Value  
 The source control plug-in implementation of this function is expected to return one of the following values:  
  
|Value|Description|  
|-----------|-----------------|  
|SCC_OK|The renaming operation completed successfully.|  
|SCC_E_PROJNOTOPEN|The project is not open under source control.|  
|SCC_E_FILENOTCONTROLLED|The file is not under source control.|  
|SCC_E_ACCESSFAILURE|There was a problem accessing the source control system, probably due to network or contention issues.|  
|SCC_E_NOTAUTHORIZED|The user is not authorized to complete this operation.|  
|SCC_E_COULDNOTCREATEPROJECT|The project could not be created as part of the renaming process.|  
|SCC_E_OPNOTPERFORMED|The operation was not performed.|  
|SCC_E_NONSPECIFICERROR|An unspecified or general error occurred.|  
  
## <a name="remarks"></a>Remarks  
 This function can be used to rename a file or move it from one location to another in the source control system. The source control plug-in should not attempt to access the file on disk. It is the IDE's responsibility to rename the local file.  
  
## <a name="see-also"></a>See Also  
 [Source Control Plug-in API Functions](../extensibility/source-control-plug-in-api-functions.md)