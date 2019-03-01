---
title: SyncLock ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 3a12c3ac7250ee2904d571406d5008d451c9dc35
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979815"
---
# <a name="synclock-statement"></a><span data-ttu-id="a3ffc-102">SyncLock ステートメント</span><span class="sxs-lookup"><span data-stu-id="a3ffc-102">SyncLock Statement</span></span>
<span data-ttu-id="a3ffc-103">ブロックを実行する前にステートメント ブロックの排他ロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-103">Acquires an exclusive lock for a statement block before executing the block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3ffc-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3ffc-104">Syntax</span></span>  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a><span data-ttu-id="a3ffc-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="a3ffc-105">Parts</span></span>  
 `lockobject`  
 <span data-ttu-id="a3ffc-106">必須。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-106">Required.</span></span> <span data-ttu-id="a3ffc-107">オブジェクト参照に評価される式。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-107">Expression that evaluates to an object reference.</span></span>  
  
 `block`  
 <span data-ttu-id="a3ffc-108">任意。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-108">Optional.</span></span> <span data-ttu-id="a3ffc-109">ロックが取得されるときに実行されるステートメントのブロックです。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-109">Block of statements that are to execute when the lock is acquired.</span></span>  
  
 `End SyncLock`  
 <span data-ttu-id="a3ffc-110">終了、`SyncLock`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-110">Terminates a `SyncLock` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3ffc-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a3ffc-111">Remarks</span></span>  
 <span data-ttu-id="a3ffc-112">`SyncLock`ステートメントが複数のスレッドが同時にステートメント ブロックを実行しないことを保証します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-112">The `SyncLock` statement ensures that multiple threads do not execute the statement block at the same time.</span></span> <span data-ttu-id="a3ffc-113">`SyncLock` 各スレッドが実行している他のスレッドがなくなるまで、ブロックを入力するを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-113">`SyncLock` prevents each thread from entering the block until no other thread is executing it.</span></span>  
  
 <span data-ttu-id="a3ffc-114">最も一般的な用途`SyncLock`から複数のスレッドによって同時に更新されたデータを保護することです。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-114">The most common use of `SyncLock` is to protect data from being updated by more than one thread simultaneously.</span></span> <span data-ttu-id="a3ffc-115">場合は、データを操作するステートメントは、中断することがなく完了するまで移動する必要があります、配置内でそれらを`SyncLock`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-115">If the statements that manipulate the data must go to completion without interruption, put them inside a `SyncLock` block.</span></span>  
  
 <span data-ttu-id="a3ffc-116">排他ロックによって保護されているステートメント ブロックが呼び出される場合があります、*クリティカル セクション*します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-116">A statement block protected by an exclusive lock is sometimes called a *critical section*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a3ffc-117">ルール</span><span class="sxs-lookup"><span data-stu-id="a3ffc-117">Rules</span></span>  
  
-   <span data-ttu-id="a3ffc-118">分岐します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-118">Branching.</span></span> <span data-ttu-id="a3ffc-119">分岐することはできません、`SyncLock`ブロックの外側からブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-119">You cannot branch into a `SyncLock` block from outside the block.</span></span>  
  
-   <span data-ttu-id="a3ffc-120">オブジェクトの値をロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-120">Lock Object Value.</span></span> <span data-ttu-id="a3ffc-121">値`lockobject`することはできません`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-121">The value of `lockobject` cannot be `Nothing`.</span></span> <span data-ttu-id="a3ffc-122">使用する前に、ロック オブジェクトを作成する必要があります、`SyncLock`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-122">You must create the lock object before you use it in a `SyncLock` statement.</span></span>  
  
     <span data-ttu-id="a3ffc-123">値を変更することはできません`lockobject`の実行中に、`SyncLock`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-123">You cannot change the value of `lockobject` while executing a `SyncLock` block.</span></span> <span data-ttu-id="a3ffc-124">メカニズムは、ロック オブジェクトが変わらないことが必要です。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-124">The mechanism requires that the lock object remain unchanged.</span></span>  
  
-   <span data-ttu-id="a3ffc-125">使用することはできません、 [Await](../../../visual-basic/language-reference/operators/await-operator.md)で演算子を`SyncLock`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-125">You can't use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in a `SyncLock` block.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a3ffc-126">動作</span><span class="sxs-lookup"><span data-stu-id="a3ffc-126">Behavior</span></span>  
  
