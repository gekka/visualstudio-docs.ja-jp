---
title: Receive アクティビティ デザイナー |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Receive.UI
ms.assetid: f58d3c70-944d-4bb4-90a7-e68c103caddc
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: f285a2d900c4f286435e4e06c4db15967f1d7aab
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "47538818"
---
# <a name="receive-activity-designer"></a>Receive アクティビティ デザイナー
**受信**作成および構成するアクティビティ デザイナーが使用される、<xref:System.ServiceModel.Activities.Receive>アクティビティ。 <xref:System.ServiceModel.Activities.Receive> アクティビティは、メッセージ (<xref:System.ServiceModel.Channels.Message>、<xref:System.IO.Stream>、<xref:System.Xml.Linq.XElement> などの組み込みの型、アプリケーション定義のデータ コントラクト、メッセージ コントラクト、またはシリアル化可能な XML クラス) を受信するアクティビティです。  
  
## <a name="the-receive-activity"></a>Receive アクティビティ  
 <xref:System.ServiceModel.Activities.Receive> アクティビティでは、使用されている受信コンテンツの型に応じて、単一または複数のアイテムを受信できます。 <xref:System.ServiceModel.Activities.SendReply> アクティビティは、サービスでの要求/応答メッセージ交換パターンの一部としてメッセージを受信する <xref:System.ServiceModel.Activities.Receive> アクティビティにバインドできます。  
  
### <a name="using-the-receive-activity-designer"></a>Receive アクティビティ デザイナーの使用  
 **受信**アクティビティ デザイナーが記載されて、**メッセージング**のカテゴリ、**ツールボックス**をクリックしてアクセスする、**ツールボックス** タブで、 [!INCLUDE[wfd2](../includes/wfd2-md.md)] (または、選択**ツールバー**から、**ビュー**メニューまたは CTRL + ALT + X)。  
  
 **受信**からアクティビティ デザイナーをドラッグすることができます、**ツールボックス**ドロップ、[!INCLUDE[wfd2](../includes/wfd2-md.md)]サーフェス場所でアクティビティを通常配置しています。 この操作により、Receive という既定の <xref:System.ServiceModel.Activities.Receive> を持つ <xref:System.Activities.Activity.DisplayName%2A> アクティビティが作成されます。 <xref:System.Activities.Activity.DisplayName%2A>のヘッダーで編集できる、**受信**アクティビティ デザイナーまたは、 **DisplayName**プロパティ グリッドのボックスです。  
  
 作成する、<xref:System.ServiceModel.Activities.SendReply>アクティビティに、選択したバインドと<xref:System.ServiceModel.Activities.Receive>アクティビティを右クリックし、**受信**アクティビティ デザイナー、 をクリックして、 **SendReply の作成**コンテキスト メニューの項目、**SendReplyToReceive**下デザイナーに表示されます、**受信**デザイナー。 <xref:System.ServiceModel.Activities.SendReply> アクティビティは、サービスでの要求/応答メッセージ交換パターンの一部として応答メッセージを送信するアクティビティであり、 構成できますが、 **SendReplyToReceive**デザイナー。  
  
 または、 **ReceiveAndSendReply**テンプレート デザイナーで、**メッセージング**のカテゴリ、**ツールボックス**の事前構成済みのペアを作成するために使用する<xref:System.ServiceModel.Activities.Receive>と<xref:System.ServiceModel.Activities.SendReply>アクティビティ。 [!INCLUDE[crabout](../includes/crabout-md.md)] 使用、 **ReceiveAndSendReply**と**SendReplyToReceive**テンプレートを参照してください、 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)トピック。  
  
### <a name="the-receive-activity-properties"></a>Receive アクティビティのプロパティ  
 次の表に、<xref:System.ServiceModel.Activities.Receive> のプロパティと、デザイナーでのその使用方法を示します。 これらのプロパティは、プロパティ グリッドまたは[!INCLUDE[wfd2](../includes/wfd2-md.md)]画面で編集できます。 必須のプロパティは <xref:System.ServiceModel.Activities.Receive.OperationName%2A> プロパティのみです。  
  
