---
title: 軽減策:パスのコロン チェック
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a74c25a9bf4dd8b9ab86bd280881fe1a7999e1d5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70789985"
---
# <a name="mitigation-path-colon-checks"></a>軽減策:パスのコロン チェック
.NET Framework 4.6.2 以降を対象とするアプリから、以前はサポートされていなかったパスをサポートするために (長さと形式の両方について) 数多くの変更が加えられました。 具体的には、適切なドライブの区切り構文 (コロン) のチェックがより正しく行われるようになりました。  
  
## <a name="impact"></a>影響  
 これらの変更は、以前は <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドと <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされていた一部の URI のパスをブロックします。  
  
## <a name="mitigation"></a>軽減策  
 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> メソッドや <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> メソッドでサポートされなくなった、以前は受け入れられていたパスの問題を回避するには、次のようにします。  
  
- URL からスキームを手動で削除します。 たとえば、URL から `file://` を削除します。  
  
- <xref:System.Uri> コンストラクターに URI を渡し、<xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> プロパティの値を取得します。  
  
- `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> を `true` に切り替えて、新しいパスの正規化を無効にします。  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>関連項目

- [変更の再ターゲット](retargeting-changes-in-the-net-framework-4-6-2.md)
