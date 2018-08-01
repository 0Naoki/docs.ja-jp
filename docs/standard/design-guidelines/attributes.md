---
title: Attributes1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 493ac709123c67311ba570894fb324ae7148bfae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574635"
---
# <a name="attributes"></a>属性
<xref:System.Attribute?displayProperty=nameWithType> カスタム属性を定義するために使用する基本クラスです。  
  
 属性は、アセンブリ、型、メンバー、およびパラメーターなどのプログラミング要素に追加できる注釈です。 これらは、アセンブリのメタデータには保存され、リフレクション Api を使用して実行時にアクセスできます。 たとえば、フレームワークの定義、 <xref:System.ObsoleteAttribute>、型またはメンバーは廃止されていることを示すために、型またはメンバーに適用できます。  
  
 属性は、属性に関連するその他のデータを伝達する 1 つまたは複数のプロパティを持つことができます。 たとえば、`ObsoleteAttribute`のリリースに関する追加情報を実行できる、型またはメンバーが使用されなくなったと廃止された API を置き換える新しい Api の説明。  
  
 属性が適用されるときに、属性の一部のプロパティを指定する必要があります。 これらと呼ばれるに必要なプロパティまたは必須の引数のため、位置指定のコンス トラクターのパラメーターとして表されます。 たとえば、<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>のプロパティ、<xref:System.Diagnostics.ConditionalAttribute>必要なプロパティです。  
  
 プロパティがないとは限りません属性が適用されたときに指定するのには、省略可能なプロパティ (または省略可能な引数) と呼ばれます。 設定可能なプロパティによって表されます。 コンパイラでは、属性が適用されるときに、これらのプロパティを設定する特別な構文を提供します。 たとえば、<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>プロパティは省略可能な引数を表します。  
  
 **✓ DO** 「属性」サフィックスを持つカスタム属性クラスの名前  
  
 **✓ DO** 適用、<xref:System.AttributeUsageAttribute>カスタム属性にします。  
  
 **✓ DO** 省略可能な引数の設定可能なプロパティを提供します。  
  
 **✓ DO** 必須の引数の取得専用のプロパティを提供します。  
  
 **✓ DO** 必須の引数に対応するプロパティを初期化するコンス トラクターのパラメーターを指定します。 各パラメーターにすることは、同じ名前 (大文字小文字が異なる) には、対応するプロパティです。  
  
 **X AVOID** 省略可能な引数に対応するプロパティを初期化するコンス トラクターのパラメーターを指定します。  
  
 つまり、コンス トラクターと、set アクセス操作子の両方で設定できるプロパティがありません。 このガイドラインは、明示的に指定する引数は省略可能なこれが必要であり、2 つの方法で同じことを行う必要はなくなります。  
  
 **X AVOID** カスタム属性のコンス トラクターのオーバー ロードします。  
  
 コンス トラクターの 1 つだけのことを明確に伝達をユーザーにどの引数が必須および省略可能な。  
  
 **✓ DO** 可能であれば、カスタム属性クラスをシールします。 これにより、属性の参照も高速です。  
  
 *部分 © 2005、2009 Microsoft Corporation します。All rights reserved.*  
  
 *ピアソン教育, Inc. からのアクセス許可によって検出[Framework デザイン ガイドライン: 規則、表現方法、および再利用可能な .NET ライブラリを第 2 版パターン](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)は Cwalina と Brad Abrams、2008 年 10 月 22 日で発行されました。Microsoft Windows 開発シリーズの一部として、Addison-wesley Professional。*  
  
## <a name="see-also"></a>関連項目  
 [フレームワーク デザインのガイドライン](../../../docs/standard/design-guidelines/index.md)  
 [使用方法のガイドライン](../../../docs/standard/design-guidelines/usage-guidelines.md)
