---
title: '方法: アプリケーションをローカライズする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: 8f1251195fdb21ac57030056abc7b5657edb49fa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614620"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="31813-102">方法: アプリケーションをローカライズする</span><span class="sxs-lookup"><span data-stu-id="31813-102">How to: Localize an Application</span></span>
<span data-ttu-id="31813-103">このチュートリアルでは、LocBaml ツールを使用して、ローカライズされたアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31813-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31813-104">LocBaml ツールは、実稼働可能なアプリケーションではありません。</span><span class="sxs-lookup"><span data-stu-id="31813-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="31813-105">それはローカリゼーション API の一部を使用するサンプルとして提供されており、ローカリゼーション ツールを記述する方法を例示します。</span><span class="sxs-lookup"><span data-stu-id="31813-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>   
## <a name="overview"></a><span data-ttu-id="31813-106">概要</span><span class="sxs-lookup"><span data-stu-id="31813-106">Overview</span></span>  
 <span data-ttu-id="31813-107">この説明では、アプリケーションのローカリゼーションの手順を段階を追って示します。</span><span class="sxs-lookup"><span data-stu-id="31813-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="31813-108">最初に、翻訳されるテキストを抽出できるようにアプリケーションを準備します。</span><span class="sxs-lookup"><span data-stu-id="31813-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="31813-109">テキストの翻訳後、翻訳されたテキストを元のアプリケーションの新しいコピーにマージします。</span><span class="sxs-lookup"><span data-stu-id="31813-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>   
