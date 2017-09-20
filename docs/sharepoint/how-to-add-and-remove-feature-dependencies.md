---
title: "方法: フィーチャーの依存関係を追加および削除する"
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
  - "MICROSOFT.VISUALSTUDIO.SHAREPOINT.DESIGNERS.CUSTOMDEPENDENCYWINDOW"
  - "VS.SHAREPOINTTOOLS.RAD.FEATUREDESIGNERDEPENDENCY"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio での SharePoint 開発, 機能"
ms.assetid: 2b34c8d9-c975-4fe9-b8e0-52db4a6014ea
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 方法: フィーチャーの依存関係を追加および削除する
  SharePoint フィーチャーが、他のフィーチャーの機能またはデータに依存している場合があります。  その場合は、このフィーチャーの依存関係として、これらの他のフィーチャーをマークできます。  これにより、依存元のフィーチャーがアクティブ化される前に、依存先のフィーチャーが確実にアクティブ化されます。  
  
## 依存関係の追加  
 ソリューション内の他のフィーチャーを依存関係として追加できます。  これにより、依存元のフィーチャーがインストールされる前に、必要なフィーチャーが確実にインストールされます。  
  
#### ソリューション内のフィーチャーの依存関係を追加するには  
  
1.  フィーチャー デザイナーを開き、**\[フィーチャー アクティブ化依存関係\]** ノードを展開し、**\[追加\]** ボタンをクリックします。  
  
2.  **\[フィーチャー アクティブ化依存関係の追加\]** ダイアログ ボックスで、**\[フィーチャーの依存関係をソリューションに追加する\]** のオプション ボタンを選択し、依存関係として追加する次へをクリックします **\[追加\]** をクリックして、フィーチャーのタイトルを指定します。  
  
     複数のタイトルを選択し、複数の機能を追加するには、Ctrl キーを押しながら。  
  
## カスタム依存関係の追加  
 SharePoint サーバーに既に配置されているフィーチャーを依存関係として追加できます。  これにより、依存元のフィーチャーがインストールされる前に、依存先のフィーチャーがすべてアクティブ化されていることが SharePoint のアクティブ化プロセスによって確認されます。  
  
#### 依存関係をフィーチャー ID で追加するには  
  
1.  フィーチャー デザイナーを開き、**\[フィーチャー アクティブ化依存関係\]** ノードを展開し、**\[追加\]** ボタンをクリックします。  
  
2.  **\[フィーチャー アクティブ化依存関係の追加\]** ダイアログ ボックスで、**\[カスタム依存関係を追加する\]** のオプション ボタンを選択します。  
  
3.  **\[フィーチャー ID\]** のテキスト ボックスに、アクティブ化の依存関係としてマークする入力し、**\[追加\]** をクリックして、フィーチャーの GUID を。  
  
## カスタム依存関係の編集  
 過去に追加したカスタム依存関係は編集することができます。  ただし、ソリューション内にある依存先のフィーチャーは削除できるだけであり、編集することはできません。  
  
#### ソリューション内のフィーチャーの依存関係を変更するには  
  
1.  フィーチャー デザイナーを開き、**\[フィーチャー アクティブ化依存関係\]** ノードを展開します。  
  
2.  編集するを選択し、**\[編集\]** ボタンをクリックします。機能の名前を指定します。  
  
3.  **\[カスタム フィーチャー アクティブ化依存関係の編集\]** ダイアログ ボックスのタイトルを変更すると、ID、または説明を提供し、**\[送信\]** ボタンをクリックします。  
  
## 依存関係の削除  
  
#### ソリューション内のフィーチャーの依存関係を削除するには  
  
1.  フィーチャー デザイナーで、**\[フィーチャー アクティブ化依存関係\]** ノードを選択し、削除するを選択して、次へを **\[削除\]** ボタンを展開します。機能の名前を指定します。  
  
## 参照  
 [SharePoint フィーチャーの作成](../sharepoint/creating-sharepoint-features.md)   
 [方法: SharePoint フィーチャーをカスタマイズする](../sharepoint/how-to-customize-a-sharepoint-feature.md)   
 [方法: SharePoint フィーチャーの項目を追加および削除する](../sharepoint/how-to-add-and-remove-items-to-sharepoint-features.md)  
  
  