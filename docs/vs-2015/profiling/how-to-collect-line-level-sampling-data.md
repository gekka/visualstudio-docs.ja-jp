---
title: '方法: 行レベルのサンプリング データを収集する | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance tools, line-level sampling
ms.assetid: 44803aad-dd39-4c2e-9209-d35185d44983
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bd57893476ba7654a37fc44d1681adc3264f92b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47539351"
---
# <a name="how-to-collect-line-level-sampling-data"></a>方法 : 行レベルのサンプリング データを収集する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックの最新バージョンをご覧[方法: 行レベルのサンプリング データの収集](https://docs.microsoft.com/visualstudio/profiling/how-to-collect-line-level-sampling-data)します。  
  
行レベルのサンプリングとは、排他サンプル数が高い関数など、プロセッサ集中型の関数のコードで、プロセッサが大部分の時間を費やす必要のある場所を特定するためのプロファイラーの機能です。  
  
## <a name="overview"></a>概要  
 行レベルのサンプリングでは、設定された間隔でプログラムのコール スタックを走査し、その結果を集計します。 これらの結果では、サンプルの取得時にプロセッサが実行していた命令が示されます。 次に、排他サンプルについて収集されたデータが分析され、コード行と命令ポインター (IP) を識別します。  
  
 行レベルのサンプリングは、ネイティブ コードだけでなく、マネージド コードにも使用できます。 このデータが表示されるパフォーマンス レポートには、行ビューおよびモジュール ビューがあります。  
  
 文字の開始または終了情報は、ネイティブ コードでは使用できません。 複数行ステートメントの場合、ネイティブ コードでは、行の開始情報を使用できず、行の終了情報だけを使用できます。  
  
### <a name="available-data"></a>使用できるデータ  
 使用できる行レベルのサンプリング データには次の情報が含まれます。  
  
-   関数名。  
  
-   関数アドレス。  
  
-   行の開始情報 - サンプリングされるコードの行番号。  
  
-   行の終了情報 - ソースの終了行番号。 これは "行の開始情報" のデータと同じです (1 つのプログラム文が複数のソース コード行にまたがっている場合を除く)。  
  
-   文字の開始情報 - 集約サンプルの開始列。 通常、これは 0 です (1 つの行に複数のプログラム文が含まれる場合を除く)。  
  
-   文字の終了情報 - 集約サンプルの終了列。  
  
-   IP - 集約サンプルが取得されたアドレス (IP ビューのみ)。  
  
 **[モジュール]** ビューでは、関数に行レベルの統計が含まれている場合、統計は各関数の下に入れ子になっています。 さらに、各行で入れ子になっている IP レベルの統計が表示されます。  
  
### <a name="turn-off-line-level-sampling-for-managed-code"></a>マネージド コードの行レベルのサンプリングの無効化  
 既定では、行レベルのサンプリングは有効になっています。 マネージド コードの行レベルのデータ収集を無効にするには、次のいずれかを実行します。  
  
-   プロファイリングの前に、「**VSPerfCLREnv /samplelineoff**」と入力します。 これは、アプリケーションとサービスの両方に影響します。  
  
     または  
  
-   アプリケーションの起動時に、「**VSPerfCmd /lineoff\<他の引数>**」を入力します。  
  
## <a name="see-also"></a>関連項目  
 [パフォーマンス セッションの構成](../profiling/configuring-performance-sessions.md)   
 [パフォーマンス ツール データの分析](../profiling/analyzing-performance-tools-data.md)


