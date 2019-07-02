---
title: グラフィックス サービスの 3 つのカテゴリ
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: a69fa7a1ccad353c879731de05dc47f0d6ae8795
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505233"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="fe728-102">グラフィックス サービスの 3 つのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="fe728-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="fe728-103">Windows フォームでグラフィックスの提供は、次の 3 つの広範なカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="fe728-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
- <span data-ttu-id="fe728-104">2 次元 (2-d) のベクター グラフィックス</span><span class="sxs-lookup"><span data-stu-id="fe728-104">Two-dimensional (2-D) vector graphics</span></span>  
  
- <span data-ttu-id="fe728-105">イメージング</span><span class="sxs-lookup"><span data-stu-id="fe728-105">Imaging</span></span>  
  
- <span data-ttu-id="fe728-106">タイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="fe728-106">Typography</span></span>  
  
## <a name="2-d-vector-graphics"></a><span data-ttu-id="fe728-107">2 次元ベクター グラフィックス</span><span class="sxs-lookup"><span data-stu-id="fe728-107">2-D Vector Graphics</span></span>  
 <span data-ttu-id="fe728-108">2 次元ベクター グラフィックスはプリミティブです。直線、曲線、および図表; など座標系のポイントのセットによって指定されています。</span><span class="sxs-lookup"><span data-stu-id="fe728-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="fe728-109">たとえば、直線がその 2 つのエンドポイントで指定され、四角形の左上隅にあると、幅と高さを定義する数値の 1 組の位置を示す点で指定します。</span><span class="sxs-lookup"><span data-stu-id="fe728-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="fe728-110">単純なパスは、直線で接続されている点の配列によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="fe728-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="fe728-111">ベジエ スプラインは、4 つのコントロール ポイントで指定された高度な曲線です。</span><span class="sxs-lookup"><span data-stu-id="fe728-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 <span data-ttu-id="fe728-112">GDI + 自体、プリミティブを描画する方法についての情報を格納するクラスおよびクラスを実際に描画を実行するクラスと、プリミティブについての情報を格納する構造体を提供します。</span><span class="sxs-lookup"><span data-stu-id="fe728-112">GDI+ provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="fe728-113">など、<xref:System.Drawing.Rectangle>構造体に格納する四角形のサイズと場所、<xref:System.Drawing.Pen>クラスは、線の色、線の幅、および線のスタイルに関する情報を格納し、<xref:System.Drawing.Graphics>クラスには、線、四角形、パスを描画するためのメソッドとその他の数値。</span><span class="sxs-lookup"><span data-stu-id="fe728-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="fe728-114">あるいくつかも<xref:System.Drawing.Brush>方法に関する情報を格納するクラスの終了図形とパスが色やパターンで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="fe728-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="fe728-115">メタファイルには、一連のグラフィック コマンドには、ベクター イメージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="fe728-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> <span data-ttu-id="fe728-116">GDI + は、提供、<xref:System.Drawing.Imaging.Metafile>記録、表示、およびメタファイルを保存するためのクラス。</span><span class="sxs-lookup"><span data-stu-id="fe728-116">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="fe728-117"><xref:System.Drawing.Imaging.MetafileHeader>と<xref:System.Drawing.Imaging.MetaHeader>クラス、メタファイル ヘッダーに格納されたデータを検査することができます。</span><span class="sxs-lookup"><span data-stu-id="fe728-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="fe728-118">イメージング</span><span class="sxs-lookup"><span data-stu-id="fe728-118">Imaging</span></span>  
 <span data-ttu-id="fe728-119">特定の種類の画像は、困難または不可能なベクター グラフィックスの手法で表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe728-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="fe728-120">たとえば、ツール バー ボタンの画像やアイコンとして表示される画像は、直線と曲線のコレクションとして指定する困難です。</span><span class="sxs-lookup"><span data-stu-id="fe728-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="fe728-121">混雑した野球場の高解像度デジタル写真はベクター手法を作成するさらに難しくなります。</span><span class="sxs-lookup"><span data-stu-id="fe728-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="fe728-122">このタイプのイメージはビットマップで、画面上の個々 のドットの色を表す数値の配列として格納されます。</span><span class="sxs-lookup"><span data-stu-id="fe728-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> <span data-ttu-id="fe728-123">GDI + は、提供、<xref:System.Drawing.Bitmap>を表示する、操作、およびビットマップの保存のクラス。</span><span class="sxs-lookup"><span data-stu-id="fe728-123">GDI+ provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="fe728-124">タイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="fe728-124">Typography</span></span>  
 <span data-ttu-id="fe728-125">文字体裁は、さまざまなフォント、サイズ、およびスタイル内のテキストの表示です。</span><span class="sxs-lookup"><span data-stu-id="fe728-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> <span data-ttu-id="fe728-126">GDI + この複雑なタスクの広範なサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="fe728-126">GDI+ provides extensive support for this complex task.</span></span> <span data-ttu-id="fe728-127">GDI + での新しい機能の 1 つは、サブピクセル アンチ エイリアスによりテキストをより滑らかな外観は、LCD 画面に描画します。</span><span class="sxs-lookup"><span data-stu-id="fe728-127">One of the new features in GDI+ is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="fe728-128">Windows フォームが GDI 機能を持つテキストを描画するオプションを提供するさらに、その<xref:System.Windows.Forms.TextRenderer>クラス。</span><span class="sxs-lookup"><span data-stu-id="fe728-128">In addition, Windows Forms offers the option to draw text with GDI capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe728-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe728-129">See also</span></span>

- [<span data-ttu-id="fe728-130">グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="fe728-130">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
- [<span data-ttu-id="fe728-131">GDI+ マネージド コードについて</span><span class="sxs-lookup"><span data-stu-id="fe728-131">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)
- [<span data-ttu-id="fe728-132">マネージド グラフィックス クラスの使用</span><span class="sxs-lookup"><span data-stu-id="fe728-132">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)
