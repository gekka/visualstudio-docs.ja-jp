---
title: IDebugDisassemblyStream2::GetCodeLocationId |Microsoft Docs
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
- IDebugDisassemblyStream2::GetCodeLocationId
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fbc2890bf91274b825446383d0f1c3e768b315be
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51767368"
---
# <a name="idebugdisassemblystream2getcodelocationid"></a>IDebugDisassemblyStream2::GetCodeLocationId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

特定のコード コンテキストのコードの場所の識別子を返します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetCodeLocationId(   
   IDebugCodeContext2* pCodeContext,  
   UINT64*             puCodeLocationId  
);  
```  
  
```csharp  
int GetCodeLocationId(   
   IDebugCodeContext2 pCodeContext,  
   out ulong          puCodeLocationId  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pCodeContext`  
 [in][IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)を識別子に変換するオブジェクト。  
  
 `puCodeLocationId`  
 [out]コードの場所の識別子を返します。 「解説」を参照してください。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。 返します`E_CODE_CONTEXT_OUT_OF_SCOPE`コードのコンテキストが有効な場合が範囲外です。  
  
## <a name="remarks"></a>Remarks  
 コードの場所の識別子は、逆アセンブルをサポートしているデバッグ エンジン (DE) に固有です。 この場所の識別子は、DE によって、コード内の位置を追跡するために使用し、は通常、アドレスまたは何らかのオフセット。 唯一の要件はされている場合の 1 つの場所のコードのコンテキストが別の場所のコードのコンテキストより小さい最初のコード コンテキストの対応するコードの場所 id でもは 2 つ目のコードのコンテキストのコードの場所 id よりも小さい必要があります。  
  
 コードの場所の識別子のコードのコンテキストを取得する、 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)メソッド。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)

