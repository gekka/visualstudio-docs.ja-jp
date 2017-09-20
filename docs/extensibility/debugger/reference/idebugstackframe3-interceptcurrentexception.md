---
title: IDebugStackFrame3::InterceptCurrentException | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugStackFrame3::InterceptCurrentException
helpviewer_keywords:
- IDebugStackFrame3::InterceptCurrentException
ms.assetid: 116c7324-7645-4c15-b484-7a5cdd065ef5
caps.latest.revision: 9
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
ms.openlocfilehash: 009c775af66f457c41342d2ce6c8b20288052f6e
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="idebugstackframe3interceptcurrentexception"></a>IDebugStackFrame3::InterceptCurrentException
Called by the debugger on the current stack frame when it wants to intercept the current exception.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT InterceptCurrentException(  
   INTERCEPT_EXCEPTION_ACTION dwFlags,  
   UINT64*                    pqwCookie  
);  
```  
  
```csharp  
int InterceptCurrentException(  
   uint dwFlags,   
   out  ulong pqwCookie  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 `dwFlags`  
 [in] Specifies different actions. Currently, only the [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md) value `IEA_INTERCEPT` is supported and must be specified.  
  
 `pqwCookie`  
 [out] Unique value identifying a particular exception.  
  
## <a name="return-value"></a>Return Value  
 If successful, returns S_OK; otherwise, returns an error code.  
  
 The following are the most common error returns.  
  
|Error|Description|  
|-----------|-----------------|  
|`E_EXCEPTION_CANNOT_BE_INTERCEPTED`|The current exception cannot be intercepted.|  
|`E_EXCEPTION_CANNOT_UNWIND_ABOVE_CALLBACK`|The current execution frame hasn't been searched for a handler yet.|  
|`E_INTERCEPT_CURRENT_EXCEPTION_NOT_SUPPORTED`|This method is not supported for this frame.|  
  
## <a name="remarks"></a>Remarks  
 When an exception is thrown, the debugger gains control from the run time at key points during the exception handling process. During these key moments, the debugger can ask the current stack frame if the frame wants to intercept the exception. In this way, an intercepted exception is essentially an on-the-fly exception handler for a stack frame, even if that stack frame doesn't have an exception handler (for example, a try/catch block in the program code).  
  
 When the debugger wants to know if the exception should be intercepted, it calls this method on the current stack frame object. This method is responsible for handling all details of the exception. If the [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md) interface is not implemented or the `InterceptStackException` method returns any error, then the debugger continues processing the exception normally.  
  
> [!NOTE]
>  Exceptions can be intercepted only in managed code, that is, when the program being debugged is running under the .NET run time. Of course, third-party language implementers can implement `InterceptStackException` in their own debug engines if they so choose.  
  
 After the interception is complete, an [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) is signaled.  
  
## <a name="see-also"></a>See Also  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [INTERCEPT_EXCEPTION_ACTION](../../../extensibility/debugger/reference/intercept-exception-action.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)