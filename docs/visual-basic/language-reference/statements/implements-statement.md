---
title: Implements ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 805813506b957afb326c71ee4bbb15837726e4e5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253144"
---
# <a name="implements-statement"></a>Implements ステートメント
1 つ以上のインターフェイス、またはインターフェイス メンバーの場合、クラスで実装する必要がありますまたはが表示される構造体の定義を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>指定項目  
 `interfacename`  
 必須。 プロパティ、プロシージャ、およびイベントのクラスまたは構造体に対応するメンバーを実装するインターフェイス。  
  
 `interfacemember`  
 必須。 実装されているインターフェイスのメンバー。  
  
## <a name="remarks"></a>Remarks  
 インターフェイスは、コレクション メンバー (プロパティ、プロシージャ、およびイベント) を表すプロトタイプのインターフェイスをカプセル化します。 インターフェイスにメンバーの宣言のみを含めるクラスと構造体は、これらのメンバーを実装します。 詳細については、「[インターフェイス](../../../visual-basic/programming-guide/language-features/interfaces/index.md)」を参照してください。  
  
 `Implements`ステートメントの直後にする必要があります、`Class`または`Structure`ステートメント。  
  
 インターフェイスを実装する場合は、インターフェイスで宣言されているすべてのメンバーを実装する必要があります。 任意のメンバーを省略すると、構文エラーであると見なされます。 指定した個々 のメンバーを実装するために、[実装](../../../visual-basic/language-reference/statements/implements-clause.md)キーワード (これとは別、`Implements`ステートメント) クラスまたは構造体のメンバーを宣言する場合。 詳細については、「[インターフェイス](../../../visual-basic/programming-guide/language-features/interfaces/index.md)」を参照してください。  
  
 クラスを使用する[プライベート](../../../visual-basic/language-reference/modifiers/private.md)プロパティと手順については、これらのメンバーの実装は、インターフェイスの型の変数に実装するクラスのインスタンスが宣言されているキャストによってのみアクセスできます。  
  
## <a name="example"></a>例  
 次の例は、使用する方法を示します、`Implements`インターフェイスのメンバーを実装するステートメント。 という名前のインターフェイスを定義`ICustomerInfo`イベント、プロパティ、およびプロシージャを使用します。 クラスは、`customerInfo`インターフェイスで定義されているすべてのメンバーを実装します。  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 なお、クラス`customerInfo`を使用して、`Implements`クラスのすべてのメンバーを実装することを示す別のソース コード行のステートメントで、`ICustomerInfo`インターフェイス。 クラス内の各メンバーを使用して、`Implements`をそのインターフェイスのメンバーを実装することを示すために、メンバー宣言の一部としてキーワード。  
  
## <a name="example"></a>例  
 次の 2 つの手順では、前の例で実装されたインターフェイスを使用する方法を示しています。 実装をテストするには、呼び出しをプロジェクトにこれらの手順を追加、`testImplements`プロシージャ。  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a>関連項目  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [Interface ステートメント](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [インターフェイス](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
