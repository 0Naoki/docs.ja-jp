---
title: コントラクト優先ワークフロー サービスの開発
ms.date: 03/30/2017
ms.assetid: e5dbaa7b-005f-4330-848d-58ac4f42f093
ms.openlocfilehash: 10129fcb40d86d1ca7e42bce68b072e9118bcc88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="contract-first-workflow-service-development"></a>コントラクト優先ワークフロー サービスの開発
以降で[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]、Windows Workflow Foundation (WF) 機能のコントラクト優先ワークフローの開発という形で web サービスとワークフローの間の統合が向上しています。 コントラクト優先ワークフローの開発ツールでは、コードのコントラクトを先に設計できます。 その後、ツールボックス内に、コントラクト内の操作用のアクティビティ テンプレートが自動的に生成されます。 このトピックでは、ワークフロー サービスのアクティビティおよびプロパティをサービス コントラクトの属性にマップする方法の概要について説明します。 コントラクト優先ワークフロー サービスを作成する例については、次を参照してください。[する方法: 既存のサービス コントラクトを使用するワークフロー サービスを作成する](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)です。  
  
## <a name="in-this-topic"></a>このトピックの内容  
  
-   [ワークフロー属性へのサービス コントラクト属性のマッピング](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MappingAttributes)  
  
    -   [サービス コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
    -   [操作コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
    -   [メッセージ コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
    -   [データ コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
    -   [エラー コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
-   [その他のサポートと実装情報](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#AdditionalSupport)  
  
    -   [サポートされていないサービス コントラクト機能](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
    -   [構成済みのメッセージング アクティビティの生成](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
##  <a name="MappingAttributes"></a> ワークフロー属性へのサービス コントラクト属性のマッピング  
 次のセクションにある表では、さまざまな WCF 属性およびプロパティを示し、それらをコントラクト優先ワークフローのメッセージング アクティビティおよびプロパティにマップする方法について説明します。  
  
-   [サービス コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ServiceContract)  
  
-   [操作コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#OperationContract)  
  
-   [メッセージ コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#MessageContract)  
  
-   [データ コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#DataContract)  
  
-   [エラー コントラクト属性](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#FaultContract)  
  
###  <a name="ServiceContract"></a> サービス コントラクト属性  
  
|プロパティ名|サポート状況|説明|WF の検証|  
|-------------------|---------------|-----------------|-------------------|  
|CallbackContract|Ｘ|コントラクトが双方向コントラクトの場合のコールバック コントラクトの型を取得または設定します。|(なし)|  
|ConfigurationName|Ｘ|アプリケーション構成ファイル内でサービスを検索するために使用される名前を取得または設定します。|(なし)|  
|HasProtectionLevel|はい|メンバーに保護レベルが割り当てられているかどうかを示す値を取得します。|Receive.ProtectionLevel を null にすることはできません。|  
|名前|[はい]|取得または設定の名前、 \<portType > Web サービス記述言語 (WSDL) 要素です。|Receive.ServiceContractName.LocalName が一致している必要があります。|  
|Namespace|[はい]|取得または設定の名前空間、 \<portType > Web サービス記述言語 (WSDL) 要素です。|Receive.ServiceContractName.NameSpace が一致している必要があります。|  
|ProtectionLevel|はい|コントラクトのバインドで、ProtectionLevel プロパティの値をサポートする必要があるかどうかを指定します。|Receive.ProtectionLevel が一致している必要があります。|  
|SessionMode|Ｘ|セッションが許可されるか、許可されないか、または必要であるかを示す値を取得または設定します。|(なし)|  
|TypeId|Ｘ|派生クラスで実装すると、この属性の一意の識別子を取得します  (属性から継承)。|(なし)|  
  
 ここにサブセクションの本文を挿入します。  
  
###  <a name="OperationContract"></a> 操作コントラクト属性  
  
|プロパティ名|サポート状況|説明|WF の検証|  
|-------------------|---------------|-----------------|-------------------|  
|動作|はい|要求メッセージの WS-Addressing アクションを取得または設定します。|Receive.Action が一致している必要があります。|  
|AsyncPattern|×|非同期的に、Begin を使用して、操作を実装することを示す\<methodName > と終了\<methodName > メソッドのペアをサービス コントラクトでします。|(なし)|  
|HasProtectionLevel|はい|この操作のメッセージの暗号化、署名、または両方が必要かどうかを示す値を取得または設定します。|Receive.ProtectionLevel を null にすることはできません。|  
|IsInitiating|Ｘ|メソッドが (セッションが存在する場合に) サーバー上でセッションを開始できる操作を実装するかどうかを示す値を取得または設定します。|(なし)|  
|IsOneWay|はい|操作が応答メッセージを返すかどうかを示す値を取得または設定します。|(この Receive の SendReply またはこの Send の ReceiveReply がありません。)|  
|IsTerminating|Ｘ|応答メッセージが存在する場合に、そのメッセージの送信後にセッションを終了するようにサービス操作がサーバーに指示するかどうかを示す値を取得または設定します。|(なし)|  
|名前|はい|操作の名前を取得または設定します。|Receive.OperationName が一致している必要があります。|  
|ProtectionLevel|はい|操作のメッセージの暗号化、署名、または両方が必要かどうかを示す値を取得または設定します。|Receive.ProtectionLevel が一致している必要があります。|  
|ReplyAction|はい|操作の応答メッセージの SOAP アクションの値を取得または設定します。|SendReply.Action が一致している必要があります。|  
|TypeId|Ｘ|派生クラスで実装すると、この属性の一意の識別子を取得します  (属性から継承)。|(なし)|  
  
###  <a name="MessageContract"></a> メッセージ コントラクト属性  
  
|プロパティ名|サポート状況|説明|WF の検証|  
|-------------------|---------------|-----------------|-------------------|  
|HasProtectionLevel|はい|メッセージに保護レベルが割り当てられているかどうかを示す値を取得します。|検証なし (Receive.Content と SendReply.Content がメッセージ コントラクト型と一致している必要があります)。|  
|IsWrapped|はい|メッセージ本文にラッパー要素があるかどうかを指定する値を取得または設定します。|検証なし (Receive.Content と Sendreply.Content がメッセージ コントラクト型と一致している必要があります)。|  
|ProtectionLevel|Ｘ|メッセージの暗号化、署名、または両方が必要かどうかを指定する値を取得または設定します。|(なし)|  
|TypeId|はい|派生クラスで実装すると、この属性の一意の識別子を取得します  (属性から継承)。|検証なし (Receive.Content と SendReply.Content がメッセージ コントラクト型と一致している必要があります)。|  
|WrapperName|はい|メッセージ本文のラッパー要素の名前を取得または設定します。|検証なし (Receive.Content と SendReply.Content がメッセージ コントラクト型と一致している必要があります)。|  
|WrapperNamespace|Ｘ|メッセージ本文のラッパー要素の名前空間を取得または設定します。|(なし)|  
  
###  <a name="DataContract"></a> データ コントラクト属性  
  
|プロパティ名|サポート状況|説明|WF の検証|  
|-------------------|---------------|-----------------|-------------------|  
|IsReference|Ｘ|オブジェクト参照データを保持するかどうかを示す値を取得または設定します。|(なし)|  
|名前|はい|型のデータ コントラクトの名前を取得または設定します。|検証なし (Receive.Content と SendReply.Content がメッセージ コントラクト型と一致している必要があります)。|  
|Namespace|はい|型のデータ コントラクトの名前空間を取得または設定します。|検証なし (Receive.Content と SendReply.Content がメッセージ コントラクト型と一致している必要があります)。|  
|TypeId|Ｘ|派生クラスで実装すると、この属性の一意の識別子を取得します  (属性から継承)。|(なし)|  
  
###  <a name="FaultContract"></a> エラー コントラクト属性  
  
|プロパティ名|サポート状況|説明|WF の検証|  
|-------------------|---------------|-----------------|-------------------|  
|動作|はい|操作コントラクトの一部として指定された SOAP エラー メッセージのアクションを取得または設定します。|SendReply.Action が一致している必要があります。|  
|DetailType|はい|エラー情報を含むシリアル化可能なオブジェクトの型を取得します。|SendReply.Content が型と一致している必要があります。|  
|HasProtectionLevel|Ｘ|SOAP エラー メッセージに保護レベルが割り当てられているかどうかを示す値を取得します。|(なし)|  
|名前|Ｘ|Web サービス記述言語 (WSDL) でのエラー メッセージの名前を取得または設定します。|(なし)|  
|Namespace|Ｘ|SOAP エラーの名前空間を取得または設定します。|(なし)|  
|ProtectionLevel|Ｘ|SOAP エラーがバインドに要求する保護レベルを指定します。|(なし)|  
|TypeId|Ｘ|派生クラスで実装すると、この属性の一意の識別子を取得します  (属性から継承)。|(なし)|  
  
##  <a name="AdditionalSupport"></a> その他のサポートと実装情報  
  
-   [サポートされていないサービス コントラクト機能](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#UnsupportedFeatures)  
  
-   [構成済みのメッセージング アクティビティの生成](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md#ActivityGeneration)  
  
###  <a name="UnsupportedFeatures"></a> サポートされていないサービス コントラクト機能  
  
-   コントラクトでの TPL (タスク並列ライブラリ) タスクの使用はサポートされていません。  
  
-   サービス コントラクトの継承はサポートされていません。  
  
###  <a name="ActivityGeneration"></a> 構成済みのメッセージング アクティビティの生成  
 コントラクト優先ワークフロー サービスを使用する場合に事前構成されたメッセージ アクティビティの生成をサポートするために、2 つのパブリック静的メソッドが <xref:System.ServiceModel.Activities.Receive> アクティビティと <xref:System.ServiceModel.Activities.SendReply> アクティビティに追加されています。  
  
-   <xref:System.ServiceModel.Activities.Receive.FromOperationDescription%2A?displayProperty=nameWithType>  
  
-   <xref:System.ServiceModel.Activities.SendReply.FromOperationDescription%2A?displayProperty=nameWithType>  
  
 これらのメソッドによって生成されたアクティビティはコントラクト検証に合格する必要があるため、これらのメソッドは <xref:System.ServiceModel.Activities.Receive> および <xref:System.ServiceModel.Activities.SendReply> の検証ロジックの一部として内部で使用されます。 <xref:System.ServiceModel.Activities.Receive.OperationName%2A>、<xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>、<xref:System.ServiceModel.Activities.Receive.Action%2A>、<xref:System.ServiceModel.Activities.Receive.SerializerOption%2A>、<xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A>、および <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> はすべて、インポートされたコントラクトに一致するよう事前に構成されています。 ワークフロー デザイナーでアクティビティのコンテンツのプロパティ ページで、**メッセージ**または**パラメーター**のセクションでは、コントラクトに一致するよう構成されてもします。  
  
 WCF エラー コントラクトは、個別のセットを返すことによっても処理が構成されている<xref:System.ServiceModel.Activities.SendReply>ごとに表示されるエラーのアクティビティ、 <xref:System.ServiceModel.Description.OperationDescription.Faults%2A> <xref:System.ServiceModel.Description.FaultDescriptionCollection>です。  
  
 他の部分<xref:System.ServiceModel.Description.OperationDescription>WF サービス今日 (例: WebGet/WebInvoke 動作、またはカスタム操作の動作) でサポートされていないこと、API の生成および構成の一環としてこれらの値は無視されます。 例外はスローされません。