|プロパティ名|必須|使用方法|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.ServiceModel.Activities.Receive> アクティビティの表示名を指定します。 既定値は Receive です。<br /><br /> 既定値以外の <xref:System.Activities.Activity.DisplayName%2A> の使用は必須ではありませんが、使用することをお勧めします。|  
|<xref:System.ServiceModel.Activities.Receive.OperationName%2A>|True|この <xref:System.ServiceModel.Activities.Receive> アクティビティによって実装されるサービス操作の名前を指定します。 このプロパティを使用して構築の既定値を**アクション**プロパティ場合、**アクション**プロパティが明示的に設定されていません。|  
|<xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>|False|サービス コントラクトの名前を指定します。 このプロパティは、サービス操作を個々のサービス コントラクトにグループ化するために使用します。 同じ <xref:System.ServiceModel.Activities.Receive> を持つすべての <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> アクティビティは、同じサービス コントラクト (WSDL ポートの種類) にグループ化されます。 既定値は、トップ レベル (ルート) アクティビティの完全修飾 CLR 名です。|  
|<xref:System.ServiceModel.Activities.Receive.Content%2A>|False|受信するメッセージまたはパラメーターの内容を指定します。 <xref:System.ServiceModel.Activities.ReceiveMessageContent> アクティビティまたは <xref:System.ServiceModel.Activities.ReceiveParametersContent> アクティビティを指定できます。 このプロパティの横にある省略記号ボタンをクリックして編集、**コンテンツ**フィールドにプロパティ グリッドまたはをクリックすると、**を定義する.** ボタンの横にある、**コンテンツ**のラベルを**受信**アクティビティ デザイナー画面。 両方を表示、**コンテンツ定義**ダイアログ。 [!INCLUDE[crabout](../includes/crabout-md.md)] このボックスを使用して、表示する方法、[コンテンツ定義 ダイアログ ボックス](../workflow-designer/content-definition-dialog-box.md)トピック。|  
|<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>|False|<xref:System.ServiceModel.Activities.Receive> オブジェクトを持つワークフローのサービス操作における <xref:System.ServiceModel.MessageQuerySet> アクティビティ間の相関関係を指定します。 横にある省略記号ボタンをクリックして、<xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>プロパティを開く [プロパティ] グリッドで、 **[CorrelatesOn の定義**] ダイアログ ボックス。 [!INCLUDE[crabout](../includes/crabout-md.md)] このダイアログ ボックスの使用を参照してください、[コンテンツ定義 ダイアログ ボックス](../workflow-designer/content-definition-dialog-box.md)トピック。|  
|<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A>|False|適切なワークフロー インスタンスにメッセージをルーティングするために使用される <xref:System.ServiceModel.Activities.CorrelationHandle> を指定します。<br /><br /> 横にある省略記号ボタンをクリックして、<xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A>プロパティを開く プロパティ グリッドで、**式エディター**  ダイアログ ボックス。 [!INCLUDE[crabout](../includes/crabout-md.md)] このダイアログ ボックスの使用を参照してください、[方法: 式エディターを使用して](../workflow-designer/how-to-use-the-expression-editor.md)トピック。|  
|<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>|False|ワークフロー内のこの <xref:System.ServiceModel.Activities.CorrelationInitializer> アクティビティを構成する複数の <xref:System.ServiceModel.Activities.CorrelationHandle> オブジェクトを初期化する <xref:System.ServiceModel.Activities.Receive> オブジェクトのコレクションを指定します。 横にある省略記号ボタンをクリックして、<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>プロパティを開く [プロパティ] グリッドで、 **[関連付け初期化子**] ダイアログ ボックス。 [!INCLUDE[crabout](../includes/crabout-md.md)] このボックスを使用して参照してください、[関連付け初期化子の追加 ダイアログ ボックス](../workflow-designer/add-correlationinitializers-dialog-box.md)トピック。|  
|<xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A>|False|メッセージが既存のワークフロー インスタンスと関連付けられていない場合に、新しいワークフロー インスタンスを作成して、このメッセージを処理するかどうかを決定する値を指定します。 値が設定されている場合**true**メッセージが既存のワークフロー インスタンスに関連付けられていない場合は、メッセージを処理する新しいワークフロー インスタンスが作成されます。|  
|<xref:System.ServiceModel.Activities.Receive.KnownTypes%2A>|False|この <xref:System.ServiceModel.Activities.Receive> アクティビティによって実装されるサービス操作の既知の型のコレクションを指定します。 このプロパティは、<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> に設定された <xref:System.Runtime.Serialization.DataContractSerializer> プロパティと共に使用する必要があり、 <xref:System.Xml.Serialization.XmlSerializer> が使用されている場合は無視されます。<br /><br /> 横にある省略記号ボタンをクリックして、 **KnownTypes**プロパティ グリッドでフィールド、**型コレクション エディター**  ダイアログ ボックスの関連する型を追加できます。 [!INCLUDE[crabout](../includes/crabout-md.md)] このボックスを使用して参照してください、[型コレクション エディター ダイアログ ボックス](../workflow-designer/type-collection-editor-dialog-box.md)トピック。|  
|<xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A>|False|メッセージの <xref:System.Net.Security.ProtectionLevel> を指定します。<br /><br /> 1。<xref:System.Net.Security.ProtectionLevel>認証のみを意味します。<br />2。<xref:System.Net.Security.ProtectionLevel>署名データ送信されるデータの整合性を確保することを意味します。<br />3。<xref:System.Net.Security.ProtectionLevel>手段の暗号化と機密性と送信されるデータの整合性を確保するデータに署名します。|  
|<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>|False|<xref:System.ServiceModel.Activities.Receive> アクティビティによって実装されるサービス操作に使用するシリアライザーの型を指定します。 既定値は <xref:System.Runtime.Serialization.DataContractSerializer> です。この場合、ある型のインスタンスが、提供されたデータ コントラクトを使用する XML ストリームまたはドキュメントへとシリアル化または逆シリアル化されます。 XML をより厳密に制御する必要がある場合は、<xref:System.Xml.Serialization.XmlSerializer> も使用できます。|  
|<xref:System.ServiceModel.Activities.Receive.Action%2A>|False|メッセージのアクション ヘッダーを指定します。 明示的に設定されていない場合、既定の値:https://tempuri.org/{serviceコントラクトの名前空間} サービス コントラクト名}/操作 {name} です。|  
  
## <a name="see-also"></a>関連項目  
 [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)   
 [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)   
 [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)   
 [送信](../workflow-designer/send-activity-designer.md)   
 [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)   
 [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)