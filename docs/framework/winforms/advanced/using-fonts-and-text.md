---
title: フォントとテキストの使用
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505111"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="3e95d-102">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="3e95d-102">Using Fonts and Text</span></span>
<span data-ttu-id="3e95d-103">Windows フォームにテキストを描画するために、GDI + と GDI によって提供されるいくつかのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="3e95d-103">There are several classes offered by GDI+ and GDI for drawing text on Windows Forms.</span></span> <span data-ttu-id="3e95d-104">GDI +<xref:System.Drawing.Graphics>クラスにはいくつか<xref:System.Drawing.Graphics.DrawString%2A>外接する四角形、フォント、および形式の場所などのテキストのさまざまな機能を指定するためのメソッド。</span><span class="sxs-lookup"><span data-stu-id="3e95d-104">The GDI+ <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="3e95d-105">さらに、描画したり、静的 using GDI を使用してテキストを計測<xref:System.Windows.Forms.TextRenderer.DrawText%2A>と<xref:System.Windows.Forms.TextRenderer.MeasureText%2A>によって提供されるメソッド、`TextRenderer`クラス。</span><span class="sxs-lookup"><span data-stu-id="3e95d-105">In addition, you can draw and measure text with GDI using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="3e95d-106">GDI メソッドでは、場所、フォント、および形式を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3e95d-106">The GDI methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="3e95d-107">テキストのレンダリング; GDI または GDI + のいずれかを選択できます。ただし、GDI は、パフォーマンスが向上しより正確なテキストの測定を一般に提供します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-107">You can choose either GDI or GDI+ for text rendering; however, GDI generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="3e95d-108">テキストのレンダリングに影響を与える他のクラスには`FontFamily`、 `Font`、 <xref:System.Drawing.StringFormat>、および`TextFormatFlags`します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e95d-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3e95d-109">In This Section</span></span>  
 [<span data-ttu-id="3e95d-110">方法: フォント ファミリとフォントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="3e95d-111">作成する方法を示します`Font`と`FontFamily`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3e95d-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="3e95d-112">方法: 指定した位置のテキストの描画</span><span class="sxs-lookup"><span data-stu-id="3e95d-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="3e95d-113">GDI + と GDI を使用して、特定の場所にテキストを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-113">Describes how to draw text in a certain location using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="3e95d-114">方法: 四角形内にテキストを折り返して描画</span><span class="sxs-lookup"><span data-stu-id="3e95d-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="3e95d-115">GDI + と GDI を使用して四角形内のテキストを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-115">Explains how to draw text in a rectangle using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="3e95d-116">方法: GDI を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="3e95d-117">GDI を使用して、テキストの描画方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-117">Demonstrates how to use GDI for drawing text.</span></span>  
  
 [<span data-ttu-id="3e95d-118">方法: 描画するテキストを揃える</span><span class="sxs-lookup"><span data-stu-id="3e95d-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="3e95d-119">GDI + と GDI のテキストの書式設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-119">Shows how to format GDI+ and GDI text.</span></span>  
  
 [<span data-ttu-id="3e95d-120">方法: 垂直方向のテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="3e95d-121">GDI + での垂直方向に配置済みのテキストを描画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-121">Describes how to draw vertically aligned text with GDI+.</span></span>  
  
 [<span data-ttu-id="3e95d-122">方法: 描画されたテキストにタブ ストップを設定します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="3e95d-123">表示は、どの GDI + でのタブ位置でテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-123">Shows how draw text with tab stops with GDI+.</span></span>  
  
 [<span data-ttu-id="3e95d-124">方法: インストールされているフォントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="3e95d-125">インストールされているフォントの名前を一覧表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="3e95d-126">方法: プライベート フォント コレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="3e95d-127">作成する方法について説明します、<xref:System.Drawing.Text.PrivateFontCollection>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3e95d-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="3e95d-128">方法: フォント メトリックを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="3e95d-129">セル アセント降下などのフォント メトリックを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="3e95d-130">方法: テキストのアンチエイリアシングを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="3e95d-131">テキストを描画するときにアンチエイリアシングを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e95d-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3e95d-132">参照</span><span class="sxs-lookup"><span data-stu-id="3e95d-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="3e95d-133">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e95d-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="3e95d-134">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e95d-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="3e95d-135">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e95d-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="3e95d-136">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e95d-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="3e95d-137">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3e95d-137">Describes this class and contains links to all of its members.</span></span>
