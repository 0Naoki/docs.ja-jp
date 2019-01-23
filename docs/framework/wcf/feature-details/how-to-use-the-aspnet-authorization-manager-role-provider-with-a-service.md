---
title: '方法: サービスと ASP.NET の承認マネージャー ロール プロバイダーを使用します。'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: de6c96fd8d0ea17954463d554504cdb4180a5268
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625563"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="2dc05-102">方法: サービスと ASP.NET の承認マネージャー ロール プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="2dc05-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] が Web サービスをホストする場合は、承認マネージャーをアプリケーションに統合してサービスを承認することができます。</span><span class="sxs-lookup"><span data-stu-id="2dc05-103">When [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="2dc05-104">承認マネージャーを使用して、アプリケーション開発者は個々の操作を定義できます。また、個々の操作をグループ化してタスクを形成できます。</span><span class="sxs-lookup"><span data-stu-id="2dc05-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="2dc05-105">次に管理者は、ロールを承認して特定のタスクまたは個々の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2dc05-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="2dc05-106">承認マネージャーでは、ロール、タスク、操作、ユーザーを管理する管理ツールとして Microsoft 管理コンソール (MMC) スナップインが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2dc05-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="2dc05-107">管理者は、承認マネージャーのポリシー ストアを XML ファイル、Active Directory、または Active Directory アプリケーション モード (ADAM) ストアに構成します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="2dc05-108">承認マネージャーをアプリケーションに統合するには、Web サービスをホストする [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] アプリケーションの承認マネージャーの [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ロール プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider for the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is hosting the Web service.</span></span> <span data-ttu-id="2dc05-109">他の [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ロール プロバイダーと同様、承認マネージャーの [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ロール プロバイダーは <`providers`> 要素を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-109">Like other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role providers, the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="2dc05-110">承認マネージャーをアプリケーションに統合する Web サービスの構成ファイルの一部を示すコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="2dc05-111">統合の詳細については、 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] WCF アプリケーションでは、ロール プロバイダーを参照してください[方法。ASP.NET ロール プロバイダーを使用して、サービスと](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-111">For more information about integrating an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="2dc05-112">承認マネージャーの詳細については[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]を参照してください[方法。ASP.NET 2.0 で Authorization Manager (AzMan) 使用](https://go.microsoft.com/fwlink/?LinkId=71303)します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-112">For more information about using Authorization Manager with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc05-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2dc05-113">See also</span></span>
- [<span data-ttu-id="2dc05-114">方法: サービスで ASP.NET ロール プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="2dc05-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
