---
title: "相互運用のための .NET 型の要件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 68ecd5e4c562f1eecb31ee539adb70d67455a584
ms.contentlocale: ja-jp
ms.lasthandoff: 08/21/2017

---
# <a name="qualifying-net-types-for-interoperation"></a>相互運用のための .NET 型の要件
COM アプリケーションにアセンブリ内の型を公開する場合は、設計時に COM 相互運用の要件を検討する必要があります。 以下のガイドラインに従うと、マネージ型 (クラス、インターフェイス、構造体、列挙型) は COM の型とシームレスに統合します。  
  
-   クラスは、インターフェイスを明示的に実装する必要があります。  
  
     COM 相互運用は、クラスのすべてのメンバーとその基底クラスのメンバーを含むインターフェイスを自動的に生成するメカニズムを備えていますが、明示的なインターフェイスを提供する方がはるかによい方法です。 自動的に生成されるインターフェイスは、クラス インターフェイスと呼ばれます。 ガイドラインについては、「[クラス インターフェイスの概要](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)」を参照してください。  
  
     インターフェイス定義言語 (IDL) またはそれと同等のものを使う代わりに、[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]、C#、C++ を使ってコードにインターフェイス定義を組み込むことができます。 構文の詳細については、言語のドキュメントを参照してください。  
  
-   マネージ型はパブリックにする必要があります。  
  
     アセンブリ内のパブリック型のみが登録されて、タイプ ライブラリにエクスポートされます。 その結果、パブリック型のみが COM に表示されます。  
  
     マネージ型は、COM に公開されない可能性がある他のマネージ コードに機能を公開します。 たとえば、パラメーター化されたコンストラクター、静的メソッド、および定数フィールドは、COM クライアントに公開されません。 さらに、ランタイムが、ある型に、またはある型からデータをマーシャリングすると、データがコピーまたは変換される可能性があります。  
  
-   メソッド、プロパティ、フィールド、イベントは、パブリックである必要があります。  
  
     また、パブリック型のメンバーを COM に表示させる場合は、メンバーもパブリックにする必要があります。 アセンブリ、パブリック型、またはパブリック型のパブリック メンバーの可視性は、<xref:System.Runtime.InteropServices.ComVisibleAttribute> を適用することにより制限できます。 既定では、すべてのパブリック型とメンバーが可視になります。  
  
-   型では、既定のパブリック コンストラクターを COM からアクティブ化する必要があります。  
  
     マネージ パブリック型のみが COM に表示されます。 ただし、既定のパブリック コンストラクター (引数のないコンストラクター) がないと、COM クライアントは型を作成できません。 その場合でも、型が他の方法でアクティブ化されると、COM クライアントは型を使うことができます。  
  
-   型を抽象にすることはできません。  
  
     COM クライアントも .NET クライアントも、抽象型は作成できません。  
  
 COM にエクスポートされるとき、マネージ型の継承階層はフラット化されます。 マネージ環境とアンマネージ環境では、バージョン管理も異なります。 COM に公開された型は、他のマネージ型とバージョン管理特性が異なります。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 [COM への .NET Framework コンポーネントの公開](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [クラス インターフェイスの概要](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [相互運用固有の属性の適用](../../../docs/framework/interop/applying-interop-attributes.md)   
 [COM 用のアセンブリのパッケージ化](../../../docs/framework/interop/packaging-an-assembly-for-com.md)

