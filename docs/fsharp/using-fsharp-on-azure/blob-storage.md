---
title: F# を使用して Azure Blob storage の概要します。
description: Azure Blob storage を使用してクラウドでは、非構造化データを格納します。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: ea9dc334ec9c2bcd4a80cc501d4b6634da5f64e4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037283"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="c6e74-103">F# を使用して Azure Blob storage の概要します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-103">Get started with Azure Blob storage using F#</span></span> #

<span data-ttu-id="c6e74-104">Azure BLOB Storage は、非構造化データをオブジェクト/BLOB としてクラウドに格納するサービスです。</span><span class="sxs-lookup"><span data-stu-id="c6e74-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="c6e74-105">Blob Storage は、ドキュメント、メディア ファイル、アプリケーション インストーラーなど、任意の種類のテキストまたはバイナリ データを格納できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="c6e74-106">Blob Storage は、オブジェクト ストレージとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="c6e74-107">この記事では、Blob storage を使用して一般的なタスクを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="c6e74-108">サンプルは、.NET 用 Azure Storage クライアント ライブラリを使用した f# を使用して記述します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="c6e74-109">対象タスクには、アップロード、一覧表示、ダウンロード、および blob を削除する方法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="c6e74-110">Blob storage の概念的概要については、次を参照してください。 [blob ストレージ用の .NET ガイド](/azure/storage/storage-dotnet-how-to-use-blobs)します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6e74-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c6e74-111">Prerequisites</span></span>

<span data-ttu-id="c6e74-112">このガイドを使用するのにはまず[Azure ストレージ アカウントを作成](/azure/storage/storage-create-storage-account)です。</span><span class="sxs-lookup"><span data-stu-id="c6e74-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="c6e74-113">このアカウントのストレージ アクセス キーも必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="c6e74-114">作成して、f# スクリプトと開始 f# 対話型</span><span class="sxs-lookup"><span data-stu-id="c6e74-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="c6e74-115">この記事のサンプルは、f# アプリケーションまたは f# スクリプトのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="c6e74-116">F# スクリプトを作成するには、ファイルを作成、`.fsx`拡張機能の例では、 `blobs.fsx`、f# 開発環境にします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="c6e74-117">次に、使用、[パッケージ マネージャー](package-management.md)など[パケット](https://fsprojects.github.io/Paket/)または[NuGet](https://www.nuget.org/)をインストールする、`WindowsAzure.Storage`と`Microsoft.WindowsAzure.ConfigurationManager`パッケージと参照`WindowsAzure.Storage.dll`と`Microsoft.WindowsAzure.Configuration.dll`を使用して、スクリプト、`#r`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="c6e74-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="c6e74-118">名前空間宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-118">Add namespace declarations</span></span>

<span data-ttu-id="c6e74-119">次の追加`open`ステートメントの先頭に、`blobs.fsx`ファイル。</span><span class="sxs-lookup"><span data-stu-id="c6e74-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="c6e74-120">接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-120">Get your connection string</span></span>

<span data-ttu-id="c6e74-121">このチュートリアルに Azure Storage の接続文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6e74-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="c6e74-122">接続文字列の詳細については、次を参照してください。[ストレージ接続文字列を構成](/azure/storage/storage-configure-connection-string)します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="c6e74-123">このチュートリアルでは、次のように、スクリプトで、接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="c6e74-124">ただし、これは**しないで**の実際のプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="c6e74-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="c6e74-125">ストレージ アカウント キーは、ストレージ アカウントの root パスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="c6e74-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="c6e74-126">常に、ストレージ アカウント キーを保護するように注意します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="c6e74-127">ハード コーディング、または他のユーザーにアクセスできるプレーン テキスト ファイルに保存することは、他のユーザーに配布しないでください。</span><span class="sxs-lookup"><span data-stu-id="c6e74-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="c6e74-128">侵害されていると思われる場合は、Azure Portal を使用して、キーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="c6e74-129">実際のアプリケーションは、ストレージ接続文字列を維持するために最善の方法は、構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="c6e74-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="c6e74-130">構成ファイルから接続文字列を取得するには、は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="c6e74-131">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c6e74-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="c6e74-132">.NET Framework のなどの API を使用することもできます。`ConfigurationManager`型。</span><span class="sxs-lookup"><span data-stu-id="c6e74-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="c6e74-133">接続文字列を解析します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-133">Parse the connection string</span></span>

