---
title: '方法: BMP イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: b7d5ace8aead864cb69a9e696a3f1f925e232600
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947642"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="ea523-102">方法: BMP イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="ea523-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="ea523-103">次の例では、デコードおよびエンコードする方法、[!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)]特定を使用するイメージ<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>と<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ea523-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea523-104">例</span><span class="sxs-lookup"><span data-stu-id="ea523-104">Example</span></span>  
 <span data-ttu-id="ea523-105">デコードする方法を示します、[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]イメージを使用して、<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>から、<xref:System.Uri>します。</span><span class="sxs-lookup"><span data-stu-id="ea523-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ea523-106">例</span><span class="sxs-lookup"><span data-stu-id="ea523-106">Example</span></span>  
 <span data-ttu-id="ea523-107">エンコードする方法を示します、<xref:System.Windows.Media.Imaging.BitmapSource>に、[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]イメージを使用して、<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>します。</span><span class="sxs-lookup"><span data-stu-id="ea523-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ea523-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea523-108">See also</span></span>

- [<span data-ttu-id="ea523-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="ea523-109">Imaging Overview</span></span>](imaging-overview.md)
