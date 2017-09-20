---
title: "DA0021: ジェネレーション 1 のガベージ コレクションが高率です | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.21
- vs.performance.DA0021
- vs.performance.rules.DA0021
ms.assetid: ebf5d9b3-a1ac-4688-8f0f-39a85f4dd15f
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: e666eb5fab2ed4d9d8903f1801c606cd879c9a62
ms.contentlocale: ja-jp
ms.lasthandoff: 05/13/2017

---
# <a name="da0021-high-rate-of-gen-1-garbage-collections"></a>DA0021: ジェネレーション 1 のガベージ コレクションが高率です
|||  
|-|-|  
|規則 ID|DA0021|  
|カテゴリ|.NET Framework の使用|  
|プロファイル方法|すべて|  
|メッセージ|比較的高い率のジェネレーション 1 ガベージ コレクションが発生しています。 設計によりプログラムのほとんどのデータ構造が長時間割り当てられて保持される場合は、通常これは問題ではありません。 一方、意図した動作でない場合は、アプリケーションがオブジェクトを固定している可能性があります。 不明な場合は、.NET のメモリ割り当てデータとオブジェクト ライフタイム情報を収集することで、アプリケーションが使用しているメモリ割り当てのパターンを知ることができます。|  
|規則の種類|情報|  
  
 サンプリング、.NET メモリ、またはリソース競合メソッドを使用してプロファイリングを行うときは、この規則を呼び出すためのサンプルを少なくとも 10 個収集する必要があります。  
  
## <a name="cause"></a>原因  
 プロファイリングの実行中に収集されたシステム パフォーマンス データは、ジェネレーション 1 のガベージ コレクションで解放された .NET Framework オブジェクト用のメモリが、ジェネレーション 0 のデータ コレクションと比較して高率であることを示しています。  
  
## <a name="rule-description"></a>規則の説明  
 Microsoft .NET 共通言語ランタイム (CLR: Common Language Runtime) は、自動メモリ管理メカニズムを備えています。このメカニズムでは、ガベージ コレクターを使用して、アプリケーションが使用しなくなったオブジェクトのメモリを解放します。 ガベージ コレクターはジェネレーション指向です。これは、多くの割り当てが短時間で終了することを前提としています。 たとえば、ローカル変数の有効期間は短時間です。 新しく作成されたオブジェクトはジェネレーション 0 (gen 0) から始まり、ガベージ コレクションの実行中に破棄されなければジェネレーション 1 に昇格します。その後もアプリケーションによって引き続き使用されていれば、最後はジェネレーション 2 に昇格します。  
  
 ジェネレーション 0 のオブジェクトの収集頻度は高く、通常は非常に効率的に収集されます。 ジェネレーション 1 のオブジェクトの収集頻度はそれよりも低くなり、収集効率も下がります。 有効期間の長いジェネレーション 2 のオブジェクトの場合、収集頻度はさらに低くなります。 また、ジェネレーション 2 のコレクション (フル ガベージ コレクションの実行) は、最も負荷のかかる操作になります。  
  
 この規則は、ジェネレーション 1 のガベージ コレクションの発生率が高くなりすぎた場合に適用されます。 有効期間が短いオブジェクトの多くが、ジェネレーション 0 のコレクションでは収集されずにジェネレーション 1 のコレクションで収集される場合、メモリ管理のコストが高くなる可能性があります。 詳細については、MSDN Web サイトの「Rico Mariani's Performance Tidbits」 (Rico Mariani のパフォーマンスに関する話題) の「[Mid-life crisis](http://go.microsoft.com/fwlink/?LinkId=177835)」 (有効期間半ばでの危機) の投稿を参照してください。  
  
## <a name="how-to-investigate-a-warning"></a>警告の調査方法  
 [エラー一覧] ウィンドウに表示されたメッセージをダブルクリックして、プロファイル データの [[マーク] ビュー](../profiling/marks-view.md)に移動します。 **.NET CLR Memory\\# of Gen 0 Collections** 列と **.NET CLR Memory\\# of Gen 1 Collections** 列を探します。 ガベージ コレクションがより高い頻度で発生している特定のプログラム実行フェーズがあるかどうかを確認します。 これらの値を **% Time in GC** 列と比較して、マネージ メモリの割り当てパターンによって過剰なメモリ管理オーバーヘッドが発生しているかどうかを調べます。  
  
 アプリケーションのマネージ メモリの使用パターンを調べるには、.NET メモリの割り当てのプロファイルを使用して再度アプリケーションのプロファイリングを行い、オブジェクトの有効期間測定を要求します。  
  
 ガベージ コレクションのパフォーマンスの向上の方法の詳細については、Microsoft Web サイトの「[ガベージ コレクターの基本とパフォーマンスのヒント](http://go.microsoft.com/fwlink/?LinkId=148226)」を参照してください。 自動ガベージ コレクションのオーバーヘッドについては、「[Large Object Heap Uncovered](http://go.microsoft.com/fwlink/?LinkId=177836)」 (大きなオブジェクト ヒープの秘密) を参照してください。