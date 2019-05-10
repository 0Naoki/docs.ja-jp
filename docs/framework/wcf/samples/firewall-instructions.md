---
title: ファイアウォール手順
ms.date: 03/30/2017
ms.assetid: a7dc429f-65ac-4faf-974a-77d5fb977fe1
ms.openlocfilehash: 06e5ba64ab0ec3558e4c773c9cb21f961384e0c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650041"
---
# <a name="firewall-instructions"></a><span data-ttu-id="0d792-102">ファイアウォール手順</span><span class="sxs-lookup"><span data-stu-id="0d792-102">Firewall Instructions</span></span>
<span data-ttu-id="0d792-103">Windows Communication Foundation (WCF) のサンプルが機能できるようにいくつかのファイアウォールの プログラムとポートを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d792-103">You must enable several ports or programs in the firewall so that the Windows Communication Foundation (WCF) samples can function.</span></span> <span data-ttu-id="0d792-104">サンプルの多くは、通信する際に 8000 ～ 8003 の範囲のポートと 9000 のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="0d792-104">Many of the samples communicate by using ports in the range 8000-8003, and port 9000.</span></span> <span data-ttu-id="0d792-105">既定ではファイアウォールが有効なので、こうしたポートにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="0d792-105">The firewall is turned on by default and prevents access to these ports.</span></span> <span data-ttu-id="0d792-106">サンプル用にファイアウォールを有効にするには、要件とセキュリティ環境に応じて次のいずれかの手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d792-106">To enable the firewall for the samples, complete one of the following procedures, depending on your requirements and security environment:</span></span>  
  
- <span data-ttu-id="0d792-107">オプション 1:実行中のサンプルを対話形式で有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d792-107">Option 1: Interactively enable samples while running.</span></span> <span data-ttu-id="0d792-108">ファイアウォールの構成をあらかじめ変更することなく、サンプルのビルドおよび実行の開始に進みます。</span><span class="sxs-lookup"><span data-stu-id="0d792-108">Make no advance changes to your firewall configuration and proceed to start building and running the samples.</span></span> <span data-ttu-id="0d792-109">サンプルを実行すると、ときに、 **Windows セキュリティの警告** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d792-109">When a sample is run, a **Windows Security Alert** dialog box appears.</span></span> <span data-ttu-id="0d792-110">対象のプログラムを、ブロック解除の一覧に対話形式で追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d792-110">The sample program in question can then be added interactively to an unblocked list.</span></span> <span data-ttu-id="0d792-111">この手順では、この後サンプルを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d792-111">With this procedure, you may have to then restart the sample.</span></span>  
  
- <span data-ttu-id="0d792-112">オプション 2:サンプル プログラムを事前に有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d792-112">Option 2: Enable sample programs in advance.</span></span> <span data-ttu-id="0d792-113">開始、**コントロール パネルの Windows ファイアウォール**アプレットとサンプル プログラムを実行する計画の有効化します。</span><span class="sxs-lookup"><span data-stu-id="0d792-113">Start the **Windows Firewall Control Panel** applet and enable the sample programs you plan to run.</span></span> <span data-ttu-id="0d792-114">実行可能ファイルが存在するように、プログラムを最初にビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d792-114">You must build the programs first so the executable files exist.</span></span> <span data-ttu-id="0d792-115">手順の詳細については、後述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d792-115">You can find more detailed instructions in the following procedure.</span></span>  
  
- <span data-ttu-id="0d792-116">オプション 3:ポートの範囲を事前に有効にします。</span><span class="sxs-lookup"><span data-stu-id="0d792-116">Option 3: Enable a port range in advance.</span></span> <span data-ttu-id="0d792-117">開始、 \*\*Windows ファイアウォール\*\*\*\*コントロール パネルの \*\*アプレットと有効にするポート 80、443、8000 ~ 8003、9000、サンプルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d792-117">Start the **Windows Firewall** **Control Panel** applet and enable ports 80, 443, 8000-8003 and 9000, which are used by the samples.</span></span> <span data-ttu-id="0d792-118">手順の詳細については、後述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d792-118">You can find more detailed instructions in the following procedure.</span></span> <span data-ttu-id="0d792-119">このオプションは他の手順よりも安全性が低くなります。サンプルだけでなく、任意のプログラムでこれらのポートを使用できるようになるからです。</span><span class="sxs-lookup"><span data-stu-id="0d792-119">This option is less secure than the others because it allows any program to use these ports, not just the samples.</span></span>  
  
 <span data-ttu-id="0d792-120">どの手順を使用するか判断に迷う場合は、最初のオプションを選択してください。</span><span class="sxs-lookup"><span data-stu-id="0d792-120">If you are unsure of which procedure to use, choose the first option.</span></span> <span data-ttu-id="0d792-121">他のベンダのファイアウォールを実行している場合も、同様の変更が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d792-121">If you are running a firewall from another vendor, you might need to make similar changes.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0d792-122">ファイアウォールの構成を変更すると、セキュリティに影響します。</span><span class="sxs-lookup"><span data-stu-id="0d792-122">Changing your firewall configuration affects your security.</span></span> <span data-ttu-id="0d792-123">変更内容は記録し、サンプルの使用が終わったらそれらの変更点を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d792-123">It is recommended that you record the changes you make and remove them when you are finished working with the samples.</span></span>  
  
