---
title: 自動レイアウトの使用の概要
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: af564c4ca865c47c7efdda6ed86732581f677218
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353596"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="fcef8-102">自動レイアウトの使用の概要</span><span class="sxs-lookup"><span data-stu-id="fcef8-102">Use Automatic Layout Overview</span></span>
<span data-ttu-id="fcef8-103">このトピックで作成する方法に関する開発者向けのガイドラインは[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]ローカライズ可能なアプリケーション[!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span></span> <span data-ttu-id="fcef8-104">以前は、UI のローカライズは時間のかかるプロセスでした。</span><span class="sxs-lookup"><span data-stu-id="fcef8-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="fcef8-105">各言語 UI が変更するには、ピクセル単位で調整が必要です。</span><span class="sxs-lookup"><span data-stu-id="fcef8-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="fcef8-106">今日は、適切な設計とコーディング標準、[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]ローカライザーがあるサイズ変更や、実行する位置を変更できるように構築できます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-106">Today with the right design and right coding standards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="fcef8-107">簡単にサイズ変更や位置が変更された可能性のあるアプリケーションを作成する方法は、自動レイアウトをという名前を使用して実現できます[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]アプリケーションの設計。</span><span class="sxs-lookup"><span data-stu-id="fcef8-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>  

<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="fcef8-108">自動レイアウトを使用する利点</span><span class="sxs-lookup"><span data-stu-id="fcef8-108">Advantages of Using Automatic Layout</span></span>  
 <span data-ttu-id="fcef8-109">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]プレゼンテーション システムは強力で柔軟なさまざまな言語の要件に合わせて調整できるアプリケーションの要素をレイアウトする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="fcef8-110">次の一覧は、自動レイアウトの利点の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="fcef8-110">The following list points out some of the advantages of automatic layout.</span></span>  

-   <span data-ttu-id="fcef8-111">任意の言語で UI を表示します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-111">UI displays well  in any language.</span></span>  

-   <span data-ttu-id="fcef8-112">テキストの翻訳後のコントロールの位置とサイズを再調整する必要性が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>  
  
-   <span data-ttu-id="fcef8-113">ウィンドウのサイズを再調整する必要性を軽減します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-113">Reduces the need to readjust window size.</span></span>  

-   <span data-ttu-id="fcef8-114">UI のレイアウトは、任意の言語で正しく表示します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-114">UI layout renders properly in any language.</span></span>  

