---
title: どのような&#39;Windows Workflow Foundation の新機能として s
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 605e1401eb2f2fdee7bb39c6636c0245154041a4
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2018
---
# <a name="what39s-new-in-windows-workflow-foundation"></a>どのような&#39;Windows Workflow Foundation の新機能として s
Windows Workflow Foundation (WF) で[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]以前のバージョンから開発パラダイムを変更します。 ワークフローでは、新しい機能のホストの作成、実行、保守、実装が簡単になっています。 [!INCLUDE[crabout](../../../includes/crabout-md.md)] .NET 3.0 を移行して、最新バージョンを使用する .NET 3.5 ワークフロー アプリケーションを参照してください。[移行ガイダンス](../../../docs/framework/windows-workflow-foundation/migration-guidance.md)です。  
  
## <a name="workflow-activity-model"></a>ワークフロー アクティビティ モデル  
 アクティビティは、現在はワークフロー作成の基本単位であり、<xref:System.Workflow.Activities.SequentialWorkflowActivity> クラスや <xref:System.Workflow.Activities.StateMachineWorkflowActivity> クラスは使用されなくなっています。 <xref:System.Activities.Activity> クラスは、ワークフロー動作の基本抽象クラスです。 このため、アクティビティの作成者は、基本的なカスタム アクティビティ機能用に <xref:System.Activities.CodeActivity> を実装するか、一定範囲のランタイムを使用するカスタム アクティビティ機能用に <xref:System.Activities.NativeActivity> を実装することができます。 <xref:System.Activities.Activity> クラス宣言の観点から他の新しい動作を明示するアクティビティの作成者によって使用<xref:System.Activities.NativeActivity>、 <xref:System.Activities.CodeActivity>、 <xref:System.Activities.AsyncCodeActivity>、または<xref:System.Activities.DynamicActivity>オブジェクト、カスタム開発したかに含まれているかどうか、[ビルトイン アクティビティライブラリ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)です。  
  
## <a name="rich-composite-activity-options"></a>豊富な複合アクティビティ オプション  
 <xref:System.Activities.Statements.Flowchart> は新しい強力な制御フロー アクティビティです。作成者は、これを使用して任意のループや条件分岐をモデル化できます。 <xref:System.Activities.Statements.Flowchart> により、以前は <xref:System.Workflow.Activities.StateMachineWorkflowActivity> でのみ実装が可能であったイベント ドリブン プログラミング モデルを使用できます。 手続き型のワークフローでは、<xref:System.Activities.Statements.TryCatch> や <xref:System.Activities.Statements.Switch%601> などの従来のフロー制御構造をモデル化する新しいフロー制御アクティビティを利用できます。  
  
## <a name="expanded-built-in-activity-library"></a>拡張ビルトイン アクティビティ ライブラリ  
 アクティビティ ライブラリには、次のような新しい機能があります。  
  
-   <xref:System.Activities.Statements.DoWhile>、<xref:System.Activities.Statements.Pick>、<xref:System.Activities.Statements.TryCatch>、<xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.Switch%601>、<xref:System.Activities.Statements.ParallelForEach%601> などの新しいフロー制御アクティビティ  
  
-   <xref:System.Activities.Statements.Assign> などのメンバー データを操作するためのアクティビティと、<xref:System.Activities.Statements.AddToCollection%601> などのコレクション アクティビティ  
  
-   <xref:System.Activities.Statements.TransactionScope> や <xref:System.Activities.Statements.Compensate> などのトランザクションを制御するアクティビティ  
  
-   <xref:System.ServiceModel.Activities.SendContent> や <xref:System.ServiceModel.Activities.ReceiveReply> などの新しいメッセージング アクティビティ  
  
## <a name="explicit-activity-data-model"></a>明示的なアクティビティ データ モデル  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] には、データを格納および移動するための新しいオプションがあります。 データは、<xref:System.Activities.Variable> を使用してアクティビティに格納できます。 データをアクティビティに移動したり、アクティビティから移動したりするときは、特殊な引数型を使用してデータの移動方向が判定されます。 これらの型は、<xref:System.Activities.InArgument>、<xref:System.Activities.InOutArgument>、<xref:System.Activities.OutArgument>です。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Windows Workflow Foundation のデータ モデル](../../../docs/framework/windows-workflow-foundation/data-model.md)です。  
  
## <a name="enhanced-hosting-persistence-and-tracking-options"></a>ホスティング、永続化、追跡の強化されたオプション  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] には、次のような永続化の拡張機能があります。  
  
-   <xref:System.ServiceModel.Activities.WorkflowServiceHost>、<xref:System.Activities.WorkflowApplication>、<xref:System.Activities.WorkflowInvoker> などの、ワークフローを実行するための多数のオプションがあります。  
  
-   <xref:System.Activities.Statements.Persist> アクティビティを使用してワークフロー状態データを明示的に永続化できます。  
  
-   ホストは、<xref:System.Activities.ActivityInstance> をアンロードせずに永続化できます。  
  
-   ワークフローは、永続化できないデータを処理するときは非永続化ゾーンを指定できます。このため、非永続化ゾーンを終了するまで永続化は延期されます。  
  
-   トランザクションは、<xref:System.Activities.Statements.TransactionScope> を使用してワークフローに流し込むことができます。  
  
-   追跡は、<xref:System.Activities.Tracking.TrackingParticipant> を使用して、簡単に実行できます。  
  
-   システムのイベント ログへの追跡は <xref:System.Activities.Tracking.EtwTrackingParticipant> を使用して実現されます。  
  
-   保留中のワークフローの再開は、<xref:System.Activities.Bookmark> オブジェクトを使用して管理されるようになりました。  
  
## <a name="easier-ability-to-extend-wf-designer-experience"></a>WF デザイナー エクスペリエンスの容易な拡張  
 新しい WF デザイナーは Windows Presentation Foundation (WPF) のビルドが簡単に Visual Studio の外部で WF デザイナーを再ホストするときに使用できるモデルを提供およびもカスタム アクティビティ デザイナーを作成するための使いやすいメカニズムを提供します。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [ワークフローのデザイン エクスペリエンスのカスタマイズ](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)です。
