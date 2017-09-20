---
title: "方法 : 最適化されたコードをデバッグする | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "ブレークポイント, 最適化されたコードで"
  - "デバッグ ビルド, 最適化"
  - "デバッグ [C++], 最適化されたコード"
  - "最適化, デバッグ ビルド"
  - "最適化されたコード, デバッグ"
ms.assetid: fc8eeeb8-6629-4c9b-99f7-2016aee81dff
caps.latest.revision: 25
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 25
---
# 方法 : 最適化されたコードをデバッグする
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。  設定を変更するには、\[ツール\] メニューの \[設定のインポートとエクスポート\] をクリックします。  詳細については、「[Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ja-jp/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
> [!NOTE]
>  Visual Studio 更新プログラム 3 で導入された [\/Zo \(最適化されたデバッグ機能の強化\)](/visual-cpp/build/reference/zo-enhance-optimized-debugging) コンパイラ オプションを使用すると、最適化されたコードについて豊富なデバッグ情報が生成されます \(**\/Od** コンパイラ オプションを使用しないでビルドされたプロジェクト。  「[\/O オプション \(コードの最適化\)](/visual-cpp/build/reference/o-options-optimize-code)」を参照してください\)。  これにはローカル変数とインライン関数のデバッグのサポートの強化が含まれます。  
>   
>  [エディット コンティニュ](../debugger/edit-and-continue-visual-csharp.md)は、**\/Zo** コンパイラ オプションを使用している場合は無効です。  
  
 コンパイラは、ソース コードを最適化するときに命令を再配置したり再構成したりします。  これにより、コンパイル後のコードの実行効率が向上します。  しかし、この命令の整理が原因となり、一連の命令に対応するソース コードをデバッガーが識別できなくなる場合があります。  
  
 最適化によって次のような影響が生じる場合があります。  
  
-   ローカル変数がオプティマイザーによって削除されたり、デバッガーの追跡できない場所に移動されたりする可能性があります。  
  
-   オプティマイザーによってコード ブロックがマージされた場合、関数内の位置が変更されます。  
  
-   オプティマイザーによって 2 つの関数がマージされた場合、呼び出し履歴上のフレームに対し、間違った関数名が表示される場合があります。  
  
 ほとんどの場合、呼び出し履歴上のフレームには、正しい情報が表示されます。ただし、これはすべてのフレームにシンボルが割り当てられていることが前提です。  スタックの破損が生じた場合、アセンブリ言語で記述された関数が存在する場合、呼び出し履歴上のシンボルに一致しないオペレーティング システムのフレームが存在する場合など、呼び出し履歴上のフレームに誤った情報が表示されることがあります。  
  
 グローバル変数および静的変数は常に正しく表示されます。  構造体レイアウトについても同様です。  構造体へのポインターが存在し、そのポインターの値が正しければ、構造体のすべてのメンバー変数は、正しい値で表示されます。  
  
 これらの制限事項のため、できるだけ最適化する前のプログラムをデバッグするようにしてください。  既定では、最適化に対する設定は、Visual C\+\+ プログラムのデバッグ構成ではオフ、リリース構成ではオンになっています。  
  
 ただし、最適化後のプログラムでしかバグが発生しない場合もあります。  このような場合は、最適化されたコードをデバッグする必要があります。  
  
### デバッグ ビルド構成で最適化をオンにするには  
  
1.  新しいプロジェクトの作成時に、`Win32 Debug` ターゲットを選択します。  プログラムが完全にデバッグされ、`Win32` ターゲットをビルドできるようになるまでは、`Debug``Win32 Release` ターゲットを使用します。  コンパイラは、`Win32 Debug` ターゲットの最適化は行いません。  
  
2.  ソリューション エクスプローラーでプロジェクトを選択します。  
  
3.  **\[表示\]** メニューの **\[プロパティ ページ\]** をクリックします。  
  
4.  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成\]** ボックスの \[`Debug`\] が選択されていることを確認します。  
  
5.  左側のフォルダー ビューで、**\[C\/C\+\+\]** フォルダーを選択します。  
  
6.  **\[C\/C\+\+\]** フォルダーの下の \[`Optimization`\] を選択します。  
  
7.  右側のプロパティ リストで、\[`Optimization`\] を探します。  その横の設定値は、`Disabled (`[\/Od](/visual-cpp/build/reference/od-disable-debug)`)` になっているはずです。  その他のオプション \(`Minimum Size``(`[\/O1](/visual-cpp/build/reference/o1-o2-minimize-size-maximize-speed)`)`、`Maximum Speed``(`[\/O2](/visual-cpp/build/reference/o1-o2-minimize-size-maximize-speed)`)`、`Full Optimization``(`[\/Ox](/visual-cpp/build/reference/ox-full-optimization)`)`、`Custom`\) から 1 つを選択します。  
  
8.  \[`Custom`\] に対して \[`Optimization`\] オプションを選択すると、プロパティ リストに表示されているその他のプロパティについてオプションを設定できるようになります。  
  
9. プロジェクトのプロパティ ページの \[構成プロパティ\]、\[C\/C\+\+\]、\[コマンド ライン\] ノードを選択し、`(`[\/Zo](/visual-cpp/build/reference/zo-enhance-optimized-debugging)`)`を \[**追加のオプション**\] テキスト ボックスに追加します。  
  
    > [!WARNING]
    >  `/Zo` には、Visual Studio 2013 更新プログラム 3 以降のバージョンが必要です。  
    >   
    >  `/Zo` を追加すると、[エディット コンティニュ](../debugger/edit-and-continue-visual-csharp.md)が無効になります。  
  
 最適化されたコードをデバッグするときは、**\[逆アセンブリ\]** ウィンドウを使用して実際にどのような命令が作成および実行されているのか確認してください。  ブレークポイントを設定する場合は、ブレークポイントが命令と共に移動する可能性があるため注意が必要です。  次に例を示します。  
  
```  
for (x=0; x<10; x++)  
```  
  
 この行にブレークポイントを設定したとします。  ブレークポイントは 10 回ヒットするように思われますが、このコードを最適化した場合、ブレークポイントは 1 回しかヒットしません。  これは、最初の命令によって `x` の値が 0 に設定されるためです。  コンパイラは、その最初の命令を 1 回だけ実行すると見なしてループの外に移動します。  このとき、ブレークポイントもこの命令と共に移動します。  `x` を比較してインクリメントする命令はループ内に残ったままになります。  **\[逆アセンブリ\]** ウィンドウを参照すると、コードの実行をより細かく制御できるように、[ステップ実行の単位](http://msdn.microsoft.com/ja-jp/8791dac9-64d1-4bb9-b59e-8d59af1833f9)が自動的に命令に設定されています。この設定は、最適化されたコードをステップ実行するときに役立ちます。  
  
## 参照  
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)