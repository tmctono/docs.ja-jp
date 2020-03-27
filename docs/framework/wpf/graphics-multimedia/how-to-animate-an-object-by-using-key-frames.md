---
title: '方法 : キー フレームを使用してオブジェクトをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344702"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="aa0b9-102">方法 : キー フレームを使用してオブジェクトをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="aa0b9-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="aa0b9-103">この例では、キー フレームを使用してコントロールの<xref:System.Windows.Controls.Page.Background%2A>プロパティであるオブジェクトをアニメーション化する方法<xref:System.Windows.Controls.Page>を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa0b9-104">例</span><span class="sxs-lookup"><span data-stu-id="aa0b9-104">Example</span></span>  
 <span data-ttu-id="aa0b9-105">次の例では、<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>このクラスを使用して、コントロールのプロパティ<xref:System.Windows.Controls.Page.Background%2A>の色の<xref:System.Windows.Controls.Page>変更をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="aa0b9-106">アニメーション例は、一定の間隔で別の背景ブラシに変更されます。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="aa0b9-107">このアニメーションでは、<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>クラスを使用して 3 つの異なるキー フレームを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="aa0b9-108">アニメーションでは、次のようにキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="aa0b9-109">最初の 1 秒目の終わりに、クラスのインスタンスを<xref:System.Windows.Media.LinearGradientBrush>アニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="aa0b9-110">このセクションでは、背景色に線形グラデーションを適用し、色が黄色からオレンジ色から赤に変わります。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="aa0b9-111">次の 1 秒の終わりに、クラスのインスタンスをアニメーション<xref:System.Windows.Media.RadialGradientBrush>化します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="aa0b9-112">このセクションでは、背景色に放射状グラデーションを適用し、色が白から青から黒に変わります。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="aa0b9-113">3 秒目の終わりに、クラスのインスタンスをアニメーション化します<xref:System.Windows.Media.DrawingBrush>。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="aa0b9-114">このセクションでは、背景にチェッカーボードパターンを適用します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="aa0b9-115">アニメーションは再び開始され、無限に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa0b9-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>は、クラスで使用できる唯一のタイプのキー<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>フレームです。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="aa0b9-117">キー フレーム<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>のような値の急激な変化、つまりこの例の色の変化が突然発生します。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="aa0b9-118">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa0b9-118">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0b9-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa0b9-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="aa0b9-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="aa0b9-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="aa0b9-121">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="aa0b9-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
