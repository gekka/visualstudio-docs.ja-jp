---
title: Open File コマンド | Microsoft Docs
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
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0b519d8defcdc4b43dd7ca84552536ca655bb348
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49247937"
---
# <a name="open-file-command"></a>OpenFile コマンド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
既存のファイルを開き、エディターを指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
File.OpenFile filename [/e:editorname]  
```  
  
## <a name="arguments"></a>引数  
 `filename`  
 必須。 開くファイルの完全パスまたは部分パス、およびファイル名。 パスに空白が含まれる場合は、引用符で囲む必要があります。  
  
## <a name="switches"></a>スイッチ  
 /e:`editorname`  
 任意。 ファイルを開くために使用するエディターの名前です。 引数は指定されていても、エディター名がない場合、**[プログラムから開く]** ダイアログ ボックスが表示されます。  
  
 /e:`editorname` 引数の構文では、[ファイルを開くアプリケーションの選択] ダイアログ ボックスで表示されるようにエディター名を入力し、引用符で囲みます。  
  
 たとえば、ソース コード エディターでファイルを開くには、/e:`editorname` 引数に対して次のように入力します。  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Remarks  
 パスを入力する場合、オート コンプリートによって正しいパス名とファイル名が検索されます。  
  
## <a name="example"></a>例  
 次の例では、スタイル ファイル "Test1.css" をソース コード エディターで開きます。  
  
```  
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)   
 [コマンド ウィンドウ](../../ide/reference/command-window.md)   
 [イミディエイト ウィンドウ](../../ide/reference/immediate-window.md)   
 [[検索/コマンド] ボックス](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



