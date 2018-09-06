---
title: ルーティング コントラクト
ms.date: 03/30/2017
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
ms.openlocfilehash: 73d303c95a636f5e90f256272726c08c581d6fdf
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785993"
---
# <a name="routing-contracts"></a>ルーティング コントラクト
ルーティング コントラクトは、ルーティング サービスが処理できるメッセージ パターンを定義します。  各コントラクトは型指定されておらず、サービスは、メッセージ スキーマやアクションを認識していない場合でもメッセージを受信できます。 このため、ルーティング サービスは、ルーティングされる基盤のメッセージの詳細構成を追加することなく、メッセージをジェネリックにルーティングできます。  
  
## <a name="routing-contracts"></a>ルーティング コントラクト  
 ルーティング サービスには汎用 WCF メッセージ オブジェクトを使用できるため、コントラクトを選ぶ場合の最大の検討事項は、クライアントとサービスとの通信時に使用されるチャネルの形状です。 ルーティング サービスは、メッセージを処理するときに対象型メッセージ ポンプを使用するため、通常、受信コントラクトの形状は、送信コントラクトの形状と一致します。 ただし、サービス モデルのディスパッチャーがなど、ディスパッチャーが要求/応答チャネルでは、双方向チャネルに変換または必要ありません (つまり使用されていないときに、チャネルからセッションのサポートを削除、形を変更できる場合があります。、ときに**SessionMode.Allowed**、変換、 **IInputSessionChannel**に、 **IInputChannel**)。  
  
 これらのメッセージ ポンプをサポートするために、ルーティング サービスでは、<xref:System.ServiceModel.Routing> 名前空間にコントラクトを用意しています。これらのコントラクトは、ルーティング サービスが使用するサービス エンドポイントを定義するときに、使用される必要があります。 これらのコントラクトは型指定されていないため、どのようなメッセージの種類やアクションでも受信でき、ルーティング サービスは、特定のメッセージ スキーマを認識しない場合でもメッセージを処理できます。 ルーティング サービスによって使用されるコントラクトの詳細については、次を参照してください。[ルーティング コントラクト](../../../../docs/framework/wcf/feature-details/routing-contracts.md)します。  
  
 ルーティング サービスによって提供されるコントラクトは、<xref:System.ServiceModel.Routing> 名前空間に含まれています。これらのコントラクトは、次の表のとおりです。  
  
|コントラクト|形式|チャネル形状|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel -> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputSessionChannel -> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel -> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|IDuplexSessionChannel -> IDuplexSessionChannel|  
  
## <a name="see-also"></a>関連項目  
 [ルーティング サービス](https://msdn.microsoft.com/library/5ac8718c-bcef-456f-bfd5-1e60a30d6eaa)  
 [ルーティングの概要](../../../../docs/framework/wcf/feature-details/routing-introduction.md)
