---
title: パス マークアップ構文
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 32eefba26b5e04370599e4c97767b6662cfd1c13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008203"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="2758f-102">パス マークアップ構文</span><span class="sxs-lookup"><span data-stu-id="2758f-102">Path Markup Syntax</span></span>
<span data-ttu-id="2758f-103">パスについては、「[WPF での図形と基本描画の概要](shapes-and-basic-drawing-in-wpf-overview.md)」および「[ジオメトリの概要](geometry-overview.md)」で説明します。ただし、このトピックでは、Extensible Application Markup Language (XAML)[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を使用してパス ジオメトリをよりコンパクトに指定できる、強力で複合的なミニ言語について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="2758f-103">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a><span data-ttu-id="2758f-104">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2758f-104">Prerequisites</span></span>  
 <span data-ttu-id="2758f-105">このトピックを理解しておく必要があるの基本的な機能を使い慣れて<xref:System.Windows.Media.Geometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2758f-105">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="2758f-106">詳細については、次を参照してください。、[ジオメトリの概要](geometry-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="2758f-106">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="2758f-107">StreamGeometry ミニ言語と PathFigureCollection ミニ言語</span><span class="sxs-lookup"><span data-stu-id="2758f-107">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="2758f-108">ジオメトリック パスを記述するためのミニ言語を提供する 2 つのクラスを提供します。<xref:System.Windows.Media.StreamGeometry>と<xref:System.Windows.Media.PathFigureCollection>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-108">provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
- <span data-ttu-id="2758f-109">使用する、<xref:System.Windows.Media.StreamGeometry>型のプロパティを設定するときに、ミニ言語<xref:System.Windows.Media.Geometry>など、<xref:System.Windows.UIElement.Clip%2A>のプロパティを<xref:System.Windows.UIElement>または<xref:System.Windows.Shapes.Path.Data%2A>のプロパティを<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="2758f-109">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="2758f-110">次の例では、属性構文を使用して、作成、<xref:System.Windows.Media.StreamGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-110">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <span data-ttu-id="2758f-111">使用する、<xref:System.Windows.Media.PathFigureCollection>ミニ言語を設定するとき、<xref:System.Windows.Media.PathGeometry.Figures%2A>のプロパティを<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-111">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="2758f-112">次の例では、属性構文を使用して、作成、<xref:System.Windows.Media.PathFigureCollection>の<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-112">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="2758f-113">前の例からわかるように、2 つのミニ言語はほとんど同じです。</span><span class="sxs-lookup"><span data-stu-id="2758f-113">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="2758f-114">使用することは常に、<xref:System.Windows.Media.PathGeometry>でどのような状況を使用する場合、 <xref:System.Windows.Media.StreamGeometry>; はどれを使用する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="2758f-114">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="2758f-115">使用して、<xref:System.Windows.Media.StreamGeometry>使用して、それを作成した後、パスを変更する必要のないとき、<xref:System.Windows.Media.PathGeometry>実行パスを変更する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="2758f-115">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="2758f-116">間の相違点の詳細については<xref:System.Windows.Media.PathGeometry>と<xref:System.Windows.Media.StreamGeometry>、オブジェクトを参照してください、[ジオメトリの概要](geometry-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="2758f-116">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="2758f-117">空白についてのメモ</span><span class="sxs-lookup"><span data-stu-id="2758f-117">A Note about White Space</span></span>  
 <span data-ttu-id="2758f-118">簡潔にするために、この後のセクションで示す構文には 1 つの空白が使用されていますが、1 つの空白を使用できるところでは、常に複数の空白スペースも許容されます。</span><span class="sxs-lookup"><span data-stu-id="2758f-118">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="2758f-119">2 つの数値がコンマまたは空白で区切って指定する必要はありません実際にが、このことができる場合にのみ実行結果の文字列があいまいです。</span><span class="sxs-lookup"><span data-stu-id="2758f-119">Two numbers don’t actually have to be separated by a comma or white space, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="2758f-120">たとえば、`2..3`が実際には 2 つの数値。"2."</span><span class="sxs-lookup"><span data-stu-id="2758f-120">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="2758f-121">と ".3" ) です。</span><span class="sxs-lookup"><span data-stu-id="2758f-121">And ".3".</span></span> <span data-ttu-id="2758f-122">同様に、 `2-3` 「2」と「-3」です。</span><span class="sxs-lookup"><span data-stu-id="2758f-122">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="2758f-123">どちらの場合も、コマンドの前後に空白は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2758f-123">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="2758f-124">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-124">Syntax</span></span>  
 <span data-ttu-id="2758f-125">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]属性の使用法の構文を<xref:System.Windows.Media.StreamGeometry>は省略可能なので構成されます<xref:System.Windows.Media.FillRule>値と 1 つ以上の説明図します。</span><span class="sxs-lookup"><span data-stu-id="2758f-125">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="2758f-126">StreamGeometry XAML 属性使用構文</span><span class="sxs-lookup"><span data-stu-id="2758f-126">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|<span data-ttu-id="2758f-127">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span><span class="sxs-lookup"><span data-stu-id="2758f-127">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
 <span data-ttu-id="2758f-128">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]属性の使用法の構文を<xref:System.Windows.Media.PathFigureCollection>は 1 つまたは複数の図の説明で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2758f-128">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="2758f-129">PathFigureCollection XAML 属性使用構文</span><span class="sxs-lookup"><span data-stu-id="2758f-129">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|<span data-ttu-id="2758f-130">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span><span class="sxs-lookup"><span data-stu-id="2758f-130">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
