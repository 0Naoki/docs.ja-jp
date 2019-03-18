---
title: ML.NET パイプライン処理中の中間データ値を検査する
description: ML.NET 機械学習パイプラインの処理中に実際の中間データ値を検査する方法について説明します。
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 362cb9351c3cb77b6aa67d59154854e882869ad9
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "57843417"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a><span data-ttu-id="7b9e9-103">ML.NET パイプライン処理中の中間データ値を検査する</span><span class="sxs-lookup"><span data-stu-id="7b9e9-103">Inspect intermediate data values during ML.NET pipeline processing</span></span>

> [!NOTE]
> <span data-ttu-id="7b9e9-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="7b9e9-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="7b9e9-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="7b9e9-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="7b9e9-108">実験中に、特定の時点のデータ処理結果を観察し、検証することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-108">During the experiment, you may want to observe and validate the data processing results at a given point.</span></span> <span data-ttu-id="7b9e9-109">これは簡単ではありません。なぜなら、ML.NET の操作は、データの 'promise' であるオブジェクトの遅延構築だからです。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-109">This isn't easy since ML.NET operations are lazy, constructing objects that are 'promises' of data.</span></span>

<span data-ttu-id="7b9e9-110">`GetColumn<T>` 拡張メソッドを使用すると、中間データを検査できます。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-110">The `GetColumn<T>` extension method lets you inspect the intermediate data.</span></span> <span data-ttu-id="7b9e9-111">1 つのデータ列の内容が `IEnumerable` として返されます。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-111">It returns the contents of one data column as an `IEnumerable`.</span></span>

<span data-ttu-id="7b9e9-112">`GetColumn<T>` 拡張メソッドを使用する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-112">The following example shows how to use the `GetColumn<T>` extension method:</span></span>

<span data-ttu-id="7b9e9-113">[ファイルの例](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="7b9e9-113">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span></span>

<!-- markdownlint-disable MD010 -->
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="7b9e9-114">このクラスは次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="7b9e9-114">Our class is defined as follows:</span></span>

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
