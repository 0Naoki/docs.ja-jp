---
title: FileName で指定されたファイルは、正しい XML ファイルではありません
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 3aecb0c2c87539717656a29f5b48f94fce3c8453
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481877"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="0a3cd-102">FileName で指定されたファイルは、正しい XML ファイルではありません</span><span class="sxs-lookup"><span data-stu-id="0a3cd-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="0a3cd-103">指定したファイル名は、正しい XML ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="0a3cd-104">XML ドキュメントの許可されている構造体とコンテンツを指定する場合、ドキュメント型定義 (DTD)、Microsoft XML-Data Reduced (XDR) スキーマ、または XML スキーマ定義言語 (XSD) スキーマを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="0a3cd-105">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]で XML 文法を指定する場合は、XSD スキーマをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a3cd-106">Visual Studio の以前のバージョンにある **XML デザイナー** とは、型指定されたデータセットおよび XML スキーマのデザイナーのことです。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="0a3cd-107">**XML デザイナー** は、XML スキーマ ファイルの作成と編集に今も使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="0a3cd-108">ただし、 [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)]では、型指定されたデータセットの作成と編集用のデザイナーは、 **データセット デザイナー**です。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-108">However, in [!INCLUDE[vs_current_long](~/includes/vs-current-long-md.md)], the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="0a3cd-109">詳細については、次を参照してください。[の作成と型指定されたデータセットの編集](/visualstudio/data-tools/creating-and-editing-typed-datasets)します。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-109">For more information, see [Creating and Editing Typed Datasets](/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0a3cd-110">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="0a3cd-110">To correct this error</span></span>  
  
-   <span data-ttu-id="0a3cd-111">正しいファイル名を指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-111">Check that you are supplying the correct file name.</span></span>  
  
-   <span data-ttu-id="0a3cd-112">確認する必要のある XML ファイルを **XML デザイナー**に読み込んで、指定したファイルに正しい XML が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="0a3cd-113">**[XML]** メニューで、 **[XML の整合性チェック]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="0a3cd-114">エラーは **[タスク一覧]** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-114">Errors are displayed in the **Task List**.</span></span>  
  
-   <span data-ttu-id="0a3cd-115">XML ファイルに関連付けられた XML スキーマがある場合は、定義された構造体にその要素が出現し、個々の要素のコンテンツがスキーマで指定された宣言されたデータ型に準拠していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a3cd-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3cd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a3cd-116">See Also</span></span>  
 <xref:System.Xml>  
 [<span data-ttu-id="0a3cd-117">方法: ファイル パスを解析する</span><span class="sxs-lookup"><span data-stu-id="0a3cd-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
