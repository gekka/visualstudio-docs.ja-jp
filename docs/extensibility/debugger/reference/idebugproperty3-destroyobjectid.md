---
title: IDebugProperty3::DestroyObjectID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
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
ms.openlocfilehash: 65dfccafc071e2cb73fd530fa9b15ac1503e203a
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
Destroys the unique ID associated with this property, indicating that the caller no longer cares to identify this property uniquely from all other properties.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Return Value  
 If successful, returns `S_OK`; otherwise, returns an error code.  
  
## <a name="remarks"></a>Remarks  
 If the debug engine doesn't need to support unique IDs for a property (because it already tracks them uniquely internally), then it can simply return `E_NOTIMPL` for this method.  
  
 Unique IDs are created with a call to the [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) method when the caller wants to make sure that this property is uniquely identified among all other properties.  
  
## <a name="see-also"></a>See Also  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)