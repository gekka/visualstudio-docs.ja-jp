---
title: IDebugPortNotify2 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortNotify2
helpviewer_keywords:
- IDebugPortNotify2 interface
ms.assetid: 43278b79-bf16-4c08-bcf1-6f7f7a17feab
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e5bc329807d4b610ae42d3bb5ac5c95faf37db40
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51740388"
---
# <a name="idebugportnotify2"></a>IDebugPortNotify2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

このインターフェイスは、登録またはで実行されているポートでデバッグできるプログラムの登録を解除します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugPortNotify2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 カスタム ポート サプライヤーは、サポートを追加して、ポートからプログラムを削除するのには、このインターフェイスを実装します。 実装する同一のオブジェクトに通常実装、 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)インターフェイス。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出し[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)上、`IDebugPort2`インターフェイスは、このインターフェイスを返します。 呼び出しも、 [GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)このインターフェイスを返します。 デバッグ エンジンは、パラメーターとしてこのインターフェイスを確認できます[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 次の表は、メソッドの`IDebugPortNotify2`します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[AddProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)|実行されているポートをデバッグできるプログラムを登録します。|  
|[RemoveProgramNode](../../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)|実行されているポートからデバッグできるプログラムを登録解除します。|  
  
## <a name="remarks"></a>Remarks  
 デバッグ ポートに、プログラムはロードまたはアンロードを知る方法がない限り、カスタム ポート サプライヤーはこのインターフェイスを実装する必要があります。 このインターフェイスを使用して、特定のポートを使用して、デバッグ用に読み込まれたすべてのプログラムが追跡されます。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

