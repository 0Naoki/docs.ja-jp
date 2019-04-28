---
title: コマンド ツリーの構造
ms.date: 03/30/2017
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
ms.openlocfilehash: 08a67c8d181188cbc14c6f60876a7e26cd6de25a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763985"
---
# <a name="the-shape-of-the-command-trees"></a><span data-ttu-id="259a9-102">コマンド ツリーの構造</span><span class="sxs-lookup"><span data-stu-id="259a9-102">The Shape of the Command Trees</span></span>

<span data-ttu-id="259a9-103">SQL 生成モジュールは、指定された入力クエリ コマンド ツリー式に基づいてバックエンドに固有の SQL クエリを生成します。</span><span class="sxs-lookup"><span data-stu-id="259a9-103">The SQL generation module is responsible for generating a backend specific SQL query based on a given input query command tree expression.</span></span> <span data-ttu-id="259a9-104">ここでは、クエリ コマンド ツリーの特性、プロパティ、および構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="259a9-104">This section discusses the characteristics, properties, and structure of the query command trees.</span></span>

## <a name="query-command-trees-overview"></a><span data-ttu-id="259a9-105">クエリ コマンド ツリーの概要</span><span class="sxs-lookup"><span data-stu-id="259a9-105">Query Command Trees Overview</span></span>

<span data-ttu-id="259a9-106">クエリ コマンド ツリーは、クエリのオブジェクト モデル表現です。</span><span class="sxs-lookup"><span data-stu-id="259a9-106">A query command tree is an object model representation of a query.</span></span> <span data-ttu-id="259a9-107">クエリ コマンド ツリーには、次の 2 つの目的があります。</span><span class="sxs-lookup"><span data-stu-id="259a9-107">Query command trees serve two purposes:</span></span>

- <span data-ttu-id="259a9-108">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] に対して指定された入力クエリを表現する。</span><span class="sxs-lookup"><span data-stu-id="259a9-108">To express an input query that is specified against the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>

- <span data-ttu-id="259a9-109">プロバイダーに対して提供された出力クエリを表現し、バックエンドに対するクエリを記述する。</span><span class="sxs-lookup"><span data-stu-id="259a9-109">To express an output query that is given to a provider and describes a query against the backend.</span></span>

<span data-ttu-id="259a9-110">クエリ コマンド ツリーでは、入れ子のコレクションおよび型操作、エンティティが特定の型であるかどうかのライク チェック、型に基づくセットのフィルター処理のサポートなど、SQL:1999 準拠のクエリよりも高度なセマンティックがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="259a9-110">Query command trees support richer semantics than SQL:1999 compliant queries, including support for working with nested collections and type operations, like checking whether an entity is of a particular type, or filtering sets based on a type.</span></span>

<span data-ttu-id="259a9-111">DBQueryCommandTree.Query プロパティは、クエリのロジックを記述する式ツリーのルートです。</span><span class="sxs-lookup"><span data-stu-id="259a9-111">The DBQueryCommandTree.Query property is the root of the expression tree that describes the query logic.</span></span> <span data-ttu-id="259a9-112">DBQueryCommandTree.Parameters プロパティには、クエリで使用されるパラメーターのリストが格納されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-112">The DBQueryCommandTree.Parameters property contains a list of parameters that are used in the query.</span></span> <span data-ttu-id="259a9-113">式ツリーは、DbExpression オブジェクトから構成されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-113">The expression tree is composed of DbExpression objects.</span></span>

<span data-ttu-id="259a9-114">DbExpression オブジェクトは、計算を表します。</span><span class="sxs-lookup"><span data-stu-id="259a9-114">A DbExpression object represents some computation.</span></span> <span data-ttu-id="259a9-115">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] では、定数、変数、関数、コンストラクター、およびフィルターや結合のような標準の関係演算子など、クエリ式を構成するための式がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="259a9-115">Several kinds of expressions are provided by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] for composing query expressions, including constants, variables, functions, constructors, and standard relational operators like filter and join.</span></span> <span data-ttu-id="259a9-116">すべての DbExpression オブジェクトには、その式によって生成される結果の型を表す ResultType プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="259a9-116">Every DbExpression object has a ResultType property that represents the type of the result produced by that expression.</span></span> <span data-ttu-id="259a9-117">この型は、TypeUsage として表されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-117">This type is expressed as a TypeUsage.</span></span>

