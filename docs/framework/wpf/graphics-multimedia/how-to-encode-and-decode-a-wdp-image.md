---
title: '方法: WDP イメージのエンコードおよびデコード'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WDP encoding [WPF]
- WDP decoding [WPF]
- encoding image formats [WPF]
- decoding WDP images [WPF]
- decoding image formats [WPF]
- encoding WDP images [WPF]
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
ms.openlocfilehash: b143106092235b42044d264189c135d2cd65426c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947525"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a><span data-ttu-id="d8d37-102">方法: WDP イメージのエンコードおよびデコード</span><span class="sxs-lookup"><span data-stu-id="d8d37-102">How to: Encode and Decode a WDP Image</span></span>
<span data-ttu-id="d8d37-103">次の例では、デコードおよびエンコードする方法、[!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)]特定を使用するイメージ<xref:System.Windows.Media.Imaging.WmpBitmapDecoder>と<xref:System.Windows.Media.Imaging.WmpBitmapEncoder>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d8d37-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8d37-104">例</span><span class="sxs-lookup"><span data-stu-id="d8d37-104">Example</span></span>  
 <span data-ttu-id="d8d37-105">デコードする方法を示します、[!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)]イメージを使用して、<xref:System.Windows.Media.Imaging.WmpBitmapDecoder>から、<xref:System.Uri>します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="d8d37-106">例</span><span class="sxs-lookup"><span data-stu-id="d8d37-106">Example</span></span>  
 <span data-ttu-id="d8d37-107">エンコードする方法を示します、<xref:System.Windows.Media.Imaging.BitmapSource>に、[!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)]イメージを使用して、<xref:System.Windows.Media.Imaging.WmpBitmapEncoder>します。</span><span class="sxs-lookup"><span data-stu-id="d8d37-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d8d37-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8d37-108">See also</span></span>

- [<span data-ttu-id="d8d37-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="d8d37-109">Imaging Overview</span></span>](imaging-overview.md)
