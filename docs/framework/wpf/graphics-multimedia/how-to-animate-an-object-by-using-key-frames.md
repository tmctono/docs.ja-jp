---
title: '方法: キー フレームを使用してオブジェクトをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: b0a0f7c00125a43228a2658415b72f4d541f37be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315843"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="efdc5-102">方法: キー フレームを使用してオブジェクトをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="efdc5-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="efdc5-103">この例があり、この例では、オブジェクトをアニメーション化する方法を示しています、<xref:System.Windows.Controls.Page.Background%2A>のプロパティを<xref:System.Windows.Controls.Page>キー フレームを使用して、コントロール。</span><span class="sxs-lookup"><span data-stu-id="efdc5-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efdc5-104">例</span><span class="sxs-lookup"><span data-stu-id="efdc5-104">Example</span></span>  
 <span data-ttu-id="efdc5-105">次の例では、<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>の色をアニメーション化するクラスを変更、<xref:System.Windows.Controls.Page.Background%2A>のプロパティを<xref:System.Windows.Controls.Page>コントロール。</span><span class="sxs-lookup"><span data-stu-id="efdc5-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="efdc5-106">例アニメーション一定の間隔で異なる背景ブラシに変更されます。</span><span class="sxs-lookup"><span data-stu-id="efdc5-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="efdc5-107">このアニメーションを使用して、 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 3 つの異なるキー フレームを作成するクラス。</span><span class="sxs-lookup"><span data-stu-id="efdc5-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="efdc5-108">アニメーションは、次のようにキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="efdc5-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="efdc5-109">最初の 2 つ目の末尾には、インスタンスをアニメーション化、<xref:System.Windows.Media.LinearGradientBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="efdc5-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="efdc5-110">例では、このセクションでは、色が赤にオレンジ色に黄色から移行できるように、背景色に線形グラデーションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="efdc5-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="efdc5-111">次の 2 つ目の末尾には、インスタンスをアニメーション化、<xref:System.Windows.Media.RadialGradientBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="efdc5-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="efdc5-112">例では、このセクションでは、色が白から黒に青に移行できるように、背景色に放射状のグラデーションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="efdc5-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="efdc5-113">3 番目の 2 つ目の末尾には、インスタンスをアニメーション化、<xref:System.Windows.Media.DrawingBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="efdc5-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="efdc5-114">例では、このセクションでは、背景をチェッカー ボード パターンが適用されます。</span><span class="sxs-lookup"><span data-stu-id="efdc5-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="efdc5-115">アニメーションが再び開始され、無限に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="efdc5-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="efdc5-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 唯一の種類のキー フレームで使用できるは、<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>クラス。</span><span class="sxs-lookup"><span data-stu-id="efdc5-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="efdc5-117">キー フレームのような<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>値、つまり急激な変化を作成、この例では色の変更が突然発生します。</span><span class="sxs-lookup"><span data-stu-id="efdc5-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="efdc5-118">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efdc5-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdc5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="efdc5-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="efdc5-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="efdc5-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="efdc5-121">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="efdc5-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
