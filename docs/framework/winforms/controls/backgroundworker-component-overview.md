---
title: BackgroundWorker コンポーネントの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- BackgroundWorker
helpviewer_keywords:
- BackgroundWorker component
- background tasks
- Asynchronous Pattern
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 64e9b3ab-7443-4a77-ab17-b8b8c0cb3f62
ms.openlocfilehash: 1f7da963db34434ee2631e9e2c0367abbd628656
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488223"
---
# <a name="backgroundworker-component-overview"></a>BackgroundWorker コンポーネントの概要
一般的な操作には、実行時間が長くかかるものが数多くあります。 次に例を示します。  
  
-   イメージのダウンロード  
  
-   Web サービスの起動  
  
-   ファイルのダウンロードとアップロード (ピアツーピア アプリケーションの場合を含む)  
  
-   ローカルでの複雑な計算  
  
-   データベース トランザクション  
  
-   ローカル ディスク アクセス (前提としてメモリ アクセスに比べて低速です)  
  
 以上のような操作の実行時には、ユーザー インターフェイスがハングアップすることがあります。 応答性に優れた UI を必要としながらも、このような操作との関連で長時間の遅延に直面する場合は、<xref:System.ComponentModel.BackgroundWorker> コンポーネントが便利なソリューションになります。  
  
 <xref:System.ComponentModel.BackgroundWorker> コンポーネントを使用すると、時間のかかる操作を、アプリケーションのメイン UI スレッドとは別のスレッドで非同期的に ("バックグラウンドで") 実行できます。 <xref:System.ComponentModel.BackgroundWorker> を使用するには、バックグラウンドで実行する、時間のかかるワーカー メソッドをこのコンポーネントに通知して、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドを呼び出すだけです。 呼び出し元スレッドが正常に動作し続けると共に、ワーカー メソッドも非同期的に動作します。 このメソッドが終了すると、<xref:System.ComponentModel.BackgroundWorker> は、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> イベントを起動して、呼び出し元スレッドに警告します。このイベントには、オプションで操作の結果を含めることもできます。  
  
 <xref:System.ComponentModel.BackgroundWorker>コンポーネントは、**ツールボックス**の**コンポーネント**タブ。<xref:System.ComponentModel.BackgroundWorker> をフォームに追加するには、<xref:System.ComponentModel.BackgroundWorker> コンポーネントをフォームにドラッグします。 コンポーネント トレイに表示され、そのプロパティに表示、**プロパティ**ウィンドウ。  
  
 非同期操作を開始するには、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> メソッドを使用します。 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> は、オプションの `object` パラメーターを受け取り、このパラメーターを使用してワーカー メソッドに引数を渡すことができます。 <xref:System.ComponentModel.BackgroundWorker> クラスは、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベントを公開します。このイベントには、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラー経由でワーカー スレッドをアタッチします。  
  
 <xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーは、<xref:System.ComponentModel.DoWorkEventArgs> プロパティを持つ <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> パラメーターを受け取ります。 このプロパティは、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> からパラメーターを受け取り、<xref:System.ComponentModel.BackgroundWorker.DoWork> イベント ハンドラーで呼び出されるワーカー メソッドに渡されます。 次の例は、`ComputeFibonacci` というワーカー メソッドの結果を代入する方法を示しています。 掲載より大きな例の一部である[方法: バック グラウンド操作を使用してフォームを実装する](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)します。  
  
 [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
 [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
 イベント ハンドラーの使用に関する詳細については、次を参照してください。[イベント](../../../../docs/standard/events/index.md)します。  
  
> [!CAUTION]
>  どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。 マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](../../../../docs/standard/threading/managed-threading-best-practices.md)」を参照してください。  
  
 使用しての詳細については、<xref:System.ComponentModel.BackgroundWorker>クラスを参照してください[方法: バック グラウンドで操作を実行](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)します。  
  
## <a name="see-also"></a>関連項目  
 [ビルド内にありません: Visual Basic でのマルチスレッド](https://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [方法: バックグラウンド操作を使用するフォームを実装する](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)
