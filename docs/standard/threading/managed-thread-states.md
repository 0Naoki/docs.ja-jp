---
title: マネージド スレッドの状態
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a55409cd2c3bed2bc09db10622de1cceab934112
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2018
ms.locfileid: "45624568"
---
# <a name="managed-thread-states"></a>マネージド スレッドの状態
プロパティ <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> には、スレッドの現在の状態を示すビット マスクが用意されています。 スレッドは、 <xref:System.Threading.ThreadState> 列挙型に含まれる状態のうち、常に少なくとも 1 つの状態となり、同時に複数の状態になることもあります。  
  
> [!IMPORTANT]
>  スレッドの状態は、いくつかのデバッグ シナリオでのみ必要になります。 スレッドの動作を同期化する目的でコード内でスレッドの状態を使用しないでください。  
  
 マネージド スレッドを作成すると、そのスレッドは <xref:System.Threading.ThreadState.Unstarted> 状態になります。 スレッドは、オペレーティング システムによって起動状態にされるまで、 <xref:System.Threading.ThreadState.Unstarted> 状態のままです。 <xref:System.Threading.Thread.Start%2A> を呼び出すと、スレッドを開始できることをオペレーティング システムに通知できますが、スレッドの状態は変化しません。  
  
 マネージド環境に入ってくるアンマネージド スレッドは、既に起動状態になっています。 スレッドがいったん起動状態になると、さまざまなアクションによってスレッドの状態が変更される可能性があります。 状態が変更される原因となるアクションと、対応する新しい状態を次の表に示します。  
  
|アクション|変更後の新しい状態|  
|------------|-------------------------|  
|<xref:System.Threading.Thread> クラスのコンストラクターが呼び出される。|<xref:System.Threading.ThreadState.Unstarted>|  
|別のスレッドが <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> を呼び出す。|<xref:System.Threading.ThreadState.Unstarted>|  
|スレッドが <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> に応答して実行を開始する。|<xref:System.Threading.ThreadState.Running>|  
|スレッドが <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> を呼び出す。|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|スレッドが別のオブジェクトで <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> を呼び出す。|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|スレッドが別のスレッドで <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> を呼び出す。|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|別のスレッドが <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> を呼び出す。|<xref:System.Threading.ThreadState.SuspendRequested>|  
|スレッドが <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 要求に応答する。|<xref:System.Threading.ThreadState.Suspended>|  
|別のスレッドが <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> を呼び出す。|<xref:System.Threading.ThreadState.Running>|  
|別のスレッドが <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> を呼び出す。|<xref:System.Threading.ThreadState.AbortRequested>|  
|スレッドが <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> に応答する。|<xref:System.Threading.ThreadState.Aborted>の後 <xref:System.Threading.ThreadState.Stopped>|  
  
 <xref:System.Threading.ThreadState.Running> 状態の値は 0 のため、ビット テストを実行しても、この状態を検出できません。 代わりに、擬似コードによる次のテストを実行できます。  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 スレッドは、どの時点でも複数の状態にあることがよくあります。 たとえば、<xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 呼び出しでスレッドがブロックされ、別のスレッドが同じスレッドに対して <xref:System.Threading.Thread.Abort%2A> を呼び出した場合、スレッドは同時に <xref:System.Threading.ThreadState.WaitSleepJoin> 状態と <xref:System.Threading.ThreadState.AbortRequested> 状態になります。 この場合、スレッドは、 <xref:System.Threading.Monitor.Wait%2A> への呼び出しから戻るか中断されるとすぐに、 <xref:System.Threading.ThreadAbortException>を受け取ります。  
  
 スレッドは、 <xref:System.Threading.ThreadState.Unstarted> への呼び出しの結果として <xref:System.Threading.Thread.Start%2A>状態から出ると、 <xref:System.Threading.ThreadState.Unstarted> 状態に戻ることはできません。 また、スレッドは <xref:System.Threading.ThreadState.Stopped> 状態から出ることはできません。  
  
## <a name="see-also"></a>関連項目

- <xref:System.Threading.ThreadAbortException>  
- <xref:System.Threading.Thread>  
- <xref:System.Threading.ThreadState>  
- [スレッド化](../../../docs/standard/threading/index.md)
