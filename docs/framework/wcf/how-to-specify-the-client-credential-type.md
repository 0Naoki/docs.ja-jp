---
title: "方法 : クライアントの資格情報の種類を指定する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 35c3b5ee429f7c9337fa3c3e3eb0d0476e3f56d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-client-credential-type"></a>方法 : クライアントの資格情報の種類を指定する
セキュリティ モード (トランスポートまたはメッセージ) を設定してから、クライアント資格情報の種類を指定することができます。 このプロパティでは、クライアントが認証時にサービスに提供する必要のある資格情報の種類を指定します。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]セキュリティ モード (必要な手順、クライアントの資格情報の種類を設定する前に) を参照してください設定[する方法: セキュリティ モードを設定](../../../docs/framework/wcf/how-to-set-the-security-mode.md)です。  
  
### <a name="to-set-the-client-credential-type-in-code"></a>コードでクライアント資格情報の種類を設定するには  
  
1.  サービスで使用されるバインドのインスタンスを作成します。 この例では、<xref:System.ServiceModel.WSHttpBinding> バインドを使用します。  
  
2.  <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> プロパティに適切な値を設定します。 この例では、メッセージ モードを使用します。  
  
3.  <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> プロパティに適切な値を設定します。 この例では、Windows 認証 (<xref:System.ServiceModel.MessageCredentialType.Windows>) を使用するように設定します。  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>構成でクライアント資格情報の種類を設定するには  
  
1.  追加、 [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)要素を構成ファイル。  
  
2.  子要素として追加して、 [\<バインド >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)要素。  
  
3.  適切なバインドを追加します。 この例では、 [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)要素。  
  
4.  追加、 [\<バインディング >](../../../docs/framework/misc/binding.md)要素、`name`属性を適切な値にします。 この例では、"SecureBinding" という名前を使用します。  
  
5.  `<security>` バインドを追加します。 `mode` 属性を適切な値に設定します。 この例では、`"Message"` に設定します。  
  
6.  セキュリティ モードによって、`<message>` 要素と `<transport>` 要素のどちらかを追加します。 `clientCredentialType` 属性を適切な値に設定します。 この例では `"Windows"` を使用します。  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>関連項目  
 [サービスのセキュリティ保護](../../../docs/framework/wcf/securing-services.md)  
 [方法: セキュリティ モードを設定する](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
