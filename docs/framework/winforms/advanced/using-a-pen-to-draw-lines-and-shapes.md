---
title: ペンを使用した直線と図形の描画
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: d20b4e47c9f8a5dd7a144e6ebb3151d3ab65a800
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505143"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="be4c1-102">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="be4c1-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="be4c1-103">GDI + を使用して、`Pen`直線セグメントでは、曲線、および形状のアウトラインを描画するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="be4c1-103">Use GDI+ `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="be4c1-104">このセクションで*行*という意味では直線セグメントのみを指定しない限り、これらのいずれかを参照します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="be4c1-105">ペンの色、幅、配置、およびそのペンで描画された直線のスタイルを制御するためのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be4c1-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="be4c1-106">In This Section</span></span>  
 [<span data-ttu-id="be4c1-107">方法: ペンを使用して線を描画するには</span><span class="sxs-lookup"><span data-stu-id="be4c1-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="be4c1-108">線を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="be4c1-109">方法: 四角形を描画するために、ペンを使用します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="be4c1-110">四角形を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="be4c1-111">方法: セットのペンの幅と配置</span><span class="sxs-lookup"><span data-stu-id="be4c1-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="be4c1-112">幅とのアラインメントを変更する方法について説明します、`Pen`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="be4c1-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="be4c1-113">方法: ライン キャップを持つ行を描画します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="be4c1-114">線を描画するときに、終端のキャップを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="be4c1-115">方法: 結合線</span><span class="sxs-lookup"><span data-stu-id="be4c1-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="be4c1-116">2 つの行を結合する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="be4c1-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="be4c1-117">方法: カスタム破線を描画します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="be4c1-118">破線を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="be4c1-119">方法: テクスチャを使用して塗りつぶした直線を描画します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="be4c1-120">テクスチャを塗りつぶした直線を描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="be4c1-121">参照</span><span class="sxs-lookup"><span data-stu-id="be4c1-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="be4c1-122">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="be4c1-122">Describes this class and has links to all its members.</span></span>
