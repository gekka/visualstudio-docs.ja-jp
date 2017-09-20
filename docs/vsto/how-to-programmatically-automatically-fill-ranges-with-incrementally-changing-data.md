---
title: 'How to: Programmatically Automatically Fill Ranges with Incrementally Changing Data | Microsoft Docs'
ms.custom: 
ms.date: 02/02/2017
ms.prod: visual-studio-dev14
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
ms.assetid: 27639d55-8ab5-483c-8907-2ea50dfd2188
caps.latest.revision: 40
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: a534bae8cb3025c2d4806ad151e0f4a653b891ca
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>How to: Programmatically Automatically Fill Ranges with Incrementally Changing Data
  The <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> method of the <xref:Microsoft.Office.Interop.Excel.Range> object enables you to fill a range in a worksheet with values automatically. Most often, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> method is used to store incrementally increasing or decreasing values in a range. You can specify the behavior by supplying an optional constant from the <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> enumeration.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 You must specify two ranges when using <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:  
  
-   The range that calls the <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> method, which specifies the starting point of the fill and contains an initial value.  
  
-   The range that you want to fill, passed as a parameter to the <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> method. This destination range must include the range that contains the initial value.  
  
    > [!NOTE]  
    >  You cannot pass a <xref:Microsoft.Office.Tools.Excel.NamedRange> control in place of the <xref:Microsoft.Office.Interop.Excel.Range>. For more information, see [Programmatic Limitations of Host Items and Host Controls](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
## <a name="example"></a>Example  
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)] [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]  
  
## <a name="compiling-the-code"></a>Compiling the Code  
 The first cell of the range that you want to fill must contain an initial value.  
  
 The example requires that you fill three regions:  
  
-   Column B is to include five weekdays. For the initial value, type **Monday** in cell B1.  
  
-   Column C is to include five months. For the initial value, type **January** in cell C1.  
  
-   Column D is to include a series of numbers, incrementing by two for each row. For the initial values, type **4** in cell D1 and **6** in cell D2.  
  
## <a name="see-also"></a>See Also  
 [Working with Ranges](../vsto/working-with-ranges.md)   
 [How to: Programmatically Refer to Worksheet Ranges in Code](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [How to: Programmatically Apply Styles to Ranges in Workbooks](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [How to: Programmatically Run Excel Calculations](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)   
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [Optional Parameters in Office Solutions](../vsto/optional-parameters-in-office-solutions.md)  
  
  