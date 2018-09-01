---
title: .NET での並列プログラミング
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 372ffd7e17f60b8045cd5f89d52456c5f9655de1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408163"
---
# <a name="parallel-programming-in-net"></a>.NET での並列プログラミング

多くのパーソナル コンピューターとワークステーションには、複数スレッドの同時実行を可能にするいくつかの CPU コアがあります。 近い将来、コンピューターは、これよりはるかに多くのコアを搭載すると予想されています。 現在および将来のハードウェアを活用するには、コードを並列化して複数のプロセッサに負荷を分散します。 以前は、並列化には低水準のスレッドおよびロックの操作が必要でした。 Visual Studio 2010 および .NET Framework 4 では、新しいランタイム、新しいクラス ライブラリの型、および新しい診断ツールを提供することで、並列プログラミングのサポートを強化しています。 これらの機能により並行開発が簡素化され、スレッドやスレッド プールを直接操作することなく、効率的で詳細な、拡張性のある並列コードを自然な表現方法で記述できるようになります。 .NET Framework 4 の並列プログラミング アーキテクチャの高度な概要を次の図に示します。

 ![.NET 並列プログラミング アーキテクチャ](./media/tpl-architecture.png "TPL_Architecture")

## <a name="related-topics"></a>関連トピック

|テクノロジ|説明|
|----------------|-----------------|
|[タスク並列ライブラリ (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|並列バージョンの <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> ループおよび `For` ループを含む `ForEach` クラスに関するドキュメントと、非同期操作の推奨される表現方法を表す <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> クラスに関するドキュメントが用意されています。|
|[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|さまざまなシナリオでパフォーマンスを大幅に向上させる、LINQ to Objects の並列実装です。|
|[並列プログラミングのデータ構造](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|スレッド セーフなコレクション クラス、軽量な同期型、および限定的な初期化の種類に関するドキュメントへのリンクを示します。|
|[並列診断ツール](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|タスクと並列スタック向けの Visual Studio デバッガー ウィンドウ、および[同時実行ビジュアライザー](/visualstudio/profiling/concurrency-visualizer)に関するドキュメントへのリンクを示します。|
|[PLINQ および TPL 用のカスタム パーティショナー](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|パーティションのしくみと、既定のパーティションの設定方法または新しいパーティションの作成方法について説明します。|
|[タスク スケジューラ](https://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|スケジューラのしくみと既定のスケジューラの構成方法について説明します。|
|[PLINQ および TPL のラムダ式](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|C# および Visual Basic のラムダ式について簡単に説明し、PLINQ およびタスク並列ライブラリでラムダ式を使用する方法を示します。|
|[関連項目](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|.NET での並列プログラミングに関する追加の情報とサンプル リソースへのリンクを示します。|

## <a name="see-also"></a>関連項目

- [非同期の概要](../async.md)
- [マネージド スレッド処理](../threading/index.md)
