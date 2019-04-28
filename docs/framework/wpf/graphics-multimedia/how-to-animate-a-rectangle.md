---
title: '方法: 四角形をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
ms.openlocfilehash: 7f7cf24f7883553329de3761ff0670e8e3a09463
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760910"
---
# <a name="how-to-animate-a-rectangle"></a><span data-ttu-id="1cb64-102">方法: 四角形をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="1cb64-102">How to: Animate a Rectangle</span></span>
<span data-ttu-id="1cb64-103">この例では、四角形のサイズと位置の変化をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1cb64-103">This example shows how to animate changes to the size and position of a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cb64-104">例</span><span class="sxs-lookup"><span data-stu-id="1cb64-104">Example</span></span>  
 <span data-ttu-id="1cb64-105">次の例のインスタンスを使用して、<xref:System.Windows.Media.Animation.RectAnimation>をアニメーション化するクラス、<xref:System.Windows.Media.RectangleGeometry.Rect%2A>のプロパティを<xref:System.Windows.Media.RectangleGeometry>、四角形の位置とサイズの変更をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="1cb64-105">The following example uses an instance of the <xref:System.Windows.Media.Animation.RectAnimation> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>, which animates changes to the size and position of the rectangle.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1cb64-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cb64-106">See also</span></span>

- <xref:System.Windows.Media.Animation.RectAnimation>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.RectangleGeometry>
- [<span data-ttu-id="1cb64-107">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="1cb64-107">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="1cb64-108">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="1cb64-108">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="1cb64-109">グラフィックスの操作方法に関するトピック</span><span class="sxs-lookup"><span data-stu-id="1cb64-109">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="1cb64-110">アニメーションとタイミングに関するトピック</span><span class="sxs-lookup"><span data-stu-id="1cb64-110">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
