---
title: ML.NET を GitHub の問題の多クラス分類シナリオで使用する
description: GitHub の問題を分類し、それを特定の領域に割り当てるための多クラス分類シナリオで、ML.NET を使用する方法について説明します。
ms.date: 02/14/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 80f4e322ee94e9c3a41bd1c3945383f89f4347d0
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333522"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="8d8cd-103">チュートリアル: ML.NET を、GitHub の問題を分類する多クラス分類シナリオで使用する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="8d8cd-104">このサンプル チュートリアルでは、Visual Studio 2017 で ML.NET を使用して、C# を使用する .NET Core コンソール アプリケーションから GitHub の問題を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="8d8cd-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="8d8cd-106">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-106">Understand the problem</span></span>
> * <span data-ttu-id="8d8cd-107">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="8d8cd-108">データを準備する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-108">Prepare your data</span></span>
> * <span data-ttu-id="8d8cd-109">データを変換する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-109">Transform the data</span></span>
> * <span data-ttu-id="8d8cd-110">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="8d8cd-110">Train the model</span></span>
> * <span data-ttu-id="8d8cd-111">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-111">Evaluate the model</span></span>
> * <span data-ttu-id="8d8cd-112">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-112">Predict with the trained model</span></span>
> * <span data-ttu-id="8d8cd-113">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="8d8cd-114">このトピックは現在プレビュー中の ML.NET について述べており、内容が変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="8d8cd-115">詳細については、[ML.NET の概要](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="8d8cd-116">GitHub の問題のサンプルの概要</span><span class="sxs-lookup"><span data-stu-id="8d8cd-116">GitHub issue sample overview</span></span>

<span data-ttu-id="8d8cd-117">このサンプルは ML.NET を使用するコンソール アプリケーションであり、GitHub の問題の区分ラベルを分類および予測するモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="8d8cd-118">また、高品質な分析のために、2 番目のデータ セットを使用してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="8d8cd-119">問題のデータセットは、dotnet/corefx GitHub リポジトリにあります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-119">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="8d8cd-120">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-120">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d8cd-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8d8cd-121">Prerequisites</span></span>

* <span data-ttu-id="8d8cd-122">[Visual Studio 2017 15.6 以降](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)が ".NET Core クロスプラット フォーム開発" とともにインストールされていること。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="8d8cd-123">[Github の問題のタブ区切りのファイル (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv)。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-123">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="8d8cd-124">[Github の問題のテスト タブ区切りのファイル (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv)。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-124">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="8d8cd-125">機械学習ワークフロー</span><span class="sxs-lookup"><span data-stu-id="8d8cd-125">Machine learning workflow</span></span>

<span data-ttu-id="8d8cd-126">このチュートリアルでは、プロセスを順序立てて進められるようにする機械学習ワークフローに従います。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="8d8cd-127">このワークフローには次のフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="8d8cd-128">**問題を把握する**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-128">**Understand the problem**</span></span>
2. <span data-ttu-id="8d8cd-129">**データを準備する**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-129">**Prepare your data**</span></span>
   * <span data-ttu-id="8d8cd-130">**データを読み込む**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-130">**Load the data**</span></span>
   * <span data-ttu-id="8d8cd-131">**特徴を抽出する (データを変換する)**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="8d8cd-132">**ビルドしてトレーニングする**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-132">**Build and train**</span></span> 
   * <span data-ttu-id="8d8cd-133">**モデルをトレーニングする**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-133">**Train the model**</span></span>
   * <span data-ttu-id="8d8cd-134">**モデルを評価する**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="8d8cd-135">**モデルの配置**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-135">**Deploy Model**</span></span>
   * <span data-ttu-id="8d8cd-136">**モデルを使用して予測する**</span><span class="sxs-lookup"><span data-stu-id="8d8cd-136">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="8d8cd-137">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-137">Understand the problem</span></span>

<span data-ttu-id="8d8cd-138">まず、問題を把握して、モデルのビルドおよびトレーニングに使用できるパーツに分ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="8d8cd-139">問題を分けることで、結果の予測および評価ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-139">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="8d8cd-140">このチュートリアルでの問題は、優先順位付けとスケジューリングを行うための正しいラベル付けのために、受け取った GitHub の問題がどの区分に属するかを理解することです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-140">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="8d8cd-141">問題は次の部分に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-141">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="8d8cd-142">問題のタイトル テキスト</span><span class="sxs-lookup"><span data-stu-id="8d8cd-142">the issue title text</span></span>
* <span data-ttu-id="8d8cd-143">問題の説明テキスト</span><span class="sxs-lookup"><span data-stu-id="8d8cd-143">the issue description text</span></span>
* <span data-ttu-id="8d8cd-144">モデルのトレーニング データの区分値</span><span class="sxs-lookup"><span data-stu-id="8d8cd-144">an area value for the model training data</span></span>
* <span data-ttu-id="8d8cd-145">評価して操作で使用できる予測される区分値</span><span class="sxs-lookup"><span data-stu-id="8d8cd-145">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="8d8cd-146">次に、区分を**決定**する必要があります。これは機械学習タスクを選択するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-146">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="8d8cd-147">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-147">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="8d8cd-148">この問題に関してわかっていることは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-148">With this problem, you know the following facts:</span></span>

<span data-ttu-id="8d8cd-149">トレーニング データ:</span><span class="sxs-lookup"><span data-stu-id="8d8cd-149">Training data:</span></span>

<span data-ttu-id="8d8cd-150">GitHub の問題は、次の例のようないくつかの領域 (**区分**) にラベル分けできます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-150">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="8d8cd-151">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="8d8cd-151">area-System.Numerics</span></span>
* <span data-ttu-id="8d8cd-152">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="8d8cd-152">area-System.Xml</span></span>
* <span data-ttu-id="8d8cd-153">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="8d8cd-153">area-Infrastructure</span></span>
* <span data-ttu-id="8d8cd-154">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="8d8cd-154">area-System.Linq</span></span>
* <span data-ttu-id="8d8cd-155">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="8d8cd-155">area-System.IO</span></span>

<span data-ttu-id="8d8cd-156">次の例のように、新しい GitHub の問題の**区分**を予測します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-156">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="8d8cd-157">Contract.Assert 対 Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="8d8cd-157">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="8d8cd-158">System.Xml のフィールドを読み取り専用にする</span><span class="sxs-lookup"><span data-stu-id="8d8cd-158">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="8d8cd-159">このシナリオには、分類機械学習アルゴリズムが適しています。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-159">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="8d8cd-160">分類学習アルゴリズムについて</span><span class="sxs-lookup"><span data-stu-id="8d8cd-160">About the classification learning algorithm</span></span>

<span data-ttu-id="8d8cd-161">分類は、データを使用して項目またはデータ行のカテゴリ、型、クラスを**判断**する機械学習アルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-161">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="8d8cd-162">分類はたとえば、次のような目的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-162">For example, you can use classification to:</span></span>

* <span data-ttu-id="8d8cd-163">センチメントが肯定的か否定的かを判断する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-163">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="8d8cd-164">電子メールをスパム、迷惑メール、正常なメールに分類する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-164">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="8d8cd-165">患者の検体が癌性かどうかを判断する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-165">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="8d8cd-166">顧客を販売キャンペーンへの反応性で分類する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-166">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="8d8cd-167">多くの場合、分類学習アルゴリズムは次のいずれかの種類です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-167">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="8d8cd-168">バイナリ: A か B のいずれかである。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-168">Binary: either A or B.</span></span>
* <span data-ttu-id="8d8cd-169">多クラス: 1 つのモデルを使用して予測できるカテゴリが多数ある。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-169">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="8d8cd-170">この種の問題では、問題カテゴリの予測が 2 つだけ (バイナリ) ではなく複数のカテゴリの 1 つ (多クラス) なので、多クラス分類学習アルゴリズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-170">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="8d8cd-171">コンソール アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-171">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="8d8cd-172">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-172">Create a project</span></span>

1. <span data-ttu-id="8d8cd-173">Visual Studio 2017 を開きます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-173">Open Visual Studio 2017.</span></span> <span data-ttu-id="8d8cd-174">**[ファイル]** > **[新規作成]** > **[プロジェクト]** をメニュー バーから選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-174">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="8d8cd-175">**[新しいプロジェクト]** ダイアログで、**[Visual C#]** ノードを選択し、**[.NET Core]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-175">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="8d8cd-176">次に、**[コンソール アプリ (.NET Core)]** プロジェクト テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-176">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="8d8cd-177">**[名前]** テキスト ボックスに「SentimentAnalysis」と入力し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-177">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="8d8cd-178">プロジェクトに *Data* という名前のディレクトリを作成して、データ セット ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-178">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="8d8cd-179">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-179">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="8d8cd-180">「Data」と入力して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-180">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="8d8cd-181">プロジェクトに *Models* という名前のディレクトリを作成して、モデルを保存します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-181">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="8d8cd-182">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しいフォルダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-182">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="8d8cd-183">「Models」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-183">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="8d8cd-184">**Microsoft.ML NuGet パッケージ**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-184">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="8d8cd-185">ソリューション エクスプローラーで、プロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-185">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="8d8cd-186">[パッケージ ソース] として "nuget.org" を選択し、[参照] タブを選択して「**Microsoft.ML**」を検索します。一覧からそのパッケージを選択し、**[インストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-186">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="8d8cd-187">**[変更のプレビュー]** ダイアログの **[OK]** を選択します。表示されているパッケージのライセンス条項に同意する場合は、**[ライセンスの同意]** ダイアログの **[同意する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-187">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="8d8cd-188">データを準備する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-188">Prepare your data</span></span>

1. <span data-ttu-id="8d8cd-189">[issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) データ セットと [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) データ セットをダウンロードして、それらを作成済みの *Data* フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-189">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="8d8cd-190">1 番目のデータ セットでは機械学習モデルをトレーニングし、2 番目のデータ セットはモデルの精度を評価するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-190">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="8d8cd-191">ソリューション エクスプローラーで、各 \*.tsv ファイルを右クリックし、**[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-191">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="8d8cd-192">**[詳細設定]** で、**[出力ディレクトリにコピー]** の値を **[新しい場合はコピーする]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-192">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="8d8cd-193">クラスを作成してパスを定義する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-193">Create classes and define paths</span></span>

<span data-ttu-id="8d8cd-194">次に示す追加の `using` ステートメントを *Program.cs* ファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-194">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="8d8cd-195">最近ダウンロードしたファイルのパスを保存する 3 つのグローバル フィールドと、`MLContext`、`DataView`、`PredictionEngine`、`TextLoader` のためのグローバル変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-195">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="8d8cd-196">`_trainDataPath` には、モデルのトレーニングに使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-196">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="8d8cd-197">`_testDataPath` には、モデルの評価に使用するデータ セットのパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-197">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="8d8cd-198">`_modelPath` には、トレーニング済みのモデルを保存するパスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-198">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="8d8cd-199">`_mlContext` は処理コンテキストを提供する <xref:Microsoft.ML.MLContext> です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-199">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="8d8cd-200">`_trainingDataView` は、トレーニング データセットを処理するために使用される <xref:Microsoft.Data.DataView.IDataView> です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-200">`_trainingDataView` is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="8d8cd-201">`_predEngine` は、1 つの予測に使用される <xref:Microsoft.ML.PredictionEngine%602> です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-201">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="8d8cd-202">`_reader` は、データセットの読み込みと変換に使用される <xref:Microsoft.ML.Data.TextLoader> です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-202">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="8d8cd-203">`Main` メソッドのすぐ上にある行に次のコードを追加して、それらのパスとその他の変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-203">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="8d8cd-204">入力データと予測のために、いくつかのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-204">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="8d8cd-205">プロジェクトに新しいクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-205">Add a new class to your project:</span></span>

1. <span data-ttu-id="8d8cd-206">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、**[追加]** > **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-206">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="8d8cd-207">**[新しい項目の追加]** ダイアログ ボックスで、**[クラス]** を選択し、**[名前]** フィールドを「*GitHubIssueData.cs*」に変更します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-207">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="8d8cd-208">次に、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-208">Then, select the **Add** button.</span></span>

    <span data-ttu-id="8d8cd-209">コード エディターで *GitHubIssueData.cs* ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-209">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="8d8cd-210">*GitHubIssueData.cs* の先頭に次の `using` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-210">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="8d8cd-211">既存のクラス定義を削除し、`GitHubIssue` と `IssuePrediction` の 2 つのクラスを含む次のコードを *GitHubIssueData.cs* ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-211">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="8d8cd-212">`GitHubIssue` は、入力データセット クラスで、次の <xref:System.String> フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-212">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="8d8cd-213">`ID` には GitHub の問題の ID 値が含まれます</span><span class="sxs-lookup"><span data-stu-id="8d8cd-213">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="8d8cd-214">`Area` には、`Area` ラベルの値が含まれます</span><span class="sxs-lookup"><span data-stu-id="8d8cd-214">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="8d8cd-215">`Title` には GitHub の問題のタイトルが含まれます</span><span class="sxs-lookup"><span data-stu-id="8d8cd-215">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="8d8cd-216">`Description` には GitHub の問題の説明が含まれます</span><span class="sxs-lookup"><span data-stu-id="8d8cd-216">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="8d8cd-217">`IssuePrediction` は、モデルがトレーニングされた後に、予測に使用されるクラスです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-217">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="8d8cd-218">これは、1 つの `string` (`Area`) と、`PredictedLabel` `ColumnName` 属性があります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-218">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="8d8cd-219">`Label` はモデルを作成してトレーニングするために使用され、2 番目のデータ セットでもモデルを評価するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-219">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="8d8cd-220">`PredictedLabel` は予測と評価の際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-220">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="8d8cd-221">評価では、トレーニング データを含む入力、予測された値、およびモデルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-221">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="8d8cd-222">ML.NET を使用してモデルをビルドするときは、まず <xref:Microsoft.ML.MLContext> を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-222">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="8d8cd-223">`MLContext` は、概念的には Entity Framework での `DbContext` の使用に相当します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-223">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="8d8cd-224">環境によって、例外の追跡とログ記録に使用できる ML ジョブのコンテキストが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-224">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="8d8cd-225">Main で変数を初期化する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-225">Initialize variables in Main</span></span>

<span data-ttu-id="8d8cd-226">複数のトレーニング間で反復可能な決定論的結果を得るために、`_mlContext` グローバル変数をランダム シード (`seed: 0`) を使用して `MLContext` の新しいインスタンスで初期化します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-226">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="8d8cd-227">`Main` メソッドの `Console.WriteLine("Hello World!")` 行を、次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-227">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="8d8cd-228">データを読み込む</span><span class="sxs-lookup"><span data-stu-id="8d8cd-228">Load the data</span></span>

<span data-ttu-id="8d8cd-229">次いで、`_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> グローバル変数を初期化して、`_trainDataPath` パラメーターを使用してデータを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-229">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="8d8cd-230">[`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer) の入力および出力として、`DataView` は基本的なデータ パイプラインの種類であり、`LINQ` の `IEnumerable` と同等です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-230">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="8d8cd-231">ML.NET ではデータは `SQL view` に似ています。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-231">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="8d8cd-232">つまり、遅延評価、体系的、異種です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-232">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="8d8cd-233">オブジェクトはパイプラインの最初の部分であり、データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-233">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="8d8cd-234">このチュートリアルでは、問題のタイトル、説明、および対応する区分 GitHub ラベルを使用してデータセットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-234">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="8d8cd-235">モデルの作成とトレーニングには、`DataView` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-235">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="8d8cd-236">以前に作成した `GitHubIssue` データ モデルの種類がデータセット スキーマと一致するため、初期化、マッピング、およびデータセットの読み込みを 1 行のコードに組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-236">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="8d8cd-237">行の最初の部分 (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) では、`GitHubIssue` データ モデル型からデータセット スキーマを推論し、データセットのヘッダーを使用し、<xref:Microsoft.ML.Data.TextLoader> を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-237">The first part of the line (`CreateTextLoader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferring the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="8d8cd-238">データ スキーマは、`GitHubIssue` クラスを作成したときに既に定義しています。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-238">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="8d8cd-239">スキーマでは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-239">For your schema:</span></span>

* <span data-ttu-id="8d8cd-240">最初の列 `ID` (GitHub 問題 ID)</span><span class="sxs-lookup"><span data-stu-id="8d8cd-240">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="8d8cd-241">2 番目の列 `Area` (トレーニングの予測)</span><span class="sxs-lookup"><span data-stu-id="8d8cd-241">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="8d8cd-242">3 番目の列 `Title` (GitHub の問題のタイトル) は、`Area` の予測に使用される最初の[特徴](../resources/glossary.md##feature)です</span><span class="sxs-lookup"><span data-stu-id="8d8cd-242">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="8d8cd-243">第 4 列 `Description` は、`Area` の予測に使用される 2 番目の特徴です</span><span class="sxs-lookup"><span data-stu-id="8d8cd-243">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="8d8cd-244">行の 2 番目の部分 (`.Read(_trainDataPath)`) では <xref:Microsoft.ML.Data.TextLoader.Read%2A> メソッドを使用して、`IDataView` (`_trainingDataView`) グローバル変数に `_trainDataPath` を使用してトレーニング用のテキスト ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-244">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="8d8cd-245">パイプラインで利用するために `_trainingDataView` グローバル変数を初期化して読み込むには、`mlContext` 初期化の後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-245">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="8d8cd-246">`Main` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-246">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="8d8cd-247">`ProcessData` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-247">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="8d8cd-248">データを抽出して変換します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-248">Extracts and transforms the data.</span></span>
* <span data-ttu-id="8d8cd-249">処理パイプラインを返します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-249">Returns the processing pipeline.</span></span>

<span data-ttu-id="8d8cd-250">`Main` メソッドの直後に、次のコードを使用して `ProcessData` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-250">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="8d8cd-251">特徴を抽出してデータを変換する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-251">Extract Features and transform the data</span></span>

<span data-ttu-id="8d8cd-252">データの前処理とクリーニングは、機械学習でデータ セットを効果的に使用する前に発生する重要なタスクです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-252">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="8d8cd-253">多くの場合、生データはノイズが多くて信頼性が低く、値が欠落している可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-253">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="8d8cd-254">これらのモデル化タスクを行わずにデータを使用すると、誤解を招く結果が生じるおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-254">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="8d8cd-255">ML.NET の変換パイプラインによって、トレーニングまたはテストの前にデータに適用されるカスタムの `transforms` セットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-255">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="8d8cd-256">この変換の主な目的は、データの[特徴付け](../resources/glossary.md#feature-engineering)です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-256">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="8d8cd-257">機械学習アルゴリズムによって理解されるのは、[特徴付け](../resources/glossary.md#feature)されたデータです。したがって、次の手順では、テキスト データを ML アルゴリズムが認識できる形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-257">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="8d8cd-258">その形式は、[数値ベクトル](../resources/glossary.md#numerical-feature-vector)です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-258">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="8d8cd-259">次の手順では、`GitHubIssue` クラス内で定義された名前によって列を参照します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-259">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="8d8cd-260">モデルのトレーニングと評価が行われるとき、既定では、**Label** 列内の値が予測される適切な値と見なされます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-260">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="8d8cd-261">`GitHubIssue` の区分 GitHub ラベルを予測したいので、`Area` 列を **Label** 列にコピーします。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-261">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="8d8cd-262">これを行うには、<xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> 変換クラスのラッパーである `MLContext.Transforms.Conversion.MapValueToKey` を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-262">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="8d8cd-263">`MapValueToKey` は、実質的にパイプラインになる <xref:Microsoft.ML.Data.EstimatorChain%601> を返します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-263">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="8d8cd-264">後でトレーナーを `EstimatorChain` に付加するときに、この `pipeline` を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-264">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="8d8cd-265">次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-265">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="8d8cd-266">特徴付けによって、各列内のさまざまな値に異なる数値が割り当てられ、機械学習のアルゴリズムで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-266">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="8d8cd-267">次に、`mlContext.Transforms.Text.FeaturizeText` を呼び出します。これによってテキスト列 (`Title` および `Description`) が特徴付けされ、それぞれ `TitleFeaturized` および `DescriptionFeaturized` と呼ばれる数値ベクトルになります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-267">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="8d8cd-268">次のコードを使用して、両列の特徴付けをパイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-268">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="8d8cd-269">ML.NET バージョン 0.10 では、変換パラメーターの順序が変更されました。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-269">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="8d8cd-270">これについては、ビルドするまでエラーが出力されません。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-270">This will not error out until you build.</span></span> <span data-ttu-id="8d8cd-271">変換パラメーターの名前を上記のコード スニペットに示すように使用してください。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-271">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="8d8cd-272">データの準備の最後の手順では、`Concatenate` 変換クラスを使用して、すべての特徴列を **Features** 列に結合します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-272">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="8d8cd-273">既定では、学習アルゴリズムは **Features** 列の特徴のみを処理します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-273">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="8d8cd-274">次のコードを使用してパイプラインに、この変換を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-274">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="8d8cd-275">次に、DataView をキャッシュするために <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> を追加します。つまり、次のコードでキャッシュを使用してデータが複数回反復されると、パフォーマンスが向上する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-275">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

<span data-ttu-id="8d8cd-276">`ProcessData` メソッドの最後で、パイプラインが返されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-276">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="8d8cd-277">この手順で前処理と特徴付けが処理されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-277">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="8d8cd-278">ML.NET に用意されているその他のコンポーネントを使用すると、モデルでより良い結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-278">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="8d8cd-279">モデルを構築してトレーニングする</span><span class="sxs-lookup"><span data-stu-id="8d8cd-279">Build and train the model</span></span>

<span data-ttu-id="8d8cd-280">`Main` メソッドの次のコード行として、`BuildAndTrainModel` メソッドに次の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-280">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="8d8cd-281">`BuildAndTrainModel` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-281">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="8d8cd-282">トレーニング アルゴリズムのクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-282">Creates the training algorithm class.</span></span>
* <span data-ttu-id="8d8cd-283">モデルをトレーニングする。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-283">Trains the model.</span></span>
* <span data-ttu-id="8d8cd-284">トレーニング データに基づいて区分を予測します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-284">Predicts area based on training data.</span></span>
* <span data-ttu-id="8d8cd-285">モデルを `.zip` ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-285">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="8d8cd-286">モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-286">Returns the model.</span></span>

<span data-ttu-id="8d8cd-287">`Main` メソッドの直後に、次のコードを使用して `BuildAndTrainModel` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-287">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<KeyToValueMappingTransformer> BuildAndTrainModel(IDataView trainingDataView, EstimatorChain<ITransformer> pipeline)
{

}
```

<span data-ttu-id="8d8cd-288">これでトレーニング データセット (`trainingDataView`) 用の `IDataView` と、ProcessData (`pipeline`) で作成された処理用パイプライン用の <xref:Microsoft.ML.Data.EstimatorChain%601> の 2 つのパラメーターが BuildAndTrainModel メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-288">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="8d8cd-289">`BuildAndTrainModel` メソッドの最初の行として、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-289">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="8d8cd-290">学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-290">Choose a learning algorithm</span></span>

<span data-ttu-id="8d8cd-291">学習アルゴリズムを追加するには、<xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> オブジェクトを返す `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` ラッパー メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-291">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="8d8cd-292">`SdcaMultiClassTrainer` が `pipeline` に追加されます。これは、特徴付けされた `Title` と `Description` (`Features`) と `Label` 入力パラメーターを受け入れて、履歴データから学習します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-292">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="8d8cd-293">元の読み取り可能な状態に戻すために、値にラベルもマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-293">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="8d8cd-294">これらの両アクションは、次のコードを使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-294">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="8d8cd-295">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="8d8cd-295">Train the model</span></span>

<span data-ttu-id="8d8cd-296">読み込まれて変換されたデータ セットに基づいて、モデル <xref:Microsoft.ML.Data.TransformerChain%601> をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-296">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="8d8cd-297">推定器が定義されたら、既に読み込まれたトレーニング データを提供しながら、<xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> を使用してモデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-297">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="8d8cd-298">このメソッドにより、予測で使用されるモデルが返されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-298">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="8d8cd-299">`trainingPipeline.Fit()` でパイプラインをトレーニングし、`DataView` に基づいて `Transformer` を返します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-299">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="8d8cd-300">`.Fit()` メソッドが実行されるまで、実験は実行されません。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-300">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="8d8cd-301">`BuildAndTrainModel` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-301">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="8d8cd-302">`model` は多数のデータ行を操作する `transformer` ですが、個々の例に対する予測のニーズは、よくある運用シナリオです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-302">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="8d8cd-303"><xref:Microsoft.ML.PredictionEngine%602> は、`CreatePredictionEngine` メソッドから返されるラッパーです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-303">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="8d8cd-304">次の行を追加して、`PredictionEngine` を `BuildAndTrainModel` メソッドの次の行として作成しましょう。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-304">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="8d8cd-305">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-305">Predict with the trained model</span></span>

<span data-ttu-id="8d8cd-306">GitHub の問題を追加して、`Predict` メソッドでトレーニングされたモデルの予測をテストします。これには `GitHubIssue` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-306">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="8d8cd-307">これを使用して、問題のデータの 1 インスタンスの `Area` レベルを予測できます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-307">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="8d8cd-308">予測を取得するには、データに対して <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-308">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="8d8cd-309">入力データは文字列で、モデルには特徴付けが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-309">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="8d8cd-310">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-310">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="8d8cd-311">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-311">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="8d8cd-312">モデルの使用: 予測結果</span><span class="sxs-lookup"><span data-stu-id="8d8cd-312">Using the model: prediction results</span></span>

<span data-ttu-id="8d8cd-313">結果を共有し、それに応じたアクションを実行するために、`GitHubIssue` および対応する `Area` ラベル予測を表示します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-313">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="8d8cd-314">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果の表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-314">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="8d8cd-315">評価に使用する、トレーニング済みのモデルを返す</span><span class="sxs-lookup"><span data-stu-id="8d8cd-315">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="8d8cd-316">`BuildAndTrainModel` メソッドの最後で、モデルを返します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-316">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="8d8cd-317">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-317">Evaluate the model</span></span>

<span data-ttu-id="8d8cd-318">これでモデルの作成とトレーニングが完了したので、品質保証と検証のために、別のデータ セットを使用してモデルを評価します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-318">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="8d8cd-319">`Evaluate` メソッドでは、`BuildAndTrainModel` で作成されたモデルが渡されて評価されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-319">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="8d8cd-320">`BuildAndTrainModel` の直後に、次のコードに示すように `Evaluate` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-320">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="8d8cd-321">`Evaluate` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-321">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="8d8cd-322">テスト データ セットを読み込む。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-322">Loads the test dataset.</span></span>
* <span data-ttu-id="8d8cd-323">多クラス評価器を作成する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-323">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="8d8cd-324">モデルを評価し、メトリックを作成する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-324">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="8d8cd-325">メトリックを表示する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-325">Displays the metrics.</span></span>

<span data-ttu-id="8d8cd-326">`BuildAndTrainModel` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-326">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="8d8cd-327">既にトレーニング データセットで行ったように、初期化、マッピング、テスト データの読み込みを 1 行のコードに結合できます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-327">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="8d8cd-328">このデータ セットを品質チェックとして使用して、モデルを評価できます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-328">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="8d8cd-329">`Evaluate` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-329">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="8d8cd-330">`MulticlassClassificationContext.Evaluate` は、指定されたデータセットを使用してモデルの品質メトリックを計算する <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> メソッドのラッパーです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-330">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="8d8cd-331">これによって返される <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> オブジェクトには、多クラス分類評価器によって計算されるメトリック全体が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-331">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="8d8cd-332">メトリックを表示してモデルの品質を判定するには、最初にメトリックを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-332">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="8d8cd-333">特徴を入力し、予測を戻す、機械学習の `_trainedModel` グローバル変数 (変換器) の `Transform` メソッドの使用法に注目してください。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-333">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="8d8cd-334">`Evaluate` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-334">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="8d8cd-335">多クラス分類では、次のメトリックが評価されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-335">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="8d8cd-336">マイクロ精度: すべてのサンプルとクラスのペアが、精度メトリックに均等に作用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-336">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="8d8cd-337">マイクロ精度は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-337">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="8d8cd-338">マクロ精度: すべてのクラスが、精度メトリックに均等に作用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-338">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="8d8cd-339">少数派のクラスは、大規模なクラスと同じ重みが与えられています。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-339">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="8d8cd-340">マクロ精度は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-340">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="8d8cd-341">対数損失: [対数損失](../resources/glossary.md#log-loss)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-341">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="8d8cd-342">対数損失は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-342">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="8d8cd-343">対数損失還元: 範囲は [-inf, 100] です。ここで、100 は完璧な予測で、0 は平均の予測です。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-343">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="8d8cd-344">対数損失還元は可能な限り 1 に近づけます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-344">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="8d8cd-345">モデル検証のためのメトリックを表示する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-345">Displaying the metrics for model validation</span></span>

<span data-ttu-id="8d8cd-346">次のコードを使用してメトリックを表示し、結果を共有し、それに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-346">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="8d8cd-347">トレーニング済みの評価されたモデルを保存する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-347">Save the trained and evaluated model</span></span>

<span data-ttu-id="8d8cd-348">この時点で、既存または新規のどの .NET アプリケーションにも統合できる、型が <xref:Microsoft.ML.Data.TransformerChain%601> のモデルができました。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-348">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="8d8cd-349">トレーニングしたモデルを .zip ファイルに保存するには、`BuildAndTrainModel` の次の行で `SaveModelAsFile` メソッドを呼び出すために次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-349">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="8d8cd-350">モデルを .zip ファイルとして保存する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-350">Save the model as a .zip file</span></span>

<span data-ttu-id="8d8cd-351">`Evaluate` メソッドの直後に、次のコードを使用して `SaveModelAsFile` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-351">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="8d8cd-352">`SaveModelAsFile` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-352">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="8d8cd-353">モデルを .zip ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-353">Saves the model as a .zip file.</span></span>

<span data-ttu-id="8d8cd-354">次に、モデルを再利用して他のアプリケーションで使用できるようにモデルを保存するメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-354">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="8d8cd-355">`ITransformer` には <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> メソッドがあり、`_modelPath` グローバル フィールドと <xref:System.IO.Stream> を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-355">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="8d8cd-356">モデルを ZIP ファイルとして保存するには、`FileStream` を作成した直後に `SaveTo` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-356">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="8d8cd-357">`SaveModelAsFile` メソッドに次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-357">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="8d8cd-358">`_modelPath` を使用してコンソール メッセージを記述することで、ファイルが書き込まれた場所も表示できるようになります。これには次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-358">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="8d8cd-359">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-359">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="8d8cd-360">`Evaluate` メソッドの呼び出しのすぐ下に、次のコードを使用して、`Main` メソッドからの新しいメソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-360">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="8d8cd-361">`Evaluate` メソッドの直後 (および `SaveModelAsFile` メソッドの直前) に、次のコードを使用して `PredictIssue` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-361">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="8d8cd-362">`PredictIssue` メソッドは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-362">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="8d8cd-363">テスト データの問題を 1 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-363">Creates a single issue of test data.</span></span>
* <span data-ttu-id="8d8cd-364">テスト データに基づいて区分を予測します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-364">Predicts Area based on test data.</span></span>
* <span data-ttu-id="8d8cd-365">テスト データと予測をレポート用に結合する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-365">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="8d8cd-366">予測された結果を表示する。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-366">Displays the predicted results.</span></span>

<span data-ttu-id="8d8cd-367">まず、次のコードを使用して、先ほど保存したモデルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-367">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="8d8cd-368">GitHub の問題を追加して、`Predict` メソッドでトレーニングされたモデルの予測をテストします。これには `GitHubIssue` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-368">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="8d8cd-369">これでモデルがあるので、それを使用して GitHub の問題データの 1 インスタンスの区分 GitHub ラベルを予測できます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-369">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="8d8cd-370">予測を取得するには、データに対して <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-370">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="8d8cd-371">入力データは文字列で、モデルには特徴付けが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-371">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="8d8cd-372">トレーニングと予測の間は、パイプラインが同期されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-372">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="8d8cd-373">予測のために前処理/特徴付けのコードを特別に記述する必要はなく、同じ API によってバッチと 1 回限りの予測の両方が処理されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-373">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="8d8cd-374">予測のために `PredictIssue` メソッドに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-374">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="8d8cd-375">予測のために読み込み済みのモデルを使用する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-375">Using the loaded model for prediction</span></span>

<span data-ttu-id="8d8cd-376">問題を分類し、それに応じて処理するために `Area` を表示します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-376">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="8d8cd-377">次の <xref:System.Console.WriteLine?displayProperty=nameWithType> コードを使用して、結果の表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-377">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="8d8cd-378">結果</span><span class="sxs-lookup"><span data-stu-id="8d8cd-378">Results</span></span>

<span data-ttu-id="8d8cd-379">結果は以下のようになるはずです。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-379">Your results should be similar to the following.</span></span> <span data-ttu-id="8d8cd-380">パイプラインが処理されると、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-380">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="8d8cd-381">警告または処理メッセージが表示されることがありますが、</span><span class="sxs-lookup"><span data-stu-id="8d8cd-381">You may see warnings, or processing messages.</span></span> <span data-ttu-id="8d8cd-382">わかりやすくするために、これらのメッセージは次の結果から削除してあります。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-382">These messages have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="8d8cd-383">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="8d8cd-383">Congratulations!</span></span> <span data-ttu-id="8d8cd-384">これで、GitHub の問題用の区分ラベルを分類および予測するための機械学習モデルをビルドできました。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-384">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="8d8cd-385">このチュートリアルのソース コードは [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) リポジトリで確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-385">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d8cd-386">次の手順</span><span class="sxs-lookup"><span data-stu-id="8d8cd-386">Next steps</span></span>

<span data-ttu-id="8d8cd-387">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-387">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="8d8cd-388">問題を把握する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-388">Understand the problem</span></span>
> * <span data-ttu-id="8d8cd-389">適切な機械学習アルゴリズムを選択する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-389">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="8d8cd-390">データを準備する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-390">Prepare your data</span></span>
> * <span data-ttu-id="8d8cd-391">データを変換する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-391">Transform the data</span></span>
> * <span data-ttu-id="8d8cd-392">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="8d8cd-392">Train the model</span></span>
> * <span data-ttu-id="8d8cd-393">モデルを評価する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-393">Evaluate the model</span></span>
> * <span data-ttu-id="8d8cd-394">トレーニング済みモデルを使用して予測する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-394">Predict with the trained model</span></span>
> * <span data-ttu-id="8d8cd-395">読み込み済みのモデルを使用して配置および予測する</span><span class="sxs-lookup"><span data-stu-id="8d8cd-395">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="8d8cd-396">さらに詳しく学習するには、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="8d8cd-396">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="8d8cd-397">タクシー代予測</span><span class="sxs-lookup"><span data-stu-id="8d8cd-397">Taxi Fare Predictor</span></span>](taxi-fare.md)
