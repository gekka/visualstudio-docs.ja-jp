---
title: "IDebugCanStopEvent2::GetReason |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
caps.latest.revision: 11
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
ms.openlocfilehash: b5d4c50b407406ea9a5d878decf859b8ab70863d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/06/2017

---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
デバッグ エンジン (DE) が停止する理由の理由を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT GetReason(   
   CANSTOP_REASON* pcr  
);  
```  
  
```csharp  
int GetReason(   
   out enum_CANSTOP_REASON pcr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pcr`  
 [out]値を返します、 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)このイベントの理由を説明する列挙体です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合を返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 このメソッドと通常呼ばれる前に、 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)メソッドの呼び出し元は、0 以外を渡すかどうかを特定できるように (`TRUE`) に、`IDebugCanStopEvent2::CanStop`メソッドです。  
  
 停止の理由には、いずれかを指定できます`CANSTOP_ENTRYPOINT`、エントリ ポイントに達して、DE つまりまたは`CANSTOP_STEPIN`関数にステップ インは、DE 意味します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)