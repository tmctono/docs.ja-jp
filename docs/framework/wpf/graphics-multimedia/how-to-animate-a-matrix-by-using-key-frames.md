---
title: '方法 : キー フレームを使用して行列をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344915"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="aacdb-102">方法 : キー フレームを使用して行列をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="aacdb-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="aacdb-103">この例では、キー フレームを使用<xref:System.Windows.Media.MatrixTransform.Matrix%2A>して a<xref:System.Windows.Media.MatrixTransform>のプロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aacdb-104">例</span><span class="sxs-lookup"><span data-stu-id="aacdb-104">Example</span></span>  
 <span data-ttu-id="aacdb-105">次の例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>クラスを使用して、<xref:System.Windows.Media.MatrixTransform.Matrix%2A>のプロパティを<xref:System.Windows.Media.MatrixTransform>アニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="aacdb-106">この例では、<xref:System.Windows.Media.MatrixTransform>オブジェクトを使用して、 の外観と<xref:System.Windows.Controls.Button>位置を変換します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="aacdb-107">このアニメーションでは、<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>クラスを使用して 2 つのキー フレームを作成し、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="aacdb-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="aacdb-108">最初の 0.2 秒間に最初<xref:System.Windows.Media.Matrix>のアニメーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="aacdb-109">この例では、 <xref:System.Windows.Media.Matrix.M11%2A> <xref:System.Windows.Media.Matrix.M12%2A>の プロパティ<xref:System.Windows.Media.Matrix>と プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="aacdb-110">この変更により、ボタンが伸びて傾斜します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="aacdb-111">また、ボタンの位置<xref:System.Windows.Media.Matrix.OffsetX%2A>が<xref:System.Windows.Media.Matrix.OffsetY%2A>変更されるように、 および プロパティも変更します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="aacdb-112">2 番目<xref:System.Windows.Media.Matrix>のアニメーションを 1.0 秒でアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="aacdb-113">ボタンが傾斜または伸びない間、ボタンが別の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="aacdb-114">アニメーションを無期限に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aacdb-115">オブジェクトから派生した<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>キーフレームは、値の間に突然ジャンプを作成します。</span><span class="sxs-lookup"><span data-stu-id="aacdb-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="aacdb-116">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aacdb-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aacdb-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="aacdb-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="aacdb-118">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="aacdb-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="aacdb-119">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="aacdb-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
