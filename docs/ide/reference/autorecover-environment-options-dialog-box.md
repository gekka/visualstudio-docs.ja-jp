---
title: "[自動バックアップ] ([オプション] ダイアログ ボックス - [環境]) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPag.Environment.AutoRecover
- VS.DialogAutoRestore
- VS.ToolsOptionsPages.Environment.AutoRecover
- VS.ToolsOptionsPages.Environment.Auto_Save_and_Restore
helpviewer_keywords:
- files, recovering
- AutoRecover page
- saving files, automatically
- files, saving automatically
ms.assetid: 397e5e44-4bbe-4289-94d1-642b466c9111
caps.latest.revision: 14
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
ms.openlocfilehash: 320b31b01237656be157be9ad9ce5787521215db
ms.contentlocale: ja-jp
ms.lasthandoff: 05/24/2017

---
# <a name="autorecover-environment-options-dialog-box"></a>[自動バックアップ]\ ([オプション] ダイアログ ボックス - [環境])
[オプション] ダイアログ ボックスのこのページを使用し、ファイルを自動的にバックアップするかどうかを指定します。 このページではまた、IDE (統合開発環境) が突然シャットダウンしたとき、変更済みのファイルを復元するかどうかも指定できます。 このダイアログ ボックスにアクセスするには、**[ツール]** メニューを選択し、**[オプション]** を選択し、**[環境]** フォルダーを選択し、**[自動バックアップ]** ページを選択します。 このページが一覧に表示されない場合は、**[オプション]** ダイアログ ボックスの **[すべての設定を表示]** を選択します。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、[ツール] メニューの [設定のインポートとエクスポート] をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](../../ide/personalizing-the-visual-studio-ide.md)」を参照してください。  
  
 **自動バックアップの実行間隔: \<n> 分**  
 このオプションを使用し、エディターでファイルを自動的に保存する頻度をカスタマイズします。 以前に保存したファイルに関しては、ファイルのコピーは \\...\My Documents\Visual Studio \<*version*>\Backup Files\\<*projectname*> に保存されています。 ファイルが新しく、手動で保存されていない場合、ファイルはランダムに生成されたファイル名で自動保存されます。  
  
 **自動バックアップした情報の保存期間: \<n> 日**  
 このオプションを使用し、Visual Studio で自動バックアップのために作成したファイルを保存する期間を指定します。  
  
## <a name="see-also"></a>関連項目  
 [[オプション] ダイアログ ボックス](../../ide/reference/options-dialog-box-visual-studio.md)