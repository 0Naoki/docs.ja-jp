---
title: '方法: インターフェイス メンバーを明示的に実装する - C# プログラミング ガイド'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 064061b44cca3adb5dde89ecc71fb1f8ea3abf8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562905"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>方法: インターフェイス メンバーを明示的に実装する (C# プログラミング ガイド)
この例では[インターフェイス](../../../csharp/language-reference/keywords/interface.md)、`IDimensions`、およびクラス `Box` を宣言します。これは、インターフェイス メンバーの `getLength` と `getWidth` を明示的に実装します。 メンバーには、インターフェイス インスタンス `dimensions` を介してアクセスします。  
  
## <a name="example"></a>例  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
  
-   `Main` メソッドでは、次の行はコメントアウトされます。これらの行でコンパイル エラーが発生するためです。 明示的に実装されるインターフェイス メンバーに、[クラス](../../../csharp/language-reference/keywords/class.md) インスタンスからアクセスすることはできません。  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   `Main` メソッドの以下の行では、メソッドがインターフェイスのインスタンスから呼び出されるため、ボックスのサイズを正常に出力できます。  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)
- [クラスと構造体](../../../csharp/programming-guide/classes-and-structs/index.md)
- [インターフェイス](../../../csharp/programming-guide/interfaces/index.md)
- [方法: 2 つのインターフェイスのメンバーを明示的に実装する](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
