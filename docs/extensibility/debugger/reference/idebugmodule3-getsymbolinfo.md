---
title: IDebugModule3::GetSymbolInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugModule3::GetSymbolInfo
helpviewer_keywords:
- GetSymbolInfo method
- IDebugModule3::GetSymbolInfo method
ms.assetid: dda5e8e1-6878-4aa9-9ee4-e7d0dcc11210
caps.latest.revision: 17
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
ms.sourcegitcommit: 21a413a3e2d17d77fd83d5109587a96f323a0511
ms.openlocfilehash: 4923c6f79299338b2e615a0c8cae25afe28f1c80
ms.contentlocale: ja-jp
ms.lasthandoff: 08/30/2017

---
# <a name="idebugmodule3getsymbolinfo"></a>IDebugModule3::GetSymbolInfo
Retrieves a list of paths that are searched for symbols as well as the results of searching each path.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSymbolInfo(  
   SYMBOL_SEARCH_INFO_FIELDS  dwFields,  
   MODULE_SYMBOL_SEARCH_INFO* pInfo  
);  
```  
  
```csharp  
int GetSymbolInfo(  
   enum_SYMBOL_SEARCH_INFO_FIELDS dwFields,   
   MODULE_SYMBOL_SEARCH_INFO[]    pinfo  
);  
  
```  
  
#### <a name="parameters"></a>Parameters  
 `dwFields`  
 [in] A combination of flags from the [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) enumeration specifying which fields of `pInfo` are to be filled in.  
  
 `pInfo`  
 [out] A [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md) structure whose members are to be filled in with the specified information. If this is a null value, this method returns `E_INVALIDARG`.  
  
## <a name="return-value"></a>Return Value  
 If the method succeeds, it returns `S_OK`; otherwise, it returns an error code.  
  
> [!NOTE]
>  The returned string (in the `MODULE_SYMBOL_SEARCH_INFO` structure) could be empty even if `S_OK` is returned. In this case, there was no search information to return.  
  
## <a name="remarks"></a>Remarks  
 If the `bstrVerboseSearchInfo` field of the `MODULE_SYMBOL_SEARCH_INFO` structure is not empty, then it contains a list of paths searched and the results of that search. The list is formatted with a path, followed by an ellipsis ("..."), followed by the result. If there is more than one path result pair, then each pair is separated by a "\r\n" (carriage-return/linefeed) pair. The pattern looks like this:  
  
 \<path>...\<result>\r\n\<path>...\<result>\r\n\<path>...\<result>  
  
 Note that the last entry does not have a \r\n sequence.  
  
## <a name="example"></a>Example  
 In this example, this method returns three paths with three different search results. Each line is terminated with a carriage-return/linefeed pair. The example output just prints the search results as a single string.  
  
> [!NOTE]
>  A status result is everything immediately following the "..." up to the end of the line.  
  
```cpp  
void ShowSymbolSearchResults(IDebugModule3 *pIDebugModule3)  
{  
    MODULE_SYMBOL_SEARCH_INFO ssi = { 0 };  
    HRESULT hr;  
    hr = pIDebugModule3->GetSymbolInfo(SSIF_VERBOSE_SEARCH_INFO,&ssi);  
    if (SUCCEEDED(hr)) {  
        CComBSTR searchInfo = ssi.bstrVerboseSearchInfo;  
        if (searchInfo.Length() != 0) {  
            std::wcout << (wchar_t *)(BSTR)searchInfo;  
            std::wcout << std::endl;  
        }  
    }  
}  
```  
  
 **c:\symbols\user32.pdb... File not found.**  
**c:\winnt\symbols\user32.pdb... Version does not match.**  
**\\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.**   
## <a name="see-also"></a>See Also  
 [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md)   
 [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md)   
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)