### <a name="to-enable-samples-programs-in-advance"></a><span data-ttu-id="0d792-124">サンプル プログラムをあらかじめ有効にしておくには</span><span class="sxs-lookup"><span data-stu-id="0d792-124">To enable samples programs in advance</span></span>  
  
1. <span data-ttu-id="0d792-125">このサンプルをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0d792-125">Build the sample.</span></span>  
  
2. <span data-ttu-id="0d792-126">をクリックして**開始**、 をクリックして**実行**、および種類`firewall.cpl`します。</span><span class="sxs-lookup"><span data-stu-id="0d792-126">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="0d792-127">開き、**コントロール パネルの Windows ファイアウォール**アプレットです。</span><span class="sxs-lookup"><span data-stu-id="0d792-127">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d792-128">Windows ファイアウォールを介して通信する機能が必要なサンプルを実行するには、ファイアウォール設定を変更するための権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d792-128">You must have permission to change the Firewall settings to run samples that require the ability to communicate through the Windows Firewall.</span></span> <span data-ttu-id="0d792-129">一部のファイウォール設定を変更できず、コンピューターがドメインに接続される場合は、システム管理者がグループ ポリシーを使用してファイアウォール設定を管理している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d792-129">If some firewall settings are unavailable and your computer is connected to a domain, your system administrator might be controlling these settings through Group Policy.</span></span>  
  
3. <span data-ttu-id="0d792-130">Windows ファイアウォールを介したプログラムを許可するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d792-130">Complete one of the following operating specific steps to allow a program through the Windows Firewall:</span></span>  
  
    - <span data-ttu-id="0d792-131">Windows 7 または Windows Server 2008 r2 では、をクリックして**プログラムまたは Windows ファイアウォール経由の機能を許可**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-131">On Windows 7 or Windows Server 2008 r2, click **Allow a program or feature through Windows Firewall**.</span></span> <span data-ttu-id="0d792-132">をクリックして**設定を変更する**、許可**別のプログラムしています**.</span><span class="sxs-lookup"><span data-stu-id="0d792-132">Click **Change Settings**, Allow **Another Program…**.</span></span>  
  
    - <span data-ttu-id="0d792-133">[[!INCLUDE[wv](../../../../includes/wv-md.md)]または[!INCLUDE[lserver](../../../../includes/lserver-md.md)]、] をクリックして**Windows ファイアウォールによるプログラムの許可**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-133">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], click **Allow a program through Windows Firewall**.</span></span>  
  
