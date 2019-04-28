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
ms.openlocfilehash: c9fe16752223203806c7d3828f632aad0cab0c28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769419"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="7362e-102">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="7362e-102">Using Fonts and Text</span></span>
<span data-ttu-id="7362e-103">によって提供されるいくつかのクラスがある[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]と[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]Windows フォームにテキストを描画するためです。</span><span class="sxs-lookup"><span data-stu-id="7362e-103">There are several classes offered by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text on Windows Forms.</span></span> <span data-ttu-id="7362e-104">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics>クラスにはいくつか<xref:System.Drawing.Graphics.DrawString%2A>外接する四角形、フォント、および形式の場所などのテキストのさまざまな機能を指定するためのメソッド。</span><span class="sxs-lookup"><span data-stu-id="7362e-104">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="7362e-105">さらに、描画、テキストを計測[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]静的<xref:System.Windows.Forms.TextRenderer.DrawText%2A>と<xref:System.Windows.Forms.TextRenderer.MeasureText%2A>によって提供されるメソッド、`TextRenderer`クラス。</span><span class="sxs-lookup"><span data-stu-id="7362e-105">In addition, you can draw and measure text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="7362e-106">[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]メソッドの場所、フォント、および形式を指定することも可能です。</span><span class="sxs-lookup"><span data-stu-id="7362e-106">The [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="7362e-107">いずれも使用できます[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]または[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]テキスト レンダリングされます。 ただし、[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]通常をより的確にパフォーマンスとより正確なテキストを測定します。</span><span class="sxs-lookup"><span data-stu-id="7362e-107">You can choose either [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] or [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] for text rendering; however, [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="7362e-108">テキストのレンダリングに影響を与える他のクラスには`FontFamily`、 `Font`、 <xref:System.Drawing.StringFormat>、および`TextFormatFlags`します。</span><span class="sxs-lookup"><span data-stu-id="7362e-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7362e-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7362e-109">In This Section</span></span>  
 [<span data-ttu-id="7362e-110">方法: フォント ファミリとフォントを作成します。</span><span class="sxs-lookup"><span data-stu-id="7362e-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="7362e-111">作成する方法を示します`Font`と`FontFamily`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7362e-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="7362e-112">方法: 指定した位置のテキストの描画</span><span class="sxs-lookup"><span data-stu-id="7362e-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="7362e-113">特定の場所を使用して、テキストを描画する方法について説明します[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]と[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7362e-113">Describes how to draw text in a certain location using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="7362e-114">方法: 四角形内にテキストを折り返して描画</span><span class="sxs-lookup"><span data-stu-id="7362e-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="7362e-115">使用して、四角形内のテキストを描画する方法について説明します[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]と[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7362e-115">Explains how to draw text in a rectangle using [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 [<span data-ttu-id="7362e-116">方法: GDI を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="7362e-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="7362e-117">使用する方法を示します[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]テキストの描画します。</span><span class="sxs-lookup"><span data-stu-id="7362e-117">Demonstrates how to use [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] for drawing text.</span></span>  
  
 [<span data-ttu-id="7362e-118">方法: 描画するテキストを揃える</span><span class="sxs-lookup"><span data-stu-id="7362e-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="7362e-119">書式設定する方法を示しています。[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]と[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]テキスト。</span><span class="sxs-lookup"><span data-stu-id="7362e-119">Shows how to format [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] text.</span></span>  
  
 [<span data-ttu-id="7362e-120">方法: 垂直方向のテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="7362e-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="7362e-121">垂直方向に配置されたテキストを描画する方法について説明します[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7362e-121">Describes how to draw vertically aligned text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="7362e-122">方法: 描画されたテキストにタブ ストップを設定します。</span><span class="sxs-lookup"><span data-stu-id="7362e-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="7362e-123">表示方法でタブ位置でテキストの描画[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="7362e-123">Shows how draw text with tab stops with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
 [<span data-ttu-id="7362e-124">方法: インストールされているフォントを列挙します。</span><span class="sxs-lookup"><span data-stu-id="7362e-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="7362e-125">インストールされているフォントの名前を一覧表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7362e-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="7362e-126">方法: プライベート フォント コレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7362e-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="7362e-127">作成する方法について説明します、<xref:System.Drawing.Text.PrivateFontCollection>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7362e-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="7362e-128">方法: フォント メトリックを取得します。</span><span class="sxs-lookup"><span data-stu-id="7362e-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="7362e-129">セル アセント降下などのフォント メトリックを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7362e-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="7362e-130">方法: テキストのアンチエイリアシングを使用します。</span><span class="sxs-lookup"><span data-stu-id="7362e-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="7362e-131">テキストを描画するときにアンチエイリアシングを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7362e-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7362e-132">参照</span><span class="sxs-lookup"><span data-stu-id="7362e-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="7362e-133">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7362e-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="7362e-134">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7362e-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="7362e-135">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7362e-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="7362e-136">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7362e-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="7362e-137">このクラスについて説明し、そのすべてのメンバーへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7362e-137">Describes this class and contains links to all of its members.</span></span>
