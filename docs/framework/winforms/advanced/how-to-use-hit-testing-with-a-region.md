---
title: '方法: ヒット テストをリージョンと使用'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 1866810b875063271e206da1fe5d6fc06f7b5de0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564306"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>方法: ヒット テストをリージョンと使用
ヒット テストの目的では、アイコンやボタンなどの特定のオブジェクトの上にカーソルがかどうかを決定します。  
  
## <a name="example"></a>例  
 次の例では、2 つの四角形領域の和集合を形成して十字型の領域を作成します。 ある変数`point`最新のクリックの位置を保持します。 コードを調べますかどうか`point`十字型の領域にします。 ポイントは、リージョン (ヒット) では場合、は、非透過の赤いブラシで領域が入力されます。 それ以外の場合、領域は、半透明の赤いブラシで塗りつぶされます。  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventHandler> のパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Drawing.Region>
- [GDI+ での領域](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)
- [方法: クリッピング領域を使用します。](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)
