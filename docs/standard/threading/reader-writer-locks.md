---
title: 読み取り/書き込みロック
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8be9b4eef30333fbbdc26915635d17157176d6fc
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275061"
---
# <a name="reader-writer-locks"></a><span data-ttu-id="70676-102">読み取り/書き込みロック</span><span class="sxs-lookup"><span data-stu-id="70676-102">Reader-Writer Locks</span></span>
<span data-ttu-id="70676-103"><xref:System.Threading.ReaderWriterLockSlim> クラスを使用すると、複数のスレッドが同時に 1 つのリソースを読み取ることができますが、リソースに書き込むためには、排他的なロックを待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70676-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="70676-104">アプリケーションで、<xref:System.Threading.ReaderWriterLockSlim> を使用して、共有リソースにアクセスするスレッド間で協調的に同期させる場合があります。</span><span class="sxs-lookup"><span data-stu-id="70676-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="70676-105">ロックは <xref:System.Threading.ReaderWriterLockSlim> 自体によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="70676-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="70676-106">他のスレッド同期機構と同様に、<xref:System.Threading.ReaderWriterLockSlim> によって提供されるロックを回避するスレッドがないようにすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="70676-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="70676-107">1 つの方法として、共有リソースをカプセル化するクラスをデザインする方法があります。</span><span class="sxs-lookup"><span data-stu-id="70676-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="70676-108">このクラスは、プライベートな共有リソースにアクセスするメンバーを提供します。このメンバーは、プライベートな <xref:System.Threading.ReaderWriterLockSlim> を使用して同期を行います。</span><span class="sxs-lookup"><span data-stu-id="70676-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="70676-109">たとえば、<xref:System.Threading.ReaderWriterLockSlim> クラスのコード例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70676-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="70676-110"><xref:System.Threading.ReaderWriterLockSlim> は効率的に動作するように設計されているので、個々のオブジェクトの同期に使用できます。</span><span class="sxs-lookup"><span data-stu-id="70676-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="70676-111">読み取り操作と書き込み操作の時間を最小限にするように、アプリケーションの構造を設計してください。</span><span class="sxs-lookup"><span data-stu-id="70676-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="70676-112">書き込みロックは排他的なので、書き込み操作の時間が長いと、その分、スループットが低下します。</span><span class="sxs-lookup"><span data-stu-id="70676-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="70676-113">読み取り操作時間が長いと、ライターを待たせることになります。また、書き込みアクセスを待機しているスレッドが 1 つでもあると、読み取りアクセスを要求するスレッドもブロックされます。</span><span class="sxs-lookup"><span data-stu-id="70676-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70676-114">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] には、<xref:System.Threading.ReaderWriterLockSlim> と <xref:System.Threading.ReaderWriterLock> という 2 つのリーダー/ライター ロックがあります。</span><span class="sxs-lookup"><span data-stu-id="70676-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="70676-115">すべての新規開発で、<xref:System.Threading.ReaderWriterLockSlim> を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70676-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="70676-116"><xref:System.Threading.ReaderWriterLockSlim> は <xref:System.Threading.ReaderWriterLock> と似ていますが、再帰の規則や、ロック状態のアップグレードおよびダウングレードの規則が簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="70676-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="70676-117"><xref:System.Threading.ReaderWriterLockSlim> は、デッドロックの可能性を大幅に回避します。</span><span class="sxs-lookup"><span data-stu-id="70676-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="70676-118">さらに、<xref:System.Threading.ReaderWriterLockSlim> のパフォーマンスは <xref:System.Threading.ReaderWriterLock> と比較して格段に優れています。</span><span class="sxs-lookup"><span data-stu-id="70676-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70676-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="70676-119">See also</span></span>

- <xref:System.Threading.ReaderWriterLockSlim>  
- <xref:System.Threading.ReaderWriterLock>  
- [<span data-ttu-id="70676-120">スレッド化</span><span class="sxs-lookup"><span data-stu-id="70676-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="70676-121">スレッド処理オブジェクトと機能</span><span class="sxs-lookup"><span data-stu-id="70676-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
