---
title: '方法: 日付と時刻の演算でタイム ゾーンを使用する'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 053ca2d10deadf58d5bb8b4628fb5dee815d82c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026498"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="a9158-102">方法: 日付と時刻の演算でタイム ゾーンを使用する</span><span class="sxs-lookup"><span data-stu-id="a9158-102">How to: Use time zones in date and time arithmetic</span></span>

<span data-ttu-id="a9158-103">通常とを実行して日付時刻の算術演算を使用して<xref:System.DateTime>または<xref:System.DateTimeOffset>結果の値は、タイム ゾーン調整規則が反映されません。</span><span class="sxs-lookup"><span data-stu-id="a9158-103">Ordinarily, when you perform date and time arithmetic using <xref:System.DateTime> or <xref:System.DateTimeOffset> values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="a9158-104">日付と時刻の値のタイム ゾーンが明確に識別できる場合でもこれが true (場合など、<xref:System.DateTime.Kind%2A>プロパティに設定されて<xref:System.DateTimeKind.Local>)。</span><span class="sxs-lookup"><span data-stu-id="a9158-104">This is true even when the time zone of the date and time value is clearly identifiable (for example, when the <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind.Local>).</span></span> <span data-ttu-id="a9158-105">このトピックでは、特定のタイム ゾーンに属している日付と時刻の値に対する算術演算を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9158-105">This topic shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="a9158-106">算術演算の結果には、タイム ゾーンの調整規則が反映されます。</span><span class="sxs-lookup"><span data-stu-id="a9158-106">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="a9158-107">日付と時刻の演算に調整規則を適用するには</span><span class="sxs-lookup"><span data-stu-id="a9158-107">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="a9158-108">なんらかの方法を実装して、日付と時刻の値と、その値が属するタイム ゾーンを密接に結び付けます。</span><span class="sxs-lookup"><span data-stu-id="a9158-108">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="a9158-109">たとえば、日付と時刻の値とそのタイム ゾーンの両方を含む構造体を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a9158-109">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="a9158-110">次の例では、このアプローチを使用してリンクする、<xref:System.DateTime>とそのタイム ゾーンの値。</span><span class="sxs-lookup"><span data-stu-id="a9158-110">The following example uses this approach to link a <xref:System.DateTime> value with its time zone.</span></span>

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. <span data-ttu-id="a9158-111">いずれかを呼び出すことによって、時刻を世界協定時刻 (UTC) を変換、<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>メソッドまたは<xref:System.TimeZoneInfo.ConvertTime%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="a9158-111">Convert a time to Coordinated Universal Time (UTC) by calling either the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> method or the <xref:System.TimeZoneInfo.ConvertTime%2A> method.</span></span>

3. <span data-ttu-id="a9158-112">UTC 時刻で算術演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9158-112">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="a9158-113">呼び出すことによって時間を UTC から元の時刻のタイム ゾーンに変換、<xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="a9158-113">Convert the time from UTC to the original time's associated time zone by calling the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="a9158-114">例</span><span class="sxs-lookup"><span data-stu-id="a9158-114">Example</span></span>

