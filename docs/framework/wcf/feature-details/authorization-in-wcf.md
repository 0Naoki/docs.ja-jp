---
title: WCF での承認
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 8e7632dda1a1bd2b60b71c385ad58c23e4207534
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408317"
---
# <a name="authorization-in-wcf"></a>WCF での承認
承認は、サービスやファイルなどのリソースへのアクセスと権限を制御するプロセスです。 このセクションのトピックでは、Windows Communication Foundation (WCF) でさまざまな方法でこの基本的なタスクを実行する方法を説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [アクセス制御機構](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 推奨される使用して、WCF 承認メカニズムの概要を提供します。  
  
 [方法: PrincipalPermissionAttribute クラスでアクセスを制限する](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> を使用してサービスへのアクセスを制限するプロセスを示します。  
  
 [方法 : ASP.NET のロール プロバイダーとサービスを使用する](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] のロール プロバイダー機能を使用できるようにサービスを構成する手順について説明します。  
  
 [方法 : ASP.NET の承認マネージャー ロール プロバイダーとサービスを使用する](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] は、承認マネージャーを使って Web サイトの承認を管理できます。 WCF を活用できる同様に、 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization マネージャー クライアントの承認の組み合わせ。  
  
 [ID モデルを使用したクレームと承認の管理](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 ID モデル インフラストラクチャをクレーム ベースの承認に使用する際の基本について説明します。  
  
 [委任と偽装](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 委任と偽装の違いについて説明します。  
  
## <a name="reference"></a>参照  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>関連項目  
 [認証](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a>関連項目  
 [セキュリティの概要](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Windows Server App Fabric のセキュリティ モデル](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
