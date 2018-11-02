---
title: F# を使用して Azure File storage の概要します。
description: Azure File storage を使用してクラウドにファイル データを格納し、Azure の仮想マシン (VM) からクラウド ファイル共有をマウントまたはオンプレミス アプリケーションから Windows を実行しています。
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: e772da5f81d2e6827295d0dfe150934a415eb3bb
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2018
ms.locfileid: "33569344"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="a9051-103">F# を使用して Azure File storage の概要します。</span><span class="sxs-lookup"><span data-stu-id="a9051-103">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="a9051-104">Azure File storage は、標準を使用して、クラウド内のファイル共有を提供するサービスで[サーバー メッセージ ブロック (SMB) プロトコル](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="a9051-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="a9051-105">SMB 2.1 と SMB 3.0 の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9051-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="a9051-106">Azure File storage を使用には、迅速かつコストのかかる書き換えを行わずに、azure ファイル共有に依存するレガシ アプリケーションを移行することができます。</span><span class="sxs-lookup"><span data-stu-id="a9051-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="a9051-107">または、オンプレミスのクライアントから Azure 仮想マシンまたはクラウド サービスで実行しているアプリケーションは、デスクトップ アプリケーションの一般的な SMB 共有をマウントすると同様に、クラウド内のファイル共有をマウントできます。</span><span class="sxs-lookup"><span data-stu-id="a9051-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="a9051-108">任意の数のアプリケーション コンポーネントのマウントし、同時に、File storage 共有にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a9051-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="a9051-109">File storage の概念的概要についてを参照してください[file storage 用の .NET ガイド](/azure/storage/storage-dotnet-how-to-use-files)します。</span><span class="sxs-lookup"><span data-stu-id="a9051-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9051-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a9051-110">Prerequisites</span></span>

<span data-ttu-id="a9051-111">このガイドを使用するのにはまず[Azure ストレージ アカウントを作成](/azure/storage/storage-create-storage-account)です。</span><span class="sxs-lookup"><span data-stu-id="a9051-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="a9051-112">このアカウントのストレージ アクセス キーも必要になります。</span><span class="sxs-lookup"><span data-stu-id="a9051-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="a9051-113">作成して、F# スクリプトと開始 F# 対話型</span><span class="sxs-lookup"><span data-stu-id="a9051-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="a9051-114">この記事のサンプルは、F# アプリケーションまたは F# スクリプトのいずれかで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9051-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="a9051-115">F# スクリプトを作成するには、ファイルを作成、`.fsx`拡張機能の例では、 `files.fsx`、F# 開発環境にします。</span><span class="sxs-lookup"><span data-stu-id="a9051-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="a9051-116">次に、使用、[パッケージ マネージャー](package-management.md)など[パケット](https://fsprojects.github.io/Paket/)または[NuGet](https://www.nuget.org/)をインストールする、`WindowsAzure.Storage`パッケージと参照`WindowsAzure.Storage.dll`を使用して、スクリプトで`#r`ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="a9051-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="a9051-117">名前空間宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="a9051-117">Add namespace declarations</span></span>

<span data-ttu-id="a9051-118">次の追加`open`ステートメントの先頭に、`files.fsx`ファイル。</span><span class="sxs-lookup"><span data-stu-id="a9051-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="a9051-119">接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9051-119">Get your connection string</span></span>

