---
title: C# のキーワード
ms.date: 03/07/2017
f1_keywords:
- cs.keywords
helpviewer_keywords:
- keywords [C#]
- C# language, keywords
- Visual C#, keywords
- '@ keyword'
ms.assetid: e929b0f2-4b92-4d37-8060-23d323b098ad
ms.openlocfilehash: 2bdaa2f4cdb19d01948effd599177f68859cb82c
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291058"
---
# <a name="c-keywords"></a>C# のキーワード

キーワードは、コンパイラで特別な意味を持つ、事前に定義されている予約済みの識別子です。 キーワードは、プレフィックスとして `@` を含めない限り、プログラムで識別子として使用できません。 たとえば、`@if` は有効な識別子ですが、`if` は違います。これは、`if` がキーワードだからです。  
  
 このトピックの最初の表では、C# プログラムの予約済み識別子であるキーワードの一覧を示します。 2 番目の表では、C# のコンテキスト キーワードの一覧を示します。 コンテキスト キーワードは、プログラムの限定されたコンテキストでのみ特別な意味を持つもので、そのコンテキストの外部では識別子として使用することができます。 一般に、C# 言語に新しいキーワードが追加されると、それらはコンテキスト キーワードとして追加されます。これは、以前のバージョンで記述されたプログラムの破損を防ぐためです。  
  
|||||  
|---|---|---|---|  
|[abstract](abstract.md)|[as](../operators/type-testing-and-cast.md#as-operator)|[base](base.md)|[bool](bool.md)|  
|[break](break.md)|[byte](../builtin-types/integral-numeric-types.md)|[case](switch.md)|[catch](try-catch.md)|  
|[char](char.md)|[checked](checked.md)|[class](class.md)|[const](const.md)|  
|[continue](continue.md)|[decimal](../builtin-types/floating-point-numeric-types.md)|[default](default.md)|[delegate](delegate.md)|  
|[do](do.md)|[double](../builtin-types/floating-point-numeric-types.md)|[else](if-else.md)|[enum](enum.md)|  
|[event](event.md)|[explicit](../operators/user-defined-conversion-operators.md)|[extern](extern.md)|[false](false-literal.md)|  
|[finally](try-finally.md)|[fixed](fixed-statement.md)|[float](../builtin-types/floating-point-numeric-types.md)|[for](for.md)|  
|[foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[implicit](../operators/user-defined-conversion-operators.md)|  
|[in](in.md)|[int](../builtin-types/integral-numeric-types.md)|[interface](interface.md)|[internal](internal.md)|
|[is](is.md)|[lock](lock-statement.md)|[long](../builtin-types/integral-numeric-types.md)|[namespace](namespace.md)|
|[new](../operators/new-operator.md)|[null](null.md)|[object](object.md)|[operator](../operators/operator-overloading.md)|
|[out](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[sbyte](../builtin-types/integral-numeric-types.md)|[sealed](sealed.md)|[short](../builtin-types/integral-numeric-types.md)||
[sizeof](../operators/sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[string](string.md)|
|[struct](struct.md)|[switch](switch.md)|[this](this.md)|[throw](throw.md)|
|[true](true-literal.md)|[try](try-catch.md)|[typeof](../operators/type-testing-and-cast.md#typeof-operator)|[uint](../builtin-types/integral-numeric-types.md)|
|[ulong](../builtin-types/integral-numeric-types.md)|[unchecked](unchecked.md)|[unsafe](unsafe.md)|[ushort](../builtin-types/integral-numeric-types.md)|
|[using](using.md)|[using static](using-static.md)|[virtual](virtual.md)|[void](void.md)|
|[volatile](volatile.md)|[while](while.md)|

## <a name="contextual-keywords"></a>コンテキスト キーワード

 コンテキスト キーワードを使用して、コード内で特定の意味を付与することができます。ただし C# ではコンテキスト キーワードは予約語ではありません。 `partial` や `where` など、2 つ以上のコンテキストで特別な意味を持つコンテキスト キーワードもあります。  
  
||||  
|---|---|---|  
|[add](add.md)|[alias](extern-alias.md)|[ascending](ascending.md)|
|[async](async.md)|[await](../operators/await.md)|[by](by.md)|
|[descending](descending.md)|[dynamic](dynamic.md)|[equals](equals.md)|
|[from](from-clause.md)|[get](get.md)|[global](../operators/namespace-alias-qualifier.md)|
|[group](group-clause.md)|[into](into.md)|[join](join-clause.md)|
|[let](let-clause.md)|[nameof](../operators/nameof.md)|[on](on.md)|
|[orderby](orderby-clause.md)|[partial (型)](partial-type.md)|[partial (メソッド)](partial-method.md)|
|[remove](remove.md)|[select](select-clause.md)|[set](set.md)|
|[unmanaged (ジェネリック型制約)](where-generic-type-constraint.md)|[value](value.md)|[var](var.md)|
|[when (フィルター条件)](when.md)|[where (ジェネリック型制約)](where-generic-type-constraint.md)|[where (クエリ句)](where-clause.md)|
|[yield](yield.md)| | |
  
## <a name="see-also"></a>関連項目

- [C# リファレンス](../index.md)
