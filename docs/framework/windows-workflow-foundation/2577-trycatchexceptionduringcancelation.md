---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: c272dd91249dfc90e6f4c38a7339919a5a6446e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755624"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="77e7b-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="77e7b-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="77e7b-103">プロパティ</span><span class="sxs-lookup"><span data-stu-id="77e7b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77e7b-104">ID</span><span class="sxs-lookup"><span data-stu-id="77e7b-104">ID</span></span>|<span data-ttu-id="77e7b-105">2577</span><span class="sxs-lookup"><span data-stu-id="77e7b-105">2577</span></span>|  
|<span data-ttu-id="77e7b-106">キーワード</span><span class="sxs-lookup"><span data-stu-id="77e7b-106">Keywords</span></span>|<span data-ttu-id="77e7b-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="77e7b-107">WFActivities</span></span>|  
|<span data-ttu-id="77e7b-108">レベル</span><span class="sxs-lookup"><span data-stu-id="77e7b-108">Level</span></span>|<span data-ttu-id="77e7b-109">警告</span><span class="sxs-lookup"><span data-stu-id="77e7b-109">Warning</span></span>|  
|<span data-ttu-id="77e7b-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="77e7b-110">Channel</span></span>|<span data-ttu-id="77e7b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="77e7b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="77e7b-112">説明</span><span class="sxs-lookup"><span data-stu-id="77e7b-112">Description</span></span>  
 <span data-ttu-id="77e7b-113">TryCatch アクティビティの子アクティビティが取り消し中に例外をスローしたことを示します。</span><span class="sxs-lookup"><span data-stu-id="77e7b-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="77e7b-114">メッセージ</span><span class="sxs-lookup"><span data-stu-id="77e7b-114">Message</span></span>  
 <span data-ttu-id="77e7b-115">TryCatch アクティビティ '%1' の子アクティビティは取り消し中に例外をスローしました。</span><span class="sxs-lookup"><span data-stu-id="77e7b-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="77e7b-116">説明</span><span class="sxs-lookup"><span data-stu-id="77e7b-116">Details</span></span>  
  
|<span data-ttu-id="77e7b-117">データ項目名</span><span class="sxs-lookup"><span data-stu-id="77e7b-117">Data Item Name</span></span>|<span data-ttu-id="77e7b-118">データ項目の型</span><span class="sxs-lookup"><span data-stu-id="77e7b-118">Data Item Type</span></span>|<span data-ttu-id="77e7b-119">説明</span><span class="sxs-lookup"><span data-stu-id="77e7b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="77e7b-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="77e7b-120">DisplayName</span></span>|<span data-ttu-id="77e7b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="77e7b-121">xs:string</span></span>|<span data-ttu-id="77e7b-122">アクティビティの表示名。</span><span class="sxs-lookup"><span data-stu-id="77e7b-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="77e7b-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="77e7b-123">AppDomain</span></span>|<span data-ttu-id="77e7b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="77e7b-124">xs:string</span></span>|<span data-ttu-id="77e7b-125">AppDomain.CurrentDomain.FriendlyName で返される文字列。</span><span class="sxs-lookup"><span data-stu-id="77e7b-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
