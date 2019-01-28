---
title: '#pragma checksum - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: c52e93bcf5771fe556730a1d7cf45b8f1c9432b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513023"
---
# <a name="pragma-checksum-c-reference"></a>#pragma checksum (C# リファレンス)
[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] ページのデバッグに使用するソース ファイルのチェックサムを生成します。  
  
## <a name="syntax"></a>構文  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a>パラメーター  
 `"filename"`  
 変更または更新を監視する必要があるファイルの名前。  
  
 `"{guid}"`  
 ハッシュ アルゴリズムのグローバル一意識別子 (GUID)。  
  
 `"checksum_bytes"`  
 チェックサムのバイト数を表す 16 進数の文字列。 偶数の 16 進数である必要があります。 奇数の数値を指定すると、コンパイル時に警告が出力され、ディレクティブが無視されます。  
  
## <a name="remarks"></a>コメント  
 Visual Studio デバッガーは、常に正しいソースを検出するために、チェックサムを使用します。 コンパイラはソース ファイルのチェックサムを計算し、プログラム データベース (PDB) ファイルに結果を出力します。 デバッガーは、その PDB ファイルを使用して、ソース ファイルについて計算したチェックサムと比較します。  
  
 このソリューションは [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] プロジェクトには使用できません。それは計算されたチェックサムは、.aspx ファイルではなく、生成されたソース ファイルを対象としているためです。 この問題に対応するため、`#pragma checksum` によって [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] ページのチェックサムがサポートされています。  
  
 Visual C# で [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] プロジェクトを作成すると、生成されるソース ファイルにソースの生成元である .aspx ファイルのチェックサムが含められます。 コンパイラは、この情報を PDB ファイルに書き込みます。  
  
 ファイルに `#pragma checksum` ディレクティブが見つからない場合、コンパイラはチェックサムを計算し、PDB ファイルにその値を書き込みます。  
  
## <a name="example"></a>例  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>関連項目

- [C# リファレンス](../../../csharp/language-reference/index.md)
- [C# プログラミング ガイド](../../../csharp/programming-guide/index.md)
- [C# プリプロセッサ ディレクティブ](../../../csharp/language-reference/preprocessor-directives/index.md)
