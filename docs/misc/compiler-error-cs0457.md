---
title: "コンパイラ エラー CS0457 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0457"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0457"
ms.assetid: 5d5cf762-c817-4468-9455-59e966b8c140
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# コンパイラ エラー CS0457
'type name 1' から 'type name 2' に変換する際のユーザー定義変換 'Conversion method name 1' および 'Conversion method name 2' があいまいです  
  
 適用できる変換メソッドが 2 つあり、コンパイラはどちらを使用すべきか判断できません。  
  
 このエラーを引き起こす可能性のある 1 つのシナリオは次のとおりです。  
  
-   A と B に関連がない場所でクラス A をクラス B に変換しようとします。  
  
-   A は A0 から派生したもので、A0 から B に変換するメソッドが存在します。  
  
-   B はサブクラス B1 を持っており、A から B1 に変換するメソッドが存在します。  
  
 最初の変換は最適な変換先の型を提供し、2 番目の変換は最適なソースの種類を提供するため、コンパイラは 2 つの変換メソッドを同等と判断します。 コンパイラがメソッドを選択できないため、このエラーが生成されます。 解決するには、A から B に変換する新しいメソッドを明示的に記述します。  
  
 このエラーが発生するもう 1 つのシナリオは、A から B に変換するメソッドが 2 つ存在する場合です。解決するには、明示的なキャストを使用して、どちらの変換を使用すべきか指定します。  
  
## 使用例  
 次の例では CS0457 が生成されます。  
  
```  
// CS0457.cs using System; public class A { } public class G0 {  } public class G1<R> : G0 {  } public class H0 { public static implicit operator G0(H0 h) { return new G0(); } } public class H1<R> : H0 { public static implicit operator G1<R>(H1<R> h) { return new G1<R>(); } } public class Test { public static void F0(G0 g) {  } public static void Main() { H1<A> h1a = new H1<A>(); F0(h1a);   // CS0457 } }  
```