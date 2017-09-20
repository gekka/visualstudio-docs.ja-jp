---
title: 'How to: Programmatically Set Search Options in Word | Microsoft Docs'
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
- settings, Word search options
- documents [Office development in Visual Studio], search options
- Word, searching options
- searching, Word options
ms.assetid: 4412b4e8-2868-4afb-a593-983603ef9b02
caps.latest.revision: 46
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: 6ba2389591a19d657fb2d533ac7be1d0b15d0c19
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="how-to-programmatically-set-search-options-in-word"></a>How to: Programmatically Set Search Options in Word
  There are two ways to set search options for selections in Microsoft Office Word documents:  
  
-   Set individual properties of a <xref:Microsoft.Office.Interop.Word.Find> object.  
  
-   Use arguments of the <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> method of a <xref:Microsoft.Office.Interop.Word.Find> object.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="using-properties-of-a-find-object"></a>Using Properties of a Find Object  
 The following code sets properties of a <xref:Microsoft.Office.Interop.Word.Find> object to search for text within the current selection. Notice that the search criteria, such as searching forward, wrapping, and text to search for, are properties of the <xref:Microsoft.Office.Interop.Word.Find> object.  
  
 Setting each of the properties of the <xref:Microsoft.Office.Interop.Word.Find> object is not useful when you write C# code because you must specify the same properties as parameters in the <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> method. Therefore this example contains only Visual Basic code.  
  
#### <a name="to-set-search-options-using-a-find-object"></a>To set search options using a Find object  
  
1.  Set the properties of a <xref:Microsoft.Office.Interop.Word.Find> object to search forward through a selection for the text **find me**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#76)]  
  
## <a name="using-execute-method-arguments"></a>Using Execute Method Arguments  
 The following code uses the <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> method of a <xref:Microsoft.Office.Interop.Word.Find> object to search for text within the current selection. Notice that the search criteria, such as searching forward, wrapping, and text to search for, are passed as parameters of the <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> method.  
  
#### <a name="to-set-search-options-using-execute-method-arguments"></a>To set search options using Execute method arguments  
  
1.  Pass search criteria as parameters of the <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> method to search forward through a selection for the text **find me**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#77)]  [!code-csharp[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#77)]  
  
## <a name="see-also"></a>See Also  
 [How to: Programmatically Search for and Replace Text  in Documents](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [How to: Programmatically Loop Through Found Items in Documents](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [How to: Programmatically Restore Selections After Searches](../vsto/how-to-programmatically-restore-selections-after-searches.md)  
  
  