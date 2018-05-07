---
title: "Windows フォーム DataGridView コントロールの既定の機能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecb8cdaa4e8eb0498259c597e0de3f80c3106549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールの既定の機能
Windows フォーム<xref:System.Windows.Forms.DataGridView>コントロールは多くの既定の機能をユーザーに提供します。
  
## <a name="default-functionality"></a>既定の機能  
<xref:System.Windows.Forms.DataGridView> コントロールは、既定で次のような機能を持ちます:

-   テーブルを垂直方向にスクロールしても列ヘッダーおよび行ヘッダーが見える状態のまま自動的に表示します。
  
-   現在の行を示す選択を含む行ヘッダーがあります。
  
-   最初のセルに選択を示す四角形があります。
  
-   自動的にサイズを変更できるユーザーが列の区分線をダブルクリックすると、列があります。  
  
-   Windows XP および Windows Server 2003 ファミリで visual スタイルを自動的にサポートされるときに、<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>メソッドは、アプリケーションから`Main`メソッドです。  
  
さらに、<xref:System.Windows.Forms.DataGridView>コントロールの内容は既定で編集できます:
  
-   ユーザーがダブルクリックするか、セル中で F2 キーを押した場合、コントロールは自動的にセルを編集モードにし、ユーザーが入力したセルの内容を更新します。
  
-   ユーザーは、グリッドの最後にスクロールする場合、新しいレコードを追加するための行が存在するユーザーが表示されます。 新しい行を追加、ユーザーは、この行をクリックすると、<xref:System.Windows.Forms.DataGridView>コントロールは、既定値を使用します。 ユーザーは、esc キーを押すと、この新しい行は表示されなくなります。  
  
-   ユーザーには、行ヘッダーがクリックすると、行全体が選択されます。  
  
<xref:System.Windows.Forms.DataGridView.DataSource%2A> プロパティの設定から <xref:System.Windows.Forms.DataGridView> コントロールをデータ ソースにバインドしたとき、コントロールは次のように振る舞います:

-   列ヘッダーのテキストとしてデータ ソースの列の名前が自動的に使用します。  
  
-   データ ソースの内容が格納されます。 <xref:System.Windows.Forms.DataGridView>列は、データ ソース内の各列に対して自動的に作成されます。  
  
-   テーブルに 1 行ごとに表示される行のデータを作成します。  
  
-   自動的にユーザーが列見出しをクリックしたときに、基になるデータに基づく行を並べ替えます。  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView コントロール](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
