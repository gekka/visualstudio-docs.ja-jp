---
title: コマンド ラインからの移植可能なプロファイル データ ファイルの作成 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9367f4b7c85886eda629767809e1841c72340e4d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51795517"
---
# <a name="creating-portable-profiling-data-files-from-the-command-line"></a>移植可能なプロファイル データ ファイルのコマンド ラインからの作成
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

プロファイル データの共有を簡単に行うために、[VSPerfReport](../profiling/vsperfreport.md) コマンドライン ツールを利用し、プロファイリング実行用のシンボルを .vsp ファイル内に埋め込むことができます。  
  
 また、サイズが小さく、IDE にすばやく読み込むことのできる解析済みプロファイル データ (.vsps) ファイルを作成することもできます。  
  
> [!NOTE]
>  シンボル (.pdb) ファイルが **VSPerfReport** で利用できることを確認します。 詳細については、「[方法: コマンド ラインからシンボル ファイルの場所を指定する](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md)」を参照してください。  
>   
>  **VSReport** のパスの詳細については、「[コマンド ライン ツールへのパスの指定](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)」をご覧ください。  
>   
>  .vsps ファイルのプロファイリング データはフィルター処理できません。  
  
### <a name="to-embed-the-symbols-for-a-profiling-run-into-a-profiling-data-vsp-file"></a>プロファイリング実行のシンボルをプロファイリング データ (.vsp) ファイルに組み込むには  
  
- [コマンド プロンプト] ウィンドウで、次のコマンドを入力します。  
  
   \<Path><strong>VSPerfReport \<</strong>VSP File> **/PackSymbols**  
  
   既定では、.vsps ファイルには、.vsp ファイルのベース名で名前が付けられます。 **Output** オプションを利用し、代替名を指定できます。  
  
### <a name="to-create-a-summary-profiling-data-file"></a>概要プロファイリング データ ファイルを作成するには  
  
- [コマンド プロンプト] ウィンドウで、次のコマンドを入力します。  
  
   \<Path><strong>VSPerfReport \<</strong>VSP File> **/SummaryFile** [**/Output:**\<File Name>]  
  
   既定では、.vsps ファイルには、.vsp ファイルのベース名で名前が付けられます。 **Output** オプションを利用し、代替名を指定できます。



