---
title: "チュートリアル : マルチスレッド アプリケーションのデバッグ | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "マルチスレッド デバッグ, チュートリアル"
  - "チュートリアル, マルチスレッド デバッグ"
ms.assetid: 590ffd57-0556-43d8-8962-ee27e5b2b7d7
caps.latest.revision: 38
caps.handback.revision: 38
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# チュートリアル : マルチスレッド アプリケーションのデバッグ
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] では、**\[スレッド\]** ウィンドウなどのユーザー インターフェイスが向上しており、マルチスレッド アプリケーションをデバッグしやすくなっています。  このチュートリアルにはあまり時間がかかりませんが、これを完了することで、マルチスレッド アプリケーションのデバッグに使用する新しいインターフェイスを理解できます。  
  
 このチュートリアルを始めるには、マルチスレッド アプリケーション プロジェクトが必要です。  次の手順に従って、このようなプロジェクトを作成します。  
  
#### チュートリアル用のプロジェクトを作成するには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  
  
     **\[新しいプロジェクト\]** ダイアログ ボックスが表示されます。  
  
2.  使用言語に応じて、**\[プロジェクトの種類\]** ボックスの **\[Visual Basic\]**、**\[Visual C\#\]**、または **\[Visual C\+\+\]** をクリックします。  
  
3.  **\[テンプレート\]** ボックスの **\[コンソール アプリケーション\]** または **\[CLR コンソール アプリケーション\]** をクリックします。  
  
4.  **\[名前\]** ボックスに、名前として「MyThreadWalkthroughApp」と入力します。  
  
5.  **\[OK\]** をクリックします。  
  
     新しいコンソール プロジェクトが表示されます。  プロジェクトが作成されると、ソース ファイルが表示されます。  選択した言語に応じて、ソース ファイル名はそれぞれ Module1.vb、Program.cs、MyThreadWalkthroughApp.cpp などとなります。  
  
6.  ソース ファイルに含まれているコードを削除し、「[Creating Threads and Passing Data at Start Time](../Topic/Creating%20Threads%20and%20Passing%20Data%20at%20Start%20Time.md)」の「スレッドの作成」にあるサンプル コードに置き換えます。  
  
7.  **\[ファイル\]** メニューの **\[すべてを保存\]** をクリックします。  
  
#### チュートリアルを開始するには  
  
-   ソース コード ウィンドウで、次のコードを探します。  
  
    ```vb  
    Thread.Sleep(3000)   
    Console.WriteLine(  
    ```  
  
```c#  
Thread.Sleep(3000);  
Console.WriteLine();  
```  
  
```cpp  
Thread::Sleep(3000);  
Console.WriteLine();  
```  
  
#### デバッグを開始するには  
  
1.  `Console.WriteLine` ステートメントを右クリックし、**\[ブレークポイント\]** をポイントして **\[ブレークポイントの挿入\]** をクリックします。  
  
     ソース ウィンドウ左端の余白に赤い丸が表示されます。  これは、ブレークポイントがその場所に設定されていることを示します。  
  
2.  **\[デバッグ\]** メニューの **\[デバッグ開始\]** をクリックします。  
  
     デバッグが開始され、コンソール アプリケーションの実行が始まり、ブレークポイントで停止します。  
  
3.  このとき、フォーカスがコンソール アプリケーション ウィンドウにある場合は、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ウィンドウの内側をクリックして、フォーカスを [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] に戻します。  
  
4.  ソース ウィンドウで、次のコードが含まれている行を探します。  
  
    ```vb  
    Thread.Sleep(5000)   
    ```  
  
```c#  
Thread.Sleep(3000);  
```  
  
```cpp  
Thread::Sleep(3000);  
```  
  
#### スレッド マーカーを見つけるには  
  
1.  **\[スレッド\]** ウィンドウを右クリックし、**\[ソースのスレッドを表示する\]** をクリックします。  
  
2.  ウィンドウ左端の余白に注目します。  マーカーがある行には、2 色のより糸の形をしたアイコンがあります。  色は、片方は赤で、もう片方は青です。  スレッド マーカーは、スレッドが停止している位置を示します。  このことから、スレッドはこの位置で停止していると考えられます。  
  
3.  スレッド マーカーの上にポインターを置きます。  データヒントが表示されます。  データヒントは、停止したスレッドごとに名前とスレッド ID 番号を表示します。  この場合、スレッドは 1 つだけで、名前は `<noname>` です。  
  
4.  スレッド マーカーを右クリックします。  ショートカット メニューに表示される項目に注目します。  
  
 次のアイコンが*スレッド マーカー*です。  
  
 ![スレッド マーカー](../debugger/media/threadmarker.png "ThreadMarker")  
  
## スレッドに対するフラグの設定と設定解除  
 [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)] では、特に注目するスレッドにフラグを設定できます。  スレッドに対するフラグの設定は、重要なスレッドを追跡し、注目する必要がないスレッドを無視するのに適しています。  
  
