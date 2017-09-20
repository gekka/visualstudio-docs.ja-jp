---
title: "[プロジェクトおよびソリューション] の [オプション] ダイアログ ボックス | Microsoft Docs"
ms.custom: 
ms.date: 7/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.General
- VS.ToolsOptionsPages.Projects.Locations
helpviewer_keywords:
- Projects and Solutions Options dialog box
- Options dialog box, Projects and Solutions
ms.assetid: 2801f24e-a138-488a-ae3c-e1f99a678ac0
caps.latest.revision: 12
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 17defdd0b96ec1c3273fc6b845af844b031a4a17
ms.openlocfilehash: 2778964a6d5e4f478422727b02e15a058868e644
ms.contentlocale: ja-jp
ms.lasthandoff: 09/06/2017

---
# <a name="projects-and-solutions-options-dialog-box"></a>[プロジェクトおよびソリューション] の [オプション] ダイアログ ボックス

プロジェクトおよびソリューションに関連する [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 動作を設定します。 これらのオプションにアクセスするには、**[ツール]、[オプション]** の順に選択し、**[プロジェクトおよびソリューション]** を展開し、**[全般]** をクリックします。

プロジェクトおよびテンプレート フォルダーの既定のパスは、同じダイアログ ボックスの **[場所]** タブで設定します。
  
> [!NOTE]
>  使用している設定またはエディションによっては、ダイアログ ボックスで使用可能なオプションや、メニュー コマンドの名前や位置がヘルプに記載されている内容と異なる場合があります。 このヘルプ ページは、**全般的な開発設定**を考慮して記述されています。 設定を表示または変更するには、[**ツール**] メニューの [**設定のインポートとエクスポート**] をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](../../ide/personalizing-the-visual-studio-ide.md)」を参照してください。  
  
## <a name="general-tab-options"></a>[全般] タブのオプション  
 
**[ライトウェイト ソリューション ロード]**: IDE で大規模なソリューションを読み込む場合に必要な時間とメモリの量を減らすことができます。 ライトウェイト ソリューション ロードを使用すると、多くの C#、Visual Basic、または C++ プロジェクトを含む大規模なソリューションのパフォーマンスが大幅に向上する可能性があります。

