---
title: JSON Web トークン ハンドラー パッケージのダウンロード
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 8f878d23afd76488de7da03f16f72cbfa43c17d7
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316481"
---
# <a name="download-the-json-web-token-handler-package"></a><span data-ttu-id="8b4d9-102">JSON Web トークン ハンドラー パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-102">Download the JSON Web Token Handler Package</span></span>

<span data-ttu-id="8b4d9-103">このトピックでは、JSON Web トークン ハンドラーをダウンロードしてプロジェクトで使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>

<span data-ttu-id="8b4d9-104">JSON Web トークン ハンドラー拡張機能は、プロジェクトに必要なアセンブリと参照を追加する NuGet パッケージとして入手できます。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-104">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="8b4d9-105">まだ NuGet がインストールされていない場合は、[nuget.org](https://nuget.org) にアクセスしてインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="8b4d9-106">NuGet の「[JSON Web Token Handler](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)」 (JSON Web トークン ハンドラー) ページにアクセスすると、拡張機能のバージョン履歴を参照できます。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-106">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="8b4d9-107">パッケージ マネージャー GUI を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="8b4d9-108">Visual Studio の**ソリューション エクスプローラー**でプロジェクトを右クリックし、**[NuGet パッケージの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="8b4d9-109">**[NuGet パッケージの管理]** ウィンドウで、検索ボックスをクリックし、「`JWT Token Handler`」と入力して **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-109">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>

3. <span data-ttu-id="8b4d9-110">結果ペインから、最初の結果の **[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="8b4d9-111">パッケージのダウンロードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-111">The package will begin downloading.</span></span> <span data-ttu-id="8b4d9-112">プロジェクトに追加される前に、[License Acceptance] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="8b4d9-113">ライセンス条項に同意する場合は、**[I Accept]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="8b4d9-114">最新の JSON Web トークン ハンドラー アセンブリがダウンロードされ、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-114">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="8b4d9-115">パッケージ マネージャー コンソールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="8b4d9-116">Visual Studio で、次のようにクリックします。**ツール** > **NuGet パッケージ マネージャー** > **パッケージ マネージャー コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="8b4d9-117">**[パッケージ マネージャー コンソール]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="8b4d9-118">次のテキストを入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. <span data-ttu-id="8b4d9-119">最新の JSON Web トークン ハンドラー アセンブリがダウンロードされ、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8b4d9-119">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>