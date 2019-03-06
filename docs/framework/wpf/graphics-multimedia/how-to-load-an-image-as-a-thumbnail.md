---
title: '方法: サムネイルとしてイメージを読み込む'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: 0b5435e9b06f37dae7dc762e9035b1eca8156ca6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353389"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="c2741-102">方法: サムネイルとしてイメージを読み込む</span><span class="sxs-lookup"><span data-stu-id="c2741-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="c2741-103">次の例を読み込む方法を示して、<xref:System.Windows.Controls.Image>アプリケーション メモリを節約するサムネイルとして。</span><span class="sxs-lookup"><span data-stu-id="c2741-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2741-104">例</span><span class="sxs-lookup"><span data-stu-id="c2741-104">Example</span></span>  
 <span data-ttu-id="c2741-105">次の例のセット、<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>のプロパティを<xref:System.Windows.Media.Imaging.BitmapImage>で[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]イメージの読み込みに必要なメモリを削減します。</span><span class="sxs-lookup"><span data-stu-id="c2741-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="c2741-106">例</span><span class="sxs-lookup"><span data-stu-id="c2741-106">Example</span></span>  
 <span data-ttu-id="c2741-107">次の例のセット、<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>のプロパティを<xref:System.Windows.Media.Imaging.BitmapImage>コードに、イメージの読み込みに必要なメモリ量を減らします。</span><span class="sxs-lookup"><span data-stu-id="c2741-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="c2741-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2741-108">See also</span></span>
- [<span data-ttu-id="c2741-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="c2741-109">Imaging Overview</span></span>](imaging-overview.md)
