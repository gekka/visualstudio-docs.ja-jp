---
title: '方法: プログラムによってワークシートをコピーします。'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, copying
- Excel [Office development in Visual Studio], copying worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: eddecb7bdb087797bc3f9f4abf4841ab4cdf97b5
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256540"
---
# <a name="how-to-programmatically-copy-worksheets"></a>方法: プログラムによってワークシートをコピーします。
  ワークシートのコピーを作成し、ブック内の既存のワークシートの前または後に挿入できます。 ワークシートの挿入先を指定しない場合は、新しいブックが作成され、そこに新しいワークシートが格納されます。  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
> [!NOTE]  
>  プログラミングによってワークシートをコピーした場合でも、エンド ユーザーが手動でワークシートをコピーした場合でも、新しいワークシートの背後にはコードが存在せず、新しいワークシート上のコントロールは機能しません。 これは、新しくコピーしたワークシートが <xref:Microsoft.Office.Interop.Excel.Worksheet> オブジェクトであって、<xref:Microsoft.Office.Tools.Excel.Worksheet> ホスト項目ではないためです。 Windows フォーム コントロールおよびホスト コントロールは、ホスト項目にのみ追加できます。 詳細については、次を参照してください。[ホスト項目とホスト コントロールのプログラム上の制限事項](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)します。  
  
## <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-document-level-customization"></a>ドキュメント レベルのカスタマイズで、コピーしたワークシートをブックに追加するには  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> メソッドを使用して、作業中のブック内の 1 番目のワークシートをコピーし、そのコピーを 3 番目のシートの後に挿入します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#16)]
     [!code-vb[Trin_VstcoreExcelAutomation#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#16)]  
  
## <a name="to-add-a-copied-worksheet-to-a-workbook-in-a-vsto-add-in"></a>VSTO アドインで、コピーしたワークシートをブックに追加するには  
  
1.  <xref:Microsoft.Office.Interop.Excel.Worksheets.Copy%2A> メソッドを使用して、作業中のブック内の 1 番目のワークシートをコピーし、そのコピーを 3 番目のシートの後に挿入します。  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#12)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#12](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#12)]  
  
## <a name="see-also"></a>関連項目  
 [ワークシートを操作します。](../vsto/working-with-worksheets.md)   
 [ホスト項目とホスト コントロールの概要](../vsto/host-items-and-host-controls-overview.md)   
 [方法: プログラムによってブックを新しいワークシートを追加](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [方法: プログラムによってブックからワークシートを削除](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)   
 [方法: プログラムによってワークシートを選択します。](../vsto/how-to-programmatically-select-worksheets.md)   
 [拡張オブジェクトを使用して Excel を自動化します。](../vsto/automating-excel-by-using-extended-objects.md)   
 [Office プロジェクト内のオブジェクトへのグローバル アクセス](../vsto/global-access-to-objects-in-office-projects.md)   
 [ホスト項目とホスト コントロールのプログラム上の制限事項](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)  
  
  