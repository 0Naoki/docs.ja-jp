---
title: 共通デザイン パターン
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- design patterns in class libraries
- class library design guidelines [.NET Framework], design patterns
ms.assetid: f7bd1361-4ab2-4132-972d-a044b8f197e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d41ba0c1e972eeee07b36ad0d15532f7b551ec2a
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "44172945"
---
# <a name="common-design-patterns"></a><span data-ttu-id="35289-102">共通デザイン パターン</span><span class="sxs-lookup"><span data-stu-id="35289-102">Common Design Patterns</span></span>
<span data-ttu-id="35289-103">ソフトウェア パターン、パターンの言語、およびパターンの非常に広範なサブジェクトに対処するためのアンチ パターンに多数の書籍があります。</span><span class="sxs-lookup"><span data-stu-id="35289-103">There are numerous books on software patterns, pattern languages, and antipatterns that address the very broad subject of patterns.</span></span> <span data-ttu-id="35289-104">したがって、ガイドラインと非常に限定された一連の .NET Framework Api の設計で頻繁に使用するパターンに関連するディスカッションについても説明します。</span><span class="sxs-lookup"><span data-stu-id="35289-104">Thus, this chapter provides guidelines and discussion related to a very limited set of patterns that are used frequently in the design of the .NET Framework APIs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35289-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="35289-105">In This Section</span></span>  
 [<span data-ttu-id="35289-106">依存関係プロパティ</span><span class="sxs-lookup"><span data-stu-id="35289-106">Dependency Properties</span></span>](../../../docs/standard/design-guidelines/dependency-properties.md)  
 [<span data-ttu-id="35289-107">Dispose パターン</span><span class="sxs-lookup"><span data-stu-id="35289-107">Dispose Pattern</span></span>](../../../docs/standard/design-guidelines/dispose-pattern.md)  
 <span data-ttu-id="35289-108">*Portions © 2005, 2009 Microsoft Corporation.All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="35289-108">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="35289-109">*2008 年 10 月 22 日に Microsoft Windows Development シリーズの一部として、Addison-Wesley Professional によって発行された、Krzysztof Cwalina および Brad Abrams による「[Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)」 (フレームワーク デザイン ガイドライン: 再利用可能な .NET ライブラリの規則、用法、パターン、第 2 版) から Pearson Education, Inc. の許可を得て再印刷されています。*</span><span class="sxs-lookup"><span data-stu-id="35289-109">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35289-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="35289-110">See also</span></span>

- [<span data-ttu-id="35289-111">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="35289-111">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
