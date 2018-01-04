---
title: "方法 : インストールされているフォントを列挙する"
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
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905b5ecbda58d2f7edb7fc30d5505eec63a64c2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a>方法 : インストールされているフォントを列挙する
<xref:System.Drawing.Text.InstalledFontCollection>クラスから継承、<xref:System.Drawing.Text.FontCollection>抽象基本クラスです。 使用することができます、<xref:System.Drawing.Text.InstalledFontCollection>コンピューターにインストールされているフォントを列挙するオブジェクト。 <xref:System.Drawing.Text.FontCollection.Families%2A>のプロパティ、<xref:System.Drawing.Text.InstalledFontCollection>オブジェクトの配列は、<xref:System.Drawing.FontFamily>オブジェクト。  
  
## <a name="example"></a>例  
 次の例では、コンピューターにインストールされているすべてのフォント ファミリの名前が一覧表示します。 コードを取得、<xref:System.Drawing.FontFamily.Name%2A>の各プロパティ<xref:System.Drawing.FontFamily>によって返される配列内のオブジェクト、<xref:System.Drawing.Text.FontCollection.Families%2A>プロパティです。 ファミリ名を取得するには、フォーム、コンマで区切られたリストに連結されます。 続いて、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>クラスは、四角形のコンマ区切りのリストを描画します。  
  
 コード例を実行する場合、出力が次の図に示すようになります。  
  
 ![インストール済みフォント](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventHandler> のパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。 さらに、インポートする必要があります、<xref:System.Drawing.Text>名前空間。  
  
## <a name="see-also"></a>参照  
 [フォントとテキストの使用](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
