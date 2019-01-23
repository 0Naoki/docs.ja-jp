---
title: '方法: 内在コントロールのプロパティを公開します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: f3ad37032ee2bb85f37a0eb754277cc9bc040a38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532163"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>方法: 内在コントロールのプロパティを公開します。
複合コントロールを構成するコントロールが呼び出される*内在コントロール*します。 これらのコントロールは通常プライベートで宣言されており、そのため、開発者がアクセスできません。 今後のユーザーにこれらのコントロールのプロパティを使用できるようにする場合は、ユーザーに公開する必要があります。 ユーザー コントロールでプロパティを作成して使用内在コントロールのプロパティを公開、`get`と`set`内在コントロールのプライベート プロパティの変更を有効にするためのプロパティのアクセサー。  
  
 という名前の構成要素であるボタンで仮想的なユーザー コントロールを検討してください`MyButton`します。 ユーザーが要求したときに、この例では、`ConstituentButtonBackColor`プロパティに格納された値、<xref:System.Windows.Forms.Control.BackColor%2A>プロパティの`MyButton`配信されます。 その値が自動的に渡される、ユーザーは、このプロパティに値を割り当てます、ときに、<xref:System.Windows.Forms.Control.BackColor%2A>プロパティの`MyButton`と`set`の色を変更する、コードが実行されます`MyButton`。  
  
 次の例では、公開する方法を示しています、<xref:System.Windows.Forms.Control.BackColor%2A>構成ボタンのプロパティ。  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### <a name="to-expose-a-property-of-a-constituent-control"></a>内在コントロールのプロパティを公開するには  
  
1.  ユーザー コントロールのパブリック プロパティを作成します。  
  
2.  `get`セクションのプロパティを公開するプロパティの値を取得するコードを記述します。  
  
3.  `set`セクションのプロパティ、プロパティの値を公開されている、内在コントロールのプロパティに渡されるコードを記述します。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.UserControl>
- [Windows フォーム コントロールのプロパティ](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
- [さまざまなカスタム コントロール](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
