---
title: "marker_series::marker_series コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cvmarkersobj/Concurrency::diagnostic::marker_series::marker_series"
helpviewer_keywords: 
  - "Concurrency::diagnostic::marker_series コンストラクター"
ms.assetid: 042c7d23-f1d8-4e09-9e76-a21c30243790
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# <a name="markerseriesmarkerseries-constructor"></a>marker_series::marker_series コンストラクター
`marker_series` クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
marker_series();  
marker_series(  
   _In_ LPCTSTR _SeriesName  
);  
marker_series(  
   _In_ const GUID* _ProviderGuid  
);  
marker_series(  
   _In_ const GUID* _ProviderGuid,  
   _In_ LPCTSTR _SeriesName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_SeriesName`  
 作成するシリーズの名前。  
  
 `_ProviderGuid`  
 シリーズのプロバイダーの GUID。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** cvmarkersobj.h  
  
 **名前空間:** Concurrency::diagnostic  
  
## <a name="see-also"></a>関連項目  
 [marker_series クラス](../profiling/marker-series-class.md)


<!--HONumber=Feb17_HO4-->

