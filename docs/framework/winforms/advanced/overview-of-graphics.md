---
title: "グラフィックスについて"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0a3286cbcaa0eebf59500582a749804b5e1b8ba
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2017
---
# <a name="overview-of-graphics"></a>グラフィックスについて
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Microsoft Windows オペレーティング システムのサブシステムを形成する、アプリケーション プログラミング インターフェイス (API)。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]画面およびプリンターの情報を表示します。 その名前からわかるように、[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] は [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] の後継であり、以前のバージョンの Windows に含まれているグラフィックス デバイス インターフェイスです。  
  
## <a name="managed-class-interface"></a>マネージ クラスのインターフェイス  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API は、一連のマネージ コードとして展開されているクラスを通じて公開されます。 このクラスのセットと呼ばれる、*マネージ クラスのインターフェイス*に[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]です。 次の名前空間は、マネージ クラスのインターフェイスを構成します。  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 グラフィックス デバイス インターフェイスを備えたなど[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]、画面またはプリンターの情報を表示するには、特定のディスプレイ デバイスの詳細について考慮する必要はありません。 プログラマは [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] クラスによって提供されるさまざまなメソッドを呼び出します。 次に、これらのメソッドで、特定のデバイス ドライバーへの適切な呼び出しを実行します。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] は、グラフィックス ハードウェアからアプリケーションを分離します。 このデバイスに依存しないアプリケーションを作成するプログラマができるようにするためです。  
  
## <a name="see-also"></a>関連項目  
 [グラフィックスの概要](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
