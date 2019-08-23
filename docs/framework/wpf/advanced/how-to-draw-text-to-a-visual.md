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
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963843"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="9a81a-102">方法: ビジュアルにテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="9a81a-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="9a81a-103">オブジェクト<xref:System.Windows.Media.DrawingContext>を<xref:System.Windows.Media.DrawingVisual>使用してにテキストを描画する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="9a81a-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="9a81a-104">描画コンテキストは、 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> <xref:System.Windows.Media.DrawingVisual>オブジェクトのメソッドを呼び出すことによって返されます。</span><span class="sxs-lookup"><span data-stu-id="9a81a-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="9a81a-105">描画コンテキストにグラフィックスやテキストを描画できます。</span><span class="sxs-lookup"><span data-stu-id="9a81a-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="9a81a-106">描画コンテキストにテキストを描画するには、 <xref:System.Windows.Media.DrawingContext.DrawText%2A> <xref:System.Windows.Media.DrawingContext>オブジェクトのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a81a-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="9a81a-107">描画コンテキストへのコンテンツの描画が完了したら、 <xref:System.Windows.Media.DrawingContext.Close%2A>メソッドを呼び出して描画コンテキストを閉じ、コンテンツを永続化します。</span><span class="sxs-lookup"><span data-stu-id="9a81a-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a81a-108">例</span><span class="sxs-lookup"><span data-stu-id="9a81a-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="9a81a-109">上記のコードの抽出元となった完全なコード サンプルについては、「[DrawingVisual を使用したヒット テストのサンプル](https://go.microsoft.com/fwlink/?LinkID=159994)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a81a-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
