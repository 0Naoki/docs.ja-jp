---
title: '方法: BindingSource で Windows フォーム コントロール内のデータ ソースの更新が反映されます。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: fca356c258b482a9f4e4fd64f48801de428f8426
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260830"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a>方法: BindingSource で Windows フォーム コントロール内のデータ ソースの更新が反映されます。
データ バインド コントロールを使用する場合、データ ソースがリスト変更イベントを発生させないことがあります。そのようなケースで、データ ソース内の変更に応答する必要が生じることがあります。 
  <xref:System.Windows.Forms.BindingSource> コンポーネントを使用してデータ ソースを Windows フォーム コントロールにバインドすれば、データ ソースが変更されたことを <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> メソッドを呼び出すことによってコントロールに通知できます。  
  
## <a name="example"></a>例  
 次のコード例では、バインドされたコントロールにデータ ソース内の更新について <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> メソッドを使用して通知する方法を示します。  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。  
  
 コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。 新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。  
  
## <a name="see-also"></a>関連項目
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingSource コンポーネント](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Windows フォーム コントロールを型にバインドします。](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