## <a name="shapes-of-the-output-query-command-tree"></a><span data-ttu-id="259a9-118">出力クエリ コマンド ツリーの構造</span><span class="sxs-lookup"><span data-stu-id="259a9-118">Shapes of the Output Query Command Tree</span></span>

<span data-ttu-id="259a9-119">出力クエリ コマンド ツリーは、リレーショナル (SQL) クエリを詳細に表しており、クエリ コマンド ツリーに適用される規則よりもはるかに厳密な規則に従います。</span><span class="sxs-lookup"><span data-stu-id="259a9-119">Output query command trees closely represent relational (SQL) queries and adhere to much stricter rules than those that apply to query command trees.</span></span> <span data-ttu-id="259a9-120">通常、出力クエリ コマンド ツリーの構造は、SQL に簡単に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="259a9-120">They typically contain constructs that are easily translated to SQL.</span></span>

<span data-ttu-id="259a9-121">入力コマンド ツリーは、ナビゲーション プロパティ、エンティティ間のアソシエーション、および継承をサポートする概念モデルに対して表現されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-121">Input command trees are expressed against the conceptual model, which supports navigation properties, associations among entities, and inheritance.</span></span> <span data-ttu-id="259a9-122">出力コマンド ツリーは、ストレージ モデルに対して表現されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-122">Output command trees are expressed against the storage model.</span></span> <span data-ttu-id="259a9-123">入力コマンド ツリーでは入れ子になったコレクションを射影することができますが、出力コマンド ツリーではこれはできません。</span><span class="sxs-lookup"><span data-stu-id="259a9-123">Input command trees allow you to project nested collections, but output command trees do not.</span></span>

<span data-ttu-id="259a9-124">出力クエリ コマンド ツリーは、利用可能な DbExpression オブジェクトのサブセットを使用して作成されます。また、そのサブセットに含まれる一部の式も、使用法が制限されています。</span><span class="sxs-lookup"><span data-stu-id="259a9-124">Output query command trees are built using a subset of the available DbExpression objects and even some expressions in that subset have restricted usage.</span></span>

<span data-ttu-id="259a9-125">型の操作、特定の式が特定の型であるかどうかのライク チェック、または型に基づくセットのフィルター処理は、出力コマンド ツリーにはありません。</span><span class="sxs-lookup"><span data-stu-id="259a9-125">Type operations, like checking whether a given expression is of a particular type or filtering sets based on a type, are not present in output command trees.</span></span>

<span data-ttu-id="259a9-126">出力コマンド ツリーでは、ブール値を返す式だけが、射影のために使用されます。また、フィルターや case ステートメントのように述語を必要とする式内の述語のみを対象として使用されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-126">In output command trees, only expressions that return Boolean values are used for projections and only for predicates in expressions requiring a predicate, like a filter or a case statement.</span></span>

<span data-ttu-id="259a9-127">出力クエリ コマンド ツリーのルートは、DbProjectExpression オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="259a9-127">The root of an output query command trees is a DbProjectExpression object.</span></span>

### <a name="expression-types-not-present-in-output-query-command-trees"></a><span data-ttu-id="259a9-128">出力クエリ コマンド ツリーに存在しない式の型</span><span class="sxs-lookup"><span data-stu-id="259a9-128">Expression Types Not Present in Output Query Command Trees</span></span>

<span data-ttu-id="259a9-129">次の式の型は出力クエリ コマンド ツリー内では無効であり、プロバイダーによって処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="259a9-129">The following expression types are not valid in an output query command tree and do not need to be handled by providers:</span></span>

- <span data-ttu-id="259a9-130">DbDerefExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-130">DbDerefExpression</span></span>

