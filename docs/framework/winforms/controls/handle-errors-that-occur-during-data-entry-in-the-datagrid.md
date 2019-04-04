---
title: '方法: Windows フォームの DataGridView コントロールでのデータ入力中に発生したエラーを処理します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 57b4591dcca42ec1e864115239a6acc61e4de609
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723999"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="007c9-102">方法: Windows フォームの DataGridView コントロールでのデータ入力中に発生したエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="007c9-102">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="007c9-103">次のコード例をは、データ エントリ エラーをユーザーに報告する <xref:System.Windows.Forms.DataGridView> コントロールの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="007c9-103">The following code example demonstrates how to use the <xref:System.Windows.Forms.DataGridView> control to report data entry errors to the user.</span></span>  
  
 <span data-ttu-id="007c9-104">このコード例の詳細については、次を参照してください。[チュートリアル。フォームの DataGridView コントロールを Windows でのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="007c9-104">For a complete explanation of this code example, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="007c9-105">例</span><span class="sxs-lookup"><span data-stu-id="007c9-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="007c9-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="007c9-106">Compiling the Code</span></span>  
 <span data-ttu-id="007c9-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="007c9-107">This example requires:</span></span>  
  
-   <span data-ttu-id="007c9-108">System、System.Data、System.Windows.Forms、および System.XML の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="007c9-108">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="007c9-109">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、[、コマンドラインからビルドする](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007c9-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="007c9-110">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="007c9-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="007c9-111">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="007c9-111">.NET Framework Security</span></span>  
 <span data-ttu-id="007c9-112">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="007c9-112">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="007c9-113">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="007c9-113">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="007c9-114">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007c9-114">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007c9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="007c9-115">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="007c9-116">チュートリアル: Windows フォームの DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="007c9-116">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="007c9-117">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="007c9-117">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="007c9-118">チュートリアル: Windows フォームの DataGridView コントロールのデータの検証</span><span class="sxs-lookup"><span data-stu-id="007c9-118">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="007c9-119">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="007c9-119">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
