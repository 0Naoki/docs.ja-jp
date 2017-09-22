---
title: "Blittable 型と非 Blittable 型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 23
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3fa97ee1df14b5e08faa944265675264c0b6d95a
ms.contentlocale: ja-jp
ms.lasthandoff: 08/21/2017

---
# <a name="blittable-and-non-blittable-types"></a>Blittable 型と非 Blittable 型
ほとんどのデータ型の表現はマネージ メモリとアンマネージ メモリの両方で共通しているため、相互運用マーシャラーによる特別な処理は必要ありません。 これらの型は、マネージ コードとアンマネージ コード間での受け渡しの際に変換が必要でないため、*blittable 型*と呼ばれます。  
  
 プラットフォーム呼び出しから返される構造体は blittable 型である必要があります。 プラットフォーム呼び出しでは、戻り値の型として非 blittable 型の構造体はサポートされません。  
  
 <xref:System> 名前空間に属する次の型は blittable 型です。  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 次の複合型も blittable 型です。  
  
-   整数の配列など、blittable 型の 1 次元配列。 ただし、blittable 型の可変配列を含む型自体は blittable ではありません。  
  
-   blittable 型だけを含む、書式設定された値型 (および、それらが書式設定された型としてマーシャリングされる場合はクラス)。 書式設定された値型の詳細については、「[Default Marshaling for Value Types](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a)」(値型に対する既定のマーシャリング) を参照してください。  
  
 オブジェクト参照は blittable ではありません。 これには、単独では blittable なオブジェクトへの参照の配列も含まれます。 たとえば、blittable な構造体は定義できますが、それらの構造体への参照の配列を含む blittable 型は定義できません。  
  
 blittable 型の配列と、blittable 型のメンバーだけを含むクラスは、最適化のために、マーシャリング時にコピーされるのではなく[固定](../../../docs/framework/interop/copying-and-pinning.md)されます。 これらの型は、呼び出し元と呼び出し先が同じアパートメントに属する場合には、In/Out パラメーターとしてマーシャリングされるように見えることがあります。 ただし、そのような型は実際には In パラメーターとしてマーシャリングされるため、引数を In/Out パラメーターとしてマーシャリングする必要がある場合には、<xref:System.Runtime.InteropServices.InAttribute> 属性と <xref:System.Runtime.InteropServices.OutAttribute> 属性を適用する必要があります。  
  
 一部のマネージ データ型は、アンマネージ環境では異なる表現が必要です。 これらの非 blittable データ型は、マーシャリングできる形式に変換する必要があります。 たとえば、マネージ文字列は、文字列オブジェクトに変換しないとマーシャリングできないので、非 blittable 型です。  
  
 <xref:System> 名前空間に属する非 blittable 型を次の表に示します。 [デリゲート](http://msdn.microsoft.com/en-us/d176ee76-f982-494b-b03d-92e4118896e2)は静的メソッドまたはクラス インスタンスを参照するデータ構造体であり、これも非 blittable 型です。  
  
|非 blittable 型|説明|  
|-------------------------|-----------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C スタイルの配列または `SAFEARRAY` に変換されます。|  
|[System.Boolean](http://msdn.microsoft.com/en-us/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|1、2、または 4 バイトの値に変換されます。`true` の場合は 1 または -1 になります。|  
|[System.Char](http://msdn.microsoft.com/en-us/cecc87c1-075e-4cde-aa56-33d189f66feb)|Unicode 文字または ANSI 文字に変換されます。|  
|[System.Class](http://msdn.microsoft.com/en-us/fe334af5-0123-43d8-be84-26f6f023ddb6)|クラス インターフェイスに変換されます。|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|バリアントまたはインターフェイスに変換されます。|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C スタイルの配列または `SAFEARRAY` に変換されます。|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|null 参照で終わる文字列または BSTR に変換されます。|  
|[System.Valuetype](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a)|固定メモリ レイアウトを持つ構造体に変換されます。|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|C スタイルの配列または `SAFEARRAY` に変換されます。|  
  
 クラス型とオブジェクト型は COM 相互運用でのみサポートされます。 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]、C#、および C++ の対応する型については、「[クラス ライブラリの概要](../../../docs/standard/class-library-overview.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [既定のマーシャリング動作](../../../docs/framework/interop/default-marshaling-behavior.md)

