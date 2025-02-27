---
title: Entity Framework の概要
ms.date: 09/17/2018
ms.assetid: a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0
ms.openlocfilehash: 92aa7b9c1f163c0496a821cca375c8b7e1b21a5f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854345"
---
# <a name="entity-framework-overview"></a>Entity Framework の概要

Entity Framework は、データ指向のソフトウェアアプリケーションの開発をサポートする ADO.NET の一連のテクノロジです。 データ指向のアプリケーションの設計者と開発者はこれまで、2 つの大きく異なる目的を達成するために苦労してきました。 解決すべきビジネス上の問題のエンティティ、リレーションシップ、およびロジックをモデル化する一方で、データの格納と取得に使用するデータ エンジンに取り組む必要もあるからです。 データは複数のストレージ システムにまたがる場合があり、それぞれに独自のプロトコルが存在します。単一のストレージ システムを使用するアプリケーションであっても、ストレージ システムの要件と効率的で保守しやすいアプリケーション コードの記述要件のバランスを取る必要があります。

Entity Framework を使用すると、開発者は、顧客や顧客の住所など、ドメイン固有のオブジェクトおよびプロパティの形式でデータを操作できます。このデータがある基になるデータベーステーブルや列を考慮する必要はありません。保存. Entity Framework, を使用すると、開発者はデータを操作するときに高い抽象化レベルで作業ができ、従来のアプリケーションよりコードの少ないデータ指向アプリケーションの作成と保守が可能になります。 Entity Framework は .NET Framework のコンポーネントなので、Entity Framework アプリケーションは、バージョン 3.5 SP1 以降の .NET Framework がインストールされている任意のコンピューターで実行できます。

