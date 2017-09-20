---
title: "PROFILER_HEAP_OBJECT_OPTIONAL_INFO 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 77e638bd-ae36-4292-a170-90a0c500e610
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# PROFILER_HEAP_OBJECT_OPTIONAL_INFO 構造体
ヒープのオブジェクトについての情報を表します。  
  
## 構文  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_OPTIONAL_INFO  
{  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE infoType;  
    [switch_type(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE), switch_is(infoType)] union  
    {  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE)] PROFILER_HEAP_OBJECT_ID prototype;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME)] LPCWSTR functionName;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE)] UINT elementAttributesSize;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE)] UINT elementTextChildrenSize;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST)] PROFILER_HEAP_OBJECT_SCOPE_LIST* scopeList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY)] PROFILER_HEAP_OBJECT_RELATIONSHIP* internalProperty;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* namePropertyList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* indexPropertyList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* relationshipList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* eventList;  
    };  
} PROFILER_HEAP_OBJECT_OPTIONAL_INFO;  
  
```  
  
## メンバー  
  
|メンバー|型|説明|  
|----------|-------|--------|  
|infoType|[PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_TYPE 列挙型](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|オプション情報の型。|  
|プロトタイプ|[PROFILER\_HEAP\_OBJECT\_ID 型](../../winscript/reference/profiler-heap-object-id-type.md)|ヒープ内のオブジェクトのプロトタイプ オブジェクトの ID。|  
|functionName|LPCWSTR|ヒープ内のオブジェクトの関数名。|  
|elementAttributesSize|UINT|ヒープのオブジェクト要素の属性のサイズ。|  
|elementTextChildrenSize|UINT|ヒープ内のオブジェクトのテキストの子のサイズ。|  
|scopeList|[PROFILER\_HEAP\_OBJECT\_SCOPE\_LIST 構造体](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|ヒープ内のオブジェクトの範囲のリスト。|  
|internalProperty|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 構造体](../../winscript/reference/profiler-heap-object-relationship-structure.md)|ヒープ内のオブジェクトの内部プロパティ。|  
|namePropertyList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 構造体](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|ヒープのオブジェクト名のプロパティのリスト。|  
|indexPropertyList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 構造体](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|ヒープ内のオブジェクトのインデックスのプロパティのリスト。|  
|relationshipList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 構造体](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|ヒープ内のオブジェクトの関係のリスト。|  
|eventList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 構造体](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|ヒープ内のオブジェクトのイベントの一覧。|