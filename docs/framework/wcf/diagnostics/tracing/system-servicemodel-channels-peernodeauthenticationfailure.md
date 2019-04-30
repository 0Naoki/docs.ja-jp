---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 315122914ebcb3e8e4d72c8d976026a126306168
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949891"
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a><span data-ttu-id="9104d-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span><span class="sxs-lookup"><span data-stu-id="9104d-102">System.ServiceModel.Channels.PeerNodeAuthenticationFailure</span></span>
<span data-ttu-id="9104d-103">潜在的な近隣ノードとのセキュリティ ハンドシェイクに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="9104d-103">The security handshake with a potential neighbor was not successful.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9104d-104">説明</span><span class="sxs-lookup"><span data-stu-id="9104d-104">Description</span></span>  
 <span data-ttu-id="9104d-105">このトレースは、セキュリティで保護された近隣との接続を確立するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="9104d-105">This trace occurs while attempting to establish a secure neighbor connection.</span></span> <span data-ttu-id="9104d-106">これは、資格情報が十分でないか間違っている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="9104d-106">This can happen due to insufficient or incorrect credentials.</span></span>  
  
 <span data-ttu-id="9104d-107">PeerChannel では、トークンの種類として、強力な識別手段である X.509 証明書だけを認識します。X.509 証明書は、実装可能な認証および承認の種類に基づいて強力な ID モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="9104d-107">PeerChannel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="9104d-108">PeerChannel では、パスワードを使用した簡単なアプリケーションもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9104d-108">PeerChannel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="9104d-109">パスワードは、セッションへのエントリを許可する目的でのみ使用できます。パスワードを使用して、メッセージの認証を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="9104d-109">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="9104d-110">これは、ピア グループで共有する共通鍵トークンをソース認証に使用することは困難かつ不適切であるためです。</span><span class="sxs-lookup"><span data-stu-id="9104d-110">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="9104d-111">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9104d-111">Troubleshooting</span></span>  
 <span data-ttu-id="9104d-112">すべての近隣ノードに適切なセキュリティ資格情報があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9104d-112">Ensure that all neighbors have the appropriate security credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9104d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9104d-113">See also</span></span>

- [<span data-ttu-id="9104d-114">ピア チャネルのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9104d-114">Peer Channel Security</span></span>](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)
- [<span data-ttu-id="9104d-115">トレース</span><span class="sxs-lookup"><span data-stu-id="9104d-115">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="9104d-116">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9104d-116">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9104d-117">管理と診断</span><span class="sxs-lookup"><span data-stu-id="9104d-117">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