<span data-ttu-id="c6e74-134">接続文字列を解析するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="c6e74-135">これにより返されます、`CloudStorageAccount`します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="c6e74-136">ローカルのダミー データの一部を作成します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-136">Create some local dummy data</span></span>

<span data-ttu-id="c6e74-137">開始する前に、スクリプトのディレクトリにダミーのローカル データの一部を作成します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="c6e74-138">後でこのデータをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="c6e74-139">Blob service クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-139">Create the Blob service client</span></span>

<span data-ttu-id="c6e74-140">`CloudBlobClient`型では、コンテナーと Blob storage に格納されている blob を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="c6e74-141">サービス クライアントを作成する方法の 1 つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="c6e74-142">データを読み取るし、Blob storage にデータを書き込むコードを記述する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="c6e74-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="c6e74-143">コンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-143">Create a container</span></span>

<span data-ttu-id="c6e74-144">この例では、存在しない場合は、コンテナーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="c6e74-145">既定では、新しいコンテナーはプライベートでは、このコンテナーから blob をダウンロードするストレージ アクセス キーを指定することを意味します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="c6e74-146">すべてのユーザーがコンテナー内のファイルを使用できるようにする場合は、次のコードを使用して公開するコンテナーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="c6e74-147">インターネット ユーザー全員、パブリック コンテナー内の blob を表示することができますが、適切なアカウント アクセス キーまたは共有アクセス署名がある場合にのみ、それらを削除または変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="c6e74-148">Blob コンテナーをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-148">Upload a blob into a container</span></span>

<span data-ttu-id="c6e74-149">Azure Blob Storage には、ブロック blob とページ blob がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c6e74-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="c6e74-150">ほとんどの場合、ブロック blob とは、使用する推奨される型です。</span><span class="sxs-lookup"><span data-stu-id="c6e74-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="c6e74-151">ブロック blob にファイルをアップロードするには、コンテナーの参照を取得し、それを使用して、ブロック blob の参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="c6e74-152">Blob の参照を作成したら、アップロードできますデータの任意のストリームを呼び出すことによって、`UploadFromFile`メソッド。</span><span class="sxs-lookup"><span data-stu-id="c6e74-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="c6e74-153">この操作は、blob を作成しますしなかった以前存在か存在する場合に上書きします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="c6e74-154">コンテナー内の blob を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-154">List the blobs in a container</span></span>

<span data-ttu-id="c6e74-155">コンテナー内の blob を一覧表示、まずコンテナーの参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="c6e74-156">コンテナーを使用することができますし、 `ListBlobs` blob やその中のディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="c6e74-157">プロパティと返されるメソッドの豊富なセットにアクセスする`IListBlobItem`にキャストする必要があります、 `CloudBlockBlob`、 `CloudPageBlob`、または`CloudBlobDirectory`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c6e74-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="c6e74-158">型が既知でない場合は、判断にキャストするために型チェックを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="c6e74-159">次のコードを取得して内の各項目の URI を出力する方法を示して、`mydata`コンテナー。</span><span class="sxs-lookup"><span data-stu-id="c6e74-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="c6e74-160">名前の blob、名前にパス情報を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="c6e74-161">これにより、整理して従来のファイル システムと同様に走査する仮想ディレクトリ構造が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="c6e74-162">ディレクトリ構造は仮想のみ - Blob storage で使用できる唯一のリソースはコンテナーと blob のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c6e74-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="c6e74-163">ただし、ストレージ クライアント ライブラリが用意されています、`CloudBlobDirectory`オブジェクトの仮想ディレクトリを参照し、この方法で編成されている blob の操作プロセスを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="c6e74-164">たとえば、次の一連のブロック blob という名前のコンテナーで`photos`:</span><span class="sxs-lookup"><span data-stu-id="c6e74-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="c6e74-165">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="c6e74-165">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span></span>

