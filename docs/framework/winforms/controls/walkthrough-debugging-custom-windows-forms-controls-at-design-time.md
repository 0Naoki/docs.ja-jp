---
title: 'チュートリアル : カスタム Windows フォーム コントロールのデザイン時のデバッグ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: 824c1e47cf50dc13a3a986e48a49158b15dbb935
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2018
ms.locfileid: "43455732"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a>チュートリアル : カスタム Windows フォーム コントロールのデザイン時のデバッグ
カスタム コントロールを作成するときに多くの場合、表示されますが、デザイン時の動作をデバッグするために必要です。 これは、カスタム コントロールのカスタム デザイナーを作成する場合に特に当てはまります。 詳細については、次を参照してください。[チュートリアル: 作成、Windows フォーム コントロールを受け取るの Visual Studio デザイン時機能を利用](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)します。  
  
 その他の .NET Framework のクラスをデバッグする場合と同様に、Visual Studio を使用して、カスタム コントロールをデバッグできます。 違いは、カスタム コントロールのコードを実行している Visual Studio の別のインスタンスをデバッグすることです。  
  
 このチュートリアルでは、以下のタスクを行います。  
  
-   カスタム コントロールをホストする Windows フォーム プロジェクトを作成します。  
  
-   コントロール ライブラリ プロジェクトを作成します。  
  
-   カスタム コントロールにプロパティを追加  
  
-   ホストのフォームにカスタム コントロールを追加します。  
  
-   デザイン時のデバッグ プロジェクトの設定  
  
-   カスタム コントロールをデザイン時のデバッグ  
  
 完了したら、カスタム コントロールのデザイン時の動作をデバッグするために必要な作業について理解があります。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。  
  
## <a name="creating-the-project"></a>プロジェクトの作成  
 最初の手順では、アプリケーション プロジェクトを作成します。 このプロジェクトを使用すると、カスタム コントロールをホストするアプリケーションをビルドします。  
  
#### <a name="to-create-the-project"></a>プロジェクトを作成するには  
  
