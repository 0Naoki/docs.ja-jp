---
title: '方法: EdmGen.exe を使用してオブジェクト レイヤー コードを生成するには'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 63542866441cb347362e64b08b5de11bde19d50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654569"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>方法: EdmGen.exe を使用してオブジェクト レイヤー コードを生成するには
このトピックでは、使用する方法を示します、 [EDM ジェネレーター (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl ファイルに基づいてオブジェクト レイヤー コードを生成するためのツール。  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>EdmGen.exe を使用して Visual Basic プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには  
  
1.  School データベースを作成します。 詳細については、次を参照してください。 [School サンプル データベースを作成する](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)します。  
  
2.  School モデルを生成するか、School.csdl ファイルを取得します。 詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。  
  
3.  コマンド プロンプトで、次のコマンド (改行なし) を実行します。  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>EdmGen.exe を使用して C# プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには  
  
1.  School データベースを作成します。 詳細については、次を参照してください。 [School サンプル データベースを作成する](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)します。  
  
2.  School モデルを生成するか、School.csdl ファイルを取得します。 詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。  
  
3.  コマンド プロンプトで、次のコマンド (改行なし) を実行します。  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>関連項目
- [モデリングとマッピング](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [方法: Entity Framework プロジェクトを手動で構成します。](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [ADO.NET Entity Data Model ツール](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [方法: クエリのパフォーマンスを向上させるためにビューを事前に生成します。](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [方法: EdmGen.exe を使用して、モデルとマッピング ファイルを生成するには](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
