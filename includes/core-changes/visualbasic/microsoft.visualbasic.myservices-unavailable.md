---
ms.openlocfilehash: 75ba041a93b71377928591967e1554742e1d17e1
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237396"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Microsoft.VisualBasic.MyServices 名前空間の型は使用できません

<xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 名前空間の型は使用できません。

#### <a name="version-introduced"></a>導入されたバージョン

.NET Core 3.0 Preview 8

#### <a name="change-description"></a>変更の説明

<xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> 名前空間の型は、一部の .NET Core 3.0 プレビュー リリースで使用できました。 それらは、.NET Core 3.0 Preview 9 以降では使用できなくなりました。

これらの型は、今後のリリースでの不要なアセンブリの依存関係や破壊的変更を回避するために削除されました。
 
#### <a name="recommended-action"></a>推奨される操作

コードが **Microsoft.VisualBasic.MyServices** 型とそのメンバーの使用に依存している場合は、.NET クラス ライブラリに、対応する型とメンバーがあります。 **Microsoft.VisualBasic.MyServices** の型と、それと同等の .NET クラス ライブラリの型との対応を次に示します。

|Microsoft.VisualBasic.MyServices の型|.NET クラス ライブラリの型|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|WPF アプリケーションの場合は <xref:System.Windows.Clipboard?displayProperty=nameWithType>、Windows フォーム アプリケーションの場合は <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType>| 
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<xref:System.IO> 名前空間の型|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<xref:Microsoft.Win32> 名前空間のレジストリ関連の型|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>カテゴリ

Visual Basic

#### <a name="affected-apis"></a>影響を受ける API

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

