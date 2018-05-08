---
title: '方法 : チャネル ファクトリを使用して、非同期的に操作を呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
ms.openlocfilehash: 95279f90fbf87d64d96a1ed036449b72416e4f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a>方法 : チャネル ファクトリを使用して、非同期的に操作を呼び出す
ここでは、<xref:System.ServiceModel.ChannelFactory%601> ベースのクライアント アプリケーションを使用する場合に、クライアントからサービス操作に非同期にアクセスする方法について説明します。 サービスを呼び出すために <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> オブジェクトを使用する場合は、イベント ドリブンの非同期呼び出しモデルを使用できます。 詳細については、次を参照してください。[する方法: サービスの操作を非同期に呼び出す](../../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)です。 イベント ベースの非同期呼び出しモデルについての詳細については、次を参照してください[イベント ベースの非同期パターンを使用したマルチ スレッド プログラミング](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)。)。  
  
 このトピックのサービスは、`ICalculator` インターフェイスを実装しています。 クライアントはこのインターフェイスにある操作を非同期に呼び出すことができます。これはたとえば `Add` という操作を `BeginAdd` と `EndAdd` の 2 つのメソッドに分割できることを意味します。前者によって呼び出しを開始し、後者によって操作の完了時に結果を取得します。 例については、サービスに非同期的に操作を実装する方法を示す、次を参照してください。[する方法: 非同期サービス操作を実装する](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)です。 同期および非同期の操作に関する詳細については、「[同期と非同期の操作](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)です。  
  
## <a name="procedure"></a>プロシージャ  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>WCF サービス操作を非同期に呼び出すには  
  
1.  実行、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)ツールを`/async`オプションを次のコマンドに示すようにします。  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     これにより、操作の非同期クライアント版のサービス コントラクトが生成されます。  
  
2.  次のサンプル コードに示すように、非同期操作の完了時に呼び出されるコールバック関数を作成します。  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3.  サービス操作に非同期にアクセスするには、次のサンプル コードに示すように、クライアントを作成して `Begin[Operation]` (たとえば `BeginAdd`) を呼び出し、コールバック関数を指定します。  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     コールバック関数が実行されると、クライアントは `End<operation>` (`EndAdd` など) を呼び出して結果を取得します。  
  
## <a name="example"></a>例  
 上記の手順で使用したクライアント コードで使用するサービスは、次のコードに示すように `ICalculator` インターフェイスを実装しています。 サービス側で、`Add`と`Subtract`コントラクトの操作が呼び出される同期的に実行時に、Windows Communication Foundation (WCF) によって、前のクライアントの手順は、クライアントに非同期的に呼び出される場合でもです。 `Multiply` 操作と `Divide` 操作は、クライアントで同期して呼び出される場合でも、サービス側ではサービスを非同期に呼び出すように使用されます。 この例では、<xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> プロパティを `true` に設定します。 このプロパティ設定は [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 非同期パターンの実装と共に、ランタイムに対して、操作を非同期で呼び出すよう指示します。  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
  
## <a name="see-also"></a>関連項目  
 [サービス コントラクト: 非同期のサンプル](http://msdn.microsoft.com/library/833db946-f511-4f64-a26f-2759a11217c7)
