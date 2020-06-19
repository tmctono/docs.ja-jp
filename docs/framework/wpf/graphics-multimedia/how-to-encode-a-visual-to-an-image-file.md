---
title: '方法: ビジュアルをイメージ ファイルにエンコードする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545295"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="31b3a-102">方法: ビジュアルをイメージ ファイルにエンコードする</span><span class="sxs-lookup"><span data-stu-id="31b3a-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="31b3a-103">この例では、<xref:System.Windows.Media.Imaging.RenderTargetBitmap> と <xref:System.Windows.Media.Imaging.PngBitmapEncoder> を使用して <xref:System.Windows.Media.Visual> オブジェクトをイメージ ファイルにエンコードする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="31b3a-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31b3a-104">例</span><span class="sxs-lookup"><span data-stu-id="31b3a-104">Example</span></span>  
 <span data-ttu-id="31b3a-105"><xref:System.Windows.Media.DrawingVisual> は、<xref:System.Windows.Media.Imaging.RenderTargetBitmap> にレンダリングされる <xref:System.Windows.Media.Imaging.BitmapImage> と <xref:System.Windows.Media.FormattedText> を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="31b3a-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="31b3a-106">次に、レンダリングされたビットマップを使用して、<xref:System.Windows.Media.Imaging.PngBitmapEncoder> に追加される <xref:System.Windows.Media.Imaging.BitmapFrame> を作成して、新しいポータブル ネットワーク グラフィックス (PNG) ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31b3a-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new Portable Network Graphics (PNG) file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="31b3a-107">この例では、<xref:System.Windows.Media.Imaging.PngBitmapEncoder> を使用しましたが、派生した <xref:System.Windows.Media.Imaging.BitmapEncoder> オブジェクトのいずれかを使用してイメージ ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="31b3a-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b3a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="31b3a-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="31b3a-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="31b3a-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="31b3a-110">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="31b3a-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="31b3a-111">DrawingVisual オブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="31b3a-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
