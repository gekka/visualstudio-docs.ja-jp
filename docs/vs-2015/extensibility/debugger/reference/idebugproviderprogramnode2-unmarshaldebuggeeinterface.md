---
title: IDebugProviderProgramNode2::UnmarshalDebuggeeInterface |Microsoft Docs
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
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
helpviewer_keywords:
- IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
ms.assetid: 2e4653c5-10f1-493c-9973-f31d266c5d48
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 94b40ba62e079fbc70fa4f9c7f9560e79bcc0a29
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51771976"
---
# <a name="idebugproviderprogramnode2unmarshaldebuggeeinterface"></a>IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

プロセスの境界を越えて、指定したインターフェイスを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT UnmarshalDebuggeeInterface(  
   REFIID riid,  
   void** ppvObject  
);  
```  
  
```csharp  
int UnmarshalDebuggeeInterface(  
   ref Guid   riid,  
   out IntPtr ppvObject  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 [in]インターフェイスの GUID を取得します。  
  
 `ppvObject`  
 [out]必要なインターフェイスを実装するオブジェクトを返します。 [C++] これは、必要なインターフェイスの型に直接キャストできます。 [C#] を使用して、<xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A>必要なインターフェイスを取得します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 デバッグ エンジンがで実行されているときに、このメソッドを使用、[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]プロセス領域とデバッグ中のプログラムが、独自のプロセス空間内で実行されています。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)

