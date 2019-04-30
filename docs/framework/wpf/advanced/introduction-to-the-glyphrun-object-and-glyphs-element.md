---
title: GlyphRun オブジェクトと Glyphs 要素の概要
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 0e5ec2b89f015c7e061b59fea755eb368f1ac7a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031305"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="b9078-102">GlyphRun オブジェクトと Glyphs 要素の概要</span><span class="sxs-lookup"><span data-stu-id="b9078-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="b9078-103">このトピックで説明します、<xref:System.Windows.Media.GlyphRun>オブジェクトと<xref:System.Windows.Documents.Glyphs>要素。</span><span class="sxs-lookup"><span data-stu-id="b9078-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>   
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="b9078-104">GlyphRun の概要</span><span class="sxs-lookup"><span data-stu-id="b9078-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="b9078-105">直接アクセスによるグリフ レベルのマークアップなどの高度なテキスト サポートを提供します<xref:System.Windows.Documents.Glyphs>を使用し、書式設定後のテキストの保持を希望するお客様向けです。</span><span class="sxs-lookup"><span data-stu-id="b9078-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="b9078-106">これらの機能は、下記のようなシナリオでのさまざまなテキスト レンダリング要件をサポートする不可欠なものです。</span><span class="sxs-lookup"><span data-stu-id="b9078-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="b9078-107">固定形式のドキュメントの画面表示。</span><span class="sxs-lookup"><span data-stu-id="b9078-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="b9078-108">印刷シナリオ。</span><span class="sxs-lookup"><span data-stu-id="b9078-108">Print scenarios.</span></span>  
  
    - <span data-ttu-id="b9078-109">デバイス プリンター言語としての [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b9078-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] as a device printer language.</span></span>  
  
    - [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]<span data-ttu-id="b9078-110">。</span><span class="sxs-lookup"><span data-stu-id="b9078-110">.</span></span>  
  
    - <span data-ttu-id="b9078-111">以前のプリンター ドライバー、[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]アプリケーションから固定形式への出力。</span><span class="sxs-lookup"><span data-stu-id="b9078-111">Previous printer drivers, output from [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="b9078-112">印刷スプール形式。</span><span class="sxs-lookup"><span data-stu-id="b9078-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="b9078-113">以前のバージョンの [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] のクライアントおよびその他のコンピューティング デバイスを含む、固定形式のドキュメント表示。</span><span class="sxs-lookup"><span data-stu-id="b9078-113">Fixed-format document representation, including clients for previous versions of [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] and other computing devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9078-114"><xref:System.Windows.Documents.Glyphs> <xref:System.Windows.Media.GlyphRun>固定形式のドキュメント プレゼンテーションと印刷シナリオ向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="b9078-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="b9078-115">いくつかの要素は、一般的なレイアウトと[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]などのシナリオ<xref:System.Windows.Controls.Label>と<xref:System.Windows.Controls.TextBlock>します。</span><span class="sxs-lookup"><span data-stu-id="b9078-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="b9078-116">レイアウトと [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] シナリオの詳細については、[WPF のタイポグラフィ](typography-in-wpf.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9078-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>   
## <a name="the-glyphrun-object"></a><span data-ttu-id="b9078-117">GlyphRun オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b9078-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="b9078-118"><xref:System.Windows.Media.GlyphRun>オブジェクトは、1 つのサイズおよび 1 つのレンダリング スタイルを使用した 1 つのフォントの書体からグリフのシーケンスを表します。</span><span class="sxs-lookup"><span data-stu-id="b9078-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="b9078-119"><xref:System.Windows.Media.GlyphRun> グリフなど両方のフォントの詳細が含まれています<xref:System.Windows.Documents.Glyphs.Indices%2A>と個々 のグリフ位置。</span><span class="sxs-lookup"><span data-stu-id="b9078-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="b9078-120">元も含まれています。[!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)]コード ポイントの文字とグリフのバッファー オフセット マッピングの情報、および文字とグリフのフラグから生成された実行します。</span><span class="sxs-lookup"><span data-stu-id="b9078-120">It also includes the original [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="b9078-121"><xref:System.Windows.Media.GlyphRun> 高度な対応しています<xref:System.Windows.FrameworkElement>、<xref:System.Windows.Documents.Glyphs>します。</span><span class="sxs-lookup"><span data-stu-id="b9078-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="b9078-122"><xref:System.Windows.Documents.Glyphs> 要素ツリーとで使用できる[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を表すマークアップ<xref:System.Windows.Media.GlyphRun>出力します。</span><span class="sxs-lookup"><span data-stu-id="b9078-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>   
## <a name="the-glyphs-element"></a><span data-ttu-id="b9078-123">Glyphs 要素</span><span class="sxs-lookup"><span data-stu-id="b9078-123">The Glyphs Element</span></span>  
 <span data-ttu-id="b9078-124"><xref:System.Windows.Documents.Glyphs>要素の出力を表して、<xref:System.Windows.Media.GlyphRun>で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b9078-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="b9078-125">次のマークアップ構文が記述に使用される、<xref:System.Windows.Documents.Glyphs>要素。</span><span class="sxs-lookup"><span data-stu-id="b9078-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="b9078-126">次のプロパティの定義は、サンプルのマークアップ内の最初の 4 つの属性に対応しています。</span><span class="sxs-lookup"><span data-stu-id="b9078-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="b9078-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9078-127">Property</span></span>|<span data-ttu-id="b9078-128">説明</span><span class="sxs-lookup"><span data-stu-id="b9078-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="b9078-129">リソース識別子を指定します。 ファイル名を Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]、またはアプリケーションの .exe またはコンテナー リソースの参照。</span><span class="sxs-lookup"><span data-stu-id="b9078-129">Specifies a resource identifier: file name, Web [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="b9078-130">フォント サイズを描画サーフェイスの単位で指定します (既定値は .96 インチ)。</span><span class="sxs-lookup"><span data-stu-id="b9078-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="b9078-131">太字や斜体のスタイルのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9078-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="b9078-132">双方向のレイアウト レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9078-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="b9078-133">偶数とゼロの値は左から右のレイアウトを意味し、奇数の値は右から左のレイアウトを意味します。</span><span class="sxs-lookup"><span data-stu-id="b9078-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>   
### <a name="indices-property"></a><span data-ttu-id="b9078-134">Indices プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9078-134">Indices property</span></span>  
 <span data-ttu-id="b9078-135"><xref:System.Windows.Documents.Glyphs.Indices%2A>プロパティは、グリフ仕様の文字列。</span><span class="sxs-lookup"><span data-stu-id="b9078-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="b9078-136">グリフのシーケンスが 1 つのクラスターを形成している場合、クラスター内の最初のグリフの仕様は、クラスターを形成するために組み合わせるグリフの数とコード ポイントの数の仕様によって先行されます。</span><span class="sxs-lookup"><span data-stu-id="b9078-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="b9078-137"><xref:System.Windows.Documents.Glyphs.Indices%2A>プロパティが 1 つの文字列で、次のプロパティを収集します。</span><span class="sxs-lookup"><span data-stu-id="b9078-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="b9078-138">グリフ インデックス</span><span class="sxs-lookup"><span data-stu-id="b9078-138">Glyph indices</span></span>  
  
- <span data-ttu-id="b9078-139">グリフのアドバンス幅</span><span class="sxs-lookup"><span data-stu-id="b9078-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="b9078-140">グリフの添付ファイルのベクトルを組み合わせること</span><span class="sxs-lookup"><span data-stu-id="b9078-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="b9078-141">コード ポイントからグリフへのクラスターのマッピング</span><span class="sxs-lookup"><span data-stu-id="b9078-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="b9078-142">グリフのフラグ</span><span class="sxs-lookup"><span data-stu-id="b9078-142">Glyph flags</span></span>  
  
 <span data-ttu-id="b9078-143">各グリフの仕様には、次の形式があります。</span><span class="sxs-lookup"><span data-stu-id="b9078-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>   
## <a name="glyph-metrics"></a><span data-ttu-id="b9078-144">グリフのメトリック</span><span class="sxs-lookup"><span data-stu-id="b9078-144">Glyph Metrics</span></span>  
 <span data-ttu-id="b9078-145">各グリフは、他の配置方法を指定するメトリックを定義します。<xref:System.Windows.Documents.Glyphs>します。</span><span class="sxs-lookup"><span data-stu-id="b9078-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="b9078-146">次の図では、2 つの異なるグリフ文字のさまざまな印刷用品質を定義しています。</span><span class="sxs-lookup"><span data-stu-id="b9078-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="b9078-147">![グリフ単位のダイアグラム](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="b9078-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>   
## <a name="glyphs-markup"></a><span data-ttu-id="b9078-148">グリフ マークアップ</span><span class="sxs-lookup"><span data-stu-id="b9078-148">Glyphs Markup</span></span>  
 <span data-ttu-id="b9078-149">次のコード例のさまざまなプロパティを使用する方法を示しています、<xref:System.Windows.Documents.Glyphs>要素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b9078-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b9078-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9078-150">See also</span></span>

- [<span data-ttu-id="b9078-151">WPF のタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="b9078-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="b9078-152">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="b9078-152">Documents in WPF</span></span>](documents-in-wpf.md)
- <span data-ttu-id="b9078-153">[[テキスト]](optimizing-performance-text.md)</span><span class="sxs-lookup"><span data-stu-id="b9078-153">[Text](optimizing-performance-text.md)</span></span>