-   <span data-ttu-id="a3ffc-127">メカニズムです。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-127">Mechanism.</span></span> <span data-ttu-id="a3ffc-128">スレッドが達したとき、`SyncLock`ステートメントでは、評価、`lockobject`式と式によって返されるオブジェクトの排他ロックを取得するまで実行を中断します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-128">When a thread reaches the `SyncLock` statement, it evaluates the `lockobject` expression and suspends execution until it acquires an exclusive lock on the object returned by the expression.</span></span> <span data-ttu-id="a3ffc-129">別のスレッドが達したとき、`SyncLock`ステートメントでは、これはロックを取得、最初のスレッドが実行されるまで、`End SyncLock`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-129">When another thread reaches the `SyncLock` statement, it does not acquire a lock until the first thread executes the `End SyncLock` statement.</span></span>  
  
-   <span data-ttu-id="a3ffc-130">保護されたデータ。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-130">Protected Data.</span></span> <span data-ttu-id="a3ffc-131">場合`lockobject`は、`Shared`変数、排他ロック クラスの任意のインスタンス内のスレッドが実行されないように、`SyncLock`他のスレッドが実行中にブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-131">If `lockobject` is a `Shared` variable, the exclusive lock prevents a thread in any instance of the class from executing the `SyncLock` block while any other thread is executing it.</span></span> <span data-ttu-id="a3ffc-132">これは、すべてのインスタンス間で共有されるデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-132">This protects data that is shared among all the instances.</span></span>  
  
     <span data-ttu-id="a3ffc-133">場合`lockobject`インスタンス変数は、(いない`Shared`)、ロックにより、スレッドの実行を現在のインスタンスで実行できなくなります、`SyncLock`同じインスタンス内の別のスレッドと同時にブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-133">If `lockobject` is an instance variable (not `Shared`), the lock prevents a thread running in the current instance from executing the `SyncLock` block at the same time as another thread in the same instance.</span></span> <span data-ttu-id="a3ffc-134">これは、個々 のインスタンスで保持されるデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-134">This protects data maintained by the individual instance.</span></span>  
  
-   <span data-ttu-id="a3ffc-135">取得と解放します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-135">Acquisition and Release.</span></span> <span data-ttu-id="a3ffc-136">A`SyncLock`ブロックのように動作を`Try...Finally`を構築、`Try`ブロックで排他ロックを取得する`lockobject`と`Finally`ブロックでは、それを解放します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-136">A `SyncLock` block behaves like a `Try...Finally` construction in which the `Try` block acquires an exclusive lock on `lockobject` and the `Finally` block releases it.</span></span> <span data-ttu-id="a3ffc-137">このため、`SyncLock`ブロックがブロックを終了する方法に関係なく、ロックの解放を保証します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-137">Because of this, the `SyncLock` block guarantees release of the lock, no matter how you exit the block.</span></span> <span data-ttu-id="a3ffc-138">これはハンドルされない例外の場合にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-138">This is true even in the case of an unhandled exception.</span></span>  
  
-   <span data-ttu-id="a3ffc-139">フレームワーク。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-139">Framework Calls.</span></span> <span data-ttu-id="a3ffc-140">`SyncLock`ブロックを取得し、呼び出すことによって、排他ロックを解放、`Enter`と`Exit`のメソッド、`Monitor`クラス、<xref:System.Threading>名前空間。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-140">The `SyncLock` block acquires and releases the exclusive lock by calling the `Enter` and `Exit` methods of the `Monitor` class in the <xref:System.Threading> namespace.</span></span>  
  
