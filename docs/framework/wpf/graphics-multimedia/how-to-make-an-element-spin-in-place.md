---
title: '方法 : 要素のスピンを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112077"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="cad64-102">方法 : 要素のスピンを設定する</span><span class="sxs-lookup"><span data-stu-id="cad64-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="cad64-103">この例では、<xref:System.Windows.Media.RotateTransform>および を使用して要素をスピンさせる<xref:System.Windows.Media.Animation.DoubleAnimation>方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cad64-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="cad64-104">要素のプロパティに<xref:System.Windows.Media.RotateTransform>を適用<xref:System.Windows.UIElement.RenderTransform%2A>する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cad64-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="cad64-105">この例では、<xref:System.Windows.Media.Animation.DoubleAnimation>の アニメーション<xref:System.Windows.Media.RotateTransform.Angle%2A>を行うために<xref:System.Windows.Media.RotateTransform>を使用します。</span><span class="sxs-lookup"><span data-stu-id="cad64-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="cad64-106">要素を所定の位置で回転させるために、要素の<xref:System.Windows.UIElement.RenderTransformOrigin%2A>プロパティをポイント(0.5,0.5)に設定します。</span><span class="sxs-lookup"><span data-stu-id="cad64-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cad64-107">例</span><span class="sxs-lookup"><span data-stu-id="cad64-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="cad64-108">その他の変換例を含む完全なサンプルについては[、「2D 変換のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad64-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad64-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="cad64-109">See also</span></span>

- [<span data-ttu-id="cad64-110">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="cad64-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="cad64-111">変換の概要</span><span class="sxs-lookup"><span data-stu-id="cad64-111">Transforms Overview</span></span>](transforms-overview.md)
