---
title: "キャッシュ ポリシーの相互作用 — 最大有効期間と最大期限延長"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: baec376501feb70e4a9ceb3f33ac66fa76b91ac1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a>キャッシュ ポリシーの相互作用 — 最大有効期間と最大期限延長
最新のコンテンツをクライアント アプリケーションに確実に返すために、クライアントのキャッシュ ポリシーとサーバーの再検証要件の相互作用によって、常に最も保守的なキャッシュ ポリシーが適用されます。 このトピックの例はいずれも、1 月 1 日にキャッシュされ、1 月 4 日に期限切れになるリソースのキャッシュ ポリシーを示しています。  
  
 以下の例では、最大期限延長値 (`maxStale`) と最大有効期間 (`maxAge`) を組み合わせて使用しています。  
  
-   キャッシュ ポリシーで `maxAge` = 5 日間が設定され、`maxStale` 値が指定されていない場合は、`maxAge` 値に従い、コンテンツは 1 月 6 日まで使用できます。 ただし、サーバーの再検証要件に従い、コンテンツは 1 月 4 日に期限切れになります。 コンテンツの有効期限の方が保守的 (早い) ので、`maxAge` ポリシーよりも優先されます。 そのため、コンテンツは 1 月 4 日に期限切れになり、最大有効期間に達していないとしても、必ず再検証されます。  
  
-   キャッシュ ポリシーで `maxAge` = 5 日間と `maxStale` = 3 日間が設定されている場合、`maxAge` 値に従い、コンテンツは 1 月 6 日まで使用できます。 `maxStale` 値に従い、コンテンツは 1 月 7 日まで使用できます。 そのため、コンテンツは 1 月 6 日に再検証されます。  
  
-   キャッシュ ポリシーで `maxAge` = 5 日間と `maxStale` = 1 日間が設定されている場合、`maxAge` 値に従い、コンテンツは 1 月 6 日まで使用できます。 `maxStale` 値に従い、コンテンツは 1 月 5 日まで使用できます。 そのため、コンテンツは 1 月 5 日に再検証されます。  
  
 最大有効期間がコンテンツの有効期限よりも短い場合、より保守的なキャッシュ動作が常に優先され、最大期限延長値の影響はありません。 以下の例は、コンテンツの期限切れ前に最大有効期間 (`maxAge`) に達したときの最大期限延長 (`maxStale`) 値の影響を示しています。  
  
-   キャッシュ ポリシーで `maxAge` = 1 日間に設定され、`maxStale` 値が指定されていない場合、期限切れ前でも、コンテンツは 1 月 2 日に再検証されます。  
  
-   キャッシュ ポリシーで `maxAge` = 1 日、`maxStale` = 3 日間が設定されている場合、より保守的なポリシー設定を適用するために、コンテンツは 1 月 2 日に再検証されます。  
  
-   キャッシュ ポリシーで `maxAge` = 1 日、`maxStale` = 1 日が設定されている場合、コンテンツは 1 月 2 日に再検証されます。  
  
## <a name="see-also"></a>関連項目  
 [ネットワーク アプリケーションのキャッシュ管理](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [キャッシュ ポリシー](../../../docs/framework/network-programming/cache-policy.md)  
 [場所ベースのキャッシュ ポリシー](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [時間ベースのキャッシュ ポリシー](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [ネットワーク アプリケーションでのキャッシュの構成](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [キャッシュ ポリシーの相互作用 - 最大有効期間と最小鮮度](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)
