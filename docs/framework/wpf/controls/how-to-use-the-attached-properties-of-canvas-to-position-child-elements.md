---
title: '方法: Canvas の添付プロパティを使用して子要素を配置する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 347c8502bd4c5fafcde7a142327f85bfb75b9954
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159628"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="818f5-102">方法: Canvas の添付プロパティを使用して子要素を配置する</span><span class="sxs-lookup"><span data-stu-id="818f5-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="818f5-103">この例の添付プロパティを使用する方法を示しています。<xref:System.Windows.Controls.Canvas>子要素を配置します。</span><span class="sxs-lookup"><span data-stu-id="818f5-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="818f5-104">例</span><span class="sxs-lookup"><span data-stu-id="818f5-104">Example</span></span>  
 <span data-ttu-id="818f5-105">次の例には、4 が加算されます<xref:System.Windows.Controls.Button>要素の親の子要素として<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="818f5-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="818f5-106">各要素が表される、 <xref:System.Windows.Controls.Canvas.Bottom%2A>、 <xref:System.Windows.Controls.Canvas.Left%2A>、 <xref:System.Windows.Controls.Canvas.Right%2A>、および<xref:System.Windows.Controls.Canvas.Top%2A>します。</span><span class="sxs-lookup"><span data-stu-id="818f5-106">Each element is represented by a <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span>
<span data-ttu-id="818f5-107">各<xref:System.Windows.Controls.Button>が、親に対する相対的な配置されている<xref:System.Windows.Controls.Canvas>とその割り当てプロパティ値に従ってします。</span><span class="sxs-lookup"><span data-stu-id="818f5-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="818f5-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="818f5-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="818f5-109">パネルの概要</span><span class="sxs-lookup"><span data-stu-id="818f5-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="818f5-110">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="818f5-110">How-to Topics</span></span>](canvas-how-to-topics.md)
- [<span data-ttu-id="818f5-111">添付プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="818f5-111">Attached Properties Overview</span></span>](../advanced/attached-properties-overview.md)
