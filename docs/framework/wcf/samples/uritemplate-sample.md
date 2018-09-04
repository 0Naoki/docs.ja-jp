---
title: UriTemplate サンプル
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 0dfb2cdc27460f3bc30a1c4302206bf43f7ef007
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518871"
---
# <a name="uritemplate-sample"></a><span data-ttu-id="09d49-102">UriTemplate サンプル</span><span class="sxs-lookup"><span data-stu-id="09d49-102">UriTemplate Sample</span></span>
<span data-ttu-id="09d49-103"><xref:System.UriTemplate> クラスには、共通構造を共有する URI のセットを使用するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="09d49-103">The <xref:System.UriTemplate> class provides methods for working with sets of URIs that share a common structure.</span></span> <span data-ttu-id="09d49-104">このサンプルでは、次の `UriTemplate` に関連する重要な概念を示します。</span><span class="sxs-lookup"><span data-stu-id="09d49-104">This sample demonstrates the following key concepts relating to `UriTemplate`:</span></span>  
  
-   <span data-ttu-id="09d49-105">テンプレートを作成するための構文</span><span class="sxs-lookup"><span data-stu-id="09d49-105">Syntax for creating templates.</span></span>  
  
-   <span data-ttu-id="09d49-106">`UriTemplate` および <xref:System.UriTemplate.BindByName%2A> を使用した、<xref:System.UriTemplate.BindByPosition%2A> からの URI のインスタンス化</span><span class="sxs-lookup"><span data-stu-id="09d49-106">Instantiating URIs from a `UriTemplate` using <xref:System.UriTemplate.BindByName%2A> and <xref:System.UriTemplate.BindByPosition%2A>.</span></span>  
  
-   <span data-ttu-id="09d49-107"><xref:System.UriTemplateTable.Match%2A> および `BindByName` の逆の操作である `BindByPosition`</span><span class="sxs-lookup"><span data-stu-id="09d49-107"><xref:System.UriTemplateTable.Match%2A>, which is the inverse operation of `BindByName` and `BindByPosition`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="09d49-108">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="09d49-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="09d49-109">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="09d49-109">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="09d49-110">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="09d49-110">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="09d49-111">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="09d49-111">The samples may already be installed on your computer.</span></span> <span data-ttu-id="09d49-112">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="09d49-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="09d49-113">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="09d49-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="09d49-114">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09d49-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a><span data-ttu-id="09d49-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="09d49-115">See Also</span></span>  
 [<span data-ttu-id="09d49-116">UriTemplate テーブル</span><span class="sxs-lookup"><span data-stu-id="09d49-116">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="09d49-117">UriTemplate テーブル ディスパッチャー</span><span class="sxs-lookup"><span data-stu-id="09d49-117">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
