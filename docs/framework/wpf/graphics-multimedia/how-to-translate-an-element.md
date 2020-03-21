---
title: '方法 : 要素を変換する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111973"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="9d6dd-102">方法 : 要素を変換する</span><span class="sxs-lookup"><span data-stu-id="9d6dd-102">How to: Translate an Element</span></span>
<span data-ttu-id="9d6dd-103">この例では、 を使用して要素を移動 (移動<xref:System.Windows.Media.TranslateTransform>) する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="9d6dd-104">この<xref:System.Windows.Media.TranslateTransform>クラスは、絶対位置決めをサポートしないパネル内の要素を移動する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="9d6dd-105">たとえば<xref:System.Windows.Media.TranslateTransform>、要素の<xref:System.Windows.UIElement.RenderTransform%2A>プロパティに a を適用すると、 または<xref:System.Windows.Controls.StackPanel><xref:System.Windows.Controls.DockPanel>内の要素を移動できます。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="9d6dd-106">要素を<xref:System.Windows.Media.TranslateTransform.X%2A>x<xref:System.Windows.Media.TranslateTransform>軸に沿って移動するには、のプロパティを使用してピクセル単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="9d6dd-107">y<xref:System.Windows.Media.TranslateTransform.Y%2A>軸に沿って要素を移動する量をピクセル単位で指定するには、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="9d6dd-108">最後に、要素<xref:System.Windows.Media.TranslateTransform>の<xref:System.Windows.UIElement.RenderTransform%2A>プロパティにを適用します。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="9d6dd-109">次の例では、<xref:System.Windows.Media.TranslateTransform>要素をを使用して、要素を右に 50 ピクセル、下に 50 ピクセル移動します。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d6dd-110">例</span><span class="sxs-lookup"><span data-stu-id="9d6dd-110">Example</span></span>  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="9d6dd-111">完全なサンプルについては[、2D 変換のサンプルを](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6dd-111">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6dd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d6dd-112">See also</span></span>

- [<span data-ttu-id="9d6dd-113">変換の概要</span><span class="sxs-lookup"><span data-stu-id="9d6dd-113">Transforms Overview</span></span>](transforms-overview.md)
