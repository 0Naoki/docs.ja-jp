---
title: WCF と国際化ドメイン名
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: c53c22e388ec352b1275018c0b945c9608565084
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335382"
---
# <a name="wcf-and-internationalized-domain-names"></a><span data-ttu-id="5e0b4-102">WCF と国際化ドメイン名</span><span class="sxs-lookup"><span data-stu-id="5e0b4-102">WCF and Internationalized Domain Names</span></span>
<span data-ttu-id="5e0b4-103">国際化ドメイン名 (IDN) を持つ WCF サービスを許可するためのサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-103">Support has been added to allow for WCF services with Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="5e0b4-104">国際化ドメイン名とは、非 ASCII 文字を含むドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-104">An internationalized domain name is a domain name that contains non-ASCII characters.</span></span> <span data-ttu-id="5e0b4-105">このサポートには、IDN 名を持つ WCF サービスをホストする機能と、IDN 名を持つ Web サービスとの通信を行う WCF クライアントをホストする機能の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-105">This support includes both the ability to host a WCF service with an IDN name and a WCF client to talk to a web service with an IDN name.</span></span>  
  
## <a name="systemuri-and-idn"></a><span data-ttu-id="5e0b4-106">System.Uri と IDN</span><span class="sxs-lookup"><span data-stu-id="5e0b4-106">System.Uri and IDN</span></span>  
 <xref:System.Uri> <span data-ttu-id="5e0b4-107">2 つのプロパティを持つ<xref:System.Uri.Host%2A>と<xref:System.Uri.DnsSafeHost%2A>します。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-107">has two properties <xref:System.Uri.Host%2A> and <xref:System.Uri.DnsSafeHost%2A>.</span></span> <span data-ttu-id="5e0b4-108">これらのプロパティには、IDN 構成設定に応じて Unicode 値または Punycode 値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-108">These properties contain Unicode or Punycode values depending upon the IDN configuration settings.</span></span>  
  
 <span data-ttu-id="5e0b4-109">IDN をアプリケーションの構成ファイルで有効にするには、次の XML を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-109">IDN is enabled in an application’s configuration file using the following XML</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 <span data-ttu-id="5e0b4-110">\<Idn > 要素には enabled 属性には、次の値のいずれかに設定することができますが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-110">The \<idn> element contains the enabled attribute which can be set to one of the following values:</span></span>  
  
1. <span data-ttu-id="5e0b4-111">"None"</span><span class="sxs-lookup"><span data-stu-id="5e0b4-111">"None"</span></span>  
  
2. <span data-ttu-id="5e0b4-112">「Allexceptintranet"」</span><span class="sxs-lookup"><span data-stu-id="5e0b4-112">"AllExceptIntranet"</span></span>  
  
3. <span data-ttu-id="5e0b4-113">「すべて」</span><span class="sxs-lookup"><span data-stu-id="5e0b4-113">"All"</span></span>  
  
 <span data-ttu-id="5e0b4-114">IDN 設定が"None"に設定されている場合、Uri.Host または Uri.DnsSafeHost によって変換は実行されません。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-114">When the IDN setting is set to "None", no conversions are performed by Uri.Host or Uri.DnsSafeHost.</span></span> <span data-ttu-id="5e0b4-115">IDN 設定を"All"、uri に設定するとします。ホストは、Unicode と uri に残ります。DnsSafeHost は Punycode に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-115">When the IDN setting is set to "All", uri.Host remains Unicode and uri.DnsSafeHost is converted to Punycode.</span></span> <span data-ttu-id="5e0b4-116">IDN 設定を"AllExceptIntranet"、uri を設定するとします。DnsSafeHost では、インターネット アドレスの Punycode に変換され、イントラネットのアドレスには Unicode のままです。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-116">When the IDN setting is set to "AllExceptIntranet", uri.DnsSafeHost is converted to Punycode for internet addresses, and remains Unicode for intranet addresses.</span></span> <span data-ttu-id="5e0b4-117">この設定は、正しい DNS 名解決にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-117">This setting is important for correct DNS name resolution.</span></span> <span data-ttu-id="5e0b4-118">Windows 8 以降のバージョンでは、この設定を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-118">Note this setting is not required to be configured for Windows 8 and newer versions.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5e0b4-119">Punycode を使用してアドレスをハードコーディングしないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-119">You should never hard-code an address using Punycode.</span></span> <span data-ttu-id="5e0b4-120">アドレスは、適用した構成設定に基づき、WCF によって自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-120">WCF will convert it for you based on the configuration settings you apply.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5e0b4-121">Unicode 文字を applicationHost.exe.config に追加する場合は、UTF-8 エンコードを使用してファイルを保存してください。</span><span class="sxs-lookup"><span data-stu-id="5e0b4-121">When adding Unicode characters to applicationHost.exe.config, save the file using the UTF-8 encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0b4-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e0b4-122">See also</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
