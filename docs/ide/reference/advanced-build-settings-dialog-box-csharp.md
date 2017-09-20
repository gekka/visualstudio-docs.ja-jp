---
title: "[ビルドの詳細設定] ダイアログ ボックス (C#) | Microsoft Docs"
ms.custom: 
ms.date: 06/20/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cs.AdvancedBuildSettings
helpviewer_keywords:
- Build options [C#], advanced
ms.assetid: 141f2dee-1563-4ce6-ba37-32920b082519
caps.latest.revision: 13
author: kempb
ms.author: kempb
manager: ghogen
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
ms.sourcegitcommit: b7b29ffadcb069b6c918dfbe89f0ae49d0da172a
ms.openlocfilehash: a281313904bb8881d2e96065a024447d151cddbd
ms.contentlocale: ja-jp
ms.lasthandoff: 06/20/2017

---
# <a name="advanced-build-settings-dialog-box-c"></a>[ビルドの詳細設定] ダイアログ ボックス (C#)

**プロジェクト デザイナー**の **[ビルドの詳細設定]** ダイアログ ボックスを使用して、プロジェクトの詳細なビルド構成プロパティを指定します。 このダイアログ ボックスは、[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] プロジェクトにのみ適用されます。

## <a name="general"></a>全般

 次のオプションを使用すると、全般的な詳細設定を有効にできます。

 **言語バージョン**
 使用する言語のバージョンを指定します。 機能セットはバージョンによって異なるので、このオプションを使用して、コンパイラが特定の実装機能のみを許可するように強制したり、既存の標準と互換性のある機能のみを有効にしたりすることができます。 この設定には、次のオプションがあります。

 - **default**

   現在のバージョンをターゲットにします。

- **ISO-1** と **ISO-2**

  それぞれ、標準機能の ISO-1 と ISO-2 をターゲットにします。

- **C# [バージョン番号]**

 特定のバージョンの C# をターゲットにします。 詳しくは、「[/langversion (C# コンパイラ オプション)](/dotnet/csharp/language-reference/compiler-options/langversion-compiler-option)」をご覧ください。


 **内部コンパイル エラー報告** コンパイラ エラーを Microsoft に報告するかどうかを指定します。 **prompt** (既定) に設定すると、内部コンパイラ エラーが発生した場合にプロンプトが表示され、エラー報告を電子的に Microsoft に送信するオプションが示されます。 **send** に設定すると、エラー報告は自動的に送信されます。 **queue** に設定すると、報告はキューに追加されます。 **none** に設定すると、エラーはコンパイラのテキスト出力にのみ報告されます。 詳しくは、「[/errorreport (C# コンパイラ オプション)](/dotnet/csharp/language-reference/compiler-options/errorreport-compiler-option)」をご覧ください。

 **演算のオーバーフローおよびアンダーフローのチェック** [checked](/dotnet/csharp/language-reference/keywords/checked) キーワードまたは [unchecked](/dotnet/csharp/language-reference/keywords/unchecked) キーワードのスコープ内に含まれない整数の算術ステートメントと、データ型の範囲外の値になる整数の算術ステートメントで、ランタイム例外が発生するかどうかを指定します。 詳しくは、「[/checked (C# コンパイラ オプション)](/dotnet/csharp/language-reference/compiler-options/checked-compiler-option)」をご覧ください。

 **mscorlib.dll を参照しない** <xref:System> 名前空間全体を定義して、mscorlib.dll をプログラムにインポートするかどうかを指定します。 独自の <xref:System> 名前空間およびオブジェクトを定義または作成する場合は、このチェック ボックスをオンにします。 詳しくは、「[/nostdlib (C# コンパイラ オプション)](/dotnet/csharp/language-reference/compiler-options/nostdlib-compiler-option)」をご覧ください。

## <a name="output"></a>出力

 次のオプションを使用すると、詳細な出力オプションを指定できます。

 **デバッグ情報**
 コンパイラによって生成されるデバッグ情報の種類を指定します。 アプリケーションのデバッグ パフォーマンスを構成する方法については、「[イメージのデバッグの簡略化](http://msdn.microsoft.com/Library/7d90ea7a-150f-4f97-98a7-f9c26541b9a3)」を参照してください。 この設定には、次のオプションがあります。

- **none**

  デバッグ情報を生成しないことを指定します。

- **full**

  実行中のプログラムにデバッガーをアタッチできるようにします。

- **pdbonly**

  プログラムがデバッガーで開始されたとき、ソース コードのデバッグが有効になりますが、実行中のプログラムがデバッガーにアタッチされているときにのみアセンブラーが表示されます。
- **ポータブル**

  プラットフォーム固有ではない、移植可能なシンボル ファイルである .PDB ファイルを生成します。このファイルは、他のツール、特にデバッガーに、主要な実行可能ファイルの内容やそれが作られた経緯に関する情報を提供します。 詳細については、「[ポータブル PDB](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md)」を参照してください。

- **埋め込み**

  ポータブル シンボル情報をアセンブリに埋め込みます。 外部 .PDB ファイルは作成されません。

詳しくは、「[/debug (C# コンパイラ オプション)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option)」をご覧ください。

**ファイルの配置** 出力ファイル内のセクションのサイズを指定します。 有効値は **512**、**1024**、**2048**、**4096**、および **8192** です。 これらの値の単位はバイトです。 各セクションは、この値の倍数である境界内にアラインされるので、出力ファイルのサイズに影響があります。 詳しくは、「[/filealign (C# コンパイラ オプション)](/dotnet/csharp/language-reference/compiler-options/filealign-compiler-option)」をご覧ください。

**ライブラリ ベース アドレス** DLL を読み込む位置に推奨されるベース アドレスを指定します。 DLL の既定のベース アドレスは、[!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] 共通言語ランタイムにより設定されます。 詳しくは、「[/baseaddress (C# コンパイラ オプション)](/dotnet/csharp/language-reference/compiler-options/baseaddress-compiler-option)」をご覧ください。

## <a name="see-also"></a>関連項目

 [C# コンパイラ オプション](/dotnet/csharp/language-reference/compiler-options/index)
 [[ビルド] ページ (プロジェクト デザイナー) (C#)](../../ide/reference/build-page-project-designer-csharp.md)
