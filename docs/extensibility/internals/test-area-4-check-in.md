---
title: 'テスト領域 4: で確認してください |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], checking items in
- source control plug-ins, checking items in
ms.assetid: d0329fa8-7a8d-4d30-b67b-6f2a97b75a30
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e7f3e8a343823016f391735aae59e58dfefe1a5f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
ms.locfileid: "31133151"
---
# <a name="test-area-4-check-in"></a>チェックイン テスト領域 4:
このソース管理プラグインのテストの領域の説明を使用して、バージョン ストアに更新された項目を送信する、**チェックイン**コマンド。  
  
## <a name="command-menu-access"></a>コマンド メニューへのアクセス  
 次[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]統合開発環境] メニューの [パスは、テストの場合に使用されます。  
  
##### <a name="check-in"></a>チェックイン：  
 **ファイル**、**ソース コントロール**、**チェックイン**です。  
  
 **ファイル**、**チェックイン**です。  
  
 ショートカット メニューの **チェックイン**です。  
  
## <a name="common-expected-behavior"></a>共通の想定される動作  
  
-   プロジェクトおよびソリューションまたはプロジェクトをソース管理に追加されたファイルの表示、**チェックイン** ダイアログ ボックスおよび**保留中のチェックイン**ウィンドウです。  
  
-   確認後に、ソース管理に追加された項目が表示されます。  
  
-   確認後に、更新された項目は適切なバージョン ストアです。  
  
## <a name="test-cases"></a>テスト ケース  
 チェックイン テスト区分の特定のテスト_ケースを次に示します。  
  
### <a name="case-4a-modified-items"></a>ケース 4 a: 項目を変更  
 アクションで、チェックを使用して、変更されているソース管理下にあるファイルを更新するについて説明します。  
  
|アクション|テスト ステップ|期待される結果を確認するには|  
|------------|----------------|--------------------------------|  
|チェック アウトされているテキスト ファイルを変更して、ファイルのみで確認してください (**チェックイン** ダイアログ ボックス)|1.テキスト ファイルを使用して、新しいプロジェクトを作成します。<br />2.ソリューションをソース管理に追加します。<br />3.チェック アウトして、テキスト ファイルを変更します。<br />4.チェックイン ダイアログ ボックスを使用してチェックイン (**ファイル**、**ソース管理**、**チェックイン**)。|共通の期待される動作です。|  
|チェック アウトされているテキスト ファイルを変更して、ファイルのみで確認してください (**保留中のチェックイン**ウィンドウ)|1.テキスト ファイルを使用して、新しいプロジェクトを作成します。<br />2.ソリューションをソース管理に追加します。<br />3.チェック アウトして、テキスト ファイルを変更します。<br />4.使用してチェックイン、**保留中のチェックイン**ウィンドウです。|共通の期待される動作です。|  
  
### <a name="case-4b-adding-files"></a>4b の場合: ファイルを追加します。  
 ファイルをプロジェクトまたはソリューションに項目を追加する場合、プロジェクトまたはソリューションも変更する必要があります。 したがって親ファイルもチェック アウトしても追加を完了にチェックインする必要があります。  
  
|アクション|テスト ステップ|期待される結果を確認するには|  
|------------|----------------|--------------------------------|  
|テキスト ファイルを追加し、すべてをチェックイン (**チェックイン** ダイアログ ボックス)|1.新しいプロジェクトを作成します。<br />2.ソリューションをソース管理に追加します。<br />3.テキスト ファイルをプロジェクトに追加します。<br />4.求められた場合は、プロジェクトのチェック アウトをそのまま使用します。<br />5.ソリューションを選択して**ソリューション エクスプ ローラー**です。<br />6.チェックイン、**チェックイン** ダイアログ ボックス。|共通の期待される動作です。|  
|テキスト ファイルを追加し、すべてをチェックイン (**保留中のチェックイン**ウィンドウ)|1.新しいプロジェクトを作成します。<br />2.ソリューションをソース管理に追加します。<br />3.テキスト ファイルをプロジェクトに追加します。<br />4.求められた場合は、プロジェクトのチェック アウトをそのまま使用します。<br />5.ソリューションをチェックイン**保留中のチェックイン**ウィンドウです。|共通の想定される動作|  
  
### <a name="case-4c-adding-projects"></a>ケース 4 c: プロジェクトの追加  
 プロジェクトをソリューションに追加する際、ソリューションも変更する必要があります。 したがって、ソリューション ファイルもチェック アウトしても追加を完了にチェックインする必要があります。  
  
|アクション|テスト ステップ|期待される結果を確認するには|  
|------------|----------------|--------------------------------|  
|ソース管理下にある空のソリューションにプロジェクトを追加 (**チェックイン** ダイアログ ボックス)|1.空のソリューションを作成します。<br />2.ソリューションをソース管理に追加します。<br />3.新しいプロジェクトを追加します。<br />4.求められた場合は、ソリューションのチェック アウトをそのまま使用します。<br />5.チェックイン、**チェックイン** ダイアログ ボックス。|共通の期待される動作です。|  
|ソース管理下にある空のソリューションにプロジェクトを追加 (**保留中のチェックイン**ウィンドウ)|1.空のソリューションを作成します。<br />2.ソリューションをソース管理に追加します。<br />3.新しいプロジェクトを追加します。<br />4.求められた場合は、ソリューションのチェック アウトをそのまま使用します。<br />5.ソリューションをチェックイン**保留中のチェックイン**ウィンドウです。|共通の期待される動作です。|  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグイン向けのテスト ガイド](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)