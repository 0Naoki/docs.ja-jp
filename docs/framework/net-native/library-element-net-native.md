---
title: '&lt;Library&gt; 要素 (.NET ネイティブ)'
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eabaf1dd99fce7cd4c45f80666534f904fcdfdf9
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2018
ms.locfileid: "34311976"
---
# <a name="ltlibrarygt-element-net-native"></a>&lt;Library&gt; 要素 (.NET ネイティブ)
実行時にリフレクションに使用可能なメタデータを持つ型と型のメンバーを含むアセンブリを定義します。  
  
 \<Directives> 要素  
\<Library> 要素  
  
## <a name="syntax"></a>構文  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|`Name`|必須の属性です。 アセンブリの名前を指定します。 この `<Library>` 要素の子要素によって、このアセンブリ内にある型と型のメンバーのランタイム リフレクション ポリシーが定義されます。|  
  
## <a name="name-attribute"></a>Name 属性  
  
|値|説明|  
|-----------|-----------------|  
|*assembly_name*|ファイル拡張子のないアセンブリの簡易名です。 この属性は、<xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> プロパティに対応します。 たとえば、Extensions.dll というアセンブリの名前は "Extensions" です。 アセンブリのメタデータの条件付きインクルードをサポートする特殊な形式の *assembly_name* については、「解説」セクションを参照してください。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|特定のアセンブリ内のすべての型にポリシーを適用します。|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|特定の名前空間内のすべての型にポリシーを適用します。|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|クラスや構造体などの特定の型にポリシーを適用します。|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|構築されたジェネリック型にポリシーを適用します。 たとえば、[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) 要素を使用して `List<String>` 型のポリシーを定義できます。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)|ランタイム ディレクティブ ファイルのルート要素です。|  
  
## <a name="remarks"></a>コメント  
 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md) 要素には、0 個以上の `<Library>` 要素を含めることができます。  
  
 `<Library>` 要素は、実行時に必要なメタデータを持つプログラム要素を定義するためのコンテナーとして機能します。この要素はポリシーを表しません。 コンパイル時に、コンパイラ ツールは `<Library>` 要素により指定されたライブラリでのみ、その子要素により示されるプログラム要素を検索します。 一方、[\<Application>](../../../docs/framework/net-native/application-element-net-native.md) 要素の子要素により示されるプログラム要素を検索する場合、コンパイラ ツールは .NET Framework コア ライブラリを含むすべてのライブラリを検索します。  
  
 `<Library>` ディレクティブは、条件付きで使用される場合があります。 場合の名前、`<Library>`要素が起動し、末尾がアスタリスク (\*) では、`<Library>`ディレクティブしている、アスタリスク間に指定されたアセンブリがアプリによって参照されている場合にのみ影響します。 たとえば、次のランタイム ディレクティブは、Utillities.dll アセンブリがアプリによって参照されている場合にのみ適用されます。  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>関連項目  
 [\<アプリケーション > 要素](../../../docs/framework/net-native/application-element-net-native.md)  
 [\<ディレクティブ > 要素](../../../docs/framework/net-native/directives-element-net-native.md)  
 [ランタイム ディレクティブ (rd.xml) 構成ファイル リファレンス](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
 [ランタイム ディレクティブ要素](../../../docs/framework/net-native/runtime-directive-elements.md)
