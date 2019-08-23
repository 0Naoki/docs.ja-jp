---
title: トレースおよびデバッグ設定のスキーマ
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
ms.openlocfilehash: 037d08b33e9aa6a64d236b36ebcf821b604b03df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927119"
---
# <a name="trace-and-debug-settings-schema"></a><span data-ttu-id="b79ab-102">トレースおよびデバッグ設定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="b79ab-102">Trace and Debug Settings Schema</span></span>
<span data-ttu-id="b79ab-103">トレースおよびデバッグの設定により、メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-103">Trace and debug settings specify trace listeners that collect, store, and route messages, and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="b79ab-104">次の表に、トレース設定とデバッグ設定の各要素の機能を示します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-104">The following table describes the function of each trace and debug settings element.</span></span>  
  
|<span data-ttu-id="b79ab-105">要素</span><span class="sxs-lookup"><span data-stu-id="b79ab-105">Element</span></span>|<span data-ttu-id="b79ab-106">説明</span><span class="sxs-lookup"><span data-stu-id="b79ab-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b79ab-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b79ab-107">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="b79ab-108">トレース ソースの `Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-108">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="b79ab-109">\<add></span><span class="sxs-lookup"><span data-stu-id="b79ab-109">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="b79ab-110">`Listeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-110">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="b79ab-111">\<add></span><span class="sxs-lookup"><span data-stu-id="b79ab-111">\<add></span></span>](add-element-for-sharedlisteners.md)|<span data-ttu-id="b79ab-112">`sharedListeners` コレクションにリスナーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-112">Adds a listener to the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="b79ab-113">\<add></span><span class="sxs-lookup"><span data-stu-id="b79ab-113">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="b79ab-114">トレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-114">Specifies the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="b79ab-115">\<assert></span><span class="sxs-lookup"><span data-stu-id="b79ab-115">\<assert></span></span>](assert-element.md)|<span data-ttu-id="b79ab-116"><xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> メソッドの呼び出し時にメッセージ ボックスを表示するかどうかを指定し、メッセージの書き込み先のファイルの名前も指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-116">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[<span data-ttu-id="b79ab-117">\<clear></span><span class="sxs-lookup"><span data-stu-id="b79ab-117">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="b79ab-118">トレース ソースの `Listeners` コレクションを消去します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-118">Clears the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="b79ab-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="b79ab-119">\<clear></span></span>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="b79ab-120">トレースの `Listeners` コレクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="b79ab-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="b79ab-121">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="b79ab-122">トレース ソースの `Listeners` コレクション内のリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-122">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="b79ab-123">\<filter></span><span class="sxs-lookup"><span data-stu-id="b79ab-123">\<filter></span></span>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="b79ab-124">トレースの `Listeners` コレクションのリスナーにフィルターに追加します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-124">Adds a filter to a listener in the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="b79ab-125">\<filter></span><span class="sxs-lookup"><span data-stu-id="b79ab-125">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="b79ab-126">`sharedListeners` コレクションのリスナーにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-126">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
|[<span data-ttu-id="b79ab-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="b79ab-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="b79ab-128">トレース ソースの `Listeners` コレクションにリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-128">Specifies listeners for the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="b79ab-129">\<listeners></span><span class="sxs-lookup"><span data-stu-id="b79ab-129">\<listeners></span></span>](listeners-element-for-trace.md)|<span data-ttu-id="b79ab-130">トレースの `Listeners` コレクションにリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-130">Specifies listeners for the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="b79ab-131">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="b79ab-131">\<performanceCounters></span></span>](performancecounters-element.md)|<span data-ttu-id="b79ab-132">パフォーマンス カウンターが共有するグローバル メモリのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-132">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[<span data-ttu-id="b79ab-133">\<remove></span><span class="sxs-lookup"><span data-stu-id="b79ab-133">\<remove></span></span>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="b79ab-134">トレースの `Listeners` コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-134">Removes a listener from the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="b79ab-135">\<remove></span><span class="sxs-lookup"><span data-stu-id="b79ab-135">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="b79ab-136">トレース ソースの `Listeners` コレクションからリスナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-136">Removes a listener from the `Listeners` collection for a trace source.</span></span>|  
|[<span data-ttu-id="b79ab-137">\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="b79ab-137">\<sharedListeners></span></span>](sharedlisteners-element.md)|<span data-ttu-id="b79ab-138">任意の source 要素または trace 要素が参照できるリスナーを含みます。</span><span class="sxs-lookup"><span data-stu-id="b79ab-138">Contains listeners that any source or trace element can reference.</span></span>|  
|[<span data-ttu-id="b79ab-139">\<sources></span><span class="sxs-lookup"><span data-stu-id="b79ab-139">\<sources></span></span>](sources-element.md)|<span data-ttu-id="b79ab-140">トレース メッセージを開始するトレース ソースを保持します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-140">Contains trace sources that initiate tracing messages.</span></span>|  
|[<span data-ttu-id="b79ab-141">\<source></span><span class="sxs-lookup"><span data-stu-id="b79ab-141">\<source></span></span>](source-element.md)|<span data-ttu-id="b79ab-142">トレース メッセージを開始するトレース ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-142">Specifies a trace source that initiates tracing messages.</span></span>|  
|[<span data-ttu-id="b79ab-143">\<switches></span><span class="sxs-lookup"><span data-stu-id="b79ab-143">\<switches></span></span>](switches-element.md)|<span data-ttu-id="b79ab-144">トレース スイッチと、トレース スイッチを設定するレベルを保持します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-144">Contains trace switches and the level where the trace switches are set.</span></span>|  
|[<span data-ttu-id="b79ab-145">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="b79ab-145">\<system.diagnostics></span></span>](system-diagnostics-element.md)|<span data-ttu-id="b79ab-146">メッセージを収集、格納、およびルーティングするトレース リスナーとトレース スイッチを設定するレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-146">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|[<span data-ttu-id="b79ab-147">\<trace></span><span class="sxs-lookup"><span data-stu-id="b79ab-147">\<trace></span></span>](trace-element.md)|<span data-ttu-id="b79ab-148">トレース メッセージを収集、格納、およびルーティングするリスナーを保持します。</span><span class="sxs-lookup"><span data-stu-id="b79ab-148">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b79ab-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="b79ab-149">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="b79ab-150">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b79ab-150">Configuration File Schema</span></span>](../index.md)
