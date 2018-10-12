---
title: '方法: 子タスクがその親にアタッチしないようにする'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 234a8de8ed9f4e403d932c01728ab9ffbc72ad14
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44214850"
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>方法: 子タスクがその親にアタッチしないようにする
このドキュメントでは、子タスクが親タスクにアタッチしないようにする方法を紹介します。 サード パーティによって書き込まれ、タスクも使用するコンポーネントを呼び出す場合は、子タスクがその親にアタッチしないようにすると便利です。 たとえば、<xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> オプションを使用して <xref:System.Threading.Tasks.Task> または <xref:System.Threading.Tasks.Task%601> オブジェクトを作成するサード パーティ コンポーネントが長時間実行されているか、ハンドルされない例外をスローする場合、コードで問題が発生する可能性があります。  
  
## <a name="example"></a>例  
 次の例では、子タスクが親にアタッチしないようにする効果と、既定のオプションを使用する効果を比較します。 この例では、<xref:System.Threading.Tasks.Task> オブジェクトも使用する、サード パーティ ライブラリを呼び出す、<xref:System.Threading.Tasks.Task> オブジェクトを作成します。 サード パーティ ライブラリでは <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> オプションを使用して、<xref:System.Threading.Tasks.Task> オブジェクトを作成します。 アプリケーションでは <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> オプションを使用して、親タスクを作成します。 このオプションは、子タスクの <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> 指定を削除するようにランタイムに指示します。  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 親タスクはすべての子タスクが終了するまで終了しないため、長時間実行される子タスクによって、アプリケーション全体のパフォーマンスが低下する場合があります。 この例では、アプリケーションが既定のオプションを使用して親タスクを作成する場合に、親タスクが終了する前に子タスクが終了する必要があります。 アプリケーションで <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> オプションを使用する場合、子は親にアタッチされません。 そのため、アプリケーションは、親タスクの終了後、子タスクが終了するのを待機する前に、追加の作業を実行できます。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`DenyChildAttach.cs` (Visual Basic では `DenyChildAttach.vb`) という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 Visual C#  
  
 **csc.exe DenyChildAttach.cs**  
  
 Visual Basic  
  
 **vbc.exe DenyChildAttach.vb**  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
  
## <a name="see-also"></a>関連項目

- [タスク ベースの非同期プログラミング](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
