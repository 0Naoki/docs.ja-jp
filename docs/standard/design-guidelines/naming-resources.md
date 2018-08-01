---
title: リソースに名前を付ける
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7cfda4e6a340d040de02903b9b64f0339751c5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571187"
---
# <a name="naming-resources"></a><span data-ttu-id="16215-102">リソースに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="16215-102">Naming Resources</span></span>
<span data-ttu-id="16215-103">ローカライズ可能なリソースは、これらのプロパティの場合と同様、特定のオブジェクトから参照できる、ために、リソースの名前付けのガイドラインは、プロパティのガイドラインに似ています。</span><span class="sxs-lookup"><span data-stu-id="16215-103">Because localizable resources can be referenced via certain objects as if they were properties, the naming guidelines for resources are similar to property guidelines.</span></span>  
  
 <span data-ttu-id="16215-104">**✓ DO** リソース キーで pascal 表記を使用を使用します。</span><span class="sxs-lookup"><span data-stu-id="16215-104">**✓ DO** use PascalCasing in resource keys.</span></span>  
  
 <span data-ttu-id="16215-105">**✓ DO** 短い識別子ではなくわかりやすいを提供します。</span><span class="sxs-lookup"><span data-stu-id="16215-105">**✓ DO** provide descriptive rather than short identifiers.</span></span>  
  
 <span data-ttu-id="16215-106">**X DO NOT** メインの CLR 言語の言語固有のキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="16215-106">**X DO NOT** use language-specific keywords of the main CLR languages.</span></span>  
  
 <span data-ttu-id="16215-107">**✓ DO** のみ英数字とアンダー スコアを使用してリソースの名前付けで使用します。</span><span class="sxs-lookup"><span data-stu-id="16215-107">**✓ DO** use only alphanumeric characters and underscores in naming resources.</span></span>  
  
 <span data-ttu-id="16215-108">**✓ DO** 例外メッセージのリソースに対して次の命名規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="16215-108">**✓ DO** use the following naming convention for exception message resources.</span></span>  
  
 <span data-ttu-id="16215-109">リソース識別子は、例外の種類名と、例外の短い識別子にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16215-109">The resource identifier should be the exception type name plus a short identifier of the exception:</span></span>  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 <span data-ttu-id="16215-110">*部分 © 2005、2009 Microsoft Corporation します。All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="16215-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="16215-111">*ピアソン教育, Inc. からのアクセス許可によって検出[Framework デザイン ガイドライン: 規則、表現方法、および再利用可能な .NET ライブラリを第 2 版パターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)は Cwalina と Brad Abrams、2008 年 10 月 22 日で発行されました。Microsoft Windows 開発シリーズの一部として、Addison-wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="16215-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16215-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="16215-112">See Also</span></span>  
 [<span data-ttu-id="16215-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="16215-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="16215-114">名前付けのガイドライン</span><span class="sxs-lookup"><span data-stu-id="16215-114">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
