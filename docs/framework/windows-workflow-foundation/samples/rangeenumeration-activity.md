---
title: RangeEnumeration アクティビティ
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: c9cf522227620422b414adc26cbc0bf338bf57d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556293"
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="30af4-102">RangeEnumeration アクティビティ</span><span class="sxs-lookup"><span data-stu-id="30af4-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="30af4-103">このサンプルでは、数値のコレクションを反復処理するカスタム アクティビティを作成する方法を示します。次の表で、このサンプルに含まれるメイン ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="30af4-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="30af4-104">ファイル名</span><span class="sxs-lookup"><span data-stu-id="30af4-104">File name</span></span>|<span data-ttu-id="30af4-105">説明</span><span class="sxs-lookup"><span data-stu-id="30af4-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30af4-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="30af4-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="30af4-107">`RangeEnumeration` クラスをオーバーライドし、一連の数値をループする <xref:System.Activities.NativeActivity> というカスタム アクティビティを定義します。</span><span class="sxs-lookup"><span data-stu-id="30af4-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="30af4-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="30af4-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="30af4-109">`RangeEnumeration` アクティビティを使用して数値のコレクションを反復処理するクライアント アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="30af4-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="30af4-110">次の表で、`RangeEnumeration` アクティビティのプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="30af4-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="30af4-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="30af4-111">Property</span></span>|<span data-ttu-id="30af4-112">説明</span><span class="sxs-lookup"><span data-stu-id="30af4-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="30af4-113">[開始]</span><span class="sxs-lookup"><span data-stu-id="30af4-113">Start</span></span>|<span data-ttu-id="30af4-114">ループの開始位置を示す整数。</span><span class="sxs-lookup"><span data-stu-id="30af4-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="30af4-115">Stop</span><span class="sxs-lookup"><span data-stu-id="30af4-115">Stop</span></span>|<span data-ttu-id="30af4-116">ループの停止位置を示す整数。</span><span class="sxs-lookup"><span data-stu-id="30af4-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="30af4-117">手順</span><span class="sxs-lookup"><span data-stu-id="30af4-117">Step</span></span>|<span data-ttu-id="30af4-118">各反復処理の反復回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="30af4-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="30af4-119">Body</span><span class="sxs-lookup"><span data-stu-id="30af4-119">Body</span></span>|<span data-ttu-id="30af4-120">各反復処理中に実行するコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="30af4-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="30af4-121">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="30af4-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="30af4-122">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、RangeEnumeration.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="30af4-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="30af4-123">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="30af4-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="30af4-124">ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="30af4-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30af4-125">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="30af4-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="30af4-126">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="30af4-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="30af4-127">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="30af4-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="30af4-128">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="30af4-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`