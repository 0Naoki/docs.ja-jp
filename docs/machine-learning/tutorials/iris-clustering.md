---
title: クラスタリング ラーナーを使用して アヤメの花をクラスター化する - ML.NET
description: クラスタリングのシナリオで ML.NET を使用する方法について説明します
author: pkulikov
ms.author: johalex
ms.date: 02/19/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: d8d324cdcad793ac8ade8124f56734bade695421
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488163"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="39659-103">チュートリアル: ML.NET でクラスタリング ラーナーを使用してアヤメの花をクラスター化する</span><span class="sxs-lookup"><span data-stu-id="39659-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="39659-104">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="39659-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="39659-105">詳しくは、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39659-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="39659-106">このチュートリアルと、関連するサンプルでは、現時点では **ML.NET バージョン 0.10** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="39659-106">This tutorial and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="39659-107">詳細については、リリース ノート ([GitHub リポジトリの dotnet/machinelearning ](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39659-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="39659-108">このチュートリアルでは、ML.NET を使って[あやめのデータ セット](https://en.wikipedia.org/wiki/Iris_flower_data_set)の[クラスタリング モデル](../resources/tasks.md#clustering)を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="39659-108">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="39659-109">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39659-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="39659-110">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="39659-110">Understand the problem</span></span>
> - <span data-ttu-id="39659-111">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="39659-111">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="39659-112">データを準備する</span><span class="sxs-lookup"><span data-stu-id="39659-112">Prepare the data</span></span>
> - <span data-ttu-id="39659-113">データを読み込んで変換する</span><span class="sxs-lookup"><span data-stu-id="39659-113">Load and transform the data</span></span>
> - <span data-ttu-id="39659-114">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="39659-114">Choose a learning algorithm</span></span>
> - <span data-ttu-id="39659-115">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="39659-115">Train the model</span></span>
> - <span data-ttu-id="39659-116">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="39659-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39659-117">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="39659-117">Prerequisites</span></span>

- <span data-ttu-id="39659-118">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="39659-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="39659-119">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="39659-119">Understand the problem</span></span>