|<span data-ttu-id="2758f-131">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-131">Term</span></span>|<span data-ttu-id="2758f-132">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-132">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2758f-133">*fillRule*</span><span class="sxs-lookup"><span data-stu-id="2758f-133">*fillRule*</span></span>|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-134">指定するかどうか、<xref:System.Windows.Media.StreamGeometry>を使用して、<xref:System.Windows.Media.FillRule.EvenOdd>または<xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-134">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="2758f-135">-   `F0` 指定します、<xref:System.Windows.Media.FillRule.EvenOdd>塗りつぶしルール。</span><span class="sxs-lookup"><span data-stu-id="2758f-135">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="2758f-136">-   `F1` 指定します、<xref:System.Windows.Media.FillRule.Nonzero>塗りつぶしルール。</span><span class="sxs-lookup"><span data-stu-id="2758f-136">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="2758f-137">サブパスは既定の動作を使用してこのコマンドを省略すると、<xref:System.Windows.Media.FillRule.EvenOdd>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-137">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="2758f-138">このコマンドを指定する場合は、先頭に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2758f-138">If you specify this command, you must place it first.</span></span>|  
|<span data-ttu-id="2758f-139">*figureDescription*</span><span class="sxs-lookup"><span data-stu-id="2758f-139">*figureDescription*</span></span>|<span data-ttu-id="2758f-140">移動コマンドと描画コマンド (および省略可能な閉じるコマンド) で構成される図形。</span><span class="sxs-lookup"><span data-stu-id="2758f-140">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> <span data-ttu-id="2758f-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span><span class="sxs-lookup"><span data-stu-id="2758f-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span></span>|  
|<span data-ttu-id="2758f-142">*moveCommand*</span><span class="sxs-lookup"><span data-stu-id="2758f-142">*moveCommand*</span></span>|<span data-ttu-id="2758f-143">図形の開始位置を指定する移動コマンド。</span><span class="sxs-lookup"><span data-stu-id="2758f-143">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="2758f-144">参照してください、 [Move コマンド](#themovecommand)セクション。</span><span class="sxs-lookup"><span data-stu-id="2758f-144">See the [Move Command](#themovecommand) section.</span></span>|  
|<span data-ttu-id="2758f-145">*drawCommands*</span><span class="sxs-lookup"><span data-stu-id="2758f-145">*drawCommands*</span></span>|<span data-ttu-id="2758f-146">図の内容を記述する 1 つまたは複数の描画コマンド。</span><span class="sxs-lookup"><span data-stu-id="2758f-146">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="2758f-147">参照してください、[描画コマンド](#drawcommands)セクション。</span><span class="sxs-lookup"><span data-stu-id="2758f-147">See the [Draw Commands](#drawcommands) section.</span></span>|  
|<span data-ttu-id="2758f-148">*closeCommand*</span><span class="sxs-lookup"><span data-stu-id="2758f-148">*closeCommand*</span></span>|<span data-ttu-id="2758f-149">図形を閉じるコマンド (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="2758f-149">An optional close command that closes figure.</span></span> <span data-ttu-id="2758f-150">参照してください、[閉じるコマンド](#closecommand)セクション。</span><span class="sxs-lookup"><span data-stu-id="2758f-150">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a><span data-ttu-id="2758f-151">移動コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-151">Move Command</span></span>  
 <span data-ttu-id="2758f-152">新しい図形の始点を指定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-152">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="2758f-153">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-153">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-154">`M` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="2758f-154">`M` *startPoint*</span></span><br /><br /> <span data-ttu-id="2758f-155">または</span><span class="sxs-lookup"><span data-stu-id="2758f-155">- or -</span></span><br /><br /> <span data-ttu-id="2758f-156">`m` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="2758f-156">`m` *startPoint*</span></span>|  
  
|<span data-ttu-id="2758f-157">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-157">Term</span></span>|<span data-ttu-id="2758f-158">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-158">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2758f-159">*startPoint*</span><span class="sxs-lookup"><span data-stu-id="2758f-159">*startPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-160">新しい図形の始点。</span><span class="sxs-lookup"><span data-stu-id="2758f-160">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="2758f-161">大文字`M`ことを示します`startPoint`絶対値; は、小文字`m`ことを示します`startPoint`過去の時点へのオフセットです (0, 0) が存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="2758f-161">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="2758f-162">移動コマンドの後ろに複数の点を指定した場合は、直線コマンドを指定した場合でも、これらの点を結ぶ線が描画されます。</span><span class="sxs-lookup"><span data-stu-id="2758f-162">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a><span data-ttu-id="2758f-163">描画コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-163">Draw Commands</span></span>  
 <span data-ttu-id="2758f-164">描画コマンドは、さまざまな図形コマンドで構成できます。</span><span class="sxs-lookup"><span data-stu-id="2758f-164">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="2758f-165">次の図形のコマンドを使用できます。直線、水平線、垂直線、3 次ベジエ曲線、2 次ベジエ曲線、スムーズ 3 次ベジエ曲線、スムーズ 2 次ベジエ曲線、および楕円の円弧。</span><span class="sxs-lookup"><span data-stu-id="2758f-165">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="2758f-166">各コマンドは、大文字または小文字で入力します。大文字は絶対値を、小文字は相対値を表し、そのセグメントの制御点は、前の例の終点を基準とします。</span><span class="sxs-lookup"><span data-stu-id="2758f-166">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="2758f-167">同じ型の 1 つ以上のコマンドを順番に入力するは、重複するコマンドの入力を省略できます。たとえば、`L 100,200 300,400`と等価`L 100,200 L 300,400`します。</span><span class="sxs-lookup"><span data-stu-id="2758f-167">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="2758f-168">次の表、**移動**と**描画**コマンド。</span><span class="sxs-lookup"><span data-stu-id="2758f-168">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="2758f-169">直線コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-169">Line Command</span></span>  
 <span data-ttu-id="2758f-170">現在の点と指定された終点の間に直線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-170">Creates a straight line between the current point and the specified end point.</span></span> <span data-ttu-id="2758f-171">`l 20 30` `L 20,30`の有効な例を示します**行**コマンド。</span><span class="sxs-lookup"><span data-stu-id="2758f-171">`l 20 30` and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="2758f-172">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-172">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-173">`L` *endPoint*</span><span class="sxs-lookup"><span data-stu-id="2758f-173">`L` *endPoint*</span></span><br /><br /> <span data-ttu-id="2758f-174">または</span><span class="sxs-lookup"><span data-stu-id="2758f-174">- or -</span></span><br /><br /> <span data-ttu-id="2758f-175">`l` *endPoint*</span><span class="sxs-lookup"><span data-stu-id="2758f-175">`l` *endPoint*</span></span>|  
  
|<span data-ttu-id="2758f-176">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-176">Term</span></span>|<span data-ttu-id="2758f-177">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-177">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2758f-178">*endPoint*</span><span class="sxs-lookup"><span data-stu-id="2758f-178">*endPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-179">線の終点。</span><span class="sxs-lookup"><span data-stu-id="2758f-179">The end point of the line.</span></span>|  

<span data-ttu-id="2758f-180">大文字`L`ことを示します`endPoint`絶対値; は、小文字`l`ことを示します`endPoint`過去の時点へのオフセットです (0, 0) が存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="2758f-180">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="2758f-181">水平線コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-181">Horizontal Line Command</span></span>  
 <span data-ttu-id="2758f-182">現在の点と指定された x 座標の間に水平線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-182">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> <span data-ttu-id="2758f-183">`H 90` は、有効な水平線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2758f-183">`H 90` is an example of a valid horizontal line command.</span></span>

|<span data-ttu-id="2758f-184">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-184">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-185">`H`  *x*</span><span class="sxs-lookup"><span data-stu-id="2758f-185">`H`  *x*</span></span><br /><br /> <span data-ttu-id="2758f-186">または</span><span class="sxs-lookup"><span data-stu-id="2758f-186">- or -</span></span><br /><br /> <span data-ttu-id="2758f-187">`h`  *x*</span><span class="sxs-lookup"><span data-stu-id="2758f-187">`h`  *x*</span></span>|  
  
|<span data-ttu-id="2758f-188">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-188">Term</span></span>|<span data-ttu-id="2758f-189">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-189">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2758f-190">*x*</span><span class="sxs-lookup"><span data-stu-id="2758f-190">*x*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-191">直線の終点の x 座標。</span><span class="sxs-lookup"><span data-stu-id="2758f-191">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="2758f-192">大文字`H`ことを示します`x`絶対値; は、小文字`h`ことを示します`x`過去の時点へのオフセットです (0, 0) が存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="2758f-192">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="2758f-193">垂直線コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-193">Vertical Line Command</span></span>  
 <span data-ttu-id="2758f-194">現在の点と指定された y 座標の間に垂直線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-194">Creates a vertical line between the current point and the specified y-coordinate.</span></span> <span data-ttu-id="2758f-195">`v 90` は、有効な垂直線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2758f-195">`v 90` is an example of a valid vertical line command.</span></span>

|<span data-ttu-id="2758f-196">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-196">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-197">`V`  *y*</span><span class="sxs-lookup"><span data-stu-id="2758f-197">`V`  *y*</span></span><br /><br /> <span data-ttu-id="2758f-198">または</span><span class="sxs-lookup"><span data-stu-id="2758f-198">- or -</span></span><br /><br /> <span data-ttu-id="2758f-199">`v`  *y*</span><span class="sxs-lookup"><span data-stu-id="2758f-199">`v`  *y*</span></span>|  
  
|<span data-ttu-id="2758f-200">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-200">Term</span></span>|<span data-ttu-id="2758f-201">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-201">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2758f-202">*y*</span><span class="sxs-lookup"><span data-stu-id="2758f-202">*y*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-203">直線の終点の y 座標。</span><span class="sxs-lookup"><span data-stu-id="2758f-203">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="2758f-204">大文字`V`ことを示します`y`絶対値; は、小文字`v`ことを示します`y`過去の時点へのオフセットです (0, 0) が存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="2758f-204">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  
    
### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="2758f-205">3 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-205">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="2758f-206">2 つの指定されたコントロール ポイントを使用して、現在の点と指定された終点の間に 3 次ベジエ曲線を作成します (`controlPoint`1 と`controlPoint`2)。</span><span class="sxs-lookup"><span data-stu-id="2758f-206">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> <span data-ttu-id="2758f-207">`C 100,200 200,400 300,200` は、有効な曲線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2758f-207">`C 100,200 200,400 300,200` is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="2758f-208">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-208">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="2758f-210">または</span><span class="sxs-lookup"><span data-stu-id="2758f-210">- or -</span></span><br /><br /> <span data-ttu-id="2758f-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="2758f-212">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-212">Term</span></span>|<span data-ttu-id="2758f-213">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-213">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2758f-214">`controlPoint`1</span><span class="sxs-lookup"><span data-stu-id="2758f-214">`controlPoint`1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-215">曲線の 1 つ目の制御点。曲線の前半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-215">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|<span data-ttu-id="2758f-216">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="2758f-216">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-217">曲線の 2 つ目の制御点。曲線の後半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-217">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-218">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2758f-218">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="2758f-219">2 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-219">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="2758f-220">指定されたコントロール ポイントを使用して現在の点と指定された終点の間で 2 次ベジエ曲線を作成します (`controlPoint`)。</span><span class="sxs-lookup"><span data-stu-id="2758f-220">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> <span data-ttu-id="2758f-221">`q 100,200 300,200` は、有効な 2 次ベジエ曲線コマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="2758f-221">`q 100,200 300,200` is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="2758f-222">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-222">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-223">`Q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-223">`Q` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="2758f-224">または</span><span class="sxs-lookup"><span data-stu-id="2758f-224">- or -</span></span><br /><br /> <span data-ttu-id="2758f-225">`q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-225">`q` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="2758f-226">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-226">Term</span></span>|<span data-ttu-id="2758f-227">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-227">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-228">曲線の制御点。曲線の前半と後半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-228">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-229">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2758f-229">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="2758f-230">スムーズ 3 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-230">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="2758f-231">現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-231">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="2758f-232">1 つ目の制御点は、現在の点に対する前のコマンドの 2 つ目の制御点のリフレクションと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2758f-232">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="2758f-233">前のコマンドが存在しない場合、または前のコマンドが 3 次ベジエ曲線コマンドまたはスムーズ 3 次ベジエ曲線コマンドでなかった場合、1 つ目の制御点は、現在の点と一致するとみなされます。</span><span class="sxs-lookup"><span data-stu-id="2758f-233">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="2758f-234">曲線の終了の制御点は、2 つ目のコントロール ポイントで指定された`controlPoint`2。</span><span class="sxs-lookup"><span data-stu-id="2758f-234">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="2758f-235">たとえば、`S 100,200 200,300`は、有効なスムーズ 3 次ベジエ曲線コマンド。</span><span class="sxs-lookup"><span data-stu-id="2758f-235">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="2758f-236">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-236">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-237">`S` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-237">`S` `controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="2758f-238">または</span><span class="sxs-lookup"><span data-stu-id="2758f-238">- or -</span></span><br /><br /> <span data-ttu-id="2758f-239">`s` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-239">`s` `controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="2758f-240">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-240">Term</span></span>|<span data-ttu-id="2758f-241">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-241">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2758f-242">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="2758f-242">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-243">曲線の制御点。曲線の後半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-243">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-244">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2758f-244">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="2758f-245">スムーズ 2 次ベジエ曲線コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-245">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="2758f-246">現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-246">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="2758f-247">制御点は、現在の点に対する前のコマンドの制御点のリフレクションと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2758f-247">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="2758f-248">前のコマンドが存在しない場合、または前のコマンドが 2 次ベジエ曲線コマンドまたはスムーズ 2 次ベジエ曲線コマンドでなかった場合、制御点は、現在の点と一致するとみなされます。</span><span class="sxs-lookup"><span data-stu-id="2758f-248">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="2758f-249">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-249">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-250">`T` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-250">`T` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="2758f-251">または</span><span class="sxs-lookup"><span data-stu-id="2758f-251">- or -</span></span><br /><br /> <span data-ttu-id="2758f-252">`t` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-252">`t` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="2758f-253">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-253">Term</span></span>|<span data-ttu-id="2758f-254">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-254">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-255">曲線の制御点。曲線の前半の接線を決定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-255">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-256">曲線が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2758f-256">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="2758f-257">楕円の円弧コマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-257">Elliptical Arc Command</span></span>  
 <span data-ttu-id="2758f-258">現在の点と指定された終点の間に楕円の円弧を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-258">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="2758f-259">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-259">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span><br /><br /> <span data-ttu-id="2758f-261">または</span><span class="sxs-lookup"><span data-stu-id="2758f-261">- or -</span></span><br /><br /> <span data-ttu-id="2758f-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="2758f-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span>|  
  
|<span data-ttu-id="2758f-263">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-263">Term</span></span>|<span data-ttu-id="2758f-264">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-264">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-265">円弧の x 半径と y 半径。</span><span class="sxs-lookup"><span data-stu-id="2758f-265">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-266">楕円の回転 (度単位)。</span><span class="sxs-lookup"><span data-stu-id="2758f-266">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="2758f-267">円弧の角度を 180 度以上にする場合は 1 に設定します。それ以外の場合は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-267">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="2758f-268">円弧が正の角度の方向に描画される場合は 1 に設定します。それ以外の場合は 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="2758f-268">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-269">円弧が描画される点。</span><span class="sxs-lookup"><span data-stu-id="2758f-269">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a><span data-ttu-id="2758f-270">閉じるコマンド</span><span class="sxs-lookup"><span data-stu-id="2758f-270">The Close Command</span></span>  
 <span data-ttu-id="2758f-271">現在の図形を終了し、現在の点と図の開始点を結ぶ線を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-271">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="2758f-272">このコマンドは、図形の最初のセグメントと最後のセグメントの間に線結合 (コーナー) を作成します。</span><span class="sxs-lookup"><span data-stu-id="2758f-272">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="2758f-273">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-273">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="2758f-274">または</span><span class="sxs-lookup"><span data-stu-id="2758f-274">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>   
## <a name="point-syntax"></a><span data-ttu-id="2758f-275">点の構文</span><span class="sxs-lookup"><span data-stu-id="2758f-275">Point Syntax</span></span>  
 <span data-ttu-id="2758f-276">ポイントの x 座標と y 座標をについて説明します。 位置 (0, 0) が左上隅。</span><span class="sxs-lookup"><span data-stu-id="2758f-276">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="2758f-277">構文</span><span class="sxs-lookup"><span data-stu-id="2758f-277">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="2758f-278">`x` `,` `y`</span><span class="sxs-lookup"><span data-stu-id="2758f-278">`x` `,` `y`</span></span><br /><br /> <span data-ttu-id="2758f-279">または</span><span class="sxs-lookup"><span data-stu-id="2758f-279">- or -</span></span><br /><br /> <span data-ttu-id="2758f-280">`x` `y`</span><span class="sxs-lookup"><span data-stu-id="2758f-280">`x` `y`</span></span>|  
  
|<span data-ttu-id="2758f-281">用語</span><span class="sxs-lookup"><span data-stu-id="2758f-281">Term</span></span>|<span data-ttu-id="2758f-282">説明</span><span class="sxs-lookup"><span data-stu-id="2758f-282">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-283">点の x 座標。</span><span class="sxs-lookup"><span data-stu-id="2758f-283">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="2758f-284">点の y 座標。</span><span class="sxs-lookup"><span data-stu-id="2758f-284">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a><span data-ttu-id="2758f-285">特殊な値</span><span class="sxs-lookup"><span data-stu-id="2758f-285">Special Values</span></span>  
 <span data-ttu-id="2758f-286">標準的な数値ではなく、次の特殊な値を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2758f-286">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="2758f-287">これらの値では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2758f-287">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="2758f-288">Infinity</span><span class="sxs-lookup"><span data-stu-id="2758f-288">Infinity</span></span>  
 <span data-ttu-id="2758f-289">表す<xref:System.Double.PositiveInfinity?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-289">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2758f-290">-Infinity</span><span class="sxs-lookup"><span data-stu-id="2758f-290">-Infinity</span></span>  
 <span data-ttu-id="2758f-291">表す<xref:System.Double.NegativeInfinity?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-291">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2758f-292">NaN</span><span class="sxs-lookup"><span data-stu-id="2758f-292">NaN</span></span>  
 <span data-ttu-id="2758f-293">表す<xref:System.Double.NaN?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="2758f-293">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2758f-294">指数表記を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2758f-294">You may also use scientific notation.</span></span> <span data-ttu-id="2758f-295">たとえば、`+1.e17`有効な値です。</span><span class="sxs-lookup"><span data-stu-id="2758f-295">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2758f-296">関連項目</span><span class="sxs-lookup"><span data-stu-id="2758f-296">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [<span data-ttu-id="2758f-297">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="2758f-297">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="2758f-298">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="2758f-298">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="2758f-299">方法トピック</span><span class="sxs-lookup"><span data-stu-id="2758f-299">How-to Topics</span></span>](geometries-how-to-topics.md)
