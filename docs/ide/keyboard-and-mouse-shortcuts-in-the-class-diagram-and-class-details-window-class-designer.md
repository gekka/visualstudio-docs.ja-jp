---
title: "クラス ダイアグラムおよびクラスの詳細情報のウィンドウでのキーボードとマウスのショートカット (クラス デザイナー) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdetails.window
helpviewer_keywords:
- class diagrams, keyboard shortcuts
- class diagrams, mouse shortcuts
ms.assetid: c12d8dac-9902-4fde-b721-2a8116da53b7
caps.latest.revision: 8
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
ms.openlocfilehash: 83c52ff92d4a5b45b13b2b1eb582ec9a4d3d2687
ms.contentlocale: ja-jp
ms.lasthandoff: 05/13/2017

---
# <a name="keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer"></a>クラス ダイアグラムおよびクラスの詳細情報のウィンドウでのキーボードとマウスのショートカット (クラス デザイナー)
クラス デザイナーおよび **[クラスの詳細]** ウィンドウでのナビゲーション操作は、マウスで実行するだけでなく、キーボードを使用することもできます。  
  
 **このトピックの内容**  
  
-   [クラス デザイナーでマウスを使用する](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#MouseClassDesigner)  
  
-   [[クラスの詳細] ウィンドウでマウスを使用する](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#MouseClassDetails)  
  
-   [クラス デザイナーでキーボードを使用する](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#KeyboardClassDesigner)  
  
-   [[クラスの詳細] ウィンドウでキーボードを使用する](../ide/keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window-class-designer.md#KeyboardClassDetails)  
  
##  <a name="MouseClassDesigner"></a> クラス デザイナーでマウスを使用する  
 次のマウス操作がクラス ダイアグラムでサポートされます。  
  
|マウス操作の組み合わせ|コンテキスト|説明|  
|-----------------------|-------------|-----------------|  
|ダブルクリック|Shape 要素|コード エディターを開きます。|  
||ロリポップ コネクタ|ロリポップの展開/折りたたみを実行します。|  
||ロリポップ コネクタのラベル|**[インターフェイスの表示]** コマンドを呼び出します。|  
|マウス ホイール|クラス ダイアグラム|垂直方向にスクロールします。|  
|Shift + マウス ホイール|クラス ダイアグラム|水平方向にスクロールします。|  
|Ctrl + マウス ホイール|クラス ダイアグラム|ズームします。|  
|Ctrl + Shift + クリック|クラス ダイアグラム|ズームします。|  
  
##  <a name="MouseClassDetails"></a> [クラスの詳細] ウィンドウでマウスを使用する  
 マウスを使用して、[クラスの詳細] ウィンドウの外観と表示されるデータを次のように変更できます。  
  
-   編集可能な任意のセルをクリックすると、そのセルの内容を編集できます。 変更内容は、[プロパティ] ウィンドウやソース コードなど、データが格納または表示されているすべての場所に反映されます。  
  
-   行の任意のセルをクリックすると、その行によって表される要素のプロパティが [プロパティ] ウィンドウに表示されます。  
  
-   列の幅を変更するには、列見出しの右端の境界線を、必要な列幅になるまでドラッグします。  
  
-   行の左側の矢印記号をクリックすると、コンパートメントまたはプロパティ ノードの展開と折りたたみを実行することができます。  
  
-   [クラスの詳細] ウィンドウには、現在のクラスに新規メンバーを作成したり、[クラスの詳細] ウィンドウ グリッドでメンバーのコンパートメント間を移動したりするためのボタンがいくつか用意されています。 詳細については、「[クラスの詳細] ウィンドウのボタン」を参照してください。  
  
##  <a name="KeyboardClassDesigner"></a> クラス デザイナーでキーボードを使用する  
 次のキーボード操作がクラス ダイアグラムでサポートされています。  
  
|キー|コンテキスト|説明|  
|---------|-------------|-----------------|  
|方向キー|型図形の内側|図形の内容に対してツリー スタイルのナビゲーションを実行します (図形の折り返しがサポートされます)。 ←キーと→キーは、現在の項目が展開できる場合は項目を展開するか折りたたみ、展開できない場合は親に移動します (詳細な動作については、ツリー ビューのナビゲーションを参照してください)。|  
||最上位の図形|ダイアグラム上で図形を移動します。|  
|Shift + 方向キー|型図形の内側|メンバー、入れ子にされた型、コンパートメントなどの図形要素からなる連続選択を実行します。 これらのショートカットでは、折り返しはサポートされません。|  
|ホーム|型図形の内側|最上位の図形のタイトルに移動します。|  
||最上位の図形|ダイアグラムの最初の図形に移動します。|  
|End|型図形の内側|図形内の最後の可視要素に移動します。|  
||最上位の図形|ダイアグラムの最後の図形に移動します。|  
|Shift + Home|型図形の内側|図形内の現在の項目から開始して、同じ図形内の一番上の項目まで、図形内の要素を選択します。|  
|Shift + End|型図形の内側|Shift + Home と同じですが、上から下への方向です。|  
|Enter|すべてのコンテキスト|ダブルクリックでも使用できる、図形の既定の操作を呼び出します。 ほとんどの場合、これは [コードの表示] ですが、一部の要素では定義が異なります (ロリポップ、コンパートメント ヘッダー、ロリポップ ラベル)。|  
|+/-|すべてのコンテキスト|現在フォーカスのある要素が展開できる場合、これらのキーは要素を展開するか折りたたみます。|  
|>|すべてのコンテキスト|子を持つ要素では、要素が縮小されている場合に要素を展開し、最初の子に移動します。|  
|<|すべてのコンテキスト|親要素に移動します。|  
|Alt + Shift + L|型図形の内側 + 型図形の上|現在選択されている図形にロリポップがある場合は、ロリポップに移動します。|  
|Alt + Shift + B|型図形の内側 + 型図形の上|基本データ型の一覧が型図形に表示され、複数の項目がある場合は、一覧の展開状態 (折りたたみ/展開) を切り替えます。|  
|Del|型図形およびコメント図形の上|**[ダイアグラムから削除]** コマンドを呼び出します。|  
||その他すべて|**[コードの削除]** コマンドを呼び出します (メンバー、パラメーター、関連付け、継承、ロリポップ ラベル)。|  
|Ctrl + Del|すべてのコンテキスト|選択項目に対して **[コードの削除]** コマンドを呼び出します。|  
|Tab|すべてのコンテキスト|同じ親を持つ次の子に移動します (折り返しをサポートします)。|  
|Shift + Tab|すべてのコンテキスト|同じ親を持つ前の子に移動します (折り返しをサポートします)。|  
|Space|すべてのコンテキスト|現在の要素の選択状態を切り替えます。|  
  
##  <a name="KeyboardClassDetails"></a> [クラスの詳細] ウィンドウでキーボードを使用する  
  
> [!NOTE]
>  次のキー バインドは、コードを入力する場合の動作に特に類似したものとなるように選ばれています。  
  
 [クラスの詳細] ウィンドウ内で移動するには、次のキーを使用します。  
  
|||  
|-|-|  
|キー|結果|  
|, (コンマ)|カーソルがパラメーター行にある場合、コンマを入力すると、カーソルが次のパラメーターの [名前] フィールドに移動します。 カーソルがメソッドの最後のパラメーター行にある場合、カーソルは [\<パラメーターの追加>] フィールドに移動します。それを使用することにより新規パラメーターを作成できます。<br /><br /> カーソルが [クラスの詳細] ウィンドウの他の場所にある場合は、コンマを入力すると、コンマが通常の文字として現在のフィールドに追加されます。|  
|; (セミコロン)<br /><br /> または<br /><br /> ) 終わりかっこ|カーソルが [クラスの詳細] ウィンドウのグリッドで次のメンバー行の [名前] フィールドに移動します。|  
|タブ|カーソルが次のフィールドに移動します。まず左から右、次に上から下に移動します。 テキストを入力したフィールドからカーソルが離れる場合、[クラスの詳細] ウィンドウはそのテキストを処理し、エラーがなければ格納します。<br /><br /> カーソルが [\<パラメーターの追加>] などの空フィールドにある場合、タブを押すと、それが次の行の最初のフィールドに移動します。|  
|\<Space>|カーソルが次のフィールドに移動します。まず左から右、次に上から下に移動します。 カーソルが [\<パラメーターの追加>] などの空のフィールドにある場合は、次の行の最初のフィールドに移動します。 コンマを押した直後に \<Space> キーを押しても無視されます。<br /><br /> カーソルが [概要] フィールドにある場合は、Space キーを押すと空白文字が追加されます。<br /><br /> カーソルが特定の行の [非表示] 列にある場合は、Space キーを押すと [非表示] チェック ボックスの値が切り替わります。|  
|Ctrl + Tab|別のドキュメント ウィンドウに切り替わります。 たとえば、[クラスの詳細] ウィンドウから、開かれているコード ファイルに切り替わります。|  
|Esc|フィールドにテキストを入力し始めた後に Esc キーを押すと、元に戻すキーとして動作し、フィールドの内容が元の値に戻ります。 [クラスの詳細] ウィンドウ全体にフォーカスがあり、特定のセルにフォーカスがない場合は、Esc キーを押すとフォーカスが [クラスの詳細] ウィンドウから別の場所に移ります。|  
|↑および↓|これらのキーによって、[クラスの詳細] ウィンドウのグリッドでカーソルが行から行に垂直方向に移動します。|  
|←|カーソルが [名前] 列にある場合は、←キーを押すと、階層で現在のノードが折りたたまれます (展開されている場合)。|  
|→|カーソルが [名前] 列にある場合は、→キーを押すと、階層で現在のノードが展開されます (折りたたまれている場合)。|  
  
## <a name="see-also"></a>関連項目  
 [型のメンバーの作成と構成 (クラス デザイナー)](../ide/creating-and-configuring-type-members-class-designer.md)