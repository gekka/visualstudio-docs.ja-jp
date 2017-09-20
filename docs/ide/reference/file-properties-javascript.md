---
title: "ファイルのプロパティ、JavaScript | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- javascript.project.property.expandedsdknode.fileversion
- javascript.project.property.expandedsdknode.uri
- javascript.project.property.expandedsdknode.filename
- javascript.project.property.reference.description
- javascript.project.property.reference.specificversion
- javascript.project.property.reference.identity
- javascript.project.property.fullpath
- javascript.project.property.packageaction
- javascript.project.property.reference.package
- javascript.project.property.copytooutputdirectory
- javascript.project.property.expandedsdknode.sdkpath
- javascript.project.property.reference.filetype
- javascript.project.property.reference.culture
- javascript.project.property.filename
- javascript.project.property.reference.resolvedpath
- javascript.project.property.reference.version
ms.assetid: 085913b8-a97b-45f7-85fa-bbb0902f3ee9
caps.latest.revision: 7
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d2f4eba36e9069a35cf279ccf1c78f72a51d77a1
ms.openlocfilehash: 6c2b3c577685fcb09cd9e9c7eeee955b75e76e27
ms.contentlocale: ja-jp
ms.lasthandoff: 06/23/2017

---
# <a name="file-properties-javascript"></a>ファイルのプロパティ、JavaScript
ファイルのプロパティを使用して、プロジェクト システムがファイルに対して実行するアクションを指定できます。 たとえば、ファイルがリソース ファイルとしてパッケージに追加するかどうかを示すには、ファイル プロパティを設定できます。  

 ソリューション エクスプローラーでファイルを選択し、[プロパティ] ウィンドウでそのプロパティを調べることができます。 JavaScript ファイルは、**[出力ディレクトリにコピー]**、**[パッケージ アクション]**、**[ファイル名]**、**[ファイル パス]** という 4 種類のプロパティがあります。  

## <a name="file-properties"></a>ファイルのプロパティ  
 このセクションでは、JavaScript ファイルに共通のプロパティについて説明します。  

### <a name="copy-to-output-directory-property"></a>[出力ディレクトリにコピー] プロパティ  
 このプロパティでは、選択したソース ファイルを出力ディレクトリにコピーする際の条件を指定します。 ファイルを出力ディレクトリにコピーしない場合は **[コピーしない]** を選択します。 ファイルを常に出力ディレクトリにコピーする場合は **[常にコピーする]** を選択します。 出力ディレクトリに既に存在する同じ名前のファイルよりも新しいときにのみファイルをコピーする場合は、**[新しい場合はコピーする]** を選択します。  

### <a name="package-action"></a>パッケージ アクション  
 **[パッケージ アクション]** のプロパティは、ビルドが実行されたときに Visual Studio がファイルの処理方法を示します。 **[パッケージ アクション]** には次のいずれかの値が使用されます。  

-   **なし** - ファイルはパッケージ マニフェストに含まれません。 たとえば、Readme ファイルなどのドキュメントを含むテキスト ファイルです。  

-   **コンテンツ** - ファイルはパッケージ マニフェストに含まれます。 たとえば、.htm、.js、.css、image、audio、または video ファイルでは、この設定が既定値です。  

-   **マニフェスト** - ファイルはパッケージ マニフェストに含まれません。 このファイルは、パッケージ マニフェストの生成時に入力に使用されます。 package.appxmanifest ファイルでは、この設定が既定値です。  

-   **リソース** - ファイルはパッケージ マニフェストに含まれません。 ファイルの内容のインデックスはパッケージ リソース インデックス (PRI) に保存され、パッケージ マニフェストに含まれます。 通常、リソース ファイルに使用されます。  

 **[パッケージ アクション]** の既定値は、ソリューションに追加するファイルの拡張子によって変わります。  

### <a name="file-name-property"></a>[ファイル名] プロパティ  
 読み取り専用の値としてファイル名が表示されます。 ファイルの名前を変更するには、ソリューション エクスプローラーで右クリックし、**[名前の変更]** を選択します。  

### <a name="full-path-property"></a>[完全パス] プロパティ  
 読み取り専用の値としてファイルの完全パスを表示します。 ファイルのパスを変更するには、ソリューション エクスプローラーでファイルをドラッグ アンド ドロップすることができます。  

## <a name="reference-file-properties"></a>参照ファイルのプロパティ  
 ここでは、[!INCLUDE[win8_app_js](../../ide/reference/includes/win8_app_js_md.md)] から参照されるファイルに一般的なプロパティについて説明します。 ソリューション エクスプローラーで .winmd ファイル、SDK リファレンス、プロジェクト間参照、またはアセンブリ参照などの参照を選択すると、ファイルの種類によっては [プロパティ] ウィンドウに他のプロパティが表示されることがあります。  

### <a name="culture"></a>カルチャ  
 参照に関連付けられている言語が表示されます。  

### <a name="file-type"></a>ファイルの種類  
 参照のファイルの種類が表示されます。  

### <a name="file-version"></a>ファイルのバージョン  
 参照のファイル バージョンが表示されます。  

### <a name="identity"></a>ID  
 プロジェクトに使用されている参照の ID が表示されます。これはプロジェクト ファイルに保存されています。  

### <a name="package"></a>Package  
 参照に関連付けられているパッケージ マニフェストの名前が表示されます。  

### <a name="resolved-path"></a>解決されたパス  
 プロジェクトで使用されている参照のパスが表示されます。  

### <a name="sdk-path"></a>SDK のパス  
 参照される SDK ファイルのパスが表示されます。  

### <a name="uri"></a>URI  
 ソース ファイルとしてファイルに含めるために、プロジェクトの HTML または JavaScript ファイルに含める必要がある URI が表示されます。  

### <a name="version"></a>バージョン  
 参照のバージョンが表示されます。  

## <a name="see-also"></a>関連項目  
 [プロジェクトおよびソリューションのプロパティの管理](../../ide/managing-project-and-solution-properties.md)
