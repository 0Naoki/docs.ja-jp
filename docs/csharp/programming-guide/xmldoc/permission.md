---
title: '&lt;permission&gt; (C# プログラミング ガイド)'
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 1447541f7e093a7cf434702368bdce0d07c4908b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43861596"
---
# <a name="ltpermissiongt-c-programming-guide"></a>&lt;permission&gt; (C# プログラミング ガイド)
## <a name="syntax"></a>構文  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>パラメーター  
 cref = "`member`"  
 現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。 コンパイラは、指定されたコード要素が存在し、出力の XML で `member` が正規要素名に変換されることを確認します。 *member* は、二重引用符 (" ") で囲む必要があります。  
  
 ジェネリック型への cref 参照を作成する方法については、「[\<see>](../../../csharp/programming-guide/xmldoc/see.md)」を参照してください。  
  
 `description`  
 メンバーへのアクセスの説明です。  
  
## <a name="remarks"></a>コメント  
 \<permission> タグを使用すると、メンバーのアクセスを文書化できます。 <xref:System.Security.PermissionSet> クラスを使用すると、メンバーへのアクセスを指定できます。  
  
 コンパイル時に [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
## <a name="example"></a>例  
 [!code-csharp[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## <a name="see-also"></a>参照

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)  
- [ドキュメント コメントとして推奨されるタグ](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
