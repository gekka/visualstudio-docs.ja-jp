---
title: METADATA_TYPE |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- METADATA_TYPE
helpviewer_keywords:
- METADATA_TYPE structure
ms.assetid: 2d8b78f6-0aef-4d79-809a-cff9b2c24659
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8e8b5cc4c0a067a8add062d2003e991eb8672af5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51732150"
---
# <a name="metadatatype"></a>METADATA_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

この構造体には、メタデータから取得したフィールドの種類に関する情報を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
typedef struct _tagTYPE_METADATA {  
   ULONG32  ulAppDomainID;  
   GUID     guidModule;  
   _mdToken tokClass;  
} METADATA_TYPE;  
```  
  
```csharp  
public struct METADATA_TYPE {  
   public uint ulAppDomainID;  
   public Guid guidModule;  
   public int  tokClass;  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 ulAppDomainID  
 シンボルが元のアプリケーションの ID。 これは、アプリケーションのインスタンスを一意に識別するに使用されます。  
  
 guidModule  
 このフィールドが含まれるモジュールの GUID です。  
  
 tokClass  
 この型のメタデータ トークン ID。  
  
 [C++]`_mdToken`は、 `typedef` 32 ビット`int`します。  
  
## <a name="remarks"></a>Remarks  
 共用体の一部としてこの構造体が表示されます、 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)ときに構造体、`dwKind`のフィールド、`TYPE_INFO`構造に設定されている`TYPE_KIND_METADATA`(からの値、 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)列挙型)。  
  
 `tokClass`値が型を一意に識別するメタデータ トークン。 メタデータ トークン ID の上位ビットを解釈する方法の詳細については、次を参照してください。、`CorTokenType`で corhdr.h ファイルで列挙、 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)

