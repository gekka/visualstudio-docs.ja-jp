---
title: IEnumDebugObjects::Reset |Microsoft Docs
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
- IEnumDebugObjects::Reset
helpviewer_keywords:
- IEnumDebugObjects::Reset method
ms.assetid: 4a245e47-cc39-4177-b83d-083ea0e3190f
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aac922e8f0916b7d26e3f84a66cc1dd865310d53
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51757746"
---
# <a name="ienumdebugobjectsreset"></a>IEnumDebugObjects::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このメソッドは、最初の要素を列挙型をリセットします。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Reset(void);  
```  
  
```csharp  
int Reset();  
```  
  
#### <a name="parameters"></a>パラメーター  
 なし  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このメソッドが呼び出された後、次回の呼び出し[次](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)列挙体の最初の要素を返します。  
  
## <a name="see-also"></a>関連項目  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)   
 [次へ](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)

