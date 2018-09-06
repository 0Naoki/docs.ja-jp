---
title: '方法 : Windows フォームの境界線を変更する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: e04234b4f2f18738567c3f9846d8ae0c94780fcb
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788221"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>方法 : Windows フォームの境界線を変更する
Windows フォームの外観や動作を決定する際にはさまざまな境界線スタイルを選択できます。 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> プロパティを変更して、フォームのサイズ変更動作を制御できます。 また、<xref:System.Windows.Forms.Form.FormBorderStyle%2A> を設定すると、キャプション バーの表示方法や、キャプション バーに表示されるボタンを変更できます。 詳細については、「<xref:System.Windows.Forms.FormBorderStyle>」を参照してください。  
  
 Visual Studio では、このタスクに対する広範なサポートが用意されています。  
  
 参照してください[方法: デザイナーを使用して Windows フォームの境界線を変更](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\))します。  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>プログラムで Windows フォームの境界線スタイルを設定するには  
  
-   <xref:System.Windows.Forms.Form.FormBorderStyle%2A> プロパティを任意のスタイルに設定します。 次のコード例は、フォームの境界線スタイルを設定`DlgBx1`に<xref:System.Windows.Forms.FormBorderStyle.FixedDialog>します。  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     参照してください[方法: デザイン時にダイアログ ボックスの作成](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))です。  
  
     さらに、オプションを提供するフォームの境界線スタイルを選択したかどうか**最小化**と**最大化**ボタン、機能するためにこれらのボタンの一方または両方をするかどうか指定できます。 これらのボタンは、ユーザーの操作感を細かく調節する場合に便利です。 **最小化**と**最大化**ボタンが既定で有効になってし、その機能を使用して操作は、**プロパティ**ウィンドウ。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [Windows フォームについて](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
