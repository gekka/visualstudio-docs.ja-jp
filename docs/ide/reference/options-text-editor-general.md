---
title: "[オプション]、[テキスト エディター]、[全般] | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.TOOLSOPTIONSPAGES.TEXT_EDITOR.SQL_SERVER_TOOLS.GENERAL
- VS.ToolsOptionsPages.Text_Editor.All_Languages.General
- VS.ToolsOptionsPages.Text_Editor.RDL_Expression.General
- VS.ToolsOptionsPages.Text_Editor.SQL.General
- vs.toolsoptionspages.text_editor
- VS.ToolsOptionsPages.Text_Editor.XML.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL80.General
- VS.ToolsOptionsPages.Text_Editor.CSS
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.General
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.General
- VS.ToolsOptionsPages.Text_Editor.SQL_Script.General
- VS.ToolsOptionsPages.Text_Editor.CSharp.General
- VS.ToolsOptionsPages.Text_Editor.All_Languages
- VS.ToolsOptionsPages.Text_Editor.T-SQL7.General
- VS.ToolsOptionsPages.Text_Editor.Basic.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL.General
- vs.toolsoptionspages.text_editor.visual_jsharp
- VS.ToolsOptionsPages.Text_Editor.F#.Tabs
- VS.ToolsOptionsPages.Text_Editor.F#
- VS.ToolsOptionsPages.Text_Editor.PL/SQL.General
- VS.ToolsOptionsPages.Text_Editor.C/C++.General
- VS.ToolsOptionsPages.Text_Editor.Plain_Text
- VS.ToolsOptionsPages.Text_Editor.HTML
- VS.ToolsOptionsPages.Text_Editor.XAML.General
- VS.ToolsOptionsPages.Text_Editor
- VS.ToolsOptionsPages.Text_Editor.F#.General
- VS.ToolsOptionsPages.Text_Editor.XOML.General
- VS.ToolsOptionsPages.Text_Editor.SQL
- vs.toolsoptionspages.text_editor.c/c++
- VS.ToolsOptionsPages.Text_Editor.SQL_Script
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.General
- VS.ToolsOptionsPages.Text_Editor.General
- VS.ToolsOptionsPages.Text_Editor.CSharp
helpviewer_keywords:
- Text Editor Options dialog box
- Code Editor
- Text Editor [Visual Studio]
- editors, global settings
ms.assetid: 4ac21e48-3243-4141-9058-7eaf12b3cde7
caps.latest.revision: 29
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
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: eee3b34e9f473c200463b65f1b839416f5dce0ec
ms.contentlocale: ja-jp
ms.lasthandoff: 05/24/2017

---
# <a name="options-text-editor-general"></a>[オプション]、[テキスト エディター]、[全般]
このダイアログ ボックスでは、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] コード/テキスト エディターのグローバル設定を変更できます。 このダイアログ ボックスを表示するには、**[ツール]** メニューの **[オプション]** をクリックし、**[テキスト エディター]** フォルダーを展開し、**[全般]** をクリックします。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](../../ide/personalizing-the-visual-studio-ide.md)」を参照してください。  
  
## <a name="settings"></a>設定  
 [ドラッグ アンド ドロップ編集]  
 選択すると、マウスでテキストを選択してドラッグし、現在の文書内や開いている他の文書内の別の場所に移動させることができます。  
  
 [区切り記号を自動強調表示する]  
 選択すると、パラメーターまたは項目/値の組を分ける区切り文字とそれに対応する括弧が強調表示されます。  
  
 [変更履歴を記録する]  
 コード エディターが選択されているとき、マージンに黄色の縦線が表示され、ファイルが前回保存されてから変更されたコードに印を付けます。 変更を保存すると、縦線は緑色になります。  
  
 [シグネチャ (BOM) なしの UTF-8 エンコードを自動検出]  
 既定では、エディターはバイト オーダー マークまたは文字セット タグを探してエンコードを検出します。 現在の文書でいずれも見つからない場合、コード エディターはバイト順序をスキャンし、UTF-8 エンコードを自動検出します。 エンコードの自動検出を無効にするには、このオプションをオフにします。  
  
## <a name="display"></a>表示  
 [マージン]  
 選択すると、エディターのテキスト領域の左端に沿って縦の余白が表示されます。 この余白をクリックしてテキスト行全体を選択したり、クリックしてドラッグし、連続するテキスト行を選択したりできます。  
  
|マージン オン|マージン オフ|  
|-------------------------|--------------------------|  
|![HTMLpageSelectionMarginOn スクリーンショット](../../ide/reference/media/vxselmaron.gif "vxSelmaron")|![HTMLpageSelectionMarginOff スクリーンショット](../../ide/reference/media/vxselmaroff.gif "vxSelmaroff")|  
  
 インジケーター マージン  
 選択すると、エディターのテキスト領域の左端の外に縦の余白が表示されます。 この余白をクリックすると、アイコンとテキストに関連付けられているヒントが表示されます。 たとえば、インジケーター マージンにブレークポイントやタスク一覧のショートカットが表示されます。 インジケーター マージンの情報は印刷されません。  
  
 [垂直スクロール バー]  
 選択すると、垂直スクロール バーが表示されます。このバーで上下にスクロールし、エディターの表示領域外の要素を表示できます。 縦のスクロール バーが利用できない場合、Page Up キー、Page Down キー、カーソル キーでスクロールできます。  
  
 [水平スクロール バー]  
 選択すると、水平スクロール バーが表示されます。このバーで左右にスクロールし、エディターの表示領域外の要素を表示できます。 水平スクロール バーが表示されない場合は、カーソル キーでスクロールできます。  
  
 [現在の行を強調表示する]  
 選択すると、カーソルが置かれているコード行の周りに灰色のボックスが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [[オプション]、[テキスト エディター]、[すべての言語]](../../ide/reference/options-text-editor-all-languages.md)   
 [[オプション]、[テキスト エディター]、[すべての言語]、[タブ]](../../ide/reference/options-text-editor-all-languages-tabs.md)   
 [[オプション]、[テキスト エディター]、[ファイル拡張子]](../../ide/reference/options-text-editor-file-extension.md)   
 [キーボード ショートカットの識別とカスタマイズ](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)   
 [エディターのカスタマイズ](../../ide/customizing-the-editor.md)   
 [IntelliSense の使用](../../ide/using-intellisense.md)