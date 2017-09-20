---
title: "トラブルシューティング コード カバレッジ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26de91b8-45e3-4976-a20e-a3bd1942ddcb
caps.latest.revision: 11
ms.author: douge
manager: douge
translation.priority.ht:
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3d32d11a430227800cb3ed53831a9565eb6adeb3
ms.openlocfilehash: c435bb9e490e9a3c59de78f383632552c0ca4641
ms.contentlocale: ja-jp
ms.lasthandoff: 05/30/2017

---
# <a name="troubleshooting-code-coverage"></a>トラブルシューティング コード カバレッジ
Visual Studio のコード カバレッジ分析ツールは、ネイティブ アセンブリとマネージ アセンブリのデータを収集します (.dll または .exe ファイル)。 しかし、[コード カバレッジの結果] ウィンドウに "空の結果が生成されました: ...." のようなエラーが表示される場合があります。このエラーが発生する原因はいくつかあります。 このトピックは、これらの問題を解決することを目的にしています。  
  
## <a name="what-you-should-see"></a>表示される内容  
 [テスト] メニューの **[コード カバレッジの分析]** コマンドを選択し、ビルドとテストが正常に実行された場合、[コード カバレッジ] ウィンドウに結果の一覧が表示されます。 詳細を表示するために、項目を展開する必要がある場合があります。  
  
 ![色分けされたコード カバレッジの結果](../test/media/codecoverage1.png "CodeCoverage1")  
  
 詳細については、「[コード カバレッジを使用した、テストされるプロジェクトのコード割合の確認](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)」を参照してください。  
  
## <a name="possible-reasons-for-seeing-no-results-or-old-results"></a>結果が表示されなかったり古い結果が表示されたりすることの考えられる原因  
  
### <a name="do-you-have-the-right-edition-of-visual-studio"></a>適切なエディションの Visual Studio を使用していますか?  
 Visual Studio Enterprise が必要です。  
  
### <a name="no-tests-were-executed"></a>テストが実行されなかった  
 分析  
 出力ウィンドウをチェックします。 **[出力元の表示]** ドロップダウン リストで、**[テスト]** を選択します。 記録された警告またはエラーがあるかどうかを確認します。  
  
 説明  
 コード カバレッジ分析は、テストの実行中に行われます。 分析には、テストの実行時にメモリに読み込まれるアセンブリだけが含まれます。 テストが実行されない場合、コード カバレッジで報告される結果はありません。  
  
 解決策  
 テスト エクスプローラーで、**[すべて実行]** を選択してテストが正常に実行されることを確認します。 **[コード カバレッジの分析]** を使用する前にエラーを修正します。  
  
### <a name="youre-looking-at-a-previous-result"></a>前の結果が表示されている  
 テストを変更し、再実行したときに、まだ前のコード カバレッジの結果が表示され、コードの色分けも前の実行のものである場合があります。  
  
1.  コード カバレッジの分析を実行します。  
  
2.  [コード カバレッジの結果] ウィンドウで、最新の結果セットが選択されていることを確認します。  
  
### <a name="pdb-symbol-files-are-unavailable"></a>.pdb (シンボル) ファイルが使用できない  
 分析  
 コンパイルの対象フォルダー (通常は bin\debug) を開き、アセンブリごとに、.dll または .exe ファイルと同じディレクトリに .pdb ファイルがあることを確認します。  
  
 説明  
 コード カバレッジ エンジンを使用するには、すべてのアセンブリにテストの実行中にアクセスできる .pdb ファイルがあることが必要です。 特定のアセンブリの .pdb ファイルがない場合、そのアセンブリは解析されません。  
  
 .pdb ファイルは、.dll または .exe ファイルと同じビルドから生成されている必要があります。  
  
 解像度  
 ビルドが .pdb ファイルを生成するように設定されていることを確認します。 プロジェクトのビルド時に .pdb ファイルが更新されない場合は、プロジェクトのプロパティを開き、**[ビルド]** ページ、**[詳細設定]** の順に選択し、**[デバッグ情報]** を確認します。  
  
 .pdb ファイルと .dll または .exe ファイルが別の場所にある場合は、.pdb ファイルを同じディレクトリにコピーします。 別の場所の .pdb ファイルを検索するようにコード カバレッジ エンジンを構成することもできます。 詳細については、「[コード カバレッジ分析のカスタマイズ](../test/customizing-code-coverage-analysis.md)」を参照してください。  
  
### <a name="using-an-instrumented-or-optimized-binary"></a>インストルメント化、または最適化されたバイナリを使用している  
 分析  
 バイナリにガイド付き最適化のプロファイルなどの詳細な最適化が適用されたかどうか、またはバイナリが vsinstr.exe や vsperfmon.exe などのプロファイリング ツールによってインストルメント化されたかどうかを確認します。  
  
 説明  
 アセンブリが別のプロファイリング ツールによって、既にインストルメント化または最適化されている場合、アセンブリはコード カバレッジ分析から省略されます。  
  
 コード カバレッジ分析は、このようなアセンブリでは実行できません。  
  
 解像度  
 最適化をオフにし、新しいビルドを使用します。  
  
