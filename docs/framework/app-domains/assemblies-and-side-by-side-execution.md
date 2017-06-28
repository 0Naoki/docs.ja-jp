---
title: "アセンブリと side-by-side 実行 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b78c82937c78286302adef532c451c24987da39
ms.contentlocale: ja-jp
ms.lasthandoff: 06/02/2017

---
# <a name="assemblies-and-side-by-side-execution"></a>アセンブリと side-by-side 実行
side-by-side 実行は、アプリケーションやコンポーネントの複数のバージョンを同じコンピューターに格納して実行する機能です。 つまり、ランタイムの複数のバージョンと、特定のバージョンのランタイムを使用するアプリケーションおよびコンポーネントの複数のバージョンを、同一コンピューター上に共存させることができます。 side-by-side 実行によって、アプリケーションをバインドするコンポーネントのバージョンや、アプリケーションが使用するランタイムのバージョンを細かく制御できます。  
  
 同じアセンブリの異なるバージョンの side-by-side ストレージにおける side-by-side 実行のサポートは、厳密な名前には不可欠の要素であり、ランタイムのインフラストラクチャに組み込まれています。 厳密な名前を持つアセンブリのバージョン番号がその識別子の一部に含まれているため、ランタイムは同じアセンブリの複数のバージョンをグローバル アセンブリ キャッシュに格納し、実行時にこれらのアセンブリを読み込むことができます。  
  
 ランタイムは、side-by-side 実行できるアプリケーションの作成機能を提供しますが、side-by-side 実行は自動的にサポートされるわけではありません。 side-by-side 実行できるアプリケーションの作成に関する詳細については、「[Guidelines for Creating Components for Side-by-Side Execution](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md)」 (side-by-side 実行用のコンポーネントを作成するためのガイドライン) を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ランタイムがアセンブリを検索する方法](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [共通言語ランタイムのアセンブリ](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
