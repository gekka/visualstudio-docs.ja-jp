---
title: ダイアログ ボックスのあいまいさを解決するには |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.Disambig
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 130f580c997cb5bc0e522d0fef57969788481273
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
ms.locfileid: "31475481"
---
# <a name="resolve-ambiguity-dialog-box"></a>[あいまいさの解決] ダイアログ ボックス
[`Resolve Ambiguity`] ダイアログ ボックスが表示されるのは、表示する場所をデバッガーが選択できない場合です。 たとえば、C++ テンプレートを使用する場合は、単一の関数テンプレートから複数の関数を作成できます。 デバッガーがテンプレートのソースの場所で停止して、`Go To Disassembly` が選択されている場合、デバッガーには複数のオプションがあります。 テンプレートから作成された各関数は独自の逆アセンブリ コードを持っており、デバッガーはどのコードを表示するのかを認識していません。 [`Resolve Ambiguity`] ダイアログ ボックスでは、対応するすべての場所の一覧から目的の場所を選択できます。  
  
 `Choose the specific location`  
 コマンドに対応するすべての場所の一覧を表示します。  
  
 `Address`  
 各関数のメモリ アドレスを表示します。  
  
 `Function`  
 各関数の名前を表示します。  
  
 `Module`  
 関数のオブジェクト コードを含むモジュール (EXE または DLL) を表示します。  
  
## <a name="see-also"></a>関連項目  
 [デバッガー内の式](../debugger/expressions-in-the-debugger.md)