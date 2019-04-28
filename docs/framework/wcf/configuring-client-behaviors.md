---
title: クライアントの動作の構成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 83fdc77bd17115f9952f2ca6c494ed0eb873cd9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608776"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="13c3c-102">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="13c3c-102">Configuring Client Behaviors</span></span>
<span data-ttu-id="13c3c-103">Windows Communication Foundation (WCF) は、2 つの方法で動作を構成します--で定義されている動作の構成を参照して、`<behavior>`セクションのクライアント アプリケーション構成ファイル – またはプログラムで、呼び出し元。アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="13c3c-103">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="13c3c-104">このトピックでは、両方の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13c3c-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="13c3c-105">構成ファイルを使用する場合、動作の構成には、構成設定の名前付きコレクションがあります。</span><span class="sxs-lookup"><span data-stu-id="13c3c-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="13c3c-106">各動作の構成には、一意の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c3c-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="13c3c-107">この文字列をエンドポイントの構成の `behaviorConfiguration` 属性で使用し、エンドポイントと動作を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="13c3c-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c3c-108">例</span><span class="sxs-lookup"><span data-stu-id="13c3c-108">Example</span></span>  
 <span data-ttu-id="13c3c-109">`myBehavior` という動作を定義する構成コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="13c3c-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="13c3c-110">クライアント エンドポイントは、この動作を `behaviorConfiguration` 属性で参照します。</span><span class="sxs-lookup"><span data-stu-id="13c3c-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="13c3c-111">プログラムによる動作の使用</span><span class="sxs-lookup"><span data-stu-id="13c3c-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="13c3c-112">設定を探し、適切な動作をプログラムで挿入や`Behaviors`Windows Communication Foundation (WCF) クライアント オブジェクトまたはクライアントを開く前に、クライアント チャネル ファクトリ オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="13c3c-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13c3c-113">例</span><span class="sxs-lookup"><span data-stu-id="13c3c-113">Example</span></span>  
 <span data-ttu-id="13c3c-114">次のコード例は、チャネル オブジェクトの作成前に、<xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> プロパティから返される <xref:System.ServiceModel.Description.ServiceEndpoint> 上の <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> プロパティにアクセスすることで、プログラムでクライアント動作が挿入される方法を示します。</span><span class="sxs-lookup"><span data-stu-id="13c3c-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="13c3c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="13c3c-115">See also</span></span>

- [<span data-ttu-id="13c3c-116">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="13c3c-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
