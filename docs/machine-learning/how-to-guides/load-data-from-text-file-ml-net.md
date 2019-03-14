---
title: 機械学習の処理のためにテキスト ファイルからデータを読み込む - ML.NET
description: ML.NET で機械学習モデルの構築、トレーニング、スコア付けに使用するデータを、テキスト ファイルから読み込む方法について説明します
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 62f68bd950d6a2c116baaba86ba7e27a10cec69d
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676292"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a><span data-ttu-id="ff78d-103">機械学習の処理のためにテキスト ファイルからデータを読み込む - ML.NET</span><span class="sxs-lookup"><span data-stu-id="ff78d-103">Load data from a text file for machine learning processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="ff78d-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff78d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ff78d-105">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff78d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ff78d-106">ここで説明する方法と関連サンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="ff78d-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="ff78d-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff78d-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="ff78d-108">`TextLoader` を使用して、テキスト ファイルからデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ff78d-108">`TextLoader` is used to load data from text files.</span></span> <span data-ttu-id="ff78d-109">データの列、型、およびテキスト ファイル内での位置を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff78d-109">You need to specify the data columns, their types, and their location in the text file.</span></span>

<span data-ttu-id="ff78d-110">ファイルの一部の列の読み込み、または同じ列の複数回の読み込みはまったく問題ないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ff78d-110">Note that it's perfectly acceptable to read some columns of a file, or read the same column multiple times.</span></span>

<span data-ttu-id="ff78d-111">[ファイルの例](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="ff78d-111">[Example file](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):</span></span>

```console
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```

<span data-ttu-id="ff78d-112">テキスト ファイルからデータを読み込むには:</span><span class="sxs-lookup"><span data-stu-id="ff78d-112">To load the data from a text file:</span></span>

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```