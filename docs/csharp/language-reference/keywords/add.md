---
title: add (C# リファレンス)
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: b55827b60a89da2569fad9da135c84571a24b094
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43390969"
---
# <a name="add-c-reference"></a>add (C# リファレンス)
`add` コンテキスト キーワードは、カスタム イベント アクセサーを定義するときに使用されます。このアクセサーは、クライアント コードが[イベント](../../../csharp/language-reference/keywords/event.md)をサブスクライブするときに呼び出されます。 カスタムの `add` アクセサーを指定するときは、[remove](../../../csharp/language-reference/keywords/remove.md) アクセサーも指定する必要があります。  
  
## <a name="example"></a>例  
 次の例は、カスタムの `add` アクセサーと [remove](../../../csharp/language-reference/keywords/remove.md) アクセサーが指定されているイベントを示しています。 サンプル全体については、「[方法: インターフェイス イベントを実装する](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)」を参照してください。  
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 通常は、独自のカスタム イベント アクセサーを提供する必要はありません。 イベントを宣言するときにコンパイラで自動生成されるアクセサーは、ほとんどのシナリオで利用することができます。  
  
## <a name="see-also"></a>参照  
- [イベント](../../../csharp/programming-guide/events/index.md)
