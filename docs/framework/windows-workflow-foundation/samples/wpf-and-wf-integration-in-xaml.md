---
title: XAML での WPF と WF の統合
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4f53b48-fc90-4315-bca0-ba009562f488
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6bc761b93ff8d5c0dc79a86d0159d50d65fb727c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2018
---
# <a name="wpf-and-wf-integration-in-xaml"></a>XAML での WPF と WF の統合
このサンプルでは、1 つの XAML ドキュメントで Windows Presentation Foundation (WPF) および Windows Workflow Foundation (WF) 機能を使用するアプリケーションを作成する方法を示します。 これを行うには、サンプルは、Windows Workflow Foundation (WF) および XAML 機能拡張を使用します。  
  
## <a name="sample-details"></a>サンプルの詳細  
 ShowWindow.xaml ファイルは、シーケンスのアクティビティによって操作される 2 つの文字列変数 <xref:System.Activities.Statements.Sequence> および `ShowWindow` を持つ `WriteLine` アクティビティに逆シリアル化します。 <xref:System.Activities.Statements.WriteLine> アクティビティは、<xref:System.Activities.Statements.WriteLine.Text%2A> プロパティに割り当てる式をコンソール ウィンドウに出力します。 `ShowWindow` アクティビティは、実行ロジックの一部として [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] ウィンドウを表示します。 このウィンドウの <xref:System.Activities.ActivityContext.DataContext%2A> には、シーケンスで宣言された変数が含まれます。 `ShowWindow` アクティビティで宣言されたウィンドウのコントロールは、データ バインドを使用してこれらの変数を操作します。 最後に、このウィンドウにはボタン コントロールが含まれます。 このボタンの `Click` イベントは、<xref:System.Activities.ActivityDelegate> アクティビティを含む `MarkupExtension` という名前の `CloseWindow` によって処理されます。 `MarkUpExtension` は、`x:Name` によって識別されるオブジェクトおよび格納先ウィンドウの <xref:System.Activities.ActivityContext.DataContext%2A> を、コンテキストとして提供する、含まれているアクティビティを呼び出します。 したがって、`CloseWindow.InArgument<Window>` は、ウィンドウの名前を参照する式を使用してバインドできます。  
  
 `ShowWindow` アクティビティは、<xref:System.Activities.AsyncCodeActivity%601> ウィンドウを表示するために [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] クラスから派生し、ウィンドウが閉じられるときに完了します。 `Window` プロパティは、アクティビティの実行ごとにウィンドウを必要に応じて作成できるようにする `Func<Window>` 型です。 `Window` プロパティは、<xref:System.Xaml.XamlDeferringLoader> を使用してこの遅延評価モデルを有効にします。 `FuncFactoryDeferringLoader` を使用すると、`XamlReader` をシリアル化中にキャプチャしてアクティビティの実行中に読み取ることができます。  
  
 アクティビティが適切に記述されていれば、スケジューラ スレッドはブロックされません。 ただし、`ShowWindow` アクティビティは、表示しているウィンドウが閉じられるまで完了できません。 `ShowWindow` アクティビティは、<xref:System.Activities.AsyncCodeActivity> から派生して <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A> メソッドを <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> メソッドで呼び出し、ウィンドウをモーダルで表示することによってこの動作を実現します。 デリゲートは、WPF <xref:System.ServiceModel.InstanceContext.SynchronizationContext%2A> を介して呼び出されます。 `ShowWindow` アクティビティは、<xref:System.Activities.ActivityContext.DataContext%2A> プロパティを `Window.DataContext` プロパティに割り当てて、データ バインド コントロールがスコープ内の変数にアクセスできるようにします。  
  
 このサンプルにおける最後の重要な点は、<xref:System.Workflow.ComponentModel.Serialization.MarkupExtension> という `DelegateActivityExtension` です。 このマークアップ拡張機能の `ProvideValue` メソッドは、埋め込みアクティビティを呼び出すデリゲートを返します。 このアクティビティは、[!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] データ コンテキストおよびスコープ内の `x:Name` 値を含む環境で実行されます。 `GenericInvoke` メソッドで、この環境は <xref:System.Activities.Hosting.SymbolResolver> 拡張機能を介してアクティビティに提供されます。 この拡張機能は、マークアップ拡張機能のデリゲートが呼び出されるたびに埋め込みアクティビティを呼び出すために使用される <xref:System.Activities.WorkflowInvoker> に追加されます。  
  
> [!NOTE]
>  既定のデザイナーでは ShowWindow アクティビティはサポートされません。したがって、ShowWindow.Xaml ファイルはデザイナーでは正しく表示されません。  
  
#### <a name="to-use-this-sample"></a>このサンプルを使用するには  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] を使用して、WPFWFIntegration.sln ソリューション ファイルを開きます。  
  
2.  ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。  
  
3.  ソリューションを実行するには、F5 キーを押します。  
  
4.  姓と名をダイアログ ボックスに入力します。  
  
5.  ダイアログ ボックスを閉じると、コンソールに名前がエコーされます。  
  
> [!IMPORTANT]
>  サンプルは、既にコンピューターにインストールされている場合があります。 続行する前に、次の (既定の) ディレクトリを確認してください。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  このディレクトリが存在しない場合は、「 [.NET Framework 4 向けの Windows Communication Foundation (WCF) および Windows Workflow Foundation (WF) のサンプル](http://go.microsoft.com/fwlink/?LinkId=150780) 」にアクセスして、 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] および [!INCLUDE[wf1](../../../../includes/wf1-md.md)] のサンプルをすべてダウンロードしてください。 このサンプルは、次のディレクトリに格納されます。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\WPFWFIntegration`