---
title: Handle a concurrency exception | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- concurrency control, exceptions
- datasets [Visual Basic], errors
- exception handling, concurrency issues
- data concurrency, walkthroughs
- updating datasets, errors
- concurrency control, walkthroughs
ms.assetid: 73ee9759-0a90-48a9-bf7b-9d6fc17bff93
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: cca2a707627c36221a654cf8a06730383492f371
ms.openlocfilehash: 2108f18ae65e5ea5e6d12bcfc09aa1c5a1d3d4e3
ms.contentlocale: ja-jp
ms.lasthandoff: 09/13/2017

---
# <a name="handle-a-concurrency-exception"></a>Handle a concurrency exception
Concurrency exceptions (<xref:System.Data.DBConcurrencyException>) are raised when two users attempt to change the same data in a database at the same time. In this walkthrough, you create a Windows application that illustrates how to catch a <xref:System.Data.DBConcurrencyException>, locate the row that caused the error, and learn a strategy for how to handle it.  
  
 This walkthrough takes you through the following process:  
  
1.  Create a new **Windows Forms Application** project.  
  
2.  Create a new dataset based on the Northwind `Customers` table.  
  
3.  Create a form with a <xref:System.Windows.Forms.DataGridView> to display the data.  
  
4.  Fill a dataset with data from the `Customers` table in the Northwind database.  
  
