---
title: "[ルール条件エディター] ダイアログ ボックス (レガシ) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI"
helpviewer_keywords: 
  - "[ルール条件] ダイアログ ボックス"
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
caps.latest.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# [ルール条件エディター] ダイアログ ボックス (レガシ)
このトピックでは、従来の [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]の **\[ルール条件エディター\]** ダイアログ ボックスの使用方法について説明します。[!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] または [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] を対象とする必要がある場合は、従来の[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]を使用します。  
  
 **\[ルール条件エディター\]** ダイアログ ボックスを使用することにより、宣言的ルール条件を作成および変更できます。これらのルール条件は、Windows Workflow Foundation の事前定義アクティビティにプロパティとして公開されています。  
  
-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)  
  
-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)  
  
-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)  
  
-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)  
  
-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)  
  
 **\[ルール条件エディタ\]** ダイアログ ボックスにアクセスするには、[\[条件の選択\] ダイアログ ボックス \(レガシ\)](../Topic/Select%20Condition%20Dialog%20Box%20\(Legacy\).md)を使用します。  
  
 **\[ルール条件エディタ\]** ダイアログ ボックスのユーザー インターフェイス \(UI\) 要素を次の表に示します。  
  
|UI 要素|説明|  
|-----------|--------|  
|**\[条件 :\]**|ルールの条件式を入力します。|  
|**\[OK\]**|これをクリックすると、ルール条件が保存されます。|  
  
## 条件式の入力  
 条件式は、テキストとして入力します。エディタに **this.** と入力すれば、IntelliSense 型のメニューを使って、ワークフローで使用されるフィールド、プロパティ、メソッドを参照できます。または、ワークフローのメンバ名を直接入力することもできます。条件には、AND、OR、NOT といった論理演算子を追加することもできます。述語も追加できます。述語は、バイナリ演算子と 2 つのオペランドから成ります。サポートされているバイナリ演算子は、**\=\=**、**\>**、**\<**、**\>\=** および **\<\=** です。サポートされているオペランドは、定数値、算術関数、スコープ付きパブリック メンバです。  
  
 比較の種類を指定することで、**null** や空文字列と比較できます。複合型を含む変数でメンバに対する呼び出しをネストすることができます \(たとえば `this.Address.State == "WA"`\)。  
  
 ルール条件エディタは、次の演算子をサポートします。  
  
-   関係演算子 : \=\=、\=、\!\=  
  
-   比較演算子 : \<、\<\=、\>、\>\=  
  
-   算術演算子 : \+、\-、\*、\/、MOD  
  
-   論理演算子 : AND、&&、OR、&#124;&#124;、NOT、\!  
  
-   ビット単位の演算子 : &、&#124;  
  
 式演算子の優先順位は、C\# 演算子の優先順位規則に従います。  
  
 ルール条件エディタは、次の数式をサポートします。  
  
 this.i \=\= 1D \(1.0 に解決\)  
  
 this.i \=\= 1E1 \(10.0 に解決\)  
  
 this.i \=\= 1L \(long として解決\)  
  
 this.i \=\= 1M \(decimal として解決\)  
  
 this.i \=\= 1F \(single として解決\)  
  
 this.i \=\= 1U \(unsigned int として解決\)  
  
 条件の詳細については、「[ワークフロー内での条件の使用](http://go.microsoft.com/fwlink?LinkID=65009)」を参照してください。  
  
## 参照  
 [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)   
 [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)   
 [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)   
 [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)   
 [\[条件の選択\] ダイアログ ボックス \(レガシ\)](../Topic/Select%20Condition%20Dialog%20Box%20\(Legacy\).md)   
 [ワークフロー内での条件の使用](http://go.microsoft.com/fwlink?LinkID=65009)   
 [従来の Designer for Windows Workflow Foundation UI ヘルプ](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)