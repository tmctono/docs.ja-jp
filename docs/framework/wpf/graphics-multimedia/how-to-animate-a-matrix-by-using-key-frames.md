---
title: '方法: キー フレームを使用して行列をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963025"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="784d0-102">方法: キー フレームを使用して行列をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="784d0-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="784d0-103">この例では、 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform>キーフレームを使用してのプロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="784d0-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="784d0-104">例</span><span class="sxs-lookup"><span data-stu-id="784d0-104">Example</span></span>  
 <span data-ttu-id="784d0-105"><xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>クラスを使用しての<xref:System.Windows.Media.MatrixTransform.Matrix%2A> <xref:System.Windows.Media.MatrixTransform>プロパティをアニメーション化する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="784d0-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="784d0-106">この例では<xref:System.Windows.Media.MatrixTransform> 、オブジェクトを使用して、 <xref:System.Windows.Controls.Button>の外観と位置を変換します。</span><span class="sxs-lookup"><span data-stu-id="784d0-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="784d0-107">このアニメーションでは<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 、クラスを使用して2つのキーフレームを作成し、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="784d0-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="784d0-108">最初の 0.2 <xref:System.Windows.Media.Matrix>秒間に最初のをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="784d0-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="784d0-109">この例では<xref:System.Windows.Media.Matrix.M11%2A> 、 <xref:System.Windows.Media.Matrix.M12%2A>の<xref:System.Windows.Media.Matrix>プロパティとプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="784d0-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="784d0-110">この変更により、ボタンが伸縮され、傾斜します。</span><span class="sxs-lookup"><span data-stu-id="784d0-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="784d0-111">また、この例で<xref:System.Windows.Media.Matrix.OffsetX%2A>は<xref:System.Windows.Media.Matrix.OffsetY%2A> 、ボタンが位置を変更するようにプロパティとプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="784d0-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="784d0-112">2番目<xref:System.Windows.Media.Matrix>のを1.0 秒でアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="784d0-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="784d0-113">ボタンが傾斜または拡大されていなくても、ボタンは別の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="784d0-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="784d0-114">アニメーションを無制限に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="784d0-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="784d0-115"><xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>オブジェクトから派生したキーフレームは、値の間に急激なジャンプを作成します。つまり、アニメーションの動きが不自然になります。</span><span class="sxs-lookup"><span data-stu-id="784d0-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="784d0-116">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="784d0-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="784d0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="784d0-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="784d0-118">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="784d0-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="784d0-119">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="784d0-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