### <a name="code-is-not-managed-net-or-native-c-code"></a>コードがマネージ (.NET) コードまたはネイティブ (C++) コードではない  
 分析  
 マネージ コードまたは C++ コードでテストを実行していることを確認します。  
  
 説明  
 Visual Studio のコード カバレッジ分析は、マネージ コードとネイティブ (C++) コードでのみ使用できます。 サードパーティ製ツールで作業している場合、コードの一部またはすべてが別のプラットフォームで実行される可能性があります。  
  
 解像度  
 解決策はありません。  
  
### <a name="assembly-has-been-installed-by-ngen"></a>アセンブリが NGen によってインストールされた  
 分析  
 アセンブリがネイティブ イメージ キャッシュから読み込まれていないことを確認します。  
  
 説明  
 パフォーマンス上の理由から、ネイティブ イメージ アセンブリは分析されません。 詳細については、「[Ngen.exe (ネイティブ イメージ ジェネレーター)](/dotnet/framework/tools/ngen-exe-native-image-generator)」を参照してください。  
  
 解決策  
 MSIL バージョンのアセンブリを使用します。 アセンブリを NGen で操作しません。  
  
### <a name="custom-runsettings-file-with-bad-syntax"></a>カスタム .runsettings ファイルに無効な構文が含まれている  
 分析  
 カスタム .runsettings ファイルを使用している場合、ファイルに構文エラーが含まれている可能性があります。  
  
 その場合、コード カバレッジはまったく実行されません。 テスト実行の最後にコード カバレッジ ウィンドウが開かれないか、ウィンドウに古い結果が表示されます。  
  
 説明  
 カスタム .runsettings ファイルで単体テストを実行して、コード カバレッジのオプションを構成することができます。 オプションで、ファイルを含めるか、除外するかを指定できます。 詳細については、「[コード カバレッジ分析のカスタマイズ](../test/customizing-code-coverage-analysis.md)」を参照してください。  
  
 解決策  
 エラーには次の 2 種類があります。  
  
-   **XML エラー**  
  
     Visual Studio XML エディターで .runsettings ファイルを開きます。 エラーを示す箇所を探します。  
  
-   **正規表現エラー**  
  
     ファイル内の各文字列は正規表現です。 エラーのすべてをレビューし、特に次の文字を探します。  
  
    -   一致しないかっこ (...) またはエスケープされないかっこ \\(...\\)。 検索文字列内でかっこを一致させる場合は、エスケープする必要があります。 たとえば、関数を一致させるには `.*MyFunction\(double\)` を使用します。  
  
    -   式の先頭のアスタリスクまたは正符号。 任意の文字列と一致させるには、ピリオドとアスタリスクを続けて使用します (`.*`)。  
  
### <a name="custom-runsettings-file-with-incorrect-exclusions"></a>カスタム .runsettings ファイルに不適切な除外が含まれている  
 分析  
 カスタム .runsettings ファイルを使用している場合は、アセンブリが含まれていることを確認します。  
  
 説明  
 カスタム .runsettings ファイルで単体テストを実行して、コード カバレッジのオプションを構成することができます。 オプションで、ファイルを含めるか、除外するかを指定できます。 詳細については、「[コード カバレッジ分析のカスタマイズ](../test/customizing-code-coverage-analysis.md)」を参照してください。  
  
 解決策  
 .runsettings ファイルからすべての `Include` ノードを削除し、すべての `Exclude` ノードを削除します。 これで問題が解決する場合は、各ノードを段階的に元に戻します。  
  
 DataCollectors ノードがコード カバレッジを指定していることを確認します。 「[コード カバレッジ分析のカスタマイズ](../test/customizing-code-coverage-analysis.md)」の例と比較します。  
  
## <a name="some-code-is-always-shown-as-not-covered"></a>一部のコードが常に未カバーとして表示される  
  
### <a name="initialization-code-in-native-dlls-is-executed-before-instrumentation"></a>ネイティブ DLL 内の初期化コードがインストルメンテーションの前に実行される  
 分析  
 静的にリンクされたネイティブ コードでは、初期化関数 **DllMain** の一部とそれが呼び出すコードが、コードが実行された場合でも未カバーとして表示されることがあります。  
  
 説明  
 コード カバレッジ ツールは、アプリケーションが実行を開始する直前にアセンブリにインストルメンテーションを挿入することで動作します。 この時点より前に読み込まれるアセンブリでは、アプリケーションの実行前の、アセンブリの読み込み直後に **DllMain** 内の初期化コードが実行されます。 そのコードは未カバーであるように見えます。  
  
 通常、これは静的に読み込まれたアセンブリに適用されます。  
  
 解像度  
 なし。  
  
## <a name="see-also"></a>関連項目  
 [コード カバレッジを使用した、テストされるプロジェクトのコード割合の確認](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)
