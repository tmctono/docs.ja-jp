---
title: '方法: ビジュアルの描画コンテンツを列挙する'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 4f0afc1075fe66c7f154fcef3cd883709db55316
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947473"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="83b70-102">方法: ビジュアルの描画コンテンツを列挙する</span><span class="sxs-lookup"><span data-stu-id="83b70-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="83b70-103"><xref:System.Windows.Media.Drawing>オブジェクトの内容を列挙するためのオブジェクト モデルの提供、<xref:System.Windows.Media.Visual>します。</span><span class="sxs-lookup"><span data-stu-id="83b70-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83b70-104">例</span><span class="sxs-lookup"><span data-stu-id="83b70-104">Example</span></span>  
 <span data-ttu-id="83b70-105">次の例では、<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>を取得するメソッド、<xref:System.Windows.Media.DrawingGroup>の値を<xref:System.Windows.Media.Visual>し、それを列挙します。</span><span class="sxs-lookup"><span data-stu-id="83b70-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83b70-106">ビジュアルの内容を列挙するときは、取得する<xref:System.Windows.Media.Drawing>オブジェクト、およびしない、ベクター グラフィックス命令リストとしてのレンダリング データの基になる表現。</span><span class="sxs-lookup"><span data-stu-id="83b70-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="83b70-107">詳しくは、「[WPF グラフィックス レンダリングの概要](wpf-graphics-rendering-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="83b70-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="83b70-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="83b70-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="83b70-109">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="83b70-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="83b70-110">WPF グラフィックス レンダリングの概要</span><span class="sxs-lookup"><span data-stu-id="83b70-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
