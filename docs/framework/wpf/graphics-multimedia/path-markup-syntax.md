---
title: パス マークアップ構文
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: adcedcea6c8d6d988021cbbccf87bd25a042fd16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181861"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="2222c-102">パス マークアップ構文</span><span class="sxs-lookup"><span data-stu-id="2222c-102">Path Markup Syntax</span></span>
<span data-ttu-id="2222c-103">パスについては[、「WPF の図形と基本描画の概要](shapes-and-basic-drawing-in-wpf-overview.md)」と[「ジオメトリの概要](geometry-overview.md)」で説明されていますが、このトピックでは、パス ジオメトリをよりコンパクトに指定するために使用できる強力で複雑なミニ言語について[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2222c-103">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a><span data-ttu-id="2222c-104">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2222c-104">Prerequisites</span></span>  
 <span data-ttu-id="2222c-105">このトピックを理解するには、オブジェクトの<xref:System.Windows.Media.Geometry>基本的な機能を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2222c-105">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="2222c-106">詳細については、「[ジオメトリの概要](geometry-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2222c-106">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="2222c-107">StreamGeometry ミニ言語と PathFigureCollection ミニ言語</span><span class="sxs-lookup"><span data-stu-id="2222c-107">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="2222c-108">には、ジオメトリック パスを記述するためのミニ言語を提供する<xref:System.Windows.Media.StreamGeometry> <xref:System.Windows.Media.PathFigureCollection>2 つのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="2222c-108">provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
- <span data-ttu-id="2222c-109">ミニ言語は<xref:System.Windows.Media.StreamGeometry>、 のプロパティや要素のプロパティなど<xref:System.Windows.Media.Geometry>、 type<xref:System.Windows.UIElement.Clip%2A>の<xref:System.Windows.UIElement>プロパティを<xref:System.Windows.Shapes.Path.Data%2A>設定するときに使用します。 <xref:System.Windows.Shapes.Path></span><span class="sxs-lookup"><span data-stu-id="2222c-109">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="2222c-110">次の例では、属性構文を使用<xref:System.Windows.Media.StreamGeometry>して を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-110">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <span data-ttu-id="2222c-111">のプロパティを<xref:System.Windows.Media.PathFigureCollection>設定するときにミニ言語を<xref:System.Windows.Media.PathGeometry.Figures%2A>使用します。 <xref:System.Windows.Media.PathGeometry></span><span class="sxs-lookup"><span data-stu-id="2222c-111">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="2222c-112">次の例では、属性構文を使用して<xref:System.Windows.Media.PathFigureCollection>の<xref:System.Windows.Media.PathGeometry>を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-112">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="2222c-113">前の例からわかるように、2 つのミニ言語はほとんど同じです。</span><span class="sxs-lookup"><span data-stu-id="2222c-113">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="2222c-114">を使用できるどんな状況<xref:System.Windows.Media.PathGeometry>でも、常に使用することができます。 <xref:System.Windows.Media.StreamGeometry>だから、あなたはどちらを使用する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="2222c-114">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="2222c-115">パスを<xref:System.Windows.Media.StreamGeometry>作成した後で変更する必要がない場合は、 を使用します。パスを<xref:System.Windows.Media.PathGeometry>変更する必要がある場合は a を使用します。</span><span class="sxs-lookup"><span data-stu-id="2222c-115">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="2222c-116">オブジェクト<xref:System.Windows.Media.PathGeometry>と<xref:System.Windows.Media.StreamGeometry>オブジェクトの違いの詳細については、「[ジオメトリの概要](geometry-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2222c-116">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="2222c-117">空白についてのメモ</span><span class="sxs-lookup"><span data-stu-id="2222c-117">A Note about White Space</span></span>  
 <span data-ttu-id="2222c-118">簡潔にするために、この後のセクションで示す構文には 1 つの空白が使用されていますが、1 つの空白を使用できるところでは、常に複数の空白スペースも許容されます。</span><span class="sxs-lookup"><span data-stu-id="2222c-118">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="2222c-119">2 つの数値は、実際にはコンマまたは空白で区切る必要はありませんが、結果の文字列が明確でない場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2222c-119">Two numbers don’t actually have to be separated by a comma or white space, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="2222c-120">たとえば、`2..3`実際には2つの数字です。</span><span class="sxs-lookup"><span data-stu-id="2222c-120">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="2222c-121">と ".3" ) です。</span><span class="sxs-lookup"><span data-stu-id="2222c-121">And ".3".</span></span> <span data-ttu-id="2222c-122">同様に`2-3`、"2" と "-3" です。</span><span class="sxs-lookup"><span data-stu-id="2222c-122">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="2222c-123">どちらの場合も、コマンドの前後に空白は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2222c-123">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="2222c-124">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-124">Syntax</span></span>  
 <span data-ttu-id="2222c-125">属性[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の使用法の構文<xref:System.Windows.Media.StreamGeometry>は、オプション<xref:System.Windows.Media.FillRule>の値と 1 つ以上の図形の説明で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2222c-125">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="2222c-126">StreamGeometry XAML 属性使用構文</span><span class="sxs-lookup"><span data-stu-id="2222c-126">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|<span data-ttu-id="2222c-127">`<`*オブジェクト\*\*property*`="`プロパティ`fillRule` `figureDescription`[ `figureDescription`] [ ]`" ... />`</span><span class="sxs-lookup"><span data-stu-id="2222c-127">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
 <span data-ttu-id="2222c-128">属性[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]の使用法は<xref:System.Windows.Media.PathFigureCollection>、1 つ以上の図形の説明で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2222c-128">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="2222c-129">PathFigureCollection XAML 属性使用構文</span><span class="sxs-lookup"><span data-stu-id="2222c-129">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|<span data-ttu-id="2222c-130">`<`*オブジェクト\*\*property*`="``figureDescription`プロパティ`figureDescription`[ ]\*`" ... />`</span><span class="sxs-lookup"><span data-stu-id="2222c-130">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
|<span data-ttu-id="2222c-131">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-131">Term</span></span>|<span data-ttu-id="2222c-132">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-132">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2222c-133">*fillRule*</span><span class="sxs-lookup"><span data-stu-id="2222c-133">*fillRule*</span></span>|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-134">が を<xref:System.Windows.Media.StreamGeometry>使用<xref:System.Windows.Media.FillRule.EvenOdd>するかどうかを指定<xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>します。</span><span class="sxs-lookup"><span data-stu-id="2222c-134">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="2222c-135">-   `F0`塗りつぶし<xref:System.Windows.Media.FillRule.EvenOdd>ルールを指定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-135">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="2222c-136">-   `F1`塗りつぶし<xref:System.Windows.Media.FillRule.Nonzero>ルールを指定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-136">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="2222c-137">このコマンドを省略すると、サブパスはデフォルトの動作<xref:System.Windows.Media.FillRule.EvenOdd>(.</span><span class="sxs-lookup"><span data-stu-id="2222c-137">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="2222c-138">このコマンドを指定する場合は、先頭に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2222c-138">If you specify this command, you must place it first.</span></span>|  
|<span data-ttu-id="2222c-139">*figureDescription*</span><span class="sxs-lookup"><span data-stu-id="2222c-139">*figureDescription*</span></span>|<span data-ttu-id="2222c-140">移動コマンドと描画コマンド (および省略可能な閉じるコマンド) で構成される図形。</span><span class="sxs-lookup"><span data-stu-id="2222c-140">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> <span data-ttu-id="2222c-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span><span class="sxs-lookup"><span data-stu-id="2222c-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span></span>|  
|<span data-ttu-id="2222c-142">*moveCommand*</span><span class="sxs-lookup"><span data-stu-id="2222c-142">*moveCommand*</span></span>|<span data-ttu-id="2222c-143">図形の開始位置を指定する移動コマンド。</span><span class="sxs-lookup"><span data-stu-id="2222c-143">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="2222c-144">「[移動コマンド](#themovecommand)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2222c-144">See the [Move Command](#themovecommand) section.</span></span>|  
|<span data-ttu-id="2222c-145">*drawCommands*</span><span class="sxs-lookup"><span data-stu-id="2222c-145">*drawCommands*</span></span>|<span data-ttu-id="2222c-146">図の内容を記述する 1 つまたは複数の描画コマンド。</span><span class="sxs-lookup"><span data-stu-id="2222c-146">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="2222c-147">「[コマンドの描画](#drawcommands)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2222c-147">See the [Draw Commands](#drawcommands) section.</span></span>|  
|<span data-ttu-id="2222c-148">*closeCommand*</span><span class="sxs-lookup"><span data-stu-id="2222c-148">*closeCommand*</span></span>|<span data-ttu-id="2222c-149">図形を閉じるコマンド (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="2222c-149">An optional close command that closes figure.</span></span> <span data-ttu-id="2222c-150">「[コマンドを閉じる](#closecommand)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2222c-150">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a><span data-ttu-id="2222c-151">移動コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-151">Move Command</span></span>  
 <span data-ttu-id="2222c-152">新しい図形の始点を指定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-152">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="2222c-153">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-153">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-154">`M`*スタートポイント*</span><span class="sxs-lookup"><span data-stu-id="2222c-154">`M` *startPoint*</span></span><br /><br /> <span data-ttu-id="2222c-155">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-155">- or -</span></span><br /><br /> <span data-ttu-id="2222c-156">`m`*スタートポイント*</span><span class="sxs-lookup"><span data-stu-id="2222c-156">`m` *startPoint*</span></span>|  
  
|<span data-ttu-id="2222c-157">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-157">Term</span></span>|<span data-ttu-id="2222c-158">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-158">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2222c-159">*startPoint*</span><span class="sxs-lookup"><span data-stu-id="2222c-159">*startPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-160">新しい図形の始点。</span><span class="sxs-lookup"><span data-stu-id="2222c-160">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="2222c-161">大文字`M`は絶対値であることを`startPoint`示します。小文字`m`は、前`startPoint`の点へのオフセットであることを示し、(0,0) が存在しない場合は、その点を示します。</span><span class="sxs-lookup"><span data-stu-id="2222c-161">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="2222c-162">移動コマンドの後ろに複数の点を指定した場合は、直線コマンドを指定した場合でも、これらの点を結ぶ線が描画されます。</span><span class="sxs-lookup"><span data-stu-id="2222c-162">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a><span data-ttu-id="2222c-163">描画コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-163">Draw Commands</span></span>  
 <span data-ttu-id="2222c-164">描画コマンドは、さまざまな図形コマンドで構成できます。</span><span class="sxs-lookup"><span data-stu-id="2222c-164">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="2222c-165">次の図形のコマンドを使用できます。直線、水平線、垂直線、3 次ベジエ曲線、2 次ベジエ曲線、スムーズ 3 次ベジエ曲線、スムーズ 2 次ベジエ曲線、および楕円の円弧。</span><span class="sxs-lookup"><span data-stu-id="2222c-165">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="2222c-166">各コマンドは、大文字または小文字で入力します。大文字は絶対値を、小文字は相対値を表し、そのセグメントの制御点は、前の例の終点を基準とします。</span><span class="sxs-lookup"><span data-stu-id="2222c-166">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="2222c-167">同じタイプの複数のコマンドを順次入力する場合は、重複するコマンド入力を省略できます。たとえば、`L 100,200 300,400`と同じ`L 100,200 L 300,400`値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2222c-167">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="2222c-168">次の表では、**移動**コマンドと**描画**コマンドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2222c-168">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="2222c-169">直線コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-169">Line Command</span></span>  
 <span data-ttu-id="2222c-170">現在の点と指定された終点の間に直線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-170">Creates a straight line between the current point and the specified end point.</span></span> <span data-ttu-id="2222c-171">`l 20 30`有効`L 20,30`な**行**コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2222c-171">`l 20 30` and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="2222c-172">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-172">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-173">`L`*エンドポイント*</span><span class="sxs-lookup"><span data-stu-id="2222c-173">`L` *endPoint*</span></span><br /><br /> <span data-ttu-id="2222c-174">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-174">- or -</span></span><br /><br /> <span data-ttu-id="2222c-175">`l`*エンドポイント*</span><span class="sxs-lookup"><span data-stu-id="2222c-175">`l` *endPoint*</span></span>|  
  
|<span data-ttu-id="2222c-176">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-176">Term</span></span>|<span data-ttu-id="2222c-177">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-177">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2222c-178">*エンドポイント*</span><span class="sxs-lookup"><span data-stu-id="2222c-178">*endPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-179">線の終点。</span><span class="sxs-lookup"><span data-stu-id="2222c-179">The end point of the line.</span></span>|  

<span data-ttu-id="2222c-180">大文字`L`は絶対値であることを`endPoint`示します。小文字`l`は、前`endPoint`の点へのオフセットであることを示し、(0,0) が存在しない場合は、その点を示します。</span><span class="sxs-lookup"><span data-stu-id="2222c-180">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="2222c-181">水平線コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-181">Horizontal Line Command</span></span>  
 <span data-ttu-id="2222c-182">現在の点と指定された x 座標の間に水平線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-182">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> <span data-ttu-id="2222c-183">`H 90` は、有効な水平線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2222c-183">`H 90` is an example of a valid horizontal line command.</span></span>

|<span data-ttu-id="2222c-184">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-184">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-185">`H`  *X*</span><span class="sxs-lookup"><span data-stu-id="2222c-185">`H`  *x*</span></span><br /><br /> <span data-ttu-id="2222c-186">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-186">- or -</span></span><br /><br /> <span data-ttu-id="2222c-187">`h`  *X*</span><span class="sxs-lookup"><span data-stu-id="2222c-187">`h`  *x*</span></span>|  
  
|<span data-ttu-id="2222c-188">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-188">Term</span></span>|<span data-ttu-id="2222c-189">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-189">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2222c-190">*X*</span><span class="sxs-lookup"><span data-stu-id="2222c-190">*x*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-191">直線の終点の x 座標。</span><span class="sxs-lookup"><span data-stu-id="2222c-191">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="2222c-192">大文字`H`は絶対値であることを`x`示します。小文字`h`は、前`x`の点へのオフセットであることを示し、(0,0) が存在しない場合は、その点を示します。</span><span class="sxs-lookup"><span data-stu-id="2222c-192">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="2222c-193">垂直線コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-193">Vertical Line Command</span></span>  
 <span data-ttu-id="2222c-194">現在の点と指定された y 座標の間に垂直線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-194">Creates a vertical line between the current point and the specified y-coordinate.</span></span> <span data-ttu-id="2222c-195">`v 90` は、有効な垂直線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2222c-195">`v 90` is an example of a valid vertical line command.</span></span>

|<span data-ttu-id="2222c-196">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-196">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-197">`V`  *Y*</span><span class="sxs-lookup"><span data-stu-id="2222c-197">`V`  *y*</span></span><br /><br /> <span data-ttu-id="2222c-198">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-198">- or -</span></span><br /><br /> <span data-ttu-id="2222c-199">`v`  *Y*</span><span class="sxs-lookup"><span data-stu-id="2222c-199">`v`  *y*</span></span>|  
  
|<span data-ttu-id="2222c-200">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-200">Term</span></span>|<span data-ttu-id="2222c-201">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-201">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2222c-202">*Y*</span><span class="sxs-lookup"><span data-stu-id="2222c-202">*y*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-203">直線の終点の y 座標。</span><span class="sxs-lookup"><span data-stu-id="2222c-203">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="2222c-204">大文字`V`は絶対値であることを`y`示します。小文字`v`は、前`y`の点へのオフセットであることを示し、(0,0) が存在しない場合は、その点を示します。</span><span class="sxs-lookup"><span data-stu-id="2222c-204">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  

### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="2222c-205">3 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-205">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="2222c-206">指定した 2 つのコントロール ポイント (1`controlPoint`と`controlPoint`2) を使用して、現在の点と指定した終点の間に 3 次ベジエ曲線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-206">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> <span data-ttu-id="2222c-207">`C 100,200 200,400 300,200` は、有効な曲線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2222c-207">`C 100,200 200,400 300,200` is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="2222c-208">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-208">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-209">`C``controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="2222c-210">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-210">- or -</span></span><br /><br /> <span data-ttu-id="2222c-211">`c``controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="2222c-212">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-212">Term</span></span>|<span data-ttu-id="2222c-213">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-213">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2222c-214">`controlPoint`1</span><span class="sxs-lookup"><span data-stu-id="2222c-214">`controlPoint`1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-215">曲線の 1 つ目の制御点。曲線の前半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-215">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|<span data-ttu-id="2222c-216">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="2222c-216">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-217">曲線の 2 つ目の制御点。曲線の後半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-217">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-218">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2222c-218">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="2222c-219">2 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-219">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="2222c-220">指定されたコントロール ポイント ()`controlPoint`を使用して、現在の点と指定した終点の間に 2 次ベジエ曲線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-220">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> <span data-ttu-id="2222c-221">`q 100,200 300,200` は、有効な 2 次ベジエ曲線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2222c-221">`q 100,200 300,200` is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="2222c-222">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-222">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-223">`Q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-223">`Q` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="2222c-224">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-224">- or -</span></span><br /><br /> <span data-ttu-id="2222c-225">`q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-225">`q` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="2222c-226">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-226">Term</span></span>|<span data-ttu-id="2222c-227">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-227">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-228">曲線の制御点。曲線の前半と後半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-228">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-229">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2222c-229">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="2222c-230">スムーズ 3 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-230">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="2222c-231">現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-231">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="2222c-232">1 つ目の制御点は、現在の点に対する前のコマンドの 2 つ目の制御点のリフレクションと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2222c-232">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="2222c-233">前のコマンドが存在しない場合、または前のコマンドが 3 次ベジエ曲線コマンドまたはスムーズ 3 次ベジエ曲線コマンドでなかった場合、1 つ目の制御点は、現在の点と一致するとみなされます。</span><span class="sxs-lookup"><span data-stu-id="2222c-233">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="2222c-234">2 番目の制御点は、曲線の終点の制御点で、2`controlPoint`で指定されます。</span><span class="sxs-lookup"><span data-stu-id="2222c-234">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="2222c-235">たとえば、`S 100,200 200,300`有効なスムーズな 3 次ベジェ曲線コマンドです。</span><span class="sxs-lookup"><span data-stu-id="2222c-235">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="2222c-236">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-236">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-237">`S``controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-237">`S` `controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="2222c-238">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-238">- or -</span></span><br /><br /> <span data-ttu-id="2222c-239">`s``controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-239">`s` `controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="2222c-240">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-240">Term</span></span>|<span data-ttu-id="2222c-241">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-241">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2222c-242">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="2222c-242">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-243">曲線の制御点。曲線の後半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-243">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-244">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2222c-244">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="2222c-245">スムーズ 2 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-245">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="2222c-246">現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-246">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="2222c-247">制御点は、現在の点に対する前のコマンドの制御点のリフレクションと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2222c-247">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="2222c-248">前のコマンドが存在しない場合、または前のコマンドが 2 次ベジエ曲線コマンドまたはスムーズ 2 次ベジエ曲線コマンドでなかった場合、制御点は、現在の点と一致するとみなされます。</span><span class="sxs-lookup"><span data-stu-id="2222c-248">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="2222c-249">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-249">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-250">`T` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-250">`T` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="2222c-251">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-251">- or -</span></span><br /><br /> <span data-ttu-id="2222c-252">`t` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-252">`t` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="2222c-253">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-253">Term</span></span>|<span data-ttu-id="2222c-254">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-254">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-255">曲線の制御点。曲線の前半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-255">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-256">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2222c-256">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="2222c-257">楕円の円弧コマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-257">Elliptical Arc Command</span></span>  
 <span data-ttu-id="2222c-258">現在の点と指定された終点の間に楕円の円弧を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-258">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="2222c-259">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-259">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span><br /><br /> <span data-ttu-id="2222c-261">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-261">- or -</span></span><br /><br /> <span data-ttu-id="2222c-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2222c-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span>|  
  
|<span data-ttu-id="2222c-263">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-263">Term</span></span>|<span data-ttu-id="2222c-264">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-264">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-265">円弧の x 半径と y 半径。</span><span class="sxs-lookup"><span data-stu-id="2222c-265">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-266">楕円の回転 (度単位)。</span><span class="sxs-lookup"><span data-stu-id="2222c-266">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="2222c-267">円弧の角度を 180 度以上にする場合は 1 に設定します。それ以外の場合は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-267">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="2222c-268">円弧が正の角度の方向に描画される場合は 1 に設定します。それ以外の場合は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2222c-268">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-269">円弧が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2222c-269">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a><span data-ttu-id="2222c-270">閉じるコマンド</span><span class="sxs-lookup"><span data-stu-id="2222c-270">The Close Command</span></span>  
 <span data-ttu-id="2222c-271">現在の図形を終了し、現在の点と図の開始点を結ぶ線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-271">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="2222c-272">このコマンドは、図形の最初のセグメントと最後のセグメントの間に線結合 (コーナー) を作成します。</span><span class="sxs-lookup"><span data-stu-id="2222c-272">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="2222c-273">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-273">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="2222c-274">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-274">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a><span data-ttu-id="2222c-275">点の構文</span><span class="sxs-lookup"><span data-stu-id="2222c-275">Point Syntax</span></span>  
 <span data-ttu-id="2222c-276">(0,0) が左上隅である点の x 座標と y 座標を記述します。</span><span class="sxs-lookup"><span data-stu-id="2222c-276">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="2222c-277">構文</span><span class="sxs-lookup"><span data-stu-id="2222c-277">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2222c-278">`x` `,` `y`</span><span class="sxs-lookup"><span data-stu-id="2222c-278">`x` `,` `y`</span></span><br /><br /> <span data-ttu-id="2222c-279">- または -</span><span class="sxs-lookup"><span data-stu-id="2222c-279">- or -</span></span><br /><br /> <span data-ttu-id="2222c-280">`x` `y`</span><span class="sxs-lookup"><span data-stu-id="2222c-280">`x` `y`</span></span>|  
  
|<span data-ttu-id="2222c-281">期間</span><span class="sxs-lookup"><span data-stu-id="2222c-281">Term</span></span>|<span data-ttu-id="2222c-282">説明</span><span class="sxs-lookup"><span data-stu-id="2222c-282">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-283">点の x 座標。</span><span class="sxs-lookup"><span data-stu-id="2222c-283">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2222c-284">点の y 座標。</span><span class="sxs-lookup"><span data-stu-id="2222c-284">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a><span data-ttu-id="2222c-285">特殊な値</span><span class="sxs-lookup"><span data-stu-id="2222c-285">Special Values</span></span>  
 <span data-ttu-id="2222c-286">標準的な数値ではなく、次の特殊な値を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2222c-286">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="2222c-287">これらの値では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2222c-287">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="2222c-288">Infinity</span><span class="sxs-lookup"><span data-stu-id="2222c-288">Infinity</span></span>  
 <span data-ttu-id="2222c-289">を<xref:System.Double.PositiveInfinity?displayProperty=nameWithType>表します。</span><span class="sxs-lookup"><span data-stu-id="2222c-289">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2222c-290">-Infinity</span><span class="sxs-lookup"><span data-stu-id="2222c-290">-Infinity</span></span>  
 <span data-ttu-id="2222c-291">を<xref:System.Double.NegativeInfinity?displayProperty=nameWithType>表します。</span><span class="sxs-lookup"><span data-stu-id="2222c-291">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2222c-292">(NaN)</span><span class="sxs-lookup"><span data-stu-id="2222c-292">NaN</span></span>  
 <span data-ttu-id="2222c-293">を<xref:System.Double.NaN?displayProperty=nameWithType>表します。</span><span class="sxs-lookup"><span data-stu-id="2222c-293">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2222c-294">指数表記を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2222c-294">You may also use scientific notation.</span></span> <span data-ttu-id="2222c-295">たとえば、`+1.e17` は有効な値です。</span><span class="sxs-lookup"><span data-stu-id="2222c-295">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2222c-296">関連項目</span><span class="sxs-lookup"><span data-stu-id="2222c-296">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [<span data-ttu-id="2222c-297">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="2222c-297">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="2222c-298">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="2222c-298">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="2222c-299">ハウツートピック</span><span class="sxs-lookup"><span data-stu-id="2222c-299">How-to Topics</span></span>](geometries-how-to-topics.md)