<span data-ttu-id="a9051-120">このチュートリアルでは、Azure Storage 接続文字列を必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9051-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="a9051-121">接続文字列の詳細については、次を参照してください。[ストレージ接続文字列を構成](/azure/storage/storage-configure-connection-string)します。</span><span class="sxs-lookup"><span data-stu-id="a9051-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="a9051-122">チュートリアルでは、次のように、スクリプトで、接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="a9051-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="a9051-123">ただし、これは**しないで**の実際のプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a9051-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="a9051-124">ストレージ アカウント キーは、ストレージ アカウントの root パスワードに似ています。</span><span class="sxs-lookup"><span data-stu-id="a9051-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="a9051-125">常に、ストレージ アカウント キーを保護するように注意します。</span><span class="sxs-lookup"><span data-stu-id="a9051-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="a9051-126">ハード コーディング、または他のユーザーにアクセスできるプレーン テキスト ファイルに保存することは、他のユーザーに配布しないでください。</span><span class="sxs-lookup"><span data-stu-id="a9051-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="a9051-127">侵害されていると思われる場合は、Azure Portal を使用して、キーを再生成することができます。</span><span class="sxs-lookup"><span data-stu-id="a9051-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="a9051-128">実際のアプリケーションは、ストレージ接続文字列を維持するために最善の方法は、構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="a9051-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="a9051-129">構成ファイルから接続文字列を取得するには、は、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9051-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="a9051-130">Azure Configuration Manager の使用は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a9051-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="a9051-131">.NET Framework のなどの API を使用することもできます。`ConfigurationManager`型。</span><span class="sxs-lookup"><span data-stu-id="a9051-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="a9051-132">接続文字列を解析します。</span><span class="sxs-lookup"><span data-stu-id="a9051-132">Parse the connection string</span></span>

<span data-ttu-id="a9051-133">接続文字列を解析するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="a9051-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="a9051-134">これにより返されます、`CloudStorageAccount`します。</span><span class="sxs-lookup"><span data-stu-id="a9051-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="a9051-135">ファイル サービス クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9051-135">Create the File service client</span></span>

<span data-ttu-id="a9051-136">`CloudFileClient`型では、File storage に格納されたファイルをプログラムで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a9051-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="a9051-137">サービス クライアントを作成する方法の 1 つを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9051-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="a9051-138">File storage からデータを読み書きするコードを記述する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="a9051-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="a9051-139">ファイル共有を作成します。</span><span class="sxs-lookup"><span data-stu-id="a9051-139">Create a file share</span></span>

<span data-ttu-id="a9051-140">この例では、存在しない場合は、ファイル共有を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9051-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="a9051-141">ルート ディレクトリとサブディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9051-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="a9051-142">ここでは、ルート ディレクトリを取得するルートのサブディレクトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9051-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="a9051-143">まだ存在しない場合は、どちらもタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9051-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="a9051-144">テキストをファイルとしてアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a9051-144">Upload text as a file</span></span>

