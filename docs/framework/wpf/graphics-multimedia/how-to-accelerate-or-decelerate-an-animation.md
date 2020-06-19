---
title: '方法: アニメーションを加速または減速させる'
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 7ab55ba44b866a992b9021284f170858f0108d15
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243012"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="7de07-102">方法: アニメーションを加速または減速させる</span><span class="sxs-lookup"><span data-stu-id="7de07-102">How to: Accelerate or decelerate an animation</span></span>

<span data-ttu-id="7de07-103">この例では、時間の経過と共にアニメーションを加速および減速させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7de07-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="7de07-104">次の例では、<xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> と <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> の異なる設定を使用したアニメーションによって複数の四角形がアニメーション化されます。</span><span class="sxs-lookup"><span data-stu-id="7de07-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7de07-105">例</span><span class="sxs-lookup"><span data-stu-id="7de07-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="7de07-106">この例では、コードは省略されています。</span><span class="sxs-lookup"><span data-stu-id="7de07-106">Code has been omitted from this example.</span></span> <span data-ttu-id="7de07-107">詳しいコードについては、[アニメーションのタイミング動作 (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) または[アニメーションのタイミング動作 (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7de07-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
