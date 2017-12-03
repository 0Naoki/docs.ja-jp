---
title: "バイナリ データの操作 (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, binary data
- WCF Data Services, streams
ms.assetid: aeccc45c-d5c5-4671-ad63-a492ac8043ac
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f94494f8f4ae038644244b93658e7e527e0067dc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2017
---
# <a name="working-with-binary-data-wcf-data-services"></a>バイナリ データの操作 (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]クライアント ライブラリを使用すると、取得し、更新からバイナリ データ、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]フィードを次の方法のいずれか。  
  
-   エンティティのプリミティブ型のプロパティとして。 メモリに容易に読み込むことができる小さいバイナリ データ オブジェクトを操作する場合は、この方法が適しています。 この場合、バイナリ プロパティは、データ モデルによって公開されるエンティティ プロパティです。データ サービスは、応答メッセージの Base-64 バイナリ エンコード XML としてバイナリ データをシリアル化します。  
  
-   個別のバイナリ リソース ストリームとして。 写真、ビデオ、またはその他の種類のバイナリ エンコード データを表すバイナリ ラージ オブジェクト (BLOB) データにアクセスしたり、変更したりする場合は、この方法が適しています。  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]定義されている HTTP を使用してバイナリ データのストリーミングを実装する、[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]です。 このメカニズムでは、バイナリ データは切り離されたメディア リソースとして扱われますが、メディア リンク エントリと呼ばれるエンティティに関連します。 詳細については、次を参照してください。[ストリーミング プロバイダー](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)です。  
  
> [!TIP]
>  作成する方法の詳細な手順の例については、[!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]からバイナリ画像ファイルをダウンロードするクライアント アプリケーション、 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 、写真を格納するサービスの投稿をご覧ください[Data Services ストリーミング プロバイダー シリーズ-パート 2: メディアへのアクセスクライアントからのリソース ストリーム](http://go.microsoft.com/fwlink/?LinkId=201637)です。 ブログの記事で取り上げるストリーミング フォト データ サービスのサンプル コードをダウンロードするを参照してください。、[ストリーミング フォト データ サービスのサンプル](http://go.microsoft.com/fwlink/?LinkId=198988)MSDN コード ギャラリーでします。  
  
## <a name="entity-metadata"></a>エンティティ メタデータ  
 メディア リソース ストリームが関連付けられているエンティティは、データ サービス メタデータで `HasStream` 属性によって示されます。この属性は、メディア リンク エントリであるエンティティ型に適用されます。 次の例で、`PhotoInfo`エンティティがメディア リンク エントリで示される、関連するメディア リソースを持つ、`HasStream`属性。  
  
 [!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria photo streaming service/xml/photodata.edmx#hasstream)]  
  
 このトピックのその他の例では、メディア リソース ストリームにアクセスし変更する方法を紹介します。 使用して、.NET Framework クライアント アプリケーションでメディア リソース ストリームを使用する方法の完全な例については、[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]クライアント ライブラリは、投稿を参照してください[クライアントからメディア リソース ストリームへのアクセス](http://go.microsoft.com/fwlink/?LinkID=201637)です。  
  
## <a name="accessing-the-binary-resource-stream"></a>バイナリ リソース ストリームへのアクセス  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] クライアント ライブラリには、[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ベースのデータ サービスからのバイナリ リソース ストリームにアクセスするためのメソッドが用意されています。 メディア リソースをダウンロードするときには、メディア リソースの URI を使用することも、メディア リソース データ自体を含むバイナリ ストリームを取得することもできます。 メディア リソース データをバイナリ ストリームとしてアップロードすることもできます。  
  
> [!TIP]
>  作成する方法の詳細な手順の例については、[!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]からバイナリ画像ファイルをダウンロードするクライアント アプリケーション、 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 、写真を格納するサービスの投稿をご覧ください[Data Services ストリーミング プロバイダー シリーズ-パート 2: メディアへのアクセスクライアントからのリソース ストリーム](http://go.microsoft.com/fwlink/?LinkId=201637)です。 ブログの記事で取り上げるストリーミング フォト データ サービスのサンプル コードをダウンロードするを参照してください。、[ストリーミング フォト データ サービスのサンプル](http://go.microsoft.com/fwlink/?LinkId=198988)MSDN コード ギャラリーでします。  
  
### <a name="getting-the-uri-of-the-binary-stream"></a>バイナリ ストリームの URI の取得  
 画像やその他のメディア ファイルなど、取得するメディア リソースの種類によっては、アプリケーションでメディア リソースの URI を使用する方がバイナリ データ ストリーム自体を処理するよりも簡単です。 特定のメディア リンク エントリに関連付けられているリソース ストリームの URI を取得するには、そのエンティティを追跡している <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> インスタンスの <xref:System.Data.Services.Client.DataServiceContext> メソッドを呼び出す必要があります。 次の例は、クライアントで新しい画像を作成するために使用するメディア リソース ストリームの URI を取得するために <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A> メソッドを呼び出す方法を示しています。  
  
 [!code-csharp[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming client/cs/photowindow.xaml.cs#getreadstreamuri)]
 [!code-vb[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming client/vb/photowindow.xaml.vb#getreadstreamuri)]  
  
### <a name="downloading-the-binary-resource-stream"></a>バイナリ リソース ストリームのダウンロード  
 バイナリ リソース ストリームを取得する場合、メディア リンク エントリを追跡している <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> インスタンスの <xref:System.Data.Services.Client.DataServiceContext> メソッドを呼び出す必要があります。 このメソッドは、<xref:System.Data.Services.Client.DataServiceStreamResponse> オブジェクトを返すデータ サービスに要求を送信します。このオブジェクトは、リソースが含まれるストリームを参照します。 アプリケーションでバイナリ リソースを <xref:System.IO.Stream> として取得する必要がある場合にこのメソッドを使用します。 次の例は、クライアントで新しい画像を作成するために使用するストリームを取得するために <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A> メソッドを呼び出す方法を示しています。  
  
 [!code-csharp[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria streaming client/cs/customerphotowindow.xaml.cs#getreadstreamclient)]
 [!code-vb[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria streaming client/vb/customerphotowindow.xaml.vb#getreadstreamclient)]  
  
> [!NOTE]
>  バイナリ ストリームを含む応答メッセージの Content-Length ヘッダーは、このデータ サービスによって設定されません。 この値は、バイナリ データ ストリームの実際の長さを反映していない場合があります。  
  
### <a name="uploading-a-media-resource-as-a-stream"></a>ストリームとしてのメディア リソースのアップロード  
 メディア リソースを挿入または更新するには、エンティティを追跡している <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> インスタンスの <xref:System.Data.Services.Client.DataServiceContext> メソッドを呼び出します。 このメソッドは、指定ストリームから読み込まれたメディア リソースを含むデータ サービスに要求を送信します。 次の例は、<xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> メソッドを呼び出してデータ サービスに画像を送信する方法を示しています。  
  
 [!code-csharp[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming client/cs/photodetailswindow.xaml.cs#setsavestream)]
 [!code-vb[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming client/vb/photodetailswindow.xaml.vb#setsavestream)]  
  
 この例では、<xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> パラメーターに値 `true` を指定して `closeStream` メソッドを呼び出しています。 したがって、必ず、バイナリ データがデータ サービスにアップロードされた後で <xref:System.Data.Services.Client.DataServiceContext> がストリームを閉じます。  
  
> [!NOTE]
>  <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> を呼び出すときには、<xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> が呼び出されるまでストリームはデータ サービスに送信されないことに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [WCF Data Services クライアント ライブラリ](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [コントロールへのデータ バインディング](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)
