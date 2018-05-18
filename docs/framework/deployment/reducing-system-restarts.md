---
title: .NET Framework 4.5 のインストール中のシステム再起動の削減
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, reducing system restarts
- installing .NET Framework
- installation [.NET Framework]
ms.assetid: 7aa8cb72-dee9-4716-ac54-b17b9ae8218f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e54dcb585c06f2bf49c41f763e03e5624a033442
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="reducing-system-restarts-during-net-framework-45-installations"></a>.NET Framework 4.5 のインストール中のシステム再起動の削減
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] インストーラーは[再起動マネージャー](http://go.microsoft.com/fwlink/?LinkId=231425)を使用して、インストール中のシステムの再起動をできる限り回避します。 アプリケーションのセットアップ プログラムで .NET Framework をインストールする場合は、再起動マネージャーとやり取りしてこの機能を利用できます。 詳しくは、「[方法: .NET Framework 4.5 インストーラーの進行状況を表示する](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)」をご覧ください。  
  
## <a name="reasons-for-a-restart"></a>再起動の理由  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] のインストールにおいて、.NET Framework 4 アプリケーションがインストール中に使用されている場合は、システムの再起動が必要になります。 これは、[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] が .NET Framework 4 のファイルを置き換え、インストール中にこれらのファイルが使用可能になっている必要があるためです。 多くの場合、再起動は使用中の .NET Framework 4 アプリケーションをプリエンティブに検出し、終了することで回避できます。 ただし、一部のシステム アプリケーションは終了しないでください。 このような場合、再起動は回避できません。  
  
## <a name="end-user-experience"></a>エンド ユーザー エクスペリエンス  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] の完全インストールを行っているエンド ユーザーには、使用中の .NET Framework 4 アプリケーションをインストーラーが検出した場合にシステムの再起動を回避する機会が与えられます。 メッセージには、実行中の .NET Framework 4 アプリケーションがすべて一覧表示され、インストール前にこれらのアプリケーションを終了するオプションが表示されます。 ユーザーが終了を確認すると、これらのアプリケーションはインストーラーによってシャットダウンされ、システムの再起動が回避されます。 一定時間内にユーザーがメッセージに応答しなかった場合、インストールはアプリケーションを終了せずに続行します。  
  
 実行中のアプリケーションが終了してもシステムの再起動が必要な状況を再起動マネージャーが検出した場合、メッセージは表示されません。  
  
 ![[アプリケーションの終了] ダイアログ](../../../docs/framework/deployment/media/closeapplicationdialog.png "CloseApplicationDialog")  
使用中の .NET Framework アプリケーションを終了するためのプロンプト  
  
## <a name="using-a-chained-installer"></a>チェーンされたインストーラーの使用  
 アプリケーションと共に .NET Framework を再配布し、ただし独自のセットアップ プログラムと UI を使用する場合は、.NET Framework のセットアップ プロセスをセットアップ プロセスにインクルード (チェーン) できます。 チェーンされたインストールについて詳しくは、「[配置ガイド (開発者向け)](../../../docs/framework/deployment/deployment-guide-for-developers.md)」をご覧ください。 チェーンされたインストールでのシステムの再起動を減らすために、.NET Framework インストーラーは、終了するアプリケーションの一覧をセットアップ プログラムに提示します。 セットアップ プログラムは、メッセージ ボックスなどのユーザー インターフェイスを経由してこの情報をユーザーに提供し、ユーザーの応答を取得して、応答を .NET Framework インストーラーに渡す必要があります。 チェーンされたインストーラーの例については、「[方法: .NET Framework 4.5 インストーラーの進行状況を表示する](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)」をご覧ください。  
  
 チェーンされたインストーラーを使用しているときに、終了するアプリケーションに対して独自のメッセージ ボックスを非表示にする場合は、.NET Framework セットアップ プロセスをチェーンするときに、コマンド ラインで `/showrmui` と `/passive` のオプションを使用できます。 これらのオプションを一緒に使用すると、システムの再起動を避けるために終了できるアプリケーションを閉じるためのメッセージ ボックスがインストーラーによって表示されます。 このメッセージ ボックスは、完全なユーザー インターフェイスの下でも、パッシブ モードでも同じように動作します。 .NET Framework 再頒布可能パッケージのコマンドライン オプションの完全なセットについては、「[配置ガイド (開発者向け)](../../../docs/framework/deployment/deployment-guide-for-developers.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [配置](../../../docs/framework/deployment/index.md)  
 [配置ガイド (開発者向け)](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [方法: .NET Framework 4.5 インストーラーの進行状況を表示する](../../../docs/framework/deployment/how-to-get-progress-from-the-dotnet-installer.md)
