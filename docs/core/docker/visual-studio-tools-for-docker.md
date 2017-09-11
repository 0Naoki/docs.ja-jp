---
title: Visual Studio Tools for Docker
description: "Visual Studio Tools for Docker を使用する"
keywords: .NET, .NET Core, Docker, ASP.NET Core, Visual Studio
author: spboyer
ms.author: shboyer
ms.date: 04/27/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 1f3b9a68-4dea-4b60-8cb3-f46164eedbbf
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 113d470a55fd92704de0e6def392a6e0a1a3a118
ms.contentlocale: ja-jp
ms.lasthandoff: 08/25/2017

---

# <a name="visual-studio-tools-for-docker"></a><span data-ttu-id="368ff-104">Visual Studio Tools for Docker</span><span class="sxs-lookup"><span data-stu-id="368ff-104">Visual Studio Tools for Docker</span></span>

<span data-ttu-id="368ff-105">[Docker for Windows](https://docs.docker.com/docker-for-windows/install/) を含む [Microsoft Visual Studio 2017](https://www.visualstudio.com/) では、Windows と Linux コンテナーを使用した .NET Framework および .NET Core の Web アプリケーションやコンソール アプリケーションのビルド、デバッグ、実行をサポートします。</span><span class="sxs-lookup"><span data-stu-id="368ff-105">[Microsoft Visual Studio 2017](https://www.visualstudio.com/) with [Docker for Windows](https://docs.docker.com/docker-for-windows/install/) supports building, debugging, and running .NET Framework and .NET Core web and console applications using Windows and Linux containers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="368ff-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="368ff-106">Prerequisites</span></span>

- <span data-ttu-id="368ff-107">.NET Core ワークロードを含む [Microsoft Visual Studio 2017](https://www.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="368ff-107">[Microsoft Visual Studio 2017](https://www.visualstudio.com/) with .NET Core workload</span></span>
- [<span data-ttu-id="368ff-108">Docker for Windows</span><span class="sxs-lookup"><span data-stu-id="368ff-108">Docker for Windows</span></span>](https://docs.docker.com/docker-for-windows/install/)

## <a name="installation-and-setup"></a><span data-ttu-id="368ff-109">インストールとセットアップ</span><span class="sxs-lookup"><span data-stu-id="368ff-109">Installation and setup</span></span>

<span data-ttu-id="368ff-110">.NET Core ワークロードで [Microsoft Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="368ff-110">Install [Microsoft Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) with the .NET Core workload.</span></span>

<span data-ttu-id="368ff-111">Docker をインストールする場合、「[Docker for Windows: What to know before you install](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install)」 (Docker for Windows: インストール前に知っておくべきこと) の情報を確認し、[Docker for Windows](https://docs.docker.com/docker-for-windows/install/) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="368ff-111">For Docker installation, review the information at [Docker for Windows: What to know before you install](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install) and install [Docker For Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

<span data-ttu-id="368ff-112">Docker for Windows では、**[共有ドライブ](https://docs.docker.com/docker-for-windows/#shared-drives)**を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="368ff-112">A required configuration is to setup **[Shared Drives](https://docs.docker.com/docker-for-windows/#shared-drives)** in Docker for Windows.</span></span> <span data-ttu-id="368ff-113">この設定は、ボリュームのマップとデバッグのサポートで必要です。</span><span class="sxs-lookup"><span data-stu-id="368ff-113">The setting is required for the volume mapping and debugging support.</span></span>

<span data-ttu-id="368ff-114">システム トレイの Docker アイコンを右クリックして **[設定]** をクリックし、**[Shared Drives]\(共有ドライブ\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="368ff-114">Right click the Docker icon in the System Tray, click **Settings** and select **Shared Drives**.</span></span> <span data-ttu-id="368ff-115">Docker によるファイルの格納先となるドライブを選択して、変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="368ff-115">Select the drive where Docker will store your files and apply changes.</span></span>

![共有ドライブ](./media/visual-studio-tools-for-docker/settings-shared-drives-win.png)

## <a name="create-an-aspnet-web-application-and-add-docker-support"></a><span data-ttu-id="368ff-117">ASP.NET Web アプリケーションを作成し、Docker のサポートを追加する</span><span class="sxs-lookup"><span data-stu-id="368ff-117">Create an ASP.NET Web Application and add Docker Support</span></span>

<span data-ttu-id="368ff-118">Visual Studio を使用して、新しい ASP.NET Core Web アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="368ff-118">Using Visual Studio, create a new ASP.NET Core Web Application.</span></span> <span data-ttu-id="368ff-119">アプリケーションが読み込まれたら、[**プロジェクト**] メニューの 「**Add Docker Support**」 (Docker サポートの追加) を選択するか、ソリューション エクスプローラーからプロジェクトを右クリックし、[**追加**] > 「**Docker Support**」 (Docker サポート) の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="368ff-119">When the application is loaded, either select **Add Docker Support** from the **Project Menu** or right click the project from the Solution Explorer and select **Add** > **Docker Support**.</span></span>

<span data-ttu-id="368ff-120">[プロジェクト] メニュー</span><span class="sxs-lookup"><span data-stu-id="368ff-120">Project Menu</span></span>

![[プロジェクト]、「Add Docker Support」 (Docker サポートの追加)](./media/visual-studio-tools-for-docker/project-add-docker-support.png)

<span data-ttu-id="368ff-122">プロジェクトのコンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="368ff-122">Project Context Menu</span></span>

![[追加]、「Docker Support」 (Docker サポート) を右クリック](./media/visual-studio-tools-for-docker/right-click-add-docker-support.png)

<span data-ttu-id="368ff-124">プロジェクトに Docker サポートを追加する場合、Windows または Linux のいずれかのコンテナーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="368ff-124">When you add Docker support to your project, you can choose either Windows or Linux containers.</span></span> <span data-ttu-id="368ff-125">(Docker ホストが同じコンテナーの種類を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="368ff-125">(The Docker host must be running the same container type.</span></span> <span data-ttu-id="368ff-126">実行中の Docker インスタンスでコンテナーの種類を変更する必要がある場合、システム トレイの **Docker** アイコンを右クリックして、**[Switch to Windows containers]\(Windows コンテナーに切り替える\)**、または **[Switch to Linux containers]\(Linux コンテナーに切り替える\)** を選択します。)</span><span class="sxs-lookup"><span data-stu-id="368ff-126">If you need change the container type in the running Docker instance, right click the **Docker** icon in the System Tray, and choose **Switch to Windows containers** or **Switch to Linux containers**.)</span></span> 

<span data-ttu-id="368ff-127">プロジェクトに次のファイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="368ff-127">The following files are added to the project.</span></span>

- <span data-ttu-id="368ff-128">**Dockerfile**: ASP.NET Core アプリケーション用の Docker ファイルは、[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore) イメージに基づきます。</span><span class="sxs-lookup"><span data-stu-id="368ff-128">**Dockerfile**: the Docker file for ASP.NET Core applications is based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore) image.</span></span> <span data-ttu-id="368ff-129">このイメージには、Just-In-Time (JIT) にコンパイルされてパフォーマンスが向上した ASP.NET Core NuGet パッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="368ff-129">This image includes the ASP.NET Core NuGet packages, which have been pre-jitted improving startup performance.</span></span> <span data-ttu-id="368ff-130">.NET Core のコンソール アプリケーションを構築するとき、Dockerfile の FROM は最新の [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet) イメージを参照します。</span><span class="sxs-lookup"><span data-stu-id="368ff-130">When building .NET Core Console Applications, the Dockerfile FROM will reference the most recent [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet) image.</span></span>   
- <span data-ttu-id="368ff-131">**docker-compose.yml**: docker-compose build/run と共に実行され構築されるイメージの集合を定義するために使用されるベースとなる Docker Compose ファイル。</span><span class="sxs-lookup"><span data-stu-id="368ff-131">**docker-compose.yml**: base Docker Compose file used to define the collection of images to be built and run with docker-compose build/run.</span></span>   
- <span data-ttu-id="368ff-132">**docker-compose.dev.debug.yml**: 構成がデバッグに設定されている場合の反復的な変更用の追加の docker-compose ファイル。</span><span class="sxs-lookup"><span data-stu-id="368ff-132">**docker-compose.dev.debug.yml**: additional docker-compose file with for iterative changes when your configuration is set to debug.</span></span> <span data-ttu-id="368ff-133">Visual Studio は -f docker-compose.yml -f docker-compose.dev.debug.yml を呼び出し、これらをマージします。</span><span class="sxs-lookup"><span data-stu-id="368ff-133">Visual Studio will call -f docker-compose.yml -f docker-compose.dev.debug.yml to merge these together.</span></span> <span data-ttu-id="368ff-134">この構成ファイルは、Visual Studio の開発ツールによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="368ff-134">This compose file is used by Visual Studio development tools.</span></span>   
- <span data-ttu-id="368ff-135">**docker-compose.dev.release.yml**: リリース定義をデバッグする、追加の Docker Compose ファイル。</span><span class="sxs-lookup"><span data-stu-id="368ff-135">**docker-compose.dev.release.yml**: additional Docker Compose file to debug your release definition.</span></span> <span data-ttu-id="368ff-136">実稼働イメージの内容を変更しないように、デバッガーをボリューム マウントします。</span><span class="sxs-lookup"><span data-stu-id="368ff-136">It will volume mount the debugger so it doesn't change the contents of the production image.</span></span>  

<span data-ttu-id="368ff-137">docker-compose.yml ファイルには、プロジェクトの実行時に作成されたイメージの名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="368ff-137">The docker-compose.yml file contains the name of the image that is created when project is run.</span></span> 

```
version '2'

services:
  hellodockertools:
    image:  user/hellodockertools${TAG}
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "80"
``` 

<span data-ttu-id="368ff-138">この例では、`image: user/hellodockertools${TAG}` によってアプリケーションが**デバッグ** モードで実行されるとき、`user/hellodockertools:dev` が生成され、**リリース** モードで実行されるときに、`user/hellodockertools:latest` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="368ff-138">In this example, `image: user/hellodockertools${TAG}` generates the image `user/hellodockertools:dev` when the application is run in **Debug** mode and `user/hellodockertools:latest` in **Release** mode respectively.</span></span> 

<span data-ttu-id="368ff-139">イメージをレジストリにプッシュする場合、`user` を Docker Hub のユーザー名に変更してください。</span><span class="sxs-lookup"><span data-stu-id="368ff-139">You will want to change the `user` to your Docker Hub username if you plan to push the image to the registry.</span></span> <span data-ttu-id="368ff-140">たとえば、`spboyer/hellodockertools` や、構成に応じて `privateregistry.domain.com/` のプライベート レジストリ url に変更します。</span><span class="sxs-lookup"><span data-stu-id="368ff-140">For example, `spboyer/hellodockertools`, or change to your private registry url `privateregistry.domain.com/` depending on your configuration.</span></span>

### <a name="debugging"></a><span data-ttu-id="368ff-141">デバッグ</span><span class="sxs-lookup"><span data-stu-id="368ff-141">Debugging</span></span>

<span data-ttu-id="368ff-142">ツールバーのデバッグ ドロップダウンから [**Docker**] を選択し、F5 を使用してアプリケーションのデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="368ff-142">Select **Docker** from the debug dropdown in the toolbar and use F5 to start debugging the application.</span></span> 

- <span data-ttu-id="368ff-143">(キャッシュにない場合) microsoft/aspnetcore イメージが取得されます</span><span class="sxs-lookup"><span data-stu-id="368ff-143">The microsoft/aspnetcore image is acquired (if not already in your cache)</span></span>
- <span data-ttu-id="368ff-144">ASPNETCORE_ENVIRONMENT は、コンテナーで Development に設定されます</span><span class="sxs-lookup"><span data-stu-id="368ff-144">ASPNETCORE_ENVIRONMENT is set to Development within the container</span></span>
- <span data-ttu-id="368ff-145">ポート 80 が公開され、localhost 用に動的に割り当てられているポートにマップされます。</span><span class="sxs-lookup"><span data-stu-id="368ff-145">PORT 80 is EXPOSED and mapped to a dynamically assigned port for localhost.</span></span> <span data-ttu-id="368ff-146">このポートは、docker ホストによって決定され、docker ps でクエリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="368ff-146">The port is determined by the docker host and can be queried with docker ps.</span></span> 
- <span data-ttu-id="368ff-147">アプリケーションがコンテナーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="368ff-147">Your application is copied to the container</span></span>
- <span data-ttu-id="368ff-148">動的に割り当てられたポートを使用して、デバッガーがコンテナーにアタッチされ、既定のブラウザーが起動します。</span><span class="sxs-lookup"><span data-stu-id="368ff-148">Default browser is launched with the debugger attached to the container, using the dynamically assigned port.</span></span> 

<span data-ttu-id="368ff-149">構築された結果の Docker イメージは `microsoft/aspnetcore` イメージをベース イメージとするアプリケーションの `dev` イメージです。</span><span class="sxs-lookup"><span data-stu-id="368ff-149">The resulting Docker image built is the `dev` image of your application with the `microsoft/aspnetcore` images as the base image.</span></span>
<span data-ttu-id="368ff-150">注: デバッグ構成では、反復にボリューム マウントを使用するため、dev イメージにはアプリのコンテンツは含みません。</span><span class="sxs-lookup"><span data-stu-id="368ff-150">Note: the dev image is empty of your app contents as Debug confgurations use volume mounting to provide the iterative experience.</span></span> <span data-ttu-id="368ff-151">イメージをプッシュするには、リリース構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="368ff-151">To push an image, use the Release configuration.</span></span>

```console
REPOSITORY                  TAG         IMAGE ID            CREATED         SIZE
spboyer/hellodockertools    dev         0b6e2e44b3df        4 minutes ago   268.9 MB
microsoft/aspnetcore        1.0.1       189ad4312ce7        5 days ago      268.9 MB
```

<span data-ttu-id="368ff-152">アプリケーションは、`docker ps` コマンドを実行して参照できるコンテナーを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="368ff-152">The application is running using the container which you can see by running the `docker ps` command.</span></span>

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   4 minutes ago       Up 4 minutes        0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="edit-and-continue"></a><span data-ttu-id="368ff-153">エディット コンティニュ</span><span class="sxs-lookup"><span data-stu-id="368ff-153">Edit and Continue</span></span>

<span data-ttu-id="368ff-154">静的なファイルや razor テンプレート ファイル (.cshtml) に対する変更は、コンパイルをする必要なく、自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="368ff-154">Changes to static files and/or razor template files (.cshtml) are automatically updated without the need of a compilation step.</span></span> <span data-ttu-id="368ff-155">変更を行って保存し、タップしてブラウザーを更新し、更新を確認します。</span><span class="sxs-lookup"><span data-stu-id="368ff-155">Make the change, save and tap refresh in the browser to view the update.</span></span>  

<span data-ttu-id="368ff-156">コード ファイルを変更した場合、コンパイルを行い、コンテナー内で Kestrel を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="368ff-156">Modifications to code files require compiling and a restart of Kestrel within the container.</span></span> <span data-ttu-id="368ff-157">変更後、CTRL キーを押しながら F5 キーを使用して、手順を実行して、コンテナー内でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="368ff-157">After making the change, use CTRL + F5 to perform the process and start the application within the container.</span></span> <span data-ttu-id="368ff-158">Docker コンテナーは再構築されたり、停止されたりすることはありません。コマンド ラインから `docker ps` を使用すると、元のコンテナーが 10 分前と同じ状態で実行されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="368ff-158">The Docker container is not rebuilt or stopped; using `docker ps` in the command line you can see that the original container is still running as of 10 minutes ago.</span></span> 

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   10 minutes ago      Up 10 minutes       0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="publishing-docker-images"></a><span data-ttu-id="368ff-159">Docker イメージの発行</span><span class="sxs-lookup"><span data-stu-id="368ff-159">Publishing Docker images</span></span>

<span data-ttu-id="368ff-160">アプリケーションの開発とデバッグのサイクルが完了したら、Visual Studio Tools for Docker でアプリケーションの実稼働イメージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="368ff-160">Once you have completed the develop and debug cycle of your application, the Visual Studio Tools for Docker will help you create the production image of your application.</span></span> <span data-ttu-id="368ff-161">デバッグ ドロップダウンを [**リリース**] に変更し、アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="368ff-161">Change the debug dropdown to **Release** and build the application.</span></span> <span data-ttu-id="368ff-162">このツールにより、イメージが、プライベート レジストリまたは Docker Hub にプッシュできる `:latest` タグ付きで生成されます。</span><span class="sxs-lookup"><span data-stu-id="368ff-162">The tooling will produce the image with the `:latest` tag which you can push to your private registry or Docker Hub.</span></span> 

<span data-ttu-id="368ff-163">`docker images` を使用すると、イメージの一覧を確認できます。</span><span class="sxs-lookup"><span data-stu-id="368ff-163">Using the `docker images` you can see the list of images.</span></span>

```console
REPOSITORY                 TAG                 IMAGE ID            CREATED             SIZE
spboyer/hellodockertools   latest              8184ae38ba91        5 seconds ago       278.4 MB
spboyer/hellodockertools   dev                 0b6e2e44b3df        About an hour ago   268.9 MB
microsoft/aspnetcore       1.0.1               189ad4312ce7        5 days ago          268.9 MB
```

<span data-ttu-id="368ff-164">**dev** イメージと比較した場合、実稼働またはリリース イメージはサイズが小さいと思うかもしれません。しかし、ボリューム マッピングを使用することにより、デバッガーとアプリケーションは実際はコンテナーではなくローカル マシンから実行されます。</span><span class="sxs-lookup"><span data-stu-id="368ff-164">There may be an expectation for the production or release image to be smaller in size by comparison to the **dev** image, however through the use of the volume mapping; the debugger and application were actually being run from your local machine and not within the container.</span></span> <span data-ttu-id="368ff-165">**latest** イメージには、ホスト コンピューターでアプリケーションを実行するために必要なアプリケーションのコード全体がパッケージ化されているため、デルタはアプリケーション コードのサイズです。</span><span class="sxs-lookup"><span data-stu-id="368ff-165">The **latest** image has packaged the entire application code needed to run the application on a host machine, therefore the delta is the size of your application code.</span></span>

