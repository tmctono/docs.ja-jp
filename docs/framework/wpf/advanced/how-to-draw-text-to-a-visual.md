---
title: '方法: ビジュアルにテキストを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 1ea31540ad59ab419e209e4133bcb88640cc01fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776169"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="4e141-102">方法: ビジュアルにテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="4e141-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="4e141-103">次の例では、テキストを描画する方法を示しています、<xref:System.Windows.Media.DrawingVisual>を使用して、<xref:System.Windows.Media.DrawingContext>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4e141-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="4e141-104">描画コンテキストが呼び出しによって返される、<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>のメソッドを<xref:System.Windows.Media.DrawingVisual>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4e141-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="4e141-105">グラフィックスとテキストを描画コンテキストに描画できます。</span><span class="sxs-lookup"><span data-stu-id="4e141-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="4e141-106">描画コンテキストにテキストを描画するために使用して、<xref:System.Windows.Media.DrawingContext.DrawText%2A>のメソッドを<xref:System.Windows.Media.DrawingContext>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4e141-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="4e141-107">コンテンツを描画コンテキストに描画が完了したら、呼び出し、<xref:System.Windows.Media.DrawingContext.Close%2A>メソッドを描画コンテキストを閉じるし、内容を保持します。</span><span class="sxs-lookup"><span data-stu-id="4e141-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e141-108">例</span><span class="sxs-lookup"><span data-stu-id="4e141-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="4e141-109">上記のコードの抽出元となった完全なコード サンプルについては、「[DrawingVisual を使用したヒット テストのサンプル](https://go.microsoft.com/fwlink/?LinkID=159994)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e141-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
