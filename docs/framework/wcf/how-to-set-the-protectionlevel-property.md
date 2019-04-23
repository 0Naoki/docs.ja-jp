---
title: '方法: ProtectionLevel プロパティを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
ms.openlocfilehash: 77596d682af6f2579ca512b0a6de1694452e025b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317780"
---
# <a name="how-to-set-the-protectionlevel-property"></a><span data-ttu-id="24bb9-102">方法: ProtectionLevel プロパティを設定する</span><span class="sxs-lookup"><span data-stu-id="24bb9-102">How to: Set the ProtectionLevel Property</span></span>
<span data-ttu-id="24bb9-103">適切な属性を適用してプロパティを設定することで、保護レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="24bb9-103">You can set the protection level by applying an appropriate attribute and setting the property.</span></span> <span data-ttu-id="24bb9-104">サービス レベルですべてのメッセージのすべての部分に影響する保護を設定したり、メソッドからメッセージ部分まで、段階的にきめ細かなレベルで保護を設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="24bb9-104">You can set protection at the service level to affect all parts of every message, or you can set protection at increasingly granular levels, from methods to message parts.</span></span> <span data-ttu-id="24bb9-105">詳細については、`ProtectionLevel`プロパティを参照してください[について保護レベル](../../../docs/framework/wcf/understanding-protection-level.md)します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-105">For more information about the `ProtectionLevel` property, see [Understanding Protection Level](../../../docs/framework/wcf/understanding-protection-level.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24bb9-106">保護レベルは構成ではなく、コードでのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="24bb9-106">You can set protection levels only in code, not in configuration.</span></span>  
  
### <a name="to-sign-all-messages-for-a-service"></a><span data-ttu-id="24bb9-107">サービスのすべてのメッセージに署名するには</span><span class="sxs-lookup"><span data-stu-id="24bb9-107">To sign all messages for a service</span></span>  
  
1. <span data-ttu-id="24bb9-108">サービス用のインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-108">Create an interface for the service.</span></span>  
  
2. <span data-ttu-id="24bb9-109">次のコードに示すように、<xref:System.ServiceModel.ServiceContractAttribute> 属性をサービスに適用し、<xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> プロパティを <xref:System.Net.Security.ProtectionLevel.Sign> に設定します (既定のレベルは <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>)。</span><span class="sxs-lookup"><span data-stu-id="24bb9-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the service and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code (the default level is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span></span>  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a><span data-ttu-id="24bb9-110">操作のすべてのメッセージ部分に署名するには</span><span class="sxs-lookup"><span data-stu-id="24bb9-110">To sign all message parts for an operation</span></span>  
  
1. <span data-ttu-id="24bb9-111">サービスのインターフェイスを作成し、このインターフェイスに <xref:System.ServiceModel.ServiceContractAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-111">Create an interface for the service and apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
2. <span data-ttu-id="24bb9-112">インターフェイスにメソッド宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-112">Add a method declaration to the interface.</span></span>  
  
