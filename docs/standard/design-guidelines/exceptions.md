---
title: 例外のデザインのガイドライン
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], exceptions
- errors [.NET Framework], exceptions
- reporting errors
ms.assetid: bc177b2f-7528-4ae4-83db-aacfb04b86d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99b27615ef16aa69e18d82cb97f4751dc92d2ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570604"
---
# <a name="design-guidelines-for-exceptions"></a><span data-ttu-id="82bac-102">例外のデザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="82bac-102">Design Guidelines for Exceptions</span></span>
<span data-ttu-id="82bac-103">例外処理では、エラーの戻り値ベースのレポートに比べて多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="82bac-103">Exception handling has many advantages over return-value-based error reporting.</span></span> <span data-ttu-id="82bac-104">適切なフレームワークの設計では、例外のメリットを実現アプリケーション開発者は、ことができます。</span><span class="sxs-lookup"><span data-stu-id="82bac-104">Good framework design helps the application developer realize the benefits of exceptions.</span></span> <span data-ttu-id="82bac-105">このセクションでは、例外の利点を説明し、それらを効果的に使用するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="82bac-105">This section discusses the benefits of exceptions and presents guidelines for using them effectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82bac-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="82bac-106">In This Section</span></span>  
 [<span data-ttu-id="82bac-107">例外のスロー</span><span class="sxs-lookup"><span data-stu-id="82bac-107">Exception Throwing</span></span>](../../../docs/standard/design-guidelines/exception-throwing.md)  
 [<span data-ttu-id="82bac-108">標準例外型の使用</span><span class="sxs-lookup"><span data-stu-id="82bac-108">Using Standard Exception Types</span></span>](../../../docs/standard/design-guidelines/using-standard-exception-types.md)  
 [<span data-ttu-id="82bac-109">例外とパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="82bac-109">Exceptions and Performance</span></span>](../../../docs/standard/design-guidelines/exceptions-and-performance.md)  
 <span data-ttu-id="82bac-110">*部分 © 2005、2009 Microsoft Corporation します。All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="82bac-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="82bac-111">*ピアソン教育, Inc. からのアクセス許可によって検出[Framework デザイン ガイドライン: 規則、表現方法、および再利用可能な .NET ライブラリを第 2 版パターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)は Cwalina と Brad Abrams、2008 年 10 月 22 日で発行されました。Microsoft Windows 開発シリーズの一部として、Addison-wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="82bac-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82bac-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="82bac-112">See Also</span></span>  
 [<span data-ttu-id="82bac-113">フレームワーク デザインのガイドライン</span><span class="sxs-lookup"><span data-stu-id="82bac-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
