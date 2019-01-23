---
title: 仮想ディレクトリのセットアップ手順
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: 0f32fd6d65db529ba1015dedd98f99efd7f408c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588109"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="9732b-102">仮想ディレクトリのセットアップ手順</span><span class="sxs-lookup"><span data-stu-id="9732b-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="9732b-103">Windows Communication Foundation (WCF) サンプルは %SystemDrive%\inetpub\wwwroot\servicemodelsamples フォルダーにマップされている servicemodelsamples という仮想ディレクトリを共有するためのものです。</span><span class="sxs-lookup"><span data-stu-id="9732b-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9732b-104">%SystemDrive% は、インターネット インフォメーション サービス (IIS) がインストールされているドライブの場所に応じて、通常は C: または D: になります。</span><span class="sxs-lookup"><span data-stu-id="9732b-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="9732b-105">ファイル Setupvroot.bat と Cleanupvroot.bat ファイルを実行することができます、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9732b-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="9732b-106">この仮想ディレクトリを手動で作成する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9732b-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9732b-107">手順</span><span class="sxs-lookup"><span data-stu-id="9732b-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="9732b-108">IIS 7.0 または 7.5 で仮想ディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="9732b-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="9732b-109">**開始** メニューのをクリックして**実行**、入力**inetmgr**インターネット インフォメーション サービス (IIS) MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="9732b-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="9732b-110">左側のウィンドウで コンピューターの名前を持つノードを展開し、展開、**サイト**ノード。</span><span class="sxs-lookup"><span data-stu-id="9732b-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3.  <span data-ttu-id="9732b-111">右クリック**既定の Web サイト**、し、**アプリケーションの追加**を開く、**アプリケーションの追加ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4.  <span data-ttu-id="9732b-112">ウィンドウで、次のように入力します。`servicemodelsamples`として作成する仮想ディレクトリのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="9732b-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="9732b-113">次のディレクトリを作成します。%SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="9732b-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6.  <span data-ttu-id="9732b-114">物理パスを %SystemDrive%\inetpub\wwwroot\servicemodelsamples に設定します。</span><span class="sxs-lookup"><span data-stu-id="9732b-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="9732b-115">WCF サンプルの多くは、ビルド時にサービス実行可能ファイルをこの場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9732b-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7.  <span data-ttu-id="9732b-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-116">Click **OK**.</span></span> <span data-ttu-id="9732b-117">Web アプリケーションが、WCF サンプル用に作成されました。</span><span class="sxs-lookup"><span data-stu-id="9732b-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9732b-118">このタスクは、すべての WCF サンプルで同じ servicemodelsamples Web アプリケーションを使用するため、1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9732b-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9732b-119">このドキュメントでは、`virtual directory`という用語は `Web application`と同じ意味で使用しています。</span><span class="sxs-lookup"><span data-stu-id="9732b-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="9732b-120">仮想ディレクトリを作成するだけでなく、実行する WCF サービスを有効にするには、そのプロパティを設定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="9732b-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="9732b-121">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9732b-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="9732b-122">仮想ディレクトリを IIS 5.1 または 6.0 で作成するには</span><span class="sxs-lookup"><span data-stu-id="9732b-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="9732b-123">コマンド プロンプト ウィンドウを開き`start inetmgr`インターネット インフォメーション サービス (IIS) MMC スナップインを開きます。</span><span class="sxs-lookup"><span data-stu-id="9732b-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="9732b-124">左側のウィンドウで コンピューターの名前を持つノードを展開し、展開、 **Websites**ノード。</span><span class="sxs-lookup"><span data-stu-id="9732b-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3.  <span data-ttu-id="9732b-125">右クリック**既定の Web サイト**選択 **、新しい仮想ディレクトリ**仮想ディレクトリの作成ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="9732b-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4.  <span data-ttu-id="9732b-126">ウィザードで、次のように入力します。`servicemodelsamples`として作成する仮想ディレクトリのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="9732b-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5.  <span data-ttu-id="9732b-127">パスを %SystemDrive%\inetpub\wwwroot\servicemodelsamples に設定します。</span><span class="sxs-lookup"><span data-stu-id="9732b-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="9732b-128">WCF サンプルの多くは、ビルド時にサービス実行可能ファイルをこの場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9732b-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6.  <span data-ttu-id="9732b-129">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-129">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="9732b-130">既定では、次のチェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9732b-130">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="9732b-131">**Read**</span><span class="sxs-lookup"><span data-stu-id="9732b-131">**Read**</span></span>  
  
    -   <span data-ttu-id="9732b-132">**ASP などのスクリプトを実行します。**</span><span class="sxs-lookup"><span data-stu-id="9732b-132">**Run scripts (such as ASP)**</span></span>  
  