## <a name="give-life-to-models"></a>モデルの有効期間を指定する
 アプリケーションやサービスを構築するとき、従来からの一般的な設計アプローチは、アプリケーションまたはサービスをドメイン モデル、論理モデル、および物理モデルの 3 つの部分に分割する方法です。 ドメイン モデルでは、モデル化の対象となるシステムに存在するエンティティとリレーションシップを定義します。 リレーショナル データベースの論理モデルでは、外部キー制約を用いながらエンティティおよびリレーションシップをテーブルとして正規化します。 物理モデルでは、パーティション分割やインデックス化などのストレージ情報を指定することで、特定のデータ エンジンの機能に対応します。

 物理モデルは、パフォーマンスを向上させるためにデータベース管理者が調整しますが、アプリケーション コードを記述するプログラマは、主に SQL クエリを記述したりストアド プロシージャを呼び出したりすることによって論理モデルを扱うことに専念します。 ドメイン モデルは通常、アプリケーションの要件を収集して伝達するためのツールとして使用されます。プロジェクトの初期段階でのみ表示および検討され、その後ほとんど使用されないのが一般的です。 概念モデルの作成を省略し、実際にリレーショナル データベースのテーブル、列、およびキーを指定することから開始する開発チームも多く存在します。

 Entity Framework は、開発者がドメインモデル内のエンティティとリレーションシップ (Entity Framework の*概念*モデルと呼ばれます) のクエリを実行しながら、Entity Framework に依存してそれらの操作をデータソースに変換できるようにすることで、モデルの有効期間を提供します。-固有のコマンド。 これにより、特定のデータ ソースへの依存関係をアプリケーションにハードコーディングしなくても済みます。

 Code First を使用すると、概念モデルはコードのストレージ モデルにマッピングされます。 Entity Framework は、オブジェクトの種類と定義した追加の構成に基づいて概念モデルを推論できます。 マッピング メタデータは、ドメインの種類を定義した方法とコードで指定する追加の構成情報の組み合わせに基づいて実行時に生成されます。 Entity Framework は、メタデータに基づいて必要に応じてデータベースを生成します。 詳細については、「[概念モデルの作成とマッピング](https://go.microsoft.com/fwlink/?LinkID=235382)」を参照してください。

 Entity Data Model ツールでの作業時には、概念モデル、ストレージ モデル、およびこの 2 者間のマッピングは、XML ベースのスキーマで表され、名前の拡張子が同じファイルで定義されます。

- 概念モデルは概念スキーマ定義言語 (CSDL) で定義されます。 CSDL は、 [Entity Data Model](../entity-data-model.md)の Entity Framework の実装です。 ファイル拡張子は .csdl です。

- ストア スキーマ定義言語ファイル (SSDL) はストレージ モデル (論理モデルとも呼ばれる) を定義します。 ファイル拡張子は .ssdl です。

- マッピング仕様言語ファイル (MSL) はストレージ モデルと概念モデルの間のマッピングを定義します。 ファイル拡張子は .msl です。

ストレージ モデルとマッピングは、概念モデル、データ クラス、またはアプリケーション コードを変更することなく、必要に応じて変更できます。 ストレージ モデルはプロバイダー固有なので、データ ソースの違いを意識することなく一貫した概念モデルを扱うことができます。

Entity Framework は、これらのモデルファイルとマッピングファイルを使用して、概念モデルのエンティティおよびリレーションシップに対する作成、読み取り、更新、および削除操作を、データソース内の同等の操作に対して行います。 Entity Framework では、概念モデルのエンティティをデータソースのストアドプロシージャにマップすることもできます。 詳細については、「 [CSDL、SSDL、および MSL の仕様](./language-reference/csdl-ssdl-and-msl-specifications.md)」を参照してください。

## <a name="map-objects-to-data"></a>オブジェクトをデータにマップする
 オブジェクト指向プログラミングには、データ ストレージ システムと対話するという難題があります。 クラスの編成はリレーショナル データベース テーブルの編成に似ている場合がありますが、完全に一致するわけではありません。 正規化された複数のテーブルと単一のクラスが対応する場合も多く、クラス間のリレーションシップとテーブル間のリレーションシップとで表現方法が異なる場合もあります。 たとえば、販売注文の顧客を表すために、`Order` クラスは `Customer` クラスのインスタンスへの参照が含まれているプロパティを使用する一方で、データベースの `Order` テーブル行には `Customer` テーブルの主キー値に対応する値がある外部キー列 (または列セット) が含まれている場合があります。 `Customer` クラスには `Orders` クラスのインスタンスのコレクションが含まれている `Order` という名前のプロパティがありますが、データベースの `Customer` テーブルに同等の列がない場合などです。 Entity Framework を使用すると、開発者はこの方法でリレーションシップを表すことができます。また、データベースで表現されているリレーションシップをより密接にモデル化することもできます。

 既存のソリューションでは、"インピーダンスのミスマッチ" とよく呼ばれるこの差異を、オブジェクト指向のクラスやプロパティをリレーショナル テーブルやリレーショナル列にマップするだけで埋めようとしてきました。 このような従来のアプローチを採用するのではなく、Entity Framework は、論理モデルのリレーショナルテーブル、列、および外部キーの制約を概念モデルのエンティティとリレーションシップにマップします。 これにより、さらに柔軟にオブジェクトを定義して論理モデルを最適化することが可能になります。 Entity Data Model ツールは、概念モデルに基づいて拡張可能なデータクラスを生成します。 このクラスは、開発者が追加するメンバーで拡張できる部分クラスです。 既定では、特定の概念モデルに対して生成されるクラスは、エンティティをオブジェクトとして具体化したり変更を追跡したり保存したりするサービスを提供する基本クラスから派生します。 開発者はこのようなクラスを使用して、エンティティとリレーションシップを、アソシエーションによって関連付けられたオブジェクトとして操作できます。 また、開発者は、概念モデルに生成されるクラスをカスタマイズすることもできます。 詳細については、「[オブジェクトの操作](working-with-objects.md)」を参照してください。

## <a name="access-and-change-entity-data"></a>エンティティデータへのアクセスと変更

Entity Framework は単なるオブジェクト リレーショナル マッピング ソリューションではなく、基本的には、概念モデルのエンティティとリレーションシップとして表されるデータにアプリケーションからアクセスして変更できるようにするためのものです。 Entity Framework は、モデルファイルとマッピングファイルの情報を使用して、概念モデルで表されるエンティティ型に対するオブジェクトクエリをデータソース固有のクエリに変換します。 クエリ結果は、Entity Framework が管理するオブジェクトに具体化されます。 Entity Framework には、概念モデルに対してクエリを実行し、オブジェクトを返すための次の方法が用意されています。

- LINQ to Entities。 概念モデルで定義されているエンティティ型に対してクエリを実行するための統合言語クエリ (LINQ) のサポートを提供します。 詳細については、「 [LINQ to Entities](./language-reference/linq-to-entities.md)」を参照してください。

- [!INCLUDE[esql](../../../../../includes/esql-md.md)]。 概念モデルのエンティティを直接操作し、Entity Data Model の概念をサポートする、ストレージに依存しない SQL の言語。 [!INCLUDE[esql](../../../../../includes/esql-md.md)]は、EntityClient プロバイダーを使用して実行されるオブジェクトクエリとクエリの両方で使用されます。 詳細については、「 [Entity SQL の概要](./language-reference/entity-sql-overview.md)」を参照してください。

Entity Framework には、EntityClient データプロバイダーが含まれています。 このプロバイダーは接続を管理し、エンティティクエリをデータソース固有のクエリに変換し、エンティティデータをオブジェクトに具体化するために Entity Framework が使用するデータリーダーを返します。 オブジェクトの具体化が不要であれば、アプリケーションで [!INCLUDE[esql](../../../../../includes/esql-md.md)] クエリを実行して返された読み取り専用のデータ リーダーを使用できるようにすることで、EntityClient プロバイダーを標準の ADO.NET データ プロバイダーと同様に使用することもできます。 詳細については、「 [Entity Framework 用の EntityClient プロバイダー](entityclient-provider-for-the-entity-framework.md)」を参照してください。

次の図は、データにアクセスするための Entity Framework アーキテクチャを示しています。

![Entity Framework アーキテクチャダイアグラム](./media/wd-efarchdiagram.gif "wd_EFArchDiagram")

Entity Data Model ツールは、概念モデルのエンティティコンテナー `System.Data.Objects.ObjectContext`を`System.Data.Entity.DbContext`表すまたはから派生したクラスを生成できます。 このオブジェクト コンテキストは、変更の追跡や ID、同時実行、およびリレーションシップの管理などの機能を提供します。 また、このクラスは、データ ソースに挿入、更新、および削除を書き込む `SaveChanges` メソッドも公開します。 このような変更は、クエリと同様に、システムによって自動的に生成されるコマンドで行うことも、特定のストアド プロシージャを使用するように指定することもできます。

## <a name="data-providers"></a>データ プロバイダー

プロバイダー `EntityClient`は、概念エンティティおよびリレーションシップの観点からデータにアクセスすることによって、ADO.NET プロバイダーモデルを拡張します。 [!INCLUDE[esql](../../../../../includes/esql-md.md)] を使用するクエリを実行します。 [!INCLUDE[esql](../../../../../includes/esql-md.md)] は、`EntityClient` がデータベースと通信する基盤となるクエリ言語を提供します。 詳細については、「 [Entity Framework 用の EntityClient プロバイダー](entityclient-provider-for-the-entity-framework.md)」を参照してください。

Entity Framework には、正規のコマンドツリーをサポートする更新された SqlClient Data Provider が含まれています。 詳細については、「 [Entity Framework の SqlClient](sqlclient-for-the-entity-framework.md)」を参照してください。

## <a name="entity-data-model-tools"></a>Entity data model ツール

Entity Framework ランタイムと共に、Visual Studio にはマッピングツールとモデリングツールが含まれています。 詳細については、「[モデリングとマッピング](modeling-and-mapping.md)」を参照してください。

## <a name="learn-more"></a>詳細情報

Entity Framework の詳細については、以下を参照してください。

[はじめに](getting-started.md)-簡単な Entity Framework アプリケーションを作成する方法を示す[クイックスタート](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))を使用して、迅速に稼働させる方法について説明します。

[Entity Framework 用語](terminology.md)-Entity Data Model と Entity Framework によって導入され、Entity Framework ドキュメントで使用される用語の多くを定義します。

[Entity Framework リソース](resources.md)-概念説明のトピックへのリンク、および Entity Framework アプリケーションを構築するための外部のトピックとリソースへのリンクを示します。

## <a name="see-also"></a>関連項目

- [ADO.NET Entity Framework](index.md)
