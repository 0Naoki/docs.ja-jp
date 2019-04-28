---
title: クライアント アプリケーションに UI オートメーション プロバイダーを実装する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: b368ab3bc842fda5a99a64e0220093ebd60698b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609816"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="21a7a-102">クライアント アプリケーションに UI オートメーション プロバイダーを実装する</span><span class="sxs-lookup"><span data-stu-id="21a7a-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
>  <span data-ttu-id="21a7a-103">このドキュメントは、[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 名前空間で定義されているマネージド <xref:System.Windows.Automation> クラスを使用する .NET Framework 開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="21a7a-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="21a7a-104">に関する最新情報については[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]を参照してください[Windows Automation API:UI オートメーション](https://go.microsoft.com/fwlink/?LinkID=156746)します。</span><span class="sxs-lookup"><span data-stu-id="21a7a-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="21a7a-105">このトピックのコード例では、アプリケーション内のクライアント側 UI オートメーション プロバイダーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21a7a-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="21a7a-106">これは、一般的ではないシナリオです。</span><span class="sxs-lookup"><span data-stu-id="21a7a-106">This is an uncommon scenario.</span></span> <span data-ttu-id="21a7a-107">通常は、UI オートメーション クライアント アプリケーションは、サーバー側プロバイダーを使用するか、または DLL 内に存在するクライアント側プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="21a7a-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21a7a-108">例</span><span class="sxs-lookup"><span data-stu-id="21a7a-108">Example</span></span>  
 <span data-ttu-id="21a7a-109">次のコード例では、コンソール ウィンドウ用の簡単なプロバイダーを実装します。</span><span class="sxs-lookup"><span data-stu-id="21a7a-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="21a7a-110">このコードは、有用な機能は備えていませんが、クライアント コード内でプロバイダーを設定し、 <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>を使用して登録する際の基本的な手順を示すために用意されています。</span><span class="sxs-lookup"><span data-stu-id="21a7a-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="21a7a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="21a7a-111">See also</span></span>

- [<span data-ttu-id="21a7a-112">UI オートメーション プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="21a7a-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="21a7a-113">クライアント側プロバイダー アセンブリの登録</span><span class="sxs-lookup"><span data-stu-id="21a7a-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="21a7a-114">クライアント側 UI オートメーション プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="21a7a-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="21a7a-115">クライアント側 UI オートメーション プロバイダーの実装</span><span class="sxs-lookup"><span data-stu-id="21a7a-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
