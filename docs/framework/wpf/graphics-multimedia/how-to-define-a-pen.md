---
title: '方法: ペンを定義する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
ms.openlocfilehash: 1d69a40604dbf2f7a73c17279ae946faeb6c634a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965400"
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="b9971-102">方法: ペンを定義する</span><span class="sxs-lookup"><span data-stu-id="b9971-102">How to: Define a Pen</span></span>
<span data-ttu-id="b9971-103">この例では、<xref:System.Windows.Media.Pen> を使用して図形のアウトラインを描く方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b9971-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="b9971-104">単純な <xref:System.Windows.Media.Pen> を作成するには、その <xref:System.Windows.Media.Pen.Thickness%2A> と <xref:System.Windows.Media.Pen.Brush%2A> のみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9971-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="b9971-105"><xref:System.Windows.Media.Pen.DashStyle%2A>、<xref:System.Windows.Media.Pen.DashCap%2A>、<xref:System.Windows.Media.Pen.LineJoin%2A>、<xref:System.Windows.Media.Pen.StartLineCap%2A>、<xref:System.Windows.Media.Pen.EndLineCap%2A> を指定して、より複雑なペンを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9971-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9971-106">例</span><span class="sxs-lookup"><span data-stu-id="b9971-106">Example</span></span>  
 <span data-ttu-id="b9971-107">次の例では、<xref:System.Windows.Media.Pen> を使用して、<xref:System.Windows.Media.GeometryDrawing> によって定義された図形のアウトラインを描きます。</span><span class="sxs-lookup"><span data-stu-id="b9971-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="b9971-108">![ペンで描いたアウトライン](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="b9971-108">![Outlines produces by a Pen](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="b9971-109">GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="b9971-109">A GeometryDrawing</span></span>
