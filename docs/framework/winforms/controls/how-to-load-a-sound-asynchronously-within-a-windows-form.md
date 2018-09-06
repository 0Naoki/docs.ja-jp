---
title: '方法 : Windows フォーム内でサウンドを非同期的に読み込む'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 2de2be478e81183201cc85e1a6dfd6f1a1833af6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858279"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="212ad-102">方法 : Windows フォーム内でサウンドを非同期的に読み込む</span><span class="sxs-lookup"><span data-stu-id="212ad-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="212ad-103">次のコード例では、URL からサウンドを非同期的に読み込み、新しいスレッド上で再生します。</span><span class="sxs-lookup"><span data-stu-id="212ad-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="212ad-104">例</span><span class="sxs-lookup"><span data-stu-id="212ad-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="212ad-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="212ad-105">Compiling the Code</span></span>  
 <span data-ttu-id="212ad-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="212ad-106">This example requires:</span></span>  
  
-   <span data-ttu-id="212ad-107">System アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="212ad-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="212ad-108">ファイル名 `"http://www.tailspintoys.com/sounds/stop.wav"` を有効なファイル名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="212ad-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="212ad-109">コマンドラインからこの例を Visual Basic または Visual c# の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。</span><span class="sxs-lookup"><span data-stu-id="212ad-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="212ad-110">新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="212ad-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="212ad-111">「[方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="212ad-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="212ad-112">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="212ad-112">Robust Programming</span></span>  
 <span data-ttu-id="212ad-113">ファイルの操作は、適切な例外処理ブロックで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="212ad-113">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="212ad-114">次の条件を満たす場合は、例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="212ad-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="212ad-115">パス名が不適切である場合。</span><span class="sxs-lookup"><span data-stu-id="212ad-115">The path name is malformed.</span></span> <span data-ttu-id="212ad-116">たとえば、無効な文字が含まれている場合や、空白だけの場合などです (<xref:System.ArgumentException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="212ad-116">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="212ad-117">パスが読み取り専用である場合 (<xref:System.IO.IOException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="212ad-117">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="212ad-118">パス名が `Nothing` である場合 (<xref:System.ArgumentNullException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="212ad-118">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="212ad-119">パス名が長すぎる場合 (<xref:System.IO.PathTooLongException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="212ad-119">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="212ad-120">パスが有効でない場合 (<xref:System.IO.DirectoryNotFoundException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="212ad-120">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="212ad-121">パスがコロン ":" のみである場合 (<xref:System.NotSupportedException> クラス)。</span><span class="sxs-lookup"><span data-stu-id="212ad-121">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="212ad-122">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="212ad-122">.NET Framework Security</span></span>  
 <span data-ttu-id="212ad-123">ファイル名からファイルの内容を判断しないでください。</span><span class="sxs-lookup"><span data-stu-id="212ad-123">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="212ad-124">たとえば、`Form1.vb` というファイルは Visual Basic のソース ファイルではない可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="212ad-124">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="212ad-125">アプリケーションでデータを使用する前に、入力をすべて検証してください。</span><span class="sxs-lookup"><span data-stu-id="212ad-125">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212ad-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="212ad-126">See Also</span></span>  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <xref:System.Media.SoundPlayer.LoadCompleted>  
 <xref:System.Media.SoundPlayer.Play%2A>  
 [<span data-ttu-id="212ad-127">方法: Windows フォームからサウンドを再生する</span><span class="sxs-lookup"><span data-stu-id="212ad-127">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