#### スレッドにフラグを設定するには  
  
1.  **\[表示\]** メニューで、**\[ツール バー\]** をポイントします。  
  
     **\[デバッグの場所\]** ツール バーが選択されていることを確認します。  
  
2.  **\[デバッグの場所\]** ツール バーに移動して、**\[スレッド\]** ボックスの一覧をクリックします。  
  
    > [!NOTE]
    >  このツール バーは、**\[プロセス\]**、**\[スレッド\]**、**\[スタック フレーム\]** という 3 つの主なボックスがあることから容易に識別できます。  
  
3.  ボックスに表示されているスレッド数に注目します。  
  
4.  ソース ウィンドウに戻って、**スレッド マーカー**をもう一度右クリックします。  
  
5.  ショートカット メニューで、**\[フラグ\]** をポイントし、目的のスレッド名と ID 番号をクリックします。  
  
6.  **\[デバッグの場所\]** ツール バーに戻り、**\[スレッド\]** ボックスの一覧をもう一度クリックします。  
  
     今度は、フラグが設定されたスレッドのみがボックスに表示されます。  **\[スレッド\]** ボックスの一覧の右横に、フラグ ボタンがあります。  そのボタンに表示されるフラグ アイコンは、それまでは淡色表示でした。  明るい赤で塗りつぶされたアイコンに変わっていることを確認します。  
  
7.  フラグ アイコンの上にポインターを置きます。  
  
     ポップアップが表示されます。  このポップアップは、**\[スレッド\]** ボックスの一覧の現在のモードが **\[フラグが設定されたスレッドのみを表示\]** になっていることを示します。  
  
8.  フラグ ボタンをクリックして、**\[すべてのスレッドの表示\]** のモードに切り替えます。  
  
9. **\[スレッド\]** ボックスの一覧をもう一度クリックし、再びすべてのスレッドが表示されることを確認します。  
  
10. フラグ ボタンをクリックして、**\[フラグが設定されたスレッドのみの表示\]** に切り替えます。  
  
11. **\[デバッグ\]** メニューの **\[ウィンドウ\]** をポイントし、**\[スレッド\]** をクリックします。  
  
     **\[スレッド\]** ウィンドウが表示されます。  1 つのスレッドに、目立つ色のフラグ アイコンが割り当てられています。  
  
12. ソース ウィンドウで、スレッド マーカーをもう一度右クリックします。  
  
     ショートカット メニューに今回表示される項目に注目します。  **\[フラグ\]** の代わりに **\[フラグ解除\]** が表示されていることを確認します。  **\[フラグ解除\]** をクリックしないでください。  
  
13. スレッドのフラグ解除に関する次の手順に進みます。  
  
#### スレッドのフラグを解除するには  
  
1.  **\[スレッド\]** ウィンドウで、フラグが設定されたスレッドのある行を右クリックします。  
  
     ショートカット メニューが表示されます。  メニュー項目に **\[フラグ解除\]** と **\[すべてのスレッドのフラグを解除\]** があることを確認します。  
  
2.  スレッドのフラグを解除するには、**\[フラグ解除\]** をクリックします。  
  
3.  赤いフラグ アイコンをクリックします。  
  
4.  **\[デバッグの場所\]** ツール バーにもう一度注目します。  フラグ ボタンが再び淡色表示になっていることを確認します。  フラグ解除されたのは、フラグが設定された唯一のスレッドでした。  フラグが設定されているスレッドがないため、ツール バーは **\[すべてのスレッドの表示\]** モードに戻ります。  **\[スレッド\]** ボックスの一覧をクリックし、すべてのスレッドが表示されることを確認します。  
  
5.  **\[スレッド\]** ウィンドウに戻り、情報列を検証します。  
  
     各列の先頭に表示されるボタンのほとんどに、列の内容を示すタイトルが表示されます。  ただし、左端の列にはタイトルはありません。  その代わりにアイコンがありますが、これはフラグの枠です。  スレッドの一覧の各行にも同じ枠があります。  この枠は、スレッドにフラグが設定されていないことを示しています。  
  
6.  一覧の下から 2 番目と 3 番目の 2 つのスレッドのフラグ枠をクリックします。  
  
     フラグ アイコンが中空の枠から塗りつぶされた赤に変わります。  
  
7.  フラグ列の最上部にあるボタンをクリックします。  
  
     このボタンをクリックすると、スレッドの一覧順序が変わります。  スレッドのリストが並べ替えられ、フラグが設定されたスレッドが先頭になります。  
  
8.  再び、フラグ列の最上部にあるボタンをクリックします。  
  
     並べ替え順序がまた変わります。  
  