<span data-ttu-id="a9158-115">次の例では、中部標準時の 2008 年 3 月 9 日午前 1 時 30 分に、2 時間 30 分を</span><span class="sxs-lookup"><span data-stu-id="a9158-115">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="a9158-116">加えます。</span><span class="sxs-lookup"><span data-stu-id="a9158-116">Central Standard Time.</span></span> <span data-ttu-id="a9158-117">夏時間へのタイム ゾーンの切り替えは、30 分後の 2008 年 3 月 9 日午前 2 時に</span><span class="sxs-lookup"><span data-stu-id="a9158-117">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="a9158-118">発生します。</span><span class="sxs-lookup"><span data-stu-id="a9158-118">on March 9, 2008.</span></span> <span data-ttu-id="a9158-119">この例は前に示した 4 つの手順に従うため、結果は正しい時刻である 2008 年 3 月 9 日午前 5 時に</span><span class="sxs-lookup"><span data-stu-id="a9158-119">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="a9158-120">前のコードと似ています。</span><span class="sxs-lookup"><span data-stu-id="a9158-120">on March 9, 2008.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<span data-ttu-id="a9158-121">両方<xref:System.DateTime>と<xref:System.DateTimeOffset>が属している任意のタイム ゾーンからの値は関連付けを解除します。</span><span class="sxs-lookup"><span data-stu-id="a9158-121">Both <xref:System.DateTime> and <xref:System.DateTimeOffset> values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="a9158-122">タイム ゾーンの調整規則が自動的に適用されるような方法で日付と時刻の演算を実行するには、日付と時刻の値の属するタイム ゾーンがすぐに識別できる状態でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a9158-122">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="a9158-123">つまり、日時と関連付けられているタイム ゾーンを密に結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9158-123">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="a9158-124">これは、次のようないくつかの方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a9158-124">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="a9158-125">アプリケーションで使用されるすべての時刻が、特定のタイム ゾーンに属するものと仮定します。</span><span class="sxs-lookup"><span data-stu-id="a9158-125">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="a9158-126">この方法は、適切な場合もありますが、柔軟性が限られ、移植性が制限される可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="a9158-126">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="a9158-127">日時と関連付けられているタイム ゾーンを型のフィールドとして組み込むことで、両者を密に結合する型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a9158-127">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="a9158-128">コード例ではこの方法を使用して、日時とタイム ゾーンを 2 つのメンバー フィールドに格納する構造体を定義しています。</span><span class="sxs-lookup"><span data-stu-id="a9158-128">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

<span data-ttu-id="a9158-129">例では、算術演算を実行する方法を示しています。<xref:System.DateTime>結果にタイム ゾーン調整規則が適用されるように値。</span><span class="sxs-lookup"><span data-stu-id="a9158-129">The example illustrates how to perform arithmetic operations on <xref:System.DateTime> values so that time zone adjustment rules are applied to the result.</span></span> <span data-ttu-id="a9158-130">ただし、<xref:System.DateTimeOffset>値は同じくらい簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9158-130">However, <xref:System.DateTimeOffset> values can be used just as easily.</span></span> <span data-ttu-id="a9158-131">次の例を示す方法で元の例では、コードが使用する可能性があります<xref:System.DateTimeOffset>の代わりに<xref:System.DateTime>値。</span><span class="sxs-lookup"><span data-stu-id="a9158-131">The following example illustrates how the code in the original example might be adapted to use <xref:System.DateTimeOffset> instead of <xref:System.DateTime> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

<span data-ttu-id="a9158-132">この加算処理は単に実行する場合、<xref:System.DateTimeOffset>最初 UTC に変換すること、結果、適切な時点の反映が、そのオフセットは反映されませんする指定されたタイム ゾーンの時点のなしの値します。</span><span class="sxs-lookup"><span data-stu-id="a9158-132">Note that if this addition is simply performed on the <xref:System.DateTimeOffset> value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="a9158-133">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a9158-133">Compiling the code</span></span>

<span data-ttu-id="a9158-134">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9158-134">This example requires:</span></span>

* <span data-ttu-id="a9158-135">System.Core.dll への参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="a9158-135">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="a9158-136"><xref:System>と共に名前空間をインポートする、`using`ステートメント (c# コードで必要)。</span><span class="sxs-lookup"><span data-stu-id="a9158-136">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9158-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9158-137">See also</span></span>

- [<span data-ttu-id="a9158-138">日付、時刻、およびタイム ゾーン</span><span class="sxs-lookup"><span data-stu-id="a9158-138">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="a9158-139">日付と時刻を使用した算術演算の実行</span><span class="sxs-lookup"><span data-stu-id="a9158-139">Performing arithmetic operations with dates and times</span></span>](../../../docs/standard/datetime/performing-arithmetic-operations.md)