<span data-ttu-id="c6e74-166">呼び出すと`ListBlobs`(上記のサンプル) のように、コンテナーに対して、階層化された一覧が返されます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-166">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="c6e74-167">両方が含まれる場合`CloudBlobDirectory`と`CloudBlockBlob`し、次のように、結果の出力ディレクトリと、コンテナー内の blob をそれぞれ表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c6e74-167">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="c6e74-168">必要に応じて、設定することができます、`UseFlatBlobListing`のパラメーター、`ListBlobs`メソッドを`true`します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-168">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="c6e74-169">この場合、コンテナー内のすべての blob として返されます、`CloudBlockBlob`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c6e74-169">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="c6e74-170">呼び出し`ListBlobs`を次のようなフラットな一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-170">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="c6e74-171">また、よう、コンテナーの現在の内容に応じて、結果になります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-171">and, depending on the current contents of your container, the results look like this:</span></span>

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a><span data-ttu-id="c6e74-172">Blob をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-172">Download blobs</span></span>

<span data-ttu-id="c6e74-173">Blob をダウンロードするには、まず blob の参照を取得を呼び出して、`DownloadToStream`メソッド。</span><span class="sxs-lookup"><span data-stu-id="c6e74-173">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="c6e74-174">次の例では、`DownloadToStream`ローカル ファイルに保存できるストリーム オブジェクトに blob の内容を転送する方法。</span><span class="sxs-lookup"><span data-stu-id="c6e74-174">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="c6e74-175">使用することも、`DownloadToStream`メソッドを文字列としての blob のコンテンツをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-175">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="c6e74-176">Blob を削除します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-176">Delete blobs</span></span>

<span data-ttu-id="c6e74-177">Blob を削除するには、まず blob の参照を取得を呼び出して、`Delete`メソッド。</span><span class="sxs-lookup"><span data-stu-id="c6e74-177">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="c6e74-178">非同期的にページ内の blob を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-178">List blobs in pages asynchronously</span></span>

<span data-ttu-id="c6e74-179">大規模な数の blob を一覧表示、または 1 つの一覧作成操作で返される結果の数を制御する場合、結果のページ内の blob を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-179">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="c6e74-180">この例は、大量の結果セットを返すを待機中には実行がブロックされないように、ページで、非同期的に結果を返す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-180">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="c6e74-181">この例の一覧を表示すると、blob をフラット、設定して、階層的な一覧についてを実行することもできますが、`useFlatBlobListing`のパラメーター、`ListBlobsSegmentedAsync`メソッドを`false`します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-181">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="c6e74-182">非同期のメソッドを定義するサンプルを使用して、`async`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-182">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="c6e74-183">``let!``キーワードは、一覧表示タスクが完了するまでに、サンプル メソッドの実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-183">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="c6e74-184">この非同期ルーチンを次のように使用できますようになりました。</span><span class="sxs-lookup"><span data-stu-id="c6e74-184">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="c6e74-185">最初に、一部のダミー データ (このチュートリアルで前に作成されたローカル ファイルを使用) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-185">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="c6e74-186">ここで、ルーチンを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-186">Now, call the routine.</span></span> <span data-ttu-id="c6e74-187">使用する`Async.RunSynchronously`非同期操作の実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-187">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="c6e74-188">追加 blob への書き込み</span><span class="sxs-lookup"><span data-stu-id="c6e74-188">Writing to an append blob</span></span>

