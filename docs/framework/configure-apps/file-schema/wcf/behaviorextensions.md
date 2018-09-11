---
title: '&lt;behaviorExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: d025497956715913923e839cb6c482f44f96babb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261432"
---
# <a name="ltbehaviorextensionsgt"></a><span data-ttu-id="8b9cc-102">&lt;behaviorExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="8b9cc-102">&lt;behaviorExtensions&gt;</span></span>
<span data-ttu-id="8b9cc-103">動作の拡張により、ユーザーはユーザー定義の動作要素を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-103">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="8b9cc-104">これらの要素は、標準の Windows Communication Foundation (WCF) 動作要素と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-104">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="8b9cc-105">`behaviorExtensions` セクションでは、構成で使用できるように要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-105">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="8b9cc-106">次の例は、一般的な動作拡張を示します。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-106">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="myBehavior" type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
       </behaviorExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="8b9cc-107">構成機能を要素に追加するには、構成要素を記述して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-107">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="8b9cc-108">詳細については、<xref:System.Configuration> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="8b9cc-109">要素とその構成の型を定義したら、次の例に示すように拡張を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-109">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>  
    <behavior configurationName="testChannelBehavior">  
        <myBehavior />  
        <channelSecurity cacheCookies="false" detectReplays="false" maxCachedNonces="9"  
            maxClockSkew="00:00:03" maxCookieCachingTime="00:07:24" replayWindow="00:07:22.2190000" />  
    </behavior>  
</behaviors>  
```  
  
## <a name="security"></a><span data-ttu-id="8b9cc-110">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="8b9cc-110">Security</span></span>  
 <span data-ttu-id="8b9cc-111">`machine.config` ファイルと `app.config` ファイルに型を登録する場合は、完全修飾アセンブリ名の使用を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-111">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="8b9cc-112">型が一意に定義されていない場合、CLR 型ローダーは次の場所を指定された順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-112">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="8b9cc-113">型のアセンブリが判明している場合、ローダーは構成ファイルのリダイレクトの場所、GAC、構成情報を使用する現在のアセンブリ、およびアプリケーションの基本ディレクトリを検索します。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-113">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="8b9cc-114">アセンブリが判明していない場合、ローダーは現在のアセンブリ、mscorlib、および `TypeResolve` イベント ハンドラーによって返される場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-114">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="8b9cc-115">この CLR 検索順序は、Type Forwarding 機構や AppDomain.TypeResolve イベントなどのフックを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-115">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="8b9cc-116">攻撃者が CLR 検索順序を悪用して、未承認のコードを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-116">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="8b9cc-117">(厳密な) 完全修飾名を使用すると、型が一意に識別され、システムのセキュリティがさらに強化されます。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-117">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="8b9cc-118">詳細については、次を参照してください。[ランタイムがアセンブリを検索する方法](https://go.microsoft.com/fwlink/?LinkId=95336)と<xref:System.AppDomain.TypeResolve>します。</span><span class="sxs-lookup"><span data-stu-id="8b9cc-118">For more information, see [How the Runtime Locates Assemblies](https://go.microsoft.com/fwlink/?LinkId=95336) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9cc-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b9cc-119">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>  
 [<span data-ttu-id="8b9cc-120">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="8b9cc-120">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
