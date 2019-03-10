---
title: マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: bf0d3a64ce8860d67f0dcfd37c780f03fbd7471a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713266"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="2610d-102">マネージド GDI+ でのイメージ エンコーダーおよびイメージ デコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="2610d-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="2610d-103"><xref:System.Drawing>名前空間には、<xref:System.Drawing.Image>と<xref:System.Drawing.Bitmap>クラスを格納すると、画像を操作します。</span><span class="sxs-lookup"><span data-stu-id="2610d-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="2610d-104">イメージ エンコーダーを使用して[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]、メモリからディスク イメージを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="2610d-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="2610d-105">イメージのデコーダーを使用して[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]、ディスクからイメージをメモリに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2610d-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="2610d-106">エンコーダーでデータを変換する、<xref:System.Drawing.Image>または<xref:System.Drawing.Bitmap>オブジェクトが指定されたディスク ファイルの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="2610d-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="2610d-107">デコーダーがディスク ファイルで必要な形式にデータを変換、<xref:System.Drawing.Image>と<xref:System.Drawing.Bitmap>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2610d-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="2610d-108">組み込みのエンコーダーとデコーダー ファイルの種類をサポートするには。</span><span class="sxs-lookup"><span data-stu-id="2610d-108">has built-in encoders and decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="2610d-109">BMP</span><span class="sxs-lookup"><span data-stu-id="2610d-109">BMP</span></span>  
  
-   <span data-ttu-id="2610d-110">GIF</span><span class="sxs-lookup"><span data-stu-id="2610d-110">GIF</span></span>  
  
-   <span data-ttu-id="2610d-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="2610d-111">JPEG</span></span>  
  
-   <span data-ttu-id="2610d-112">PNG</span><span class="sxs-lookup"><span data-stu-id="2610d-112">PNG</span></span>  
  
-   <span data-ttu-id="2610d-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="2610d-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="2610d-114">次のファイルの種類をサポートする組み込みのデコーダーがあります。</span><span class="sxs-lookup"><span data-stu-id="2610d-114">also has built-in decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="2610d-115">WMF</span><span class="sxs-lookup"><span data-stu-id="2610d-115">WMF</span></span>  
  
-   <span data-ttu-id="2610d-116">EMF</span><span class="sxs-lookup"><span data-stu-id="2610d-116">EMF</span></span>  
  
-   <span data-ttu-id="2610d-117">アイコン</span><span class="sxs-lookup"><span data-stu-id="2610d-117">ICON</span></span>  
  
 <span data-ttu-id="2610d-118">次のトピックでは、エンコーダーとデコーダーの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="2610d-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2610d-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2610d-119">In This Section</span></span>  
 [<span data-ttu-id="2610d-120">方法: インストールされたエンコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="2610d-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="2610d-121">コンピューターで使用可能なエンコーダーの一覧を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2610d-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="2610d-122">方法: インストールされたデコーダーの一覧</span><span class="sxs-lookup"><span data-stu-id="2610d-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="2610d-123">コンピューターで使用可能なデコーダーの一覧を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2610d-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="2610d-124">方法: エンコーダーがサポートするパラメーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="2610d-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="2610d-125">一覧表示する方法について説明します、<xref:System.Drawing.Imaging.EncoderParameters>エンコーダーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2610d-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="2610d-126">方法: BMP イメージを PNG イメージに変換します。</span><span class="sxs-lookup"><span data-stu-id="2610d-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="2610d-127">さまざまなイメージ形式でイメージを保存する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2610d-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="2610d-128">方法: JPEG 圧縮レベルの設定します。</span><span class="sxs-lookup"><span data-stu-id="2610d-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="2610d-129">イメージの品質レベルを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2610d-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2610d-130">参照</span><span class="sxs-lookup"><span data-stu-id="2610d-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="2610d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="2610d-131">Related Sections</span></span>  
 [<span data-ttu-id="2610d-132">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="2610d-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="2610d-133">イメージ、ビットマップ、メタファイル</span><span class="sxs-lookup"><span data-stu-id="2610d-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
