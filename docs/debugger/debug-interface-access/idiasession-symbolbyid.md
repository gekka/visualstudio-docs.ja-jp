---
title: Idiasession::symbolbyid |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ca800c4409c9c3c1b72b625aa8cedac31e5b194
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49911636"
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
一意の識別子をシンボルを取得します。  
  
## <a name="syntax"></a>構文  
  
```C++  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `id`  
 [in]一意の識別子。  
  
 `ppSymbol`  
 [out]返します、 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)シンボルを表すオブジェクトを取得します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 指定された識別子が、一意の値がすべてのシンボルを一意にする、DIA SDK によって内部的に使用します。  
  
 このメソッドができますが、たとえば、他の記号の型を表すシンボルを取得する (例を参照してください)。  
  
## <a name="example"></a>例  
 この例では取得、 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)他の記号の型を表します。 この例は、使用する方法を示します、`symbolById`セッション内のメソッド。 簡単な方法には、 [idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)型のシンボルを直接取得するメソッド。  
  
```C++  
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)  
{  
    IDiaSymbol *pTypeSymbol = NULL;  
    if (pSymbol != NULL && pSession != NULL)  
    {  
        DWORD symbolTypeId;  
        pSymbol->get_typeId(&symbolTypeId);  
        pSession->symbolById(symbolTypeId, &pTypeSymbol);  
    }  
    return(pTypeSymbol);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)