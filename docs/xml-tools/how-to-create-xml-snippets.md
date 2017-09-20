---
title: "方法 : XML スニペットを作成する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8556dd7-1382-4af7-ba80-3e873c9416be
caps.latest.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 2
---
# 方法 : XML スニペットを作成する
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

XML エディターを使用して、新しい XML スニペットを作成することができます。エディターには、新しい XML スニペットを作成する際の定型スニペットである、"Snippet" という名前の XML スニペットが含まれています。  
  
## 新しい XML スニペットを作成するには  
 新しい XML コード スニペットを作成するには、新しい XML ファイルを作成し、\[スニペットの挿入\] 機能を使用します。  
  
1.  \[ファイル\] メニューの \[新規作成\] をポイントし、\[ファイル\] をクリックします。  
  
2.  \[XML ファイル\] をクリックし、\[開く\] をクリックします。  
  
3.  エディター ペイン内を右クリックして \[スニペットの挿入\] をクリックします。  
  
4.  一覧から \[スニペット\] を選択し、**Enter** キーを押します。  
  
5.  新しいスニペットに必要な変更を加えます。  
  
6.  \[ファイル\] メニューの \[XMLFile.xml の保存\] をクリックします。  
  
     \[名前を付けてファイルを保存\] ダイアログ ボックスが表示されます。  
  
7.  新しいスニペットの名前を入力し、\[ファイルの種類\] ドロップダウン ウィンドウの \[スニペット ファイル\] をクリックします。  
  
8.  \[保存先\] ボックスを使用してファイルの場所を My Documents\\Visual Studio 2005\\Code Snippets\\XML\\My XML Snippets フォルダーに変更し、\[保存\] をクリックします。  
  
## スニペットの説明  
 このセクションでは、定型スニペットの主な要素について説明します。XML スニペットで使用されるスキーマ要素の詳細については、「[コード スニペット スキーマ リファレンス](../ide/code-snippets-schema-reference.md)」を参照してください。  
  
### SnippetType 要素  
 エディターは、2 つのスニペット型をサポートしています。  
  
```  
<SnippetTypes>  
  <SnippetType>SurroundsWith</SnippetType>  
  <SnippetType>Expansion</SnippetType>  
</SnippetTypes>  
```  
  
 `Expansion` 型は、\[スニペットの挿入\] コマンドを呼び出すときにスニペットを呼び出すかどうかを決定します。`SurroundsWith` 型は、\[Surrounds With\] コマンドを呼び出すときにスニペットを呼び出すかどうかを決定します。  
  
### Code 要素  
 `Code` 要素は、スニペットが呼び出されたときに挿入される XML テキストを定義します。  
  
> [!NOTE]
>  XML スニペットのテキストは、`<![CDATA[...]]>` セクションで囲む必要があります。  
  
 定型スニペットによって作成される `Code` 要素を次に示します。  
  
```  
<Code Language="XML">  
  <![CDATA[<test>  
  <name>$name$</name>  
  $selected$ $end$</test>]]>  
</Code>  
```  
  
 この `Code` 要素には 3 つの変数が含まれています。  
  
-   $name$ はユーザー定義変数です。この変数によって、編集可能な値を持つ `name` 要素が作成されます。既定値は "name" です。ユーザー定義変数は、`Literal` 要素を使用して定義されます。  
  
-   $selected$ は定義済みの変数です。この変数は、スニペットを呼び出す前に XML エディターで選択されたテキストを表します。この変数の配置によって、選択されたテキストが、選択範囲を囲むコード スニペット内のどこに出現するかが決まります。  
  
-   $end$ は定義済みの変数です。**Enter** キーを押してコード スニペット フィールドの編集を終了すると、この変数によってキャレット \(^\) の移動先が決まります。  
  
 上記の `Code` 要素によって、次の XML テキストが挿入されます。  
  
```  
<test>  
  <name>name</name>  
</test>  
```  
  
 name 要素の値は、編集可能な領域としてマークされます。  
  
### Literal 要素  
 `Literal` 要素は、ファイルへの挿入後にカスタマイズすることができる置換テキストを識別するために使用されます。たとえば、リテラル文字列、数値、および一部の変数名はリテラルとして宣言できます。XML スニペット内には任意の数のリテラルを定義することができ、スニペット内では、それらを複数回参照することができます。既定値が "name" である $name$ 変数を 1 つ定義している `Literal` 要素の例を次に示します。  
  
```  
<Literal>  
  <ID>name</ID>  
  <Default>name</Default>  
</Literal  
```  
  
 リテラルは関数を参照することもできます。XML エディターには、**LookupPrefix** という名前の関数が用意されています。**LookupPrefix** 関数は、このスニペットの呼び出された XML ドキュメントの位置から指定された名前空間 URI を検索し、見つかった場合は、その名前空間に定義されている名前空間プレフィックスを、名前にコロン \(:\) を含めて返します。次は、**LookupPrefix** 関数を使用する `Literal` 要素の一例です。  
  
```  
<Literal Editable="false">  
   <ID>prefix</ID>  
   <Function>LookupPrefix("namespaceURI")</Function>  
</Literal>  
```  
  
 この後は、XML スニペット内の任意の場所で $prefix$ 変数を使用できます。  
  
## 参照  
 [XML スニペット](../xml-tools/xml-snippets.md)   
 [方法 : XML スニペットを使用する](../xml-tools/how-to-use-xml-snippets.md)   
 [方法 : XML スキーマから XML スニペットを生成する](../Topic/How%20to:%20Generate%20an%20XML%20Snippet%20From%20an%20XML%20Schema.md)