<span data-ttu-id="39659-120">この問題は、アヤメの花のセットを特徴に基づいて異なるグループに分類するというものです。</span><span class="sxs-lookup"><span data-stu-id="39659-120">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="39659-121">対象となる特徴は、がくの長さと幅および花弁の長さと幅です。</span><span class="sxs-lookup"><span data-stu-id="39659-121">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="39659-122">このチュートリアルでは、各花の種類は不明であるものとします。</span><span class="sxs-lookup"><span data-stu-id="39659-122">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="39659-123">特徴からデータ セットの構造を理解し、データのインスタンスがこの構造にどのように当てはまるかを予測します。</span><span class="sxs-lookup"><span data-stu-id="39659-123">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="39659-124">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="39659-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="39659-125">各花がどのグループに属するかわからないので、[教師なし機械学習](../resources/glossary.md#unsupervised-machine-learning)タスクを選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-125">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="39659-126">同じグループ内の要素同士の方が他のグループの要素より似ているようにデータ セットをグループに分割するので、[クラスタリング](../resources/tasks.md#clustering)機械学習タスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="39659-126">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="39659-127">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="39659-127">Create a console application</span></span>

1. <span data-ttu-id="39659-128">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="39659-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="39659-129">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="39659-130">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="39659-131">次に、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="39659-132">**[名前]** テキスト ボックスに「IrisFlowerClustering」と入力し、**[OK]** ボタンを選びます。</span><span class="sxs-lookup"><span data-stu-id="39659-132">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="39659-133">プロジェクトに *Data* という名前のディレクトリを作成して、データ セットとモデルのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="39659-133">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="39659-134">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="39659-135">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="39659-135">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="39659-136">**Microsoft.ML** NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="39659-136">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="39659-137">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="39659-138">[パッケージ ソース] として "nuget.org" を選択し、**[参照]** タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="39659-139">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="39659-140">データを準備する</span><span class="sxs-lookup"><span data-stu-id="39659-140">Prepare the data</span></span>

1. <span data-ttu-id="39659-141">[iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) データ セットをダウンロードし、前の手順で作成した *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="39659-141">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="39659-142">あやめのデータ セットについて詳しくは、Wikipedia の「[Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set)」(あやめのデータ セット) のページと、データ セットのソースである「[Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris)」(あやめのデータ セット) のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39659-142">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="39659-143">**ソリューション エクスプローラー**で、*iris.data* ファイルを右クリックして、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-143">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="39659-144">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="39659-144">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="39659-145">*Iris.data* ファイルには、次の値を表す 5 つの列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39659-145">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="39659-146">がくの長さ (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="39659-146">sepal length in centimetres</span></span>
- <span data-ttu-id="39659-147">がくの幅 (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="39659-147">sepal width in centimetres</span></span>
- <span data-ttu-id="39659-148">花弁の長さ (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="39659-148">petal length in centimetres</span></span>
- <span data-ttu-id="39659-149">花弁の幅 (センチメートル単位)</span><span class="sxs-lookup"><span data-stu-id="39659-149">petal width in centimetres</span></span>
- <span data-ttu-id="39659-150">アヤメの種類</span><span class="sxs-lookup"><span data-stu-id="39659-150">type of iris flower</span></span>

<span data-ttu-id="39659-151">クラスタリングの例が目的なので、このチュートリアルでは最後の列を無視します。</span><span class="sxs-lookup"><span data-stu-id="39659-151">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="39659-152">データ クラスを作成する</span><span class="sxs-lookup"><span data-stu-id="39659-152">Create data classes</span></span>

<span data-ttu-id="39659-153">入力データと予測のためのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="39659-153">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="39659-154">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-154">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="39659-155">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを「*IrisData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="39659-155">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="39659-156">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-156">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="39659-157">以下の `using` ディレクティブを新しいファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-157">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="39659-158">既存のクラス定義を削除し、`IrisData` クラスと `ClusterPrediction` クラスを定義する次のコードを *IrisData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-158">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="39659-159">`IrisData` は入力データ クラスであり、データ セットの各特徴の定義が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39659-159">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="39659-160">データ セット ファイル内のソース列のインデックスを指定するには、[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) 属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="39659-160">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="39659-161">`ClusterPrediction` クラスは、`IrisData` インスタンスに適用されたクラスタリング モデルの出力を表します。</span><span class="sxs-lookup"><span data-stu-id="39659-161">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="39659-162">[ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性を使って、`PredictedClusterId` フィールドを **PredictedLabel** 列に、`Distances` フィールドを **Score** 列に、それぞれバインドします。</span><span class="sxs-lookup"><span data-stu-id="39659-162">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="39659-163">クラスタリング タスクの場合、これらの列には次の意味があります。</span><span class="sxs-lookup"><span data-stu-id="39659-163">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="39659-164">**PredictedLabel** 列には、予測されたクラスターの ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39659-164">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="39659-165">**Score** 列には、クラスターの重心へのユークリッド距離を二乗した値の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39659-165">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="39659-166">配列の長さは、クラスターの数と同じです。</span><span class="sxs-lookup"><span data-stu-id="39659-166">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="39659-167">入力データと予測データのクラス内の浮動小数点値を表すには、`float` 型を使います。</span><span class="sxs-lookup"><span data-stu-id="39659-167">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="39659-168">データおよびモデルのパスを定義する</span><span class="sxs-lookup"><span data-stu-id="39659-168">Define data and model paths</span></span>

<span data-ttu-id="39659-169">*Program.cs* ファイルに戻り、データ セット ファイルと、モデルを保存するファイルへのパスを保持するために、2 つのフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-169">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="39659-170">`_dataPath` には、モデルのトレーニングに使用するデータ セットがあるファイルへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39659-170">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="39659-171">`_modelPath` には、トレーニング済みモデルが格納されるファイルへのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39659-171">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="39659-172">`Main` メソッドのすぐ上に次のコードを追加して、それらのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="39659-172">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="39659-173">上記のコードをコンパイルするには、*Program.cs* ファイルの先頭に次の `using` ディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-173">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="39659-174">ML のコンテキストの作成</span><span class="sxs-lookup"><span data-stu-id="39659-174">Create ML context</span></span>

<span data-ttu-id="39659-175">以下の追加の `using` ディレクティブを、*Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-175">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="39659-176">`Main` メソッドの `Console.WriteLine("Hello World!");` 行を次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="39659-176">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="39659-177"><xref:Microsoft.ML.MLContext?displayProperty=nameWithType> クラスは機械学習環境を表し、ログ記録のメカニズムとデータの読み込みのエントリ ポイント、モデルのトレーニング、予測、およびその他のタスクを提供します。</span><span class="sxs-lookup"><span data-stu-id="39659-177">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="39659-178">これは、概念的には Entity Framework での `DbContext` の使用に相当します。</span><span class="sxs-lookup"><span data-stu-id="39659-178">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="39659-179">データの読み込みのセットアップ</span><span class="sxs-lookup"><span data-stu-id="39659-179">Setup data loading</span></span>

<span data-ttu-id="39659-180">`Main` メソッドに次のコードを追加して、データを読み込む方法をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="39659-180">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SetupTextLoader)]

<span data-ttu-id="39659-181">`IrisData` クラス定義からデータセットのスキーマを推論するには、[generic `CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader%60%601(Microsoft.ML.DataOperationsCatalog,System.Boolean,System.Char,System.Boolean,System.Boolean,System.Boolean)) メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="39659-181">Use the [generic `CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader%60%601(Microsoft.ML.DataOperationsCatalog,System.Boolean,System.Char,System.Boolean,System.Boolean,System.Boolean)) method to infer the dataset schema from the `IrisData` class definition.</span></span>

<span data-ttu-id="39659-182">インスタンス化された <xref:Microsoft.ML.Data.TextLoader> インスタンスを使用して、<xref:Microsoft.Data.DataView.IDataView> インスタンスを作成します。これはトレーニング データ セットのデータ ソースを表します。</span><span class="sxs-lookup"><span data-stu-id="39659-182">Use instantiated <xref:Microsoft.ML.Data.TextLoader> instance to create an <xref:Microsoft.Data.DataView.IDataView> instance, which represents the data source for the training data set:</span></span>

[!code-csharp[Create IDataView](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateDataView)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="39659-183">学習パイプラインを作成する</span><span class="sxs-lookup"><span data-stu-id="39659-183">Create a learning pipeline</span></span>

<span data-ttu-id="39659-184">このチュートリアルでは、クラスタリング タスクの学習パイプラインは、次の 2 つの手順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="39659-184">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="39659-185">読み込まれた列を、クラスタリング トレーナーによって使用される 1 つの **Features** 列に連結します。</span><span class="sxs-lookup"><span data-stu-id="39659-185">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="39659-186"><xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> トレーナーを使用して、K- 平均法++ クラスタリング アルゴリズムを使用するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="39659-186">use a <xref:Microsoft.ML.Trainers.KMeans.KMeansPlusPlusTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="39659-187">`Main` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-187">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="39659-188">このコードは、データ セットを 3 つのクラスターに分割することを指定します。</span><span class="sxs-lookup"><span data-stu-id="39659-188">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="39659-189">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="39659-189">Train the model</span></span>

<span data-ttu-id="39659-190">前のセクションで追加した手順では、トレーニング用にパイプラインを準備しましたが、トレーニングは実行されていません。</span><span class="sxs-lookup"><span data-stu-id="39659-190">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="39659-191">次の行を `Main` メソッドに追加して、データの読み込みとモデルのトレーニングを実行します。</span><span class="sxs-lookup"><span data-stu-id="39659-191">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="39659-192">モデルを保存する</span><span class="sxs-lookup"><span data-stu-id="39659-192">Save the model</span></span>

<span data-ttu-id="39659-193">この時点で、既存または新規のどの .NET アプリケーションにも統合できるモデルができました。</span><span class="sxs-lookup"><span data-stu-id="39659-193">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="39659-194">モデルを .zip ファイルに保存するには、次のコードを `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-194">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="39659-195">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="39659-195">Use the model for predictions</span></span>

<span data-ttu-id="39659-196">予測を行うには、トランスフォーマー パイプラインを介して入力の型のインスタンスを受け取り、出力の型のインスタンスを生成する <xref:Microsoft.ML.PredictionEngine%602> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="39659-196">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="39659-197">次の行を `Main` メソッドに追加して、そのクラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="39659-197">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="39659-198">テスト データのインスタンスを格納するための `TestIrisData` クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="39659-198">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="39659-199">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-199">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="39659-200">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを「*TestIrisData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="39659-200">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="39659-201">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39659-201">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="39659-202">次の例に示すように、静的になるようにクラスを変更します。</span><span class="sxs-lookup"><span data-stu-id="39659-202">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="39659-203">このチュートリアルでは、このクラスで 1 つのあやめのデータ インスタンスを示します。</span><span class="sxs-lookup"><span data-stu-id="39659-203">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="39659-204">他のシナリオを追加してモデルで実験できます。</span><span class="sxs-lookup"><span data-stu-id="39659-204">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="39659-205">`TestIrisData` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-205">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="39659-206">指定した項目が属するクラスターを発見するには、*Program.cs* ファイルに戻り、次のコードを `Main` メソッドに追加します。</span><span class="sxs-lookup"><span data-stu-id="39659-206">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="39659-207">プログラムを実行し、指定したデータ インスタンスが含まれるクラスターと、そのインスタンスからクラスターの重心までの平方距離を確認します。</span><span class="sxs-lookup"><span data-stu-id="39659-207">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="39659-208">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="39659-208">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="39659-209">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="39659-209">Congratulations!</span></span> <span data-ttu-id="39659-210">これで、アヤメのクラスタリングの機械学習モデルを作成し、それを使用して予測を行うことができました。</span><span class="sxs-lookup"><span data-stu-id="39659-210">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="39659-211">このチュートリアルのソース コードは、[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="39659-211">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="39659-212">次の手順</span><span class="sxs-lookup"><span data-stu-id="39659-212">Next steps</span></span>

<span data-ttu-id="39659-213">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="39659-213">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="39659-214">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="39659-214">Understand the problem</span></span>
> - <span data-ttu-id="39659-215">適切な機械学習タスクを選択する</span><span class="sxs-lookup"><span data-stu-id="39659-215">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="39659-216">データを準備する</span><span class="sxs-lookup"><span data-stu-id="39659-216">Prepare the data</span></span>
> - <span data-ttu-id="39659-217">データを読み込んで変換する</span><span class="sxs-lookup"><span data-stu-id="39659-217">Load and transform the data</span></span>
> - <span data-ttu-id="39659-218">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="39659-218">Choose a learning algorithm</span></span>
> - <span data-ttu-id="39659-219">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="39659-219">Train the model</span></span>
> - <span data-ttu-id="39659-220">モデルを使用して予測を行う</span><span class="sxs-lookup"><span data-stu-id="39659-220">Use the model for predictions</span></span>

<span data-ttu-id="39659-221">学習を続けてその他のサンプルを確認するには、GitHub リポジトリをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39659-221">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="39659-222">dotnet/machinelearning GitHub リポジトリ</span><span class="sxs-lookup"><span data-stu-id="39659-222">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)
