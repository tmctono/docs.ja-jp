---
title: グラデーション ブラシを使用した図形の塗りつぶし
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063610"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="4495e-102">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="4495e-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="4495e-103">グラデーション ブラシを使用して、徐々 に変化する色で図形を塗りつぶすことができます。</span><span class="sxs-lookup"><span data-stu-id="4495e-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="4495e-104">たとえば、図形を塗りつぶす色、形状の左端から右端に移動する段階的に変化するように、水平方向のグラデーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4495e-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="4495e-105">左端で黒の四角形を想像してみてください (0, 0, 0 は、赤、緑、および青のコンポーネントによって表される) と、右端が red (255, 0, 0 で表されます)。</span><span class="sxs-lookup"><span data-stu-id="4495e-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="4495e-106">四角形が 256 ピクセルである場合は、1 つの左側にピクセルの赤の要素より大きいを特定のピクセルの赤の要素になります。</span><span class="sxs-lookup"><span data-stu-id="4495e-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="4495e-107">行の左端のピクセルが (0, 0, 0) の色要素、2 番目のピクセルが (1, 0, 0)、3 番目のピクセルは、(2, 0, 0) というように、(255, 0, 0) の色要素の右端のピクセルが表示されるまでです。</span><span class="sxs-lookup"><span data-stu-id="4495e-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="4495e-108">これらの色の補間値は、色のグラデーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4495e-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="4495e-109">線形グラデーションは、水平、垂直方向に移動するか、指定した斜線を並列に色を変更します。</span><span class="sxs-lookup"><span data-stu-id="4495e-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="4495e-110">パス グラデーションは、内部およびパスの境界を移動するように色を変更します。</span><span class="sxs-lookup"><span data-stu-id="4495e-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="4495e-111">さまざまな効果を実現するためにパス グラデーションをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="4495e-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="4495e-112">次の図は、線状グラデーション ブラシで塗りつぶした四角形とパスのグラデーション ブラシで塗りつぶした楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="4495e-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush:</span></span>  
  
 ![四角形は、楕円にグラデーション ブラシで塗りつぶされます。](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a><span data-ttu-id="4495e-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4495e-114">In This Section</span></span>  
 [<span data-ttu-id="4495e-115">方法: 線形グラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4495e-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="4495e-116">線形グラデーションを使用して、作成する方法を示しています、<xref:System.Drawing.Drawing2D.LinearGradientBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="4495e-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="4495e-117">方法: パス グラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4495e-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="4495e-118">パス グラデーションを使用して、作成する方法について説明します、<xref:System.Drawing.Drawing2D.PathGradientBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="4495e-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="4495e-119">方法: グラデーションに対してガンマ補正を適用します。</span><span class="sxs-lookup"><span data-stu-id="4495e-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="4495e-120">グラデーション ブラシでガンマ補正を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4495e-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4495e-121">参照</span><span class="sxs-lookup"><span data-stu-id="4495e-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="4495e-122">このクラスの説明を表すし、そのすべてのメンバーへのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="4495e-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="4495e-123">このクラスの説明を表すし、そのすべてのメンバーへのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="4495e-123">Contains a description of this class and has links to all of its members.</span></span>
