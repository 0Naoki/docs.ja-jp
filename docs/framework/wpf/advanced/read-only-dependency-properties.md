---
title: "読み取り専用の依存関係プロパティ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9cb4477fe388c294bbd6b87589d5a3108a90d27f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="read-only-dependency-properties"></a>読み取り専用の依存関係プロパティ
このトピックでは、既存の読み取り専用の依存関係プロパティ、カスタムの読み取り専用の依存関係プロパティを作成するシナリオと手法など、読み取り専用の依存関係プロパティについて説明します。  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>必須コンポーネント  
 このトピックでは、依存関係プロパティの実装の基本シナリオとカスタム依存関係プロパティへのメタデータの適用方法を理解していることを前提とします。 詳細については、「[カスタム依存関係プロパティ](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)」および「[依存関係プロパティのメタデータ](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)」を参照してください。  
  
<a name="existing"></a>   
## <a name="existing-read-only-dependency-properties"></a>既存の読み取り専用の依存関係プロパティ  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] フレームワークで定義されている依存関係プロパティの一部は読み取り専用です。 読み取り専用の依存関係プロパティを指定する一般的な理由は、それらが状態決定に使用されるプロパティであるにも関わらず、その状態は多くの要因の影響を受け、プロパティをその状態に設定するだけではユーザー インターフェイス設計の観点から望ましくないことにあります。 たとえば、このプロパティ<xref:System.Windows.UIElement.IsMouseOver%2A>マウス入力から決定された状態の表示が実際には。 実際にマウス入力を行わずにプログラムでこの値を設定しようとすると、予期しない結果になり、不整合が生じる原因になります。  
  
 設定可能ではないため、読み取り専用の依存関係プロパティは、依存関係プロパティがソリューションを通常提供するシナリオの多くには適切ではありません (データ バインディング、直接スタイル設定可能な値、検証、アニメーション、継承など)。 それでも、設定不可能な読み取り専用依存関係プロパティには、プロパティ システムの依存関係プロパティによってサポートされるいくつかの追加機能があります。 その他の機能のうち最も重要なのは、読み取り専用の依存関係プロパティはスタイルのプロパティ トリガーとして使用できることです。 通常の [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] プロパティではトリガーを有効にできません。依存関係プロパティであることが必要です。 前述<xref:System.Windows.UIElement.IsMouseOver%2A>プロパティ場合がありますをいくつかのコントロールのスタイルを定義するのには、非常に役にシナリオの完全な例は、背景、前景、内の合成要素のようなプロパティなどの visible プロパティ、ユーザーがコントロールのいくつかの定義済みの領域の上にマウスを置いたときに、コントロールが変更されます。 読み取り専用の依存関係プロパティの変化は、プロパティ システム固有の無効化プロセスによって検出して報告することもでき、これは実際にはプロパティ トリガー機能を内部的にサポートします。  
  
<a name="new"></a>   
## <a name="creating-custom-read-only-dependency-properties"></a>読み取り専用のカスタム依存関係プロパティの作成  
 多くの一般的な依存関係プロパティのシナリオで読み取り専用依存関係プロパティが機能しない理由に関する前のセクションを参照してください。 ただし、適切なシナリオがある場合は、独自の読み取り専用依存関係プロパティを作成してもかまいません。  
  
 読み取り専用の依存関係プロパティを作成するプロセスの大部分は、「[カスタム依存関係プロパティ](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)」と「[依存関係プロパティの実装](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md)」のトピックの説明と同じです。 ただし、次の 3 つの重要な違いがあります。  
  
-   プロパティを登録するときに呼び出す、<xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>メソッド、標準ではなく<xref:System.Windows.DependencyProperty.Register%2A>プロパティの登録の方法です。  
  
-   [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] の "ラッパー" プロパティを実装するときは、ラッパーにも set 実装をしないようにして、公開するパブリック ラッパーの読み取り専用状態が矛盾しないようにする必要があります。  
  
-   読み取り専用登録によって返されるオブジェクトは<xref:System.Windows.DependencyPropertyKey>なく<xref:System.Windows.DependencyProperty>です。 やはりこのフィールドをメンバーとして格納する必要がありますが、通常は、型のパブリック メンバーにはしません。  
  
 読み取り専用の依存関係プロパティを補足するために使用するプライベートのフィールドまたは値はすべて、適当なロジックを使用して完全に書き込み可能にしてかまいません。 ただし、初期化で、またはランタイム ロジックの一部として、プロパティを設定する最も簡単な方法は、プロパティ システムを使用しないでプライベートなバッキング フィールドを直接設定するのではなく、プロパティ システムの [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] を使用する方法です。 具体的には、署名がある<xref:System.Windows.DependencyObject.SetValue%2A>型のパラメーターを受け入れる<xref:System.Windows.DependencyPropertyKey>です。 この値、アプリケーション ロジック内で、プログラムによって設定方法と場所に影響を与える方法に対してアクセスを設定する場合、<xref:System.Windows.DependencyPropertyKey>依存関係プロパティを最初に登録するときに作成します。 このロジックすべてをクラス内で処理する場合はプライベートにでき、アセンブリの他の部分から設定する必要がある場合は内部に設定します。 呼び出す方法の 1 つは、<xref:System.Windows.DependencyObject.SetValue%2A>ストアド プロパティの値が変更する必要があるクラスのインスタンスに通知する関連イベントのクラスのイベント ハンドラー内で。 別のアプローチがペアリングを使用して、依存関係プロパティを結び、<xref:System.Windows.PropertyChangedCallback>と<xref:System.Windows.CoerceValueCallback>登録時にこれらのプロパティのメタデータの一部としてコールバック。  
  
 <xref:System.Windows.DependencyPropertyKey>はプライベートであるとは反映されませんプロパティで、システムによって、コードの外部で、読み取り専用の依存関係プロパティがより読み取り/書き込みの依存関係プロパティよりもセキュリティを設定します。 読み取り/書き込み依存関係プロパティの場合は、識別するフィールドは明示的または暗黙的にパブリックであり、したがってプロパティは広範に設定可能です。 詳細については、「[依存関係プロパティのセキュリティ](../../../../docs/framework/wpf/advanced/dependency-property-security.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [依存関係プロパティの概要](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [カスタム依存関係プロパティ](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [スタイルとテンプレート](../../../../docs/framework/wpf/controls/styling-and-templating.md)