<span data-ttu-id="c6e74-189">追加 blob は、ログ記録などの追加操作のために最適化されます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-189">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="c6e74-190">ブロック blob、追加 blob はブロックで構成されますが、blob の末尾に必ず追加される追加 blob に新しいブロックを追加するとします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-190">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="c6e74-191">更新または追加 blob の既存のブロックを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6e74-191">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="c6e74-192">ブロック blob は、追加 blob のブロック Id は公開されません。</span><span class="sxs-lookup"><span data-stu-id="c6e74-192">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="c6e74-193">追加 blob 内の各ブロックは、最大 4 MB までのさまざまなサイズ、追加 blob は最大 50,000 のブロックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-193">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="c6e74-194">追加 blob の最大サイズは 195 GB (4 MB X 50,000 ブロック) よりも少しではそのためです。</span><span class="sxs-lookup"><span data-stu-id="c6e74-194">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="c6e74-195">次の例では、新しい追加 blob を作成し、簡単なログ記録操作をシミュレートするのには、いくつかのデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-195">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="c6e74-196">参照してください[ブロック Blob、ページ Blob、および追加 Blob](https://msdn.microsoft.com/library/azure/ee691964.aspx) blob の 3 つの種類の違いの詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-196">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="c6e74-197">同時実行のアクセス</span><span class="sxs-lookup"><span data-stu-id="c6e74-197">Concurrent access</span></span>

<span data-ttu-id="c6e74-198">使用することができますから複数のクライアントまたは複数のプロセス インスタンスを blob への同時アクセスをサポートする**Etag**または**リース**します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-198">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="c6e74-199">**Etag** -blob またはコンテナーが別のプロセスによって変更されたことを検出する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-199">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="c6e74-200">**リース**の取得だけで、更新可能な書き込みまたは一定期間、blob へのアクセスを削除する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-200">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="c6e74-201">詳細については、次を参照してください。 [Microsoft Azure Storage 内の同時実行を管理する](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-201">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="c6e74-202">名前付けコンテナー</span><span class="sxs-lookup"><span data-stu-id="c6e74-202">Naming containers</span></span>

<span data-ttu-id="c6e74-203">Azure storage 内のすべての blob は、コンテナー内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-203">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="c6e74-204">コンテナーは、blob 名の一部を形成します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-204">The container forms part of the blob name.</span></span> <span data-ttu-id="c6e74-205">たとえば、`mydata`これらサンプル blob Uri 内のコンテナーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-205">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="c6e74-206">コンテナー名は、次の名前付け規則に準拠している、有効な DNS 名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-206">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="c6e74-207">コンテナー名は英字または数字で始まらなければなりませんし、文字、数字、およびダッシュ (-) 文字のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-207">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="c6e74-208">すべてのダッシュ (-) 文字はすぐに前し、後にアルファベットまたは数字; する必要があります。コンテナー名では、連続するダッシュは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="c6e74-208">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="c6e74-209">コンテナー名のすべての文字を小文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-209">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="c6e74-210">コンテナー名は 3 ~ 63 文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-210">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="c6e74-211">コンテナーの名前が小文字に常にする必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c6e74-211">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="c6e74-212">コンテナー名に、大文字を含めるか、それ以外の場合、コンテナーの名前付け規則に違反した場合 400 (Bad Request) エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-212">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="c6e74-213">Blob のセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-213">Managing security for blobs</span></span>

<span data-ttu-id="c6e74-214">既定では、Azure Storage のデータはセキュリティを維持は、アカウント アクセス キーを所有しているユーザー アカウントの所有者へのアクセスを制限することで。</span><span class="sxs-lookup"><span data-stu-id="c6e74-214">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="c6e74-215">ストレージ アカウント内の blob データを共有する必要がある場合は、アカウント アクセス キーのセキュリティを損なうことがなく行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-215">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="c6e74-216">さらに、ネットワーク経由でと、Azure Storage に安全であることを確認する blob データを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-216">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="c6e74-217">Blob データへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-217">Controlling access to blob data</span></span>

