---
title: '方法: Canvas を作成および使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
ms.openlocfilehash: edef660b2da2f09e0a6edbc0a87f0d1f26eb03da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964229"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="c775c-102">方法: Canvas を作成および使用する</span><span class="sxs-lookup"><span data-stu-id="c775c-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="c775c-103">この例では、の<xref:System.Windows.Controls.Canvas>インスタンスを作成して使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c775c-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c775c-104">例</span><span class="sxs-lookup"><span data-stu-id="c775c-104">Example</span></span>  
 <span data-ttu-id="c775c-105">次の例では、 <xref:System.Windows.Controls.TextBlock>のメソッド<xref:System.Windows.Controls.Canvas.SetTop%2A>と<xref:System.Windows.Controls.Canvas.SetLeft%2A>メソッドを使用し<xref:System.Windows.Controls.Canvas>て、2つの要素を明示的に配置しています。</span><span class="sxs-lookup"><span data-stu-id="c775c-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="c775c-106">また、この例で<xref:System.Windows.Controls.Control.Background%2A>は、 `LightSteelBlue` <xref:System.Windows.Controls.Canvas>の色をに割り当てています。</span><span class="sxs-lookup"><span data-stu-id="c775c-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c775c-107">を使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]し<xref:System.Windows.Controls.Canvas.Top%2A>て要素<xref:System.Windows.Controls.TextBlock>を配置する場合は<xref:System.Windows.Controls.Canvas.Left%2A> 、プロパティとプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="c775c-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c775c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="c775c-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="c775c-109">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="c775c-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="c775c-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="c775c-110">How-to Topics</span></span>](canvas-how-to-topics.md)