## <a name="requirements"></a><span data-ttu-id="31813-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="31813-110">Requirements</span></span>  
 <span data-ttu-id="31813-111">この説明の過程で、コマンド ラインから実行するコンパイラである [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] を使用します。</span><span class="sxs-lookup"><span data-stu-id="31813-111">Over the course of this discussion, you will use [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="31813-112">また、プロジェクト ファイルを使用するよう指示されます。</span><span class="sxs-lookup"><span data-stu-id="31813-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="31813-113">使用する方法の詳細について[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]とプロジェクト ファイルを参照してください[をビルドおよび配置](../app-development/building-and-deploying-wpf-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="31813-113">For instructions on how to use [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="31813-114">この説明のすべての例では、カルチャとして en-US (英語-米国) を使用します。</span><span class="sxs-lookup"><span data-stu-id="31813-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="31813-115">別の言語をインストールしなくても、この例の手順全体の作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="31813-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>   
## <a name="create-a-sample-application"></a><span data-ttu-id="31813-116">サンプルのアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="31813-116">Create a Sample Application</span></span>  
 <span data-ttu-id="31813-117">このステップでは、ローカリゼーション用のアプリケーションを準備します。</span><span class="sxs-lookup"><span data-stu-id="31813-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="31813-118">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] のサンプルでは、この説明のコード サンプルで使用される HelloApp のサンプルが提供されています。</span><span class="sxs-lookup"><span data-stu-id="31813-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="31813-119">このサンプルを使用する場合は、ダウンロード、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ファイルから、 [LocBaml ツール サンプル](https://go.microsoft.com/fwlink/?LinkID=160016)します。</span><span class="sxs-lookup"><span data-stu-id="31813-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
1. <span data-ttu-id="31813-120">ローカリゼーションを開始するポイントまで、アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="31813-120">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="31813-121">[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] がメイン アセンブリとサテライト アセンブリ (.resources.dll の拡張子が付いたファイル) を生成してニュートラルな言語リソースを含めるように、プロジェクト ファイルの開発言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="31813-121">Specify the development language in the project file so that [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="31813-122">HelloApp サンプルのプロジェクト ファイルは HelloApp.csproj です。</span><span class="sxs-lookup"><span data-stu-id="31813-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="31813-123">このファイルに、以下のように特定される開発言語があります。</span><span class="sxs-lookup"><span data-stu-id="31813-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="31813-124">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルに UID を追加します。</span><span class="sxs-lookup"><span data-stu-id="31813-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="31813-125">UID は、ファイルへの変更を追跡して、翻訳する必要がある項目を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="31813-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="31813-126">Uid をファイルに追加するには、実行**updateuid**プロジェクト ファイルで。</span><span class="sxs-lookup"><span data-stu-id="31813-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="31813-127">**msbuild -t:updateuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="31813-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="31813-128">不足していないか、重複する Uid ことを確認するには、実行**checkuid**:</span><span class="sxs-lookup"><span data-stu-id="31813-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="31813-129">**msbuild -t:checkuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="31813-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="31813-130">実行後**updateuid**ファイルに Uid を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="31813-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="31813-131">たとえば、HelloApp の Pane1.xaml ファイルに、以下の内容があるはずです。</span><span class="sxs-lookup"><span data-stu-id="31813-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="31813-132">ニュートラル言語リソースのサテライト アセンブリを作成する</span><span class="sxs-lookup"><span data-stu-id="31813-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="31813-133">ニュートラル言語リソースのサテライト アセンブリを生成するようにアプリケーションを構成した後、アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="31813-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="31813-134">これにより、メイン アプリケーション アセンブリだけでなく、ローカリゼーションで LocBaml が必要とするニュートラル言語リソースのサテライト アセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31813-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="31813-135">アプリケーションをビルドするには</span><span class="sxs-lookup"><span data-stu-id="31813-135">To build the application:</span></span>  
  
1. <span data-ttu-id="31813-136">HelloApp をコンパイルして [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] を作成します。</span><span class="sxs-lookup"><span data-stu-id="31813-136">Compile HelloApp to create a [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)]:</span></span>  
  
     <span data-ttu-id="31813-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="31813-137">**msbuild helloapp.csproj**</span></span>  
  
2. <span data-ttu-id="31813-138">新規作成されたメインのアプリケーション アセンブリ HelloApp.exe は、次のフォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="31813-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3. <span data-ttu-id="31813-139">新規作成されたニュートラル言語リソースのサテライト アセンブリ HelloApp.resources.dll は次のフォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="31813-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="31813-140">LocBaml ツールをビルドする</span><span class="sxs-lookup"><span data-stu-id="31813-140">Build the LocBaml Tool</span></span>  
  
1. <span data-ttu-id="31813-141">LocBaml のビルドに必要なすべてのファイルは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] サンプルに配置されています。</span><span class="sxs-lookup"><span data-stu-id="31813-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="31813-142">C# ファイルをダウンロード、 [LocBaml ツール サンプル](https://go.microsoft.com/fwlink/?LinkID=160016)します。</span><span class="sxs-lookup"><span data-stu-id="31813-142">Download the C# files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
2. <span data-ttu-id="31813-143">ツールをビルドするには、コマンド ラインでプロジェクト ファイル (locbaml.csproj) を実行します。</span><span class="sxs-lookup"><span data-stu-id="31813-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="31813-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="31813-144">**msbuild locbaml.csproj**</span></span>  
  
3. <span data-ttu-id="31813-145">新しく作成された実行可能ファイル (locbaml.exe) を検索するには、bin \release ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="31813-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="31813-146">例: C:\LocBaml\Bin\Release\locbaml.exe</span><span class="sxs-lookup"><span data-stu-id="31813-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4. <span data-ttu-id="31813-147">LocBaml を実行するときに指定できるオプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31813-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    - <span data-ttu-id="31813-148">**解析**または **-p:** 解析 Baml、リソース、または[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)].csv または .txt ファイルを生成するファイル。</span><span class="sxs-lookup"><span data-stu-id="31813-148">**parse** or **-p:** Parses Baml, resources, or [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] files to generate a .csv or .txt file.</span></span>  
  
    - <span data-ttu-id="31813-149">**生成**または **-g:** 翻訳ファイルを使用して、ローカライズされたバイナリ ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="31813-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    - <span data-ttu-id="31813-150">**out**または **-o** {*filedirectory*] **:** 出力ファイル名。</span><span class="sxs-lookup"><span data-stu-id="31813-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    - <span data-ttu-id="31813-151">**カルチャ**または **- cul** {*カルチャ*] **:** 出力アセンブリのロケール。</span><span class="sxs-lookup"><span data-stu-id="31813-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    - <span data-ttu-id="31813-152">**translation** or **-trans** {*translation.csv*] **:** 翻訳またはローカライズされたファイルです。</span><span class="sxs-lookup"><span data-stu-id="31813-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    - <span data-ttu-id="31813-153">**asmpath**または **- asmpath:** {*filedirectory*] **:** 場合、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]コードには、カスタム コントロールが含まれる、指定する必要があります、 **asmpath**カスタム コントロール アセンブリにします。</span><span class="sxs-lookup"><span data-stu-id="31813-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    - <span data-ttu-id="31813-154">**nologo:** ロゴまたは著作権情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="31813-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    - <span data-ttu-id="31813-155">**詳細。** 詳細モードの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="31813-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31813-156">入力の場合は、ツールを実行するときは、オプションの一覧を作成する必要があります、 **LocBaml.exe** ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="31813-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>   
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="31813-157">LocBaml を使用してファイルを解析する</span><span class="sxs-lookup"><span data-stu-id="31813-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="31813-158">LocBaml ツールが作成されたので、これを使用して HelloApp.resources.dll を解析し、ローカライズするテキスト コンテンツを抽出できる状態になりました。</span><span class="sxs-lookup"><span data-stu-id="31813-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="31813-159">LocBaml.exe を、メインのアプリケーション アセンブリが作成された、アプリケーションの bin \debug フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="31813-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="31813-160">サテライト アセンブリ ファイルを解析して、.csv ファイルとして出力を格納するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="31813-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="31813-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="31813-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31813-162">入力ファイル HelloApp.resources.dll が LocBaml.exe と同じディレクトリに存在しない場合は、いずれかのファイルを移動して両方のファイルが同じディレクトリにあるようにします。</span><span class="sxs-lookup"><span data-stu-id="31813-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="31813-163">LocBaml を実行してファイルを解析する際、出力はコンマ区切り (.csv ファイル) またはタブ区切り (.txt ファイル) された 7 つのフィールドで構成されます。</span><span class="sxs-lookup"><span data-stu-id="31813-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="31813-164">HelloApp.resources.dll の解析済みの .csv ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="31813-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="31813-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="31813-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="31813-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="31813-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="31813-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="31813-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="31813-168">7 つのフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="31813-168">The seven fields are:</span></span>  
  
   1. <span data-ttu-id="31813-169">**BAML 名**。</span><span class="sxs-lookup"><span data-stu-id="31813-169">**BAML Name**.</span></span> <span data-ttu-id="31813-170">ソース言語のサテライト アセンブリに関する BAML リソースの名前。</span><span class="sxs-lookup"><span data-stu-id="31813-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2. <span data-ttu-id="31813-171">**リソース キー**。</span><span class="sxs-lookup"><span data-stu-id="31813-171">**Resource Key**.</span></span> <span data-ttu-id="31813-172">ローカライズされたリソースの識別子。</span><span class="sxs-lookup"><span data-stu-id="31813-172">The localized resource identifier.</span></span>  
  
   3. <span data-ttu-id="31813-173">**カテゴリ**。</span><span class="sxs-lookup"><span data-stu-id="31813-173">**Category**.</span></span> <span data-ttu-id="31813-174">値の型です。</span><span class="sxs-lookup"><span data-stu-id="31813-174">The value type.</span></span> <span data-ttu-id="31813-175">参照してください[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)します。</span><span class="sxs-lookup"><span data-stu-id="31813-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4. <span data-ttu-id="31813-176">**読みやすさ**。</span><span class="sxs-lookup"><span data-stu-id="31813-176">**Readability**.</span></span> <span data-ttu-id="31813-177">ローカライザーによって値が読み取れるかどうか。</span><span class="sxs-lookup"><span data-stu-id="31813-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="31813-178">参照してください[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)します。</span><span class="sxs-lookup"><span data-stu-id="31813-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5. <span data-ttu-id="31813-179">**変更可能性**。</span><span class="sxs-lookup"><span data-stu-id="31813-179">**Modifiability**.</span></span> <span data-ttu-id="31813-180">ローカライザーによって値が変更できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="31813-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="31813-181">参照してください[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)します。</span><span class="sxs-lookup"><span data-stu-id="31813-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6. <span data-ttu-id="31813-182">**コメント**。</span><span class="sxs-lookup"><span data-stu-id="31813-182">**Comments**.</span></span> <span data-ttu-id="31813-183">値をローカライズする方法を決定するための値の追加の説明。</span><span class="sxs-lookup"><span data-stu-id="31813-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="31813-184">参照してください[ローカリゼーション属性とコメント](localization-attributes-and-comments.md)します。</span><span class="sxs-lookup"><span data-stu-id="31813-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7. <span data-ttu-id="31813-185">**値**。</span><span class="sxs-lookup"><span data-stu-id="31813-185">**Value**.</span></span> <span data-ttu-id="31813-186">目的のカルチャに翻訳するテキストの値。</span><span class="sxs-lookup"><span data-stu-id="31813-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="31813-187">次の表は、.csv ファイルの区切り記号付きの値にこれらのフィールドをマップする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31813-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="31813-188">BAML 名</span><span class="sxs-lookup"><span data-stu-id="31813-188">BAML name</span></span>|<span data-ttu-id="31813-189">リソース キー</span><span class="sxs-lookup"><span data-stu-id="31813-189">Resource key</span></span>|<span data-ttu-id="31813-190">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="31813-190">Category</span></span>|<span data-ttu-id="31813-191">読みやすさ</span><span class="sxs-lookup"><span data-stu-id="31813-191">Readability</span></span>|<span data-ttu-id="31813-192">変更可能性</span><span class="sxs-lookup"><span data-stu-id="31813-192">Modifiability</span></span>|<span data-ttu-id="31813-193">コメント</span><span class="sxs-lookup"><span data-stu-id="31813-193">Comments</span></span>|<span data-ttu-id="31813-194">[値]</span><span class="sxs-lookup"><span data-stu-id="31813-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="31813-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="31813-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="31813-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="31813-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="31813-197">Ignore</span><span class="sxs-lookup"><span data-stu-id="31813-197">Ignore</span></span>|<span data-ttu-id="31813-198">FALSE</span><span class="sxs-lookup"><span data-stu-id="31813-198">FALSE</span></span>|<span data-ttu-id="31813-199">FALSE</span><span class="sxs-lookup"><span data-stu-id="31813-199">FALSE</span></span>||<span data-ttu-id="31813-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="31813-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="31813-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="31813-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="31813-202">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="31813-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="31813-203">なし</span><span class="sxs-lookup"><span data-stu-id="31813-203">None</span></span>|<span data-ttu-id="31813-204">true</span><span class="sxs-lookup"><span data-stu-id="31813-204">TRUE</span></span>|<span data-ttu-id="31813-205">true</span><span class="sxs-lookup"><span data-stu-id="31813-205">TRUE</span></span>||<span data-ttu-id="31813-206">Hello World</span><span class="sxs-lookup"><span data-stu-id="31813-206">Hello World</span></span>|
   |<span data-ttu-id="31813-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="31813-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="31813-208">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="31813-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="31813-209">なし</span><span class="sxs-lookup"><span data-stu-id="31813-209">None</span></span>|<span data-ttu-id="31813-210">true</span><span class="sxs-lookup"><span data-stu-id="31813-210">TRUE</span></span>|<span data-ttu-id="31813-211">true</span><span class="sxs-lookup"><span data-stu-id="31813-211">TRUE</span></span>||<span data-ttu-id="31813-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="31813-212">Goodbye World</span></span>|
  
   <span data-ttu-id="31813-213">注意のすべての値、**コメント**フィールドに値が含まれていません。 フィールド値をがない場合は空です。</span><span class="sxs-lookup"><span data-stu-id="31813-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="31813-214">としてまたの最初の行の項目が読み取り可能でも変更できますでもないと、"Ignore"が含まれて、**カテゴリ**値がローカライズ可能ではないことを示しますの値。</span><span class="sxs-lookup"><span data-stu-id="31813-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="31813-215">特に、大容量ファイルの解析済みのファイルでローカライズ可能な項目の検出を容易に並べ替えるまたはで項目をフィルター**カテゴリ**、**読みやすさ**、および**Modifiability**.</span><span class="sxs-lookup"><span data-stu-id="31813-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="31813-216">たとえば、読み取りも変更もできない値をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="31813-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>   
