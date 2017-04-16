---
title: "Windows フォームの概要 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "スマート クライアント"
  - "Windows フォーム, Windows フォームの概要"
ms.assetid: 3a2b6284-c8d6-4e1c-8c69-0bed38f38cd4
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Windows フォームの概要
次の概要では、スマート クライアント アプリケーションの利点、Windows フォームのプログラミングの主な機能について説明し、Windows フォームを使用して今日の企業とエンドユーザーのニーズを満たすスマート クライアントを構築する方法を示します。  
  
## Windows フォームとスマート クライアント アプリケーション  
 Windows フォームを使用して、スマート クライアントを開発します。  *スマート クライアント*は、展開と更新が容易で、インターネットに接続したときも切断しているときも動作し、従来の Windows ベースのアプリケーションよりも安全な方法でローカル コンピューター上のリソースにアクセスできる、リッチなグラフィックスのアプリケーションです。  
  
### リッチで対話型のユーザー インターフェイスの構築  
 Windows フォームは、[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] のためのスマート クライアント テクノロジであり、ファイル システムへの読み書きなど、アプリケーションの一般的なタスクを簡略化するマネージ ライブラリのセットです。  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] などの開発環境を使用する場合、情報を表示して、ユーザーからの入力を要求し、ネットワーク経由でリモート コンピューターと通信する Windows フォームのスマート クライアント アプリケーションを作成できます。  
  
 Windows フォームでは、*フォーム*はユーザーに情報を表示するビジュアル サーフェイスです。  通常は、コントロールをフォームに追加して、マウスのクリックやキーの押下などのユーザー アクションへの応答を開発することで、Windows フォーム アプリケーションを開発します。  *コントロール* は、データを表示したりデータ入力を受け入れたりする独立したユーザー インターフェイス \(UI\) 要素です。  
  
 ユーザーがフォームまたはそのコントロールのいずれかにアクションを実行すると、そのアクションがイベントを生成します。  アプリケーションは、コードを使用してこれらのイベントに反応し、イベントが発生したときにそのイベントを処理します。  詳細については、「[Windows フォーム内でのイベント ハンドラーの作成](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)」を参照してください。  
  
 Windows フォームには、テキスト ボックス、ボタン、ドロップダウン ボックス、ラジオ ボタン、Web ページなどを表示するコントロールなど、フォームに追加できるさまざまなコントロールが含まれています。  フォーム上で使用できるすべてのコントロールの一覧は、「[Windows フォームで使用するコントロール](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)」を参照してください。  既存のコントロールがニーズを満たしていない場合に、Windows フォームは <xref:System.Windows.Forms.UserControl> クラスを使用した独自のカスタム コントロールの作成もサポートしています。  
  
 Windows フォームには、Microsoft Office のようなハイエンド アプリケーションの機能をエミュレートする豊富な UI コントロールが用意されています。  <xref:System.Windows.Forms.ToolStrip> コントロールと <xref:System.Windows.Forms.MenuStrip> コントロールを使用する場合、テキストとイメージを含むツールバーとメニューを作成したり、サブメニューを表示したり、テキスト ボックスやコンボ ボックスなど、その他のコントロールをホストしたりできます。  
  
 Windows フォーム デザイナーで [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] をドラッグ アンド ドロップすると、Windows フォーム アプリケーションを簡単に作成できます。  コントロールをカーソルで選択して、フォームの任意の場所に追加するだけです。  デザイナーがグリッド線やスナップ線などのツールを提供するので、コントロールの調整が楽になります。  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] を使用する場合も、コマンド ラインでコンパイルする場合も、<xref:System.Windows.Forms.FlowLayoutPanel>、<xref:System.Windows.Forms.TableLayoutPanel>、および <xref:System.Windows.Forms.SplitContainer> の各コントロールを使用して、短時間で高度なフォーム レイアウトを作成できます。  
  
 最後に、独自のカスタム UI 要素を作成する必要がある場合は、<xref:System.Drawing> 名前空間に、線、円、およびその他の図形をフォーム上に直接表示するクラスが多数含まれています。  
  