-   "DebuggingExample"と呼ばれる Windows アプリケーション プロジェクトを作成 (**ファイル** > **新規** > **プロジェクト** >  **Visual c#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォーム アプリケーション**)。  
  
## <a name="creating-a-control-library-project"></a>コントロール ライブラリ プロジェクトを作成します。  
 次の手順では、コントロール ライブラリ プロジェクトを作成し、カスタム コントロールを設定します。  
  
#### <a name="to-create-the-control-library-project"></a>コントロール ライブラリ プロジェクトを作成するには  
  
1.  追加、 **Windows コントロール ライブラリ**プロジェクトがソリューションにします。  
  
2.  新しい追加**UserControl** DebugControlLibrary プロジェクトに項目。 詳細については、次を参照してください。 [NIB: 方法: 新しいプロジェクト項目の追加](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)します。 新しいソース ファイルに「タブ」の基本の名前を付けます。  
  
3.  使用して、**ソリューション エクスプ ローラー**の基本名を持つコード ファイルを削除することによって、プロジェクトの既定のコントロールを削除"`UserControl1`"。 詳細については、次を参照してください。 [NIB: 方法: 削除、削除、および除外項目](https://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)します。  
  
4.  ソリューションをビルドします。  
  
## <a name="checkpoint"></a>チェックポイント  
 この時点では、ことができますでカスタム コントロールを表示する、**ツールボックス**します。  
  
#### <a name="to-check-your-progress"></a>進行状況をチェックするには  
  
-   という新しいタブを見つけます**DebugControlLibrary コンポーネント** をクリックして選択します。 開くときに、コントロールが表示されます**タブ**の横にある既定のアイコン。  
  
## <a name="adding-a-property-to-your-custom-control"></a>カスタム コントロールにプロパティを追加  
 デザイン時にカスタム コントロールのコードが実行されていることを示すためは、プロパティを追加し、プロパティを実装するコードにブレークポイントを設定します。  
  
#### <a name="to-add-a-property-to-your-custom-control"></a>カスタム コントロールにプロパティを追加するには  
  
1.  開いている**タブ**で、**コード エディター**します。 クラス定義には、次のコードを追加します。  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  ソリューションをビルドします。  
  
## <a name="adding-your-custom-control-to-the-host-form"></a>ホストのフォームにカスタム コントロールを追加します。  
 カスタム コントロールのデザイン時の動作をデバッグするには、ホストのフォームにカスタム コントロール クラスのインスタンスを配置します。  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a>ホストのフォームにカスタム コントロールを追加するには  
  
1.  "DebuggingExample"プロジェクトで、Form1 を開き、 **Windows フォーム デザイナー**します。  
  
2.  **ツールボックス**、オープン、 **DebugControlLibrary コンポーネント**タブし、ドラッグ、**タブ**フォーム上にインスタンス。  
  
3.  検索、`DemoString`にカスタム プロパティ、**プロパティ**ウィンドウ。 他のプロパティと同様、その値を変更できますに注意してください。 場合にも注意してください、`DemoString`プロパティが選択されている場合の下部にあるプロパティの説明文字列が表示されます、**プロパティ**ウィンドウ。  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a>デザイン時のデバッグ プロジェクトの設定  
 カスタム コントロールのデザイン時の動作をデバッグするには、カスタム コントロールのコードを実行している Visual Studio の別のインスタンスをデバッグします。  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a>デザイン時のデバッグ プロジェクトを設定するには  
  
1.  右クリックし、 **DebugControlLibrary**プロジェクト、**ソリューション エクスプ ローラー**選択**プロパティ**します。  
  
2.  **DebugControlLibrary**プロパティ シート、**デバッグ**タブ。  
  
     **開始動作**セクションで、**外部プログラムの開始**します。 されますので、省略記号をクリックして、Visual Studio の別のインスタンスをデバッグ (![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))、Visual Studio IDE を参照するボタンをクリックします。 実行可能ファイルの名前は**devenv.exe**、され、パスは %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe で既定の場所にインストールした場合。  
  
3.  **[OK]** をクリックしてダイアログ ボックスを閉じます。  
  
4.  右クリックし、 **DebugControlLibrary**順に選択して**スタートアップ プロジェクトとして設定**このデバッグ構成を有効にします。  
  
## <a name="debugging-your-custom-control-at-design-time"></a>カスタム コントロールをデザイン時のデバッグ  
 デザイン モードで実行するときに、カスタム コントロールをデバッグする準備が整いました。 デバッグ セッションを開始して、Visual Studio の新しいインスタンスを作成は"DebuggingExample"ソリューションの読み込みに使用します。 Form1 を開くと、**フォーム デザイナー**、カスタム コントロールのインスタンスが作成され、実行が開始されます。  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a>デザイン時に、カスタム コントロールをデバッグするには  
  
1.  開く、**タブ**内のソース ファイル、**コード エディター**にブレークポイントを配置し、`Set`のアクセサー、`DemoString`プロパティ。  
  
2.  F5 キーを押して、デバッグ セッションを開始します。 Visual Studio の新しいインスタンスが作成されたことに注意してください。 2 つの方法でインスタンスを区別することができます。  
  
    -   デバッグ インスタンスが、word**を実行している**のタイトル バーに  
  
    -   デバッグ インスタンスが、**開始**のボタンではその**デバッグ**ツールバーを無効になっています  
  
     デバッグ インスタンスで、ブレークポイントが設定されます。  
  
3.  Visual Studio の新しいインスタンスでは、"DebuggingExample"ソリューションを開きます。 選択して、ソリューションを簡単に見つけることができます**最近使ったプロジェクト**から、**ファイル**メニュー。 "DebuggingExample.sln"ソリューション ファイルは、最近使用したファイルとして表示されます。  
  
4.  Form1 を開き、**フォーム デザイナー**を選択し、**タブ**コントロール。  
  
5.  値を変更、`DemoString`プロパティ。 変更をコミットするときに、Visual Studio のデバッグ インスタンスがフォーカスを取得し、実行がブレークポイントで停止に注意してください。 プロパティ アクセサーを 1 ステップを実行できますと同様、その他のコードには。  
  
6.  Visual Studio のホスト インスタンスを閉じるか、クリックして終了する、デバッグ セッションがしたら、**デバッグの停止**デバッグ インスタンスでボタンをクリックします。  
  
## <a name="next-steps"></a>次の手順  
 これで、カスタム コントロールをデバッグするにはデザイン時に、Visual Studio IDE とコントロールの相互作用を拡張するためのさまざまな操作があります。  
  
-   使用することができます、<xref:System.ComponentModel.Component.DesignMode%2A>のプロパティ、<xref:System.ComponentModel.Component>クラスはデザイン時にのみ実行するコードを記述します。 詳細については、「<xref:System.ComponentModel.Component.DesignMode%2A>」を参照してください。  
  
-   いくつかの属性があるデザイナーを使用したカスタム コントロールの相互作用を操作するコントロールのプロパティに適用することができます。 これらの属性を見つけることができます、<xref:System.ComponentModel?displayProperty=nameWithType>名前空間。  
  
-   カスタム コントロールのカスタム デザイナーを記述できます。 これにより、Visual Studio によって公開される拡張可能なデザイナー インフラストラクチャを使用して、デザイン エクスペリエンスを完全に制御できるようにします。 詳細については、次を参照してください。[チュートリアル: 作成、Windows フォーム コントロールを受け取るの Visual Studio デザイン時機能を利用](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)します。  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [方法: デザイン時サービスにアクセス](https://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [方法: Windows フォームでデザイン時サポートにアクセスする](https://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
