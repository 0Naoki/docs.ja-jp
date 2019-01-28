---
title: コールバック メソッドとしてのデリゲートのマーシャ リング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, Callback sample
- marshaling, Callback sample
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2aa999199ddf11a1a2db57b6f7b1dd198b4ea61d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529846"
---
# <a name="marshaling-a-delegate-as-a-callback-method"></a><span data-ttu-id="bd9f7-102">コールバック メソッドとしてのデリゲートのマーシャ リング</span><span class="sxs-lookup"><span data-stu-id="bd9f7-102">Marshaling a Delegate as a Callback Method</span></span>
<span data-ttu-id="bd9f7-103">このサンプルでは、関数ポインターを要求するアンマネージ関数にデリゲートを渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-103">This sample demonstrates how to pass delegates to an unmanaged function expecting function pointers.</span></span> <span data-ttu-id="bd9f7-104">デリゲートは、メソッドへの参照を保持できるクラスであり、タイプ セーフな関数ポインターまたはコールバック関数と同等のものです。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-104">A delegate is a class that can hold a reference to a method and is equivalent to a type-safe function pointer or a callback function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd9f7-105">呼び出しの中でデリゲートを使うと、共通言語ランタイムがデリゲートをその呼び出しの期間中ガベージ コレクションから保護します。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-105">When you use a delegate inside a call, the common language runtime protects the delegate from being garbage collected for the duration of that call.</span></span> <span data-ttu-id="bd9f7-106">ただし、アンマネージ関数が呼び出し完了後に使うためにデリゲートを保存する場合は、アンマネージ関数がデリゲートを終了するまで手動でガベージ コレクションを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-106">However, if the unmanaged function stores the delegate to use after the call completes, you must manually prevent garbage collection until the unmanaged function finishes with the delegate.</span></span> <span data-ttu-id="bd9f7-107">詳細については、「[HandleRef Sample](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100))」(HandleRef のサンプル) および「[GCHandle Sample](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100))」(GCHandle のサンプル) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-107">For more information, see the [HandleRef Sample](https://msdn.microsoft.com/library/ab23b04e-1d53-4ec7-b27a-e892d9298959(v=vs.100)) and [GCHandle Sample](https://msdn.microsoft.com/library/6acce798-0385-4ded-a790-77da842c113f(v=vs.100)).</span></span>  
  
 <span data-ttu-id="bd9f7-108">Callback のサンプルで使用するアンマネージ関数とその元の関数宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-108">The Callback sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="bd9f7-109">PinvokeLib.dll からエクスポートされる **TestCallBack**。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-109">**TestCallBack** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   <span data-ttu-id="bd9f7-110">PinvokeLib.dll からエクスポートされる **TestCallBack2**。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-110">**TestCallBack2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 <span data-ttu-id="bd9f7-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) はカスタム アンマネージ ライブラリであり、上で示した関数の実装を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-111">[PinvokeLib.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as6wyhwt(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed functions.</span></span>  
  
 <span data-ttu-id="bd9f7-112">このサンプルでは、`LibWrap` クラスには、`TestCallBack` メソッドと `TestCallBack2` メソッドのマネージド プロトタイプが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-112">In this sample, the `LibWrap` class contains managed prototypes for the `TestCallBack` and `TestCallBack2` methods.</span></span> <span data-ttu-id="bd9f7-113">どちらのメソッドも、コールバック関数にパラメーターとしてデリゲートを渡します。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-113">Both methods pass a delegate to a callback function as a parameter.</span></span> <span data-ttu-id="bd9f7-114">デリゲートのシグネチャは、それが参照しているメソッドのシグネチャと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-114">The signature of the delegate must match the signature of the method it references.</span></span> <span data-ttu-id="bd9f7-115">たとえば、`FPtr` および `FPtr2` デリゲートのシグネチャは、`DoSomething` および `DoSomething2` メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="bd9f7-115">For example, the `FPtr` and `FPtr2` delegates have signatures that are identical to the `DoSomething` and `DoSomething2` methods.</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="bd9f7-116">プロトタイプの宣言</span><span class="sxs-lookup"><span data-stu-id="bd9f7-116">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## <a name="calling-functions"></a><span data-ttu-id="bd9f7-117">関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="bd9f7-117">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## <a name="see-also"></a><span data-ttu-id="bd9f7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd9f7-118">See also</span></span>
- <span data-ttu-id="bd9f7-119">[各種のマーシャリングのサンプル](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bd9f7-119">[Miscellaneous Marshaling Samples](https://msdn.microsoft.com/library/a915c948-54e9-4d0f-a525-95a77fd8ed70(v=vs.100))</span></span>
- <span data-ttu-id="bd9f7-120">[プラットフォーム呼び出しのデータ型](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bd9f7-120">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>
- [<span data-ttu-id="bd9f7-121">マネージド コードでのプロトタイプの作成</span><span class="sxs-lookup"><span data-stu-id="bd9f7-121">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