-   <span data-ttu-id="fcef8-115">ローカリゼーションは、文字列の翻訳より若干高であるポイントに削減できます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-115">Localization can be reduced to the point that it is little more than string translation.</span></span>  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a><span data-ttu-id="fcef8-116">自動レイアウトとコントロール</span><span class="sxs-lookup"><span data-stu-id="fcef8-116">Automatic Layout and Controls</span></span>  
 <span data-ttu-id="fcef8-117">自動レイアウトには、コントロールのサイズを自動的に調整するアプリケーションができるようにします。</span><span class="sxs-lookup"><span data-stu-id="fcef8-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="fcef8-118">たとえば、文字列の長さに合わせてコントロールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="fcef8-119">この機能により、ローカライザーに文字列を変換するには不要になった、翻訳されたテキストに合わせてコントロールのサイズを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcef8-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="fcef8-120">次の例では、英語コンテンツをボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-120">The following example creates a button with English content.</span></span>  
  
 [!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="fcef8-121">例をスペイン語のボタンのために実行する必要がある、テキストを変更します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="fcef8-122">例えば以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="fcef8-122">For example,</span></span>  
  
 [!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="fcef8-123">次の図は、コード サンプルの出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="fcef8-123">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="fcef8-124">![テキストの言語が異なる同じボタン](./media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="fcef8-124">![The same button with text in different languages](./media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="fcef8-125">自動サイズ変更可能なボタン</span><span class="sxs-lookup"><span data-stu-id="fcef8-125">Auto Resizable Button</span></span>  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="fcef8-126">自動レイアウトとコーディング標準</span><span class="sxs-lookup"><span data-stu-id="fcef8-126">Automatic Layout and Coding Standards</span></span>  
 <span data-ttu-id="fcef8-127">自動レイアウトのアプローチを使用するには、一連のコーディングし設計標準と完全にローカライズ可能な UI を生成するために規則が必要です。</span><span class="sxs-lookup"><span data-stu-id="fcef8-127">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="fcef8-128">次のガイドライン、自動レイアウトのコーディングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="fcef8-128">The following guidelines will aid your automatic layout coding.</span></span>  

<span data-ttu-id="fcef8-129">**絶対位置を使用しないでください。**</span><span class="sxs-lookup"><span data-stu-id="fcef8-129">**Do not use absolute positions**</span></span>

- <span data-ttu-id="fcef8-130">使用しない<xref:System.Windows.Controls.Canvas>のため、絶対に要素を配置します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-130">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="fcef8-131">使用<xref:System.Windows.Controls.DockPanel>、 <xref:System.Windows.Controls.StackPanel>、および<xref:System.Windows.Controls.Grid>コントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-131">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="fcef8-132">パネルのさまざまな種類の詳細については、次を参照してください。[パネルの概要](../controls/panels-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-132">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="fcef8-133">**ウィンドウの固定サイズを設定しないでください。**</span><span class="sxs-lookup"><span data-stu-id="fcef8-133">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="fcef8-134"><xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fcef8-134">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fcef8-135">例:</span><span class="sxs-lookup"><span data-stu-id="fcef8-135">For example:</span></span>

   [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="fcef8-136">**追加します。 <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="fcef8-136">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="fcef8-137">追加、<xref:System.Windows.FrameworkElement.FlowDirection%2A>アプリケーションのルート要素にします。</span><span class="sxs-lookup"><span data-stu-id="fcef8-137">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

   <span data-ttu-id="fcef8-138">WPF には、水平方向をサポートする便利な方法、双方向、および垂直方向のレイアウトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fcef8-138">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="fcef8-139">プレゼンテーションのフレームワークで、<xref:System.Windows.FrameworkElement.FlowDirection%2A>レイアウトを定義するプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-139">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="fcef8-140">フロー方向パターンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fcef8-140">The flow-direction patterns are:</span></span>
   
     - <span data-ttu-id="fcef8-141"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb)-ラテン語や東アジア言語などのための横書きレイアウト。</span><span class="sxs-lookup"><span data-stu-id="fcef8-141"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>
     
     - <span data-ttu-id="fcef8-142"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb)-アラビア語やヘブライ語などの双方向。</span><span class="sxs-lookup"><span data-stu-id="fcef8-142"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="fcef8-143">**物理フォントではなく複合フォントを使用します。**</span><span class="sxs-lookup"><span data-stu-id="fcef8-143">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="fcef8-144">複合のフォントを含む、<xref:System.Windows.Controls.Control.FontFamily%2A>プロパティはローカライズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fcef8-144">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="fcef8-145">開発者では、次のフォントのいずれかを使用したり、独自に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-145">Developers can use one of the following fonts or create their own.</span></span>

   - <span data-ttu-id="fcef8-146">グローバル ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fcef8-146">Global User Interface</span></span>
   - <span data-ttu-id="fcef8-147">グローバル San Serif</span><span class="sxs-lookup"><span data-stu-id="fcef8-147">Global San Serif</span></span>
   - <span data-ttu-id="fcef8-148">グローバル Serif</span><span class="sxs-lookup"><span data-stu-id="fcef8-148">Global Serif</span></span>

<span data-ttu-id="fcef8-149">**Xml:lang を追加します。**</span><span class="sxs-lookup"><span data-stu-id="fcef8-149">**Add xml:lang**</span></span>

- <span data-ttu-id="fcef8-150">追加、`xml:lang`など、UI のルート要素に属性`xml:lang="en-US"`英語版のアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="fcef8-150">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="fcef8-151">複合フォントを使用しているため`xml:lang`を使用するフォントを確認するには、多言語シナリオをサポートするには、このプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-151">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a><span data-ttu-id="fcef8-152">自動レイアウトとグリッド</span><span class="sxs-lookup"><span data-stu-id="fcef8-152">Automatic Layout and Grids</span></span>  
 <span data-ttu-id="fcef8-153"><xref:System.Windows.Controls.Grid>要素は、開発者が要素を配置するため、自動レイアウト用に便利です。</span><span class="sxs-lookup"><span data-stu-id="fcef8-153">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="fcef8-154">A<xref:System.Windows.Controls.Grid>コントロールの列と行の並べ替え方法を使用して、その子要素間で使用可能な領域を配布します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-154">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="fcef8-155">UI 要素が複数のセルにまたがることができます、グリッド内にグリッドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-155">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="fcef8-156">グリッドを作成し、複雑な UI を配置することができるため便利です。</span><span class="sxs-lookup"><span data-stu-id="fcef8-156">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="fcef8-157">次の例では、グリッドを使用したいくつかのボタンとテキストの位置を示します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-157">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="fcef8-158">セルの幅と高さに設定されている通知<xref:System.Windows.GridUnitType.Auto>。 したがって、イメージ付きのボタンを含むセルを画像に合わせて調整します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-158">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>  

 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="fcef8-159">次の図は、前のコードによって生成されるグリッドを示します。</span><span class="sxs-lookup"><span data-stu-id="fcef8-159">The following graphic shows the grid produced by the previous code.</span></span>  
  
 <span data-ttu-id="fcef8-160">![グリッドの例](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="fcef8-160">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="fcef8-161">グリッド</span><span class="sxs-lookup"><span data-stu-id="fcef8-161">Grid</span></span>  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="fcef8-162">自動レイアウトと IsSharedSizeScope プロパティを使用してグリッド</span><span class="sxs-lookup"><span data-stu-id="fcef8-162">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>  
 <span data-ttu-id="fcef8-163">A<xref:System.Windows.Controls.Grid>要素がコンテンツに合わせて調整されるコントロールを作成する、ローカライズ可能なアプリケーションで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="fcef8-163">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="fcef8-164">ただし、たい場コンテンツに関係なく特定のサイズを維持するコントロール。</span><span class="sxs-lookup"><span data-stu-id="fcef8-164">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="fcef8-165">たとえば、"OK"があれば、「キャンセル」と「参照」おそらくたくないボタンのサイズをコンテンツに合わせてボタン。</span><span class="sxs-lookup"><span data-stu-id="fcef8-165">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="fcef8-166">この場合、<xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType>添付プロパティは複数の grid 要素間で同じサイズの変更を共有するために便利です。</span><span class="sxs-lookup"><span data-stu-id="fcef8-166">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="fcef8-167">次の例は、列と行の複数の間でデータをサイズ変更を共有する方法を示します<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="fcef8-167">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="fcef8-168">**注**完全なコード サンプルでは、次を参照してください[共有サイズ設定プロパティの間でグリッド。](../controls/how-to-share-sizing-properties-between-grids.md)</span><span class="sxs-lookup"><span data-stu-id="fcef8-168">**Note** For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcef8-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcef8-169">See also</span></span>
- [<span data-ttu-id="fcef8-170">WPF のグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="fcef8-170">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="fcef8-171">自動レイアウトを使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="fcef8-171">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="fcef8-172">自動レイアウト用のグリッドを使用する</span><span class="sxs-lookup"><span data-stu-id="fcef8-172">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
