---
title: QuickWatch コマンド | Microsoft Docs
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
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: afe27d567601e43b10323f9dcc3417bcf15e9298
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269413"
---
# <a name="quick-watch-command"></a>QuickWatch コマンド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
[式] フィールドで選択または指定したテキストが表示されます、 [[クイック ウォッチ] ダイアログ ボックス](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)します。 このダイアログ ボックスを利用し、デバッガーが認識する変数または式の現在値やレジスタのコンテンツの現在値を計算できます。 さらに、非定数の変数の値やレジストリのコンテンツの値を変更できます。  
  
## <a name="syntax"></a>構文  
  
```  
Debug.QuickWatchq [text]  
```  
  
## <a name="arguments"></a>引数  
 `text`  
 任意。 **[クイック ウォッチ]** ダイアログ ボックスに追加するテキスト。  
  
## <a name="remarks"></a>Remarks  
 `text` を省略した場合、カーソルで現在選択されているテキストや単語がウォッチ ウィンドウに追加されます。  
  
## <a name="example"></a>例  
  
```  
>Debug.QuickWatch  
```  
  
## <a name="see-also"></a>関連項目  
 [方法: [クイック ウォッチ] ダイアログ ボックスを使用します。](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)   
 [コマンド ウィンドウ](../../ide/reference/command-window.md)   
 [[検索/コマンド] ボックス](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



