---
title: '方法: RectangleGeometry の角に丸みを付ける'
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: f00d7a7cd6117318efb17645bbb9df279c97adff
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378536"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="4ec99-102">方法: RectangleGeometry の角に丸みを付ける</span><span class="sxs-lookup"><span data-stu-id="4ec99-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="4ec99-103">角を丸める、<xref:System.Windows.Media.RectangleGeometry>に設定して、その<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>と<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>プロパティを 0 より大きい値です。</span><span class="sxs-lookup"><span data-stu-id="4ec99-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="4ec99-104">値が大きいほど、四角形の角はの角。</span><span class="sxs-lookup"><span data-stu-id="4ec99-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ec99-105">例</span><span class="sxs-lookup"><span data-stu-id="4ec99-105">Example</span></span>  
 <span data-ttu-id="4ec99-106">次の例をいくつか示します<xref:System.Windows.Media.RectangleGeometry>オブジェクトが異なる<xref:System.Windows.Media.RectangleGeometry.RadiusX%2A>と<xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>設定します。</span><span class="sxs-lookup"><span data-stu-id="4ec99-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="4ec99-107"><xref:System.Windows.Media.RectangleGeometry>を使用してオブジェクトが表示される<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="4ec99-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="4ec99-108">![別の RadiusX 長方形&#47;RadiusY 設定](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="4ec99-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="4ec99-109">角の丸い四角形</span><span class="sxs-lookup"><span data-stu-id="4ec99-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec99-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ec99-110">See also</span></span>
- [<span data-ttu-id="4ec99-111">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="4ec99-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="4ec99-112">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="4ec99-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="4ec99-113">PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="4ec99-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