## <a name="programming-practices"></a><span data-ttu-id="a3ffc-141">プログラミング手法</span><span class="sxs-lookup"><span data-stu-id="a3ffc-141">Programming Practices</span></span>  
 <span data-ttu-id="a3ffc-142">`lockobject`式は常をクラスにのみ属しているオブジェクトを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-142">The `lockobject` expression should always evaluate to an object that belongs exclusively to your class.</span></span> <span data-ttu-id="a3ffc-143">宣言する必要があります、`Private`オブジェクト変数を現在のインスタンスに属するデータを保護または`Private Shared`オブジェクト変数をすべてのインスタンスに共通のデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-143">You should declare a `Private` object variable to protect data belonging to the current instance, or a `Private Shared` object variable to protect data common to all instances.</span></span>  
  
 <span data-ttu-id="a3ffc-144">使用しないようにする、`Me`ロックを提供するキーワードはオブジェクトのインスタンス データ。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-144">You should not use the `Me` keyword to provide a lock object for instance data.</span></span> <span data-ttu-id="a3ffc-145">ロック オブジェクトとしてその参照を使用できます、クラスの外部のコードに、クラスのインスタンスへの参照がある場合、`SyncLock`ブロックから、まったく異なる別のデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-145">If code external to your class has a reference to an instance of your class, it could use that reference as a lock object for a `SyncLock` block completely different from yours, protecting different data.</span></span> <span data-ttu-id="a3ffc-146">この方法で、クラスとその他のクラスでした互いにブロックの実行が関連付けられていない`SyncLock`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-146">In this way, your class and the other class could block each other from executing their unrelated `SyncLock` blocks.</span></span> <span data-ttu-id="a3ffc-147">同様に、文字列をロックも問題が、同じ文字列を使用して、プロセスの他のコードが同じロックを共有します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-147">Similarly locking on a string can be problematic since any other code in the process using the same string will share the same lock.</span></span>  
  
 <span data-ttu-id="a3ffc-148">使用しないようにする、`Me.GetType`のロック オブジェクトを提供するメソッドは、データを共有します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-148">You should also not use the `Me.GetType` method to provide a lock object for shared data.</span></span> <span data-ttu-id="a3ffc-149">これは、ため`GetType`常に、同じを返します`Type`オブジェクトの特定のクラス名。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-149">This is because `GetType` always returns the same `Type` object for a given class name.</span></span> <span data-ttu-id="a3ffc-150">外部コードを呼び出すことが`GetType`クラスを使用している同じロック オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-150">External code could call `GetType` on your class and obtain the same lock object you are using.</span></span> <span data-ttu-id="a3ffc-151">結果から互いをブロックしている 2 つのクラスになり、`SyncLock`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-151">This would result in the two classes blocking each other from their `SyncLock` blocks.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a3ffc-152">使用例</span><span class="sxs-lookup"><span data-stu-id="a3ffc-152">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="a3ffc-153">説明</span><span class="sxs-lookup"><span data-stu-id="a3ffc-153">Description</span></span>  
 <span data-ttu-id="a3ffc-154">次の例では、メッセージの単純なリストを保持するクラスを示します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-154">The following example shows a class that maintains a simple list of messages.</span></span> <span data-ttu-id="a3ffc-155">配列内のメッセージを保持し、最後は、変数にその配列の要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-155">It holds the messages in an array and the last used element of that array in a variable.</span></span> <span data-ttu-id="a3ffc-156">`addAnotherMessage`プロシージャが最後の要素をインクリメントし、新しいメッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-156">The `addAnotherMessage` procedure increments the last element and stores the new message.</span></span> <span data-ttu-id="a3ffc-157">これら 2 つの操作がによって保護されている、`SyncLock`と`End SyncLock`ステートメント、他のスレッドはその最後の要素をインクリメントする前に、新しいメッセージを格納する必要があるしたら、最後の要素がインクリメントされていたためです。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-157">Those two operations are protected by the `SyncLock` and `End SyncLock` statements, because once the last element has been incremented, the new message must be stored before any other thread can increment the last element again.</span></span>  
  
 <span data-ttu-id="a3ffc-158">場合、`simpleMessageList`クラスは、そのすべてのインスタンス、変数間のメッセージの 1 つのリストを共有`messagesList`と`messagesLast`宣言`Shared`します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-158">If the `simpleMessageList` class shared one list of messages among all its instances, the variables `messagesList` and `messagesLast` would be declared as `Shared`.</span></span> <span data-ttu-id="a3ffc-159">この場合は、変数`messagesLock`必要もあります`Shared`、すべてのインスタンスによって使用される 1 つのロック オブジェクトがあるようにします。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-159">In this case, the variable `messagesLock` should also be `Shared`, so that there would be a single lock object used by every instance.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a3ffc-160">コード</span><span class="sxs-lookup"><span data-stu-id="a3ffc-160">Code</span></span>  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a><span data-ttu-id="a3ffc-161">説明</span><span class="sxs-lookup"><span data-stu-id="a3ffc-161">Description</span></span>  
 <span data-ttu-id="a3ffc-162">次のコードの例では、スレッドと`SyncLock`します。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-162">The following example uses threads and `SyncLock`.</span></span> <span data-ttu-id="a3ffc-163">限り、`SyncLock`ステートメントが存在する、ステートメント ブロックがクリティカル セクションと`balance`決して、負の数。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-163">As long as the `SyncLock` statement is present, the statement block is a critical section and `balance` never becomes a negative number.</span></span> <span data-ttu-id="a3ffc-164">コメント アウトすることができます、`SyncLock`と`End SyncLock`隠れますの効果を確認するステートメント、`SyncLock`キーワード。</span><span class="sxs-lookup"><span data-stu-id="a3ffc-164">You can comment out the `SyncLock` and `End SyncLock` statements to see the effect of leaving out the `SyncLock` keyword.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a3ffc-165">コード</span><span class="sxs-lookup"><span data-stu-id="a3ffc-165">Code</span></span>  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a><span data-ttu-id="a3ffc-166">コメント</span><span class="sxs-lookup"><span data-stu-id="a3ffc-166">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ffc-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3ffc-167">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [<span data-ttu-id="a3ffc-168">同期プリミティブの概要</span><span class="sxs-lookup"><span data-stu-id="a3ffc-168">Overview of synchronization primitives</span></span>](../../../standard/threading/overview-of-synchronization-primitives.md)
