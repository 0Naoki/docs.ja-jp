---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804449"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="aa6ac-101">WCF MsmqSecureHashAlgorithm の既定値が SHA256 になった</span><span class="sxs-lookup"><span data-stu-id="aa6ac-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aa6ac-102">説明</span><span class="sxs-lookup"><span data-stu-id="aa6ac-102">Details</span></span>|<span data-ttu-id="aa6ac-103">.NET Framework 4.7.1 以降では、Msmq メッセージの WCF での既定のメッセージ署名アルゴリズムは SHA256 です。</span><span class="sxs-lookup"><span data-stu-id="aa6ac-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="aa6ac-104">.NET Framework 4.7 以前のバージョンでは、既定のメッセージ署名アルゴリズムは SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="aa6ac-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="aa6ac-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="aa6ac-105">Suggestion</span></span>|<span data-ttu-id="aa6ac-106">.NET Framework 4.7.1 以降でこの変更に関する互換性の問題が発生した場合は、次の行を app.config ファイルの <code>&lt;runtime&gt;</code> セクションに追加することで、変更を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="aa6ac-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="aa6ac-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="aa6ac-107">Scope</span></span>|<span data-ttu-id="aa6ac-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="aa6ac-108">Minor</span></span>|
|<span data-ttu-id="aa6ac-109">Version</span><span class="sxs-lookup"><span data-stu-id="aa6ac-109">Version</span></span>|<span data-ttu-id="aa6ac-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="aa6ac-110">4.7.1</span></span>|
|<span data-ttu-id="aa6ac-111">型</span><span class="sxs-lookup"><span data-stu-id="aa6ac-111">Type</span></span>|<span data-ttu-id="aa6ac-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="aa6ac-112">Runtime</span></span>|
