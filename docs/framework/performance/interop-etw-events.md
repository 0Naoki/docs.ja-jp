---
title: 相互運用 ETW イベント
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09b2848619256a255cc27f0268d46e5e6db8cbe4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083609"
---
# <a name="interop-etw-events"></a><span data-ttu-id="04b28-102">相互運用 ETW イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="04b28-103">相互運用イベントは、Microsoft intermediate language (MSIL) のスタブ生成とキャッシュに関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="04b28-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="04b28-104">このカテゴリは、次のイベントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="04b28-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="04b28-105">ILStubGenerated イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="04b28-106">ILStubCacheHit イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="04b28-107">ILStubGenerated イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="04b28-108">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="04b28-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="04b28-109">(詳細については、「 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="04b28-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="04b28-110">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="04b28-110">Keyword for raising the event</span></span>|<span data-ttu-id="04b28-111">レベル</span><span class="sxs-lookup"><span data-stu-id="04b28-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="04b28-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="04b28-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="04b28-113">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="04b28-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="04b28-114">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="04b28-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="04b28-115">イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-115">Event</span></span>|<span data-ttu-id="04b28-116">イベント ID</span><span class="sxs-lookup"><span data-stu-id="04b28-116">Event ID</span></span>|<span data-ttu-id="04b28-117">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="04b28-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="04b28-118">88</span><span class="sxs-lookup"><span data-stu-id="04b28-118">88</span></span>|<span data-ttu-id="04b28-119">MSIL スタブが生成された。</span><span class="sxs-lookup"><span data-stu-id="04b28-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="04b28-120">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="04b28-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="04b28-121">フィールド名</span><span class="sxs-lookup"><span data-stu-id="04b28-121">Field name</span></span>|<span data-ttu-id="04b28-122">データ型</span><span class="sxs-lookup"><span data-stu-id="04b28-122">Data type</span></span>|<span data-ttu-id="04b28-123">説明</span><span class="sxs-lookup"><span data-stu-id="04b28-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="04b28-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="04b28-124">ModuleID</span></span>|<span data-ttu-id="04b28-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="04b28-125">win:UInt16</span></span>|<span data-ttu-id="04b28-126">モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="04b28-126">The module identifier.</span></span>|  
|<span data-ttu-id="04b28-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="04b28-127">StubMethodID</span></span>|<span data-ttu-id="04b28-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="04b28-128">win:UInt64</span></span>|<span data-ttu-id="04b28-129">スタブのメソッド識別子。</span><span class="sxs-lookup"><span data-stu-id="04b28-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="04b28-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="04b28-130">StubFlags</span></span>|<span data-ttu-id="04b28-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="04b28-131">win:UInt64</span></span>|<span data-ttu-id="04b28-132">スタブのフラグ:</span><span class="sxs-lookup"><span data-stu-id="04b28-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="04b28-133">0x1 - 逆方向の相互運用。</span><span class="sxs-lookup"><span data-stu-id="04b28-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="04b28-134">0x2 - COM 相互運用。</span><span class="sxs-lookup"><span data-stu-id="04b28-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="04b28-135">0x4 - NGen.exe で生成されたスタブ。</span><span class="sxs-lookup"><span data-stu-id="04b28-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="04b28-136">0x8 - デリゲート。</span><span class="sxs-lookup"><span data-stu-id="04b28-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="04b28-137">0x10 - 可変個引数。</span><span class="sxs-lookup"><span data-stu-id="04b28-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="04b28-138">0x20 - アンマネージ呼び出し先。</span><span class="sxs-lookup"><span data-stu-id="04b28-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="04b28-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="04b28-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="04b28-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="04b28-140">win:UInt32</span></span>|<span data-ttu-id="04b28-141">マネージド相互運用メソッドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="04b28-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="04b28-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="04b28-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-143">win:UnicodeString</span></span>|<span data-ttu-id="04b28-144">マネージド相互運用メソッドの名前空間。</span><span class="sxs-lookup"><span data-stu-id="04b28-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="04b28-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="04b28-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-146">win:UnicodeString</span></span>|<span data-ttu-id="04b28-147">マネージド相互運用メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="04b28-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="04b28-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="04b28-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-149">win:UnicodeString</span></span>|<span data-ttu-id="04b28-150">マネージド相互運用メソッドのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="04b28-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="04b28-151">NativeMethodSignature</span></span>|<span data-ttu-id="04b28-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-152">win:UnicodeString</span></span>|<span data-ttu-id="04b28-153">ネイティブ メソッド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="04b28-153">The native method signature.</span></span>|  
|<span data-ttu-id="04b28-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="04b28-154">StubMethodSignature</span></span>|<span data-ttu-id="04b28-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-155">win:UnicodeString</span></span>|<span data-ttu-id="04b28-156">スタブ メソッド シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="04b28-156">The stub method signature.</span></span>|  
|<span data-ttu-id="04b28-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="04b28-157">StubMethodILCode</span></span>|<span data-ttu-id="04b28-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-158">win:UnicodeString</span></span>|<span data-ttu-id="04b28-159">スタブ メソッドの MSIL コード。</span><span class="sxs-lookup"><span data-stu-id="04b28-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="04b28-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="04b28-160">ClrInstanceID</span></span>|<span data-ttu-id="04b28-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="04b28-161">win:UInt16</span></span>|<span data-ttu-id="04b28-162">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="04b28-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="04b28-163">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="04b28-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="04b28-164">ILStubCacheHit イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="04b28-165">次の表に、キーワードとレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="04b28-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="04b28-166">イベントを発生させるキーワード</span><span class="sxs-lookup"><span data-stu-id="04b28-166">Keyword for raising the event</span></span>|<span data-ttu-id="04b28-167">レベル</span><span class="sxs-lookup"><span data-stu-id="04b28-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="04b28-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="04b28-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="04b28-169">情報通知 (4)</span><span class="sxs-lookup"><span data-stu-id="04b28-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="04b28-170">次の表に、イベント情報を示します。</span><span class="sxs-lookup"><span data-stu-id="04b28-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="04b28-171">イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-171">Event</span></span>|<span data-ttu-id="04b28-172">イベント ID</span><span class="sxs-lookup"><span data-stu-id="04b28-172">Event ID</span></span>|<span data-ttu-id="04b28-173">いつ発生するか</span><span class="sxs-lookup"><span data-stu-id="04b28-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="04b28-174">89</span><span class="sxs-lookup"><span data-stu-id="04b28-174">89</span></span>|<span data-ttu-id="04b28-175">MSIL のキャッシュにアクセスがあった。</span><span class="sxs-lookup"><span data-stu-id="04b28-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="04b28-176">次の表に、イベント データを示します。</span><span class="sxs-lookup"><span data-stu-id="04b28-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="04b28-177">フィールド名</span><span class="sxs-lookup"><span data-stu-id="04b28-177">Field name</span></span>|<span data-ttu-id="04b28-178">データ型</span><span class="sxs-lookup"><span data-stu-id="04b28-178">Data type</span></span>|<span data-ttu-id="04b28-179">説明</span><span class="sxs-lookup"><span data-stu-id="04b28-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="04b28-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="04b28-180">ModuleID</span></span>|<span data-ttu-id="04b28-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="04b28-181">win:UInt16</span></span>|<span data-ttu-id="04b28-182">モジュールの識別子。</span><span class="sxs-lookup"><span data-stu-id="04b28-182">The module identifier.</span></span>|  
|<span data-ttu-id="04b28-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="04b28-183">StubMethodID</span></span>|<span data-ttu-id="04b28-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="04b28-184">win:UInt64</span></span>|<span data-ttu-id="04b28-185">スタブのメソッド識別子。</span><span class="sxs-lookup"><span data-stu-id="04b28-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="04b28-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="04b28-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="04b28-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="04b28-187">win:UInt32</span></span>|<span data-ttu-id="04b28-188">マネージド相互運用メソッドのトークンです。</span><span class="sxs-lookup"><span data-stu-id="04b28-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="04b28-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="04b28-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-190">win:UnicodeString</span></span>|<span data-ttu-id="04b28-191">マネージド相互運用メソッドの名前空間。</span><span class="sxs-lookup"><span data-stu-id="04b28-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="04b28-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="04b28-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-193">win:UnicodeString</span></span>|<span data-ttu-id="04b28-194">マネージド相互運用メソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="04b28-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="04b28-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="04b28-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="04b28-196">win:UnicodeString</span></span>|<span data-ttu-id="04b28-197">マネージド相互運用メソッドのシグネチャ。</span><span class="sxs-lookup"><span data-stu-id="04b28-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="04b28-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="04b28-198">ClrInstanceID</span></span>|<span data-ttu-id="04b28-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="04b28-199">win:UInt16</span></span>|<span data-ttu-id="04b28-200">CLR または CoreCLR のインスタンスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="04b28-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="04b28-201">ページのトップへ</span><span class="sxs-lookup"><span data-stu-id="04b28-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="04b28-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="04b28-202">See also</span></span>

- [<span data-ttu-id="04b28-203">CLR ETW イベント</span><span class="sxs-lookup"><span data-stu-id="04b28-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
