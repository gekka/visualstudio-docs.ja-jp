---
title: "チュートリアル: SharePoint のサイト列、コンテンツ タイプ、およびリストの作成"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.ListDesigner.GeneralMessageHelp"
  - "Microsoft.VisualStudio.SharePoint.Designers.ListDesigner.ViewModels.ListViewModel.SortingAndGrouping"
  - "VS.SharePointTools.ListDesigner.SortingGrouping"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio での SharePoint 開発, コンテンツ タイプ"
  - "Visual Studio での SharePoint 開発, フィールド"
  - "Visual Studio での SharePoint 開発, リスト定義"
  - "Visual Studio での SharePoint 開発, リスト インスタンス"
ms.assetid: caebacc2-616c-4373-8e21-edc7979338e7
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# チュートリアル: SharePoint のサイト列、コンテンツ タイプ、およびリストの作成
  次の手順では、サイト内の列を使用するコンテンツ タイプとしておらず、*フィールドとして*カスタムの SharePoint サイトを列または作成する方法を示します。  また、新しいコンテンツ タイプを使用してリストを作成する方法を示します。  
  
 このチュートリアルでは、次のタスクについて説明します。  
  
-   [Creating Custom でサイト内の列](#BKMK_CreatingCustSiteCols)。  
  
-   [カスタム コンテンツ タイプの作成](#BKMK_CreateCustContType)。  
  
-   [リストの作成](#BKMK_CreateList)。  
  
-   [リストの作成](#BKMK_CreateList)。  
  
-   [アプリケーションのテスト](#BKMK_TestApp)。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   サポート対象エディションの Windows と SharePoint。  詳細については、「[SharePoint ソリューションの開発要件](../sharepoint/requirements-for-developing-sharepoint-solutions.md)」を参照してください。  
  
-   Visual Studio  
  
##  <a name="BKMK_CreatingCustSiteCols"></a> Creating Custom でサイト内の列  
 この例では、病院の管理の患者のリストを作成します。  まず、[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] で次のように SharePoint のプロジェクトを作成し、サイト内の列を追加する必要があります。  
  
#### プロジェクトを作成するには  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] の **\[ファイル\]** メニューで、**\[プロジェクト\]\[新規作成\]** をクリックします。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスで、**\[Visual C\#\]** または **\[Visual Basic\]** で、**\[SharePoint\]** ノードを展開し、**2010**をクリックします。  
  
3.  **\[テンプレート\]** のペインで、**\[SharePoint 2010 プロジェクト\]** をクリックします、プロジェクトの名前をクリニックに変更し、**\[OK\]** ボタンをクリックします。  
  
     SharePoint 2010 プロジェクト テンプレートは後で追加する他のプロジェクト項目、サイト内の列が含まれているために、この例で使用される空のプロジェクトです。  
  
4.  **\[デバッグのサイトとセキュリティ レベルの指定\]** ページで、新しいカスタム フィールド項目の追加先と入力するか、既定の場所 \(`http://<`*SystemName*`>/)`を使用してローカルの SharePoint サイトの URL です。  
  
5.  **\[この SharePoint ソリューションの信頼レベル\]** セクションでは、**\[サンドボックス ソリューションとして配置する\]** の既定値を使用します。  
  
     サンドボックス化ソリューションとファーム ソリューションの違いの詳細については、「[サンドボックス ソリューションの考慮事項](../sharepoint/sandboxed-solution-considerations.md)」を参照してください。  
  
6.  **\[完了\]** をクリックします。  プロジェクトは **\[ソリューション エクスプローラー\]** に表示されます。  
  
#### サイト内の列を追加します。  
  
1.  新しいサイト内の列を追加します。  これは、**\[ソリューション エクスプローラー\]** で、**\[クリニック\]** のショートカット メニューを開き、**\[新しいアイテム\]**、**\[追加\]** をクリックします。  
  
2.  **\[新しいアイテムの追加\]** ダイアログ ボックスで、**\[サイト列\]** をクリックします、名前を Patient Name に変更し、**\[追加\]** ボタンをクリックします。  
  
3.  サイト内の列の Elements.xml ファイルで、**\[テキスト\]** として設定する **\[種類\]** のままクリニックのサイト内の列に設定する **\[グループ\]** を変更します。  完了すると、サイト内の列の Elements.xml ファイルは次の例のようになります。  
  
    ```  
    <Field  
         ID="{f9ba60d1-5631-41fb-b016-a38cf48eef63}"  
         Name="Clinic - Patient Name"  
         DisplayName="Patient Name"  
         Type="Text"  
         Required="FALSE"  
         Group="Clinic Site Columns">  
    </Field>  
    ```  
  
4.  同じ手順を使用して、プロジェクトに 2 個以上のサイト内の列を追加する: 患者 ID \(種類 \= 「整数\) 」および" Type 博士 \= 「text」\)。  クリニックのサイト内の列グループに値を設定します。  
  
##  <a name="BKMK_CreateCustContType"></a> カスタム コンテンツ タイプの作成  
 次に、前の手順で作成したサイト内の列を含む型、連絡先の内容で型ベースのコンテンツを作成します。  既存のコンテンツ タイプにコンテンツ タイプを基にして、ベース コンテンツ タイプが新しいコンテンツ タイプを使用して複数のサイト内の列を提供するため、時間を節約できます。  
  
#### カスタム コンテンツ タイプを作成するには  
  
1.  プロジェクトにコンテンツ タイプを追加します。  これは、**\[ソリューション エクスプローラー\]** で、プロジェクト ノードを選択します。  
  
2.  メニュー バーで **\[プロジェクト\]**、**\[新しい項目の追加\]** の順に選択します。  
  
3.  **\[Visual C\#\]** または **\[Visual Basic\]** で、**\[SharePoint\]** ノードを展開し、**2010** ノードを選択します。  
  
4.  **\[テンプレート\]** のペインで、**\[コンテンツ タイプ\]** テンプレートを選択し、患者のヒントに名前を変更し、**\[追加\]** ボタンをクリックします。  
  
     **\[SharePoint カスタマイズ ウィザード\]** が開きます。  
  
5.  **\[このコンテンツ タイプの継承元となる基本コンテンツ タイプ\]** ボックスの一覧で、新しいコンテンツ タイプを使用 **\[完了\]**、をクリックするコンテンツ タイプとして **\[連絡先\]** をクリックします。  
  
     これを行うには、以前に定義したサイト内の列に加えて、連絡先のコンテンツ タイプの他の便利な削除は、サイト内の列へのアクセスを提供します。  
  
6.  コンテンツ タイプのデザイナーが **\[列\]** タブで、表示されたら、前に定義した 3 個のサイト内の列を追加する: **\[Patient Name\]**、**\[患者 ID\]** と **\[Name 博士\]**。  これらの列を追加するには、サイト内の列の最初のリスト ボックスの一覧と **\[表示名\]** の下に移動し、一つずつ選択し、リストの各サイト内の列を選択します。  
  
    > [!TIP]  
    >  サイト内の列をすばやく選択するには、列名の最初の数文字を入力すると、一覧をフィルター処理します。  
  
7.  3 種類のカスタム サイト内の列のほかに、サイト内の列の一覧から **\[コメント\]** でサイト内の列を追加します。  
  
8.  **\[Patient Name\]** に **\[必要な領域\]** のチェック ボックスをオンにすると、変更を行った **\[患者 ID\]** のサイト内の列がフィールドが必要です。  
  
9. **\[コンテンツ タイプ\]** タブで、コンテンツ タイプの名前が **\[患者のヒント\]** であることを確認し、患者の情報カードに説明を変更します。  
  
10. **\[グループ名\]** をクリニックのコンテンツ タイプに変更し、既定値で他の設定をそのまま使用します。  
  
11. メニュー バーで、**\[すべて保存\]\[ファイル\]** をクリックします、次にコンテンツ タイプのデザイナーを閉じます。  
  
##  <a name="BKMK_CreateList"></a> リストの作成  
 今度は、新しいコンテンツ タイプおよびサイト内の列を使用してリストを作成します。  
  
#### リストを作成するには  
  
1.  プロジェクトにリストを追加します。  これは、**\[ソリューション エクスプローラー\]** で、プロジェクト ノードを選択します。  
  
2.  メニュー バーで **\[プロジェクト\]**、**\[新しい項目の追加\]** の順に選択します。  
  
3.  **\[Visual C\#\]** または **\[Visual Basic\]** で、**\[SharePoint\]** ノードを展開し、**2010** ノードを選択します。  
  
4.  **\[テンプレート\]** のペインで、**\[リスト\]** のテンプレートを選択して、患者に名前を変更し、**\[追加\]** ボタンをクリックします。  
  
5.  **\[既定 \(空白\)\]** として設定する **\[次に基づいてリストをカスタマイズ\]** のまま **\[完了\]** 次へボタンをクリックします。  
  
6.  リストのデザイナーでは、**\[コンテンツ タイプ設定\]** ダイアログ ボックスを表示するに **\[コンテンツ タイプ\]** ボタンをクリックします。  
  
7.  新しい行を選択し、**\[患者のヒント\]** のコンテンツ タイプをコンテンツの一覧の種類を選択し、**\[OK\]** ボタンをクリックします。  
  
     これを行うには、リストに **\[患者のヒント\]** コンテンツ タイプからサイト内の列を追加します。  
  
8.  次を除くリストでサイト内の列をすべて削除する:  
  
    -   患者 ID  
  
    -   Patient Name  
  
    -   たとえば、  
  
    -   電子メール  
  
    -   Name 博士  
  
    -   コメント  
  
9. **\[列の表示名\]** で、空の行を選択し、カスタム リスト内の列を追加し、病院という名前を付けます。  **\[1 行テキスト\]** としてデータ型をそのまま使用します。  
  
     カスタム リスト内の列がこのリストにのみ適用されます。  一覧にカスタム リスト内の列を追加すると、リストに追加される既定の一覧にすべての列を含む新しいリスト コンテンツ タイプは、作成および設定されます。  
  
    > [!TIP]  
    >  サイト内の列の一覧で列を選択し、既存のサイト内の列が使用されます。  ただし、一覧で列を選択しないで列名値を入力すると、カスタム リスト内の列が同じ名前の列が一覧に存在している場合は、作成されます。  
  
     必要に応じて、カスタム リスト内の列のデータ型が **\[1 行テキスト\]** に設定するのではなく、参照には、その列のデータ型を設定できる値は、テーブルまたは別の一覧から取得されます。  参照列については、[SharePoint 2010 のリスト関係](http://go.microsoft.com/fwlink/?LinkId=224994) "参照してください [参照とリスト関係](http://go.microsoft.com/fwlink/?LinkID=224995)。  
  
10. **\[患者 ID\]** と **\[Patient Name\]** ボックスの横にある **\[必要な領域\]** チェック ボックスをオンにします。  
  
11. **\[ビュー\]** タブで、表示を作成する空の行をクリックします。  患者の詳細を入力します。  
  
     **\[ビュー\]** タブで、SharePoint リストに表示する列を指定できます。  
  
12. **\[患者の詳細\]** の新しい行を選択し、**\[既定に設定\]** ボタンをクリックします。  
  
     これで、新しいビューがリストの既定のビューです。  
  
13. 次の順序で **\[選択されている列\]** の一覧に次の列を追加する:  
  
    -   患者 ID  
  
    -   Patient Name  
  
    -   たとえば、  
  
    -   電子メール  
  
    -   Name 博士  
  
    -   病院  
  
    -   コメント  
  
14. **\[プロパティ\]** の一覧で、**\[並べ替えとグループ化\]** のプロパティを選択し、**\[並べ替えとグループ化\]** ダイアログ ボックスを ![省略記号アイコン](~/sharepoint/media/ellipsisicon.gif "省略記号アイコン") 表示するには、…ボタンをクリックします。  
  
15. **\[列名\]** の一覧で、**\[Patient Name\]** をクリックします、**\[並べ替え\]** の列が **\[昇順\]** に設定されている、**\[OK\]** ボタンをクリックします。  
  
##  <a name="BKMK_TestApp"></a> アプリケーションのテスト  
 カスタム サイト内の列、コンテンツ タイプ、リストの準備が整うと、これらを SharePoint に配置した後、テストのアプリケーションを実行します。  
  
#### アプリケーションをテストするには  
  
1.  メニュー バーで、**\[ファイル\]**、**\[すべてを保存\]** の順に選択します。  
  
2.  F5 キーを選択してアプリケーションを実行します。  
  
     アプリケーションがコンパイルされ、フィーチャーが SharePoint に配置され、アクティブにします。  
  
3.  高速のナビゲーション バーで、**\[患者\]** を一覧表示するに **\[患者\]** リンクをクリックします。  
  
     リスト内の項目の名前が [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]で **\[ビュー\]** タブで入力した項目の名前と一致する必要があります。  
  
4.  Patient カード情報を作成するに **\[新しいアイテムの追加\]** リンクをクリックします。  
  
5.  情報をフィールドに入力し、**\[保存\]** ボタンをクリックします。  
  
     新しいレコードが表示されます。  
  
## 参照  
 [SharePoint のサイト列、コンテンツ タイプ、およびリストの作成](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [方法: Create a Custom Field の型](http://go.microsoft.com/fwlink/?LinkId=192079)   
 [コンテンツ タイプ](http://go.microsoft.com/fwlink/?LinkId=192080)   
 [列](http://go.microsoft.com/fwlink/?LinkId=192081)  
  
  