---
title: データベースに新しいレコードを挿入 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- TableAdapters, inserting new records into
- data [Visual Studio], saving
- databases, inserting new records into
- records, inserting
- saving data
ms.assetid: ea118fff-69b1-4675-b79a-e33374377f04
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e9613d154cd0d9bb307fbde6d7255a8f1ecce000
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49891480"
---
# <a name="insert-new-records-into-a-database"></a>データベースに新しいレコードを挿入する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
使用することができますをデータベースに新しいレコードを挿入するのには、`TableAdapter.Update`メソッド、または TableAdapter の DBDirect メソッドのいずれか (具体的には、`TableAdapter.Insert`メソッド)。 詳細については、「 [TableAdapter Overview](../data-tools/tableadapter-overview.md)」を参照してください。  
  
 アプリケーションでは、Tableadapter を使用しない場合は、コマンド オブジェクトを使用することができます (たとえば、 <xref:System.Data.SqlClient.SqlCommand>)、データベースに新しいレコードを挿入します。  
  
 アプリケーションでは、データを格納するデータセットを使用する場合は、使用、`TableAdapter.Update`メソッド。 `Update`メソッドは、データベースにすべての変更 (更新、挿入、および削除) を送信します。  
  
 アプリケーションがデータを格納または使用して、データベースに新しいレコードの作成をより細かく制御する場合にオブジェクトを使用するかどうか、`TableAdapter.Insert`メソッド。  
  
 TableAdapter を持っていない場合、`Insert`メソッド、TableAdapter のいずれかがストアド プロシージャを使用して構成されていることを意味またはその`GenerateDBDirectMethods`プロパティに設定されて`false`します。 TableAdapter を設定してみてください`GenerateDBDirectMethods`プロパティを`true`内から、[データセット デザイナー](../data-tools/creating-and-editing-typed-datasets.md)、データセットを保存します。 これには、TableAdapter が再生成します。 TableAdapter がまだない場合、`Insert`個々 の行を区別するために十分なスキーマはおそらくは行いませんメソッドでは、次の表に、(たとえば、ある可能性がありますいないテーブルに主キーのセット)。  
  
## <a name="insert-new-records-by-using-tableadapters"></a>Tableadapter を使用して新しいレコードを挿入します。  
 Tableadapter では、アプリケーションの要件に応じて、データベースに新しいレコードを挿入するさまざまな方法を提供します。  
  
 アプリケーション データを格納するデータセットを使用する場合に必要なだけ新しいレコードを追加できます<xref:System.Data.DataTable>データセット、および次の呼び出しで、`TableAdapter.Update`メソッド。 `TableAdapter.Update`ですべての変更を送信するメソッド、 <xref:System.Data.DataTable> (変更および削除されたレコードを含む)、データベースにします。  
  
#### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterupdate-method"></a>TableAdapter.Update メソッドを使用して、データベースに新しいレコードを挿入するには  
  
1. 新しいレコードの追加に必要な<xref:System.Data.DataTable>新しい<xref:System.Data.DataRow>に追加することと、<xref:System.Data.DataTable.Rows%2A>コレクション。 詳細については、次を参照してください。[方法: DataTable に行の追加](http://msdn.microsoft.com/library/78ebbb43-c402-49cf-81da-0715289487bf)します。  
  
2. 新しい行を追加した後、<xref:System.Data.DataTable>を呼び出し、`TableAdapter.Update`メソッド。 全体のいずれかで渡すことで更新するデータの量を制御できます<xref:System.Data.DataSet>、 <xref:System.Data.DataTable>、配列の<xref:System.Data.DataRow>、または 1 つ<xref:System.Data.DataRow>します。  
  
    次のコードは新しいレコードを追加する方法、<xref:System.Data.DataTable>を呼び出して、`TableAdapter.Update`を新しい行をデータベースに保存するメソッド。 (この例では、 `Region` Northwind データベースのテーブルです)。  
  
    [!code-csharp[VbRaddataSaving#14](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form5.cs#14)]
    [!code-vb[VbRaddataSaving#14](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form5.vb#14)]  
  
   アプリケーションでは、データを格納するオブジェクトを使用する場合は使用できます、`TableAdapter.Insert`メソッドを直接データベースに新しい行を作成します。 `Insert`メソッドはパラメーターとして各列の値を受け取ります。 メソッドを呼び出すことで渡されたパラメーター値をデータベースに新しいレコードを挿入します。  
  
   次の手順を使用して、`Region`例として、Northwind データベースのテーブル。  
  
#### <a name="to-insert-new-records-into-a-database-by-using-the-tableadapterinsert-method"></a>TableAdapter.Insert メソッドを使用して、データベースに新しいレコードを挿入するには  
  
-   呼び出す TableAdapter の`Insert`メソッド、パラメーターとして各列の値で渡します。  
  
    > [!NOTE]
    >  使用可能なインスタンスがいない場合に使用する TableAdapter をインスタンス化します。  
  
     [!code-csharp[VbRaddataSaving#15](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#15)]
     [!code-vb[VbRaddataSaving#15](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#15)]  
  
## <a name="insert-new-records-by-using-command-objects"></a>コマンド オブジェクトを使用して新しいレコードを挿入します。  
 次の例では、コマンド オブジェクトを使用してデータベースに直接新しいレコードを挿入します。 コマンド オブジェクトを使用して、コマンドやストアド プロシージャを実行する方法の詳細については、次を参照してください。[アプリケーションへのデータのフェッチ](../data-tools/fetching-data-into-your-application.md)します。  
  
 次の手順を使用して、`Region`例として、Northwind データベースのテーブル。  
  
#### <a name="to-insert-new-records-into-a-database-by-using-command-objects"></a>コマンド オブジェクトを使用して、データベースに新しいレコードを挿入するには  
  
-   新しいコマンド オブジェクトを作成し、設定、 `Connection`、 `CommandType`、および`CommandText`プロパティ。  
  
     [!code-csharp[VbRaddataSaving#16](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#16)]
     [!code-vb[VbRaddataSaving#16](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#16)]  
  
## <a name="net-framework-security"></a>.NET Framework セキュリティ  
 データベースに接続しようとするいると、目的のテーブルに挿入を実行するアクセス許可へのアクセスが必要です。  
  
## <a name="see-also"></a>関連項目  
 [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)

