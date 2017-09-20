---
title: 'Error: Kerberos Authentication Failed | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: c18053f9-9074-4bc3-a8bf-13e4acbea921
caps.latest.revision: 7
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
ms.openlocfilehash: a118e8fa105902ce655aa91038c968dfe5a40d7c
ms.contentlocale: ja-jp
ms.lasthandoff: 08/22/2017

---
# <a name="error-kerberos-authentication-failed"></a>Error: Kerberos Authentication Failed
When you try to do remote debugging, you might get the following error message:  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos authentication failed.  
```  
  
 This error occurs when the Visual Studio Remote Debugging Monitor is running under the Local System or Network Service account. Under one of these accounts, the remote debugger must establish a Kerberos authentication connection to communicate back to the Visual Studio debugger host computer.  
  
 Kerberos authentication is not available under these conditions:  
  
-   Either the target computer or the debugger host computer is on a workgroup, instead of a domain  
  
     \- or -  
  
-   Kerberos has been disabled on the domain controller.  
  
 If Kerberos authentication is not available, change the account that is used to run the Visual Studio Remote Debugging Monitor. For the procedure, see [Error: The Visual Studio Remote Debugger service on the target computer cannot connect back to this computer](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).  
  
 If both computers are connected to the same domain and you still get this message, verify that DNS on the target computer is correctly resolving the name of the debugger host computer. See the following procedure.  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>To verify that DNS on the target computer is correctly resolving the debugger host computer name  
  
1.  On the target computer, open the **Start** menu, point to **Accessories** and then click **Command Prompt**.  
  
2.  In the **Command Prompt** window, type:  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3.  The first line of the `ping` response shows the full computer name and IP address returned by DNS for the specified computer.  
  
4.  On the debugger host computer, open a **Command Prompt** window and run `ipconfig`.  
  
5.  Compare the IP address values.  
  
## <a name="see-also"></a>See Also  
 [Remote Debugging Errors and Troubleshooting](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Remote Debugging](../debugger/remote-debugging.md)