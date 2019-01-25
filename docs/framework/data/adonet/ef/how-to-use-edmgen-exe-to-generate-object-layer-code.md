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
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="26b6b-102">方法: EdmGen.exe を使用してオブジェクト レイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="26b6b-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="26b6b-103">このトピックでは、使用する方法を示します、 [EDM ジェネレーター (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) .csdl ファイルに基づいてオブジェクト レイヤー コードを生成するためのツール。</span><span class="sxs-lookup"><span data-stu-id="26b6b-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="26b6b-104">EdmGen.exe を使用して Visual Basic プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="26b6b-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="26b6b-105">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-105">Create the School database.</span></span> <span data-ttu-id="26b6b-106">詳細については、次を参照してください。 [School サンプル データベースを作成する](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-106">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="26b6b-107">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="26b6b-108">詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="26b6b-109">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="26b6b-110">EdmGen.exe を使用して C# プロジェクト用の School モデルのオブジェクトレイヤー コードを生成するには</span><span class="sxs-lookup"><span data-stu-id="26b6b-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1.  <span data-ttu-id="26b6b-111">School データベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-111">Create the School database.</span></span> <span data-ttu-id="26b6b-112">詳細については、次を参照してください。 [School サンプル データベースを作成する](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0)します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-112">For more information, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).</span></span>  
  
2.  <span data-ttu-id="26b6b-113">School モデルを生成するか、School.csdl ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="26b6b-114">詳細については、「[方法 :EdmGen.exe を使用して、モデルとマッピング ファイルを生成する](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3.  <span data-ttu-id="26b6b-115">コマンド プロンプトで、次のコマンド (改行なし) を実行します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="26b6b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="26b6b-116">See also</span></span>
- [<span data-ttu-id="26b6b-117">モデリングとマッピング</span><span class="sxs-lookup"><span data-stu-id="26b6b-117">Modeling and Mapping</span></span>](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [<span data-ttu-id="26b6b-118">方法: Entity Framework プロジェクトを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-118">How to: Manually Configure an Entity Framework Project</span></span>](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [<span data-ttu-id="26b6b-119">ADO.NET Entity Data Model ツール</span><span class="sxs-lookup"><span data-stu-id="26b6b-119">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [<span data-ttu-id="26b6b-120">方法: クエリのパフォーマンスを向上させるためにビューを事前に生成します。</span><span class="sxs-lookup"><span data-stu-id="26b6b-120">How to: Pre-Generate Views to Improve Query Performance</span></span>](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [<span data-ttu-id="26b6b-121">方法: EdmGen.exe を使用して、モデルとマッピング ファイルを生成するには</span><span class="sxs-lookup"><span data-stu-id="26b6b-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