- <span data-ttu-id="259a9-131">DbEntityRefExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-131">DbEntityRefExpression</span></span>

- <span data-ttu-id="259a9-132">DbRefKeyExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-132">DbRefKeyExpression</span></span>

- <span data-ttu-id="259a9-133">DbIsOfExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-133">DbIsOfExpression</span></span>

- <span data-ttu-id="259a9-134">DbOfTypeExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-134">DbOfTypeExpression</span></span>

- <span data-ttu-id="259a9-135">DbRefExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-135">DbRefExpression</span></span>

- <span data-ttu-id="259a9-136">DbRelationshipNavigationExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-136">DbRelationshipNavigationExpression</span></span>

- <span data-ttu-id="259a9-137">DbTreatExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-137">DbTreatExpression</span></span>

### <a name="expression-restrictions-and-notes"></a><span data-ttu-id="259a9-138">式の制限および注意事項</span><span class="sxs-lookup"><span data-stu-id="259a9-138">Expression Restrictions and Notes</span></span>

<span data-ttu-id="259a9-139">式を出力クエリ コマンド ツリー内で使用する場合、多くの式は、その使用方法が制限を受けます。</span><span class="sxs-lookup"><span data-stu-id="259a9-139">Many expressions can only be used in a restricted manner in output query command trees:</span></span>

#### <a name="dbfunctionexpression"></a><span data-ttu-id="259a9-140">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-140">DbFunctionExpression</span></span>

<span data-ttu-id="259a9-141">次の種類の関数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="259a9-141">The following function types can be passed:</span></span>

- <span data-ttu-id="259a9-142">Edm 名前空間で認識される正規関数</span><span class="sxs-lookup"><span data-stu-id="259a9-142">Canonical functions that are recognized by the Edm namespace.</span></span>

- <span data-ttu-id="259a9-143">BuiltInAttribute で認識される組み込み関数 (ストア関数)</span><span class="sxs-lookup"><span data-stu-id="259a9-143">Built-in (store) functions that are recognized by the BuiltInAttribute.</span></span>

- <span data-ttu-id="259a9-144">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="259a9-144">User-defined functions.</span></span>

<span data-ttu-id="259a9-145">正規関数 (を参照してください[正規関数](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)詳細については) の一部として指定されて、 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]、し、プロバイダは、これらの仕様に基づいて正規の関数の実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="259a9-145">Canonical functions (see [Canonical Functions](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) for more information) are specified as part of the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], and providers should supply implementations for canonical functions based on those specifications.</span></span> <span data-ttu-id="259a9-146">ストア関数は、対応するプロバイダー マニフェスト内の仕様に基づいています。</span><span class="sxs-lookup"><span data-stu-id="259a9-146">Store functions are based on the specifications in the corresponding provider manifest.</span></span> <span data-ttu-id="259a9-147">ユーザー定義の関数は、SSDL 内の仕様に基づいています。</span><span class="sxs-lookup"><span data-stu-id="259a9-147">User defined functions are based on specifications in the SSDL.</span></span>

<span data-ttu-id="259a9-148">また、NiladicFunction 属性を持つ関数は引数を持たないため、末尾のかっこを省略して変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="259a9-148">Also, functions having the NiladicFunction attribute have no arguments and should be translated without the parenthesis at the end.</span></span>  <span data-ttu-id="259a9-149">つまり、  *\<functionName >* の代わりに *\<functionName > ()* します。</span><span class="sxs-lookup"><span data-stu-id="259a9-149">That is, to *\<functionName>* instead of *\<functionName>()*.</span></span>

#### <a name="dbnewinstanceexpression"></a><span data-ttu-id="259a9-150">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-150">DbNewInstanceExpression</span></span>

<span data-ttu-id="259a9-151">DbNewInstanceExpression は、次の 2 つのケースでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="259a9-151">DbNewInstanceExpression can only occur in the following two cases:</span></span>

