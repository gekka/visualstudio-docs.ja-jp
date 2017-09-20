---
title: Source Server Security Alert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
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
ms.translationtype: HT
ms.sourcegitcommit: 9e6c28d42bec272c6fd6107b4baf0109ff29197e
ms.openlocfilehash: 58dede96d21933a5f185face9f4213da13777942
ms.contentlocale: ja-jp
ms.lasthandoff: 08/22/2017

---
# <a name="source-server-security-alert"></a>Source Server Security Alert
When using Source Server, only use symbol files that are from a known and trusted location.  
  
 This warning appears when you enable Source Server support. Source Server commands are embedded in debug symbol files (***.pdb** files). Make sure you know where your PDB files come from.  
  
> [!IMPORTANT]
>  The following potential security threats must be taken into account when using Source Server: Arbitrary commands can be embedded in the application's PDB file, so make sure you put only the ones you want to execute in the srcsrv.ini file. Any attempt to execute a command not in the srcsvr.ini file will cause a confirmation dialog box to appear. For more information, see [Security Warning: Debugger Must Execute Untrusted Command](../debugger/security-warning-debugger-must-execute-untrusted-command.md).No validation is done on command parameters, so be careful with trusted commands. For example, if you trusted cmd.exe, a malicious user might specify parameters that would make the command dangerous.  
  
## <a name="see-also"></a>See Also  
 [Specify Symbol (.pdb) and Source Files](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Debugger Security](../debugger/debugger-security.md)   
 [Source Server](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)