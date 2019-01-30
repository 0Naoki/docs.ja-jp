---
title: 属性 '<attributename>' を複数回適用することはできません。
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: 62e84d174e4e218472eda9b7c08ed677e0140438
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278708"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a>属性 '\<attributename >' 複数回適用できません
属性は、1 回のみ適用できます。 `AttributeUsage`属性が属性を複数回適用できるかどうかを決定します。  
  
 **エラー ID:** BC30663  
  
## <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  属性は 1 回のみ適用することを確認します。  
  
2.  開発したカスタム属性を使用している場合は、変更することを検討してください、`AttributeUsage`の次の例と同じ複数の属性の使用を許可する属性。  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a>関連項目
- <xref:System.AttributeUsageAttribute>
- [カスタム属性の作成](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [AttributeUsage](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
