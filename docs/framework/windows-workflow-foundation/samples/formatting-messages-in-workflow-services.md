---
title: ワークフロー サービスでのメッセージの書式設定
ms.date: 03/30/2017
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
ms.openlocfilehash: eb9a6b3a83a28154dc968bd4c1c41d34028bdd41
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46003036"
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="59497-102">ワークフロー サービスでのメッセージの書式設定</span><span class="sxs-lookup"><span data-stu-id="59497-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="59497-103">このサンプルでは、メッセージング アクティビティ (WF サービス) で使用できるユーザーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="59497-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="59497-104">サンプルのサービスは、簡単な費用承認サービスで、3 つの操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="59497-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="59497-105">`ApproveExpense` はデータ コントラクト型を受け取り、既知の型を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="59497-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="59497-106">この操作では、費用の金額に基づいて `true` または `false` を返します。</span><span class="sxs-lookup"><span data-stu-id="59497-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="59497-107">`ApprovePO` XmlSerializer 型を受け取り、返します`true`または`false`経費量に基づいています。`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="59497-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="59497-108">メッセージ コントラクト型を受け取り、返します`true`または`false`仕入先が、承認済みのベンダーの一覧にある場合、または要求が経理部 (finance 部門は、すべてのベンダーを使用できます) に付属している場合。</span><span class="sxs-lookup"><span data-stu-id="59497-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="59497-109">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="59497-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="59497-110">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] でプロジェクト ソリューションを読み込み、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="59497-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="59497-111">最初に、[ソリューションの基本ディレクトリ]\FormatterService\bin\debug\ に生成されたサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="59497-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="59497-112">2 番目に、[ソリューションの基本ディレクトリ]\FormatterClient\bin\debug に生成されたクライアント アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="59497-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="59497-113">クライアントは、サービスで 3 つの操作を呼び出し、結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="59497-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="59497-114">完了したら、Enter キーを押してクライアントを終了し、サービスを終了します。</span><span class="sxs-lookup"><span data-stu-id="59497-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59497-115">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="59497-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="59497-116">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="59497-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="59497-117">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="59497-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="59497-118">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="59497-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`