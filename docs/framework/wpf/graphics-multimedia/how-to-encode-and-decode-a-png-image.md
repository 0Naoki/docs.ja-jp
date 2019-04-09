---
title: '方法: PNG イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- PNG encoding [WPF]
- decoding PNG images [WPF]
- PNG decoding [WPF]
- encoding image formats [WPF]
- decoding image formats [WPF]
- encoding PNG images [WPF]
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
ms.openlocfilehash: 46d4a7ffbfe7a6a620c26447cce30f3a0bd35adc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090854"
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="7dcb5-102">方法: PNG イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="7dcb5-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="7dcb5-103">次の例では、デコードおよびエンコードする方法、[!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)]特定を使用するイメージ<xref:System.Windows.Media.Imaging.PngBitmapDecoder>と<xref:System.Windows.Media.Imaging.PngBitmapEncoder>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7dcb5-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dcb5-104">例</span><span class="sxs-lookup"><span data-stu-id="7dcb5-104">Example</span></span>  
 <span data-ttu-id="7dcb5-105">デコードする方法を示します、[!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)]イメージを使用して、<xref:System.Windows.Media.Imaging.PngBitmapDecoder>から、<xref:System.IO.FileStream>します。</span><span class="sxs-lookup"><span data-stu-id="7dcb5-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="7dcb5-106">例</span><span class="sxs-lookup"><span data-stu-id="7dcb5-106">Example</span></span>  
 <span data-ttu-id="7dcb5-107">エンコードする方法を示します、<xref:System.Windows.Media.Imaging.BitmapSource>に、[!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)]イメージを使用して、<xref:System.Windows.Media.Imaging.PngBitmapEncoder>します。</span><span class="sxs-lookup"><span data-stu-id="7dcb5-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="7dcb5-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dcb5-108">See also</span></span>

- [<span data-ttu-id="7dcb5-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="7dcb5-109">Imaging Overview</span></span>](imaging-overview.md)
