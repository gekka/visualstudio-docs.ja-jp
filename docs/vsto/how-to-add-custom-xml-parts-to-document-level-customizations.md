---
title: '方法: ドキュメント レベルのカスタマイズにカスタム XML 部分を追加します。'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document-level customizations [Office development in Visual Studio], custom XML parts
- Office documents [Office development in Visual Studio, custom XML parts
- Word [Office development in Visual Studio], custom XML parts
- Excel [Office development in Visual Studio], custom XML parts
- custom XML parts [Office development in Visual Studio], adding
- documents [Office development in Visual Studio], custom XML parts
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0472ad001dee595f1f8edb77d7a70f1eefb0c024
ms.sourcegitcommit: be938c7ecd756a11c9de3e6019a490d0e52b4190
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50744864"
---
# <a name="how-to-add-custom-xml-parts-to-document-level-customizations"></a>方法: ドキュメント レベルのカスタマイズにカスタム XML 部分を追加します。
  ドキュメント レベルのカスタマイズにカスタム XML 部分を作成すると、Microsoft Office Excel ブックまたは Microsoft Office Word 文書に XML データを格納できます。 詳細については、次を参照してください。[カスタム XML 部分の概要](../vsto/custom-xml-parts-overview.md)します。  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
> [!NOTE]  
>  Visual Studio では、Microsoft Office PowerPoint のドキュメント レベルのプロジェクトは提供していません。 VSTO アドインを使用して、PowerPoint プレゼンテーションにカスタム XML 部分を追加する方法の詳細については、次を参照してください。[方法: VSTO アドインを使用して、カスタム XML 部分をドキュメントに追加](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)します。  
  
### <a name="to-add-a-custom-xml-part-to-an-excel-workbook"></a>カスタム XML 部分を Excel ブックに追加するには  
  
1.  ブックの <xref:Microsoft.Office.Core.CustomXMLPart> コレクションに、新しい <xref:Microsoft.Office.Core.CustomXMLParts> オブジェクトを追加します。 <xref:Microsoft.Office.Core.CustomXMLPart> にはブックに格納する XML 文字列が含まれています。  
  
     [!code-csharp[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.cs#1)]
     [!code-vb[Trin_AddCustomXmlPartExcelDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartExcelDocLevel/ThisWorkbook.vb#1)]  
  
2.  Excel のドキュメント レベルのプロジェクト内の `ThisWorkbook` クラスに `AddCustomXmlPartToWorkbook` メソッドを追加します。  
  
3.  プロジェクトの他のコードからメソッドを呼び出します。 たとえば、ユーザーがブックを開いたときにカスタム XML 部分を作成するには、このメソッドを `ThisWorkbook_Startup` イベント ハンドラーから呼び出します。  
  
### <a name="to-add-a-custom-xml-part-to-a-word-document"></a>カスタム XML 部分を Word ドキュメントに追加するには  
  
1.  ドキュメントの <xref:Microsoft.Office.Core.CustomXMLPart> コレクションに、新しい <xref:Microsoft.Office.Core.CustomXMLParts> オブジェクトを追加します。 <xref:Microsoft.Office.Core.CustomXMLPart> にはドキュメントに格納する XML 文字列が含まれています。  
  
     [!code-vb[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/VisualBasic/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.vb#1)]
     [!code-csharp[Trin_AddCustomXmlPartWordDocLevel#1](../vsto/codesnippet/CSharp/Trin_AddCustomXmlPartWordDocLevel/ThisDocument.cs#1)]  
  
2.  Word のドキュメント レベルのプロジェクト内の `AddCustomXmlPartToDocument` クラスに `ThisDocument` メソッドを追加します。  
  
3.  プロジェクトの他のコードからメソッドを呼び出します。 たとえば、ユーザーが文書を開いたときにカスタム XML 部分を作成するには、このメソッドを `ThisDocument_Startup` イベント ハンドラーから呼び出します。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 わかりやすくするために、この例では、メソッドでローカル変数として定義されている XML 文字列を使用しています。 通常は、ファイルやデータベースなどの外部ソースから XML を取得する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [カスタム XML 部分の概要](../vsto/custom-xml-parts-overview.md)   
 [方法: VSTO アドインを使用して、カスタム XML 部分をドキュメントに追加](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md)  
  