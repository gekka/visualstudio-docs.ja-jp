---
title: "モジュール ビュー - プロファイラー .NET メモリ サンプリング データ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "[モジュール] ビュー"
ms.assetid: 9c05b51a-8382-44cf-a8f7-3fabdd2e8f1b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# モジュール ビュー - プロファイラー .NET メモリ サンプリング データ
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

サンプリング メソッドを使用して収集された .NET メモリの割り当てデータのモジュール ビューは、メモリ データをプロファイリング実行中に実行されたモジュールごとにグループ化します。  各モジュールが、階層ツリーのルートです。  モジュールの関数が、モジュール ノードの下に一覧表示されます。  
  
 メモリを割り当てたステートメントのソース ファイルの行番号が関数ノードの下に一覧表示され、割り当てを実行した命令のアドレスは行ノードの下に一覧表示されます。  行データと命令データの包括値と排他値は常に同じです。  
  
|列|説明|  
|-------|--------|  
|**名前**|モジュール、関数、行番号、または命令アドレスの名前。|  
|**プロセス ID**|プロファイリング実行のプロセス ID \(PID\)。|  
|**プロセス名**|プロセスの名前。|  
|**\[モジュール名\]**|関数を含むモジュールの名前。|  
|**\[モジュール パス\]**|モジュールのパス。|  
|**\[ソース ファイル\]**|この関数の定義を含むソース ファイル。|  
|**\[関数行番号\]**|ソース ファイルのこの関数の開始行番号。|  
|**\[割り当て数 \(子を含む\)\]**|-   関数の場合、その関数によって作成されたオブジェクトの合計数。  この数値には、この関数によって呼び出された関数で作成されたオブジェクトが含まれます。<br />-   モジュールの場合、モジュールから少なくとも 1 つの関数が実行されている間に割り当てられたプロファイリング実行のオブジェクト数。  この数値には、モジュール関数によって呼び出された関数で作成されたオブジェクトが含まれます。<br />-   行または命令の場合、行または命令によって割り当てられたオブジェクトの総数。|  
|**\[割り当て % \(子を含む\)\]**|プロファイリング実行で割り当てられたすべてのオブジェクトに対する、モジュール、関数、行、または命令の包括的割り当てであったオブジェクトの割合。|  
|**\[割り当て数 \(関数のみ\)\]**|-   現在の関数の場合、関数が関数本体のコードを実行していたとき \(つまり呼び出し履歴の最上位に存在していたとき\) に作成されたオブジェクトの数。  この数値には、この関数によって呼び出された関数で作成されたオブジェクトは含まれません。<br />-   モジュールの場合、このモジュール内の関数における排他的割り当ての合計。<br />-   行または命令の場合、この行または命令によって作成されたオブジェクトの総数。|  
|**\[割り当て % \(関数のみ\)\]**|プロファイリング実行で割り当てられたすべてのオブジェクトに対する、そのモジュール、関数、行、または命令の排他的割り当てであったオブジェクトの割合。|  
|**\[割り当てバイト数 \(子を含む\)\]**|-   関数の場合、関数によって割り当てられたバイト数。  この数値には、この関数によって呼び出された関数で割り当てられたバイト数が含まれます。<br />-   モジュールの場合、モジュールから少なくとも 1 つの関数が実行されている間に割り当てられたプロファイリング実行で割り当てられたバイト数。  この数値には、モジュール関数によって呼び出されたすべての関数で作成されたオブジェクトが含まれます。<br />-   行または命令の場合、行または命令によって作成されたオブジェクトの総数。|  
|**\[割り当てバイト数 % \(子を含む\)\]**|プロファイリング実行で割り当てられたすべてのバイトに対する、そのモジュール、関数、行、または命令の包括バイトであったバイトの割合。|  
|**\[割り当てバイト数 \(関数のみ\)\]**|-   関数の場合、関数によって割り当てられた合計バイト数。  この数値には、この関数によって呼び出された関数で割り当てられたバイト数は含まれません。<br />-   モジュールの場合、モジュール内の関数によって割り当てられた排他バイトの合計。<br />-   行または命令の場合、この行または命令によって割り当てられたオブジェクトの総数。|  
|**\[割り当てバイト数 % \(関数のみ\)\]**|プロファイリング実行で割り当てられたすべてのバイトに対する、そのモジュール、関数、行、または命令の排他バイトであったバイトの割合。|  
  
## 参照  
 [方法: レポート ビューの列をカスタマイズする](../profiling/how-to-customize-report-view-columns.md)   
 [モジュール ビュー \- インストルメンテーション](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [モジュール ビュー](../profiling/modules-view-sampling-data.md)   
 [モジュール ビュー](../profiling/modules-view-instrumentation-data.md)