---
title: "[セキュリティの詳細設定] ダイアログ ボックス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.err.debug_in_zone_no_hostproc"
  - "vs.err.debug_in_zone_no_hostproc:11310"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "[セキュリティの詳細設定] ダイアログ ボックス"
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# [セキュリティの詳細設定] ダイアログ ボックス
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

このダイアログボックスを使用すると、ゾーンでのデバッグに関連したセキュリティ設定を指定できます。  
  
 このダイアログ ボックスを表示するには、**ソリューション エクスプローラー**でプロジェクト ノードを選択し、**\[プロジェクト\]** メニューの **\[プロパティ\]** をクリックします。  **プロジェクト デザイナー**が表示されたら、**\[セキュリティ\]** タブをクリックします。  **\[セキュリティ\]** ページで、**\[ClickOnce セキュリティ設定を有効にする\]** をオンにし、**\[これは部分的に信頼するアプリケーションです\]** をクリックして、**\[詳細設定\]** をクリックします。  
  
## UIElement の一覧  
 **\[このアプリケーションを選択されたアクセス許可のセットでデバッグする\]**  
 このチェック ボックスをオンにすると、**\[セキュリティ\]** ページで選択したアクセス許可セットがデバッグ時に使用されます。  既定では、このチェック ボックスはオンになっています。  
  
 セキュリティ ゾーンでデバッグを有効にするには、このオプションと **\[Visual Studio ホスティング プロセスを有効にする\]** オプション \(**プロジェクト デザイナー**の **\[デバッグ\]** ページ\) を有効にする必要があります。  
  
 WPF Web ブラウザー アプリケーション プロジェクトでは、**\[このアプリケーションを選択されたアクセス許可のセットでデバッグする\]** オプションがオンになり、変更はできません。  
  
 **\[アプリケーション アクセスをその元のサイトに与える\]**  
 このチェック ボックスをオンにすると、アプリケーションは、公開先の Web サイトまたはサーバー共有にアクセスできます。  既定では、このチェック ボックスはオンになっています。  
  
 **\[このアプリケーションが次の URL からダウンロードされたと仮定してデバッグする\]**  
 **\[発行\]** ページで指定した **\[インストールの URL\]** に対応する Web サイトまたはサーバー共有にアプリケーションからアクセスできるようにする場合は、その URL をここに入力します。  このオプションは、**\[アプリケーション アクセスをその元のサイトに与える\]** チェック ボックスがオンの場合のみ使用できます。  
  
## 参照  
 [\[セキュリティ\] ページ \(プロジェクト デザイナー\)](../Topic/Security%20Page,%20Project%20Designer.md)