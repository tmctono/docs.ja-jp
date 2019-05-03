---
title: '方法: 純色で領域を塗りつぶす'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: c85ba72c858d155f29875bb944824db1c44ffaab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922630"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="7f891-102">方法: 純色で領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="7f891-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="7f891-103">純色で領域を塗りつぶすに、使用できる、定義済みのシステム ブラシなど<xref:System.Windows.Media.Brushes.Red%2A>または<xref:System.Windows.Media.Brushes.Blue%2A>、新規に作成することができますか<xref:System.Windows.Media.SolidColorBrush>について説明してその<xref:System.Windows.Media.SolidColorBrush.Color%2A>アルファ、赤、緑、および青の値を使用して。</span><span class="sxs-lookup"><span data-stu-id="7f891-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="7f891-104">XAML では、16 進数表記を使用して、純色で領域を塗りつぶすこともできます。</span><span class="sxs-lookup"><span data-stu-id="7f891-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="7f891-105">次の例では、これらの手法を使用を描画する、<xref:System.Windows.Shapes.Rectangle>青。</span><span class="sxs-lookup"><span data-stu-id="7f891-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f891-106">例</span><span class="sxs-lookup"><span data-stu-id="7f891-106">Example</span></span>  
 <span data-ttu-id="7f891-107">**定義済みのブラシの使用**</span><span class="sxs-lookup"><span data-stu-id="7f891-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="7f891-108">次の例では、定義済みのブラシを使用して<xref:System.Windows.Media.Brushes.Blue%2A>青い四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="7f891-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="7f891-109">**16 進数表記の使用**</span><span class="sxs-lookup"><span data-stu-id="7f891-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="7f891-110">次の例では、8 桁の 16 進数表記を使用して、四角形を青で塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="7f891-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="7f891-111">**ARGB 値の使用**</span><span class="sxs-lookup"><span data-stu-id="7f891-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="7f891-112">次の例では、作成、<xref:System.Windows.Media.SolidColorBrush>について説明しますと、 <xref:System.Windows.Media.SolidColorBrush.Color%2A> ARGB を使用して、色の青の値します。</span><span class="sxs-lookup"><span data-stu-id="7f891-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="7f891-113">他の色を記述する方法についてを参照してください。、<xref:System.Windows.Media.Color>構造体。</span><span class="sxs-lookup"><span data-stu-id="7f891-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="7f891-114">**関連トピック**</span><span class="sxs-lookup"><span data-stu-id="7f891-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="7f891-115"><xref:System.Windows.Media.SolidColorBrush> やその他の例の詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f891-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="7f891-116">このコード例が示されている例の一部、<xref:System.Windows.Media.SolidColorBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="7f891-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="7f891-117">完全なサンプルについては、「[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7f891-117">For the complete sample, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f891-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f891-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
