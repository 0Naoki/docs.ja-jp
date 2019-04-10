---
title: サービス コントラクトの実装
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: 766e0c4d30a4fa0eed9ce154ca932f5371a43211
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196321"
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="46bc3-102">サービス コントラクトの実装</span><span class="sxs-lookup"><span data-stu-id="46bc3-102">Implementing Service Contracts</span></span>
<span data-ttu-id="46bc3-103">サービスは、1 つ以上のエンドポイントでクライアントが使用できる機能を公開するクラスです。</span><span class="sxs-lookup"><span data-stu-id="46bc3-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="46bc3-104">サービスを作成するには、Windows Communication Foundation (WCF) コントラクトを実装するクラスを記述します。</span><span class="sxs-lookup"><span data-stu-id="46bc3-104">To create a service, write a class that implements a Windows Communication Foundation (WCF) contract.</span></span> <span data-ttu-id="46bc3-105">2 つの方法のいずれかでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="46bc3-105">You can do this in one of two ways.</span></span> <span data-ttu-id="46bc3-106">コントラクトを個別にインターフェイスとして定義し、そのインターフェイスを実装するクラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="46bc3-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="46bc3-107">または、クラスに <xref:System.ServiceModel.ServiceContractAttribute> 属性を配置し、サービスのクライアントが使用できるメソッドに <xref:System.ServiceModel.OperationContractAttribute> 属性を配置することによって、クラスとコントラクトを直接作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="46bc3-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="46bc3-108">サービス クラスの作成</span><span class="sxs-lookup"><span data-stu-id="46bc3-108">Creating a service class</span></span>  
 <span data-ttu-id="46bc3-109">個別に定義された `IMath` コントラクトを実装するサービスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="46bc3-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]   
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="46bc3-110">また、サービスは直接コントラクトを公開できます。</span><span class="sxs-lookup"><span data-stu-id="46bc3-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="46bc3-111">`MathService` コントラクトを定義し、実装するサービス クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="46bc3-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="46bc3-112">コントラクト名が異なるので、上記の 2 つのサービスが公開するコントラクトはそれぞれ異なります。</span><span class="sxs-lookup"><span data-stu-id="46bc3-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="46bc3-113">最初の例では、公開されるコントラクトの名前が "`IMath`" であるのに対し、2 番目の例では、コントラクトの名前は "`MathService`" です。</span><span class="sxs-lookup"><span data-stu-id="46bc3-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="46bc3-114">コンカレンシーやインスタンス化など、いくつかの項目は、サービス実装レベルと操作実装レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="46bc3-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="46bc3-115">詳細については、次を参照してください。[のデザインと実装サービス](../../../docs/framework/wcf/designing-and-implementing-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="46bc3-115">For more information, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="46bc3-116">サービス コントラクトを実装したら、そのサービスに 1 つ以上のエンドポイントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46bc3-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="46bc3-117">詳細については、次を参照してください。[エンドポイントの作成の概要](../../../docs/framework/wcf/endpoint-creation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="46bc3-117">For more information, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="46bc3-118">サービスを実行する方法の詳細については、次を参照してください。[ホスティング サービス](../../../docs/framework/wcf/hosting-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="46bc3-118">For more information about how to run a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46bc3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="46bc3-119">See also</span></span>

- [<span data-ttu-id="46bc3-120">サービスの設計と実装</span><span class="sxs-lookup"><span data-stu-id="46bc3-120">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="46bc3-121">方法: コントラクト クラスを使用してサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="46bc3-121">How to: Create a Service with a Contract Class</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [<span data-ttu-id="46bc3-122">方法: コントラクト インターフェイスを使用してサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="46bc3-122">How to: Create a Service with a Contract Interface</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [<span data-ttu-id="46bc3-123">サービスのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="46bc3-123">Specifying Service Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