5.  Use the [Visual Database Tools](http://msdn.microsoft.com/en-us/6b145922-2f00-47db-befc-bf351b4809a1) in Visual Studio to directly access the `Customers` data table and change a record.  
  
6.  Change the same record to a different value, update the dataset, and attempt to write the changes to the database, which results in a concurrency error being raised.  
  
7.  Catch the error, then display the different versions of the record, allowing the user to determine whether to continue and update the database, or to cancel the update.  
  
## <a name="prerequisites"></a>Prerequisites  
 In order to complete this walkthrough, you need:  
  
-   Access to the Northwind sample database with permission to perform updates. For more information, see [How to: Install Sample Databases](../data-tools/installing-database-systems-tools-and-samples.md).  
  
> [!NOTE]
>  The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or the edition that you're using. To change your settings, choose **Import and Export Settings** on the **Tools** menu. For more information, see [Personalize the Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="create-a-new-project"></a>Create a new project  
 You begin your walkthrough by creating a new Windows Forms application.  
  
#### <a name="to-create-a-new-windows-forms-application-project"></a>To create a new Windows Forms application project  
  
1. In Visual Studio, on the **File** menu, select **New**, **Project...**.  
  
2. Expand either **Visual C#** or **Visual Basic** in the left-hand pane, then select **Windows Classic Desktop**.  

3. In the middle pane, select the **Windows Forms App** project type.  

4. Name the project **ConcurrencyWalkthrough**, and then choose **OK**. 
  
     The **ConcurrencyWalkthrough** project is created and added to **Solution Explorer**, and a new form opens in the designer.  
  
## <a name="create-the-northwind-dataset"></a>Create the Northwind dataset  
 In this section, you create a dataset named `NorthwindDataSet`.  
  
#### <a name="to-create-the-northwinddataset"></a>To create the NorthwindDataSet  
  
1.  On the **Data** menu, choose **Add New Data source**.  
  
     The [Data Source Configuration Wizard](../data-tools/media/data-source-configuration-wizard.png) opens.  
  
2.  On the **Choose a Data Source Type** screen, select **Database**.  
  
3.  Select a connection to the Northwind sample database from the list of available connections. If the connection is not available in the list of connections, select **New Connection**  
  
    > [!NOTE]
    >  If you are connecting to a local database file, select **No** when asked if you would you like to add the file to your project.  
  
4.  On the **Save connection string to the application configuration file** screen, select **Next**.  
  
5.  Expand the **Tables** node and select the `Customers` table. The default name for the dataset should be `NorthwindDataSet`.  
  
6.  Select **Finish** to add the dataset to the project.  
  
## <a name="create-a-data-bound-datagridview-control"></a>Create a data-bound DataGridView control  
 In this section, you create a <xref:System.Windows.Forms.DataGridView> by dragging the **Customers** item from the **Data Sources** window onto your Windows Form.  
  
#### <a name="to-create-a-datagridview-control-that-is-bound-to-the-customers-table"></a>To create a DataGridView control that is bound to the Customers table  
  
1.  On the **Data** menu, choose **Show Data Sources** to open the **Data Sources Window**.  
  
2.  In the **Data Sources** window, expand the **NorthwindDataSet** node, and then select the **Customers** table.  
  
3.  Select the down arrow on the table node, and then select **DataGridView** in the drop-down list.  
  
4.  Drag the table onto an empty area of your form.  
  
     A <xref:System.Windows.Forms.DataGridView> control named `CustomersDataGridView` and a <xref:System.Windows.Forms.BindingNavigator> named `CustomersBindingNavigator` are added to the form that's bound to the <xref:System.Windows.Forms.BindingSource>.This, is in, is turn bound to the `Customers` table in the `NorthwindDataSet`.  
  
## <a name="test-the-form"></a>Test the form  
 You can now test the form to make sure it behaves as expected up to this point.  
  
#### <a name="to-test-the-form"></a>To test the form  
  
1.  Select **F5** to run the application  
  
     The form appears with a <xref:System.Windows.Forms.DataGridView> control on it that's filled with data from the `Customers` table.  
  
2.  On the **Debug** menu, select **Stop Debugging**.  
  
## <a name="handle-concurrency-errors"></a>Handle concurrency errors  
 How you handle errors depends on the specific business rules that govern your application. For this walkthrough, we use the following strategy as an example for how to handle the concurrency error.  
  
 The application presents the user with three versions of the record:  
  
-   The current record in the database  
  
-   The original record that's loaded into the dataset  
  
-   The proposed changes in the dataset  
  
The user is then able to either overwrite the database with the proposed version, or cancel the update and refresh the dataset with the new values from the database.  
  
#### <a name="to-enable-the-handling-of-concurrency-errors"></a>To enable the handling of concurrency errors  
  
1.  Create a custom error handler.  
  
2.  Display choices to the user.  
  
3.  Process the user's response.  
  
4.  Resend the update, or reset the data in the dataset.  
  
### <a name="add-code-to-handle-the-concurrency-exception"></a>Add code to handle the concurrency exception  
 When you attempt to perform an update and an exception gets raised, you generally want to do something with the information that's provided by the raised exception.  
  
 In this section, you add code that  attempts to update the database. You also handle any <xref:System.Data.DBConcurrencyException> that might get raised, as well as any other exceptions.  
  
> [!NOTE]
>  The `CreateMessage` and `ProcessDialogResults` methods will be added later in this walkthrough.  
  
##### <a name="to-add-error-handling-for-the-concurrency-error"></a>To add error handling for the concurrency error  
  
1.  Add the following code below the `Form1_Load` method:  
  
     [!code-csharp[VbRaddataConcurrency#1](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_1.cs)]
     [!code-vb[VbRaddataConcurrency#1](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_1.vb)]  
  
2.  Replace the `CustomersBindingNavigatorSaveItem_Click` method to call the `UpdateDatabase` method so it looks like the following:  
  
     [!code-csharp[VbRaddataConcurrency#2](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_2.cs)]
     [!code-vb[VbRaddataConcurrency#2](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_2.vb)]  
  
### <a name="display-choices-to-the-user"></a>Display choices to the user  
 The code you just wrote calls the `CreateMessage` procedure to display error information to the user. For this walkthrough, you use a message box to display the different versions of the record to the user. This enables the user to choose whether to overwrite the record with the changes or cancel the edit. Once the user selects an option (clicks a button) on the message box, the response is passed to the `ProcessDialogResult` method.  
  
##### <a name="to-create-the-message-to-display-to-the-user"></a>To create the message to display to the user  
  
-   Create the message by adding the following code to the **Code Editor**. Enter this code below the `UpdateDatabase` method.  
  
     [!code-csharp[VbRaddataConcurrency#4](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_3.cs)]
     [!code-vb[VbRaddataConcurrency#4](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_3.vb)]  
  
### <a name="process-the-users-response"></a>Process the user's response  
 You also need code to process the user's response to the message box. The options are either to overwrite the current record in the database with the proposed change, or abandon the local changes and refresh the data table with the record that's currently in the database. If the user chooses yes, the <xref:System.Data.DataTable.Merge%2A> method is called with the *preserveChanges* argument set to `true`. This causes the update attempt to be successful, because the original version of the record now matches the record in the database.  
  
##### <a name="to-process-the-user-input-from-the-message-box"></a>To process the user input from the message box  
  
-   Add the following code below the code that was added in the previous section.  
  
     [!code-csharp[VbRaddataConcurrency#3](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_4.cs)]
     [!code-vb[VbRaddataConcurrency#3](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_4.vb)]  
  
## <a name="test-the-form"></a>Test the form  
 You can now test the form to make sure it behaves as expected. To simulate a concurrency violation you need to change data in the database after filling the NorthwindDataSet.  
  
#### <a name="to-test-the-form"></a>To test the form  
  
1.  Select **F5** to run the application.  
  
2.  After the form appears, leave it running and switch to the Visual Studio IDE.  
  
3.  On the **View** menu, choose **Server Explorer**.  
  
4.  In **Server Explorer**, expand the connection your application is using, and then expand the **Tables** node.  
  
5.  Right-click the **Customers** table, and then select **Show Table Data**.  
  
6.  In the first record (`ALFKI`) change `ContactName` to `Maria Anders2`.  
  
    > [!NOTE]
    >  Navigate to a different row to commit the change.  
  
7.  Switch to the `ConcurrencyWalkthrough`'s running form.  
  
8.  In the first record on the form (`ALFKI`), change`ContactName` to `Maria Anders1`.  
  
9. Select the **Save** button.  
  
     The concurrency error is raised, and the message box appears.  
  
10. Selecting **No** cancels the update and updates the dataset with the values that are currently in the database. Selecting **Yes** writes the proposed value to the database.  
  
## <a name="see-also"></a>See Also  
 [Save data back to the database](../data-tools/save-data-back-to-the-database.md)
