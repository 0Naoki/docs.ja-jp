---
title: セキュリティ保護されたメッセージ交換とセッション
ms.date: 03/30/2017
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
ms.openlocfilehash: d3fd1b82aa05e39e2555ea31955009ea0be881bd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2018
ms.locfileid: "50182048"
---
# <a name="secure-conversations-and-secure-sessions"></a>セキュリティ保護されたメッセージ交換とセッション
Windows Communication Foundation (WCF) の機能は、相互に認証し、暗号化とデジタル署名のプロセスについて合意する 2 つのエンドポイント間のセキュリティで保護されたセッションを確立する機能です。 たとえば、サービス エンドポイントは、クライアント エンドポイントに対して認証のために X.509 証明書に基づいたセキュリティ トークンを送信するよう要求する場合があります。 クライアントの認証が終わると、サービス エンドポイントはセキュリティ コンテキスト トークン (SCT: Security Context Token) をクライアントに返します。このセッションにおける後続のすべてのメッセージは、このセキュリティ トークンを使用してセキュリティ保護されます。 セキュリティで保護されたセッションが確立されると、SCT には対称キーが含まれるため、2 つのエンドポイント間で交換される一連のメッセージの効率が向上します。 X.509 証明書の基盤となる非対称キーでは、デジタル署名の生成やデータの暗号化を行う場合に、対称キーに比べて非常に大きな計算能力が必要になります。  
  
 ブートス トラップ ポリシー (の 6.2.7 で定義されている、 [Ws-securitypolicy](https://go.microsoft.com/fwlink/?LinkId=99817)標準)、チャネルをセキュリティで保護し、RST および RSTR/SCT 交換する前にクライアントを認証するために使用するメッセージ セキュリティ アサーションが含まれます。 特定の WCF の標準バインディングが、`Security.Message.EstablishSecurityContext`コントロールかどうかメッセージ交換をセキュリティで保護するプロパティを使用します。 カスタム バインドを使用して、ブートス トラップが使用するか、入れ子のセキュリティ バインド要素によって示されます[ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)または呼び出すことによって、構成ファイルで<xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>コード。  
  
 セッションの詳細については、次を参照してください。[を使用してセッション](../../../../docs/framework/wcf/using-sessions.md)します。  
  
## <a name="see-also"></a>関連項目  
 [セッション、インスタンス化、およびコンカレンシー](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [方法 : セッションを必要とするサービスを作成する](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
