---
title: '方法: アニメーションを加速または減速させる'
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: d4fcaf4a684c37590f27d603ef5cb2c86a6fb854
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376248"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="cda3a-102">方法: アニメーションを加速または減速させる</span><span class="sxs-lookup"><span data-stu-id="cda3a-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="cda3a-103">この例では、高速化し、時間の経過と共に/減速のアニメーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cda3a-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="cda3a-104">次の例では、いくつかの四角形を使用してさまざまなアニメーションによってアニメーション化します。<xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A>と<xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A>設定します。</span><span class="sxs-lookup"><span data-stu-id="cda3a-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cda3a-105">例</span><span class="sxs-lookup"><span data-stu-id="cda3a-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="cda3a-106">コードは、この例から省略されています。</span><span class="sxs-lookup"><span data-stu-id="cda3a-106">Code has been omitted from this example.</span></span> <span data-ttu-id="cda3a-107">完全なコードでは、次を参照してください。、[アニメーションのタイミング動作 (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp)または[アニメーションのタイミング動作 (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic)します。</span><span class="sxs-lookup"><span data-stu-id="cda3a-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
