---
title: 曲線の作成と描画
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506105"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="961f4-102">曲線の作成と描画</span><span class="sxs-lookup"><span data-stu-id="961f4-102">Constructing and Drawing Curves</span></span>
<span data-ttu-id="961f4-103">GDI + の曲線のいくつかの種類をサポートしています。 省略記号、円弧、カーディナル スプライン、およびベジエ スプラインします。</span><span class="sxs-lookup"><span data-stu-id="961f4-103">GDI+ supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="961f4-104">楕円は、外接する四角形。円弧は、開始角度および掃引角度によって定義される楕円の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="961f4-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="961f4-105">カーディナル スプラインがポイントとテンション パラメーターの配列で定義されている-曲線は、配列内の各ポイントをスムーズに通過およびテンションで湾曲する方法に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="961f4-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="961f4-106">ベジエ スプラインは、2 つのエンドポイントと曲線が制御点を通過しません、2 つの制御点によって定義されますが、コントロール ポイントの方向およびように曲線が 1 つのエンドポイントから、もう一方にします。</span><span class="sxs-lookup"><span data-stu-id="961f4-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="961f4-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="961f4-107">In This Section</span></span>  
 [<span data-ttu-id="961f4-108">方法: カーディナル スプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="961f4-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="961f4-109">カーディナル スプライン、およびこれらを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="961f4-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="961f4-110">方法: 1 つのベジエ スプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="961f4-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="961f4-111">ベジエ スプラインを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="961f4-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="961f4-112">方法: 一連のベジエ スプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="961f4-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="961f4-113">シーケンスに複数のベジエ スプラインを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="961f4-113">Explains how to draw several Bézier splines in sequence.</span></span>
