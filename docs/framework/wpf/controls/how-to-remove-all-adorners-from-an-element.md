---
title: "方法 : 要素からすべての装飾を削除する"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0f7bb16c2cd641579706609ff14ca16cc57bd620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>方法 : 要素からすべての装飾を削除する
この例は、プログラムから、指定したすべての装飾を削除する方法を示しています。<xref:System.Windows.UIElement>です。  
  
## <a name="example"></a>例  
 この詳細なコード例はすべての装飾によって返される装飾の配列に<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>です。  この例の発生時に装飾を取得する、<xref:System.Windows.UIElement>という*myTextBox*です。  呼び出しで、要素が指定されている場合<xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>、装飾を持たない`null`が返されます。  このコードは明示的に null 配列をチェックしが、null 配列は比較的一般的である必要なアプリケーションに最適です。  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>例  
 この圧縮されたコード例は、機能的には、上記の詳細な例です。 このコードに明示的に確認しません null 配列の場合は、可能であればを<xref:System.NullReferenceException>例外が発生する可能性があります。  このコードが、null 配列はまれである必要なアプリケーションに最適です。  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>参照  
 [装飾の概要](../../../../docs/framework/wpf/controls/adorners-overview.md)
