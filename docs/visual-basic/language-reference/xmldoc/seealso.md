---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 0231ff748949874f4b477cac15d891d313b25f4f
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524650"
---
# <a name="seealso-visual-basic"></a>\<seealso > (Visual Basic)
「関連項目」セクションに表示されるリンクを指定します。  
  
## <a name="syntax"></a>構文  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a>パラメーター  
 `member`  
 現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。 コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力 XML 内の要素名に渡します。 `member` は、二重引用符 (" ") で囲む必要があります。  
  
## <a name="remarks"></a>Remarks  
 @No__t_0 タグを使用して、「関連項目」セクションに表示するテキストを指定します。 [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) タグを使用すると、テキスト内からリンクを指定できます。  
  
 コンパイル時に [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
## <a name="example"></a>例  
 この例では、`DoesRecordExist` 解説セクションの `<seealso>` タグを使用して、`UpdateRecord` メソッドを参照します。  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>関連項目

- [XML のコメント用タグ](../../../visual-basic/language-reference/xmldoc/index.md)
