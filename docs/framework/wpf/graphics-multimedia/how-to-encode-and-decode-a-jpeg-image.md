---
title: '方法: エンコードおよびデコードの JPEG 画像'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 0f64ef8537f22ea996cbcf274885de1f3968267a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373791"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="5373a-102">方法: エンコードおよびデコードの JPEG 画像</span><span class="sxs-lookup"><span data-stu-id="5373a-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="5373a-103">次の例は、デコード、および特定を使用して、JPEG イメージをエンコードする方法を示します<xref:System.Windows.Media.Imaging.JpegBitmapDecoder>と<xref:System.Windows.Media.Imaging.JpegBitmapEncoder>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5373a-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="5373a-104">例: JPEG イメージのデコード</span><span class="sxs-lookup"><span data-stu-id="5373a-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="5373a-105">この例を使用して JPEG イメージをデコードする方法、<xref:System.Windows.Media.Imaging.JpegBitmapDecoder>から、<xref:System.IO.FileStream>します。</span><span class="sxs-lookup"><span data-stu-id="5373a-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="5373a-106">例: JPEG イメージのエンコード</span><span class="sxs-lookup"><span data-stu-id="5373a-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="5373a-107">この例では、エンコード、<xref:System.Windows.Media.Imaging.BitmapSource>に JPEG イメージを使用して、 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>。</span><span class="sxs-lookup"><span data-stu-id="5373a-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5373a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="5373a-108">See also</span></span>

- [<span data-ttu-id="5373a-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="5373a-109">Imaging Overview</span></span>](imaging-overview.md)
