---
title: -main
ms.date: 03/13/2018
helpviewer_keywords:
- main compiler option [Visual Basic]
- /main compiler option [Visual Basic]
- -main compiler option [Visual Basic]
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
ms.openlocfilehash: d1676cea520c42a40082e31cce9de9797b06e9ee
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814043"
---
# <a name="-main"></a><span data-ttu-id="1acb4-102">-main</span><span class="sxs-lookup"><span data-stu-id="1acb4-102">-main</span></span>
<span data-ttu-id="1acb4-103">`Sub Main` プロシージャを格納するクラスまたはモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1acb4-103">Specifies the class or module that contains the `Sub Main` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1acb4-104">構文</span><span class="sxs-lookup"><span data-stu-id="1acb4-104">Syntax</span></span>  
  
```  
-main:location  
```  
  
## <a name="arguments"></a><span data-ttu-id="1acb4-105">引数</span><span class="sxs-lookup"><span data-stu-id="1acb4-105">Arguments</span></span>  
 `location`  
 <span data-ttu-id="1acb4-106">必須。</span><span class="sxs-lookup"><span data-stu-id="1acb4-106">Required.</span></span> <span data-ttu-id="1acb4-107">クラスまたはを含むモジュールの名前、`Sub Main`プログラムの開始時に呼び出されるプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="1acb4-107">The name of the class or module that contains the `Sub Main` procedure to be called when the program starts.</span></span> <span data-ttu-id="1acb4-108">フォームのことが考えられます **-メイン: モジュール**または **-main:namespace.module**します。</span><span class="sxs-lookup"><span data-stu-id="1acb4-108">This may be in the form **-main:module** or **-main:namespace.module**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1acb4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="1acb4-109">Remarks</span></span>  
 <span data-ttu-id="1acb4-110">実行可能ファイルまたは Windows 実行可能プログラムを作成するときに、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="1acb4-110">Use this option when you create an executable file or Windows executable program.</span></span> <span data-ttu-id="1acb4-111">場合、 **-メイン**オプションを省略すると、コンパイラは、有効な共有の検索`Sub Main`ですべてのパブリック クラスとモジュール。</span><span class="sxs-lookup"><span data-stu-id="1acb4-111">If the **-main** option is omitted, the compiler searches for a valid shared `Sub Main` in all public classes and modules.</span></span>  
  
 <span data-ttu-id="1acb4-112">参照してください[Visual Basic の Main プロシージャ](../../../visual-basic/programming-guide/program-structure/main-procedure.md)のさまざまな形式の詳細については、`Main`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="1acb4-112">See [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) for a discussion of the various forms of the `Main` procedure.</span></span>  
  
 <span data-ttu-id="1acb4-113">ときに`location`から継承するクラスは、 <xref:System.Windows.Forms.Form>、コンパイラは、既定値を用意`Main`クラスにない場合に、アプリケーションを開始するプロシージャ`Main`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="1acb4-113">When `location` is a class that inherits from <xref:System.Windows.Forms.Form>, the compiler provides a default `Main` procedure that starts the application if the class has no `Main` procedure.</span></span> <span data-ttu-id="1acb4-114">これにより、開発環境で作成したコマンドラインでコードをコンパイルできます。</span><span class="sxs-lookup"><span data-stu-id="1acb4-114">This lets you compile code at the command line that was created in the development environment.</span></span>  
  
 [!code-vb[VbVbalrCompiler#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#16)]  
  
### <a name="to-set--main-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="1acb4-115">設定 - Visual Studio 統合開発環境で主に</span><span class="sxs-lookup"><span data-stu-id="1acb4-115">To set -main in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="1acb4-116">**ソリューション エクスプローラー**でプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="1acb4-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1acb4-117">**[プロジェクト]** メニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1acb4-117">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="1acb4-118">**[アプリケーション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1acb4-118">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="1acb4-119">確認、**アプリケーション フレームワークを有効にする**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="1acb4-119">Make sure the **Enable application framework** check box is not checked.</span></span>  
  
4.  <span data-ttu-id="1acb4-120">値を変更、**スタートアップ オブジェクト**ボックス。</span><span class="sxs-lookup"><span data-stu-id="1acb4-120">Modify the value in the **Startup object** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1acb4-121">例</span><span class="sxs-lookup"><span data-stu-id="1acb4-121">Example</span></span>  
 <span data-ttu-id="1acb4-122">次のコードのコンパイル`T2.vb`と`T3.vb`を指定している、`Sub Main`手順が記載されて、`Test2`クラス。</span><span class="sxs-lookup"><span data-stu-id="1acb4-122">The following code compiles `T2.vb` and `T3.vb`, specifying that the `Sub Main` procedure will be found in the `Test2` class.</span></span>  
  
```console
vbc t2.vb t3.vb -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="1acb4-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="1acb4-123">See also</span></span>

- [<span data-ttu-id="1acb4-124">Visual Basic のコマンド ライン コンパイラ</span><span class="sxs-lookup"><span data-stu-id="1acb4-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1acb4-125">-ターゲット (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1acb4-125">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="1acb4-126">コンパイル コマンド ラインのサンプル</span><span class="sxs-lookup"><span data-stu-id="1acb4-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="1acb4-127">Visual Basic の main プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1acb4-127">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
