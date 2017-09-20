---
title: 'How to: Programmatically Send E-Mail | Microsoft Docs'
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
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
ms.assetid: 4fa0e1b5-2caf-4a11-8626-df643b23f5f0
caps.latest.revision: 18
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: f8cb1afe7e496514ce8ceae60f705bb801a3d3ec
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="how-to-programmatically-send-e-mail"></a>How to: Programmatically Send E-Mail  
  This example sends an e-mail message to contacts that have the domain name **example.com** in their e-mail addresses.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>Example  
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>Compiling the Code  
 This example requires:  
  
-   Contacts that have the domain name **example.com** in their e-mail addresses.  
  
## <a name="robust-programming"></a>Robust Programming  
 Do not remove the filter code that searches for the domain name **example.com**. Your solution will send e-mail messages to all of your contacts if you remove the filter.  
  
## <a name="see-also"></a>See Also  
 [Working with Mail Items](../vsto/working-with-mail-items.md)   
 [How to: Programmatically Create an E-Mail Item](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [How to: Programmatically Access Outlook Contacts](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [How to: Programmatically Perform Actions When an E-Mail Message Is Received](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  