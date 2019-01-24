---
title: 型の値&#39; &lt;typename1&gt; &#39;に変換できない&#39; &lt;typename2&gt; &#39; (複数ファイル参照)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 943b9612a9217b90c19f34285e812c4e1cccf81a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691374"
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="92f53-102">型の値&#39; &lt;typename1&gt; &#39;に変換できない&#39; &lt;typename2&gt; &#39; (複数ファイル参照)</span><span class="sxs-lookup"><span data-stu-id="92f53-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="92f53-103">型の値 '\<typename1 >' に変換できません。'\<typename2 >'。</span><span class="sxs-lookup"><span data-stu-id="92f53-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="92f53-104">型の不一致がへの参照をファイルの混合によって生じた可能性があります '\<filepath1 >' プロジェクトで'\<projectname1 >' への参照をファイルに '\<filepath2 >' プロジェクトで'\<projectname2 >'。</span><span class="sxs-lookup"><span data-stu-id="92f53-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="92f53-105">両方のアセンブリが同一である場合は、これらの参照を同じ場所から参照するように置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="92f53-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="92f53-106">プロジェクト アセンブリへの 1 つ以上のファイル参照は、場所の状況で、コンパイラは別に 1 つの型を変換できることを保証することはできません。</span><span class="sxs-lookup"><span data-stu-id="92f53-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="92f53-107">それぞれのファイル参照は、ファイルのパスとプロジェクト (通常は DLL ファイル) の出力ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="92f53-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="92f53-108">コンパイラは、出力ファイルが、同じソースから取得することや、同じアセンブリの同じバージョンを表すことが保証できません。</span><span class="sxs-lookup"><span data-stu-id="92f53-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="92f53-109">そのため、別の参照の型は、同じ型でまたは他にも、あるを変換できることを保証ができません。</span><span class="sxs-lookup"><span data-stu-id="92f53-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="92f53-110">参照されたアセンブリが同じアセンブリ id を持つことがわかっている場合は、1 つのファイルの参照を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92f53-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="92f53-111">*アセンブリ ID* には、アセンブリの名前、バージョン、公開キー (存在する場合)、およびカルチャが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92f53-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="92f53-112">この情報はアセンブリを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="92f53-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="92f53-113">**エラー ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="92f53-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92f53-114">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="92f53-114">To correct this error</span></span>  
  
-   <span data-ttu-id="92f53-115">参照先アセンブリのアセンブリ id が同じ場合は、削除するか置き換えるファイルの参照のいずれか 1 つのファイル参照のみがあります。</span><span class="sxs-lookup"><span data-stu-id="92f53-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="92f53-116">参照されたアセンブリは、同じアセンブリ id を持っていない場合、それ以外の型を 1 つの型を変換しませんようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="92f53-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f53-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="92f53-117">See also</span></span>
- [<span data-ttu-id="92f53-118">Visual Basic における型変換</span><span class="sxs-lookup"><span data-stu-id="92f53-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="92f53-119">プロジェクト内の参照の管理</span><span class="sxs-lookup"><span data-stu-id="92f53-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)