4. <span data-ttu-id="0d792-134">**例外**] タブで [**プログラムの追加**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-134">On the **Exceptions** tab, click **Add Program**.</span></span>  
  
5. <span data-ttu-id="0d792-135">をクリックして、**参照**ボタンをクリックしを実行するサンプルの実行可能ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d792-135">Click the **Browse** button and select the executable file of the sample you plan to run.</span></span>  
  
6. <span data-ttu-id="0d792-136">実行する予定のすべてのサンプルの実行可能ファイルを追加するまで、手順 4. と 5. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0d792-136">Repeat steps 4 and 5 until you have added the executable files of all the samples you plan to run.</span></span>  
  
7. <span data-ttu-id="0d792-137">クリックして**OK**ファイアウォール アプレットを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0d792-137">Click **OK** to close the firewall applet.</span></span>  
  
### <a name="to-enable-a-port-range-in-advance"></a><span data-ttu-id="0d792-138">ポート範囲をあらかじめ有効にしておくには</span><span class="sxs-lookup"><span data-stu-id="0d792-138">To enable a port range in advance</span></span>  
  
1. <span data-ttu-id="0d792-139">をクリックして**開始**、 をクリックして**実行**、および種類`firewall.cpl`します。</span><span class="sxs-lookup"><span data-stu-id="0d792-139">Click **Start**, click **Run**, and type `firewall.cpl`.</span></span> <span data-ttu-id="0d792-140">開き、**コントロール パネルの Windows ファイアウォール**アプレットです。</span><span class="sxs-lookup"><span data-stu-id="0d792-140">This opens the **Windows Firewall Control Panel** applet.</span></span>  
  
2. <span data-ttu-id="0d792-141">Windows 7 または Windows Server 2008 R2 の場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d792-141">On Windows 7 or Windows Server 2008 R2, follow these steps.</span></span>  
  
    1. <span data-ttu-id="0d792-142">クリックして**詳細設定**で Windows ファイアウォール ウィンドウの左の列。</span><span class="sxs-lookup"><span data-stu-id="0d792-142">Click **Advanced settings** in the left column of the Windows Firewall window.</span></span>  
  
    2. <span data-ttu-id="0d792-143">クリックして**受信の規則**左の列にします。</span><span class="sxs-lookup"><span data-stu-id="0d792-143">Click **Inbound Rules** in the left column.</span></span>  
  
    3. <span data-ttu-id="0d792-144">クリックして**新しいルール**右側の列にします。</span><span class="sxs-lookup"><span data-stu-id="0d792-144">Click **New Rules** in the right column.</span></span>  
  
    4. <span data-ttu-id="0d792-145">選択**ポート** をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-145">Select **Port** and click **next**.</span></span>  
  
    5. <span data-ttu-id="0d792-146">選択**TCP**入力`8000, 8001, 8002, 8003, 9000, 80, 443`で、**特定のローカル ポート**フィールド。</span><span class="sxs-lookup"><span data-stu-id="0d792-146">Select **TCP** and enter `8000, 8001, 8002, 8003, 9000, 80, 443` in the **Specific local ports** field.</span></span>  
  
    6. <span data-ttu-id="0d792-147">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d792-147">Click **Next**.</span></span>  
  
    7. <span data-ttu-id="0d792-148">選択**接続を許可する**、 をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-148">Select **Allow the connection**, and click **Next** .</span></span>  
  
    8. <span data-ttu-id="0d792-149">選択**ドメイン**と**プライベート**、 をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-149">Select **Domain** and **Private**, and click **Next**.</span></span>  
  
    9. <span data-ttu-id="0d792-150">この規則の名前`WCF-WF 4.0 Samples`、 をクリック**完了**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-150">Name this rule `WCF-WF 4.0 Samples`, and click **Finish**.</span></span>  
  
    10. <span data-ttu-id="0d792-151">クリックして**送信の規則**手順 c ~ h を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0d792-151">Click **Outbound Rules** and repeat steps c to h.</span></span>  
  
3. <span data-ttu-id="0d792-152">[!INCLUDE[wv](../../../../includes/wv-md.md)] または [!INCLUDE[lserver](../../../../includes/lserver-md.md)] の場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d792-152">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)], follow these steps.</span></span>  
  
    1. <span data-ttu-id="0d792-153">クリックして**Windows ファイアウォールによるプログラムの許可**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-153">Click **Allow a program through Windows Firewall**.</span></span>  
  
    2. <span data-ttu-id="0d792-154">**例外**] タブで [**ポートの追加**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-154">On the **Exceptions** tab, click **Add Port**.</span></span>  
  
    3. <span data-ttu-id="0d792-155">名前を入力し、ポート番号 8000 を入力を選択、 **TCP**オプション。</span><span class="sxs-lookup"><span data-stu-id="0d792-155">Enter a name, enter 8000 as the port number, and select the **TCP** option.</span></span>  
  
    4. <span data-ttu-id="0d792-156">をクリックして、**スコープの変更**ボタンを選択、**マイ ネットワーク**(サブネット) のみのオプションをクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0d792-156">Click the **Change Scope** button, select the **My Network** (subnet) only option, and click **OK**.</span></span>  
  
    5. <span data-ttu-id="0d792-157">手順 b ～ d を繰り返して、ポート 8001、8002、8003、9000、80、および 443 を設定します。</span><span class="sxs-lookup"><span data-stu-id="0d792-157">Repeat steps b to d for ports 8001, 8002, 8003, 9000, 80, and 443.</span></span>  
  
4. <span data-ttu-id="0d792-158">クリックして**OK**ファイアウォール アプレットを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0d792-158">Click **OK** to close the firewall applet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d792-159">サンプルの実行が終わったら、ファイアウォールのすべての例外を削除します。</span><span class="sxs-lookup"><span data-stu-id="0d792-159">Remove any firewall exceptions when you are finished working with the samples.</span></span> <span data-ttu-id="0d792-160">これを行うには、開く、**コントロール パネルの Windows ファイアウォール**アプレットのすべてのプログラムを削除するか、前の手順で追加されたエントリのポートします。</span><span class="sxs-lookup"><span data-stu-id="0d792-160">To do so, open the **Windows Firewall Control Panel** applet and remove any programs or port entries that were added by the previous procedures.</span></span>
