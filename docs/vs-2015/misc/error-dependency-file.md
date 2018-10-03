---
title: 'エラー: 依存関係&#39;ファイル&#39;プロジェクトで&#39;プロジェクト&#39;依存関係と競合するために、実行ディレクトリにコピーできません&#39;ファイル&#39;|Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.tasklisterror.copy_version_conflict
ms.assetid: cd7de1eb-7d58-4e2c-9811-a7201f7817be
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: douge
ms.openlocfilehash: 6f571ec21094a28077f63bf86d4afe97af5429dd
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "47592518"
---
# <a name="error-the-dependency-39file39-in-project-39project39-cannot-be-copied-to-the-run-directory-because-it-would-conflict-with-dependency-39file39"></a>エラー: 依存関係&#39;ファイル&#39;プロジェクトで&#39;プロジェクト&#39;依存関係と競合するために、実行ディレクトリにコピーできません&#39;ファイル&#39;
参照間で競合が発生しています。アプリケーションが実行される bin ディレクトリに、ファイル名が同じ複数の依存関係がコピーされようとしています。 どの依存関係もプライマリ参照ではないため、実行ディレクトリは競合を解決できません。  
  
 このエラーが発生すると、ビルドが失敗します。  
  
 このタスク一覧の項目をダブルクリックすると、競合が発生しているプロジェクトの参照ノードが表示されます。  
  
 **このエラーを修正するには**  
  
-   アセンブリのいずれかをプロジェクトの直接参照にします。 この方法で考えられる欠点は、選択するアセンブリが、他のバージョンの参照アセンブリを要求するアセンブリと共に動作することが保証されない点です。  
  
     \- または -  
  
-   両方のアセンブリ コピーが厳密に命名され、グローバル アセンブリ キャッシュに存在することを確認します。 これにより、アセンブリを bin ディレクトリにコピーする必要がなくなります。  
  
## <a name="see-also"></a>関連項目  
 [プロジェクト内の参照の管理](../ide/managing-references-in-a-project.md)   
 [グローバル アセンブリ キャッシュ](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)   
 [厳密な名前付きアセンブリ](http://msdn.microsoft.com/library/d4a80263-f3e0-4d81-9b61-f0cbeae3797b)   
 [アセンブリのバージョン管理](http://msdn.microsoft.com/library/775ad4fb-914f-453c-98ef-ce1089b6f903)   
 [方法 : プロジェクトの依存関係を作成および削除する](../ide/how-to-create-and-remove-project-dependencies.md)