3. <span data-ttu-id="24bb9-113">次のコードに示すように、メソッドに <xref:System.ServiceModel.OperationContractAttribute> 属性を適用し、<xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> プロパティを <xref:System.Net.Security.ProtectionLevel.Sign> に設定します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-113">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to the method, and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a><span data-ttu-id="24bb9-114">エラー メッセージの保護</span><span class="sxs-lookup"><span data-stu-id="24bb9-114">Protecting Fault Messages</span></span>  
 <span data-ttu-id="24bb9-115">サービスでスローされた例外は、SOAP エラーとしてクライアントに送信できます。</span><span class="sxs-lookup"><span data-stu-id="24bb9-115">Exceptions that are thrown on a service can be sent to a client as SOAP faults.</span></span> <span data-ttu-id="24bb9-116">厳密に作成の詳細については、エラーを型指定されたを参照してください。[を指定すると処理のエラー コントラクトおよびサービスの](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)と[方法。サービス コントラクトでのエラーを宣言](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-116">For more information about creating strongly typed faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md) and [How to: Declare Faults in Service Contracts](../../../docs/framework/wcf/how-to-declare-faults-in-service-contracts.md).</span></span>  
  
#### <a name="to-protect-a-fault-message"></a><span data-ttu-id="24bb9-117">エラー メッセージを保護するには</span><span class="sxs-lookup"><span data-stu-id="24bb9-117">To protect a fault message</span></span>  
  
1. <span data-ttu-id="24bb9-118">エラー メッセージを表す型を作成します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-118">Create a type that represents the fault message.</span></span> <span data-ttu-id="24bb9-119">次の例では、2 つのフィールドを持つ `MathFault` という名前のクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-119">The following example creates a class named `MathFault` with two fields.</span></span>  
  
2. <span data-ttu-id="24bb9-120">次のコードに示すように、型に <xref:System.Runtime.Serialization.DataContractAttribute> 属性を適用し、シリアル化する必要のある各フィールドに <xref:System.Runtime.Serialization.DataMemberAttribute> 属性を適用します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-120">Apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type and a <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each field that should be serialized, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3. <span data-ttu-id="24bb9-121">エラーを返すインターフェイスで、エラーを返すメソッドに <xref:System.ServiceModel.FaultContractAttribute> 属性を適用し、エラー クラスの型に `detailType` パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-121">In the interface that will return the fault, apply the <xref:System.ServiceModel.FaultContractAttribute> attribute to the method that will return the fault and set the `detailType` parameter to the type of the fault class.</span></span>  
  
4. <span data-ttu-id="24bb9-122">次のコードに示すように、コンストラクターでも、<xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> プロパティを <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> に設定します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-122">Also in the constructor, set the <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a><span data-ttu-id="24bb9-123">メッセージ部分の保護</span><span class="sxs-lookup"><span data-stu-id="24bb9-123">Protecting Message Parts</span></span>  
 <span data-ttu-id="24bb9-124">メッセージ部分を保護するには、メッセージ コントラクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-124">Use a message contract to protect parts of a message.</span></span> <span data-ttu-id="24bb9-125">メッセージ コントラクトの詳細については、次を参照してください。 [Using Message Contracts](../../../docs/framework/wcf/feature-details/using-message-contracts.md)します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-125">For more information about message contracts, see [Using Message Contracts](../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span></span>  
  
#### <a name="to-protect-a-message-body"></a><span data-ttu-id="24bb9-126">メッセージ本文を保護するには</span><span class="sxs-lookup"><span data-stu-id="24bb9-126">To protect a message body</span></span>  
  
1. <span data-ttu-id="24bb9-127">メッセージを表す型を作成します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-127">Create a type that represents the message.</span></span> <span data-ttu-id="24bb9-128">次の例では、`Company` と `CompanyName` の 2 つのフィールドを持つ `CompanyID` クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-128">The following example creates a `Company` class with two fields, `CompanyName` and `CompanyID`.</span></span>  
  
2. <span data-ttu-id="24bb9-129">このクラスに <xref:System.ServiceModel.MessageContractAttribute> 属性を適用し、<xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> プロパティを <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> に設定します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-129">Apply the <xref:System.ServiceModel.MessageContractAttribute> attribute to the class and set the <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
3. <span data-ttu-id="24bb9-130">メッセージ ヘッダーとして表現されるフィールドに <xref:System.ServiceModel.MessageHeaderAttribute> 属性を適用し、`ProtectionLevel` プロパティを <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> に設定します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-130">Apply the <xref:System.ServiceModel.MessageHeaderAttribute> attribute to a field that will be expressed as a message header and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
4. <span data-ttu-id="24bb9-131">適用、 <xref:System.ServiceModel.MessageBodyMemberAttribute> 、メッセージ本文の一部として表現および設定される任意のフィールドに、`ProtectionLevel`プロパティを<xref:System.Net.Security.ProtectionLevel.EncryptAndSign>次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="24bb9-131">Apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to any field that will be expressed as part of the message body, and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following example.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="24bb9-132">例</span><span class="sxs-lookup"><span data-stu-id="24bb9-132">Example</span></span>  
 <span data-ttu-id="24bb9-133">次の例では、サービスのいろいろな場所で、いくつかの属性クラスの `ProtectionLevel` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-133">The following example sets the `ProtectionLevel` property of several attribute classes at various places in a service.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24bb9-134">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="24bb9-134">Compiling the Code</span></span>  
 <span data-ttu-id="24bb9-135">コード例のコンパイルに必要な名前空間を、次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="24bb9-135">The following code shows the namespaces required to compile the example code.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="24bb9-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="24bb9-136">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [<span data-ttu-id="24bb9-137">保護レベルの理解</span><span class="sxs-lookup"><span data-stu-id="24bb9-137">Understanding Protection Level</span></span>](../../../docs/framework/wcf/understanding-protection-level.md)
