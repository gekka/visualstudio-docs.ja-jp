---
title: IDebugEngineProgram2::Stop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEngineProgram2::Stop
helpviewer_keywords:
- IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: 8
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
ms.openlocfilehash: e8a1d5fd980d50326c11101acc54146e4de03258
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
Stops all threads running in this program.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## <a name="remarks"></a>Remarks  
 This method is called when this program is being debugged in a multi-program environment. When a stopping event from some other program is received, this method is called on this program. The implementation of this method should be asynchronous; that is, not all threads should be required to be stopped before this method returns. The implementation of this method may be as simple as calling the [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) method on this program.  
  
 No debug event is sent in response to this method.  
  
## <a name="see-also"></a>See Also  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)