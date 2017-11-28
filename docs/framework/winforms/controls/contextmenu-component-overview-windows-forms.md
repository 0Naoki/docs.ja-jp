---
title: "ContextMenu コンポーネントの概要 (Windows フォーム)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6c2542ca7ee27bec96bb5010bcdb2fcd7416f72
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="contextmenu-component-overview-windows-forms"></a>ContextMenu コンポーネントの概要 (Windows フォーム)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.MenuStrip>と<xref:System.Windows.Forms.ContextMenuStrip>交換し、する機能を追加、<xref:System.Windows.Forms.MainMenu>と<xref:System.Windows.Forms.ContextMenu>以前のバージョンでのコントロール<xref:System.Windows.Forms.MainMenu>と<xref:System.Windows.Forms.ContextMenu>を選択した場合、旧バージョンとの互換性と将来の使用の両方に保持されます。  
  
 Windows フォームで<xref:System.Windows.Forms.ContextMenu>コンポーネント、選択したオブジェクトに関連付けられている頻繁に使用されるコマンドを簡単にアクセスできるショートカット メニューをユーザーに提供できます。 ショートカット メニューの項目は、多くの場合、アプリケーションでの場所に表示されるメイン メニューの項目のサブセットです。 ユーザーは、マウスを右クリックしてショートカット メニューを通常アクセスできます。 Windows フォームでは、ショートカット メニューは、コントロールに関連付けられます。  
  
## <a name="key-properties"></a>主要プロパティ  
 コントロールにするには、コントロールのショートカット メニューを関連付けることができます<xref:System.Windows.Forms.Control.ContextMenu%2A>プロパティを<xref:System.Windows.Forms.ContextMenu>コンポーネントです。 1 つのショートカット メニューは、複数のコントロールを関連付けることができますが、各コントロールが 1 つだけのショートカット メニューを持つことができます。  
  
 キー プロパティ、<xref:System.Windows.Forms.ContextMenu>コンポーネントは、<xref:System.Windows.Forms.Menu.MenuItems%2A>プロパティです。 メニュー項目を追加するにはプログラムで作成することで<xref:System.Windows.Forms.MenuItem>オブジェクトとに追加すること、<xref:System.Windows.Forms.Menu.MenuItemCollection>のショートカット メニュー。 ショートカット メニューの項目は通常、その他のメニューから描画、ためにをコピーしてショートカット メニューに項目を最も頻繁に追加します。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