8.  <span data-ttu-id="9732b-133">をクリックして **[次へ]**、順にクリックします**完了**ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="9732b-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9732b-134">このタスクは、すべての WCF サンプルで同じ servicemodelsamples 仮想ディレクトリを使用するため、1 回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9732b-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="9732b-135">IIS 7.0 で追加の仮想ディレクトリのプロパティまたは 7.5 を設定するには</span><span class="sxs-lookup"><span data-stu-id="9732b-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="9732b-136">servicemodelsamples ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="9732b-137">ウィンドウの下端に沿って 2 つのビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9732b-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="9732b-138">選択**機能ビュー**が選択されていない場合。</span><span class="sxs-lookup"><span data-stu-id="9732b-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2.  <span data-ttu-id="9732b-139">エントリをダブルクリック**ディレクトリの参照**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3.  <span data-ttu-id="9732b-140">[操作] ウィンドウで、選択、**を有効にする**オプション。</span><span class="sxs-lookup"><span data-stu-id="9732b-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="9732b-141">これにより、Internet Explorer でディレクトリにアクセスできるようになり、サービスのデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9732b-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="9732b-142">最後に、servicemodelsamples フォルダーのセキュリティ プロパティを、他のユーザーがアクセスできるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9732b-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="9732b-143">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9732b-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="9732b-144">仮想ディレクトリの追加プロパティを IIS 5.1 または 6.0 で設定するには</span><span class="sxs-lookup"><span data-stu-id="9732b-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="9732b-145">Servicemodelsamples ノードを右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9732b-146">既定では、次のチェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="9732b-146">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="9732b-147">**Read**</span><span class="sxs-lookup"><span data-stu-id="9732b-147">**Read**</span></span>  
  
    -   <span data-ttu-id="9732b-148">**[ログ アクセス]**</span><span class="sxs-lookup"><span data-stu-id="9732b-148">**Log visits**</span></span>  
  
    -   <span data-ttu-id="9732b-149">**このリソースします。**</span><span class="sxs-lookup"><span data-stu-id="9732b-149">**Index this resource**</span></span>  
  
3.  <span data-ttu-id="9732b-150">選択、**ディレクトリの参照**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="9732b-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="9732b-151">これにより、Internet Explorer でディレクトリにアクセスできるようになり、サービスのデバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9732b-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="9732b-152">IIS 7.0 または 7.5 でフォルダーのセキュリティ プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="9732b-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1.  <span data-ttu-id="9732b-153">%SystemDrive%\inetpub\wwwroot\servicemodelsamples に移動します。</span><span class="sxs-lookup"><span data-stu-id="9732b-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="9732b-154">Servicemodelsamples フォルダーを右クリックし、をクリックして**共有**または**共有する相手**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3.  <span data-ttu-id="9732b-155">左側に下向きの矢印をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4.  <span data-ttu-id="9732b-156">選択、**検索**エントリ。</span><span class="sxs-lookup"><span data-stu-id="9732b-156">Select the **Find** entry.</span></span> <span data-ttu-id="9732b-157">**ユーザーまたはグループ**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="9732b-157">The **Select Users or Groups** window opens.</span></span>  
  
