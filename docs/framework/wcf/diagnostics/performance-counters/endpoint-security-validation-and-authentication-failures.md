---
title: 'エンドポイント : セキュリティ検証エラーと認証エラー'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
author: BrucePerlerMS
ms.openlocfilehash: f7cd2268eefa0176ab71a3d5d3bc82c178664742
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075097"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="49dc9-102">エンドポイント : セキュリティ検証エラーと認証エラー</span><span class="sxs-lookup"><span data-stu-id="49dc9-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="49dc9-103">カウンター名 : セキュリティ検証と認証エラー</span><span class="sxs-lookup"><span data-stu-id="49dc9-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="49dc9-104">説明</span><span class="sxs-lookup"><span data-stu-id="49dc9-104">Description</span></span>  
 <span data-ttu-id="49dc9-105">このカウンターは、"承認されていないセキュリティ呼び出し" カウンターでカウントの対象とならないセキュリティ上の問題が原因でメッセージが拒否されるたびにインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="49dc9-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="49dc9-106">この問題には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="49dc9-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="49dc9-107">メッセージからクライアント トークンを読み取ることができない。</span><span class="sxs-lookup"><span data-stu-id="49dc9-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="49dc9-108">クライアント トークンが認証に失敗した (無効なパスワード)。</span><span class="sxs-lookup"><span data-stu-id="49dc9-108">Client token has failed authentication (bad password).</span></span>  
  
-   <span data-ttu-id="49dc9-109">署名の検証に失敗した (メッセージが改変された)。</span><span class="sxs-lookup"><span data-stu-id="49dc9-109">Signature verification has failed (the message has been tampered).</span></span>  
  
-   <span data-ttu-id="49dc9-110">メッセージが以前のメッセージと重複する。この現象はリプレイ攻撃中に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="49dc9-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="49dc9-111">復号化に失敗した。</span><span class="sxs-lookup"><span data-stu-id="49dc9-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="49dc9-112">一部の必須要素 (タイムスタンプ、暗号化データ ブロックなど) がメッセージにない。</span><span class="sxs-lookup"><span data-stu-id="49dc9-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="49dc9-113">TLSNEGO/SPNEGO ハンドシェイク中にエラーが発生した。</span><span class="sxs-lookup"><span data-stu-id="49dc9-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
