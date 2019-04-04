---
title: トランスポート セキュリティと匿名クライアントの WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 20d7e59ba2b4b9dedc0b0daff1c1aa9c5210e61b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260386"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="658f0-102">トランスポート セキュリティと匿名クライアント</span><span class="sxs-lookup"><span data-stu-id="658f0-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="658f0-103">この Windows Communication Foundation (WCF) のシナリオでは、トランスポート セキュリティ (HTTPS) を使用して、機密性と整合性を確認します。</span><span class="sxs-lookup"><span data-stu-id="658f0-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="658f0-104">サーバーは SSL (Secure Sockets Layer) 証明書で認証される必要があり、クライアントはサーバーの証明書を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="658f0-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="658f0-105">クライアントを認証する機構はないため、匿名となります。</span><span class="sxs-lookup"><span data-stu-id="658f0-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="658f0-106">サンプル アプリケーションでは、[WS トランスポート セキュリティ](../samples/ws-transport-security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="658f0-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="658f0-107">トランスポート セキュリティの詳細については、[トランスポート セキュリティの概要](transport-security-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="658f0-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="658f0-108">サービスで証明書の使用に関する詳細については、次を参照してください。 [Working with Certificates](working-with-certificates.md)と[方法。SSL 証明書でポートを構成](how-to-configure-a-port-with-an-ssl-certificate.md)します。</span><span class="sxs-lookup"><span data-stu-id="658f0-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![匿名クライアントを使用する場合のトランスポート セキュリティ](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="658f0-110">特徴</span><span class="sxs-lookup"><span data-stu-id="658f0-110">Characteristic</span></span>|<span data-ttu-id="658f0-111">説明</span><span class="sxs-lookup"><span data-stu-id="658f0-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="658f0-112">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="658f0-112">Security Mode</span></span>|<span data-ttu-id="658f0-113">Transport</span><span class="sxs-lookup"><span data-stu-id="658f0-113">Transport</span></span>|
|<span data-ttu-id="658f0-114">相互運用性</span><span class="sxs-lookup"><span data-stu-id="658f0-114">Interoperability</span></span>|<span data-ttu-id="658f0-115">既存の Web サービスとクライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="658f0-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="658f0-116">認証 (サーバー)</span><span class="sxs-lookup"><span data-stu-id="658f0-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="658f0-117">認証 (クライアント)</span><span class="sxs-lookup"><span data-stu-id="658f0-117">Authentication (Client)</span></span>|<span data-ttu-id="658f0-118">[はい]</span><span class="sxs-lookup"><span data-stu-id="658f0-118">Yes</span></span><br /><br /> <span data-ttu-id="658f0-119">アプリケーション レベル (WCF はサポートされません)</span><span class="sxs-lookup"><span data-stu-id="658f0-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="658f0-120">整合性</span><span class="sxs-lookup"><span data-stu-id="658f0-120">Integrity</span></span>|<span data-ttu-id="658f0-121">はい</span><span class="sxs-lookup"><span data-stu-id="658f0-121">Yes</span></span>|
|<span data-ttu-id="658f0-122">機密性</span><span class="sxs-lookup"><span data-stu-id="658f0-122">Confidentiality</span></span>|<span data-ttu-id="658f0-123">はい</span><span class="sxs-lookup"><span data-stu-id="658f0-123">Yes</span></span>|
|<span data-ttu-id="658f0-124">Transport</span><span class="sxs-lookup"><span data-stu-id="658f0-124">Transport</span></span>|<span data-ttu-id="658f0-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="658f0-125">HTTPS</span></span>|
|<span data-ttu-id="658f0-126">バインディング</span><span class="sxs-lookup"><span data-stu-id="658f0-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="658f0-127">サービス</span><span class="sxs-lookup"><span data-stu-id="658f0-127">Service</span></span>

<span data-ttu-id="658f0-128">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="658f0-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="658f0-129">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="658f0-129">Do one of the following:</span></span>

- <span data-ttu-id="658f0-130">構成を使用せずに、コードを使用してスタンドアロン サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="658f0-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="658f0-131">提供された構成を使用してサービスを作成しますが、エンドポイントを定義しません。</span><span class="sxs-lookup"><span data-stu-id="658f0-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="658f0-132">コード</span><span class="sxs-lookup"><span data-stu-id="658f0-132">Code</span></span>

<span data-ttu-id="658f0-133">次のコードは、トランスポート セキュリティを使用してエンドポイントを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="658f0-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="658f0-134">構成</span><span class="sxs-lookup"><span data-stu-id="658f0-134">Configuration</span></span>

<span data-ttu-id="658f0-135">次のコードは、構成を使用して同一のエンドポイントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="658f0-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="658f0-136">クライアントを認証する機構はないため、匿名となります。</span><span class="sxs-lookup"><span data-stu-id="658f0-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="658f0-137">クライアント</span><span class="sxs-lookup"><span data-stu-id="658f0-137">Client</span></span>

<span data-ttu-id="658f0-138">次のコードと構成は、別々に実行します。</span><span class="sxs-lookup"><span data-stu-id="658f0-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="658f0-139">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="658f0-139">Do one of the following:</span></span>

- <span data-ttu-id="658f0-140">コード (およびクライアント コード) を使用してスタンドアロン クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="658f0-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="658f0-141">エンドポイント アドレスを定義しないクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="658f0-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="658f0-142">代わりに、引数として構成名を受け取るクライアント コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="658f0-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="658f0-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="658f0-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="658f0-144">コード</span><span class="sxs-lookup"><span data-stu-id="658f0-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="658f0-145">構成</span><span class="sxs-lookup"><span data-stu-id="658f0-145">Configuration</span></span>

<span data-ttu-id="658f0-146">コードの代わりに次の構成を使用して、サービスをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="658f0-146">The following configuration can be used instead of the code to set up the service.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="658f0-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="658f0-147">See also</span></span>

- [<span data-ttu-id="658f0-148">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="658f0-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="658f0-149">WS トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="658f0-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="658f0-150">トランスポート セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="658f0-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="658f0-151">[Windows Server App Fabric のセキュリティ モデル](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="658f0-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>