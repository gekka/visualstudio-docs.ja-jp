---
title: "IEnumDebugApplicationNodes::Next | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugApplicationNodes.Next
apilocation: pdm.dll
helpviewer_keywords: 
  - "IEnumDebugApplicationNodes::Next"
ms.assetid: 925511c8-4f11-423d-ba2d-01589457050c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugApplicationNodes::Next
列挙体シーケンス内の指定した数のセグメントを取得します。  
  
## 構文  
  
```  
HRESULT Next(  
   ULONG                    celt,  
   IDebugApplicationNode**  pprddp,  
   ULONG*                   pceltFetched  
);  
```  
  
#### パラメーター  
 `celt`  
 \[入力\]取得する線分の数。  
  
 `pprddp`  
 \[入力\]取得されるセグメントを表す `IDebugApplicationNode` のインターフェイスの配列を返します。  
  
 `pceltFetched`  
 \[入力\]列挙子によってフェッチ セグメントの実際の数。  
  
## 戻り値  
 このメソッドは `HRESULT` を返します。  指定できる値は、に含まれていますが、次の表に、これらはありません。  
  
|値|説明|  
|-------|--------|  
|`S_OK`|メソッドが成功しました。|  
  
## 解説  
 このメソッドは、列挙体シーケンスのセグメントの指定した数を取得します。  
  
## 参照  
 [IEnumDebugApplicationNodes インターフェイス](../../winscript/reference/ienumdebugapplicationnodes-interface.md)