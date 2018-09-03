---
title: XNA アプリケーションでの操作と慣性の使用
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 70b8d0c5c098089b6f16ef817ff86698f68cf7c3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43478144"
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>XNA アプリケーションでの操作と慣性の使用
この記事では、操作と慣性の処理を Microsoft XNA アプリケーションで使用して、ゲーム ピースの動きを制御する方法について説明します。 この記事をお読みになる前に、「[操作と慣性の概要](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)」トピックの内容、および基本的な XNA のプログラミングの概念についてよく理解してください。  
  
 この記事で説明されているタスクを実行するには、XNA プロジェクトから <xref:System.Windows.Input.Manipulations> アセンブリを参照し、コンピューターに [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([ダウンロード](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) をインストールして、プロジェクトから XNA アセンブリを参照できるようにする必要があります。  
  
## <a name="overview-of-functionality"></a>機能の概要  
 この記事では、操作と慣性の処理を使用するゲーム ピースを表すカスタム クラスの作成方法を示します。 このクラスを使用すると、マウスでゲーム ピースをドラッグしてから放すことで、画面全体で操作できるようになります。 ゲーム ピースを放すと、慣性の処理により、ゲーム ピースの移動速度が徐々に低下します。 直線運動と角運動の両方が行われます。  
  
 ![単純な操作と慣性のアプリケーション。](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")  
  
 さらに、複数のゲーム ピースを管理するカスタム コレクションが作成されます。 これにより、XNA Game クラスから必要とされる処理が簡略化します。  
  
 [GamePiece クラスの作成](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [GamePieceCollection クラスの作成](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Game1 クラスの作成](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [完全なコードの一覧](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a>参照  
 <xref:System.Windows.Input.Manipulations>  
 [操作と慣性の概要](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
