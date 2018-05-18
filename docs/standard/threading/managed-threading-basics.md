---
title: マネージ スレッド処理の基本
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fa91bb22de6492815f79bfd50e1fefc800c6047
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="managed-threading-basics"></a>マネージ スレッド処理の基本
このセクションの最初の 5 つのトピックは、マネージ スレッド処理を使用するタイミングを判断するのに役立つように設計されており、また、いくつかの基本的な機能について説明するためのものです。 その他の機能を提供するクラスについては、「[スレッド処理オブジェクトと機能](../../../docs/standard/threading/threading-objects-and-features.md)」と「[同期プリミティブの概要](../../../docs/standard/threading/overview-of-synchronization-primitives.md)」を参照してください。  
  
 このセクションの残りのトピックには、マネージ スレッド処理と Windows オペレーティング システムとの相互作用など、高度なトピックが含まれます。  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] では、タスク並列ライブラリと PLINQ は、マルチスレッド プログラムでのタスクとデータの並列処理のための API を提供します。 詳細については、[並列プログラミング](../../../docs/standard/parallel-programming/index.md)に関するページをご覧ください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [スレッドおよびスレッド処理](../../../docs/standard/threading/threads-and-threading.md)  
 複数のスレッドの利点と欠点について説明し、スレッドを作成またはスレッド プール スレッドを使用する可能性のあるシナリオの概要を示します。  
  
 [マネージ スレッドの例外](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 さまざまなバージョンの .NET Framework のスレッドでのハンドルされていない例外の動作、特に、アプリケーションの終了の原因となる状況について説明します。  
  
 [マルチスレッド処理のためのデータの同期](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 複数のスレッドで使用されるクラスのデータを同期する方法について説明します。  
  
 [マネージ スレッドの状態](../../../docs/standard/threading/managed-thread-states.md)  
 基本的なスレッドの状態と、スレッドが実行されているかどうかの検出方法について説明します。  
  
 [フォアグラウンド スレッドとバックグラウンド スレッド](../../../docs/standard/threading/foreground-and-background-threads.md)  
 フォアグラウンド スレッドとバック グラウンド スレッドの違いについて説明します。  
  
 [Windows でのマネージ スレッド処理とアンマネージ スレッド処理](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 マネージ スレッド処理とアンマネージ スレッド処理の関係について説明し、Windows のスレッド処理 API に相当するマネージ API をリストし、COM アパートメントとマネージ スレッドの相互作用について説明します。  
  
 [Thread.Suspend、ガベージ コレクション、およびセーフ ポイント](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 スレッドの中断とガベージ コレクションについて説明します。  
  
 [スレッド ローカル ストレージ: スレッド相対静的フィールドとデータ スロット](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 スレッド相対ストレージ メカニズムについて説明します。  
  
 [マネージ スレッドのキャンセル](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 取り消しトークンを使用して、非同期または長時間実行されている同期操作の取り消し方法について説明します。  
  
## <a name="reference"></a>参照  
 <xref:System.Threading.Thread>  
 **Thread** クラスのリファレンス ドキュメントです。このクラスは、アンマネージ コードから作成されたか、マネージ アプリケーションで作成されたかにかかわらず、マネージ スレッドを表します。  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 ユーザー インターフェイス オブジェクトと共にマルチスレッドを実装するための安全な方法を提供します。  
  
## <a name="related-sections"></a>関連項目  
 [同期プリミティブの概要](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 複数のスレッドのアクティビティを同期するために使用されるマネージ クラスについて説明します。  
  
 [マネージ スレッド処理の実施](../../../docs/standard/threading/managed-threading-best-practices.md)  
 マルチスレッドに関する一般的な問題と、問題を回避するための方法について説明します。  
  
 [並列プログラミング](../../../docs/standard/parallel-programming/index.md)  
 非同期およびマルチスレッドの .NET Framework アプリケーションを作成する作業を大幅に簡素化する、タスク並列ライブラリと PLINQ について説明します。
