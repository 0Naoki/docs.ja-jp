---
title: jitCompilationStart MDA
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 80473e01581a372c193c4b816a37166b73d57824
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854150"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="42133-102">jitCompilationStart MDA</span><span class="sxs-lookup"><span data-stu-id="42133-102">jitCompilationStart MDA</span></span>
<span data-ttu-id="42133-103">`jitCompilationStart` マネージド デバッグ アシスタント (MDA: Managed Debugging Assistant) が起動すると、Just-In-Time (JIT) コンパイラが関数のコンパイルを開始した時刻が報告されます。</span><span class="sxs-lookup"><span data-stu-id="42133-103">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="42133-104">症状</span><span class="sxs-lookup"><span data-stu-id="42133-104">Symptoms</span></span>  
 <span data-ttu-id="42133-105">mscorjit.dll がプロセスに読み込まれるため、既にネイティブの画像形式になっているプログラムで、ワーキング セット サイズが増えます。</span><span class="sxs-lookup"><span data-stu-id="42133-105">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="42133-106">原因</span><span class="sxs-lookup"><span data-stu-id="42133-106">Cause</span></span>  
 <span data-ttu-id="42133-107">プログラムが依存するアセンブリの一部がネイティブ形式に生成されていないか、生成されていても正しく登録されていません。</span><span class="sxs-lookup"><span data-stu-id="42133-107">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="42133-108">解決策</span><span class="sxs-lookup"><span data-stu-id="42133-108">Resolution</span></span>  
 <span data-ttu-id="42133-109">この MDA を有効にすると、JIT コンパイルされている関数を判断できます。</span><span class="sxs-lookup"><span data-stu-id="42133-109">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="42133-110">関数が含まれるアセンブリがネイティブ形式に生成され、正しく登録されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="42133-110">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="42133-111">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="42133-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="42133-112">この MDA は、メソッドが JIT コンパイルされる前にメッセージをログに記録します。そのため、この MDA を有効にすると、パフォーマンスに大きな影響が出ます。</span><span class="sxs-lookup"><span data-stu-id="42133-112">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="42133-113">メソッドがインラインの場合、この MDA は別個のメッセージを生成しません。</span><span class="sxs-lookup"><span data-stu-id="42133-113">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="42133-114">Output</span><span class="sxs-lookup"><span data-stu-id="42133-114">Output</span></span>  
 <span data-ttu-id="42133-115">次のコード サンプルでは、サンプル出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="42133-115">The following code sample shows sample output.</span></span> <span data-ttu-id="42133-116">ここでは、アセンブリ Test で、クラス "ns2.CO" のメソッド "m" が JIT コンパイルされたことを出力で確認できます。</span><span class="sxs-lookup"><span data-stu-id="42133-116">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```output
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="42133-117">構成</span><span class="sxs-lookup"><span data-stu-id="42133-117">Configuration</span></span>  
 <span data-ttu-id="42133-118">次の構成ファイルでは、最初に JIT コンパイルされたときに報告されるメソッドを絞り込むためのさまざまなフィルターを確認できます。</span><span class="sxs-lookup"><span data-stu-id="42133-118">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="42133-119">Name 属性の値をに\*設定することによって、すべてのメソッドを報告するように指定できます。</span><span class="sxs-lookup"><span data-stu-id="42133-119">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="42133-120">例</span><span class="sxs-lookup"><span data-stu-id="42133-120">Example</span></span>  
 <span data-ttu-id="42133-121">次のコード サンプルは、先の構成ファイルとの併用を意図しています。</span><span class="sxs-lookup"><span data-stu-id="42133-121">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="42133-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="42133-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="42133-123">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="42133-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="42133-124">相互運用マーシャリング</span><span class="sxs-lookup"><span data-stu-id="42133-124">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