- **[Let Visual Studio choose what's best for my solution]\(ソリューションに最適な機能を Visual Studio に選択させる\)**: Visual Studio は、ソリューションの特性に基づいてくライトウェイト ソリューション ロードを適用するかどうかを自動的に判断します。
- **[有効]**: ソリューションを読み込むときに、常にライトウェイト ソリューション ロードが適用されます。
- **[無効]**: ライトウェイト ソリューション ロードは適用されません。

詳細については、[「Visual Studio の起動時間の最適化」](../optimize-visual-studio-startup-time.md#speed_up_solution_load) を参照してください。

**ビルドがエラーで終了した場合には常にエラー一覧を表示する**  
プロジェクトのビルドが失敗した場合にのみ、ビルドの完了時に [**エラー一覧**] ウィンドウを開きます。 ビルド処理中に発生したエラーが表示されます。 このオプションがオフの場合、エラーは引き続き発生しますが、ビルドの完了時にウィンドウは開きません。 既定では、このオプションは有効になっています。  

**ソリューション エクスプローラーでアクティブなアイテムを追跡する**  
選択した場合、**ソリューション エクスプローラー**が自動的に開いて、アクティブな項目が選択されます。 選択される項目は、プロジェクトまたはソリューション内の別のファイルや、デザイナー内の異なるコンポーネントを処理の対象にすると変更されます。 このオプションがオフのとき、**ソリューション エクスプローラー**での選択内容は自動的に変更されません。 既定では、このオプションは有効になっています。  

**ビルド構成の詳細を表示**  
選択した場合、ビルドの構成オプションが [**プロジェクト プロパティ ページ**] ダイアログ ボックスおよび [**ソリューション プロパティ ページ**] ダイアログ ボックスに表示されます。 オフにすると、ビルドの構成オプションは、1 つの構成または 2 つの構成のデバッグとリリースを含む  **および**  プロジェクトのための、[**プロジェクト プロパティ ページ**] ダイアログ ボックスや [[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]ソリューション プロパティ ページ[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]] ダイアログ ボックスに表示されません。 プロジェクトにユーザー定義の構成がある場合、ビルドの構成オプションが表示されます。  

オフの場合、[**ビルド**] メニューのコマンド ([**ソリューションのビルド**]、[**ソリューションのリビルド**]、[**ソリューションのクリーン**] など) はリリース構成で実行され、[**デバッグ**] メニューのコマンド ([**デバッグ開始**]、[**デバッグなしで開始**] など) はデバッグ構成で実行されます。  

**常にソリューションを表示**  
選択した場合、ソリューションおよびソリューションで動作するすべてのコマンドが常に IDE に表示されます。 オフの場合、すべてのプロジェクトはスタンドアロン プロジェクトとして作成され、ソリューションに 1 つのプロジェクトだけが含まれている場合、ソリューション エクスプローラー内のソリューションや、IDE 内のソリューションで動作するコマンドは表示されません。  

**新しいプロジェクトを作成時に保存する**  
選択すると、[**新しいプロジェクト**] ダイアログ ボックスにプロジェクトの場所を指定できます。 オフの場合、すべての新しいプロジェクトは一時プロジェクトとして作成されます。 一時プロジェクトで作業する場合、ディスクの場所を指定しなくても、プロジェクトを作成して試してみることができます。  

**プロジェクトの場所が信頼されていないときにユーザーに警告**  
完全に信頼されていない場所 (UNC パスの上や HTTP パスの上など) で、新しいプロジェクトの作成または既存のプロジェクトのオープンを試行すると、メッセージが表示されます。 このオプションを使用して、完全に信頼されていない場所でプロジェクトの作成またはオープンを試行するたびにメッセージを表示するかどうかを指定します。  

**ビルド開始時に出力ウィンドウを表示**  
ソリューション ビルドの開始時に、IDE の出力ウィンドウを自動的に表示します。 詳細については、「[方法 : 出力ウィンドウを制御する](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858)」を参照してください。

**ファイル名の変更時にシンボルの名前変更を求めるプロンプトを出す**  
選択すると、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] がコード要素に対するプロジェクト内のすべての参照も名前変更するかどうかを確認する、メッセージ ボックスが表示されます。  

**[Prompt before moving files to a new location]\(新しい場所にファイルを移動する前にメッセージを表示する\)**  
選択すると、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、ソリューション エクスプ ローラーでの操作によってファイルの場所が変更される前に確認メッセージ ボックスを表示します。 

## <a name="locations-tab-options"></a>[場所] タブのオプション

**プロジェクトの場所**  
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] が新しいプロジェクトとソリューション フォルダーを作成する既定の場所を指定します。 複数のダイアログ ボックスも、このオプションで指定した場所をフォルダーの開始点として使用します。 たとえば、[プロジェクトを開く] ダイアログ ボックスは、この場所を [マイ プロジェクト] のショートカットのために使用します。  

**ユーザー プロジェクト テンプレートの場所**  
**[新しいプロジェクト]** ダイアログ ボックスで **[マイ テンプレート]** の一覧を作成するときに使用される既定の場所を指定します。 詳細については、「[方法 : プロジェクト テンプレートと項目テンプレートを配置して整理する](../../ide/how-to-locate-and-organize-project-and-item-templates.md)」を参照してください。  

**ユーザー項目テンプレートの場所**  
**[新しい項目の追加]** ダイアログ ボックスで **[マイ テンプレート]** の一覧を作成するときに使用される既定の場所を設定します。 詳細については、「[方法 : プロジェクト テンプレートと項目テンプレートを配置して整理する](../../ide/how-to-locate-and-organize-project-and-item-templates.md)」を参照してください。 

## <a name="see-also"></a>関連項目  
- [[オプション] ダイアログ ボックス、[プロジェクトおよびソリューション]、[ビルド/実行]](../../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- - [[Web プロジェクト] ([オプション] ダイアログ ボックス - [プロジェクトおよびソリューション])](../../ide/reference/options-dialog-box-projects-and-solutions-web-projects.md)