5.  <span data-ttu-id="9732b-158">**[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-158">Click **Advanced**.</span></span>  
  
6.  <span data-ttu-id="9732b-159">クリックして**場所**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-159">Click **Locations**.</span></span> <span data-ttu-id="9732b-160">**場所**ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="9732b-160">The **Locations** window is now open.</span></span>  
  
7.  <span data-ttu-id="9732b-161">使用するコンピューターのエントリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9732b-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="9732b-162">一覧表示されているドメインやネットワークのエントリではなく、ローカル コンピューターを選択してください。</span><span class="sxs-lookup"><span data-stu-id="9732b-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="9732b-163">コンピューターを選択したらクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-163">After you have selected the computer, click **OK**.</span></span>  
  
8.  <span data-ttu-id="9732b-164">クリックして**検索開始**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-164">Click **Find Now**.</span></span> <span data-ttu-id="9732b-165">これで、ローカル コンピューターに関連付けられたオブジェクトが検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9732b-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="9732b-166">検索、 **IIS_IUSRS**内のエントリ、**名前 (相対識別名)** 列。</span><span class="sxs-lookup"><span data-stu-id="9732b-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="9732b-167">そのエントリを選択し、クリックして**OK**結果ウィンドウの検索を閉じます。</span><span class="sxs-lookup"><span data-stu-id="9732b-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="9732b-168">クリックして**OK**を閉じる、 **ユーザーまたはグループ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="9732b-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="9732b-169">クリックして**共有**変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="9732b-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="9732b-170">共有を有効に変更が完了したら、クリックして**完了**を閉じる、**ファイルの共有**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="9732b-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="9732b-171">フォルダーのセキュリティ プロパティを IIS 5.1 または 6.0 で設定するには</span><span class="sxs-lookup"><span data-stu-id="9732b-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1.  <span data-ttu-id="9732b-172">%SystemDrive%\inetpub\wwwroot\servicemodelsamples に移動します。</span><span class="sxs-lookup"><span data-stu-id="9732b-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2.  <span data-ttu-id="9732b-173">右クリックし、 **servicemodelsamples**フォルダーをクリック**共有とセキュリティ。**</span><span class="sxs-lookup"><span data-stu-id="9732b-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3.  <span data-ttu-id="9732b-174">**[セキュリティ]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-174">Click the **Security** tab.</span></span>  
  
4.  <span data-ttu-id="9732b-175">IIS 6.0 を使用している場合、**グループまたはユーザー名**ボックス、チェックするかどうか**インターネット ゲスト アカウント**が表示されています。</span><span class="sxs-lookup"><span data-stu-id="9732b-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="9732b-176">表示されていない場合:</span><span class="sxs-lookup"><span data-stu-id="9732b-176">If it is not listed:</span></span>  
  
    1.  <span data-ttu-id="9732b-177">**[スタート]** ボタンをクリックし、**コントロール パネル** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="9732b-178">表示されない場合、**ユーザー アカウント**アイコンをクリックします**カテゴリの表示を切り替える**。</span><span class="sxs-lookup"><span data-stu-id="9732b-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3.  <span data-ttu-id="9732b-179">をクリックして、**ユーザー アカウント**アイコン。</span><span class="sxs-lookup"><span data-stu-id="9732b-179">Click the **User Accounts** icon.</span></span>  
  
    4.  <span data-ttu-id="9732b-180">「または、コントロール パネル アイコンを選択する」をクリックして**ユーザー アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5.  <span data-ttu-id="9732b-181">**ユーザー アカウント**ダイアログ ボックスで、をクリックして、**詳細** タブ。</span><span class="sxs-lookup"><span data-stu-id="9732b-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6.  <span data-ttu-id="9732b-182">**[詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-182">Click **Advanced**.</span></span>  
  
    7.  <span data-ttu-id="9732b-183">**ローカル ユーザーとグループ**ダイアログ ボックスで、クリックして展開し、**ユーザー**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="9732b-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8.  <span data-ttu-id="9732b-184">右側のウィンドウでダブルクリック**インターネット ゲスト アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="9732b-185">**プロパティ**名前は、インターネット ゲスト アカウントとして使用 ダイアログ ボックスをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9732b-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="9732b-186">既定では、その名前は "USR_" で始まり、その次にコンピューターの名前が続きます。</span><span class="sxs-lookup"><span data-stu-id="9732b-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="9732b-187">**[プロパティ]** ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9732b-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="9732b-188">閉じる、**ローカル ユーザーとグループ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9732b-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="9732b-189">閉じる、**ユーザー アカウント** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9732b-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="9732b-190">もう一方を閉じる**ユーザー アカウント** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9732b-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="9732b-191">**Servicemodelsamples のプロパティ** ダイアログ ボックスで、**セキュリティ** タブで **追加**。</span><span class="sxs-lookup"><span data-stu-id="9732b-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="9732b-192">バック スラッシュを付加するには、コンピューターの名前を入力し、たとえば、myMachineName でインターネット ユーザー アカウントの名前を貼り付けます\\InternetGuestAccountName %。</span><span class="sxs-lookup"><span data-stu-id="9732b-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="9732b-193">クリックして**名前の確認**追加を確認します。</span><span class="sxs-lookup"><span data-stu-id="9732b-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="9732b-194">名前が有効な場合は、すべての文字が下線付きの大文字になります。</span><span class="sxs-lookup"><span data-stu-id="9732b-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5.  <span data-ttu-id="9732b-195">IIS 6.0 の確認もネットワーク サービスが表示されている、**グループまたはユーザー名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="9732b-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="9732b-196">NETWORK SERVICE が表示されていない場合:</span><span class="sxs-lookup"><span data-stu-id="9732b-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1.  <span data-ttu-id="9732b-197">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9732b-197">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="9732b-198">**ユーザーまたはグループ**コンピューターの名前が続けて円記号にダイアログ ボックスで、種類。</span><span class="sxs-lookup"><span data-stu-id="9732b-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3.  <span data-ttu-id="9732b-199">型**サービス**円記号 (スペースなし) 後にします。</span><span class="sxs-lookup"><span data-stu-id="9732b-199">Type **service** after the backslash (no space).</span></span>  
  
    4.  <span data-ttu-id="9732b-200">クリックして**名前の確認**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-200">Click **Check names**.</span></span>  
  
    5.  <span data-ttu-id="9732b-201">複数の名前が見つかった場合は、選択**ネットワーク サービス** をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9732b-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="9732b-202">クリックして**OK**を閉じる、 **[ユーザーまたはグループ**] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="9732b-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6.  <span data-ttu-id="9732b-203">Windows XP SP2 で IIS 5.1 を使用している場合でインターネット ゲスト アカウントと"aspnet"の両方が表示されていることを確認、**グループまたはユーザー名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="9732b-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="9732b-204">ASPNET ユーザーは、組み込みのメンバーであることに注意してください。**ユーザー**セキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="9732b-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="9732b-205">場合は、次の場合、**ユーザー**グループが表示されます ダイアログ ボックスで、個別のアイテムとして許可されているユーザーの一覧に追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9732b-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="9732b-206">ASPNET の一部であるかどうかにチェックする、**ユーザー**セキュリティ グループ。</span><span class="sxs-lookup"><span data-stu-id="9732b-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1.  <span data-ttu-id="9732b-207">**開始**] メニューのをクリックして**コントロール パネルの [** します。</span><span class="sxs-lookup"><span data-stu-id="9732b-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="9732b-208">をクリックして、**ユーザー アカウント**アイコン。</span><span class="sxs-lookup"><span data-stu-id="9732b-208">Click the **User Accounts** icon.</span></span>  
  
    3.  <span data-ttu-id="9732b-209">**グループ**列、いることを確認の値は、 **ASPNET**は「ユーザー」にします。</span><span class="sxs-lookup"><span data-stu-id="9732b-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9732b-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="9732b-210">See also</span></span>
- [<span data-ttu-id="9732b-211">インターネット インフォメーション サービスのホスティング手順</span><span class="sxs-lookup"><span data-stu-id="9732b-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
