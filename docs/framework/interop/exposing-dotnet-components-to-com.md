---
title: "COM への .NET Framework コンポーネントの公開"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a3d34c60a5c2cae5abaa6763b935f6d11a29a39e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2018
---
# <a name="exposing-net-framework-components-to-com"></a>COM への .NET Framework コンポーネントの公開
.NET 型の記述とその型をアンマネージ コードから使用することは、開発者にとっては個別のアクティビティです。 このセクションでは、COM クライアントと相互運用するマネージ コードの記述のためのいくつかのヒントについて説明します。  
  
-   [相互運用のための .NET 型の要件を満たす](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)。  
  
     COM に対して公開するすべてのマネージ型、マネージ メソッド、マネージ プロパティ、マネージ フィールド、およびマネージ イベントは、パブリックとしてください。 型は、パブリックな既定のコンストラクターを持っている必要があります。このコンストラクターが、COM を通じて呼び出すことができる唯一のコンストラクターです。  
  
-   [相互運用属性を適用する](../../../docs/framework/interop/applying-interop-attributes.md)。  
  
     マネージ コード内のカスタム属性は、コンポーネントの相互運用性を強化できます。  
  
-   [COM 用にアセンブリをパッケージ化する](../../../docs/framework/interop/packaging-an-assembly-for-com.md)。  
  
     COM 開発者から、アセンブリの参照と展開に必要な手順をまとめるように求められる場合があります。  
  
 さらに、このセクションでは、COM クライアントからマネージ型の使用に関連するタスクを明らかにします。  
  
#### <a name="to-consume-a-managed-type-from-com"></a>COM からマネージ型を使用するには  
  
1.  [COM にアセンブリを登録する](../../../docs/framework/interop/registering-assemblies-with-com.md)。  
  
     アセンブリ (およびタイプ ライブラリ) 内の型は、デザイン時に登録する必要があります。 インストーラーでアセンブリが登録されない場合は、Regasm.exe を使用するように COM 開発者に指示します。  
  
2.  [COM から .NET 型を参照する](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)。  
  
     COM 開発者は、現在使用しているのと同じツールと手法を使用して、アセンブリ内の型を参照できます。  
  
3.  [.NET オブジェクトを呼び出す](http://msdn.microsoft.com/library/40c9626c-aea6-4bad-b8f0-c1de462efd33)。  
  
     COM 開発者は、アンマネージ型でメソッドを呼び出すのと同じ方法で、.NET オブジェクトでメソッドを呼び出すことができます。 たとえば、COM **CoCreateInstance** API は、.NET オブジェクトをアクティブにします。  
  
4.  [COM アクセスに対してアプリケーションを展開する](http://msdn.microsoft.com/library/fb63564c-c1b9-4655-a094-a235625882ce)。  
  
     厳格な名前付きのアセンブリは、グローバル アセンブリ キャッシュにインストールすることができ、発行元からの署名が必要です。 厳密な名前のないアセンブリは、クライアントのアプリケーション ディレクトリにインストールする必要があります。  
  
## <a name="see-also"></a>参照  
 [アンマネージ コードとの相互運用](../../../docs/framework/interop/index.md)  
 [COM 相互運用機能のサンプル: COM クライアントおよび .NET サーバー](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)
