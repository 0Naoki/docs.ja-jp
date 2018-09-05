---
title: 'チュートリアル : ステータス バー情報の実行時更新'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
ms.openlocfilehash: 49722d5dadf694e8ee3037646652b921ddda3e91
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542604"
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>チュートリアル : ステータス バー情報の実行時更新
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip>と<xref:System.Windows.Forms.ToolStripStatusLabel>コントロールの置換し、する機能を追加、<xref:System.Windows.Forms.StatusBar>と<xref:System.Windows.Forms.StatusBarPanel>を制御しますただし、、<xref:System.Windows.Forms.StatusBar>と<xref:System.Windows.Forms.StatusBarPanel>場合、下位互換性と将来の使用の両方のコントロールが保持されますします。選択します。  
  
 多くの場合、アプリケーションの状態の変化や他のユーザー操作に基づいて、ステータス バー パネルの内容を実行時に動的に更新する必要があります。 これは、CapsLock、NumLock、ScrollLock などのキーが有効化されたことをユーザーに通知したり、便利な情報として日付や時刻を表示したりするための一般的な方法です。  
  
 次の例では、インスタンスを使用して、<xref:System.Windows.Forms.StatusBarPanel>クラス時計をホストします。  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>ステータス バーを更新できる状態にするには  
  
1.  新しい Windows フォームを作成します。  
  
2.  フォームに <xref:System.Windows.Forms.StatusBar> コントロールを追加します。 詳細については、「[方法 : Windows フォームにコントロールを追加する](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)」を参照してください。  
  
3.  ステータス バー パネルを追加、<xref:System.Windows.Forms.StatusBar>コントロール。 詳細については、「[方法 : StatusBar コントロールにパネルを追加する](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)」を参照してください。  
  
4.  <xref:System.Windows.Forms.StatusBar>をフォームに追加されたコントロールの設定、<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>プロパティを`true`します。  
  
5.  Windows フォームの追加<xref:System.Windows.Forms.Timer>コンポーネントをフォームにします。  
  
    > [!NOTE]
    >  Windows フォーム<xref:System.Windows.Forms.Timer?displayProperty=nameWithType>コンポーネントが Windows フォーム環境向けに設計されています。 サーバー環境に適したタイマーが必要な場合は、「[サーバー ベースのタイマーの概要](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)」を参照してください。  
  
6.  <xref:System.Windows.Forms.Timer.Enabled%2A> プロパティを `true` に設定します。  
  
7.  設定、<xref:System.Windows.Forms.Timer.Interval%2A>のプロパティ、<xref:System.Windows.Forms.Timer>を 30000 に設定します。  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.Timer.Interval%2A>のプロパティ、<xref:System.Windows.Forms.Timer>部分が表示される時刻に正確な時刻が反映されることを確認に 30 秒 (30,000 ミリ秒) に設定します。  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>タイマーを実装してステータス バーを更新するには  
  
1.  イベント ハンドラーに次のコードを挿入、<xref:System.Windows.Forms.Timer>のパネルを更新するコンポーネント、<xref:System.Windows.Forms.StatusBar>コントロール。  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     この時点で、アプリケーションを実行して、ステータス バー パネルで実行される時計を確認できる状態になります。  
  
### <a name="to-test-the-application"></a>アプリケーションをテストするには  
  
1.  アプリケーションをデバッグし、F5 キーを押してアプリケーションを実行します。 デバッグの詳細については、「[Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)」を参照してください。  
  
    > [!NOTE]
    >  ステータス バーに時計が表示されるまでに約 30 秒かかります。 これは、できるだけ正確な時刻を取得するためです。 逆に表示するにクロックをするためを減らせるの値、<xref:System.Windows.Forms.Timer.Interval%2A>前の手順では、手順 7. で設定するプロパティ。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [方法: StatusBar コントロールにパネルを追加する](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [方法: Windows フォームの StatusBar コントロールでクリックされたパネルを確認する](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [StatusBar コントロールの概要](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
