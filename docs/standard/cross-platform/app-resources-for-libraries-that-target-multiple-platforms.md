---
title: "複数のプラットフォームを対象とするライブラリのアプリケーション リソース"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multiple platforms, resources for
- resources [.NET Framework]
- .NET Framework, resources when targeting multiple platforms
- resources, for multiple platforms
- targeting multiple platforms, resources for
ms.assetid: 72c76f0b-7255-4576-9261-3587f949669c
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 74cd3df645c2490bcf98533ca8846ddfb742f67f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="app-resources-for-libraries-that-target-multiple-platforms"></a>複数のプラットフォームを対象とするライブラリのアプリケーション リソース
.NET Framework を使用して[ポータブル クラス ライブラリ](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)プロジェクトの種類を複数のプラットフォームからクラス ライブラリ内のリソースにアクセスできることを確認してください。 このプロジェクトの種類は [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] で利用でき、.NET Framework クラス ライブラリの移植性の高いサブセットを対象としています。 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] を使用すると、デスクトップ アプリケーション、Silverlight アプリケーション、Windows Phone アプリケーション、および [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリケーションからライブラリにアクセスできます。  
  
 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] プロジェクトでは、アプリケーションで使用できるのは <xref:System.Resources> 名前空間内の非常に限られた型のサブセットのみですが、<xref:System.Resources.ResourceManager> クラスを使用してリソースを取得することはできます。 ただし、Visual Studio を使用してアプリケーションを作成する場合は、<xref:System.Resources.ResourceManager> クラス ライブラリを使用するのではなく、Visual Studio によって作成された厳密に型指定されたラッパーを使用する必要があります。  
  
 Visual Studio で厳密に型指定されたラッパーを作成、設定、メイン リソース ファイルの**アクセス修飾子**に Visual Studio リソース デザイナーで**パブリック**です。 これにより、厳密に型指定された ResourceManager ラッパーを含む [resourceFileName].designer.cs または [resourceFileName].designer.vb ファイルが作成されます。 厳密に型指定されたリソース ラッパーの使用に関する詳細についてを参照してください「を生成する、厳密に型指定されたリソース クラス」、 [Resgen.exe (リソース ファイル ジェネレーター)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)トピックです。  
  
## <a name="resource-manager-in-the-includenetportableincludesnet-portable-mdmd"></a>[!INCLUDE[net_portable](../../../includes/net-portable-md.md)] のリソース マネージャー  
 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] プロジェクトでは、リソースへのすべてのアクセスは <xref:System.Resources.ResourceManager> クラスによって処理されます。 <xref:System.Resources> や <xref:System.Resources.ResourceReader> などの <xref:System.Resources.ResourceSet> 名前空間の型には [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] プロジェクトからアクセスできないため、これらはリソースへのアクセスには使用できません。  
  
 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] プロジェクトには、以下の表に示す 4 つの <xref:System.Resources.ResourceManager> メンバーが含まれています。 これらのコンストラクターおよびメソッドを使用すると、<xref:System.Resources.ResourceManager> オブジェクトをインスタンス化して文字列リソースを取得できます。  
  
|`ResourceManager` のメンバー|説明|  
|------------------------------|-----------------|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.String%2CSystem.Reflection.Assembly%29>|<xref:System.Resources.ResourceManager> インスタンスを作成し、指定されたアセンブリ内にある、名前の指定されたリソース ファイルにアクセスします。|  
|<xref:System.Resources.ResourceManager.%23ctor%28System.Type%29>|指定された型に対応する <xref:System.Resources.ResourceManager> インスタンスを作成します。|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%29>|現在のカルチャに対する、名前の指定されたリソースを取得します。|  
|<xref:System.Resources.ResourceManager.GetString%28System.String%2CSystem.Globalization.CultureInfo%29>|指定されたカルチャに属する、名前の指定されたリソースを取得します。|  
  
 <xref:System.Resources.ResourceManager> の他の [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] メンバーを除外すると、シリアル化されたオブジェクト、文字列以外のデータ、およびイメージはリソース ファイルから取得できなくなります。 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]からリソースを使用するには、すべてのオブジェクト データを文字列形式で格納する必要があります。 たとえば、数値を文字列に変換してリソース ファイルに格納し、これらを取得して、数値データ型の `Parse` メソッドまたは `TryParse` メソッドを使用して数値に戻すことができます。 イメージや他のバイナリ データを文字列形式に変換するには <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> メソッドを呼び出し、バイト配列に戻すには <xref:System.Convert.FromBase64String%2A?displayProperty=nameWithType> メソッドを呼び出します。  
  
