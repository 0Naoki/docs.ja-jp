---
title: Visual Basic でのプロジェクトのカスタマイズと My の拡張
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: 4dfe14f7680ad0c3a302334c07bb17e3e92011b0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534557"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="90fb0-102">Visual Basic でのプロジェクトのカスタマイズと My の拡張</span><span class="sxs-lookup"><span data-stu-id="90fb0-102">Customizing Projects and Extending My with Visual Basic</span></span>
<span data-ttu-id="90fb0-103">追加するためにプロジェクト テンプレートをカスタマイズする`My`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="90fb0-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="90fb0-104">これにより、簡単に検索して、オブジェクトを使用するには、他の開発者。</span><span class="sxs-lookup"><span data-stu-id="90fb0-104">This makes it easy for other developers to find and use your objects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90fb0-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="90fb0-105">In This Section</span></span>  
 [<span data-ttu-id="90fb0-106">Visual Basic における My 名前空間の拡張</span><span class="sxs-lookup"><span data-stu-id="90fb0-106">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)  
 <span data-ttu-id="90fb0-107">カスタム メンバーを追加する方法について説明し、値を`My`Visual Basic における名前空間。</span><span class="sxs-lookup"><span data-stu-id="90fb0-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>  
  
 [<span data-ttu-id="90fb0-108">カスタム My 拡張のパッケージ化と配置</span><span class="sxs-lookup"><span data-stu-id="90fb0-108">Packaging and Deploying Custom My Extensions</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="90fb0-109">ユーザー設定を発行する方法について説明します`My`Visual Studio テンプレートを使用して名前空間の拡張機能。</span><span class="sxs-lookup"><span data-stu-id="90fb0-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>  
  
 [<span data-ttu-id="90fb0-110">Visual Basic アプリケーション モデルの拡張</span><span class="sxs-lookup"><span data-stu-id="90fb0-110">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="90fb0-111">メンバーをオーバーライドすることで、アプリケーション モデルを独自の拡張機能を指定する方法について説明します、<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>クラス。</span><span class="sxs-lookup"><span data-stu-id="90fb0-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>  
  
 [<span data-ttu-id="90fb0-112">My で利用可能なオブジェクトのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="90fb0-112">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="90fb0-113">これを制御する方法について説明します`My`オブジェクトは、プロジェクトの _MYTYPE の条件付きコンパイル定数を設定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="90fb0-113">Describes how to control which `My` objects are enabled by setting your project's _MYTYPE conditional-compilation constant.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="90fb0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="90fb0-114">Related Sections</span></span>  
 [<span data-ttu-id="90fb0-115">My による開発</span><span class="sxs-lookup"><span data-stu-id="90fb0-115">Development with My</span></span>](../../../visual-basic/developing-apps/development-with-my/index.md)  
 <span data-ttu-id="90fb0-116">これについて説明します`My`オブジェクトは既定で種類のプロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="90fb0-116">Describes which `My` objects are available in different project types by default.</span></span>  
  
 [<span data-ttu-id="90fb0-117">Visual Basic アプリケーション モデルの概要</span><span class="sxs-lookup"><span data-stu-id="90fb0-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="90fb0-118">Windows フォーム アプリケーションの動作を制御するための Visual Basic のモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="90fb0-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="90fb0-119">プロジェクトの種類に応じた My の機能</span><span class="sxs-lookup"><span data-stu-id="90fb0-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="90fb0-120">これについて説明します`My`オブジェクトは既定で種類のプロジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="90fb0-120">Describes which `My` objects are available in different project types by default.</span></span>  
  
 [<span data-ttu-id="90fb0-121">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="90fb0-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="90fb0-122">コンパイラが条件付きコンパイルを使用して、コードをコンパイルし、その他のセクションを除外する特定のセクションを選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90fb0-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>  
  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="90fb0-123">について説明します、`My`プロパティ、メソッド、およびイベントを提供するオブジェクトが現在のアプリケーションに関連します。</span><span class="sxs-lookup"><span data-stu-id="90fb0-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90fb0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="90fb0-124">See Also</span></span>  
 [<span data-ttu-id="90fb0-125">Visual Basic でのアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="90fb0-125">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
