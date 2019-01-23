---
title: '方法: 読み取り専用の Freezable の書き込み可能なコピーを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 2853b1e02e1223cbb2b6dff4acbddb0a41d882cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629957"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a>方法: 読み取り専用の Freezable の書き込み可能なコピーを取得する
この例は、使用する方法を示します、<xref:System.Windows.Freezable.Clone%2A>読み取り専用の書き込み可能なコピーを作成するメソッドを<xref:System.Windows.Freezable>します。  
  
 後に、<xref:System.Windows.Freezable>オブジェクトがマークされている読み取り専用 (「固定」)、として、それを変更できません。 ただし、使用することができます、<xref:System.Windows.Freezable.Clone%2A>固定されたオブジェクトの変更可能な複製を作成します。  
  
## <a name="example"></a>例  
 次の例は、固定の変更可能な複製を作成<xref:System.Windows.Media.SolidColorBrush>オブジェクト。  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 詳細については<xref:System.Windows.Freezable>、オブジェクトを参照してください、 [Freezable オブジェクトの概要](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)します。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [Freezable オブジェクトの概要](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [方法トピック](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
