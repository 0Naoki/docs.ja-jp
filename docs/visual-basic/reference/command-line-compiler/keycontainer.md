---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc6453dc188e7621444b6f44b805aab9354d81f0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43854685"
---
# <a name="-keycontainer"></a>-keycontainer
アセンブリに厳密な名前を付けるキー ペアのキー コンテナー名を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a>引数  
  
|用語|定義|  
|---|---|  
|`container`|必須。 コンテナー キーを含むファイルです。 ファイル名を引用符で囲みます ("")、名前にスペースが含まれている場合。|  
  
## <a name="remarks"></a>Remarks  
 コンパイラは、秘密キーで最終アセンブリに署名して、アセンブリ マニフェストに公開キーを挿入することで、共有可能なコンポーネントを作成します。 キー ファイルを生成するには、コマンド ラインで「`sn -k file`」と入力します。 `-i`オプションは、コンテナーにキー ペアをインストールします。 詳細については、[Sn.exe (厳密名ツール)] を参照してください。[Sn.exe (厳密名ツール)](../../../framework/tools/sn-exe-strong-name-tool.md))。  
  
 使用してコンパイルする場合`-target:module`、キー ファイルの名前がモジュールに保持され、使用してアセンブリをコンパイルするときに作成されるアセンブリに組み込まれます[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)します。  
  
 このオプションは、任意の Microsoft Intermediate Language (MSIL) モジュールのソース コードで、カスタム属性 (<xref:System.Reflection.AssemblyKeyNameAttribute>) として指定することもできます。  
  
 また、暗号化情報を [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) でコンパイラに渡すことができます。 部分的に署名されたアセンブリを作成する場合は、[-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) を使います。  
  
 参照してください[の作成と using strong-named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)アセンブリへの署名の詳細についてはします。  
  
> [!NOTE]
>  `-keycontainer`オプションは、Visual Studio 開発環境内からは使用できません。 コマンドラインからコンパイルする場合にのみ使用可能なです。  
  
## <a name="example"></a>例  
 次のコードは、ソース ファイルをコンパイル`Input.vb`をキー コンテナーを指定します。  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>関連項目  
 [アセンブリとグローバル アセンブリ キャッシュ](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
