---
title: IDebugProgramPublisher2::PublishProgram |Microsoft Docs
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
- IDebugProgramPublisher2::PublishProgram
helpviewer_keywords:
- IDebugProgramPublisher2::PublishProgram
ms.assetid: 92ff63f0-e869-4040-b3ae-b2c899e708ff
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 53ddd111710eccb14fba2a6d2a4a9a3648c51f4e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51755199"
---
# <a name="idebugprogrampublisher2publishprogram"></a>IDebugProgramPublisher2::PublishProgram
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

この方法は、デバッグ エンジン (DEs) を利用プログラムおよびセッション デバッグ マネージャーになります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   LPCOLESTR        szFriendlyName,  
   IUnknown*        pDebuggeeInterface  
);  
```  
  
```csharp  
int PublishProgram(  
   CONST_GUID_ARRAY Engines,  
   string           szFriendlyName,  
   object           pDebuggeeInterface  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Engines`  
 [in]DEs を開始したり、このプログラムにアタッチされる Guid の配列。  
  
 `szFriendlyName`  
 [in]プログラムのフレンドリーな名前（これはメニューまたはユーザーに表示されるダイアログに表示されます）。  
  
 `pDebuggeeInterface`  
 [in]`IUnknown`プログラム インターフェイス (この値は、プログラムを一意に識別するために cookie として使用されますこの同じの値は、プログラムを"非公開"に使用されます)。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 プログラムをデバッグに使用できなくするには、呼び出す[UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)

