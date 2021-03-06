---
title: コマンド配置のガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
caps.latest.revision: 29
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1729d4b5e65e60246926c1a3fd25342b10545068
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51731005"
---
# <a name="command-placement-guidelines"></a>コマンド配置のガイドライン
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Visual Studio 統合開発環境 (IDE) でのコマンドを配置するためのベスト プラクティスは、コマンド セットのサイズによって異なります。 コマンドが定義されているし、.vsct ファイルの情報に従って配置します。  
  
## <a name="best-practices-for-all-command-sets"></a>すべてのコマンド セットのベスト プラクティス  
 コマンドのセットはすべて、次のガイドラインに従います。  
  
-   コマンドの構造体のグラフを事前に準備します。 コマンド、コンボ ボックス、コマンド グループ、および複数の場所で使用されるショートカット メニューを特定します。  
  
-   同じグループ内に表示されるコマンドに関連付ける必要があります。  
  
-   1 つのコマンドを含むグループを利用できます。  
  
-   パッケージは、多くのコマンドを既存の Visual Studio のメニューに追加しないでください。 代わりに、メニューまたはサブメニューを新しいコマンドをホストするを作成する必要があります。  
  
-   配置すると、コマンド、名前のコマンドは、既存のメニューで目的がはっきりとはしない既存のコマンドで混乱するようにします。  
  
## <a name="best-practices-for-small-command-sets"></a>小規模なコマンド セットのベスト プラクティス  
 いくつかのコマンドを含む VSPackage を開発している場合は、これらのガイドラインに従っても。  
  
-   可能であればを使用して、[親要素](../../extensibility/parent-element.md)の適切なグループに配置するコマンド、コンボ ボックス、グループ、または子メニュー。  
  
-   VSPackage によって表示されるメニューには、これらのグループを割り当てます。  
  
-   子メニューまたはコマンドの親である必要があります、[グループ要素](../../extensibility/group-element.md)します。 コマンドおよび子メニュー グループに割り当てるし、親メニューに、グループを割り当てます。  
  
-   他のグループにコマンドを配置するには追加することで、 [CommandPlacements 要素](../../extensibility/commandplacements-element.md)セクションの後、コマンドの定義にし、追加する、 `CommandPlacements Element` 、 [CommandPlacement 要素](../../extensibility/commandplacement-element.md)ごと追加のグループ。  
  
## <a name="best-practices-for-large-command-sets"></a>大量のコマンド セットのベスト プラクティス  
 VSPackage が複数のコンテキストで表示される多くのコマンドである場合は、次のガイドラインを次も実行します。  
  
-   メニューのグループ、および自己の親のコマンドを作成します。 つまり、割り当てないでください、`Parent Element`アイテムの定義でします。  
  
-   使用`CommandPlacement Element`内のエントリ、`CommandPlacements Element`セクション グループ、親メニューにメニューのグループ、およびコマンドを配置します。  
  
-   `CommandPlacements`セクションで、指定されたメニューを設定するエントリまたはグループは互いに隣接する必要があります。 読みやすくなり、この、`Priority`ランキングを容易に判断します。  
  
## <a name="see-also"></a>関連項目  
 [Vspackage がユーザー インターフェイス要素を追加する方法](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Visual Studio Command Table (.Vsct) ファイル](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

