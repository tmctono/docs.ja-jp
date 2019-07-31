---
title: '方法: GIF イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: ec509a03d95e5f72af0b1f362e253799b07edc1f
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671689"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="d988e-102">方法: GIF イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="d988e-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="d988e-103">次の例は、特定<xref:System.Windows.Media.Imaging.GifBitmapDecoder>のオブジェクトと<xref:System.Windows.Media.Imaging.GifBitmapEncoder>オブジェクトを使用して、グラフィックスインターチェンジ形式 (GIF) イメージをデコードおよびエンコードする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d988e-103">The following examples show how to decode and encode a Graphics Interchange Format (GIF) image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d988e-104">例</span><span class="sxs-lookup"><span data-stu-id="d988e-104">Example</span></span>  
 <span data-ttu-id="d988e-105">この例では、 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> <xref:System.IO.FileStream>からを使用して GIF イメージをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d988e-105">This example demonstrates how to decode a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="d988e-106">例</span><span class="sxs-lookup"><span data-stu-id="d988e-106">Example</span></span>  
 <span data-ttu-id="d988e-107">この例では、を<xref:System.Windows.Media.Imaging.BitmapSource> <xref:System.Windows.Media.Imaging.GifBitmapEncoder>使用して、を GIF イメージにエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d988e-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d988e-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d988e-108">See also</span></span>

- [<span data-ttu-id="d988e-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="d988e-109">Imaging Overview</span></span>](imaging-overview.md)
