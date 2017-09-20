---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
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
ms.openlocfilehash: 4102336616511239bbf3249fc3dc5552a4e9de40
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
Retrieves a managed code interface that represents the value associated with this alias.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 `ppUnk`  
 [out] `IUnknown` interface that represents the value associated with this alias. This interface can be queried for the `ICorDebugValue` interface.  
  
## <a name="return-value"></a>Return Value  
 If successful, returns S_OK; otherwise, returns an error code.  
  
## <a name="remarks"></a>Remarks  
 This method applies only to managed values (the `ICorDebugValue` is an interface available in the [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] and is defined in the [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK in the cordebug.idl file).  
  
## <a name="see-also"></a>See Also  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)