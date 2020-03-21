---
title: グラフィックス サービスの 3 つのカテゴリ
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: b0f2ad8293daf6ad53899a0f8be82985c24ff50d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111206"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="8b38b-102">グラフィックス サービスの 3 つのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="8b38b-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="8b38b-103">Windows フォームのグラフィックス製品は、次の 3 つの大きなカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="8b38b-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
- <span data-ttu-id="8b38b-104">2 次元 (2 次元) ベクトル グラフィックス</span><span class="sxs-lookup"><span data-stu-id="8b38b-104">Two-dimensional (2-D) vector graphics</span></span>  
  
- <span data-ttu-id="8b38b-105">イメージング</span><span class="sxs-lookup"><span data-stu-id="8b38b-105">Imaging</span></span>  
  
- <span data-ttu-id="8b38b-106">タイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="8b38b-106">Typography</span></span>  
  
## <a name="2d-vector-graphics"></a><span data-ttu-id="8b38b-107">2D ベクトル グラフィックス</span><span class="sxs-lookup"><span data-stu-id="8b38b-107">2D Vector Graphics</span></span>  
 <span data-ttu-id="8b38b-108">2 次元ベクトル グラフィックスはプリミティブです。線、曲線、図など。座標系上のポイントのセットで指定されます。</span><span class="sxs-lookup"><span data-stu-id="8b38b-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="8b38b-109">たとえば、直線は 2 つの端点で指定され、四角形は左上隅の位置を示す点と、幅と高さを示す数値のペアで指定されます。</span><span class="sxs-lookup"><span data-stu-id="8b38b-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="8b38b-110">単純パスは、直線で接続されたポイントの配列で指定されます。</span><span class="sxs-lookup"><span data-stu-id="8b38b-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="8b38b-111">ベジェ スプラインは、4 つのコントロール ポイントで指定された高度な曲線です。</span><span class="sxs-lookup"><span data-stu-id="8b38b-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 <span data-ttu-id="8b38b-112">GDI+ には、プリミティブ自体に関する情報、プリミティブの描画方法に関する情報を格納するクラス、および実際に描画を行うクラスを格納するクラスと構造体が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8b38b-112">GDI+ provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="8b38b-113">たとえば、この構造体<xref:System.Drawing.Rectangle>には、四角形の位置とサイズが格納されます。この<xref:System.Drawing.Pen>クラスには、線の色、線の幅、線のスタイルに関する情報が格納されます。<xref:System.Drawing.Graphics>クラスには、線、長方形、パス、およびその他の図形を描画するためのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="8b38b-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="8b38b-114">閉じた図形や<xref:System.Drawing.Brush>パスが色やパターンで塗りつぶされる方法に関する情報を格納するクラスもいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="8b38b-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="8b38b-115">グラフィック コマンドのシーケンスであるベクター イメージをメタファイルに記録できます。</span><span class="sxs-lookup"><span data-stu-id="8b38b-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> <span data-ttu-id="8b38b-116">GDI+ は<xref:System.Drawing.Imaging.Metafile>、メタファイルの記録、表示、保存のためのクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8b38b-116">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="8b38b-117"><xref:System.Drawing.Imaging.MetafileHeader>クラスと<xref:System.Drawing.Imaging.MetaHeader>クラスを使用すると、メタファイル ヘッダーに格納されているデータを検査できます。</span><span class="sxs-lookup"><span data-stu-id="8b38b-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="8b38b-118">イメージング</span><span class="sxs-lookup"><span data-stu-id="8b38b-118">Imaging</span></span>  
 <span data-ttu-id="8b38b-119">特定の種類の画像は、ベクトルグラフィックスのテクニックでは表示が困難または不可能です。</span><span class="sxs-lookup"><span data-stu-id="8b38b-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="8b38b-120">たとえば、ツール バー ボタン上の図やアイコンとして表示される図は、線や曲線のコレクションとして指定するのが困難です。</span><span class="sxs-lookup"><span data-stu-id="8b38b-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="8b38b-121">混雑した野球場の高解像度デジタル写真は、ベクトル技術で作成することはさらに困難です。</span><span class="sxs-lookup"><span data-stu-id="8b38b-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="8b38b-122">このタイプのイメージはビットマップとして保存され、画面上の個々のドットの色を表す数値の配列です。</span><span class="sxs-lookup"><span data-stu-id="8b38b-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> <span data-ttu-id="8b38b-123">GDI+ は<xref:System.Drawing.Bitmap>、ビットマップの表示、操作、および保存を行うためのクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8b38b-123">GDI+ provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="8b38b-124">タイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="8b38b-124">Typography</span></span>  
 <span data-ttu-id="8b38b-125">文字体裁は、さまざまなフォント、サイズ、およびスタイルでテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="8b38b-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> <span data-ttu-id="8b38b-126">GDI+ は、この複雑なタスクを広範囲にサポートします。</span><span class="sxs-lookup"><span data-stu-id="8b38b-126">GDI+ provides extensive support for this complex task.</span></span> <span data-ttu-id="8b38b-127">GDI+ の新機能の 1 つはサブピクセル アンチエイリアシングで、LCD 画面に表示されるテキストの外観が滑らかになります。</span><span class="sxs-lookup"><span data-stu-id="8b38b-127">One of the new features in GDI+ is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="8b38b-128">さらに、Windows フォームには、GDI 機能を持つテキストをそのクラス<xref:System.Windows.Forms.TextRenderer>で描画するオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8b38b-128">In addition, Windows Forms offers the option to draw text with GDI capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b38b-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b38b-129">See also</span></span>

- [<span data-ttu-id="8b38b-130">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="8b38b-130">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
- [<span data-ttu-id="8b38b-131">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="8b38b-131">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)
- [<span data-ttu-id="8b38b-132">マネージド グラフィックス クラスの使用</span><span class="sxs-lookup"><span data-stu-id="8b38b-132">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)
