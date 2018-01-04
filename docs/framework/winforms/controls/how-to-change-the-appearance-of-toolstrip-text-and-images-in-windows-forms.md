---
title: "方法 : Windows フォーム内の ToolStrip テキストとイメージの外観を変更する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe88ff8d31a83b8516b11cd9aadd4bc2d4bf99a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>方法 : Windows フォーム内の ToolStrip テキストとイメージの外観を変更する
テキストとイメージを表示するかどうかを制御することができます、<xref:System.Windows.Forms.ToolStripItem>互いを基準としての配置方法と、<xref:System.Windows.Forms.ToolStrip>です。  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>ToolStripItem 上に表示される内容を定義するには  
  
-   設定、<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>プロパティを目的の値にします。 表示される値は`Image`、 `ImageAndText`、 `None`、および`Text`です。 既定値は、`ImageAndText` です。  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>ToolStripItem 上のテキストを整列するには  
  
-   設定、<xref:System.Windows.Forms.ToolStripItem.TextAlign%2A>プロパティを目的の値にします。 表示される値は top、中間色、および左、中央、右と一番下の任意の組み合わせです。 既定値は、`MiddleCenter` です。  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>ToolStripItem 上の画像を整列するには  
  
-   設定、<xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>プロパティを目的の値にします。 表示される値は top、中間色、および左、中央、右と一番下の任意の組み合わせです。 既定値は、`MiddleLeft` です。  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>互いを基準として ToolStripItem テキストとイメージを表示する方法を定義するには  
  
-   設定、<xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>プロパティを目的の値にします。 表示される値は`ImageAboveText`、 `ImageBeforeText`、 `Overlay`、 `TextAboveImage`、および`TextBeforeImage`です。 既定値は、`ImageBeforeText` です。  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.ToolStrip>  
 [ToolStrip コントロールの概要](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip コントロールのアーキテクチャ](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip テクノロジの概要](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
