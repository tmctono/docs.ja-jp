---
title: '方法: イメージをトリミングする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: e672c7e24ec4db2d6424fa0b611cb1c135cf8eec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053393"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="61eb0-102">方法: イメージをトリミングする</span><span class="sxs-lookup"><span data-stu-id="61eb0-102">How to: Crop an Image</span></span>
<span data-ttu-id="61eb0-103">この例では、<xref:System.Windows.Media.Imaging.CroppedBitmap> を使用してイメージをトリミングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61eb0-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="61eb0-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> は主に、トリミングしたイメージをエンコードしてファイルに保存するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="61eb0-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="61eb0-105">表示目的でイメージをトリミングする方法については、「[方法: クリップ領域を作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61eb0-105">To crop an image for display purposes see the [How to: Create a Clip Region](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61eb0-106">例</span><span class="sxs-lookup"><span data-stu-id="61eb0-106">Example</span></span>  
 <span data-ttu-id="61eb0-107">次の [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] では、以下のサンプル内で使用されるリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="61eb0-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="61eb0-108">次の例では、そのソースとして <xref:System.Windows.Media.Imaging.CroppedBitmap> を使用し、イメージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="61eb0-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="61eb0-109"><xref:System.Windows.Media.Imaging.CroppedBitmap> は別の <xref:System.Windows.Media.Imaging.CroppedBitmap> のソースとして利用し、トリミングを連結することもできます。</span><span class="sxs-lookup"><span data-stu-id="61eb0-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="61eb0-110"><xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> では、最初のイメージではなく、ソースのトリミングされたビットマップの相対値が使用されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="61eb0-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="61eb0-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="61eb0-111">See also</span></span>

- <span data-ttu-id="61eb0-112">[方法: クリップ領域を作成する](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="61eb0-112">[How to: Create a Clip Region](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))</span></span>
