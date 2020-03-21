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
ms.openlocfilehash: 32e8ab7104b8ea2f985395065868ed154ca1e378
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181961"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a><span data-ttu-id="06508-102">GlyphRun オブジェクトと Glyphs 要素の概要</span><span class="sxs-lookup"><span data-stu-id="06508-102">Introduction to the GlyphRun Object and Glyphs Element</span></span>
<span data-ttu-id="06508-103">このトピックでは、<xref:System.Windows.Media.GlyphRun>オブジェクトと要素について<xref:System.Windows.Documents.Glyphs>説明します。</span><span class="sxs-lookup"><span data-stu-id="06508-103">This topic describes the <xref:System.Windows.Media.GlyphRun> object and the <xref:System.Windows.Documents.Glyphs> element.</span></span>  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a><span data-ttu-id="06508-104">GlyphRun の概要</span><span class="sxs-lookup"><span data-stu-id="06508-104">Introduction to GlyphRun</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="06508-105">書式設定後にテキストをインターセプトして永続化する顧客に直接アクセス<xref:System.Windows.Documents.Glyphs>できるグリフ レベルのマークアップを含む高度なテキスト サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="06508-105">provides advanced text support including glyph-level markup with direct access to <xref:System.Windows.Documents.Glyphs> for customers who want to intercept and persist text after formatting.</span></span> <span data-ttu-id="06508-106">これらの機能は、下記のようなシナリオでのさまざまなテキスト レンダリング要件をサポートする不可欠なものです。</span><span class="sxs-lookup"><span data-stu-id="06508-106">These features provide critical support for the different text rendering requirements in each of the following scenarios.</span></span>  
  
1. <span data-ttu-id="06508-107">固定形式のドキュメントの画面表示。</span><span class="sxs-lookup"><span data-stu-id="06508-107">Screen display of fixed-format documents.</span></span>  
  