<span data-ttu-id="a9051-145">この例では、テキストとしてファイルをアップロードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9051-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="a9051-146">ファイル、ファイルのローカル コピーをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a9051-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="a9051-147">ここでは、ローカル ファイルに内容を追加、先ほど作成したファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a9051-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="a9051-148">ファイル共有の最大サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="a9051-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="a9051-149">次の例では、共有の現在の使用状況を確認して、共有のクォータを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9051-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="a9051-150">`FetchAttributes` 共有の設定を呼び出す必要がある`Properties`、および`SetProperties`Azure File storage にローカルの変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="a9051-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="a9051-151">ファイルまたはファイル共有の共有アクセス署名を生成します。</span><span class="sxs-lookup"><span data-stu-id="a9051-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="a9051-152">ファイル共有または個々 のファイルの shared access signature (SAS) を生成することができます。</span><span class="sxs-lookup"><span data-stu-id="a9051-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="a9051-153">Shared access signature を管理するファイル共有に共有アクセス ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a9051-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="a9051-154">共有アクセス ポリシーの作成は推奨、それが侵害された場合は、SAS を取り消す手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9051-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="a9051-155">ここで、作成、共有、共有上のポリシーにアクセスし、そのポリシーを使用して、共有内のファイルを SAS に制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9051-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="a9051-156">作成と共有アクセス署名の使用に関する詳細については、次を参照してください。[を使用して Shared Access Signature (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1)と[の作成と使用して SAS を Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2)します。</span><span class="sxs-lookup"><span data-stu-id="a9051-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="a9051-157">ファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="a9051-157">Copy files</span></span>

<span data-ttu-id="a9051-158">ファイルを別のファイルまたは blob または blob にファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="a9051-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="a9051-159">ファイルまたは blob をファイルに blob をコピーする場合を*する必要があります*同じストレージ アカウント内にコピーする場合でも、ソース オブジェクトを認証する共有アクセス署名 (SAS) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a9051-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="a9051-160">ファイルを別のファイルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a9051-160">Copy a file to another file</span></span>

<span data-ttu-id="a9051-161">ここでは、同じ共有内の別のファイルにファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="a9051-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="a9051-162">このコピー操作は、同じストレージ アカウント内のファイルをコピーするので、コピーを実行するのに共有キー認証を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a9051-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="a9051-163">ファイルを blob にコピーします。</span><span class="sxs-lookup"><span data-stu-id="a9051-163">Copy a file to a blob</span></span>

<span data-ttu-id="a9051-164">ここでは、ファイルを作成して、同じストレージ アカウント内の blob にコピーします。</span><span class="sxs-lookup"><span data-stu-id="a9051-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="a9051-165">コピー操作中にソース ファイルへのアクセスを認証するサービスを使用するソース ファイルの SAS を作成します。</span><span class="sxs-lookup"><span data-stu-id="a9051-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="a9051-166">同じ方法でファイルに blob をコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9051-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="a9051-167">ソース オブジェクトが blob の場合は、コピー操作中にその blob へのアクセスの認証に SAS を作成します。</span><span class="sxs-lookup"><span data-stu-id="a9051-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="a9051-168">メトリックを使用して File storage のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a9051-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="a9051-169">Azure Storage Analytics は、File storage のメトリックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a9051-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="a9051-170">メトリック データを要求のトレースでき、問題を診断できます。</span><span class="sxs-lookup"><span data-stu-id="a9051-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="a9051-171">File storage のメトリックを有効にすることができます、 [Azure Portal](https://portal.azure.com)から実行できますかF#次のように。</span><span class="sxs-lookup"><span data-stu-id="a9051-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="a9051-172">次の手順</span><span class="sxs-lookup"><span data-stu-id="a9051-172">Next steps</span></span>

<span data-ttu-id="a9051-173">Azure File storage の詳細については、これらのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9051-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="a9051-174">概念に関する記事とビデオ</span><span class="sxs-lookup"><span data-stu-id="a9051-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="a9051-175">Windows および Linux 用の azure File Storage: 円滑なクラウド SMB ファイル システム</span><span class="sxs-lookup"><span data-stu-id="a9051-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="a9051-176">Linux で Azure File Storage を使用する方法</span><span class="sxs-lookup"><span data-stu-id="a9051-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="a9051-177">File storage のツールのサポート</span><span class="sxs-lookup"><span data-stu-id="a9051-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="a9051-178">Azure Storage で Azure PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="a9051-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="a9051-179">Microsoft Azure Storage で AzCopy を使用する方法</span><span class="sxs-lookup"><span data-stu-id="a9051-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="a9051-180">Azure Storage で Azure CLI の使用</span><span class="sxs-lookup"><span data-stu-id="a9051-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="a9051-181">参照</span><span class="sxs-lookup"><span data-stu-id="a9051-181">Reference</span></span>

- [<span data-ttu-id="a9051-182">.NET リファレンス用ストレージ クライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="a9051-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="a9051-183">ファイル サービス REST API リファレンス</span><span class="sxs-lookup"><span data-stu-id="a9051-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="a9051-184">ブログの投稿</span><span class="sxs-lookup"><span data-stu-id="a9051-184">Blog posts</span></span>

- [<span data-ttu-id="a9051-185">Azure File storage の一般提供開始</span><span class="sxs-lookup"><span data-stu-id="a9051-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="a9051-186">Inside Azure File Storage</span><span class="sxs-lookup"><span data-stu-id="a9051-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="a9051-187">Microsoft Azure File Service の概要</span><span class="sxs-lookup"><span data-stu-id="a9051-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="a9051-188">Microsoft Azure Files への接続の維持</span><span class="sxs-lookup"><span data-stu-id="a9051-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
