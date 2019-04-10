---
title: 属性 '<attributename>' を複数回適用することはできません。
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: da4a766e2617308cb33b9673a88db9e7a954152a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304299"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="fa6ba-102">属性 '\<attributename >' 複数回適用できません</span><span class="sxs-lookup"><span data-stu-id="fa6ba-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>
<span data-ttu-id="fa6ba-103">属性は、1 回のみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="fa6ba-103">The attribute can only be applied once.</span></span> <span data-ttu-id="fa6ba-104">`AttributeUsage`属性が属性を複数回適用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fa6ba-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="fa6ba-105">**エラー ID:** BC30663</span><span class="sxs-lookup"><span data-stu-id="fa6ba-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa6ba-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="fa6ba-106">To correct this error</span></span>  
  
1. <span data-ttu-id="fa6ba-107">属性は 1 回のみ適用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa6ba-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="fa6ba-108">開発したカスタム属性を使用している場合は、変更することを検討してください、`AttributeUsage`の次の例と同じ複数の属性の使用を許可する属性。</span><span class="sxs-lookup"><span data-stu-id="fa6ba-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa6ba-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa6ba-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="fa6ba-110">カスタム属性の作成</span><span class="sxs-lookup"><span data-stu-id="fa6ba-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="fa6ba-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="fa6ba-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
