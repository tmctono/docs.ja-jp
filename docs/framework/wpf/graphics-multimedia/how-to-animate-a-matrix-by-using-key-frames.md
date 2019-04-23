---
title: '方法: キー フレームを使用して行列をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: ff5320fa5b4441ae3e0f414b274ab9118b77ec50
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336799"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="bdf49-102">方法: キー フレームを使用して行列をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="bdf49-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="bdf49-103">この例は、アニメーション化する方法を示しています。、<xref:System.Windows.Media.MatrixTransform.Matrix%2A>のプロパティを<xref:System.Windows.Media.MatrixTransform>キー フレームを使用しています。</span><span class="sxs-lookup"><span data-stu-id="bdf49-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdf49-104">例</span><span class="sxs-lookup"><span data-stu-id="bdf49-104">Example</span></span>  
 <span data-ttu-id="bdf49-105">次の例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>をアニメーション化するクラス、<xref:System.Windows.Media.MatrixTransform.Matrix%2A>のプロパティを<xref:System.Windows.Media.MatrixTransform>します。</span><span class="sxs-lookup"><span data-stu-id="bdf49-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="bdf49-106">この例では、<xref:System.Windows.Media.MatrixTransform>の位置と外観を変換するオブジェクト、<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="bdf49-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="bdf49-107">このアニメーションを使用して、<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>クラスの 2 つのキー フレームを作成して、それらを使用して、次は。</span><span class="sxs-lookup"><span data-stu-id="bdf49-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1. <span data-ttu-id="bdf49-108">最初のアニメーション<xref:System.Windows.Media.Matrix>最初 0.2 秒間にします。</span><span class="sxs-lookup"><span data-stu-id="bdf49-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="bdf49-109">例の変更、<xref:System.Windows.Media.Matrix.M11%2A>と<xref:System.Windows.Media.Matrix.M12%2A>のプロパティ、<xref:System.Windows.Media.Matrix>します。</span><span class="sxs-lookup"><span data-stu-id="bdf49-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="bdf49-110">この変更により、拡大し、傾斜するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bdf49-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="bdf49-111">また、<xref:System.Windows.Media.Matrix.OffsetX%2A>と<xref:System.Windows.Media.Matrix.OffsetY%2A>プロパティ、ボタンの位置を変更するようにします。</span><span class="sxs-lookup"><span data-stu-id="bdf49-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2. <span data-ttu-id="bdf49-112">2 番目のアニメーション<xref:System.Windows.Media.Matrix>1.0 秒。</span><span class="sxs-lookup"><span data-stu-id="bdf49-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="bdf49-113">ボタンは、ボタンが不要になった傾斜や拡大中に別の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdf49-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3. <span data-ttu-id="bdf49-114">アニメーションを無限に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="bdf49-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdf49-115">キー フレームから派生した、<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>オブジェクトの値の間に急なジャンプを作成する、つまり、アニメーションの動きはぎくしゃくします。</span><span class="sxs-lookup"><span data-stu-id="bdf49-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="bdf49-116">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdf49-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf49-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdf49-117">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [<span data-ttu-id="bdf49-118">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="bdf49-118">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="bdf49-119">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="bdf49-119">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
