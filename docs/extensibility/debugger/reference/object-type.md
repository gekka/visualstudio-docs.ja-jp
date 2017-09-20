---
title: OBJECT_TYPE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OBJECT_TYPE
helpviewer_keywords:
- OBJECT_TYPE enumeration
ms.assetid: c4d246f9-8a98-44ec-b2bb-ff5c684f668e
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
ms.openlocfilehash: 5cb562b54d088e5f5c5fdb300a8f897e35f82f17
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="objecttype"></a>OBJECT_TYPE
Specifies the type of an object from the expression evaluator.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
typedef DWORD OBJECT_TYPE;  
```  
  
```csharp  
public enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
```  
  
## <a name="members"></a>Members  
 OBJECT_TYPE_BOOLEAN  
 Indicates that the object is a Boolean.  
  
 OBJECT_TYPE_CHAR  
 Indicates that the object is a character.  
  
 OBJECT_TYPE_I1  
 Indicates that the object is a one-byte signed integer.  
  
 OBJECT_TYPE_U1  
 Indicates that the object is a one-byte unsigned integer.  
  
 OBJECT_TYPE_I2  
 Indicates that the object is a two-byte signed integer.  
  
 OBJECT_TYPE_U2  
 Indicates that the object is a two-byte unsigned integer.  
  
 OBJECT_TYPE_I4  
 Indicates that the object is a four-byte signed integer.  
  
 OBJECT_TYPE_U4  
 Indicates that the object is a four-byte unsigned integer.  
  
 OBJECT_TYPE_I8  
 Indicates that the object is an eight-byte signed integer.  
  
 OBJECT_TYPE_U8  
 Indicates that the object is an eight-byte unsigned integer.  
  
 OBJECT_TYPE_R4  
 Indicates that the object is a four-byte floating-point number.  
  
 OBJECT_TYPE_R8  
 Indicates that the object is an eight-byte floating-point number.  
  
 OBJECT_TYPE_OBJECT  
 Indicates that the object is an object.  
  
 OBJECT_TYPE_NULL  
 Indicates that the object is NULL.  
  
 OBJECT_TYPE_CLASS  
 Indicates that the object is a class.  
  
## <a name="remarks"></a>Remarks  
 Passed as an argument to the [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md) and [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md) methods.  
  
## <a name="requirements"></a>Requirements  
 Header: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>See Also  
 [Enumerations](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)   
 [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)