---
title: '方法: IIS のプロパティ設定を確認します |。Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- IIS, property settings
- debugging Web applications, troubleshooting
- IIS administration tool
- Web applications, setting properties
- properties [debugger], setting with IIS administration tool
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f98796a7fd9546c8377eefcc4ad25fb90e549544
ms.sourcegitcommit: dd839de3aa24ed7cd69f676293648c6c59c6560a
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "52389488"
---
# <a name="how-to-verify-iis-property-settings"></a>方法 : IIS のプロパティ設定を確認する

IIS 管理ツールで、Web アプリケーションのプロパティを設定できます。 これらのプロパティは、実行するアプリケーションに合わせて正しく設定する必要があります。そのため、トラブルシューティングのときに、多くの場合、設定を確認することが必要になります。

> [!NOTE]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、次を参照してください。[設定にリセット](../ide/environment-settings.md#reset-settings)します。

## <a name="to-check-iis-settings-for-the-web-application"></a>Web アプリケーションの IIS 設定をチェックするには

1. **[管理ツール]** ウィンドウを開くには、**[スタート]** メニューの **[プログラム]** をポイントし、次に **[管理ツール]** をクリックします。 **[管理ツール]** が **[プログラム]** メニューに表示されないときは、**[コントロール パネル]** を検索します。

   -   Windows 2000 では、**[インターネット サービス マネージャー]** を選択します。

   -   Windows XP では、**[インターネット インフォメーション サービス]** を選択します。

   -   Windows Server 2003 では、**[サーバーの管理]** をダブルクリックします。

        **[サーバーの管理]** ウィンドウが開きます。 **[アプリケーション サーバー]** の下にある **[このアプリケーション サーバーを管理する]** をクリックします。

        **[アプリケーション サーバー]** ウィンドウが開きます。 左側のペインで、**[インターネット インフォメーション サービス (IIS) マネージャー]** ノードを開きます。

2. ダイアログ ボックスで、使用しているコンピューターのツリー コントロール ノードをクリックします。 **[Web サイト]** ノードをクリックし、Web アプリケーションのノードを選択します。 このノードは、[Web サイト] ノード (**[既定の Web サイト]** ノードの兄弟ノード)、または既存の Web サイト ノード下にある仮想ディレクトリ ノードのいずれかになります。

3. Web アプリケーションを右クリックし、ショートカット メニューの **[プロパティ]** をクリックします。

4. Web アプリケーションのセキュリティ設定を確認します。

   1.  Web アプリケーションの **[プロパティ]** ウィンドウで、**[ディレクトリ セキュリティ]** タブをクリックし、**[編集]** をクリックします。

   2.  **[認証方法]** ダイアログ ボックスで、**[匿名アクセスを有効にする]** および **[統合 Windows 認証]** を選択します (選択されていない場合)。

   3.  **[OK]** をクリックして **[認証方法]** ダイアログ ボックスを閉じます。

5. ATL Server アプリケーションの場合は、DEBUG の動詞が ISAPI 拡張機能に関連付けられていることを確認してください。 詳細については、次を参照してください。[方法: 拡張機能とデバッグ動詞を関連付ける](https://msdn.microsoft.com/library/50d261d3-4bd4-41c0-b44e-3591086f121e)します。

6. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリケーションの場合、アプリケーションの仮想フォルダーに、**インターネット インフォメーション サービス (IIS) マネージャー**、**インターネット サービス マネージャー**、または**インターネット インフォメーション サービス**で設定されたアプリケーション名があることを確認します。

   1.  Web アプリケーションの **[プロパティ]** ウィンドウで、**[ディレクトリ]** タブ (アプリケーションが仮想ディレクトリにある場合) または **[ホーム ディレクトリ]** タブ (アプリケーションが Web サイトにある場合) を選択します。

   2.  **[ローカル パス]** の名前が、アプリケーションを実際に配置したディレクトリ名と一致することを確認します。

   3.  **[アプリケーションの設定]** の下に、アプリケーションが格納されている root ディレクトリの名前を入力します。

   4.  **[OK]** をクリックして、**[プロパティ]** ダイアログ ボックスを閉じます。

7. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] アプリケーションの場合、**[ASP.NET]** タブをクリックし、正しいバージョンの [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] が指定されていることを確認します。

8. **[OK]** をクリックして、**[プロパティ]** ダイアログ ボックスを閉じます。

9. **[OK]** をクリックして、**[インターネット インフォメーション サービス (IIS) マネージャー]**、**[インターネット サービス マネージャー]**、または **[インターネット インフォメーション サービス]** の各ダイアログ ボックスを閉じます。

## <a name="see-also"></a>関連項目

- [トラブルシューティング](../debugger/debugging-web-applications-troubleshooting.md)