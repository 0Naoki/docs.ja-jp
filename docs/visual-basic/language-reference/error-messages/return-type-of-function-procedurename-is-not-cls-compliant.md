---
title: 関数 '<procedurename>' の戻り値の型は CLS に準拠していません。
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: 5e746981d10ba8e662aebf86f67f08856ba37199
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013740"
---
# <a name="return-type-of-function-procedurename-is-not-cls-compliant"></a><span data-ttu-id="2c4a2-102">関数の型を返す '\<procedurename >' は CLS 準拠</span><span class="sxs-lookup"><span data-stu-id="2c4a2-102">Return type of function '\<procedurename>' is not CLS-compliant</span></span>
<span data-ttu-id="2c4a2-103">A`Function`プロシージャがマーク`<CLSCompliant(True)>`としてマークされている型を返しますが、 `<CLSCompliant(False)>`、マークされていない、または非準拠の型であるためには修飾されません。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="2c4a2-104">プロシージャを[言語への非依存性および言語非依存コンポーネント](../../../standard/language-independence-and-language-independent-components.md) (CLS) に準拠させるには、CLS 準拠型のみを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="2c4a2-105">これは、パラメーターの型、戻り値の型、およびすべてのローカル変数の型に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="2c4a2-106">次の Visual Basic データ型は CLS 準拠ではありません。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="2c4a2-107">SByte データ型</span><span class="sxs-lookup"><span data-stu-id="2c4a2-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="2c4a2-108">UInteger データ型</span><span class="sxs-lookup"><span data-stu-id="2c4a2-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="2c4a2-109">ULong データ型</span><span class="sxs-lookup"><span data-stu-id="2c4a2-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="2c4a2-110">UShort データ型</span><span class="sxs-lookup"><span data-stu-id="2c4a2-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="2c4a2-111">プログラミング要素に <xref:System.CLSCompliantAttribute> を適用する場合は、準拠または非準拠を示すために、属性の `isCompliant` パラメーターを `True` または `False` のどちらかに設定します。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="2c4a2-112">このパラメーターには既定値がありません。値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="2c4a2-113">要素に <xref:System.CLSCompliantAttribute> を適用しないと、その要素は非準拠と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="2c4a2-114">既定では、このメッセージは警告です。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-114">By default, this message is a warning.</span></span> <span data-ttu-id="2c4a2-115">警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](/visualstudio/ide/configuring-warnings-in-visual-basic)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="2c4a2-116">**エラー ID:** BC40027</span><span class="sxs-lookup"><span data-stu-id="2c4a2-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2c4a2-117">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="2c4a2-117">To correct this error</span></span>  
  
- <span data-ttu-id="2c4a2-118">場合、`Function`プロシージャがこの特定の型を返す、削除する必要があります、<xref:System.CLSCompliantAttribute>します。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="2c4a2-119">プロシージャは CLS 準拠になりません。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="2c4a2-120">場合、`Function`プロシージャが CLS に準拠する、最も近い CLS 準拠型に戻り値の型を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="2c4a2-121">たとえば、2,147,483,647 を超える値の範囲が不要な場合は、 `UInteger` の代わりに `Integer` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="2c4a2-122">拡張範囲が必要な場合は、 `UInteger` の代わりに `Long`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="2c4a2-123">オートメーション オブジェクトや COM オブジェクトとやり取りする場合は、一部の型のデータ幅が [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] とは異なることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="2c4a2-124">たとえば、他の多くの環境では `int` は 16 ビットです。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="2c4a2-125">このようなコンポーネントに 16 ビット整数を返す場合は宣言として`Short`の代わりに`Integer`管理対象の Visual Basic コードです。</span><span class="sxs-lookup"><span data-stu-id="2c4a2-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>