---
title: クライアント検証
ms.date: 03/30/2017
ms.assetid: f0c1f805-1a81-4d0d-a112-bf5e2e87a631
ms.openlocfilehash: 3f8b5ec3f8652ef50bbda3456669f2abf456472b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45624867"
---
# <a name="client-validation"></a>クライアント検証
サービスは頻繁にメタデータを公開し、クライアント プロキシの型を自動的に生成して構成できるようにします。 サービスが信頼できない場合、クライアント アプリケーションでは、セキュリティ、トランザクション、サービス コントラクトの型などに関して、メタデータがクライアント アプリケーションのポリシーに合致しているかどうか検証する必要があります。 次のサンプルでは、サービス エンドポイントを検証するクライアント エンドポイントの動作を記述して、サービス エンドポイントを安全に使用できることを確認する方法を示します。  
  
 サービスは 4 つのサービス エンドポイントを公開します。 1 つ目は WSDualHttpBinding を使用するエンドポイント、2 つ目は NTLM 認証を使用するエンドポイント、3 つ目はトランザクション フローを有効にするエンドポイント、4 つ目は証明書ベースの認証を使用するエンドポイントです。  
  
 クライアントは <xref:System.ServiceModel.Description.MetadataResolver> クラスを使用してサービスのメタデータを取得します。 クライアントは検証動作を使用して、二重バインディング、NTLM 認証、およびトランザクション フローを禁止するポリシーを適用します。 各<xref:System.ServiceModel.Description.ServiceEndpoint>サービスのメタデータをクライアント アプリケーションからインポートされたインスタンスのインスタンスを追加する、`InternetClientValidatorBehavior`エンドポイント動作を<xref:System.ServiceModel.Description.ServiceEndpoint>への接続に Windows Communication Foundation (WCF) クライアントを使用する前にエンドポイント。 動作の `Validate` メソッドはサービスで操作が呼び出される前に実行され、`InvalidOperationExceptions` をスローすることによってクライアントのポリシーを適用します。  
  
### <a name="to-build-the-sample"></a>サンプルをビルドするには  
  
1.  ソリューションをビルドする手順については、 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>サンプルを同じコンピューターで実行するには  
  
1.  管理特権を使用して Visual Studio コマンド プロンプトを開き、サンプルのインストール フォルダーから Setup.bat を実行します。 これにより、サンプルの実行に必要なすべての証明書がインストールされます。  
  
2.  サービス アプリケーションを \service\bin\Debug で実行します。  
  
3.  クライアント アプリケーションを \client\bin\Debug で実行します。 クライアント アクティビティがクライアントのコンソール アプリケーションに表示されます。  
  
4.  クライアントとサービスが通信できるようにされていない場合[トラブルシューティングのヒント](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)します。  
  
5.  サンプルの使用が終わったら、Cleanup.bat を実行して証明書を削除してください。 他のセキュリティ サンプルでも同じ証明書を使用します。  
  
### <a name="to-run-the-sample-across-computers"></a>サンプルを複数のコンピューターで実行するには  
  
1.  サーバーで管理者特権で実行、Visual Studio コマンド プロンプトで次のように入力します。`setup.bat service`します。 実行している`setup.bat`で、`service`引数が、コンピューターの完全修飾ドメイン名でサービス証明書を作成し、Service.cer というファイルに、サービス証明書をエクスポートします。  
  
2.  サーバーで、App.config を編集して新しい証明書の名前を反映します。 つまり、変更、`findValue`属性、 [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)コンピューターの完全修飾ドメイン名に要素。  
  
3.  Service.cer ファイルを、サービス ディレクトリからクライアント コンピューターのクライアント ディレクトリにコピーします。  
  
4.  クライアントでは、管理者特権と型を持つ Visual Studio コマンド プロンプトを開き`setup.bat client`します。 実行している`setup.bat`で、`client`引数は、Client.com というクライアント証明書を作成し、Client.cer というファイルに、クライアント証明書をエクスポートします。  
  
5.  client.cs ファイルで、MEX エンドポイントと、既定のサーバー証明書を設定するための `findValue` のアドレス値を、サービスの新しいアドレスに合わせて変更します。 そのためには、localhost をサーバーの完全修飾ドメイン名に置き換えます。 再ビルドします。  
  
6.  Client.cer ファイルを、クライアント ディレクトリからサーバーのサービス ディレクトリにコピーします。  
  
7.  クライアント上で、管理特権を使用して Visual Studio コマンド プロンプトを開き、ImportServiceCert.bat を実行します。 これにより、サービス証明書が Service.cer ファイルから CurrentUser - TrustedPeople ストアにインポートされます。  
  
8.  サーバー上で、管理特権を使用して Visual Studio コマンド プロンプトを開き、ImportClientCert.bat を実行します。 これにより、クライアント証明書が Client.cer ファイルから LocalMachine - TrustedPeople ストアにインポートされます。  
  
9. サービス コンピューターの Visual Studio でサービス プロジェクトをビルドし、service.exe を実行します。  
  
10. クライアント コンピューターで、client.exe を実行します。  
  
    1.  クライアントとサービスが通信できるようにされていない場合[トラブルシューティングのヒント](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)します。  
  
### <a name="to-clean-up-after-the-sample"></a>サンプルの実行後にクリーンアップするには  
  
-   サンプルの実行が終わったら、サンプル フォルダーにある Cleanup.bat を実行します。  
  
    > [!NOTE]
    >  このサンプルを複数のコンピューターで実行している場合、このスクリプトはサービス証明書をクライアントから削除しません。 コンピューター間での証明書の使用、必ず、CurrentUser - でインストールされているサービス証明書をオフにする WCF サンプルを実行している場合 TrustedPeople を格納します。 削除するには、コマンド `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>. For example: certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com` を実行します。  
  
## <a name="see-also"></a>関連項目  
 [メタデータを使用する](../../../../docs/framework/wcf/feature-details/using-metadata.md)
