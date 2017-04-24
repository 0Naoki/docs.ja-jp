---
title: "シリアル化と逆シリアル化 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d71814c-bda7-424b-85b7-15084ff9377a
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# シリアル化と逆シリアル化
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] には新しいシリアル化エンジン、<xref:System.Runtime.Serialization.DataContractSerializer> が含まれます。<xref:System.Runtime.Serialization.DataContractSerializer> は、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] オブジェクトと XML を双方向で変換します。 ここでは、シリアライザーのしくみについて説明します。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] オブジェクトをシリアル化するときに、シリアライザーは新しい*データ コントラクト* モデルも含めて、さまざまなシリアル化プログラミング モデルを認識します。 サポートされるすべての型の一覧については、「[データ コントラクト シリアライザーでサポートされる型](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)」を参照してください。 データ コントラクトの概要については、「[データ コントラクトの使用](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)」を参照してください。  
  
 XML を逆シリアル化するときに、シリアライザーは <xref:System.Xml.XmlReader> クラスと <xref:System.Xml.XmlWriter> クラスを使用します。 また、<xref:System.Xml.XmlDictionaryReader> バイナリ XML 形式を使用する場合などに、最適化された XML を生成できるように、<xref:System.Xml.XmlDictionaryWriter> クラスと [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] クラスもサポートしています。  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] には、コンパニオン シリアライザーである <xref:System.Runtime.Serialization.NetDataContractSerializer> も含まれます。<xref:System.Runtime.Serialization.NetDataContractSerializer> は、シリアル化されたデータの一部として <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 型名を出力するため、<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> シリアライザーや [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] シリアライザーに似ています。 このシリアライザーは、シリアル化と逆シリアル化の終了時に、同じ型を共有する場合に使用します。<xref:System.Runtime.Serialization.DataContractSerializer> と <xref:System.Runtime.Serialization.NetDataContractSerializer> は、共通の基本クラスである <xref:System.Runtime.Serialization.XmlObjectSerializer> から派生します。  
  
> [!WARNING]
>  <xref:System.Runtime.Serialization.DataContractSerializer> は、20 未満の 16 進数値と制御文字を含む文字列を XML エンティティとしてシリアル化します。 このため、WCF サービスにそのようなデータを送信する際に WCF 以外のクライアントに問題が発生することがあります。  
  
## DataContractSerializer インスタンスの作成  
 <xref:System.Runtime.Serialization.DataContractSerializer> のインスタンスの作成は重要な手順です。 インスタンスの作成後に、設定を変更することはできません。  
  
