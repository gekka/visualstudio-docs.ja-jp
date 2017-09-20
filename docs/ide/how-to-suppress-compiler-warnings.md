---
title: "方法: コンパイラの警告を非表示にする | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31827b17-f933-413d-b28a-b19f903b64ca
caps.latest.revision: 5
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 0c4c9c5a885b6f71b8531d4b04baecaec7f45949
ms.contentlocale: ja-jp
ms.lasthandoff: 05/13/2017

---
# <a name="how-to-suppress-compiler-warnings"></a>方法: コンパイラ警告を非表示にする
必要のないコンパイラの警告の種類を指定することで、ビルド ログを見やすくすることができます。 たとえば、この方法を使って、ビルド ログの詳細さを標準、詳細、または診断に設定したときに自動的に生成される情報の全部ではなく一部だけを確認できます。 詳細さについて詳しくは「[方法: ビルド ログ ファイルを表示、保存、および構成する](../ide/how-to-view-save-and-configure-build-log-files.md)」をご覧ください。  
  
### <a name="to-suppress-specific-warnings-for-visual-c-or-f"></a>Visual C# または F# の特定の警告を抑制するには #
  
1.  **ソリューション エクスプローラー**で、警告を抑制するプロジェクトを選びます。  
  
2.  メニュー バーの **[表示]**、 **[プロパティ ページ]**の順にクリックします。  
  
3.  **[ビルド]** ページを選びます。  
  
4.  **[警告の表示なし]** ボックスで表示しない警告のエラー コードをセミコロンで区切って指定した後、ソリューションをリビルドします。  
  
### <a name="to-suppress-specific-warnings-for-visual-c"></a>Visual C++ の特定の警告を抑制するには  
  
1.  **ソリューション エクスプローラー**で、警告を抑制するプロジェクトまたはソース ファイルを選びます。  
  
2.  メニュー バーの **[表示]**、 **[プロパティ ページ]**の順にクリックします。  
  
3.  **[構成プロパティ]** カテゴリを選び、**[C/C++]** カテゴリを選んだ後、**[詳細設定]** ページを選びます。  
  
4.  次のいずれかの操作を実行します。  
  
    -   **[指定の警告を無効にする]** ボックスで表示しない警告のエラー コードをセミコロンで区切って指定します。  
  
    -   **[指定の警告を無効にする]** ボックスで、**[編集]** を選んで他のオプションを表示します。  
  
5.  **[OK]** ボタンを選び、ソリューションをリビルドします。  
  
## <a name="suppressing-warnings-for-visual-basic"></a>Visual Basic の警告の抑制  
 プロジェクトの .vbproj ファイルを編集することで、Visual Basic コンパイラの特定の警告を非表示にできます。 また、[プロジェクト デザイナーの [コンパイル] ページ](../ide/reference/compile-page-project-designer-visual-basic.md)を使って、カテゴリ単位で警告を抑制することもできます。 詳しくは、「[Visual Basic での警告の構成](../ide/configuring-warnings-in-visual-basic.md)」をご覧ください。  
  
#### <a name="to-suppress-specific-warnings-for-visual-basic"></a>Visual Basic の特定の警告を抑制するには  
  
1.  **ソリューション エクスプローラー**で、警告を抑制するプロジェクトを選びます。  
  
2.  メニュー バーから、**[プロジェクト]**、**[プロジェクトのアンロード]** の順に選びます。  
  
3.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、**[<***プロジェクト名***>.vbproj の編集]** を選びます。  
  
     コード エディターでプロジェクト ファイルが開かれます。  
  
4.  ビルドしているビルド構成で `<NoWarn></NoWarn>` 要素を探します。  
  
     次の例では、x86 プラットフォームでのデバッグ ビルド構成の `<NoWarn></NoWarn>` 要素を太字で示してあります。  
  
    ```  
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">  
        <PlatformTarget>x86</PlatformTarget>  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <ErrorReport>prompt</ErrorReport>  
        <NoWarn></NoWarn>  
        <WarningLevel>1</WarningLevel>  
      </PropertyGroup>  
    ```  
  
5.  `<NoWarn>` 要素の値として、1 つ以上の警告番号を追加します。 複数の警告番号を指定する場合は、次の例のようにコンマで区切ります。  
  
    ```  
    <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|x86' ">  
        <PlatformTarget>x86</PlatformTarget>  
        <DebugSymbols>true</DebugSymbols>  
        <DebugType>full</DebugType>  
        <Optimize>false</Optimize>  
        <OutputPath>bin\Debug\</OutputPath>  
        <DefineDebug>true</DefineDebug>  
        <DefineTrace>true</DefineTrace>  
        <ErrorReport>prompt</ErrorReport>  
        <NoWarn>40059,42024</NoWarn>  
        <WarningLevel>1</WarningLevel>  
      </PropertyGroup>  
    ```  
  
6.  変更を .vbproj ファイルに保存します。  
  
7.  メニュー バーから、**[プロジェクト]**、**[プロジェクトの再読み込み]** の順に選びます。  
  
8.  メニュー バーから、**[ビルド]**、**[ソリューションのリビルド]** の順に選びます。  
  
     指定した警告が、**[出力]** ウィンドウに表示されなくなります。  
  
 詳しくは、「[/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル: アプリケーションをビルドする](../ide/walkthrough-building-an-application.md)   
 [方法: ビルド ログ ファイルを表示、保存、および構成する](../ide/how-to-view-save-and-configure-build-log-files.md)   
 [コードのコンパイルとビルド](../ide/compiling-and-building-in-visual-studio.md)