- <span data-ttu-id="259a9-152">DbProjectExpression の Projection プロパティとして使用する場合。</span><span class="sxs-lookup"><span data-stu-id="259a9-152">As the Projection property of DbProjectExpression.</span></span>  <span data-ttu-id="259a9-153">使用時には、次の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-153">When used as such the following restrictions apply:</span></span>

  - <span data-ttu-id="259a9-154">結果型は行型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="259a9-154">The result type must be a row type.</span></span>

  - <span data-ttu-id="259a9-155">それぞれの引数は、プリミティブ型の結果を生成する式です。</span><span class="sxs-lookup"><span data-stu-id="259a9-155">Each of its arguments is an expression that produces a result with a primitive type.</span></span> <span data-ttu-id="259a9-156">通常、それぞれの引数は、スカラー式 (たとえば、DbVariableReferenceExpression に対する PropertyExpression)、関数呼び出し、または DbVariableReferenceExpression に対する DbPropertyExpression や関数呼び出しの算術演算です。</span><span class="sxs-lookup"><span data-stu-id="259a9-156">Typically, each argument is a scalar expression, like a PropertyExpression over a DbVariableReferenceExpression, a function invocation, or an arithmetic computation of the DbPropertyExpression over a DbVariableReferenceExpression or a function invocation.</span></span> <span data-ttu-id="259a9-157">ただし、スカラー サブクエリを表す式は、DbNewInstanceExpression の引数リスト内にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="259a9-157">However, an expression representing a scalar subquery can also occur in the list of arguments for a DbNewInstanceExpression.</span></span> <span data-ttu-id="259a9-158">スカラー サブクエリを表す式は 1 つの行と DbElementExpression オブジェクトのルートを含むプリミティブ型の 1 つの列を返すサブクエリを表す式ツリー</span><span class="sxs-lookup"><span data-stu-id="259a9-158">An expression that represents a scalar subquery is an expression tree that represents a subquery that returns exactly one row and one column of a primitive type with a DbElementExpression object root</span></span>

- <span data-ttu-id="259a9-159">戻り値の型がコレクション型の場合。この場合は、引数として提供される式の新しいコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="259a9-159">With a collection return type, in which case it defines a new collection of the expressions provided as arguments.</span></span>

#### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="259a9-160">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-160">DbVariableReferenceExpression</span></span>

<span data-ttu-id="259a9-161">DbVariableReferenceExpression は、DbPropertyExpression ノードの子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="259a9-161">A DbVariableReferenceExpression has to be a child of DbPropertyExpression node.</span></span>

#### <a name="dbgroupbyexpression"></a><span data-ttu-id="259a9-162">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-162">DbGroupByExpression</span></span>

<span data-ttu-id="259a9-163">DbGroupByExpression の Aggregates プロパティは、DbFunctionAggregate 型の要素のみを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="259a9-163">The Aggregates property of a DbGroupByExpression can only have elements of type DbFunctionAggregate.</span></span> <span data-ttu-id="259a9-164">それ以外の集計型はありません。</span><span class="sxs-lookup"><span data-stu-id="259a9-164">There are no other aggregate types.</span></span>

#### <a name="dblimitexpression"></a><span data-ttu-id="259a9-165">DbLimitExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-165">DbLimitExpression</span></span>

<span data-ttu-id="259a9-166">Limit プロパティには、DbConstantExpression または DbParameterReferenceExpression のみを設定できます。</span><span class="sxs-lookup"><span data-stu-id="259a9-166">The property Limit can only be a DbConstantExpression or a DbParameterReferenceExpression.</span></span> <span data-ttu-id="259a9-167">また、.NET Framework Version 3.5 では、WithTies プロパティは常に false です。</span><span class="sxs-lookup"><span data-stu-id="259a9-167">Also property WithTies is always false as of version 3.5 of the .NET Framework.</span></span>

#### <a name="dbscanexpression"></a><span data-ttu-id="259a9-168">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="259a9-168">DbScanExpression</span></span>

