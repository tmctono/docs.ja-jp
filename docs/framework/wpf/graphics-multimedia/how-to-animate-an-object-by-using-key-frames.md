---
title: '方法: キー フレームを使用してオブジェクトをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933906"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="ab31a-102">方法: キー フレームを使用してオブジェクトをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ab31a-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="ab31a-103">この例では、キーフレームを使用して、オブジェクト (この<xref:System.Windows.Controls.Page.Background%2A>例では<xref:System.Windows.Controls.Page>コントロールのプロパティ) をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab31a-104">例</span><span class="sxs-lookup"><span data-stu-id="ab31a-104">Example</span></span>  
 <span data-ttu-id="ab31a-105">次の例では<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 、クラスを使用して、 <xref:System.Windows.Controls.Page.Background%2A> <xref:System.Windows.Controls.Page>コントロールのプロパティの色の変更をアニメーション化しています。</span><span class="sxs-lookup"><span data-stu-id="ab31a-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="ab31a-106">この例のアニメーションは、一定の間隔で別の背景ブラシに変わります。</span><span class="sxs-lookup"><span data-stu-id="ab31a-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="ab31a-107">このアニメーションでは<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 、クラスを使用して、3つの異なるキーフレームを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="ab31a-108">アニメーションは、次の方法でキーフレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="ab31a-109">最初の秒の最後に、 <xref:System.Windows.Media.LinearGradientBrush>クラスのインスタンスをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="ab31a-110">この例のこのセクションでは、色が黄色からオレンジ色に変化するように、背景色に線状グラデーションを適用します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="ab31a-111">次の秒の最後に、 <xref:System.Windows.Media.RadialGradientBrush>クラスのインスタンスをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="ab31a-112">この例のこのセクションでは、色が白から青に変化するように背景色に放射状グラデーションを適用します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="ab31a-113">3番目の秒の最後に、 <xref:System.Windows.Media.DrawingBrush>クラスのインスタンスをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="ab31a-114">この例のこのセクションでは、背景にチェッカーボードパターンを適用します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="ab31a-115">アニメーションは再び開始され、無限に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="ab31a-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab31a-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>は、 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>クラスで使用できるキーフレームの唯一の種類です。</span><span class="sxs-lookup"><span data-stu-id="ab31a-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="ab31a-117">値が急激<xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>に変化するようなキーフレーム (この例の色の変化) は突然発生します。</span><span class="sxs-lookup"><span data-stu-id="ab31a-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="ab31a-118">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab31a-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab31a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab31a-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="ab31a-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="ab31a-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="ab31a-121">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="ab31a-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
