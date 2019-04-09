---
title: '方法: フォント メトリックを取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 24cada3962339cae0608bbe01e070a0b8e256e73
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119055"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="5cbfc-102">方法: フォント メトリックを取得する</span><span class="sxs-lookup"><span data-stu-id="5cbfc-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="5cbfc-103"><xref:System.Drawing.FontFamily>クラスは、特定のファミリとスタイルの組み合わせに対してさまざまなメトリックを取得する次のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <xref:System.Drawing.FontFamily.GetEmHeight%2A><span data-ttu-id="5cbfc-104">(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="5cbfc-104">(FontStyle)</span></span>  
  
-   <xref:System.Drawing.FontFamily.GetCellAscent%2A><span data-ttu-id="5cbfc-105">(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="5cbfc-105">(FontStyle)</span></span>  
  
-   <xref:System.Drawing.FontFamily.GetCellDescent%2A><span data-ttu-id="5cbfc-106">(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="5cbfc-106">(FontStyle)</span></span>  
  
-   <xref:System.Drawing.FontFamily.GetLineSpacing%2A><span data-ttu-id="5cbfc-107">(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="5cbfc-107">(FontStyle)</span></span>  
  
 <span data-ttu-id="5cbfc-108">これらのメソッドによって返される数値は、サイズと、特定の単位から独立しているためフォント デザイン単位では<xref:System.Drawing.Font>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="5cbfc-109">次の図は、さまざまなメトリックを示します。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="5cbfc-110">![フォント テキスト](./media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="5cbfc-110">![Fonts Text](./media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cbfc-111">例</span><span class="sxs-lookup"><span data-stu-id="5cbfc-111">Example</span></span>  
 <span data-ttu-id="5cbfc-112">次の例では、Arial フォント ファミリの標準のスタイルのメトリックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="5cbfc-113">コードを作成も、 <xref:System.Drawing.Font> 16 ピクセルのサイズと、その特定のピクセル単位のメトリックが表示されます (Arial ファミリに基づく) オブジェクト<xref:System.Drawing.Font>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="5cbfc-114">次の図は、コード例の出力を示します。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="5cbfc-115">![フォント テキスト](./media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="5cbfc-115">![Fonts Text](./media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="5cbfc-116">前の図の出力の最初の 2 つの行に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="5cbfc-117"><xref:System.Drawing.Font>オブジェクトは、16 のサイズを返します、<xref:System.Drawing.FontFamily>オブジェクトは、2,048 の em の高さを返します。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="5cbfc-118">これら 2 つの数値 (16 と 2,048) は、キーをフォント デザイン単位と単位 (このケースのピクセル単位) の間の変換、<xref:System.Drawing.Font>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="5cbfc-119">たとえば、次のようにアセントをデザイン単位からピクセルに変換できます。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="5cbfc-120">![フォント テキスト](./media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="5cbfc-120">![Fonts Text](./media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="5cbfc-121">次のコードを配置テキスト垂直方向に設定して、<xref:System.Drawing.PointF.Y%2A>のデータ メンバーを<xref:System.Drawing.PointF>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="5cbfc-122">Y 座標が増加して`font.Height`テキストの新しい行はごとです。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="5cbfc-123"><xref:System.Drawing.Font.Height%2A>のプロパティを<xref:System.Drawing.Font>オブジェクトがその特定の行間 (ピクセル単位) でを返す<xref:System.Drawing.Font>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="5cbfc-124">この例では、によって返される数<xref:System.Drawing.Font.Height%2A>19。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="5cbfc-125">これは行間隔をピクセルに変換することで得られる数値 (整数に切り上げたもの) と同じであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="5cbfc-126">Em 高 (サイズまたは em サイズとも呼ばれます) がアセントと降下の合計ではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="5cbfc-127">アセントと降下の合計には、セルの高さが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="5cbfc-128">内部のレディング マイナス セルの高さは、em 高さと同じです。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="5cbfc-129">セルの高さと外部レディングは、線の間隔と同じです。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5cbfc-130">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5cbfc-130">Compiling the Code</span></span>  
 <span data-ttu-id="5cbfc-131">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e`、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="5cbfc-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cbfc-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cbfc-132">See also</span></span>

- [<span data-ttu-id="5cbfc-133">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="5cbfc-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="5cbfc-134">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="5cbfc-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
