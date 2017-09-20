---
title: "XML ドキュメントの検証 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: abb353bd-6c4a-4978-b03b-a8c245bbfb55
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# XML ドキュメントの検証
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

XML エディターは、ユーザーが入力するときに XML 1.0 の構文をチェックし、データの検証も実行します。エディターは、ドキュメント型定義 \(DTD\) やスキーマを使用して検証を行うことができます。XML 1.0 の整形式のエラーは、赤色の波下線で強調表示されます。青色の波下線は、DTD またはスキーマの検証に基づいたセマンティック エラーを示します。エラーの一覧には、それぞれのエラーに関連するエントリが示されます。マウスを波下線の上に置くことで、エラー メッセージを表示させることもできます。  
  
 検証で使用されるスキーマの検索は、コンパイル済みのスキーマの `targetNamespace` と、要素の xmlns 宣言とを照合して行われます。コンパイル済みのスキーマが読み込まれる場所を、優先度の高い順に次に示します。  
  
-   ドキュメントのプロパティ ウィンドウの \[Schemas \(スキーマ\)\] フィールドで名前が指定されているファイル。  
  
-   インラインのスキーマまたは DTD。  
  
-   外部 DTD または `xsd:schemaLocation` および `xsd:noNamespaceSchemaLocation` 属性。  
  
-   "x\-schema" XDR スキーマ名前空間 URI。  
  
 スキーマに空でない対象名前空間がある場合は、次に示す場所でスキーマが検索されることもあります。  
  
-   スキーマを含む他のエディター ウィンドウ。  
  
-   現在のソリューション内にあるスキーマ。  
  
-   スキーマ キャッシュ ディレクトリ内にあるスキーマ。  
  
## XSLT ファイル  
 XSLT ファイルの編集時には、スキーマ キャッシュ内に置かれている xslt.xsd ファイルが検証に使用されます。検証エラーは、青色の波下線で表示されます。XSLT コンパイラによるエラーは、赤色の波下線で示されます。  
  
## XML スキーマ \(XSD\) ファイル  
 XML スキーマ ファイルの編集時には、スキーマ キャッシュ内に置かれている xsdschema.xsd ファイルが検証に使用されます。検証エラーは、青色の波下線で表示されます。コンパイル エラーも赤色の波下線で示されます。  
  
## 参照  
 [XML エディター](../xml-tools/xml-editor.md)