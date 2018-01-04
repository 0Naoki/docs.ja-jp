---
title: "Windows フォーム DataGridView コントロールでのパフォーマンス チューニング"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da0171bf4fa056de2dd06c2f7e431ea55a8dab1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Windows フォーム DataGridView コントロールでのパフォーマンス チューニング
大量のデータを使用するときに、`DataGridView`コントロールが大量のオーバーヘッドが、メモリを使用できるは、慎重に使用する場合を除き、します。 メモリの制限とのクライアントではメモリ消費の多い機能を回避することでこのオーバーヘッドの一部を回避できます。 データ メンテナンスの一部またはすべてを管理することもでき、シナリオでは、メモリ使用量をカスタマイズするために仮想モードを使用して自分でタスクを取得します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Windows フォーム DataGridView コントロールを拡張するための推奨される手順](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 使用する方法について説明します、`DataGridView`大量のデータを操作するときに、不要なメモリの使用状況とパフォーマンスの低下を回避する方法で制御します。  
  
 [Windows フォーム DataGridView コントロールでの仮想モード](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 仮想モードを使用して補完したり、標準的なデータ バインディング機構を置換する方法について説明します。  
  
 [チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 複数の仮想モード イベントのハンドラーを実装する方法について説明します。 行レベルのロールバックとユーザーを編集するためのコミットを実装する方法も示します。  
  
 [Windows フォーム DataGridView コントロールでの Just-In-Time データ読み込みによる仮想モードの実装](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 必要に応じて、使用可能なクライアントのメモリを格納できるよりもを表示する複数のデータがある場合に有用なデータを読み込む方法について説明します。  
  
## <a name="reference"></a>参照  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView> コントロールのリファレンス ドキュメントを提供します。  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 リファレンス ドキュメントを提供、<xref:System.Windows.Forms.DataGridView.VirtualMode%2A>プロパティです。  
  
## <a name="see-also"></a>参照  
 [DataGridView コントロール](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Windows フォーム DataGridView コントロールでのデータ表示モード](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