## <a name="translate-the-localizable-content"></a><span data-ttu-id="31813-217">ローカライズ可能なコンテンツを翻訳する</span><span class="sxs-lookup"><span data-stu-id="31813-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="31813-218">抽出されたコンテンツを翻訳するために使用可能な任意のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="31813-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="31813-219">これを行う良い方法は、リソースを .csv ファイルに記述し、それらを [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] に表示して、翻訳の変更内容を最後の列 (値) にすることです。</span><span class="sxs-lookup"><span data-stu-id="31813-219">A good way to do this is to write the resources to a .csv file and view them in [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)], making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>   
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="31813-220">LocBaml を使用して新しい .resources.dll ファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="31813-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="31813-221">LocBaml で HelloApp.resources.dll を解析して識別されたコンテンツは翻訳済みであり、元のアプリケーションにマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31813-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="31813-222">使用して、**生成**または **-g**新しいを生成するオプション。 .resources.dll ファイル。</span><span class="sxs-lookup"><span data-stu-id="31813-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="31813-223">新しい HelloApp.resources.dll ファイルを生成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="31813-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="31813-224">カルチャを en-US (/cul:en-US) としてマークします。</span><span class="sxs-lookup"><span data-stu-id="31813-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="31813-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="31813-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31813-226">入力ファイル Hello.csv が実行可能ファイル LocBaml.exe と同じディレクトリに存在しない場合は、いずれかのファイルを移動して、両方のファイルが同じディレクトリにあるようにします。</span><span class="sxs-lookup"><span data-stu-id="31813-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="31813-227">C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll ディレクトリにある古い HelloApp.resources.dll ファイルを新規作成した HelloApp.resources.dll ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31813-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3. <span data-ttu-id="31813-228">ここで "Hello World" と "Goodbye World" をアプリケーション内で翻訳する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31813-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="31813-229">別のカルチャに翻訳するには、翻訳先の言語のカルチャを使用します。</span><span class="sxs-lookup"><span data-stu-id="31813-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="31813-230">フランス語 (カナダ) に翻訳する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31813-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="31813-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="31813-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5. <span data-ttu-id="31813-232">メイン アプリケーション アセンブリと同じアセンブリで、新しいサテライト アセンブリを格納するために、新しいカルチャ固有のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="31813-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="31813-233">フランス語 (カナダ) のフォルダーは "fr-CA" となります。</span><span class="sxs-lookup"><span data-stu-id="31813-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="31813-234">新しいフォルダーに生成されたサテライト アセンブリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="31813-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="31813-235">新しいサテライト アセンブリをテストするには、アプリケーションが実行するカルチャを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31813-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="31813-236">2 つの方法のいずれかでこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="31813-236">You can do this in one of two ways:</span></span>  
  
    - <span data-ttu-id="31813-237">オペレーティング システムの地域設定を変更 (**開始** &#124; **コントロール パネルの** &#124; **地域と言語のオプション**)。</span><span class="sxs-lookup"><span data-stu-id="31813-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    - <span data-ttu-id="31813-238">アプリケーションで、次のコードを App.xaml.cs に追加します。</span><span class="sxs-lookup"><span data-stu-id="31813-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="31813-239">LocBaml を使用するためのヒント</span><span class="sxs-lookup"><span data-stu-id="31813-239">Some Tips for Using LocBaml</span></span>  
  
- <span data-ttu-id="31813-240">カスタム コントロールを定義するすべての依存アセンブリを LocBaml のローカル ディレクトリにコピーするか、GAC にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31813-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="31813-241">ローカリゼーション API は、[!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)] を読み取るときに、依存アセンブリにアクセスできる必要があるため、これが必要になります。</span><span class="sxs-lookup"><span data-stu-id="31813-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)].</span></span>  
  
