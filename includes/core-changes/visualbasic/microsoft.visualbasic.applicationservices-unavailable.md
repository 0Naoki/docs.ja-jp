---
ms.openlocfilehash: 294c077b837899bd714deb2afd1bdff2b3185f38
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237391"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Microsoft.VisualBasic.ApplicationServices 名前空間の型は使用できません

<xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 名前空間の型は使用できません。

#### <a name="version-introduced"></a>導入されたバージョン

.NET Core 3.0 Preview 8

#### <a name="change-description"></a>変更の説明

<xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 名前空間の型は、一部の .NET Core 3.0 プレビュー リリースで使用できました。 それらは、.NET Core 3.0 Preview 9 以降では使用できなくなりました。

これらの型は、今後のリリースでの不要なアセンブリの依存関係や破壊的変更を回避するために削除されました。
 
#### <a name="recommended-action"></a>推奨される操作

コードが <xref:Microsoft.VisualBasic.ApplicationServices> 型とそのメンバーの使用に依存している場合は、.NET クラス ライブラリ内の対応する型またはメンバーを使用できる可能性があります。 たとえば、一部の <xref:System.Environment?displayProperty=nameWithType> および <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> メンバーには、<xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> クラスのプロパティと同等の機能が用意されています。

#### <a name="category"></a>カテゴリ

Visual Basic

#### <a name="affected-apis"></a>影響を受ける API

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-- >

