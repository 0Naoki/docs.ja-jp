---
title: 拡張保護認証のサンプルの ReadMe
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d45271180b7f00ba78d106f2a93d5860375da5f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495081"
---
# <a name="readme-for-extended-protection-authentication-sample"></a>拡張保護認証のサンプルの ReadMe
拡張保護を攻撃者 (、「- 内の中間」) がクライアントの資格情報をインターセプトし、クライアントの目的のサーバーのセキュリティで保護されたリソースにアクセスするために使用、中間の (MITM) 攻撃を防ぐためにセキュリティ イニシアチブです。  
  
 詳細については、次を参照してください。[認証の概要の拡張保護](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md)です。  
  
> [!NOTE]
>  このサンプルは、IIS でホストされた場合にのみ機能します。 このサンプルは HTTPS をサポートしないので、Visual Studio Development Server 上では機能しません。  
  
## <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップしてビルドし、実行するには  
  
1.  [プログラムの追加と削除] の [Windows の機能] から IIS をインストールします。  
  
2.  Windows 機能の Windows 認証を有効にします ([インターネット インフォメーション サービス] -> [World Wide Web サービス] -> [セキュリティ] -> [Windows 認証])。  
  
3.  Windows 機能の HTTP アクティブ化を有効にします ([Microsoft .NET Framework 3.5.1] -> [Windows Communication Foundation HTTP Activation])。  
  
4.  このサンプルを実行するには、サーバーとの安全なチャネルを確立する必要のあるクライアントが必要なので、インターネット インフォメーション サービス (IIS) マネージャーからインストールすることのできるサーバー証明書が存在する必要があります。  
  
    1.  IIS マネージャーを開いて、[機能表示] タブから [サーバー証明書] を選択します。  
  
    2.  このサンプルをテストする目的で、自己署名証明書を作成できます  (インターネット エクスプローラーで証明書の安全性に関するプロンプトが表示されないようにする場合は、信頼されたルート証明機関ストアに証明書をインストールできます)。  
  
5.  既定の Web サイトの操作ウィンドウに移動します。 [サイトの編集] の [バインド] をクリックします。 存在しない場合は、種類として HTTPS を追加します。ポート番号に 443 を指定し、前の手順で作成した SSL 証明書を割り当てます。  
  
6.  サービスをビルドします。 (プロジェクト プロパティで指定されたビルド後のアクションから) IIS に仮想ディレクトリが作成され、サービスを Web ホスト サービスにするために必要な dll、.svc、および構成ファイルがコピーされます。  
  
7.  IIS マネージャーを開きます。 前の手順で作成した仮想ディレクトリ (ExtendedProtection) を右クリックして、[アプリケーションへの変換] を選択します。  
  
8.  この仮想ディレクトリの認証モジュールを IIS マネージャーで開き、Windows 認証を有効にします。  
  
9. このサンプルでは対応する ExtendedProtection 設定が [常に] に設定されているので、この仮想ディレクトリの Windows 認証の [詳細設定] を開き、[必須] に設定します。  
  
10. ブラウザー ウィンドウから URL にアクセスして、サービスをテストできます。 コンピューター間でこの URL にアクセスする場合は、すべての受信 HTTP および HTTPS 通信に対してファイアウォールが開かれていることを確認してください。  
  
11. クライアント構成ファイルを開きのフル コンピューター名を指定、\<クライアント >-\<エンドポイント >-アドレスの属性、<< full_machine_name >> を置換します。  
  
12. クライアントを実行します。 クライアントがセキュリティで保護されたチャネルを確立し、エンドポイント保護を使用してサービスと通信します。
