---
title: 発行者名レジストリの検証
ms.date: 03/30/2017
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
ms.openlocfilehash: aa6a71ced0f9bf969eb6c8800739f629810dd63f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="validating-issuer-name-registry"></a>発行者名レジストリの検証
Windows Identity Foundation の Validating Issuer Name Registry (VINR) 拡張機能を使用すると、受信トークンが信頼できるテナントおよび ID プロバイダーから発行されたことをマルチテナント アプリケーションが確認できます。 Microsoft Azure AD によって発行されるすべてのトークンは同じ証明書を使用して署名されているため、この機能は Microsoft Azure Active Directory を使用するマルチテナント アプリケーションに特に役立ちます。 同じ証明書を使用する (つまり、母音が同じ) 複数のテナントからの要求を区別するため、アプリケーションはテナントごとに発行者名を維持して検証ロジックを実行する必要があります。 VINR にはこの機能が備わっており、カスタム検証ロジックを追加したり、構成ファイル以外の場所に発行者のレジストリ データを格納したりすることができます。 この拡張機能は、アプリケーションの WIF パイプラインに追加したり、別個に使用することができます。  
  
 VINR は NuGet パッケージとして入手できます。 詳細については、「[Downloading the Validating Issuer Name Registry Package](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md)」(発行者名レジストリの検証パッケージのダウンロード) を参照してください。  
  
## <a name="scenarios"></a>シナリオ  
 VINR により、次の主要なシナリオが可能になります。  
  
-   **マルチテナント アプリケーションのトークンを検証する**: このシナリオでは、Litware という会社が Windows Azure AD として ID プロバイダーを使用するマルチテナント アプリケーションを開発しました。 このアプリケーションは、2 つの顧客 (Contoso および Fabrikam) にサービスを提供しています。 Fabrikam のユーザーが Litware のアプリケーションで認証を行うと、Microsoft Azure AD から生成されるトークンは標準の証明書を使用して署名され、要求は Fabrikam により発行されます。 アプリケーションは発行者名とトークンの両方が有効であることを検証し、Windows Azure AD の同じ証明書を使用して署名された Contoso からの要求を区別する必要があります。 VINR を使用すると、Litware アプリケーションが Contoso や Fabrikam などのマルチテナントからの要求を簡単に区別できるようになります。  
  
## <a name="features"></a>フィーチャー  
 VINR には次の機能があります。  
  
-   **マルチテナント アプリケーションの発行者名とトークンの検証**: 発行者名 (テナント) と、トークンが ID プロバイダーの有効な証明書を使用して署名されたかどうかを確認することで、受信トークンを検証します。  
  
-   **カスタム検証ロジックとデータ ストアの機能拡張**: 独自の検証ロジックを挿入し、既定の構成ファイル以外のデータ ストアを指定するための機能拡張を提供します。
