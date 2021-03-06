---
title: '方法: エディット コンティニュを使用 (c#) |Microsoft Docs'
ms.custom: ''
ms.date: 10/04/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 41e97f488344e3d34ce326a3d35880d94da4ad9a
ms.sourcegitcommit: c5e72875206b8c5737c29d5b1ec7b86eec747303
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2018
ms.locfileid: "49382806"
---
# <a name="how-to-use-edit-and-continue-c"></a>方法 : エディット コンティニュを使用する (C#)
エディット コンティニュと、作成し、停止し、デバッグ セッションを再起動しなくても、デバッグ中に中断モードでコードに変更を適用できます。  

エディット コンティニュC#中断モードでコードを変更しを使用してデバッグを続行するときに自動的に行われる**続行**、**手順**、または**次のステートメントの設定**、か、デバッガー ウィンドウで関数を評価します。  

詳細については、次を参照してください。[エディット コンティニュ (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)します。

>[!NOTE]
>エディット コンティニュは最適化された、サポートされていません、混在、または SQL Server 共通言語ランタイム (CLR) 統合コード。 サポートされていないその他のシナリオについては、次を参照してください。[コードの変更がサポートされています (C#および Visual Basic)](../debugger/supported-code-changes-csharp.md)します。 編集し、これらのシナリオのいずれかを続行しようとする場合は、エディット コンティニュがサポートされていないことを示すメッセージ ボックスが表示されます。  
  
**有効または、エディット コンティニュを無効にします。**  
   
1. デバッグ セッションの場合は、デバッグを停止 (**デバッグ** > **デバッグの停止**または**Shift**+**F5**).
   
1. **ツール** > **オプション**(または**デバッグ** > **オプション**) > **のデバッグ** > **全般**、オンまたはオフ、**編集を有効にして続行**チェック ボックスをオンします。  
  
設定は、開始、またはデバッグ セッションを再開するときに有効です。  

**エディット コンティニュを使用します。**  
   
1. 中断モードでは、デバッグ中に、ソース コードに変更を加えます。  
   
1. **デバッグ** メニューのをクリックして**続行**、**手順**、または**次のステートメントの設定**、か、デバッガー ウィンドウで関数を評価します。  
   
   新しいコンパイル済みコードでデバッグが続行します。 

エディット コンティニュでは、いくつかの種類のコード変更はサポートされていません。 詳細については、次を参照してください。[コードの変更がサポートされています (C#および Visual Basic)](../debugger/supported-code-changes-csharp.md)します。   
