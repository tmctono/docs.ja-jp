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
ms.openlocfilehash: 7d3520a1b1913fe68fedb0ea9d76cc138ed661c4
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331733"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="89b14-102">方法: BMP イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="89b14-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="89b14-103">次の例は、特定<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>のオブジェクトと<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>オブジェクトを使用してビットマップ (BMP) イメージをデコードおよびエンコードする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="89b14-103">The following examples show how to decode and encode a bitmap (BMP) image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89b14-104">例</span><span class="sxs-lookup"><span data-stu-id="89b14-104">Example</span></span>  
 <span data-ttu-id="89b14-105">この例では、 <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> <xref:System.Uri>からを使用して BMP イメージをデコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="89b14-105">This example demonstrates how to decode a BMP image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="89b14-106">例</span><span class="sxs-lookup"><span data-stu-id="89b14-106">Example</span></span>  
 <span data-ttu-id="89b14-107">この例では、を<xref:System.Windows.Media.Imaging.BitmapSource> <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>使用して、を BMP イメージにエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="89b14-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a BMP image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="89b14-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="89b14-108">See also</span></span>

- [<span data-ttu-id="89b14-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="89b14-109">Imaging Overview</span></span>](imaging-overview.md)
