---
title: GDI+ でのメタファイル
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: 7562de76d3875e25404a6aef68355f120184b840
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627617"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="a58e9-102">GDI+ でのメタファイル</span><span class="sxs-lookup"><span data-stu-id="a58e9-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a58e9-103">提供、<xref:System.Drawing.Imaging.Metafile>クラスに記録し、メタファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a58e9-103">provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="a58e9-104">ベクター イメージとも呼ばれる、メタファイルは、一連の描画コマンドと設定として格納されているイメージです。</span><span class="sxs-lookup"><span data-stu-id="a58e9-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="a58e9-105">コマンドおよび設定に記録する<xref:System.Drawing.Imaging.Metafile>オブジェクトをメモリに格納されているか、ファイルまたはストリームに保存します。</span><span class="sxs-lookup"><span data-stu-id="a58e9-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="a58e9-106">メタファイル形式</span><span class="sxs-lookup"><span data-stu-id="a58e9-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a58e9-107">次の形式で格納されているメタファイルを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a58e9-107">can display metafiles that have been stored in the following formats:</span></span>  
  
-   <span data-ttu-id="a58e9-108">Windows メタファイル (WMF)</span><span class="sxs-lookup"><span data-stu-id="a58e9-108">Windows Metafile (WMF)</span></span>  
  
-   <span data-ttu-id="a58e9-109">拡張メタファイル (EMF)</span><span class="sxs-lookup"><span data-stu-id="a58e9-109">Enhanced Metafile (EMF)</span></span>  
  
-   <span data-ttu-id="a58e9-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="a58e9-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a58e9-111">WMF の形式ではなく、EMF、EMF + 形式には、メタファイルを記録できます。</span><span class="sxs-lookup"><span data-stu-id="a58e9-111">can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="a58e9-112">EMF + は、拡張機能により、EMF[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]レコードが格納されます。</span><span class="sxs-lookup"><span data-stu-id="a58e9-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="a58e9-113">EMF + 形式の 2 つのバリエーションがあります。EMF + のみと EMF + Dual します。</span><span class="sxs-lookup"><span data-stu-id="a58e9-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="a58e9-114">メタファイル EMF + だけしか[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]レコード。</span><span class="sxs-lookup"><span data-stu-id="a58e9-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="a58e9-115">このようなメタファイルで表示できる[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]がなく、[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a58e9-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="a58e9-116">EMF + Dual メタファイルを含む[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]と[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]レコード。</span><span class="sxs-lookup"><span data-stu-id="a58e9-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="a58e9-117">各[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]EMF + Dual レコード メタファイルとペアになって、代替[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]レコード。</span><span class="sxs-lookup"><span data-stu-id="a58e9-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="a58e9-118">このようなメタファイルで表示できる[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]または[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a58e9-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="a58e9-119">次の例では、ファイルとして保存された以前メタファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="a58e9-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="a58e9-120">左上隅にあるとメタファイルが表示されます (100, 100)。</span><span class="sxs-lookup"><span data-stu-id="a58e9-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="a58e9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a58e9-121">See also</span></span>
- [<span data-ttu-id="a58e9-122">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="a58e9-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
