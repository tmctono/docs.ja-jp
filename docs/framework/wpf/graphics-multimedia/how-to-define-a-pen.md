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
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365785"
---
# <a name="how-to-define-a-pen"></a><span data-ttu-id="eec44-102">方法: ペンを定義する</span><span class="sxs-lookup"><span data-stu-id="eec44-102">How to: Define a Pen</span></span>
<span data-ttu-id="eec44-103">この例では、<xref:System.Windows.Media.Pen>図形のアウトラインにします。</span><span class="sxs-lookup"><span data-stu-id="eec44-103">This example shows how use a <xref:System.Windows.Media.Pen> to outline a shape.</span></span> <span data-ttu-id="eec44-104">単純なを作成する<xref:System.Windows.Media.Pen>、だけを指定する必要があるその<xref:System.Windows.Media.Pen.Thickness%2A>と<xref:System.Windows.Media.Pen.Brush%2A>します。</span><span class="sxs-lookup"><span data-stu-id="eec44-104">To create a simple <xref:System.Windows.Media.Pen>, you need only specify its <xref:System.Windows.Media.Pen.Thickness%2A> and <xref:System.Windows.Media.Pen.Brush%2A>.</span></span> <span data-ttu-id="eec44-105">複雑なペンを作成するには指定することによって、 <xref:System.Windows.Media.Pen.DashStyle%2A>、 <xref:System.Windows.Media.Pen.DashCap%2A>、 <xref:System.Windows.Media.Pen.LineJoin%2A>、 <xref:System.Windows.Media.Pen.StartLineCap%2A>、および<xref:System.Windows.Media.Pen.EndLineCap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="eec44-105">You can create more complex pen's by specifying a <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, and <xref:System.Windows.Media.Pen.EndLineCap%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eec44-106">例</span><span class="sxs-lookup"><span data-stu-id="eec44-106">Example</span></span>  
 <span data-ttu-id="eec44-107">次の例では、<xref:System.Windows.Media.Pen>で定義された図形のアウトラインを<xref:System.Windows.Media.GeometryDrawing>します。</span><span class="sxs-lookup"><span data-stu-id="eec44-107">The following example uses a <xref:System.Windows.Media.Pen> to outline a shape defined by a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 <span data-ttu-id="eec44-108">![ペンで描いたアウトライン](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span><span class="sxs-lookup"><span data-stu-id="eec44-108">![Outlines produces by a Pen](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")</span></span>  
<span data-ttu-id="eec44-109">GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="eec44-109">A GeometryDrawing</span></span>
