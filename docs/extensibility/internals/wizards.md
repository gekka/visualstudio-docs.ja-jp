---
title: ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], providing wizard support
ms.assetid: 59d9a77f-ee80-474b-a14f-90f477ab717b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 03cee9de14da76ea65882d906acb3af88e72e999
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138715"
---
# <a name="wizards"></a>ウィザード
追加するウィザードを作成したら、通常、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]他のユーザーが使用できるように開発環境 (IDE) を統合します。 追加のウィザードが表示されます、**新しいプロジェクトの追加**または**新しい項目の追加** ダイアログ ボックス。 表示する、**新しいプロジェクトの追加**または**新しい項目の追加** ダイアログ ボックスで開いているソリューションを右クリックして**ソリューション エクスプ ローラー**、 をポイント**追加**とをクリックして**新しいプロジェクト**または**新しい項目の**します。  
  
 ウィザードを実装することができます[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]ユーザーができるようにを開いたときに使用できる値のツリー ビューから選択して、**新しいプロジェクトの追加** ダイアログ ボックスまたは**新しい項目の追加**ダイアログ ボックスで、右クリックすると、または内の項目**ソリューション エクスプ ローラー**です。  
  
 ウィザードで、ites の新しいプロジェクトの名前をローカライズするオプションを指定することができ、ウィザードを選択するときにユーザーに表示されるアイコンを決定することができます。 他の利用可能な項目; 基準とした新しい項目が表示される順序を制御することもできます。項目は、アルファベット順に整理することはありません。  
  
 ウィザードを開いたときに、ウィザードに渡されるカスタムのパラメーターに基づいて異なる方法で、開始を指定することもできます。  
  
 このセクションのトピックで説明が発生するために実装ファイル、 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **新しいプロジェクトの追加**と**新しい項目の追加**を利用できるウィザードおよびテンプレートの中で、ウィザードを一覧表示するダイアログ ボックスIDE で正常に動作するウィザードが満たす必要がある要件です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [テンプレート ディレクトリの説明 (.Vsdir) ファイル](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)  
 ディレクトリの記述ファイル テンプレートの概要を説明し、フォルダー、ウィザードの .vsz ファイル、およびダイアログ ボックスで、プロジェクトに関連付けられているテンプレート ファイルを表示するための IDE で正常に実行する方法について説明します。  
  
 [ウィザード (.Vsz) ファイル](../../extensibility/internals/wizard-dot-vsz-file.md)  
 IDE がウィザードを起動する方法について説明し、.vsz ファイルの 3 つの部分を一覧表示します。  
  
 [ウィザード インターフェイス (IDTWizard)](../../extensibility/internals/wizard-interface-idtwizard.md)  
 について説明します、`IDTWizard`インターフェイス ウィザードは、IDE で作業するために実装する必要があります。  
  
 [コンテキスト パラメーター](../../extensibility/internals/context-parameters.md)  
 ウィザードの実装方法と、IDE が実装するコンテキスト パラメーターを渡すときの動作について説明します。  
  
 [カスタム パラメーター](../../extensibility/internals/custom-parameters.md)  
 カスタム パラメーターを使用して、ウィザードを起動した後、ウィザードの操作を制御する方法について説明します。  
  
## <a name="related-sections"></a>関連項目  
 [プロジェクト タイプ](../../extensibility/internals/project-types.md)  
 新しいプロジェクトの種類を設計する方法に関する情報を提供するその他のトピックへのリンクを提供します。  
  
 [プロジェクトの拡張](../../extensibility/extending-projects.md)  
 使用する方法について説明[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]プロジェクトおよびソリューションのコード ファイルとリソース ファイル、およびソース管理を実装する方法を整理します。