---
title: "方法: [定義をここに表示] を使用してコードを表示および編集する (Alt + F12) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45f3dd20-902a-4047-8cca-9f18216123f4
caps.latest.revision: 16
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: e4b64d7c82e28c5ba58157ea729465eef84f52a4
ms.contentlocale: ja-jp
ms.lasthandoff: 05/13/2017

---
# <a name="how-to-view-and-edit-code-by-using-peek-definition-altf12"></a>方法: [定義をここに表示] を使用してコードを表示および編集する (Alt + F12)
**[定義をここに表示]** を使うと、記述中のコードから切り替えずにコードを表示および編集できます。 **[定義をここに表示]** と **[定義へ移動]** では同じ情報が表示されますが、**[定義をここに表示]** ではコードがポップアップ ウィンドウに表示され、**[定義へ移動]** では別のコード ウィンドウに表示されます。 **[定義へ移動]** を実行すると、コンテキスト (アクティブなコード ウィンドウ、現在の行、およびカーソルの位置) が定義コード ウィンドウに切り替わります。 **[定義をここに表示]** を使うと、元のコード ファイル内での位置を保ちながら、定義を表示および編集したり、定義ファイル内を移動したりできます。  
  
 **[定義をここに表示]** は、C#、Visual Basic、および C++ のコードで使うことができます。 Visual Basic では **[定義をここに表示]** に、定義メタデータのないシンボル (.NET Framework の組み込み型など) の**オブジェクト ブラウザー**へのリンクが表示されます。  
  
> [!IMPORTANT]
>  このコマンドは、Visual Studio 2013 の Express Edition では使用できません。  
  
## <a name="working-with-peek-definition"></a>[定義をここに表示] の操作  
  
#### <a name="to-open-a-peek-definition-window"></a>[定義をここに表示] ウィンドウを開くには  
  
1.  **[定義をここに表示]** は、調査対象のメソッドのショートカット メニューを開くと見つかります  (キーボード: Alt + F12)。  
  
     次の図に、`Print()` という名前のメソッドの **[定義をここに表示]** ウィンドウを示します。  
  
     ![[定義をここに表示] ウィンドウ](../ide/media/peekwindow.png "PeekWindow")  
  
     定義ウィンドウは、元のファイルの `printer.Print("Hello World!")` 行の下に表示されます。 このウィンドウにより、元のファイル内のどのコードも隠れて見えなくなることはありません。 `printer.Print("Hello World!")` 呼び出しに続く行は定義ウィンドウの下に表示されます。  
  
2.  コード定義ウィンドウ内のさまざまな位置にカーソルを移動できます。 定義ウィンドウの上または下の元のコード ウィンドウ内でも、今までどおりカーソルを移動できます。  
  
3.  定義ウィンドウから文字列をコピーし、元のコード内で貼り付けることができます。 定義ウィンドウから元のコードに文字列をドラッグ アンド ドロップすることもできますが、定義ウィンドウからその文字列は削除されません。  
  
4.  Esc キーを押すか、定義ウィンドウ タブの **[閉じる]** ボタンをクリックすることで、定義ウィンドウを閉じることができます。  
  
#### <a name="to-open-a-peek-definition-window-from-within-a-peek-definition-window"></a>[定義をここに表示] ウィンドウ内から [定義をここに表示] を開くには  
  
-   既に **[定義をここに表示]** ウィンドウを開いている場合、そのウィンドウ内のコードで **[定義をここに表示]** を再度呼び出すことができます。 もう 1 つの定義ウィンドウが開きます。 定義ウィンドウ タブの横に一連の階層リンクの点が表示されます。これらの点を使用して定義ウィンドウ間を移動できます。 各点のツールヒントには、それぞれの点が表す定義ファイルの名前とパスが表示されます。  
  
     ![[定義をここに表示] ウィンドウ内の [定義をここに表示] ウィンドウ](../ide/media/peekwithinpeek.png "PeekWithinPeek")  
  
#### <a name="to-use-peek-definition-with-multiple-results"></a>複数の結果で [定義をここに表示] を使用するには  
  
-   複数の定義 (部分クラスなど) があるコードで **[定義をここに表示]** を使うと、結果の一覧がコード定義ビューの右側に表示されます。 一覧内の結果を選択してその定義を表示できます。  
  
     ![複数の結果がある [定義をここに表示] ウィンドウ](../ide/media/peekmultiple.png "PeekMultiple")  
  
#### <a name="to-edit-inside-the-peek-definition-window"></a>[定義をここに表示] ウィンドウ内で編集するには  
  
-   **[定義をここに表示]** ウィンドウ内で編集を始めると、変更中のファイルがコード エディターの別のタブで自動的に開き、既に行った変更が反映されます。 **[定義をここに表示]** ウィンドウで続けて変更を加えたり、元に戻したり、保存したりすることができ、タブにはそれらの変更が反映され続けます。 変更を保存せずにウィンドウを閉じた場合でも、タブ内で変更を加えたり、元に戻したり、保存したりすることができ、ウィンドウで作業をやめた箇所から再開することができます。  
  
     ![[定義をここに表示] ウィンドウ内での編集](../ide/media/peekedit.png "PeekEdit")  
  
#### <a name="to-use-keyboard-shortcuts-for-peek-definition"></a>[定義をここに表示] のキーボード ショートカットを使用するには  
  
-   **[定義をここに表示]** ウィンドウでは次のキーボード ショートカットを使うことができます。  
  
    |機能|キーボード ショートカット|  
    |-------------------|-----------------------|  
    |定義ウィンドウを開く|Alt + F12|  
    |定義ウィンドウを閉じる|Esc|  
    |定義ウィンドウを通常のドキュメント タブに昇格する|Shift + Alt + Home|  
    |定義ウィンドウ間を移動する|Ctrl + Alt + マイナス記号 (-) と Ctrl + Alt + 等号 (=)|  
    |複数の結果の間を移動する|F8 と Shift + F8|  
    |コード エディター ウィンドウと定義ウィンドウの間で切り替える|Shift + Esc|  
  
    > [!NOTE]
    >  Visual Studio の他の場所でも、同じキーボード ショートカットを使って **[定義をここに表示]** ウィンドウでコードを編集できます。  
  
## <a name="see-also"></a>関連項目  
 [生産性に関するヒント](../ide/productivity-tips-for-visual-studio.md)