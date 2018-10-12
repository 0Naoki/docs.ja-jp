---
title: 相互運用アプリケーションの配置
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], interop
- strong-named assemblies, interop applications
- unsigned assemblies
- private assemblies
- exposing COM components to .NET Framework
- interoperation with unmanaged code, deploying applications
- shared assemblies
- COM interop, deploying applications
- interoperation with unmanaged code, exposing COM components
- signed assemblies
- COM interop, exposing COM components
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4689c52dee84e2a310f0ddb39d0874c273081bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389419"
---
# <a name="deploying-an-interop-application"></a>相互運用アプリケーションの配置
通常、相互運用アプリケーションには、.NET クライアント アセンブリ、個別の COM タイプ ライブラリを表す 1 つ以上の相互運用機能アセンブリ、および 1 つ以上の登録済み COM コンポーネントが含まれています。 Visual Studio および [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] には、タイプ ライブラリを相互運用機能アセンブリにインポートして変換するためのツールが用意されています。詳細については、「[タイプ ライブラリのアセンブリとしてのインポート](importing-a-type-library-as-an-assembly.md)」を参照してください。 相互運用アプリケーションを配置する方法には、次の 2 つがあります。  
  
-   埋め込まれた相互運用機能型を使用する: [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 以降では、相互運用機能アセンブリから実行可能ファイルに型情報を埋め込むようにコンパイラに指示できます。 コンパイラは、アプリケーションで使用する型情報のみを埋め込みます。 アプリケーションで相互運用機能アセンブリを配置する必要はありません。 この手法を使用することをお勧めします。  
  
-   相互運用機能アセンブリを配置する: 相互運用機能アセンブリへの標準の参照を作成できます。 この場合、アプリケーションで相互運用機能アセンブリを展開する必要があります。 この手法を採用し、プライベートの COM コンポーネントを使用しない場合は、常に、マネージ コードに組み込む予定の COM コンポーネントの作成者によって発行されたプライマリ相互運用機能アセンブリ (PIA) を参照します。 プライマリ相互運用機能アセンブリの生成と使用の詳細については、「[プライマリ相互運用機能](https://msdn.microsoft.com/library/b977a8be-59a0-40a0-a806-b11ffba5c080(v=vs.100))」を参照してください。  
  
 埋め込まれた相互運用機能型を使用すると、配置を簡単に行うことができます。 特別な操作を行う必要はありません。 ここからは、アプリケーションで相互運用機能アセンブリを配置するシナリオについて説明します。  
  
## <a name="deploying-interop-assemblies"></a>相互運用機能アセンブリの配置  
 アセンブリには厳密な名前を付けることができます。 厳密な名前のアセンブリには、一意の識別子を提供する、発行者の公開キーが含まれています。 発行者は、**/keyfile** オプションを使用して、[タイプ ライブラリ インポーター (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) で生成されたアセンブリに署名できます。 署名付きアセンブリは、グローバル アセンブリ キャッシュにインストールできます。 署名のないアセンブリは、プライベート アセンブリとしてユーザーのコンピューターにインストールする必要があります。  
  
### <a name="private-assemblies"></a>プライベート アセンブリ  
 プライベートに使用するアセンブリをインストールするには、アプリケーションの実行可能ファイルと、インポートされた COM 型を含む相互運用機能アセンブリの両方を同じディレクトリ構造にインストールする必要があります。 別個のアプリケーション ディレクトリに配置された Client1.exe と Client2.exe によってプライベートに使用される、署名のない相互運用機能アセンブリを次の図に示します。 この例の LOANLib.dll という相互運用機能アセンブリは、2 回インストールされています。  
  
 ![ディレクトリ構造と Windows レジストリ](media/comdeployprivate.gif "comdeployprivate")  
プライベートに配置する場合のディレクトリ構造とレジストリ エントリ  
  
 アプリケーションに関連付けられているすべての COM コンポーネントを、Windows レジストリにインストールする必要があります。 この図の Client1.exe と Client2.exe が別のコンピューターにインストールされている場合は、両方のコンピューターで COM コンポーネントを登録する必要があります。  
  
### <a name="shared-assemblies"></a>共有アセンブリ  
 複数のアプリケーションによって共有されるアセンブリは、グローバル アセンブリ キャッシュと呼ばれる集中化されたリポジトリにインストールする必要があります。 .NET クライアントは、署名され、グローバル アセンブリ キャッシュにインストールされた、相互運用機能アセンブリの同じコピーにアクセスできます。 プライマリ相互運用機能アセンブリの生成と使用の詳細については、「[プライマリ相互運用機能](https://msdn.microsoft.com/library/b977a8be-59a0-40a0-a806-b11ffba5c080(v=vs.100))」を参照してください。  
  
## <a name="see-also"></a>参照  
 [.NET Framework への COM コンポーネントの公開](exposing-com-components.md)  
 [タイプ ライブラリのアセンブリとしてのインポート](importing-a-type-library-as-an-assembly.md)  
 [マネージ コードでの COM 型の使用](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))  
 [相互運用プロジェクトのコンパイル](compiling-an-interop-project.md)
