---
title: .NET メモリの割り当てビュー | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.allocation
helpviewer_keywords:
- performance reports, allocation view
- Allocations view
- profiling tools, Allocation view
- profiling tools reports, Allocation view
ms.assetid: 01eb876e-c413-4516-977b-4f896929e8a6
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e53fe27148901bc4af78f9b607c0e3a70ba4b91
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47544840"
---
# <a name="net-memory-allocations-view"></a>.NET メモリの割り当てビュー
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[.NET メモリの割り当てビュー](https://docs.microsoft.com/visualstudio/profiling/dotnet-memory-allocations-view)します。  
  
割り当てビューには、プロファイリング実行中に作成された型が一覧表示されます。 それぞれの型が、型の割り当てが発生する原因となった関数の実行パスを表示するコール ツリーのルート ノードに該当します。  
  
 型行のデータには、プロファイリング実行で作成された型のオブジェクトの総数とその型のオブジェクトに割り当てられた総バイト数が表示されます。 型の包括値と排他値は常に同じです。  
  
-   包括値は、コール ツリーの親関数によって呼び出された関数とその子関数のインスタンスで作成されたオブジェクトの値です。  
  
-   排他値は、親関数によって呼び出された関数によって直接作成されたオブジェクトの値です。 子関数で作成されたオブジェクトは含まれません。  
  
 関数のデータは、親型のオブジェクトに対して作成されたオブジェクト数と割り当てられたバイト数を示します。  
  
## <a name="highlighting-the-execution-hot-path"></a>実行ホット パスの強調表示  
 親型のほとんどのオブジェクトを作成したコール ツリーの実行パスを見つけることができます。  
  
-   最もアクティブなパスを表示するには、型または関数を右クリックし、**[ホット パスの展開]** をクリックします。  
  
|Column|説明|  
|------------|-----------------|  
|**Name**|割り当てられた型または関数の名前です。|  
|**プロセス ID**|プロファイリング実行のプロセス ID (PID) です。|  
|**プロセス名**|プロセスの名前です。|  
|**モジュール名**|型または関数を含むモジュールの名前です。|  
|**モジュール パス**|型または関数を含むモジュールのパスです。|  
|**ソース ファイル**|型または関数の定義を含むソース ファイルです。|  
|**関数行番号**|ソース ファイルでのこの型定義または関数の開始行番号です。|  
|**レベル**|データが型のデータであるか、関数のデータであるかを示します。|  
|**割り当て数 (子を含む)**|-   関数の場合、その関数によって作成された、親型のオブジェクトの合計数。 この数には、子関数で作成されたオブジェクトが含まれます。<br />-   型の場合、作成された、その型のインスタンスの合計数。|  
|**割り当て % (子を含む)**|-   関数の場合、プロファイリング実行で作成されたすべてのオブジェクトに対する、その関数による親型の包括的割り当てであったオブジェクトの割合。<br />-   型の場合、プロファイリング実行で作成されたオブジェクトの合計数に対する、その型のインスタンスであったオブジェクトの割合。|  
|**割り当て数 (関数のみ)**|-   関数の場合、その関数が呼び出し履歴の最上位で直接実行されたときに作成されたオブジェクトの数。 この数には、子関数で作成されたオブジェクトが含まれません。<br />-   型の場合、作成された、その型のインスタンスの合計数。|  
|**割り当て % (関数のみ)**|-   関数の場合、プロファイリング実行で作成されたすべてのオブジェクトに対する、その関数による親型の排他的割り当てであったオブジェクトの割合。<br />-   型の場合、プロファイリング実行で作成されたオブジェクトの合計数に対する、その型のインスタンスであったオブジェクトの割合。|  
|**割り当てバイト数 (子を含む)**|-   関数の場合、親型のオブジェクトの関数によって割り当てられたメモリのバイト数。 この数には、その子関数によって割り当てられたメモリが含まれます。<br />-   型の場合、その型のインスタンスのプロファイリング実行で割り当てられた総バイト数。|  
|**割り当てバイト数 % (子を含む)**|-   関数の場合、プロファイリング実行で割り当てられたすべてのメモリに対する、その関数による親型の包括的割り当てであったメモリの割合。<br />-   型の場合、プロファイリング実行で割り当てられたすべてのメモリに対する、その型のインスタンスに割り当てられたメモリの割合。|  
|**割り当てバイト数 (関数のみ)**|-   関数の場合、親型のオブジェクトの関数によって割り当てられたメモリのバイト数。 この数には、その子関数によって割り当てられたメモリが含まれません。<br />-   型の場合、その型のインスタンスのプロファイリング実行で割り当てられた総バイト数。|  
|**割り当てバイト数 % (関数のみ)**|-   関数の場合、プロファイリング実行で割り当てられたすべてのメモリに対する、その関数による親型の排他的割り当てであったメモリの割合。<br />-   型の場合、プロファイリング実行で割り当てられたすべてのメモリに対する、その型のインスタンスに割り当てられたメモリの割合。|


