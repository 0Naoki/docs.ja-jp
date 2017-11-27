---
title: T:System.Reflection.AssemblyKeyFileAttribute
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33c9bdf3cf055ea005542f8b2471963b16c16122
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="keyfile"></a>T:System.Reflection.AssemblyKeyFileAttribute
アセンブリに厳密な名前を付けるキーまたはキー ペアを含むファイルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a>引数  
 `file`  
 必須です。 キーを含むファイルです。 ファイル名にスペースが含まれている場合は、名前を引用符で囲みます ("") です。  
  
## <a name="remarks"></a>コメント  
 コンパイラは、アセンブリ マニフェストに公開キーを挿入し、秘密キーを使用し、最終的なアセンブリを署名します。 キー ファイルを生成する入力`sn -k file`コマンドライン。 詳細については、「[Sn.exe (厳密名ツール)](https://msdn.microsoft.com/library/k5b5tt23)」を参照してください。  
  
 コンパイルする場合`/target:module`、キー ファイルの名前が、モジュール内に保持しを伴うアセンブリをコンパイルするときに作成されるアセンブリに組み込む[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)です。  
  
 また、暗号化情報を [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) でコンパイラに渡すことができます。 部分的に署名されたアセンブリを作成する場合は、[/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) を使います。  
  
 カスタム属性としては、このオプションを指定することもできます (<xref:System.Reflection.AssemblyKeyFileAttribute>)、Microsoft intermediate language モジュールのソース コードにします。  
  
 場合両方`/keyfile`と[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)がで指定された (コマンド ライン オプションまたはカスタム属性によって)、同じコンパイル時に、コンパイラにより、キー コンテナーを最初に試行します。 それが成功すると、アセンブリはキー コンテナーの情報で署名されます。 指定されたファイルを試みますが、コンパイラが、キー コンテナーを見つけられない場合`/keyfile`です。 これが成功した、キーのファイルの情報と、アセンブリは署名およびキー コンテナーにキー情報がインストールされている場合 (に似て`sn -i`) 次のコンパイル時に、キー コンテナーが有効になるようにします。  
  
 キー ファイルには公開キーだけが含まれる場合があることに注意してください。  
  
 参照してください[作成と使用](https://msdn.microsoft.com/library/xwb8f617)アセンブリに署名する方法についてです。  
  
> [!NOTE]
>  `/keyfile`オプションは内から使用できません、[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]開発環境は、コマンドラインからコンパイルするときにのみ使用します。  
  
## <a name="example"></a>例  
 次のコードは、ソース ファイルをコンパイル`Input.vb`し、キー ファイルを指定します。  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>関連項目  
 [アセンブリとグローバル アセンブリ キャッシュ](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Visual Basic のコマンド ライン コンパイラ](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [コンパイル コマンド ラインのサンプル](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
