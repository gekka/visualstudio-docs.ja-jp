---
title: DEBUGREF_INFO_FLAGS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUGREF_INFO_FLAGS
helpviewer_keywords:
- DEBUGREF_INFO_FLAGS enumeration
ms.assetid: 1b043327-302a-4f6d-b51d-f94f9d7c7f9d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9957b0aaf81048c5040e3f7ff54f3fa9be742dc1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49858564"
---
# <a name="debugrefinfoflags"></a>DEBUGREF_INFO_FLAGS
デバッグの参照オブジェクトを取得するには、どのような情報を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
typedef DWORD DEBUGREF_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_DEBUGREF_INFO_FLAGS {   
   DEBUGREF_INFO_NAME             = 0x00000001,  
   DEBUGREF_INFO_TYPE             = 0x00000002,  
   DEBUGREF_INFO_VALUE            = 0x00000004,  
   DEBUGREF_INFO_ATTRIB           = 0x00000008,  
   DEBUGREF_INFO_REFTYPE          = 0x00000010,  
   DEBUGREF_INFO_REF              = 0x00000020,  
   DEBUGREF_INFO_VALUE_AUTOEXPAND = 0x00010000,  
   DEBUGREF_INFO_NONE             = 0x00000000,  
   DEBUGREF_INFO_ALL              = 0xffffffff  
};  
```  
  
## <a name="members"></a>メンバー  
 DEBUGREF_INFO_NAME  
 初期化/使用、`bstrName`フィールド構造にします。  
  
 DEBUGREF_INFO_TYPE  
 初期化/使用、`bstrType`フィールド構造にします。  
  
 DEBUGREF_INFO_VALUE  
 初期化/使用、`bstrValue`フィールド構造にします。  
  
 DEBUGREF_INFO_ATTRIB  
 初期化/使用、`dwAttrib`フィールド構造にします。  
  
 DEBUGREF_INFO_REFTYPE  
 初期化/使用、`dwRefType`フィールド構造にします。  
  
 DEBUGREF_INFO_REF  
 初期化/使用、`pReference`フィールド構造にします。  
  
 DEBUGREF_INFO_VALUE_AUTOEXPAND  
 [値] フィールドは、この種類のオブジェクトの使用可能な場合、自動拡張値を含める必要があります。  
  
 DEBUGREF_INFO_NONE  
 フラグが設定されていないことを示します。  
  
 DEBUGREF_INFO_ALL  
 フラグのマスクを示します。  
  
## <a name="remarks"></a>Remarks  
 これらのフラグに渡される、 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)と[GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)のどのフィールドを示すメソッド、 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)構造体が初期化するには。  
  
 使用、`dwFields`のメンバー、`DEBUG_REFERENCE_INFO`構造体を構造体が返されるときにどのフィールドが使用し、有効なレポートを示します。  
  
 これらの値は、演算と組み合わせることがあります`OR`します。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)