- <span data-ttu-id="31813-242">メインのアセンブリが署名済みの場合は、生成されたリソース DLL も読み込むために署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="31813-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
- <span data-ttu-id="31813-243">ローカライズされたリソースの DLL は、メインのアセンブリと同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31813-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>   
## <a name="whats-next"></a><span data-ttu-id="31813-244">次の内容</span><span class="sxs-lookup"><span data-stu-id="31813-244">What's Next</span></span>  
 <span data-ttu-id="31813-245">これで、LocBaml ツールの使用方法に関する基本的な知識が得られました。</span><span class="sxs-lookup"><span data-stu-id="31813-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="31813-246">UID を含むファイルを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="31813-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="31813-247">LocBaml ツールを使用することで、ローカライズ可能なコンテンツを抽出するファイルを解析できます。コンテンツを翻訳すると、翻訳済みのコンテンツをマージする .resources.dll ファイルを生成できます。</span><span class="sxs-lookup"><span data-stu-id="31813-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="31813-248">このトピックには、可能性のあるすべての詳細情報は含まれていませんが、LocBaml を使用してアプリケーションをローカライズするために必要な知識は得られました。</span><span class="sxs-lookup"><span data-stu-id="31813-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31813-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="31813-249">See also</span></span>

- [<span data-ttu-id="31813-250">WPF のグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="31813-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="31813-251">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="31813-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