2. <span data-ttu-id="06508-108">印刷シナリオ。</span><span class="sxs-lookup"><span data-stu-id="06508-108">Print scenarios.</span></span>  
  
    - <span data-ttu-id="06508-109">デバイス プリンター言語としての [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="06508-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] as a device printer language.</span></span>  
  
    - <span data-ttu-id="06508-110">マイクロソフト XPS ドキュメント ライター。</span><span class="sxs-lookup"><span data-stu-id="06508-110">Microsoft XPS Document Writer.</span></span>  
  
    - <span data-ttu-id="06508-111">以前のプリンター ドライバー、Win32 アプリケーションから固定形式に出力します。</span><span class="sxs-lookup"><span data-stu-id="06508-111">Previous printer drivers, output from Win32 applications to the fixed format.</span></span>  
  
    - <span data-ttu-id="06508-112">印刷スプール形式。</span><span class="sxs-lookup"><span data-stu-id="06508-112">Print spool format.</span></span>  
  
3. <span data-ttu-id="06508-113">以前のバージョンの Windows やその他のコンピューティング デバイス用のクライアントを含む、固定形式のドキュメント表現。</span><span class="sxs-lookup"><span data-stu-id="06508-113">Fixed-format document representation, including clients for previous versions of Windows and other computing devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06508-114"><xref:System.Windows.Documents.Glyphs>固定<xref:System.Windows.Media.GlyphRun>形式のドキュメントプレゼンテーションおよび印刷シナリオ用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="06508-114"><xref:System.Windows.Documents.Glyphs> and <xref:System.Windows.Media.GlyphRun> are designed for fixed-format document presentation and print scenarios.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="06508-115">には、一般的なレイアウトや[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]シナリオなど<xref:System.Windows.Controls.Label>、いくつかの<xref:System.Windows.Controls.TextBlock>要素が用意されています。</span><span class="sxs-lookup"><span data-stu-id="06508-115">provides several elements for general layout and [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] scenarios such as <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="06508-116">レイアウトと[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]シナリオの詳細については、 WPF の[文字体裁](typography-in-wpf.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06508-116">For more information on layout and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios, see the [Typography in WPF](typography-in-wpf.md).</span></span>  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a><span data-ttu-id="06508-117">GlyphRun オブジェクト</span><span class="sxs-lookup"><span data-stu-id="06508-117">The GlyphRun Object</span></span>  
 <span data-ttu-id="06508-118">オブジェクト<xref:System.Windows.Media.GlyphRun>は、単一のフォントの単一の面から単一のサイズで、単一のレンダリング スタイルでのグリフのシーケンスを表します。</span><span class="sxs-lookup"><span data-stu-id="06508-118">The <xref:System.Windows.Media.GlyphRun> object represents a sequence of glyphs from a single face of a single font at a single size, and with a single rendering style.</span></span>  
  
 <span data-ttu-id="06508-119"><xref:System.Windows.Media.GlyphRun>には、グリフや個々のグリフ<xref:System.Windows.Documents.Glyphs.Indices%2A>の位置などのフォントの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="06508-119"><xref:System.Windows.Media.GlyphRun> includes both font details such as glyph <xref:System.Windows.Documents.Glyphs.Indices%2A> and individual glyph positions.</span></span> <span data-ttu-id="06508-120">また、実行元の Unicode コード ポイント、文字からグリフへのバッファー オフセット マッピング情報、および文字単位およびグリフごとのフラグも含まれます。</span><span class="sxs-lookup"><span data-stu-id="06508-120">It also includes the original Unicode code points the run was generated from, character-to-glyph buffer offset mapping information, and per-character and per-glyph flags.</span></span>  
  
 <span data-ttu-id="06508-121"><xref:System.Windows.Media.GlyphRun>には、対応する高レベル<xref:System.Windows.FrameworkElement> <xref:System.Windows.Documents.Glyphs>、 を持ちます。</span><span class="sxs-lookup"><span data-stu-id="06508-121"><xref:System.Windows.Media.GlyphRun> has a corresponding high-level <xref:System.Windows.FrameworkElement>, <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="06508-122"><xref:System.Windows.Documents.Glyphs>は、要素ツリーおよびマークアップで[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]出力を表すために<xref:System.Windows.Media.GlyphRun>使用できます。</span><span class="sxs-lookup"><span data-stu-id="06508-122"><xref:System.Windows.Documents.Glyphs> can be used in the element tree and in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup to represent <xref:System.Windows.Media.GlyphRun> output.</span></span>  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a><span data-ttu-id="06508-123">Glyphs 要素</span><span class="sxs-lookup"><span data-stu-id="06508-123">The Glyphs Element</span></span>  
 <span data-ttu-id="06508-124">要素<xref:System.Windows.Documents.Glyphs>は、 の出力を<xref:System.Windows.Media.GlyphRun>表[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="06508-124">The <xref:System.Windows.Documents.Glyphs> element represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="06508-125">要素を記述するために、次のマークアップ構文<xref:System.Windows.Documents.Glyphs>を使用します。</span><span class="sxs-lookup"><span data-stu-id="06508-125">The following markup syntax is used to describe the <xref:System.Windows.Documents.Glyphs> element.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="06508-126">次のプロパティの定義は、サンプルのマークアップ内の最初の 4 つの属性に対応しています。</span><span class="sxs-lookup"><span data-stu-id="06508-126">The following property definitions correspond to the first four attributes in the sample markup.</span></span>  
  
|<span data-ttu-id="06508-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="06508-127">Property</span></span>|<span data-ttu-id="06508-128">説明</span><span class="sxs-lookup"><span data-stu-id="06508-128">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|<span data-ttu-id="06508-129">リソース識別子 (ファイル名、Web ユニフォーム リソース識別子 (URI)、またはアプリケーション .exe またはコンテナー内のリソース参照を指定します。</span><span class="sxs-lookup"><span data-stu-id="06508-129">Specifies a resource identifier: file name, Web uniform resource identifier (URI), or resource reference in the application .exe or container.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|<span data-ttu-id="06508-130">フォント サイズを描画サーフェイスの単位で指定します (既定値は .96 インチ)。</span><span class="sxs-lookup"><span data-stu-id="06508-130">Specifies the font size in drawing surface units (default is .96 inches).</span></span>|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|<span data-ttu-id="06508-131">太字や斜体のスタイルのフラグを指定します。</span><span class="sxs-lookup"><span data-stu-id="06508-131">Specifies flags for bold and Italic styles.</span></span>|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|<span data-ttu-id="06508-132">双方向のレイアウト レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="06508-132">Specifies the bidirectional layout level.</span></span> <span data-ttu-id="06508-133">偶数とゼロの値は左から右のレイアウトを意味し、奇数の値は右から左のレイアウトを意味します。</span><span class="sxs-lookup"><span data-stu-id="06508-133">Even-numbered and zero values imply left-to-right layout; odd-numbered values imply right-to-left layout.</span></span>|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a><span data-ttu-id="06508-134">Indices プロパティ</span><span class="sxs-lookup"><span data-stu-id="06508-134">Indices property</span></span>  
 <span data-ttu-id="06508-135">プロパティ<xref:System.Windows.Documents.Glyphs.Indices%2A>はグリフの指定の文字列です。</span><span class="sxs-lookup"><span data-stu-id="06508-135">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property is a string of glyph specifications.</span></span> <span data-ttu-id="06508-136">グリフのシーケンスが 1 つのクラスターを形成している場合、クラスター内の最初のグリフの仕様は、クラスターを形成するために組み合わせるグリフの数とコード ポイントの数の仕様によって先行されます。</span><span class="sxs-lookup"><span data-stu-id="06508-136">Where a sequence of glyphs forms a single cluster, the specification of the first glyph in the cluster is preceded by a specification of how many glyphs and how many code points combine to form the cluster.</span></span> <span data-ttu-id="06508-137">プロパティ<xref:System.Windows.Documents.Glyphs.Indices%2A>は、次のプロパティを 1 つの文字列で収集します。</span><span class="sxs-lookup"><span data-stu-id="06508-137">The <xref:System.Windows.Documents.Glyphs.Indices%2A> property collects in one string the following properties.</span></span>  
  
- <span data-ttu-id="06508-138">グリフ インデックス</span><span class="sxs-lookup"><span data-stu-id="06508-138">Glyph indices</span></span>  
  
- <span data-ttu-id="06508-139">グリフアドバンス幅</span><span class="sxs-lookup"><span data-stu-id="06508-139">Glyph advance widths</span></span>  
  
- <span data-ttu-id="06508-140">グリフの結合ベクトルの結合</span><span class="sxs-lookup"><span data-stu-id="06508-140">Combining glyph attachment vectors</span></span>  
  
- <span data-ttu-id="06508-141">コード ポイントからグリフへのクラスタ マッピング</span><span class="sxs-lookup"><span data-stu-id="06508-141">Cluster mapping from code points to glyphs</span></span>  
  
- <span data-ttu-id="06508-142">グリフフラグ</span><span class="sxs-lookup"><span data-stu-id="06508-142">Glyph flags</span></span>  
  
 <span data-ttu-id="06508-143">各グリフの仕様には、次の形式があります。</span><span class="sxs-lookup"><span data-stu-id="06508-143">Each glyph specification has the following form.</span></span>  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a><span data-ttu-id="06508-144">グリフのメトリック</span><span class="sxs-lookup"><span data-stu-id="06508-144">Glyph Metrics</span></span>  
 <span data-ttu-id="06508-145">各グリフは、他<xref:System.Windows.Documents.Glyphs>の グリフとの位置合わせ方法を指定するメトリックを定義します。</span><span class="sxs-lookup"><span data-stu-id="06508-145">Each glyph defines metrics that specify how it aligns with other <xref:System.Windows.Documents.Glyphs>.</span></span> <span data-ttu-id="06508-146">次の図では、2 つの異なるグリフ文字のさまざまな印刷用品質を定義しています。</span><span class="sxs-lookup"><span data-stu-id="06508-146">The following graphic defines the various typographic qualities of two different glyph characters.</span></span>  
  
 <span data-ttu-id="06508-147">![グリフ単位のダイアグラム](./media/glyph-example.png "glyph_example")</span><span class="sxs-lookup"><span data-stu-id="06508-147">![Diagraph of glyph measurements](./media/glyph-example.png "glyph_example")</span></span>  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a><span data-ttu-id="06508-148">グリフ マークアップ</span><span class="sxs-lookup"><span data-stu-id="06508-148">Glyphs Markup</span></span>  
 <span data-ttu-id="06508-149">次のコード例は、 で<xref:System.Windows.Documents.Glyphs>[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]要素のさまざまなプロパティを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="06508-149">The following code example shows how to use various properties of the <xref:System.Windows.Documents.Glyphs> element in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="06508-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="06508-150">See also</span></span>

- [<span data-ttu-id="06508-151">WPF のタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="06508-151">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="06508-152">WPF のドキュメント</span><span class="sxs-lookup"><span data-stu-id="06508-152">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="06508-153">テキスト</span><span class="sxs-lookup"><span data-stu-id="06508-153">Text</span></span>](optimizing-performance-text.md)