## \[スレッド\] ウィンドウの詳細  
  
#### \[スレッド\] ウィンドウについての理解を深めるには  
  
1.  **\[スレッド\]** ウィンドウで、左から 3 番目の列に注目します。  この列の最上部にあるボタンには **\[ID\]** と表示されていることを確認します。  
  
2.  **\[ID\]** をクリックします。  
  
     スレッドの一覧がスレッド ID 番号で並べ替えられます。  
  
3.  一覧の中から任意のスレッドを右クリックします。  ショートカット メニューの **\[16 進数で表示\]** をクリックします。  
  
     スレッド ID 番号の書式が変わります。  
  
4.  マウス ポインターを一覧の任意のスレッドの上に置きます。  
  
     少し遅れて、データヒントが表示されます。  ここには、スレッドの呼び出し履歴の一部が表示されます。  
  
5.  **\[カテゴリ\]** というラベルの付いた、左から 4 番目の列に注目します。  スレッドはカテゴリ別に分類されています。  
  
     プロセスで最初に作成されたスレッドは、メイン スレッドと呼ばれます。  スレッドの一覧でそれを探します。  
  
6.  メイン スレッドを右クリックし、**\[スレッドに切り替え\]** をクリックします。  
  
     警告ダイアログ ボックスが表示されます。  そこには、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] がメイン スレッドのソース コードを表示できないというメッセージが表示されます。  
  
     **\[OK\]** をクリックします。  
  
7.  **\[呼び出し履歴\]** ウィンドウと **\[デバッグの場所\]** ツール バーに注目します。  
  
     **\[呼び出し履歴\]** ウィンドウの表示内容が変わっていることを確認します。  
  
## アクティブ スレッドの切り替え  
  
#### スレッドを切り替えるには  
  
1.  **\[スレッド\]** ウィンドウで、左から 2 番目の列に注目します。  この列の最上部にあるボタンにはテキストもアイコンもありません。  この列が**アクティブ スレッド**列です。  
  
2.  **アクティブ スレッド**列に注目し、スレッドの 1 つに黄色い矢印があることを確認します。  これが*アクティブ スレッド インジケーター*です。  
  
3.  アクティブ スレッド インジケーターがあるスレッド ID 番号をメモしておきます。  これからアクティブ スレッド インジケーターを動かしますが、完了したら元に戻す必要があるためです。  
  
4.  別のスレッドを右クリックし、**\[スレッドに切り替え\]** をクリックします。  
  
5.  ソース ウィンドウの **\[呼び出し履歴\]** ウィンドウに注目します。  内容が変わっていることを確認します。  
  
6.  **\[デバッグの場所\]** ツール バーに注目します。  アクティブ スレッドも変わっていることを確認します。  
  
7.  **\[デバッグの場所\]** ツール バーに移動します。  **\[スレッド\]** ボックスの一覧の別のスレッドをクリックします。  
  
8.  **\[スレッド\]** ウィンドウに注目します。  アクティブ スレッド インジケーターが変わっていることを確認します。  
  
9. ソース ウィンドウで、スレッド マーカーを右クリックします。  ショートカット メニューで、**\[切り替え先\]** をポイントし、目的のスレッド名\/ID 番号をクリックします。  
  
     これで、アクティブ スレッドを変更する方法として、**\[スレッド\]** ウィンドウを使用する方法、**\[デバッグの場所\]** ツール バーの **\[スレッド\]** ボックスを使用する方法、ソース ウィンドウのスレッド インジケーターを使用する方法の 3 とおりを見てきました。  
  
     スレッド インジケーターを使用すると、特定の場所で停止されたスレッドのみを切り替えることができます。  **\[スレッド\]** ウィンドウと **\[デバッグの場所\]** ツール バーを使用すると、任意のスレッドに切り替えることができます。  
  
## スレッド実行の凍結と凍結解除  
  
#### スレッドを凍結および凍結解除するには  
  
1.  **\[スレッド\]** ウィンドウで、任意のスレッドを右クリックし、**\[凍結\]** をクリックします。  
  
2.  アクティブ スレッド列に注目します。  2 本の垂直バーが表示されることを確認します。  この 2 本の青いバーは、スレッドが凍結していることを示しています。  
  
3.  **\[中断\]** 列に注目します。  スレッドの中断カウントが 1 になっていることを確認します。  
  
4.  凍結しているスレッドを右クリックし、**\[凍結解除\]** をクリックします。  
  
     アクティブ スレッド列と **\[中断\]** 列の表示が変わります。  
  
## 参照  
 [マルチスレッド アプリケーションのデバッグ](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [方法 : デバッグ中に別のスレッドに切り替える](../debugger/how-to-switch-to-another-thread-while-debugging.md)