---
title: '方法: 要素のスピンを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2eaca5ba75eb8ac2eeb375a177c08659a65af2db
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371503"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="c692a-102">方法: 要素のスピンを設定する</span><span class="sxs-lookup"><span data-stu-id="c692a-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="c692a-103">この例は、スピンを使用して要素を作成する方法を示しています、<xref:System.Windows.Media.RotateTransform>と<xref:System.Windows.Media.Animation.DoubleAnimation>します。</span><span class="sxs-lookup"><span data-stu-id="c692a-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="c692a-104">次の例では、適用、<xref:System.Windows.Media.RotateTransform>を<xref:System.Windows.UIElement.RenderTransform%2A>要素のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c692a-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="c692a-105">この例では、<xref:System.Windows.Media.Animation.DoubleAnimation>をアニメーション化する、<xref:System.Windows.Media.RotateTransform.Angle%2A>の<xref:System.Windows.Media.RotateTransform>します。</span><span class="sxs-lookup"><span data-stu-id="c692a-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="c692a-106">例を設定するために、スピンが要素、<xref:System.Windows.UIElement.RenderTransformOrigin%2A>ポイント (0.5, 0.5) に要素のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="c692a-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c692a-107">例</span><span class="sxs-lookup"><span data-stu-id="c692a-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="c692a-108">例については変換が含まれているサンプル全体については、次を参照してください。 [2-d 変換のサンプル](https://go.microsoft.com/fwlink/?LinkID=158252)します。</span><span class="sxs-lookup"><span data-stu-id="c692a-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c692a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c692a-109">See also</span></span>
- [<span data-ttu-id="c692a-110">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="c692a-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c692a-111">変換の概要</span><span class="sxs-lookup"><span data-stu-id="c692a-111">Transforms Overview</span></span>](transforms-overview.md)