<span data-ttu-id="259a9-169">出力コマンド ツリーで使用する場合、DbScanExpression は、テーブル、ビュー、または EntitySetBase::Target によって表されるストア クエリに対するスキャンを効果的に表します。</span><span class="sxs-lookup"><span data-stu-id="259a9-169">When used in output command trees, the DbScanExpression effectively represents a scan over a table, a view, or a store query, represented by EntitySetBase::Target.</span></span>

<span data-ttu-id="259a9-170">メタデータ プロパティの"Defining Query"、ターゲットが null 以外の場合、クエリを表しますが、ストア スキーマ定義で指定されているプロバイダーの特定の言語 (またはダイアレクト) でメタデータ プロパティ内のクエリ テキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="259a9-170">If the metadata property "Defining Query" of the target is non-null, then it represents a query, the query text for which is provided in that metadata property in the provider’s specific language (or dialect) as specified in the store schema definition.</span></span>

<span data-ttu-id="259a9-171">ターゲットの "Defining Query" メタデータ プロパティが null の場合、ターゲットは、テーブルまたはビューを表します。</span><span class="sxs-lookup"><span data-stu-id="259a9-171">Otherwise, the target represents a table or a view.</span></span> <span data-ttu-id="259a9-172">スキーマ プレフィックスは、"Schema"メタデータ プロパティでない場合 null の場合、それ以外の場合は、エンティティ コンテナー名。</span><span class="sxs-lookup"><span data-stu-id="259a9-172">Its schema prefix is either in the "Schema" metadata property, if not null, otherwise is the entity container name.</span></span>  <span data-ttu-id="259a9-173">テーブルまたはビュー名は、いずれか、"Table"メタデータ プロパティでは、ない場合 null の場合、エンティティの Name プロパティの基本設定、それ以外の場合です。</span><span class="sxs-lookup"><span data-stu-id="259a9-173">The table or view name is either the "Table" metadata property, if not null, otherwise the Name property of the entity set base.</span></span>

<span data-ttu-id="259a9-174">これらのプロパティはすべて、ストア スキーマ定義ファイル (SSDL) 内の対応する EntitySet の定義に基づいています。</span><span class="sxs-lookup"><span data-stu-id="259a9-174">All these properties originate from the definition of the corresponding EntitySet in the store schema definition file (the SSDL).</span></span>

### <a name="using-primitive-types"></a><span data-ttu-id="259a9-175">プリミティブ型の使用</span><span class="sxs-lookup"><span data-stu-id="259a9-175">Using Primitive Types</span></span>

<span data-ttu-id="259a9-176">プリミティブ型を出力コマンド ツリー内で参照する場合、通常は概念モデルのプリミティブ型で参照します。</span><span class="sxs-lookup"><span data-stu-id="259a9-176">When primitive types are referenced in output command trees, they are typically referenced in the conceptual model's primitive types.</span></span> <span data-ttu-id="259a9-177">ただし、一部の式に対しては、対応するストア プリミティブ型がプロバイダーで必要となります。</span><span class="sxs-lookup"><span data-stu-id="259a9-177">However, for certain expressions, providers need the corresponding store primitive type.</span></span> <span data-ttu-id="259a9-178">このような式の例としては、DbCastExpression があります。また、null を対応する型にキャストする必要がある場合は、DbNullExpression も同様です。</span><span class="sxs-lookup"><span data-stu-id="259a9-178">Examples of such expressions include DbCastExpression and possibly DbNullExpression, if the provider needs to cast the null to the corresponding type.</span></span> <span data-ttu-id="259a9-179">こうした式では、プロバイダーは、プリミティブ型の種類およびファセットに基づいて、プロバイダー型へマッピングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="259a9-179">In these cases, providers should do the mapping to the provider type based on the primitive type kind and its facets.</span></span>

## <a name="see-also"></a><span data-ttu-id="259a9-180">関連項目</span><span class="sxs-lookup"><span data-stu-id="259a9-180">See also</span></span>

- [<span data-ttu-id="259a9-181">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="259a9-181">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
