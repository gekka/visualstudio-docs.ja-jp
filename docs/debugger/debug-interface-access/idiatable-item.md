---
title: Idiatable::item |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 476e4d01ed6e092936fc2d9bc7b8e264215e21dc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950057"
---
# <a name="idiatableitem"></a>IDiaTable::Item
テーブル内の指定されたエントリへの参照を取得します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `index`  
 [in]テーブルのエントリに 0 の範囲内のインデックス`count`-1 の場合、`count`によって返される、 [idiatable::get_count](../../debugger/debug-interface-access/idiatable-get-count.md)メソッド。  
  
 `element`  
 [out]返します、`IUnknown`指定したテーブルのエントリを表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 テーブルは、オブジェクトのコレクションを表します。 によって、これらのオブジェクト要素のパラメーターは、適切なインターフェイスにキャストできます。 たとえば、テーブルに含まれる[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)オブジェクトに要素のパラメーターをキャストすることができ、`IDiaSegment`インターフェイス。  
  
 呼び出す方が一般的ですが、`QueryInterface`メソッドで、 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)適切な列挙子インターフェイスのためのインターフェイスし、列挙子の特定のメソッドを使用してテーブルの内容にアクセスします。 参照してください、 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)例については、インターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiatable::get_count](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)