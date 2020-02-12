---
title: '方法 : BorderThickness 値をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124664"
---
# <a name="how-to-animate-a-borderthickness-value"></a><span data-ttu-id="939ed-102">方法 : BorderThickness 値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="939ed-102">How to: Animate a BorderThickness Value</span></span>
<span data-ttu-id="939ed-103">この例では、<xref:System.Windows.Media.Animation.ThicknessAnimation> クラスを使用して、境界線の太さに対する変更をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="939ed-103">This example shows how to animate changes to the thickness of a border by using the <xref:System.Windows.Media.Animation.ThicknessAnimation> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="939ed-104">例</span><span class="sxs-lookup"><span data-stu-id="939ed-104">Example</span></span>  
 <span data-ttu-id="939ed-105">次の例では、<xref:System.Windows.Media.Animation.ThicknessAnimation>を使用して、境界線の太さをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="939ed-105">The following example animates the thickness of a border by using <xref:System.Windows.Media.Animation.ThicknessAnimation>.</span></span> <span data-ttu-id="939ed-106">この例では、<xref:System.Windows.Controls.Border>の <xref:System.Windows.Controls.Border.BorderThickness%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="939ed-106">The example uses the <xref:System.Windows.Controls.Border.BorderThickness%2A> property of <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 <span data-ttu-id="939ed-107">完全なサンプルについては、「アニメーションのサンプル[ギャラリー](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939ed-107">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="939ed-108">参照</span><span class="sxs-lookup"><span data-stu-id="939ed-108">See also</span></span>

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="939ed-109">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="939ed-109">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="939ed-110">アニメーションとタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="939ed-110">Animation and Timing How-to Topics</span></span>](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="939ed-111">キー フレームを使用して境界線の太さをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="939ed-111">Animate the Thickness of a Border by Using Key Frames</span></span>](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
