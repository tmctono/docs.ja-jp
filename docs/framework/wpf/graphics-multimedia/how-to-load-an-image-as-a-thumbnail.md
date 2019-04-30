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
ms.openlocfilehash: f984293a395e925368b20cef6aa0cd902bd6fc15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003185"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="0fbc3-102">方法: サムネイルとしてイメージを読み込む</span><span class="sxs-lookup"><span data-stu-id="0fbc3-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="0fbc3-103">次の例を読み込む方法を示して、<xref:System.Windows.Controls.Image>アプリケーション メモリを節約するサムネイルとして。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fbc3-104">例</span><span class="sxs-lookup"><span data-stu-id="0fbc3-104">Example</span></span>  
 <span data-ttu-id="0fbc3-105">次の例のセット、<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>のプロパティを<xref:System.Windows.Media.Imaging.BitmapImage>で[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]イメージの読み込みに必要なメモリを削減します。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="0fbc3-106">例</span><span class="sxs-lookup"><span data-stu-id="0fbc3-106">Example</span></span>  
 <span data-ttu-id="0fbc3-107">次の例のセット、<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>のプロパティを<xref:System.Windows.Media.Imaging.BitmapImage>コードに、イメージの読み込みに必要なメモリ量を減らします。</span><span class="sxs-lookup"><span data-stu-id="0fbc3-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="0fbc3-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fbc3-108">See also</span></span>

- [<span data-ttu-id="0fbc3-109">イメージングの概要</span><span class="sxs-lookup"><span data-stu-id="0fbc3-109">Imaging Overview</span></span>](imaging-overview.md)
