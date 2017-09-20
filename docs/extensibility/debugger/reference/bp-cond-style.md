---
title: BP_COND_STYLE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
caps.latest.revision: 10
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
ms.openlocfilehash: 3148f8a1aaa333c8ae0cf55bdc3bc4e218c0f574
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="bpcondstyle"></a>BP_COND_STYLE
Specifies the breakpoint condition style for pending and bound breakpoints.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
typedef DWORD BP_COND_STYLE;  
```  
  
```csharp  
public enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
```  
  
## <a name="members"></a>Members  
 BP_COND_NONE  
 Fires the breakpoint when the breakpoint's position is reached. No breakpoint condition specified.  
  
 BP_COND_WHEN_TRUE  
 Fires the breakpoint only when the conditional expression associated with the breakpoint evaluates to `true`.  
  
 BP_COND_WHEN_CHANGED  
 Fires the breakpoint only when the value of the conditional expression associated with the breakpoint has changed from its previous evaluation.  
  
## <a name="remarks"></a>Remarks  
 Used for the `styleCondition` member of the [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) structure.  
  
## <a name="requirements"></a>Requirements  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>See Also  
 [Enumerations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)