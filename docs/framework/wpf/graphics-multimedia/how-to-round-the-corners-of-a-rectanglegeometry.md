---
title: '方法: RectangleGeometry の角に丸みを付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651396"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="dbdf3-102">方法: RectangleGeometry の角に丸みを付ける</span><span class="sxs-lookup"><span data-stu-id="dbdf3-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="dbdf3-103">角を丸める、<xref:System.Windows.Media.RectangleGeometry>に設定して、その<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>と<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>プロパティを 0 より大きい値です。</span><span class="sxs-lookup"><span data-stu-id="dbdf3-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="dbdf3-104">値が大きいほど、四角形の角はの角。</span><span class="sxs-lookup"><span data-stu-id="dbdf3-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbdf3-105">例</span><span class="sxs-lookup"><span data-stu-id="dbdf3-105">Example</span></span>  
 <span data-ttu-id="dbdf3-106">次の例をいくつか示します<xref:System.Windows.Media.RectangleGeometry>オブジェクトが異なる<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>と<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>設定します。</span><span class="sxs-lookup"><span data-stu-id="dbdf3-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="dbdf3-107"><xref:System.Windows.Media.RectangleGeometry>を使用してオブジェクトが表示される<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="dbdf3-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="dbdf3-108">![別の RadiusX 長方形&#47;RadiusY 設定](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="dbdf3-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="dbdf3-109">角の丸い四角形</span><span class="sxs-lookup"><span data-stu-id="dbdf3-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbdf3-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbdf3-110">See also</span></span>

- [<span data-ttu-id="dbdf3-111">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="dbdf3-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="dbdf3-112">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="dbdf3-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="dbdf3-113">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="dbdf3-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
