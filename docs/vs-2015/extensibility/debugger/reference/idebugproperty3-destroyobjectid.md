---
title: IDebugProperty3::DestroyObjectID |Microsoft Docs
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
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88eb8160e265c51e40b3d96be7e9c1d187e8a861
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51793192"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

呼び出し元がこのプロパティの他のすべてのプロパティから一意に識別する気不要になったことを示す、このプロパティに関連付けられた一意 ID を破棄します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 デバッグ エンジンは、(その既には追跡するために内部的には一意に) プロパティの一意の Id をサポートする必要がある場合、単に返すことができますし、`E_NOTIMPL`このメソッドにします。  
  
 呼び出しに一意の Id を作成、 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)メソッドの呼び出し元がこのプロパティは、その他のすべてのプロパティの間で一意に識別することを確認する場合。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)

