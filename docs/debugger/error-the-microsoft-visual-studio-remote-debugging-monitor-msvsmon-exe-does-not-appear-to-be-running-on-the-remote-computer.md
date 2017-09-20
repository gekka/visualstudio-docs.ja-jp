---
title: 'Error: The Microsoft Visual Studio Remote Debugging Monitor (MSVSMON.EXE) does not appear to be running on the remote computer. | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.error.server_machine_no_default
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 86db9931-50e3-4095-b161-802ed8ef39c9
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 9e6c28d42bec272c6fd6107b4baf0109ff29197e
ms.openlocfilehash: 17c436f1fc74d2b06eb98b0bbfb71634563fe558
ms.contentlocale: ja-jp
ms.lasthandoff: 08/22/2017

---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-msvsmonexe-does-not-appear-to-be-running-on-the-remote-computer"></a>Error: The Microsoft Visual Studio Remote Debugging Monitor (MSVSMON.EXE) does not appear to be running on the remote computer.
This error message means that Visual Studio could not find the correct instance of the Visual Studio Remote Debugging Monitor on the remote computer. The Visual Studio Remote Debugging Monitor must be installed for remote debugging to work. For information about downloading and setting up the remote debugger, see [Remote Debugging](../debugger/remote-debugging.md).  
  
> [!IMPORTANT]
>  If you believe you have received this message because of a product bug, please [report this issue to Visual Studio](../ide/how-to-report-a-problem-with-visual-studio-2017.md). If you need more help, see [Talk to Us](../ide/talk-to-us.md) for ways to contact Microsoft.  
  
## <a name="i-got-this-message-while-i-was-debugging-in-visual-studio-2010-or-earlier"></a>I got this message while I was debugging in Visual Studio 2010 or earlier  
 If the version of Visual Studio that you are using is Visual Studio 2010 or earlier, you might also receive this error if file and printer sharing is not enabled. To find out more about this issue, please refer to the Visual Studio 2010 version of this documentation: [Error: The Microsoft Visual Studio Remote Debugging Monitor (MSVSMON.EXE) does not appear to be running on the remote computer. - Visual Studio 2010](https://msdn.microsoft.com/en-us/library/ms164726\(v=vs.100\).aspx)  
  
## <a name="i-got-this-message-while-i-was-debugging-locally"></a>I got this message while I was debugging locally  
 If you are getting this message while you are debugging locally, your anti-virus software or a third-party firewall may be to blame. Visual Studio is a 32-bit application, so it uses the 64-bit version of the remote debugger to debug 64-bit applications. The two processes communicate using the local network within the local computer. No traffic leaves the computer, but it is possible that third party security software may block the communication.  
  
 The following sections list some other reasons why you might have gotten this message, and what you can do to fix the issue.  
  
## <a name="the-remote-machine-is-not-reachable"></a>The remote machine is not reachable  
 Try to [ping](https://technet.microsoft.com/en-us/library/ee624059\(v=ws.10\).aspx) the remote machine. If it doesn't reply to the ping, the remote tools won't be able to connect either. Try rebooting the remote machine and otherwise making sure that it is correctly configured on the network.  
  
## <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>The version of the remote debugger doesn't match the version of Visual Studio  
 The version of Visual Studio that you are running locally needs to match the version of the remote debugging monitor that is running on the remote machine. To fix this, download and install the matching version of the remote debugging monitor. Go to the [Download Center](http://www.microsoft.com/en-us/download) to find the right version of the remote debugger.  
  
## <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>The local and remote machines have different authentication modes  
 The local and remote machines need to use the same authentication mode. To fix this, make sure that both machines are using the same authentication mode. For more information about authentication modes, see [Windows Authentication Overview](https://technet.microsoft.com/en-us/library/hh831472.aspx).  
  
## <a name="the-remote-debugger-is-running-under-a-different-user-account"></a>The remote debugger is running under a different user account  
 You can solve this in one of the following ways:  
  
-   You can stop the remote debugger and restart it with the account you are using on the local computer.  
  
-   You can start the remote debugger from the command line with the **/allow \<username>** parameter: `msvsmon /allow <username@computer>`  
  
-   You can add the user to the remote debugger's permissions (in the remote debugger window, **Tools > Permissions**).  
  
-   If you can't use the methods in the preceding steps, you can allow any user to do remote debugging. In the remote debugger window, go to the **Tools > Options** dialog. When you select   **No Authentication**, you can then check **Allow any user to debug**. However, you should use this option only if you have no choice, or if you are on a private network.  
  
## <a name="the-firewall-on-the-remote-machine-doesnt-allow-incoming-connections-to-the-remote-debugger"></a>The firewall on the remote machine doesn't allow incoming connections to the remote debugger  
 The firewall on the Visual Studio machine and the firewall on the remote machine must be configured to allow communication between Visual Studio and the remote debugger. For information about the ports the remote debugger is using, see [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md). For information about configuring the Windows firewall, see [Configure the Windows Firewall for Remote Debugging](../debugger/configure-the-windows-firewall-for-remote-debugging.md).  
  
## <a name="anti-virus-software-is-blocking-the-connections"></a>Anti-virus software is blocking the connections  
 Windows anti-virus software allows remote debugger connections, but some third-party anti-virus software may block them. Check the documentation for your anti-virus software to find out how to allow these connections.  
  
## <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>Network security policy is blocking communication between the remote machine and Visual Studio  
 Review your network security to make sure that it is not blocking communication. For more information about Windows network security policy, see [Security policy settings](/windows/device-security/security-policy-settings/security-policy-settings).  
  
## <a name="the-network-is-too-busy-to-support-remote-debugging"></a>The network is too busy to support remote debugging  
 You may need to do remote debugging at a different time, or reschedule work on the network for a different time.  
  
## <a name="more-help"></a>More help  
 To get more remote debugger help, including command-line switches, click **Help > Usage** in the remote debugger window. If you don't have it open you can see the web page by copying the following line to a  **File Explorer** window. (You need to replace \<Visual Studio installation directory> with the location of your Visual Studio installation.)  
  
 res://*\<Visual Studio installation directory>*\Common7\IDE\Remote%20Debugger\x64\msvsmon.exe/help.htm  
  
## <a name="see-also"></a>See Also  
 [Remote Debugging Errors and Troubleshooting](../debugger/remote-debugging-errors-and-troubleshooting.md)