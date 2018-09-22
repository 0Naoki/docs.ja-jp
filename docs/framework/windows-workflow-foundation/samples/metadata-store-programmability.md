---
title: メタデータ ストアのプログラム性
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 9f30fcdac131b8749a4d165875b9bbb584542843
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2018
ms.locfileid: "46583575"
---
# <a name="metadata-store-programmability"></a>メタデータ ストアのプログラム性
メタデータ ストアは、実行時に任意のメタデータを CLR 属性の形式で型に関連付けることができる [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]機能です。 これにより、実行時コンポーネントと対応するデザイン時コンポーネントの間の疎結合、および実行時コンポーネントに影響を与えることなくデザイン時コンポーネントを変更する機能が実現します。 このサンプルでは、属性を実行時の型に適用することで、メタデータ ストアを使用して制御できないソースをプログラミングする方法を示します。 通常使用されるこの用語は、ホスト アプリケーションによって型セットのメタデータが登録されることを示します。  
  
 出力内に、追加の予期しない属性 <xref:System.Runtime.InteropServices.GuidAttribute> がある場合があります。 これはメタデータ API の使用時に追加されるもので、サンプルの実行には影響しません。  
  
 このサンプルでは、次の方法を示します。  
  
## <a name="demonstrates"></a>使用例  
  
-   メタデータ ストア API を使用して属性を挿入する方法。  
  
-   コールバック メカニズムを使用してメタデータの登録を遅らせる方法。  
  
## <a name="to-set-up-build-and-run-the-sample"></a>サンプルをセットアップ、ビルド、および実行するには
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、ProgrammingMetadataStore.sln ソリューション ファイルを開きます。  
  
2.  ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。  
  
3.  ソリューションを実行するには、F5 キーを押します。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`