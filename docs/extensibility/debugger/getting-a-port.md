---
title: Getting a Port | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, getting
- debugging [Debugging SDK], ports
ms.assetid: 745c2337-cfff-4d02-b49c-3ca7c4945c5e
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: a13a24f2816f846769b8639da965f360f8a8f92b
ms.contentlocale: ja-jp
ms.lasthandoff: 08/28/2017

---
# <a name="getting-a-port"></a>Getting a Port
A port represents a connection to a machine on which processes are running. That machine could be the local machine or a remote machine (which could possibly be running a non-Windows-based operating system; see [Ports](../../extensibility/debugger/ports.md) for more information).  
  
 A port is represented by the [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) interface. It is used to obtain information about processes running on the machine the port is connected to.  
  
 A debug engine needs access to a port in order to register program nodes with the port and to satisfy requests for process information. For example, if the debug engine implements the [IDebugProgramProvider2](../../extensibility/debugger/reference/idebugprogramprovider2.md) interface, the implementation for the [GetProviderProcessData](../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md) method could ask the port for the necessary process information to be returned.  
  
 Visual Studio supplies the necessary port to the debug engine, and it obtains this port from a port supplier. If a program is attached to (either from within the debugger or because of an exception was thrown, which triggers the Just-in-Time [JIT] dialog box), the user is given the choice of transport (another name for a port supplier) to use. Otherwise, if the user launches the program from within the debugger, the project system specifies the port supplier to use. In either event, Visual Studio instantiates the port supplier, represented by an [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) interface, and asks for a new port by calling [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) with an [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) interface. This port is then passed on to the debug engine in one form or another.  
  
## <a name="example"></a>Example  
 This code fragment shows how to use the port supplied to [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) to register a program node in [ResumeProcess](../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md). Parameters not directly related to this concept have been omitted for clarity.  
  
> [!NOTE]
>  This example uses the port to launch and resume the process and assumes that the [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md) interface is implemented on the port. This is by no means the only way to perform these tasks, and it is possible that the port may not even be involved other than to have the program's [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) given to it.  
  
```cpp  
// This is an IDebugEngineLaunch2 method.  
HRESULT CDebugEngine::LaunchSuspended(/* omitted parameters */,  
                                      IDebugPort2 *pPort,  
                                      /* omitted parameters */,  
                                      IDebugProcess2**ppDebugProcess)  
{  
    // do stuff here to set up for a launch (such as handling the other parameters)  
    ...  
  
    // Now get the IPortNotify2 interface so we can register a program node  
    // in CDebugEngine::ResumeProcess.  
    CComPtr<IDebugDefaultPort2> spDefaultPort;  
    HRESULT hr = pPort->QueryInterface(&spDefaultPort);  
    if (SUCCEEDED(hr))  
    {  
        CComPtr<IDebugPortNotify2> spPortNotify;  
        hr = spDefaultPort->GetPortNotify(&spPortNotify);  
        if (SUCCEEDED(hr))  
        {  
            // Remember the port notify so we can use it in ResumeProcess.  
            m_spPortNotify = spPortNotify;  
  
            // Now launch the process in a suspended state and return the  
            // IDebugProcess2 interface  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = pPort->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                // pass on the parameters we were given (omitted here)  
                hr = spPortEx->LaunchSuspended(/* omitted paramters */,ppDebugProcess)  
            }  
        }  
    }  
    return(hr);  
}  
  
HRESULT CDebugEngine::ResumeProcess(IDebugProcess2 *pDebugProcess)  
{  
    // Make a program node for this process  
    HRESULT hr;  
    CComPtr<IDebugProgramNode2> spProgramNode;  
    hr = this->GetProgramNodeForProcess(pProcess, &spProgramNode);  
    if (SUCCEEDED(hr))  
    {  
        hr = m_spPortNotify->AddProgramNode(spProgramNode);  
        if (SUCCEEDED(hr))  
        {  
            // resume execution of the process using the port given to us earlier.  
           // (Querying for the IDebugPortEx2 interface is valid here since  
           // that's how we got the IDebugPortNotify2 interface in the first place.)  
            CComPtr<IDebugPortEx2> spPortEx;  
            hr = m_spPortNotify->QueryInterface(&spPortEx);  
            if (SUCCEEDED(hr))  
            {  
                hr  = spPortEx->ResumeProcess(pDebugProcess);  
            }  
        }  
    }  
    return(hr);  
}  
```  
  
## <a name="see-also"></a>See Also  
 [Registering the Program](../../extensibility/debugger/registering-the-program.md)   
 [Enabling a Program to Be Debugged](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)   
 [Port Suppliers](../../extensibility/debugger/port-suppliers.md)   
 [Ports](../../extensibility/debugger/ports.md)