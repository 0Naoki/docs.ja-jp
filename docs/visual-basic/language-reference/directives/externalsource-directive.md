---
title: '#ExternalSource ディレクティブ (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: 39e6963c97340daab3f0ab7ad6860695f1f6c135
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823429"
---
# <a name="externalsource-directive"></a><span data-ttu-id="3e51d-102">#ExternalSource ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="3e51d-102">#ExternalSource Directive</span></span>
<span data-ttu-id="3e51d-103">ソース コードの特定の行とソース外部のテキスト間のマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="3e51d-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e51d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e51d-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="3e51d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="3e51d-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="3e51d-106">外部ソースへのパス。</span><span class="sxs-lookup"><span data-stu-id="3e51d-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="3e51d-107">外部ソースの最初の行の行番号。</span><span class="sxs-lookup"><span data-stu-id="3e51d-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="3e51d-108">行を外部ソースでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e51d-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="3e51d-109">`#ExternalSource` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="3e51d-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e51d-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e51d-110">Remarks</span></span>  
 <span data-ttu-id="3e51d-111">このディレクティブは、コンパイラと、デバッガーでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e51d-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="3e51d-112">ソース ファイルには、ソース ファイル内のコードの特定の行と、.aspx ファイルなど、ソースの外部のテキスト間のマッピングを示す外部ソース ディレクティブを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3e51d-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="3e51d-113">指定されたソース コードでは、コンパイル中にエラーが発生する場合は、外部ソースからのものとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="3e51d-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="3e51d-114">外部ソース ディレクティブは、コンパイルに影響を与えるありませんし、入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3e51d-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="3e51d-115">内部使用のアプリケーションのみが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3e51d-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e51d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e51d-116">See also</span></span>

- [<span data-ttu-id="3e51d-117">条件付きコンパイル</span><span class="sxs-lookup"><span data-stu-id="3e51d-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
