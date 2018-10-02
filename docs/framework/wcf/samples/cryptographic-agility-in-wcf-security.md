---
title: WCF セキュリティの暗号化方式の指定
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
ms.openlocfilehash: df40a87e2fe58b93a963d53fc79f88bbc7bdb805
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2018
ms.locfileid: "48026962"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="03816-102">WCF セキュリティの暗号化方式の指定</span><span class="sxs-lookup"><span data-stu-id="03816-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="03816-103">このサンプルでは、Windows Communication Foundation (WCF) クライアントとサービスで迅速な暗号化の実装を提供する標準またはカスタム アルゴリズムで指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="03816-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="03816-104">サンプルは、以下のプロジェクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="03816-104">The sample is composed of the following projects:</span></span>  
  
 <span data-ttu-id="03816-105">サービス</span><span class="sxs-lookup"><span data-stu-id="03816-105">Service</span></span>  
 <span data-ttu-id="03816-106">これは、自己ホスト型 WCF サービスを実装する、`ICalculator`インターフェイスを使用してエンドポイントを保護し、<<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> セキュリティで保護されたセッションと信頼できるセッションは無効にします。</span><span class="sxs-lookup"><span data-stu-id="03816-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="03816-107">このサービスは、カスタム `SecurityAlgorithmSuite` クラスを定義し、メッセージのセキュリティを確保するために使用される暗号化アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="03816-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
 <span data-ttu-id="03816-108">クライアント</span><span class="sxs-lookup"><span data-stu-id="03816-108">Client</span></span>  
 <span data-ttu-id="03816-109">これは、認証成功後にサービスにアクセスする WCFclient です。</span><span class="sxs-lookup"><span data-stu-id="03816-109">This is a WCFclient that accesses the service after successful authentication.</span></span> <span data-ttu-id="03816-110">このクライアントは、`ICalculator` インターフェイスによって公開され、サービスによって実装される操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="03816-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="03816-111">このクライアントも、同じカスタム `SecurityAlgorithmSuite` クラスを定義し、メッセージのセキュリティを確保するために使用される暗号化アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="03816-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="03816-112">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="03816-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="03816-113">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] で CryptoAgility.sln ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="03816-113">Open the CryptoAgility.sln solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="03816-114">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="03816-114">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="03816-115">開いている[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]\WCF\Basic\Security\CryptoAgility\Service\bin ディレクトリに移動し、service.exe を右クリックして、service.exe ファイルを管理者特権で実行**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="03816-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="03816-116">\WCF\Basic\Security\CryptoAgility\Client\bin ディレクトリに移動して、client.exe ファイルを通常の方法で実行します。</span><span class="sxs-lookup"><span data-stu-id="03816-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="03816-117">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="03816-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="03816-118">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="03816-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="03816-119">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="03816-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03816-120">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="03816-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="03816-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="03816-121">See Also</span></span>  
 [<span data-ttu-id="03816-122">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="03816-122">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
