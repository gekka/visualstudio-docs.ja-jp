---
title: '方法: データベースからデータをワークシートに読み込む'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets [Office development in Visual Studio], populating
- databases [Office development in Visual Studio], populating worksheets
- data [Office development in Visual Studio], adding to worksheets
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 25e73eaa3cdd0655a51711ddd30996915f984213
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758470"
---
# <a name="how-to-populate-worksheets-with-data-from-a-database"></a>方法: データベースからデータをワークシートに読み込む

Windows フォーム プロジェクトでのデータにアクセスするのと同じ方法でドキュメント レベルの Office プロジェクトでのデータにアクセスすることができます。 同じツールとコードを使用してソリューションにデータを取り込むことができ、Windows フォーム コントロールを使用してデータを表示できます。 さらに、利用では、ホスト コントロールは、イベントとデータ バインディング機能による機能強化された Microsoft Office Excel でのネイティブのオブジェクトと呼ばれるようです。 詳細については、次を参照してください。[ホスト項目とホスト コントロールの概要](../vsto/host-items-and-host-controls-overview.md)します。

[!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

次の例は、デザイナーを使用してドキュメント レベルのプロジェクトにデータ バインド コントロールを追加する方法を示しています。 アプリケーション レベルのプロジェクトの実行時にデータ バインド コントロールを追加する方法の例は、次を参照してください。[チュートリアル: VSTO アドイン プロジェクトで複雑なデータ バインディング](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md)します。

![ビデオへのリンク](../vsto/media/playvideo.gif "ビデオへのリンク")関連するビデオ デモについては、次を参照してください。[を Excel ワークシートにデータの操作の転送を操作する方法でしょうか。](http://go.microsoft.com/fwlink/?LinkID=130277)、および[Excel でデータベースの操作を使用するデータを操作する方法でしょうか。](http://go.microsoft.com/fwlink/?LinkID=130287)します。

## <a name="add-a-data-bound-control-to-a-worksheet-at-design-time"></a>デザイン時にデータ バインド コントロールをワークシートに追加します。

### <a name="to-populate-a-worksheet-with-data-from-a-database"></a>ワークシートに、データベースからデータを設定するには

1.  デザイナーでワークシートを開き、Visual Studio で、Excel のドキュメント レベルのプロジェクトを開きます。

2.  **[データ ソース]** ウィンドウを開いて、プロジェクトのデータ ソースを作成します。 詳細については、次を参照してください。[新しい接続を追加](../data-tools/add-new-connections.md)します。

3.  フィールドまたはから使用テーブルをドラッグして、**データソース**をワークシートにウィンドウ。

次のコントロールの 1 つは、ワークシートに作成されます。

-   フィールドをドラッグする場合、<xref:Microsoft.Office.Tools.Excel.NamedRange>コントロールがワークシートに作成します。 詳細については、次を参照してください。 [NamedRange コントロール](../vsto/namedrange-control.md)します。

-   テーブルをドラッグする場合、<xref:Microsoft.Office.Tools.Excel.ListObject>コントロールがワークシートに作成します。 詳細については、次を参照してください。 [ListObject コントロール](../vsto/listobject-control.md)します。

テーブルを選択して、別のコントロールを追加したり、フィールドに、**データソース**ウィンドウとドロップダウン リストから別のコントロールを選択します。

## <a name="objects-in-the-project"></a>プロジェクト内のオブジェクト

プロジェクトには、コントロールに加えて、データに関連する以下のオブジェクトも自動的に追加されます。

-   データベース内の接続したデータ テーブルをカプセル化する型指定されたデータセット。 詳細については、次を参照してください。 [Visual Studio でのデータセット ツール](/visualstudio/data-tools/dataset-tools-in-visual-studio)します。

-   コントロールを型指定されたデータセットに接続する <xref:System.Windows.Forms.BindingSource>。 詳細については、次を参照してください。 [BindingSource コンポーネントの概要](/dotnet/framework/winforms/controls/bindingsource-component-overview)します。

-   型指定されたデータセットをデータベースに接続する TableAdapter。 詳細については、次を参照してください。 [TableAdapter の概要](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview)します。

-   階層更新を有効にするデータセット内のテーブル アダプターを調整するために使用 TableAdapterManager します。 詳細については、次を参照してください。[階層更新](../data-tools/hierarchical-update.md)と[TableAdapterManager 参照](../data-tools/fill-datasets-by-using-tableadapters.md#tableadaptermanager-reference)します。

プロジェクトを実行すると、データ ソースの先頭のレコードがコントロールに表示されます。 <xref:System.Windows.Forms.BindingSource> を使用すると、ユーザーがレコードをスクロールできるようになります。

### <a name="to-scroll-through-the-records"></a>レコードをスクロールするには

-   <xref:System.Windows.Forms.BindingSource.MoveNext%2A> や <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> など、<xref:System.Windows.Forms.BindingSource> のメソッドを使用します。

型指定されたデータセットと、データベースに更新プログラムを送信する方法については、次を参照してください。[方法: ホスト コントロールからのデータでデータ ソースを更新](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)します。

## <a name="see-also"></a>関連項目

- [Office ソリューションでのコントロールにデータをバインドします。](../vsto/binding-data-to-controls-in-office-solutions.md)
- [新しいデータ ソースの追加](../data-tools/add-new-data-sources.md)
- [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [方法: オブジェクトからのデータをドキュメントに読み込む](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [方法: データベースからデータをドキュメントに読み込む](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [方法: データ サービスからドキュメントに読み込む](../vsto/how-to-populate-documents-with-data-from-services.md)
- [方法: ホスト コントロールからのデータでデータ ソースを更新](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Excel のワークシートにデータの操作の転送を操作する方法](http://go.microsoft.com/fwlink/?LinkID=130277)
- [Excel でデータベースの操作を使用するデータを操作する方法](http://go.microsoft.com/fwlink/?LinkID=130287)