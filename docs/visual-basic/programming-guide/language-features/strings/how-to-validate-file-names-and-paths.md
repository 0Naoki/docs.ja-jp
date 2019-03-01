---
title: '方法: ファイル名と Visual Basic でのパスを検証します。'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: d29553071d68319d754406b3104da6e096f908fd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975525"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="895d6-102">方法: ファイル名と Visual Basic でのパスを検証します。</span><span class="sxs-lookup"><span data-stu-id="895d6-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="895d6-103">この例を返します、`Boolean`文字列が、ファイル名またはパスを表すかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="895d6-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="895d6-104">ファイル システムで許可されていない文字が名前に含まれるかどうか、検証を確認します。</span><span class="sxs-lookup"><span data-stu-id="895d6-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="895d6-105">例</span><span class="sxs-lookup"><span data-stu-id="895d6-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="895d6-106">この例では、名前が正常に配置され、コロン、またはディレクトリ名がない場合、または名前の長さがシステム定義の最大長を超える場合はチェックしません。</span><span class="sxs-lookup"><span data-stu-id="895d6-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="895d6-107">チェックされません、アプリケーションが、指定した名前のファイル システム リソースにアクセスする権限を持つかどうかです。</span><span class="sxs-lookup"><span data-stu-id="895d6-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="895d6-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="895d6-108">See also</span></span>
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="895d6-109">Visual Basic における文字列の検証</span><span class="sxs-lookup"><span data-stu-id="895d6-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
