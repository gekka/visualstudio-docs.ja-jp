---
title: Visual Studio プロファイラー API リファレンス (ネイティブ) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, API
- Profiler, API
ms.assetid: a0c3be92-c263-4678-9fb9-bafead3bd5f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: ba2590c17a41d200f0a8dd3c38c7c9ae8c8a85cc
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572099"
---
# <a name="visual-studio-profiler-api-reference-native"></a>Visual Studio プロファイラー API リファレンス (ネイティブ)
Visual Studio プロファイラー API を使用すると、収集データの量をプログラムで制御したり、タイムスタンプとプロファイルの両方のマークをプロファイル時に挿入したりできます。 ネイティブ API を使用するには、*VSPerf.h* ヘッダー ファイルをインクルードし、*VSPerf.lib* をプロジェクトに追加する必要があります。  
  
> [!NOTE]
>  既定では、*VSPerf.h* と *VSPerf.lib* は *PerfSDK* という名前のフォルダーにあります。 たとえば、*\<ドライブ>:\Program Files\Microsoft Visual Studio 14.0\Team Tools\Performance Tools\PerfSDK* ディレクトリなどです。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [CommentMarkAtProfile](../profiling/commentmarkatprofile.md)  
  
 [CommentMarkProfile](../profiling/commentmarkprofile.md)  
  
 [MarkProfile](../profiling/markprofile.md)  
  
 [NameProfile](../profiling/nameprofile.md)  
  
 [ResumeProfile](../profiling/resumeprofile.md)  
  
 [StartProfile](../profiling/startprofile.md)  
  
 [StopProfile](../profiling/stopprofile.md)  
  
 [SuspendProfile](../profiling/suspendprofile.md)  
  
 [PROFILE_CURRENTID](../profiling/profile-currentid.md)  
  
## <a name="see-also"></a>関連項目  
 [プロファイリング ツールの API](../profiling/profiling-tools-apis.md)   
 [チュートリアル : プロファイラー API の使用](../profiling/walkthrough-using-profiler-apis.md)
