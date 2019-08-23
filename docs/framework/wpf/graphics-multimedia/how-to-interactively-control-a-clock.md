---
title: '方法: クロックを対話的に制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951346"
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="6c30a-102">方法: クロックを対話的に制御する</span><span class="sxs-lookup"><span data-stu-id="6c30a-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="6c30a-103">オブジェクト<xref:System.Windows.Media.Animation.Clock> の<xref:System.Windows.Media.Animation.ClockController>プロパティを使用すると、対話形式で開始、一時停止、再開、シーク、時計をその塗りつぶし期間に進め、時計を止めることができます。</span><span class="sxs-lookup"><span data-stu-id="6c30a-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="6c30a-104">タイミングツリーのルートクロックだけを対話式で制御できます。</span><span class="sxs-lookup"><span data-stu-id="6c30a-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c30a-105">クロックを直接操作する必要のないアニメーションを対話的に制御する方法は他にもあります。ストーリーボードを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c30a-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="6c30a-106">ストーリーボードは、マークアップとコードの両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c30a-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="6c30a-107">例については、「ストーリーボードまたは[アニメーションの概要](animation-overview.md)を使用して[プロパティをアニメーション化](how-to-animate-a-property-by-using-a-storyboard.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c30a-107">For an example, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="6c30a-108">次の例では、いくつかのボタンを使用して、アニメーションクロックを対話的に制御しています。</span><span class="sxs-lookup"><span data-stu-id="6c30a-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c30a-109">例</span><span class="sxs-lookup"><span data-stu-id="6c30a-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="6c30a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c30a-110">See also</span></span>

- [<span data-ttu-id="6c30a-111">ストーリーボードを使ってプロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="6c30a-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="6c30a-112">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="6c30a-112">Animation Overview</span></span>](animation-overview.md)