> [!NOTE]
>  Windows フォーム コントロールは、アプリケーション ドメイン間でマーシャリングするよう設計されていません。  このため、<xref:System.MarshalByRefObject> の <xref:System.Windows.Controls.Control> 基本型で可能であるように見えても、Microsoft は、<xref:System.AppDomain> 境界間の Windows フォーム コントロールの引き渡しはサポートしていません。  複数のアプリケーション ドメインを持つ Windows フォーム アプリケーションは、Windows フォーム コントロールがアプリケーション ドメインの境界を越えて渡されない限りサポートされます。  
  
#### フォームとコントロールの作成に関するヘルプ  
 これらの機能を使用する方法の手順を追った説明については、次のヘルプ トピックを参照してください。  
  
|説明|ヘルプ トピック|  
|--------|--------------|  
|フォーム上のコントロールを使用する|[方法 : Windows フォームにコントロールを追加する](../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|  
|<xref:System.Windows.Forms.ToolStrip> コントロールを使用する|[方法 : デザイナーを使用して標準アイテムで基本的な ToolStrip を作成する](../../../docs/framework/winforms/controls/create-a-basic-wf-toolstrip-with-standard-items-using-the-designer.md)|  
|<xref:System.Drawing> を使用してグラフィックスを作成する|[グラフィックス プログラミングについて](../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|カスタム コントロールの作成|[方法 : UserControl クラスを継承する](../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
### データの表示と操作  
 多くのアプリケーションは、データベース、XML ファイル、XML Web サービス、またはその他のデータ ソースからデータを表示する必要があります。  Windows フォームは、従来の行と列の形式である、表形式のデータを表示するために、<xref:System.Windows.Forms.DataGridView> コントロールという名前の柔軟なコントロールを提供しているため、すべてのデータが独自のセルを占有します。  <xref:System.Windows.Forms.DataGridView> を使用すると、個別のセルの外観のカスタマイズ、任意の列と行のその場でのロック、セルの内部の複雑なコントロールの表示や、その他の機能が可能になります。  
  
 ネットワーク経由のデータ ソースへの接続は、Windows フォームのスマート クライアントを使用すればシンプルなタスクです。  <xref:System.Windows.Forms.BindingSource> コンポーネントは、[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] と [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] の新しい Windows フォームであり、データ ソースへの接続を表し、データをコントロールにバインドするためのメソッドの公開、前または次のレコードへの移動、レコードの編集、元のソースへの変更の保存を実行します。  <xref:System.Windows.Forms.BindingNavigator> コントロールは、ユーザーがレコード間を移動する <xref:System.Windows.Forms.BindingSource> コンポーネントに対して、シンプルなインターフェイスを提供します。  
  
 \[データ ソース\] ウィンドウを使用すると、データ バインド コントロールを簡単に作成できます。  ウィンドウには、プロジェクト内のデータベース、Web サービス、オブジェクトなどのデータ ソースが表示されます。  このウィンドウからプロジェクトのフォームに項目をドラッグして、データ バインド コントロールを作成できます。  また、\[データ ソース\] ウィンドウから既存のコントロールにオブジェクトをドラッグして、データに既存のコントロールをバインドすることもできます。  
  
 Windows フォームで管理できる別の種類のデータ バインディングは*設定*です。  ほとんどのスマート クライアント アプリケーションは、フォームの前回のサイズなどの実行時の状態に関する情報を保持し、保存されたファイルの既定の場所などのユーザー設定のデータを保持する必要があります。  アプリケーション設定機能は、クライアント コンピューターに両方の種類の設定を保存する簡単な方法を提供することで、こうした要件に対応します。  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] またはコード エディターを使用してこれらの設定を定義したら、設定は XML として永続化され、実行時に自動的にメモリに読み取られます。  
  
#### データの表示と操作に関するヘルプ  
 これらの機能を使用する方法の手順を追った説明については、次のヘルプ トピックを参照してください。  
  
|説明|ヘルプ トピック|  
|--------|--------------|  
|<xref:System.Windows.Forms.BindingSource> コンポーネントを使用する|[方法 : デザイナーを使用して Windows フォーム コントロールを BindingSource コンポーネントにバインドする](../../../docs/framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|[!INCLUDE[vstecado](../../../includes/vstecado-md.md)] データ ソースを操作する|[方法 : Windows フォーム BindingSource コンポーネントで ADO.NET データを並べ替える\/フィルター処理する](../../../docs/framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|  
|\[データ ソース\] ウィンドウを使用する|[チュートリアル: Windows フォームでのデータの表示](../Topic/Walkthrough:%20Displaying%20Data%20on%20a%20Windows%20Form.md)|  
|アプリケーション設定を使用する|[方法 : アプリケーション設定を作成する](../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)|  
  
### クライアント コンピューターにアプリケーションを配置する  
 アプリケーションを作成した後、ユーザーにアプリケーションを送信して、独自のクライアント コンピューターにインストールして実行できるようにする必要があります。  [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] テクノロジを使用する場合、数回クリックするだけで、[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] の中からアプリケーションを配置して、Web 上のアプリケーションを指す URL をユーザーに提供することができます。  [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] は、アプリケーションのすべての要素と依存関係を管理し、クライアント コンピューターにアプリケーションが正しくインストールされていることを確認します。  
  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] アプリケーションは、ユーザーがネットワークに接続されている場合にのみ実行するか、オンラインとオフラインの両方で実行するかを構成することができます。  アプリケーションがオフライン操作をサポートするよう指定すると、[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] はユーザーの **\[スタート\]** メニューにアプリケーションへのリンクを追加します。  ユーザーは、URL を使用せずにアプリケーションを開くことができます。  
  
 アプリケーションを更新するときに、新しい配置マニフェストとアプリケーションの新しいコピーを Web サーバーに発行します。  [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] は、使用可能な更新プログラムがあることを検出し、ユーザーのインストールをアップグレードします。古いアセンブリを更新するのに、カスタム プログラミングは必要ありません。  
  
#### ClickOnce アプリケーションの配置に関するヘルプ  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] の完全な概要については、「[ClickOnce のセキュリティと配置](../Topic/ClickOnce%20Security%20and%20Deployment.md)」を参照してください。  これらの機能を使用する方法の手順を追った説明については、次のヘルプ トピックを参照してください。  
  
|説明|ヘルプ トピック|  
|--------|--------------|  
|[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] を使用してアプリケーションを配置する|[方法: 発行ウィザードを使用して ClickOnce アプリケーションを発行する](../Topic/How%20to:%20Publish%20a%20ClickOnce%20Application%20using%20the%20Publish%20Wizard.md)<br /><br /> [チュートリアル : ClickOnce アプリケーションを手動で配置する](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)|  
|[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] の配置を更新する|[方法 : ClickOnce アプリケーションの更新プログラムを管理する](../Topic/How%20to:%20Manage%20Updates%20for%20a%20ClickOnce%20Application.md)|  
|[!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] を使用してセキュリティを管理する|[方法 : ClickOnce のセキュリティ設定を有効にする](../Topic/How%20to:%20Enable%20ClickOnce%20Security%20Settings.md)|  
  
### その他のコントロールおよび機能  
 Windows フォームには、ダイアログ ボックスの作成、ヘルプやドキュメントの印刷や追加、アプリケーションの複数言語へのローカライズのサポートなど、一般的なタスクを高速で簡単に実装できる機能が他にも多数あります。  さらに、Windows フォームは、[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] の堅牢なセキュリティ システムを利用しています。  このシステムを使用することで、顧客により安全なアプリケーションをリリースできます。  
  
#### その他のコントロールや機能の実装に関するヘルプ  
 これらの機能を使用する方法の手順を追った説明については、次のヘルプ トピックを参照してください。  
  
|説明|ヘルプ トピック|  
|--------|--------------|  
|フォームの内容を印刷する|[方法 : Windows フォームでグラフィックスを印刷する](../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [方法 : Windows フォームで複数ページのテキスト ファイルを印刷する](../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|  
|Windows フォームのセキュリティについての詳細|[Windows フォームのセキュリティの概要](../../../docs/framework/winforms/security-in-windows-forms-overview.md)|  
  
## 参照  
 [Windows フォームについて](../../../docs/framework/winforms/getting-started-with-windows-forms.md)   
 [新しい Windows フォームの作成](../../../docs/framework/winforms/creating-a-new-windows-form.md)   
 [ToolStrip コントロールの概要](../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [DataGridView コントロールの概要](../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [BindingSource コンポーネントの概要](../../../docs/framework/winforms/controls/bindingsource-component-overview.md)   
 [アプリケーション設定の概要](../../../docs/framework/winforms/advanced/application-settings-overview.md)   
 [ClickOnce のセキュリティと配置](../Topic/ClickOnce%20Security%20and%20Deployment.md)