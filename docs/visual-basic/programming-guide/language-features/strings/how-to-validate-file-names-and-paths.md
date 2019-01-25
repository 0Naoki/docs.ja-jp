---
title: '方法: ファイル名と Visual Basic でのパスを検証します。'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c0d39ecbaf9ca23c72e45b8839d268fbc38fe48e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648451"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="8f19e-102">方法: ファイル名と Visual Basic でのパスを検証します。</span><span class="sxs-lookup"><span data-stu-id="8f19e-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="8f19e-103">この例を返します、`Boolean`文字列が、ファイル名またはパスを表すかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="8f19e-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="8f19e-104">ファイル システムで許可されていない文字が名前に含まれるかどうか、検証を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f19e-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f19e-105">例</span><span class="sxs-lookup"><span data-stu-id="8f19e-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 <span data-ttu-id="8f19e-106">この例では、名前が正常に配置され、コロン、またはディレクトリ名がない場合、または名前の長さがシステム定義の最大長を超える場合はチェックしません。</span><span class="sxs-lookup"><span data-stu-id="8f19e-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="8f19e-107">チェックされません、アプリケーションが、指定した名前のファイル システム リソースにアクセスする権限を持つかどうかです。</span><span class="sxs-lookup"><span data-stu-id="8f19e-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f19e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f19e-108">See also</span></span>
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="8f19e-109">Visual Basic における文字列の検証</span><span class="sxs-lookup"><span data-stu-id="8f19e-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
