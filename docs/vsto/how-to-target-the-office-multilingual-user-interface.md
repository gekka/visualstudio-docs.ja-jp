---
title: 'How to: Target the Office Multilingual User Interface | Microsoft Docs'
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
- globalization [Office development in Visual Studio], user interface targeting
- MUI [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], localization
- Multilingual User Interface [Office development in Visual Studio]
- localization [Office development in Visual Studio], user interface targeting
- Office applications [Office development in Visual Studio], globalization
ms.assetid: b1f03164-f0cf-42e3-942b-8cf90c242ffb
caps.latest.revision: 30
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: 424211704500cb93b37a78a799ddbe06872559b5
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>How to: Target the Office Multilingual User Interface
  The Multilingual User Interface (MUI) is a Microsoft Office feature that gives the end user the ability to change the language of the user interface (UI). For example, an end user working with an English UI can change the language of the UI to Spanish.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 If your application will be used by people who use multiple languages of Office, you can add code to automatically change the language of your UI strings to match the language being used by Office on the user's computer (if the user has the correct resources installed).  
  
### <a name="to-check-the-current-office-ui-setting"></a>To check the current Office UI setting  
  
1.  Use the <xref:System.Threading.Thread.CurrentUICulture%2A> property of the current thread. Set the language of your UI strings to match the language being used by the version of Office currently running on the user's computer.  
  
     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]  [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]  
  
## <a name="see-also"></a>See Also  
 [How to: Target Office Applications Through Primary Interop Assemblies](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Late Binding in Office Solutions](../vsto/late-binding-in-office-solutions.md)  
  
  