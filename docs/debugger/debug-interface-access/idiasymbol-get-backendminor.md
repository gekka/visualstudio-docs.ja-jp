---
title: "IDiaSymbol::get_backEndMinor | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSymbol::get_backEndMinor メソッド"
ms.assetid: 37f38d19-6685-440d-a477-7127c4f8699e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_backEndMinor
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

コンパイラのバック エンドのマイナー バージョン番号を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_backEndMinor (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]バック エンドのマイナー バージョン番号を返します。 「解説」を参照してください。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返す `S_OK`、それ以外を返します `S_FALSE` またはエラー コード。  
  
> [!NOTE]
>  戻り値 `S_FALSE` プロパティがシンボルを使用できないことを意味します。  
  
## <a name="remarks"></a>コメント  
 コンパイラは、2 つの主な要素で構成されます。: 中間形式のソース コードの解析を処理するフロント エンド (パーサー) と、バック エンド (コード ジェネレーター) をアセンブリに中間形式に変換します。 フロント エンドがバックエンドとは異なるバージョンがあるは珍しいことではありません。  
  
 フロント エンドまたはバックエンドのバージョン番号は 3 つの部分で構成されます: \< 主要な>. \< マイナー>. \< ビルド>, ここで、\< メジャー> メジャー バージョン番号は、\< マイナー> マイナー バージョン番号と \< ビルド> ビルド番号です。 たとえば、13.10.3077 です。  
  
## <a name="requirements"></a>要件  
  
|必要条件|説明|  
|-----------------|-----------------|  
|ヘッダー:|dia2.h|  
|バージョン:|DIA SDK v7.0|  
  
## <a name="see-also"></a>関連項目  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)