---
title: C# の概要 - 開発ツールに対する理解を深める
description: この記事では、コンピューターで C# アプリケーションと .NET アプリケーションを開発するためのツールの基礎を提供します。
ms.date: 10/23/2018
ms.openlocfilehash: db0b3228272a17feaa11ec754fa0aa4952a0d1ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58920663"
---
# <a name="become-familiar-with-the-net-development-tools"></a><span data-ttu-id="53f19-103">.NET 開発ツールに対する理解を深める</span><span class="sxs-lookup"><span data-stu-id="53f19-103">Become familiar with the .NET development tools</span></span>

<span data-ttu-id="53f19-104">コンピューターでチュートリアルを実行する最初の手順は、開発環境を設定することです。</span><span class="sxs-lookup"><span data-stu-id="53f19-104">The first step in running a tutorial on your machine is to set up a development environment.</span></span>
<span data-ttu-id="53f19-105">Mac、PC、または Linux 上でローカルの開発環境を設定する手順については、.NET の [10 分でわかる概要](https://www.microsoft.com/net/core)に関するトピックに記載されています。</span><span class="sxs-lookup"><span data-stu-id="53f19-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="53f19-106">または、[.NET Core SDK](https://www.microsoft.com/net/download) と [Visual Studio Code](https://code.visualstudio.com/) をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="53f19-106">Alternatively, you can install the [.NET Core SDK](https://www.microsoft.com/net/download) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="53f19-107">アプリケーション開発の基本フロー</span><span class="sxs-lookup"><span data-stu-id="53f19-107">Basic application development flow</span></span>

<span data-ttu-id="53f19-108">[`dotnet new`](../../../core/tools/dotnet-new.md) コマンドを使用してアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="53f19-108">You'll create applications using the [`dotnet new`](../../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="53f19-109">このコマンドによってアプリケーションに必要なファイルとアセットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="53f19-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="53f19-110">C# の概要チュートリアルではすべて、アプリケーションの種類 `console` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="53f19-110">The introduction to C# tutorials all use the `console` application type.</span></span> <span data-ttu-id="53f19-111">基本を習得したら、他の種類のアプリケーションに応用できます。</span><span class="sxs-lookup"><span data-stu-id="53f19-111">Once you've got the basics, you can expand to other application types.</span></span>

<span data-ttu-id="53f19-112">その他には、実行可能ファイルをビルドする [`dotnet build`](../../../core/tools/dotnet-build.md) コマンド、実行可能ファイルを実行する [`dotnet run`](../../../core/tools/dotnet-run.md) コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="53f19-112">The other commands you'll use are [`dotnet build`](../../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-tutorial"></a><span data-ttu-id="53f19-113">チュートリアルを選択する</span><span class="sxs-lookup"><span data-stu-id="53f19-113">Pick your tutorial</span></span>

<span data-ttu-id="53f19-114">最初に次のいずれかのチュートリアルを選択します。</span><span class="sxs-lookup"><span data-stu-id="53f19-114">You can start with any of the following tutorials:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="53f19-115">C# における数値</span><span class="sxs-lookup"><span data-stu-id="53f19-115">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="53f19-116">[C# における数値](numbers-in-csharp-local.md)チュートリアルでは、コンピューターに数値が格納されるしくみとさまざまな数値型で計算するしくみが紹介されます。</span><span class="sxs-lookup"><span data-stu-id="53f19-116">In the [Numbers in C#](numbers-in-csharp-local.md) tutorial, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="53f19-117">丸めの基本と C# を使用した数学計算方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="53f19-117">You'll learn the basics of rounding and how to perform mathematical calculations using C#.</span></span>

<span data-ttu-id="53f19-118">このチュートリアルでは、[Hello world](hello-world.yml) レッスンを修了していることが前提条件となります。</span><span class="sxs-lookup"><span data-stu-id="53f19-118">This tutorial assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="53f19-119">分岐とループ</span><span class="sxs-lookup"><span data-stu-id="53f19-119">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="53f19-120">[分岐とループ](branches-and-loops-local.md) チュートリアルでは、変数に格納されている値に基づき、コード実行のさまざまなパスを選択することの基本を説明します。</span><span class="sxs-lookup"><span data-stu-id="53f19-120">The [Branches and loops](branches-and-loops-local.md) tutorial teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="53f19-121">プログラムが決定して異なる操作を選択する上で基本となる、制御フローの基礎を学習します。</span><span class="sxs-lookup"><span data-stu-id="53f19-121">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span>

<span data-ttu-id="53f19-122">このチュートリアルでは、[Hello world](hello-world.yml) レッスンと [C# における数値](numbers-in-csharp-local.md)レッスンを修了していることが前提条件となります。</span><span class="sxs-lookup"><span data-stu-id="53f19-122">This tutorial assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="53f19-123">リスト コレクション</span><span class="sxs-lookup"><span data-stu-id="53f19-123">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="53f19-124">「[リスト コレクション](arrays-and-collections.md)」レッスンでは、データのシーケンスを格納するリスト コレクション型について説明します。</span><span class="sxs-lookup"><span data-stu-id="53f19-124">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="53f19-125">項目の追加方法や削除方法、項目の検索方法、リストを並べ替える方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="53f19-125">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="53f19-126">さまざまな種類のリストを紹介します。</span><span class="sxs-lookup"><span data-stu-id="53f19-126">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="53f19-127">このチュートリアルでは、上に挙げたレッスンを修了していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="53f19-127">This tutorial assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="53f19-128">クラスの概要</span><span class="sxs-lookup"><span data-stu-id="53f19-128">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="53f19-129">この C# 概要の最後のチュートリアルはお使いのコンピューターでのみ実行できます。自分のローカル開発環境と .NET Core を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53f19-129">This final introduction to C# tutorial is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="53f19-130">コンソール アプリケーションを構築し、C# 言語に含まれるオブジェクト指向の基本的な機能について学習します。</span><span class="sxs-lookup"><span data-stu-id="53f19-130">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