## <a name="the-includenetportableincludesnet-portable-mdmd-and-windows-store-apps"></a>[!INCLUDE[net_portable](../../../includes/net-portable-md.md)]と Windows ストア アプリ  
 [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] プロジェクトでは、リソースを .resx ファイルに格納します。これらのファイルはその後 .resources ファイルにコンパイルされ、コンパイル時にメイン アセンブリまたはサテライト アセンブリに埋め込まれます。 一方、[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリケーションではリソースを .resw ファイルに格納する必要があります。このファイルはその後、単一のパッケージ リソース インデックス (PRI) ファイルにコンパイルされます。 ただし、ファイル形式に互換性がないにもかかわらず、[!INCLUDE[net_portable](../../../includes/net-portable-md.md)] は [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリケーションで機能します。  
  
 クラス ライブラリを [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリケーションで使用するには、Windows ストア アプリケーション プロジェクトでその参照を追加します。 Visual Studio ではアセンブリのリソースを .resw ファイルに透過的に抽出し、それを使用して PRI ファイルを生成して、そこから [!INCLUDE[wrt](../../../includes/wrt-md.md)] がリソースを抽出できるようにします。 実行時に [!INCLUDE[wrt](../../../includes/wrt-md.md)] は [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] 内のコードを実行しますが、汎用性のあるクラス ライブラリのリソースは PRI ファイルから取得します。  
  
 ローカライズされたリソースが [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] プロジェクトに含まれている場合は、デスクトップ アプリケーション内のライブラリの場合と同様に、ハブ アンド スポーク モデルを使用してこれらを配置します。 メイン リソース ファイルおよびローカライズされたリソース ファイルを [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリケーションで使用するには、参照をメイン アセンブリに追加します。 コンパイル時に、Visual Studio はメイン リソース ファイルとローカライズされているリソース ファイルからリソースを個別の .resw ファイルに抽出します。 次に、実行時に [!INCLUDE[wrt](../../../includes/wrt-md.md)] によってアクセスされる単一の PRI ファイルに .resw ファイルをコンパイルします。  
  
<a name="NonLoc"></a>   
## <a name="example-non-localized-includenetportableincludesnet-portable-mdmd"></a>例: ローカライズされていない [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]  
 以下の単純なローカライズされていない [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] の例では、リソースを使用して列名を格納し、表形式データ用に予約する文字数を決定します。 この例では LibResources.resx という名前のファイルを使用して、次の表に示す文字列リソースを格納します。  
  
|リソース名|リソースの値|  
|-------------------|--------------------|  
|Born|Birthdate|  
|BornLength|12|  
|Hired|Hire Date|  
|HiredLength|12|  
|ID|ID|  
|ID.Length|12|  
|名前|名前|  
|NameLength|25|  
|タイトル|従業員データベース|  
  
 次のコード定義、`UILibrary`を名前付きリソース マネージャーのラッパーを使用してクラス`resources`Visual Studio によって生成されたときに、**アクセス修飾子**にファイルが変更されたり**パブリック**. UILibrary クラスは必要に応じて文字列データを解析します。 . このクラスは `MyCompany.Employees` 名前空間にあることに注意してください。  
  
 [!code-csharp[Conceptual.Resources.Portable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/uilibrary.cs#1)]
 [!code-vb[Conceptual.Resources.Portable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/uilibrary.vb#1)]  
  
 次のコードは、`UILibrary` クラスとそのリソースをコンソールモード アプリケーションからアクセスする方法を示します。 コンソール アプリケーションのプロジェクトに追加するには UILIbrary.dll への参照が必要です。  
  
 [!code-csharp[Conceptual.Resources.Portable#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program.cs#2)]
 [!code-vb[Conceptual.Resources.Portable#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module1.vb#2)]  
  
 次のコードは、`UILibrary` クラスとそのリソースを [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリケーションからアクセスする方法を示します。 Windows ストア アプリケーション プロジェクトに追加するには UILIbrary.dll への参照が必要です。  
  
 [!code-csharp[Conceptual.Resources.PortableMetro#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetro/cs/blankpage.xaml.cs#1)]  
  
## <a name="example-localized-includenetportableincludesnet-portable-mdmd"></a>例: ローカライズされている [!INCLUDE[net_portable](../../../includes/net-portable-md.md)]  
 以下のローカライズされている [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] の例には、フランス語 (フランス) と英語 (米国) のカルチャのリソースが含まれています。 英語 (米国) カルチャは、アプリの既定のカルチャです。テーブルで、そのリソースが示すように、[前のセクション](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md#NonLoc)です。 フランス語 (フランス) のカルチャのリソース ファイルは LibResources.fr-FR.resx という名前で、以下の表に示す文字列リソースで構成されています。 `UILibrary` クラスのソース コードは前のセクションに示すものと同じです。  
  
|リソース名|リソースの値|  
|-------------------|--------------------|  
|Born|Date de naissance|  
|BornLength|20|  
|Hired|Date embauché|  
|HiredLength|16|  
|ID|ID|  
|名前|Nom|  
|タイトル|Base de données des employés|  
  
 次のコードは、`UILibrary` クラスとそのリソースをコンソールモード アプリケーションからアクセスする方法を示します。 コンソール アプリケーションのプロジェクトに追加するには UILIbrary.dll への参照が必要です。  
  
 [!code-csharp[Conceptual.Resources.Portable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portable/cs/program2.cs#3)]
 [!code-vb[Conceptual.Resources.Portable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portable/vb/module2.vb#3)]  
  
 次のコードは、`UILibrary` クラスとそのリソースを [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリケーションからアクセスする方法を示します。 Windows ストア アプリケーション プロジェクトに追加するには UILIbrary.dll への参照が必要です。 静的な `ApplicationLanguages.PrimaryLanguageOverride` プロパティを使用してアプリケーションの優先言語をフランス語に設定します。  
  
 [!code-csharp[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.portablemetroloc/cs/blankpage.xaml.cs#1)]
 [!code-vb[Conceptual.Resources.PortableMetroLoc#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.portablemetroloc/vb/blankpage.xaml.vb#1)]  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Resources.ResourceManager>  
 [デスクトップ アプリケーションのリソース](../../../docs/framework/resources/index.md)  
 [リソースのパッケージ化と配置](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
