---
title: Idiasymbol::get_isaggregated |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isAggregated method
ms.assetid: 24d280ef-6ea3-4958-9418-4ad3ca7c67c1
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: db1d709395eb632d5e0136fdb9f67d7fa4a843eb
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51776097"
---
# <a name="idiasymbolgetisaggregated"></a>IDiaSymbol::get_isAggregated
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

データ シンボルが集計またはシンボルのコレクションの一部であるかどうかを指定するフラグを取得します。コンパイラでは、集計されたシンボルは個別のエンティティとして扱いますが、これらは実際に 1 つの大規模なシンボルの一部です。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_isAggregated(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pFlag`  
 [out]返します`TRUE`データが分割親シンボルからシンボルの集計の一部である場合を返しますそれ以外の場合、`FALSE`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外を返します`S_FALSE`またはエラー コード。  
  
> [!NOTE]
>  戻り値`S_FALSE`プロパティが、シンボルの使用可能なことを意味します。  
  
## <a name="remarks"></a>Remarks  
 [Idiasymbol::get_issplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)メソッドは`TRUE`の集計されたシンボルの親であるシンボル。  
  
## <a name="requirements"></a>必要条件  
  
|必要条件|説明|  
|-----------------|-----------------|  
|ヘッダー:|Dia2.h|  
|バージョン:|DIA SDK バージョン 8.0|  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)



