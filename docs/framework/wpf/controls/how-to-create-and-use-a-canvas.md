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
ms.openlocfilehash: 13ed32195621350284530da78544e026ed341658
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360382"
---
# <a name="how-to-create-and-use-a-canvas"></a><span data-ttu-id="cd2d8-102">方法: Canvas を作成および使用する</span><span class="sxs-lookup"><span data-stu-id="cd2d8-102">How to: Create and Use a Canvas</span></span>
<span data-ttu-id="cd2d8-103">この例は、作成しのインスタンスを使用する方法を示しています。<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="cd2d8-103">This example shows how to create and use an instance of <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd2d8-104">例</span><span class="sxs-lookup"><span data-stu-id="cd2d8-104">Example</span></span>  
 <span data-ttu-id="cd2d8-105">次の例を明示的に 2 つ配置<xref:System.Windows.Controls.TextBlock>要素を使用して、<xref:System.Windows.Controls.Canvas.SetTop%2A>と<xref:System.Windows.Controls.Canvas.SetLeft%2A>メソッドの<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="cd2d8-105">The following example explicitly positions two <xref:System.Windows.Controls.TextBlock> elements by using the <xref:System.Windows.Controls.Canvas.SetTop%2A> and <xref:System.Windows.Controls.Canvas.SetLeft%2A> methods of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="cd2d8-106">また、例、割り当て、<xref:System.Windows.Controls.Control.Background%2A>の色`LightSteelBlue`を<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="cd2d8-106">The example also assigns a <xref:System.Windows.Controls.Control.Background%2A> color of `LightSteelBlue` to the <xref:System.Windows.Controls.Canvas>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd2d8-107">使用すると[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]位置に<xref:System.Windows.Controls.TextBlock>、要素を使用して、<xref:System.Windows.Controls.Canvas.Top%2A>と<xref:System.Windows.Controls.Canvas.Left%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="cd2d8-107">When you use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to position <xref:System.Windows.Controls.TextBlock> elements, use the <xref:System.Windows.Controls.Canvas.Top%2A> and <xref:System.Windows.Controls.Canvas.Left%2A> properties.</span></span>  
  
 [!code-csharp[CanvasCode#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cd2d8-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd2d8-108">See also</span></span>
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.TextBlock>
- <xref:System.Windows.Controls.Canvas.SetTop%2A>
- <xref:System.Windows.Controls.Canvas.SetLeft%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- [<span data-ttu-id="cd2d8-109">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="cd2d8-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="cd2d8-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="cd2d8-110">How-to Topics</span></span>](canvas-how-to-topics.md)
