---
title: '方法: サービス コントラクトでのエラーを宣言する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 0e173f71201d5f98a04d2ad922469e4ff6666681
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768593"
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="5d21b-102">方法: サービス コントラクトでのエラーを宣言する</span><span class="sxs-lookup"><span data-stu-id="5d21b-102">How to: Declare Faults in Service Contracts</span></span>
<span data-ttu-id="5d21b-103">マネージド コードでは、エラー条件が発生すると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5d21b-103">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="5d21b-104">Windows Communication Foundation (WCF) アプリケーション、ただし、サービス コントラクト指定サービス コントラクトの SOAP エラーを宣言することでどのようなエラー情報がクライアントに返されます。</span><span class="sxs-lookup"><span data-stu-id="5d21b-104">In Windows Communication Foundation (WCF) applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="5d21b-105">例外とエラーの間のリレーションシップの概要については、次を参照してください。[を指定すると処理のエラー コントラクトおよびサービスの](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-105">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="5d21b-106">SOAP エラーを指定するサービス コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="5d21b-106">Create a service contract that specifies a SOAP fault</span></span>  
  
1. <span data-ttu-id="5d21b-107">サービス コントラクトを作成し、操作をいくつか定義します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-107">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="5d21b-108">例については、「[方法: サービス コントラクトを定義する](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-108">For an example, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2. <span data-ttu-id="5d21b-109">操作を選択します。これに対して指定したエラー条件が発生したとき、クライアント側に通知することになります。</span><span class="sxs-lookup"><span data-stu-id="5d21b-109">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="5d21b-110">エラー状態がクライアントに SOAP エラーを返すことを正当化するには、次を参照してください。[を指定すると処理のエラー コントラクトおよびサービスの](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-110">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
3. <span data-ttu-id="5d21b-111">選択した操作に対して <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> 属性を適用し、シリアル化可能なエラー型をコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-111">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="5d21b-112">詳細については、作成して、シリアル化可能な型を使用して、次を参照してください。 [Data Transfer in Service Contracts にを指定する](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-112">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="5d21b-113">`SampleMethod` 操作で `GreetingFault` を返せるように指定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-113">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4. <span data-ttu-id="5d21b-114">コントラクト内でクライアントへの通知が必要な操作すべてについて、手順 2. および 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-114">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="5d21b-115">指定した SOAP エラーを返す操作の実装</span><span class="sxs-lookup"><span data-stu-id="5d21b-115">Implementing an Operation to Return a Specified SOAP Fault</span></span>  
 <span data-ttu-id="5d21b-116">エラー状態を呼び出し元アプリケーションに通知するために、前の手順で指定したような特定の SOAP エラーを操作中に返せるように指定したので、次に実際に通知処理を実装します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-116">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="5d21b-117">指定した SOAP エラーを操作中に例外としてスローする</span><span class="sxs-lookup"><span data-stu-id="5d21b-117">Throw the specified SOAP fault in the operation</span></span>  
  
1. <span data-ttu-id="5d21b-118">操作中に <xref:System.ServiceModel.FaultContractAttribute> で指定したエラー条件が発生したとき、<xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> 例外を生成してスローする、というコードを記述します。SOAP エラーは型パラメーターとして、生成する例外に渡します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-118">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="5d21b-119">前の手順で示した `GreetingFault` 内で `SampleMethod` 例外をスローするコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-119">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="5d21b-120">例</span><span class="sxs-lookup"><span data-stu-id="5d21b-120">Example</span></span>  
 <span data-ttu-id="5d21b-121">`GreetingFault` 操作内で `SampleMethod` エラーが発生した場合の処理を実装したコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d21b-121">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5d21b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d21b-122">See also</span></span>

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
