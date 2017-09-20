---
title: "[オプション] ダイアログ ボックス、[プロジェクトおよびソリューション]、[ビルド/実行] | Microsoft Docs"
ms.custom: 
ms.date: 7/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
caps.latest.revision: 20
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: e48ebcafaca37505dbcc92bce682d0c6169004e1
ms.openlocfilehash: 8e5165b4b17195e5f9172dd25962c9486a7aeeeb
ms.contentlocale: ja-jp
ms.lasthandoff: 07/26/2017

---

# <a name="options-dialog-box--projects-and-solutions-build-and-run"></a>[オプション] ダイアログ ボックス、[プロジェクトおよびソリューション]、[ビルド/実行]

このダイアログ ボックスで、同時にビルドできる Visual C++ または Visual C# のプロジェクトの最大数、特定の既定のビルドの動作、およびいくつかのビルドのログ設定を指定することができます。 これらのオプションにアクセスするには、**[ツール]、[オプション]** の順に選択し、**[プロジェクトおよびソリューション]** を展開し、**[ビルド/実行]** を選択します。
  
**並行してビルドするプロジェクトの最大数**  
同時にビルドできる Visual C++ および Visual C# のプロジェクトの最大数を指定します。 ビルド プロセスを最適化するため、並列プロジェクトのビルドの最大数が、コンピューターの CPU 数に自動的に設定されます。 最大値は 32 です。  

**実行時に、スタートアップ プロジェクトおよび依存関係のみをビルドする**  
F5 キーを使用する場合にスタートアップ プロジェクトとその依存関係のみをビルドするには、**[デバッグ]、[開始]**メニュー コマンドの順に選択するか、または **[ビルド]** メニューの適用可能なコマンドを選択します。 何も選択しないと、すべてのプロジェクトと依存関係がビルドされます。 

**実行時に、プロジェクトが最新の状態でないとき**  
*"[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] プロジェクトだけで使用できます。"*

F5 キーを押すか、**[デバッグ]、[開始]** コマンドの順に選択してプロジェクトを実行するとき、プロジェクトの構成が最新の状態でない場合には、既定の設定 **[ビルドするかどうかを確認する]** でメッセージが表示されます。 実行のたびにプロジェクトをビルドするには、**[常にビルドする]** を選択します。 プロジェクト実行時のすべての自動ビルドを抑止するには、**[ビルドしない]** を選択します。

**実行時に、ビルドまたは配置のエラーが発生したとき**  
*"[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] プロジェクトだけで使用できます。"*

F5 キーを押すか、**[デバッグ]、[開始]** コマンドの順に選択してプロジェクトを実行するとき、ビルドが失敗してもプロジェクトを実行する必要がある場合は、既定の設定 **[起動するかどうかを確認する]** でメッセージが表示されます。 **[古いバージョンを起動する]** を選択すると、最新の正常なビルドが自動的に起動されます。この結果として、実行コードとソース コードとの間に不一致が生じる可能性があります。 メッセージを抑止するには、**[起動しない]** を選択します。

**新しいソリューションでは現在選択されているプロジェクトをスタートアップ プロジェクトとして使用する**  
このオプションを設定すると、新しいソリューションでは現在選択されているプロジェクトがスタートアップ プロジェクトとして使用されます。  

**MSBuild プロジェクト ビルドの出力の詳細**  
ビルドの**[出力]** ウィンドウで表示される情報量を決定します。  

**MSBuild プロジェクト ビルド ログ ファイルの詳細**  
*"[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] プロジェクトだけで使用できます。"*

ビルド ログ ファイルに書き込まれる情報量を決定します。ビルド ログ ファイルは、\\...\\*ProjectName*\Debug\\*ProjectName*.log にあります。  

## <a name="see-also"></a>関連項目  
-[コードのコンパイルとビルド](../../ide/compiling-and-building-in-visual-studio.md)
- [[オプション] ダイアログ ボックス、[プロジェクトおよびソリューション]](projects-and-solutions-options-dialog-box.md)
- [[Web プロジェクト] ([オプション] ダイアログ ボックス - [プロジェクトおよびソリューション])](options-dialog-box-projects-and-solutions-web-projects.md)