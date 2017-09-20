---
title: IDebugMethodField::EnumParameters | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
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
ms.openlocfilehash: 14ba9e70c2caf4073a594fe657348ef10b70191d
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
Creates an enumerator for the parameters of the method.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>Parameters  
 `ppParams`  
 [out] Returns an [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) object representing the list of parameters to the method; otherwise, returns a null value if there are no parameters.  
  
## <a name="return-value"></a>Return Value  
 If successful, returns S_OK or returns S_FALSE if there are no parameters. Otherwise, returns an error code.  
  
## <a name="remarks"></a>Remarks  
 Each element is an [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) object representing different types of parameters. Call the [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) method on each object to determine exactly what kind of parameter the object represents.  
  
 A parameter includes both its variable name and its type. The first parameter to a class method is typically the "this" pointer.  
  
 If only the types of the parameters is needed, call the [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) method.  
  
## <a name="see-also"></a>See Also  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)