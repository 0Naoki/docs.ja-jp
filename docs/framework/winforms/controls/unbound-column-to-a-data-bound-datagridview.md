---
title: '方法 : データバインドされた Windows フォーム DataGridView コントロールに非バインド列を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 39c637fe30ed852f7d6e9fa7a1dbbfa72af9e4b4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466070"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>方法 : データバインドされた Windows フォーム DataGridView コントロールに非バインド列を追加する
<xref:System.Windows.Forms.DataGridView> コントロールに表示するデータは、通常なんらかのデータ ソースから取得されるデータですが、データ ソース以外からのデータの列を表示する必要が生じることがあります。 この種類の列は、非バインド列と呼ばれます。 非バインド列の形式はさまざまです。 しばしば、データ行の詳細へのアクセスに使用されます。  
  
 次のコード例のバインドされていない列を作成する方法を示します**詳細**マスター/詳細シナリオを実装するときに親テーブルで特定の行に関連する子テーブルを表示するボタン。 ボタンのクリックに応答するには、子テーブルを含むフォームを表示する <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> イベント ハンドラーを実装します。  
  
 Visual Studio では、このタスクに対するサポートが用意されています。  参照してください[方法: 追加して、Windows フォーム DataGridView コントロールを使用して、デザイナーで列を削除](https://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))  
  
## <a name="example"></a>例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。  
  
-   <xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.DataGridView>  
 [Windows フォーム DataGridView コントロールでのデータの表示](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Windows フォーム DataGridView コントロールでのデータ表示モード](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