### ルート型の指定  
 *ルート型*は、シリアル化または逆シリアル化するインスタンスの型です。<xref:System.Runtime.Serialization.DataContractSerializer> には、多数のコンストラクター オーバーロードがありますが、`type`  パラメーターを使用して、少なくともルート型を指定する必要があります。  
  
 特定のルート型に対応するシリアライザーを作成した場合、このシリアライザーを使用して別の型をシリアル化 \(または逆シリアル化\) することはできません。ただし、対象の型がルート型の派生型である場合を除きます。 2 つのクラスを次の例に示します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#1)]
 [!code-vb[c_StandaloneDataContractSerializer#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#1)]  
  
 `DataContractSerializer` クラスのインスタンスをシリアル化または逆シリアル化する場合にのみ使用できる `Person` のインスタンスを作成するコードを次に示します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#2)]
 [!code-vb[c_StandaloneDataContractSerializer#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#2)]  
  
### 既知の型の指定  
 <xref:System.Runtime.Serialization.KnownTypeAttribute> 属性またはその他の機構を使用してまだ処理されていないシリアル化対象の型にポリモーフィズムが必要な場合、`knownTypes` パラメーターを使用して、存在し得る既知の型のリストをシリアライザーのコンストラクターに渡す必要があります。 既知の型[!INCLUDE[crabout](../../../../includes/crabout-md.md)]、「[既知のデータ コントラクト型](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)」を参照してください。  
  
 `LibraryPatron` 型のコレクションを含む `LibraryItem` クラスの例を次に示します。 2 番目のクラスでは、`LibraryItem` 型を定義しています。 3 番目と 4 番目のクラス \(`Book` と `Newspaper`\) は、`LibraryItem` クラスを継承しています。  
  
 <!-- TODO: review snippet reference [!code-csharp[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#3)]  -->
 [!code-vb[c_StandaloneDataContractSerializer#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#3)]  
  
 `knownTypes` パラメーターを使用して、シリアライザーのインスタンスを作成するコードを次に示します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#4)]
 [!code-vb[c_StandaloneDataContractSerializer#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#4)]  
  
### 既定のルート名と名前空間の指定  
 通常、オブジェクトをシリアル化すると、データ コントラクト名と名前空間に従って、最も外側にある XML 要素の既定の名前と名前空間が決定されます。 内側のすべての要素の名前はデータ メンバー名から決定され、名前空間にはデータ コントラクトの名前空間が使用されます。`Name` クラスと `Namespace` クラスのコンストラクターで、<xref:System.Runtime.Serialization.DataContractAttribute> および <xref:System.Runtime.Serialization.DataMemberAttribute> の値を設定する例を次に示します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#5)]
 [!code-vb[c_StandaloneDataContractSerializer#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#5)]  
  
 `Person` クラスのインスタンスをシリアル化すると、次のような XML が生成されます。  
  
```  
<PersonContract xmlns="http://schemas.contoso.com">  
  <AddressMember>  
    <StreetMember>123 Main Street</StreetMember>  
   </AddressMember>  
</PersonContract>  
```  
  
 ただし、`rootName` パラメーターと `rootNamespace` パラメーターの値を <xref:System.Runtime.Serialization.DataContractSerializer> のコンストラクターに渡すことにより、ルート要素の既定の名前と名前空間をカスタマイズできます。`rootNamespace` は、データ メンバーに対応する格納されている要素の名前空間には影響を及ぼしません。 このパラメーターの影響を受けるのは、最も外側の要素の名前空間だけです。  
  
 これらの値を文字列または <xref:System.Xml.XmlDictionaryString> クラスのインスタンスとして渡すと、バイナリ XML 形式を使用して最適化できます。  
  
### オブジェクトの最大クォータの設定  
 `DataContractSerializer` の一部のコンストラクター オーバーロードには、`maxItemsInObjectGraph` パラメーターが含まれています。 このパラメーターにより、<xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> メソッドの 1 回の呼び出しで、シリアライザーがシリアル化または逆シリアル化するオブジェクトの最大数が決まります  \(このメソッドは常に、1 つのルート オブジェクトを読み取りますが、このオブジェクトはそのデータ メンバー内に他のオブジェクトを保持する場合があります。 さらに、そうしたオブジェクトも他のオブジェクトを持つ場合があります。以降のオブジェクトについても同様です\)。 既定値は 65536 です。 配列のシリアル化または逆シリアル化を行う場合、すべての配列エントリが個別のオブジェクトとしてカウントされることに注意してください。 また、オブジェクトによってはメモリ表現が大きくなる場合があり、このクォータだけでは、サービス拒否攻撃の防止には不十分である可能性があることに注意してください。[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [セキュリティに関するデータの考慮事項](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)。 このクォータはデータの読み取り時と書き込み時の両方に適用されるため、このクォータに既定値を上回る値を設定する必要がある場合は、送信側 \(シリアル化\) と受信側 \(逆シリアル化\) の両方で設定することが重要です。  
  
### ラウンド トリップ  
 *ラウンド トリップ*は、1 つの操作でオブジェクトの逆シリアル化と再シリアル化が行われるときに発生します。 したがって、XML からオブジェクト インスタンスを経由し、再び XML ストリームに戻るラウンド トリップが発生します。  
  
 `DataContractSerializer` の一部のコンストラクター オーバーロードには、`ignoreExtensionDataObject`  パラメーターが含まれており、既定で `false`  に設定されています。 この既定のモードでは、データ コントラクトが <xref:System.Runtime.Serialization.IExtensibleDataObject> インターフェイスを実装していれば、データ コントラクトの新しいバージョンから以前のバージョンを経由し、新しいバージョンに戻るラウンド トリップで、データを失うことなく送信できます。 たとえば、`Person` データ コントラクトのバージョン 1 に、`Name` および `PhoneNumber` の各データ メンバーが含まれており、バージョン 2 で `Nickname` メンバーを追加したとします。`IExtensibleDataObject` を実装している場合、バージョン 2 からバージョン 1 に情報を送信すると、`Nickname` データが格納され、データを再度シリアル化したときに再出力されます。したがって、ラウンド トリップでデータが失われることはありません。[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][上位互換性のあるデータ コントラクト](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)」および「[データ コントラクトのバージョン管理](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)」を参照してください。  
  
#### ラウンド トリップでのセキュリティとスキーマ検証の問題  
 ラウンド トリップは、セキュリティに影響する場合があります。 たとえば、大量の無関係のデータを逆シリアル化し格納した場合、セキュリティ リスクが生じる可能性があります。 特に、デジタル署名を伴う場合は、検証方法のないこのようなデータの再出力について、セキュリティの問題が発生することがあります。 たとえば、前のシナリオでは、バージョン 1 エンドポイントが、悪質なデータを含む `Nickname` 値に署名する可能性があります。 また、スキーマ検証の問題が発生することもあります。エンドポイントでは、余分な値を出力せずに、記述されたコントラクトに厳密に従ったデータを常に出力することが必要な場合があります。 前の例では、バージョン 1 エンドポイントのコントラクトで `Name` と `PhoneNumber` だけを出力するよう指定されているときに、スキーマ検証を使用すると、余分な `Nickname` 値の出力によって検証が失敗します。  
  
#### ラウンド トリップの有効化と無効化  
 ラウンド トリップを無効にする場合は、<xref:System.Runtime.Serialization.IExtensibleDataObject> インターフェイスを実装しないでください。 型を制御できない場合は、`ignoreExtensionDataObject` パラメーターを `true` に設定することで、同じ効果を得ることができます。  
  
### オブジェクト グラフの保存  
 次のコードに示すように、通常、シリアライザーはオブジェクト ID に留意することはありません。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#6)]
 [!code-vb[c_StandaloneDataContractSerializer#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#6)]  
  
 発注書を作成するコードを次に示します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#7)]
 [!code-vb[c_StandaloneDataContractSerializer#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#7)]  
  
 `billTo` フィールドと `shipTo` フィールドが、同じオブジェクト インスタンスに設定されていることに注意してください。 ただし、生成される XML は重複する情報を繰り返します。XML は次のようになります。  
  
```  
<PurchaseOrder>  
  <billTo><street>123 Main St.</street></billTo>  
  <shipTo><street>123 Main St.</street></shipTo>  
</PurchaseOrder>  
```  
  
 この方法には以下の特性があり、望ましくないことがあります。  
  
-   パフォーマンス。 データのレプリケートは非効率的です。  
  
-   循環参照。 他のオブジェクトを介してであっても、オブジェクトがそれ自体を参照している場合、レプリケーションによるシリアル化は無限ループを発生させます  \(この状況が発生した場合、シリアライザーは <xref:System.Runtime.Serialization.SerializationException> をスローします\)。  
  
-   セマンティクス。 2 つの参照の参照先が 1 つのオブジェクトであり、2 つの同一のオブジェクトではない状態を維持することが重要な場合があります。  
  
 上記の理由から、`DataContractSerializer` の一部のコンストラクター オーバーロードには、`preserveObjectReferences` パラメーターが含まれています \(既定値は `false` です\)。 このパラメーターを `true` に設定すると、オブジェクト参照をエンコードする特殊なメソッドが使用されます。これは、[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] だけが認識するメソッドです。`true` に設定すると、XML コードの例は次のようになります。  
  
```  
<PurchaseOrder ser:id="1">  
  <billTo ser:id="2"><street ser:id="3">123 Main St.</street></billTo>  
  <shipTo ser:ref="2"/>  
</PurchaseOrder>  
```  
  
 "ser" 名前空間は、シリアル化標準名前空間である http:\/\/schemas.microsoft.com\/2003\/10\/Serialization\/ を指します。 データの各部分は 1 回だけシリアル化され、ID 番号が与えられます。以降は、既にシリアル化されたデータへの参照を使用することになります。  
  
> [!IMPORTANT]
>  "id" および "ref" 属性の両方がデータ コントラクト `XMLElement` に存在する場合、"ref" 属性が使用され、"id" 属性は無視されます。  
  
 このモードの以下の制限を理解しておくことが重要です。  
  
-   `DataContractSerializer` が `preserveObjectReferences`  に設定された `true` によって生成した XML は、他のテクノロジと相互運用できません。この XML にアクセスできるのは、`DataContractSerializer` が `preserveObjectReferences` に設定された別の `true` インスタンスだけです。  
  
-   この機能では、メタデータ \(スキーマ\) はサポートされていません。 生成されるスキーマは、`preserveObjectReferences` が `false` に設定されている場合にのみ有効です。  
  
-   この機能により、シリアル化および逆シリアル化プロセスの実行速度が低下することがあります。 データをレプリケートする必要はありませんが、このモードではオブジェクトの比較を追加で実行する必要があります。  
  
> [!CAUTION]
>  `preserveObjectReferences` モードを有効にする場合、`maxItemsInObjectGraph` の値を適切なクォータに設定することが特に重要となります。 このモードでの配列の処理方法に起因して、攻撃者は `maxItemsInObjectGraph` のクォータによってのみ制限される、メモリを大量に消費させる小さい悪質なメッセージを容易に作成できます。  
  
### データ コントラクト サロゲートの指定  
 `DataContractSerializer` の一部のコンストラクター オーバーロードには、`dataContractSurrogate` パラメーターが含まれています。このパラメーターは、`null` に設定できます。 それ以外の場合は、このパラメーターを使用して、*データ コントラクト サロゲート*を指定できます。データ コントラクト サロゲートは、<xref:System.Runtime.Serialization.IDataContractSurrogate> インターフェイスを実装する型です。 このインターフェイスを使用して、シリアル化および逆シリアル化プロセスをカスタマイズできます。[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [データ コントラクト サロゲート](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)。  
  
## シリアル化  
 次の情報は <xref:System.Runtime.Serialization.XmlObjectSerializer> を継承するすべてのクラス \(<xref:System.Runtime.Serialization.DataContractSerializer> クラスおよび <xref:System.Runtime.Serialization.NetDataContractSerializer> クラスを含む\) に適用されます。  
  
### 単純なシリアル化  
 オブジェクトをシリアル化する最も簡単な方法は、オブジェクトを <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> メソッドに渡すことです。 このメソッドには 3 つのオーバーロードがあり、それぞれ <xref:System.IO.Stream>、<xref:System.Xml.XmlWriter>、および <xref:System.Xml.XmlDictionaryWriter> への書き込みに対応しています。<xref:System.IO.Stream> オーバーロードの場合、出力は UTF\-8 エンコードの XML です。<xref:System.Xml.XmlDictionaryWriter> オーバーロードを使用すると、シリアライザーによってバイナリ XML の出力が最適化されます。  
  
 <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> メソッドを使用した場合、シリアライザーはラッパー要素の既定の名前と名前空間を使用し、コンテンツと共に書き込みます \(前の「既定のルート名と名前空間の指定」セクションを参照してください\)。  
  
 <xref:System.Xml.XmlDictionaryWriter> を使用した書き込みの例を次に示します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#8)]
 [!code-vb[c_StandaloneDataContractSerializer#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#8)]  
  
 これにより作成される XML は、次のようになります。  
  
```  
<Person>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
### 段階的なシリアル化  
 終了要素を書き込み、オブジェクトの内容を書き込み、ラッパー要素を閉じるには、それぞれ <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A>、<xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObjectContent%2A>、<xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> の各メソッドを使用します。  
  
> [!NOTE]
>  これらのメソッドの <xref:System.IO.Stream> オーバーロードはありません。  
  
 この段階的なシリアル化には、2 つの一般的な使用方法があります。 次の例に示すように、1 つは属性やコメントなどのコンテンツを `WriteStartObject` と `WriteObjectContent` の間に挿入する場合に使用します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#9)]
 [!code-vb[c_StandaloneDataContractSerializer#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#9)]  
  
 これにより作成される XML は、次のようになります。  
  
```  
<Person serializedBy="myCode">  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</Person>  
```  
  
 もう 1 つは、次のコードに示すように、<xref:System.Runtime.Serialization.XmlObjectSerializer.WriteStartObject%2A> と <xref:System.Runtime.Serialization.XmlObjectSerializer.WriteEndObject%2A> を使用せずに、独自のカスタム ラッパー要素を書き込む場合 \(ラッパーの書き込みを省略する場合もあります\) に使用します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#10)]
 [!code-vb[c_StandaloneDataContractSerializer#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#10)]  
  
 これにより作成される XML は、次のようになります。  
  
```  
<MyCustomWrapper>  
  <Name>Jay Hamlin</Name>  
  <Address>123 Main St.</Address>  
</MyCustomWrapper>  
```  
  
> [!NOTE]
>  段階的なシリアル化を使用すると、スキーマが無効な XML が生成されることがあります。  
  
## 逆シリアル化  
 次の情報は <xref:System.Runtime.Serialization.XmlObjectSerializer> を継承するすべてのクラス \(<xref:System.Runtime.Serialization.DataContractSerializer> クラスおよび <xref:System.Runtime.Serialization.NetDataContractSerializer> クラスを含む\) に適用されます。  
  
 オブジェクトを逆シリアル化する最も簡単な方法は、<xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> メソッド オーバーロードのいずれかを呼び出すことです。 3 つのオーバーロードがあり、それぞれ <xref:System.Xml.XmlDictionaryReader>、`XmlReader`、および `Stream` を使用した読み取りに対応しています。`Stream` オーバーロードは、クォータによって保護されていないテキスト形式の <xref:System.Xml.XmlDictionaryReader> を作成するため、信頼されたデータを読み取る場合にのみ使用します。  
  
 `ReadObject` メソッドが返すオブジェクトは、適切な型にキャストする必要があります。  
  
 <xref:System.Runtime.Serialization.DataContractSerializer> のインスタンスと <xref:System.Xml.XmlDictionaryReader> を作成し、`Person` インスタンスを逆シリアル化するコードを次に示します。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#11)]
 [!code-vb[c_StandaloneDataContractSerializer#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#11)]  
  
 <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> メソッドを呼び出す前に、ラッパー要素またはラッパー要素の前にあるコンテンツ ノード以外のノードに XML リーダーを配置します。 これを行うには、次のコードに示すように、<xref:System.Xml.XmlReader.Read%2A> またはその派生クラスの <xref:System.Xml.XmlReader> メソッドを呼び出し、<xref:System.Xml.XmlReader.NodeType%2A> を調べます。  
  
 [!code-csharp[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_standalonedatacontractserializer/cs/source.cs#12)]
 [!code-vb[c_StandaloneDataContractSerializer#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_standalonedatacontractserializer/vb/source.vb#12)]  
  
 `ReadObject` にリーダーを渡す前に、このラッパー要素の属性を読み取ることができます。  
  
 簡単な `ReadObject` オーバーロードのいずれかを使用すると、デシリアライザーはラッパー要素の既定の名前と名前空間を検索し \(前の「既定のルート名と名前空間の指定」セクションを参照\)、不明な要素が見つかった場合は例外をスローします。 前の例では、`<Person>` ラッパー要素が必要とされます。 予想どおりの名前が付けられた要素にリーダーが配置されているかどうかを確認するために、<xref:System.Runtime.Serialization.XmlObjectSerializer.IsStartObject%2A> メソッドが呼び出されます。  
  
 ラッパー要素のこの名前チェックを無効にする方法があります。`ReadObject` メソッドの一部のオーバーロードは、ブール型パラメーター `verifyObjectName` を取得します。このパラメーターは、既定で `true` に設定されています。 このパラメーターを `false` に設定すると、ラッパー要素の名前と名前空間が無視されます。 これは、前述の段階的なシリアル化機構を使用して書き込まれた XML を読み取る際に役立ちます。  
  
## NetDataContractSerializer の使用  
 `DataContractSerializer` と <xref:System.Runtime.Serialization.NetDataContractSerializer> の大きな違いは、`DataContractSerializer` は、データ コントラクト名を使用するのに対し、`NetDataContractSerializer` は、シリアル化された XML に [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] アセンブリと型の完全名を出力するという点です。 これは、シリアル化エンドポイントと逆シリアル化エンドポイント間で、まったく同じ型を共有する必要があることを意味します。 逆シリアル化する正確な型が常にわかっているため、`NetDataContractSerializer` では既知の型機構は必要ないということです。  
  
 ただし、次のようないくつかの問題が発生する可能性があります。  
  
-   セキュリティ。 逆シリアル化する XML で見つかったすべての型が読み込まれます。 これを利用して、悪質な型が強制的に読み込まれるおそれがあります。 信頼できないデータでの `NetDataContractSerializer` の使用は、\(<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder%2A> プロパティまたはコンストラクター パラメーターを使用して\) *シリアル化バインダー*を使用する場合に限定する必要があります。 バインダーが読み込みを許可するのは安全な型だけです。 このバインダー機構は、<xref:System.Runtime.Serialization> 名前空間の型が使用するものと同じです。  
  
-   バージョン管理。 XML で型とアセンブリの完全名を使用する場合、型をバージョン管理する方法が厳しく制限されます。 型名、名前空間、アセンブリ名、およびアセンブリのバージョンを変更することはできません。<xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> プロパティまたはコンストラクター パラメーターを既定値の <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> ではなく、<xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> に設定すると、アセンブリのバージョンを変更できるようになりますが、ジェネリック パラメーターの型を変更することはできません。  
  
-   相互運用性。[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 型名とアセンブリ名は XML に含まれるため、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 以外のプラットフォームでは、生成されたデータにアクセスできません。  
  
-   パフォーマンス。 型名とアセンブリ名を書き込むと、生成される XML のサイズが大幅に増加します。  
  
 この機構は、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] リモート処理で使用されるバイナリ シリアル化または SOAP シリアル化 \(具体的には、<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> と <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>\) に似ています。  
  
 `NetDataContractSerializer` の使用方法と `DataContractSerializer` の使用方法は似ていますが、次のような違いがあります。  
  
-   コンストラクターでルート型を指定する必要はありません。`NetDataContractSerializer` の同じインスタンスを使用して、すべての型をシリアル化できます。  
  
-   コンストラクターは、既知の型のリストを受け入れません。 型名を XML にシリアル化する場合、既知の型機構は不要です。  
  
-   コンストラクターは、データ コントラクト サロゲートを受け入れません。 代わりに、\(<xref:System.Runtime.Serialization.ISurrogateSelector> プロパティに割り当てられた\) `surrogateSelector` という <xref:System.Runtime.Serialization.NetDataContractSerializer.SurrogateSelector%2A> のパラメーターを受け入れます。 これは、従来のサロゲート機構です。  
  
-   コンストラクターは、`assemblyFormat` プロパティに割り当てられた、<xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> の <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> というパラメーターを受け入れます。 前述のように、このパラメーターを使用することで、シリアライザーのバージョン管理機能を強化できます。 これは、バイナリ シリアル化または SOAP シリアル化の <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle> 機構と同じです。  
  
-   コンストラクターは、<xref:System.Runtime.Serialization.StreamingContext> プロパティに割り当てられた `context` という <xref:System.Runtime.Serialization.NetDataContractSerializer.Context%2A> のパラメーターを受け入れます。 このパラメーターを使用して、シリアル化する型に情報を渡すことができます。 この使用方法は、他の <xref:System.Runtime.Serialization.StreamingContext> クラスで使用する <xref:System.Runtime.Serialization> 機構と同じです。  
  
-   <xref:System.Runtime.Serialization.NetDataContractSerializer.Serialize%2A> メソッドと <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize%2A> メソッドは、<xref:System.Runtime.Serialization.XmlObjectSerializer.WriteObject%2A> メソッドと <xref:System.Runtime.Serialization.XmlObjectSerializer.ReadObject%2A> メソッドのエイリアスです。 これらのメソッドは、より一貫性のあるプログラミング モデルで、バイナリ シリアル化または SOAP シリアル化を使用できるようにするために存在しています。  
  
 このような機能の[!INCLUDE[crabout](../../../../includes/crabout-md.md)]については、「[バイナリ シリアル化](../../../../docs/framework/serialization/binary-serialization.md)」を参照してください。  
  
 通常、`NetDataContractSerializer` と `DataContractSerializer` が使用する XML 形式には互換性がありません。 したがって、これらのシリアライザーの一方を使用してシリアル化し、もう一方を使用して逆シリアル化するシナリオはサポートされていません。  
  
 また、`NetDataContractSerializer` は、オブジェクト グラフの各ノードについて、[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 型とアセンブリの完全名を出力しません。 この情報を出力するのは、情報が不明確な場合だけです。 つまり、ポリモーフィックである場合に、ルート オブジェクト レベルで出力します。  
  
## 参照  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.NetDataContractSerializer>   
 <xref:System.Runtime.Serialization.XmlObjectSerializer>   
 [バイナリ シリアル化](../../../../docs/framework/serialization/binary-serialization.md)   
 [データ コントラクト シリアライザーでサポートされる型](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)