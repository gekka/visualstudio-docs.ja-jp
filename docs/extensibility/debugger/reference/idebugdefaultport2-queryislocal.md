---
title: IDebugDefaultPort2::QueryIsLocal |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2::QueryIsLocal
helpviewer_keywords:
- IDebugDefaultPort2::QueryIsLocal
ms.assetid: 1a42e774-c6ed-419a-a0e3-cab5778652ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2ed411d632df544d47b376e59bc59b7331d8aa91
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49901808"
---
# <a name="idebugdefaultport2queryislocal"></a>IDebugDefaultPort2::QueryIsLocal
このメソッドでは、このポートは、ローカル コンピューター上にかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>戻り値  
 返します`S_OK`かどうか、このポートは (呼び出し元と同じコンピューター) 上のローカルまたは`S_FALSE`ポートが別のコンピューター上にある場合。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)