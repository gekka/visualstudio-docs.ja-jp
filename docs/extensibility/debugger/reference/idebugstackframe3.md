---
title: "IDebugStackFrame3 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugStackFrame3
helpviewer_keywords:
- IDebugStackFrame3 interface
ms.assetid: 39af2f57-0a01-42b8-b093-b7fbc61e2909
caps.latest.revision: 15
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
translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 71ffa007c894090b9c0af2ad16429f381eb2db8b
ms.lasthandoff: 04/05/2017

---
# <a name="idebugstackframe3"></a>IDebugStackFrame3
このインターフェイスを拡張[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)傍受した例外を処理します。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugStackFrame3 : IDebugStackFrame2  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 デバッグ エンジン (DE) を実装する同一のオブジェクトにこのインターフェイスを実装する、 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)傍受した例外をサポートするインターフェイスです。  
  
## <a name="notes-for-callers"></a>呼び出し元のノート  
 呼び出す[QueryInterface](/cpp/atl/queryinterface)上、`IDebugStackFrame2`インターフェイスをこのインターフェイスを取得します。  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
 継承されたメソッドだけでなく[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)、`IDebugStackFrame3`は次のメソッドを公開します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)|任意の通常の例外処理の前に、現在のスタック フレームの例外を処理します。|  
|[GetUnwindCodeContext](../../../extensibility/debugger/reference/idebugstackframe3-getunwindcodecontext.md)|スタック アンワインドが発生した場合は、コードのコンテキストを返します。|  
  
## <a name="remarks"></a>コメント  
 傍受した例外は、通常の例外処理ルーチンは、ランタイムによって呼び出される前に、デバッガーが例外を処理できることを意味します。 例外をインターセプトし、基本的には、実行時間がある例外ハンドラーがない場合にも存在として扱わを行うを意味します。  
  
 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) (唯一の例外は、かどうかはコードをデバッグする混合モード (マネージし、アンマネージ コード)、最終コールバック中に例外をインターセプトできない場合は) すべての標準の例外コールバック イベント中に呼び出されます。 デを実装しない場合`IDebugStackFrame3`、か、DE IDebugStackFrame3 からエラーが返されます::`InterceptCurrentException` (など`E_NOTIMPL`)、デバッガーが通常は、例外を処理し、します。  
  
 例外をインターセプトし、によって、デバッガーはデバッグ中のプログラムの状態を変更して、例外がスローされた時点での実行を再開するユーザーを許可できます。  
  
> [!NOTE]
>  傍受した例外は、共通言語ランタイム (CLR) 下で実行しているプログラムでは、マネージ コードでのみ許可されてです。  
  
 デバッグ エンジンを示す"metricExceptions"を設定して、受信の例外をサポートしている値の 1 に実行時に使用して、`SetMetric`関数。 詳細については、次を参照してください。[をデバッグ用の SDK ヘルパー](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)です。  
  
## <a name="requirements"></a>要件  
 ヘッダー: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [コア インターフェイス](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [デバッグ用の SDK ヘルパー](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)