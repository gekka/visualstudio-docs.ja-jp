---
title: Visual Studio のスタート ページのカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start page
ms.assetid: 925d42eb-ec34-426e-ad81-19db8630e536
caps.latest.revision: 48
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ece49968c4a887e89f91feb83fae3de23aa2c282
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49211485"
---
# <a name="customizing-the-start-page-for-visual-studio"></a>Visual Studio のスタート ページのカスタマイズ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio のスタート ページは、既定のさまざまな方法でカスタマイズできます。**[プロジェクトを開く]** ダイアログ ボックスを表示することも、最後に読み込まれたソリューションを開くこともできます。 また、カスタム スタート ページを表示することもできます。これは、ツール ウィンドウで実行される Windows Presentation Foundation (WPF) の XAML ページで、Visual Studio 内のコマンドを実行できます。  
  
## <a name="customizing-the-default-start-page"></a>既定のスタート ページのカスタマイズ  
  
1.  メニュー バーの **[ツール]**、 **[オプション]** の順にクリックします。  
  
2.  **[環境]** を展開し、**[スタートアップ]** を選びます。  
  
3.  **[スタートアップ時]** の一覧で、カスタマイズ対象の項目を選びます。  
  
## <a name="show-a-custom-start-page"></a>カスタム スタート ページの表示  
  
1.  次のいずれかの方法でカスタム スタート ページをインストールします。  
  
    -   [Visual Studio ギャラリー](http://visualstudiogallery.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=start%20page)、別の Web サイト、またはローカル イントラネットのページからインストールします。  
  
        > [!NOTE]
        >  Visual Studio の旧バージョンを対象とするページの場合、Visual Studio SDK を使用してページをアップグレードできます。 参照してください[方法: Visual Studio のカスタム スタート ページをアップグレード](../misc/how-to-upgrade-a-visual-studio-custom-start-page.md)します。  
  
         カスタム スタート ページを含む .vsix ファイルを開くか、コピーして、スタート ページのファイルに貼り付けます、 **%USERPROFILE% \My Documents\Visual Studio 2015 \startpages**コンピューター上のフォルダー。  
  
    -   Visual Studio SDK をインストールしている場合は独自のスタート ページを作成できます。  
  
         参照してください[スタート ページを独自に作成](../misc/creating-your-own-start-page.md)です。  
  
2.  メニュー バーの **[ツール]**、 **[オプション]** の順にクリックします。  
  
3.  **[環境]** を展開し、**[スタートアップ]** を選びます。  
  
4.  **[スタート ページのカスタマイズ]** の一覧で、使用するページを選択します。  
  
> [!NOTE]
>  カスタム スタート ページのエラーによって Visual Studio がクラッシュする場合、セーフ モードで Visual Studio を起動し、既定のスタート ページを使用するように設定します。 「[/SafeMode (devenv.exe)](../ide/reference/safemode-devenv-exe.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [独自のスタート ページの作成](../misc/creating-your-own-start-page.md)