<span data-ttu-id="c6e74-218">既定では、ストレージ アカウント内の blob データはストレージ アカウント所有者のみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-218">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="c6e74-219">Blob storage に対する要求の認証には、既定では、アカウント アクセス キーが必要です。</span><span class="sxs-lookup"><span data-stu-id="c6e74-219">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="c6e74-220">ただし、特定の blob データを他のユーザーが利用できるようにする場合があります。</span><span class="sxs-lookup"><span data-stu-id="c6e74-220">However, you might want to make certain blob data available to other users.</span></span>

<span data-ttu-id="c6e74-221">Blob ストレージへのアクセスを制御する方法の詳細については、次を参照してください。[アクセス コントロール上の blob ストレージ セクションの .NET ガイド](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data)します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-221">For details on how to control access to blob storage, see [the .NET guide for blob storage section on access control](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span></span>


### <a name="encrypting-blob-data"></a><span data-ttu-id="c6e74-222">Blob データの暗号化</span><span class="sxs-lookup"><span data-stu-id="c6e74-222">Encrypting blob data</span></span>

<span data-ttu-id="c6e74-223">Azure Storage では、クライアントとサーバーの両方の blob データの暗号化をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c6e74-223">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

<span data-ttu-id="c6e74-224">Blob データの暗号化について詳しくは、次を参照してください。 [blob ストレージ セクションの暗号化には、.NET ガイド](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data)します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-224">For details on encrypting blob data, see [the .NET guide for blob storage section on encryption](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c6e74-225">次の手順</span><span class="sxs-lookup"><span data-stu-id="c6e74-225">Next steps</span></span>

<span data-ttu-id="c6e74-226">これで、Blob storage の基本を学習するは詳細については、これらのリンクに従います。</span><span class="sxs-lookup"><span data-stu-id="c6e74-226">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="c6e74-227">ツール</span><span class="sxs-lookup"><span data-stu-id="c6e74-227">Tools</span></span>
- <span data-ttu-id="c6e74-228">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)の f# 型プロバイダー Blob、Table、および Azure Storage のキューの資産を探索し、それらに対する CRUD 操作を簡単に適用するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c6e74-228">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>
- <span data-ttu-id="c6e74-229">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) f# の API を Microsoft Azure Table Storage サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-229">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) An F# API for using Microsoft Azure Table Storage service</span></span>
- <span data-ttu-id="c6e74-230">[Microsoft Azure ストレージ エクスプ ローラー (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)から Microsoft Windows、OS X、Linux で Azure Storage のデータを視覚的に作業することができますが、無料のスタンドアロン アプリです。</span><span class="sxs-lookup"><span data-stu-id="c6e74-230">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) is a free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="c6e74-231">Blob ストレージのリファレンス</span><span class="sxs-lookup"><span data-stu-id="c6e74-231">Blob storage reference</span></span>

- [<span data-ttu-id="c6e74-232">.NET 用 azure Storage Api</span><span class="sxs-lookup"><span data-stu-id="c6e74-232">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="c6e74-233">Azure ストレージ サービス REST API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c6e74-233">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="c6e74-234">関連ガイド</span><span class="sxs-lookup"><span data-stu-id="c6e74-234">Related guides</span></span>

- [<span data-ttu-id="c6e74-235">C# での Azure Blob Storage の概要</span><span class="sxs-lookup"><span data-stu-id="c6e74-235">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="c6e74-236">Windows 上の AzCopy コマンド ライン ユーティリティを使用したデータを転送します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-236">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="c6e74-237">Linux 上の AzCopy コマンド ライン ユーティリティを使用したデータを転送します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-237">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="c6e74-238">Azure Storage 接続文字列を構成します。</span><span class="sxs-lookup"><span data-stu-id="c6e74-238">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="c6e74-239">Azure Storage チーム ブログ</span><span class="sxs-lookup"><span data-stu-id="c6e74-239">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
