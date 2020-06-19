---
title: グローバリゼーション
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], international user interface
- XAML [WPF], globalization
- international user interface [WPF], XAML
- globalization [WPF]
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
ms.openlocfilehash: 95c0368889dfa4e69b5e40b32ea19ba845aa5c30
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747058"
---
# <a name="globalization-for-wpf"></a><span data-ttu-id="ff11c-102">WPF のグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="ff11c-102">Globalization for WPF</span></span>
<span data-ttu-id="ff11c-103">このトピックでは、グローバル市場向けに [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] アプリケーションを開発するときに注意するべき問題を紹介します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-103">This topic introduces issues that you should be aware of when writing [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications for the global market.</span></span> <span data-ttu-id="ff11c-104">グローバリゼーション プログラミング要素は、.NET の <xref:System.Globalization> 名前空間に定義されています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-104">The globalization programming elements are defined in .NET in the <xref:System.Globalization> namespace.</span></span>

<a name="xaml_globalization"></a>
## <a name="xaml-globalization"></a><span data-ttu-id="ff11c-105">XAML グローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="ff11c-105">XAML Globalization</span></span>
 <span data-ttu-id="ff11c-106">Extensible Application Markup Language (XAML) は XML に基づいており、XML 仕様で定義されているグローバリゼーション サポートが利用されます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-106">Extensible Application Markup Language (XAML) is based on XML and takes advantage of the globalization support defined in the XML specification.</span></span> <span data-ttu-id="ff11c-107">以下のセクションでは、注意するべき [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 機能についていくつか説明します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-107">The following sections describe some [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] features that you should be aware of.</span></span>

<a name="char_reference"></a>
### <a name="character-references"></a><span data-ttu-id="ff11c-108">文字参照</span><span class="sxs-lookup"><span data-stu-id="ff11c-108">Character References</span></span>
<span data-ttu-id="ff11c-109">文字参照は、特定の Unicode 文字の UTF16 コード ユニットを、10 進数または 16 進数で表したものです。</span><span class="sxs-lookup"><span data-stu-id="ff11c-109">A character reference gives the UTF16 code unit of the particular Unicode character it represents, in either decimal or hexadecimal.</span></span> <span data-ttu-id="ff11c-110">次の例は、コプト語の大文字のホリ (つまり 'Ϩ') の 10 進の文字参照を示しています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-110">The following example shows a decimal character reference for the COPTIC CAPITAL LETTER HORI, or 'Ϩ':</span></span>

```
&#1000;
```

<span data-ttu-id="ff11c-111">次は、16 進数の文字参照の例です。</span><span class="sxs-lookup"><span data-stu-id="ff11c-111">The following example shows a hexadecimal character reference.</span></span> <span data-ttu-id="ff11c-112">16 進数の前には **x** が付くことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ff11c-112">Notice that it has an **x** in front of the hexadecimal number.</span></span>

```
&#x3E8;
```

<a name="encoding"></a>
### <a name="encoding"></a><span data-ttu-id="ff11c-113">エンコード</span><span class="sxs-lookup"><span data-stu-id="ff11c-113">Encoding</span></span>
 <span data-ttu-id="ff11c-114">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] でサポートされているエンコードは、ASCII、Unicode UTF-16、および UTF-8 です。</span><span class="sxs-lookup"><span data-stu-id="ff11c-114">The encoding supported by [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] are ASCII, Unicode UTF-16, and UTF-8.</span></span> <span data-ttu-id="ff11c-115">エンコード ステートメントは [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 文書の最初に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-115">The encoding statement is at the beginning of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] document.</span></span> <span data-ttu-id="ff11c-116">エンコーディング属性が存在せず、バイト順もない場合、パーサーでは既定として UTF-8 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-116">If no encoding attribute exists and there is no byte-order, the parser defaults to UTF-8.</span></span> <span data-ttu-id="ff11c-117">UTF-8 と UTF-16 は優先エンコードです。</span><span class="sxs-lookup"><span data-stu-id="ff11c-117">UTF-8 and UTF-16 are the preferred encodings.</span></span> <span data-ttu-id="ff11c-118">UTF-7 には対応していません。</span><span class="sxs-lookup"><span data-stu-id="ff11c-118">UTF-7 is not supported.</span></span> <span data-ttu-id="ff11c-119">次の例は、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルで UTF-8 エンコードを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-119">The following example demonstrates how to specify a UTF-8 encoding in a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span>

```xaml
?xml encoding="UTF-8"?
```

<a name="lang_attrib"></a>
### <a name="language-attribute"></a><span data-ttu-id="ff11c-120">言語属性</span><span class="sxs-lookup"><span data-stu-id="ff11c-120">Language Attribute</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="ff11c-121">は [xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) を利用し、要素の言語属性を表します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-121">uses [xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) to represent the language attribute of an element.</span></span>  <span data-ttu-id="ff11c-122"><xref:System.Globalization.CultureInfo> クラスを利用するには、言語属性値が <xref:System.Globalization.CultureInfo> で事前定義されたカルチャ名のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-122">To take advantage of the <xref:System.Globalization.CultureInfo> class, the language attribute value needs to be one of the culture names predefined by <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="ff11c-123">[xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) は要素ツリーで継承可能であり (XML ルールによる継承であり、必ずしも依存関係プロパティの継承によるものではありません)、その既定値は、明示的に割り当てられていない場合、空の文字列になります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-123">[xml:lang](../../../desktop-wpf/xaml-services/xml-language-handling.md) is inheritable in the element tree (by XML rules, not necessarily because of dependency property inheritance) and its default value is an empty string if it is not assigned explicitly.</span></span>

 <span data-ttu-id="ff11c-124">言語属性は、方言を指定するときに非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-124">The language attribute is very useful for specifying dialects.</span></span> <span data-ttu-id="ff11c-125">たとえば、フランス語であれば、フランス、ケベック、ベルギー、スイスでスペル、語彙、発音が異なります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-125">For example, French has different spelling, vocabulary, and pronunciation in France, Quebec, Belgium, and Switzerland.</span></span> <span data-ttu-id="ff11c-126">また、中国語、日本語、韓国語は Unicode のコード ポイントを共有していますが、表意文字の形が異なり、まったく別のフォントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-126">Also Chinese, Japanese, and Korean share code points in Unicode, but the ideographic shapes are different and they use totally different fonts.</span></span>

 <span data-ttu-id="ff11c-127">次の [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 例では、`fr-CA` 言語属性を利用し、カナダのフランス語を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-127">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example uses the `fr-CA` language attribute to specify Canadian French.</span></span>

```xaml
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>
```

<a name="unicode"></a>
### <a name="unicode"></a><span data-ttu-id="ff11c-128">Unicode</span><span class="sxs-lookup"><span data-stu-id="ff11c-128">Unicode</span></span>
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="ff11c-129">は、サロゲートを含むすべての Unicode 機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-129">supports all Unicode features including surrogates.</span></span> <span data-ttu-id="ff11c-130">文字セットを Unicode にマッピングできるのであればサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-130">As long as the character set can be mapped to Unicode, it is supported.</span></span> <span data-ttu-id="ff11c-131">たとえば、GB18030 では、一部の文字が中国語、日本語、韓国語 (CFK) の拡張 A および B とサロゲート ペアにマッピングされているため、完全に対応しています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-131">For example, GB18030 introduces some characters that are mapped to the Chinese, Japanese, and Korean (CFK) extension A and B and surrogate pairs, therefore it is fully supported.</span></span> <span data-ttu-id="ff11c-132">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションでは、<xref:System.Globalization.StringInfo> を使用して、サロゲート ペアまたは結合文字があるかどうかを知らなくても文字列を操作できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-132">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can use <xref:System.Globalization.StringInfo> to manipulate strings without understanding whether they have surrogate pairs or combining characters.</span></span>

<a name="design_intl_ui_with_xaml"></a>
## <a name="designing-an-international-user-interface-with-xaml"></a><span data-ttu-id="ff11c-133">XAML で各国対応ユーザー インターフェイスを設計する</span><span class="sxs-lookup"><span data-stu-id="ff11c-133">Designing an International User Interface with XAML</span></span>
 <span data-ttu-id="ff11c-134">このセクションでは、アプリケーションの開発時に考慮するべき [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-134">This section describes [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] features that you should consider when writing an application.</span></span>

<a name="intl_text"></a>
### <a name="international-text"></a><span data-ttu-id="ff11c-135">国際対応テキスト</span><span class="sxs-lookup"><span data-stu-id="ff11c-135">International Text</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ff11c-136">には、Microsoft .NET Framework でサポートされているすべての書記体系の組み込み処理が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-136">includes built-in processing for all Microsoft .NET Framework supported writing systems.</span></span>

 <span data-ttu-id="ff11c-137">現在、次の書体がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-137">The following scripts are currently supported:</span></span>

- <span data-ttu-id="ff11c-138">アラビア語</span><span class="sxs-lookup"><span data-stu-id="ff11c-138">Arabic</span></span>

- <span data-ttu-id="ff11c-139">ベンガル語</span><span class="sxs-lookup"><span data-stu-id="ff11c-139">Bengali</span></span>

- <span data-ttu-id="ff11c-140">デバナガリ</span><span class="sxs-lookup"><span data-stu-id="ff11c-140">Devanagari</span></span>

- <span data-ttu-id="ff11c-141">キリル言語</span><span class="sxs-lookup"><span data-stu-id="ff11c-141">Cyrillic</span></span>

- <span data-ttu-id="ff11c-142">ギリシャ語</span><span class="sxs-lookup"><span data-stu-id="ff11c-142">Greek</span></span>

- <span data-ttu-id="ff11c-143">グジャラート語</span><span class="sxs-lookup"><span data-stu-id="ff11c-143">Gujarati</span></span>

- <span data-ttu-id="ff11c-144">グルムキー</span><span class="sxs-lookup"><span data-stu-id="ff11c-144">Gurmukhi</span></span>

- <span data-ttu-id="ff11c-145">ヘブライ語</span><span class="sxs-lookup"><span data-stu-id="ff11c-145">Hebrew</span></span>

- <span data-ttu-id="ff11c-146">表意文字スクリプト</span><span class="sxs-lookup"><span data-stu-id="ff11c-146">Ideographic scripts</span></span>

- <span data-ttu-id="ff11c-147">カナラ語</span><span class="sxs-lookup"><span data-stu-id="ff11c-147">Kannada</span></span>

- <span data-ttu-id="ff11c-148">ラオス語</span><span class="sxs-lookup"><span data-stu-id="ff11c-148">Lao</span></span>

- <span data-ttu-id="ff11c-149">ラテン語</span><span class="sxs-lookup"><span data-stu-id="ff11c-149">Latin</span></span>

- <span data-ttu-id="ff11c-150">マラヤーラム語</span><span class="sxs-lookup"><span data-stu-id="ff11c-150">Malayalam</span></span>

- <span data-ttu-id="ff11c-151">モンゴル語</span><span class="sxs-lookup"><span data-stu-id="ff11c-151">Mongolian</span></span>

- <span data-ttu-id="ff11c-152">オディア語</span><span class="sxs-lookup"><span data-stu-id="ff11c-152">Odia</span></span>

- <span data-ttu-id="ff11c-153">シリア語</span><span class="sxs-lookup"><span data-stu-id="ff11c-153">Syriac</span></span>

- <span data-ttu-id="ff11c-154">タミール語</span><span class="sxs-lookup"><span data-stu-id="ff11c-154">Tamil</span></span>

- <span data-ttu-id="ff11c-155">テルグ語</span><span class="sxs-lookup"><span data-stu-id="ff11c-155">Telugu</span></span>

- <span data-ttu-id="ff11c-156">ターナ</span><span class="sxs-lookup"><span data-stu-id="ff11c-156">Thaana</span></span>

- <span data-ttu-id="ff11c-157">タイ語\*</span><span class="sxs-lookup"><span data-stu-id="ff11c-157">Thai\*</span></span>

- <span data-ttu-id="ff11c-158">チベット語</span><span class="sxs-lookup"><span data-stu-id="ff11c-158">Tibetan</span></span>

 <span data-ttu-id="ff11c-159">\* このリリースでは、タイ語テキストを表示し、編集できますが、単語を分割することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff11c-159">\*In this release the display and editing of Thai text is supported; word breaking is not.</span></span>

 <span data-ttu-id="ff11c-160">現在、次のスクリプトはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ff11c-160">The following scripts are not currently supported:</span></span>

- <span data-ttu-id="ff11c-161">クメール語</span><span class="sxs-lookup"><span data-stu-id="ff11c-161">Khmer</span></span>

- <span data-ttu-id="ff11c-162">韓国語の古いハングル</span><span class="sxs-lookup"><span data-stu-id="ff11c-162">Korean Old Hangul</span></span>

- <span data-ttu-id="ff11c-163">ミャンマー</span><span class="sxs-lookup"><span data-stu-id="ff11c-163">Myanmar</span></span>

- <span data-ttu-id="ff11c-164">シンハラ語</span><span class="sxs-lookup"><span data-stu-id="ff11c-164">Sinhala</span></span>

 <span data-ttu-id="ff11c-165">すべての書記体系エンジンは OpenType フォントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-165">All the writing system engines support OpenType fonts.</span></span> <span data-ttu-id="ff11c-166">OpenType フォントには、OpenType レイアウト テーブルを追加できます。このテーブルを追加すると、フォントの作成時、洗練された国際対応の印刷フォントの設計能力が上がります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-166">OpenType fonts can include the OpenType layout tables that enable font creators to design better international and high-end typographic fonts.</span></span> <span data-ttu-id="ff11c-167">OpenType フォント レイアウト テーブルには、グリフ代用、グリフ配置、位置揃え、基線配置に関する情報が含まれています。テキスト処理アプリケーションでテキスト レイアウトを改善できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-167">The OpenType font layout tables contain information about glyph substitutions, glyph positioning, justification, and baseline positioning, enabling text-processing applications to improve text layout.</span></span>

 <span data-ttu-id="ff11c-168">OpenType フォントでは、Unicode エンコードを使用して大きなグリフ セットを処理できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-168">OpenType fonts allow the handling of large glyph sets using Unicode encoding.</span></span> <span data-ttu-id="ff11c-169">このようなエンコードにより、広範な国際対応が可能になり、さまざまなグリフを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-169">Such encoding enables broad international support as well as for typographic glyph variants.</span></span>

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ff11c-170">のテキスト レンダリングには、解像度に依存しない Microsoft ClearType サブピクセル テクノロジが採用されています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-170">text rendering is powered by Microsoft ClearType sub-pixel technology that supports resolution independence.</span></span> <span data-ttu-id="ff11c-171">これにより読みやすさが大幅に向上し、あらゆる書体で高品質の雑誌スタイルの書面を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-171">This significantly improves legibility and provides the ability to support high quality magazine style documents for all scripts.</span></span>

<a name="intl_layout"></a>
### <a name="international-layout"></a><span data-ttu-id="ff11c-172">国際対応レイアウト</span><span class="sxs-lookup"><span data-stu-id="ff11c-172">International Layout</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ff11c-173">では非常に便利な方法で横書きレイアウト、双方向レイアウト、縦書きレイアウトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-173">provides a very convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="ff11c-174">プレゼンテーション フレームワークでは、<xref:System.Windows.FrameworkElement.FlowDirection%2A> プロパティを使用してレイアウトを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-174">In presentation framework the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="ff11c-175">フローの方向パターン:</span><span class="sxs-lookup"><span data-stu-id="ff11c-175">The flow direction patterns are:</span></span>

- <span data-ttu-id="ff11c-176">*LeftToRight* - ラテン語や東アジア言語などのための横書きレイアウト。</span><span class="sxs-lookup"><span data-stu-id="ff11c-176">*LeftToRight* - horizontal layout for Latin, East Asian and so forth.</span></span>

- <span data-ttu-id="ff11c-177">*RightToLeft* - アラビア語やヘブライ語などのための双方向レイアウト。</span><span class="sxs-lookup"><span data-stu-id="ff11c-177">*RightToLeft* - bidirectional for Arabic, Hebrew and so forth.</span></span>

<a name="developing_localizable_apps"></a>
## <a name="developing-localizable-applications"></a><span data-ttu-id="ff11c-178">ローカライズ可能なアプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="ff11c-178">Developing Localizable Applications</span></span>
 <span data-ttu-id="ff11c-179">世界中で利用されるアプリケーションを開発するときは、アプリケーションをローカライズ可能にすることを忘れてはなりません。</span><span class="sxs-lookup"><span data-stu-id="ff11c-179">When you write an application for global consumption you should keep in mind that the application must be localizable.</span></span> <span data-ttu-id="ff11c-180">後続のトピックで、考慮事項を指摘します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-180">The following topics point out things to consider.</span></span>

<a name="mui"></a>
### <a name="multilingual-user-interface"></a><span data-ttu-id="ff11c-181">多言語ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff11c-181">Multilingual User Interface</span></span>
 <span data-ttu-id="ff11c-182">多言語ユーザー インターフェイス (MUI) は、UI をある言語から別の言語に切り替えるための Microsoft サポートです。</span><span class="sxs-lookup"><span data-stu-id="ff11c-182">Multilingual User Interfaces (MUI) is a Microsoft support for switching UIs from one language to another.</span></span> <span data-ttu-id="ff11c-183">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションはアセンブリ モデルを利用して MUI をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ff11c-183">A [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses the assembly model to support MUI.</span></span> <span data-ttu-id="ff11c-184">1 つのアプリケーションに言語に依存しないアセンブリと言語に依存するサテライト リソース アセンブリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-184">One application contains language-neutral assemblies as well as language-dependent satellite resource assemblies.</span></span> <span data-ttu-id="ff11c-185">エントリ ポイントはメイン アセンブリのマネージド .EXE です。</span><span class="sxs-lookup"><span data-stu-id="ff11c-185">The entry point is a managed .EXE in the main assembly.</span></span>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ff11c-186">リソース ローダーは、Framework のリソース マネージャーを利用し、リソースのルックアップとフォールバックをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ff11c-186">resource loader takes advantage of the Framework's resource manager to support resource lookup and fallback.</span></span> <span data-ttu-id="ff11c-187">多言語サテライト アセンブリは同じメイン アセンブリと連動します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-187">Multiple language satellite assemblies work with the same main assembly.</span></span> <span data-ttu-id="ff11c-188">読み込まれるリソース アセンブリは、現在のスレッドの <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> によって変わります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-188">The resource assembly that is loaded depends on the <xref:System.Globalization.CultureInfo.CurrentUICulture%2A> of the current thread.</span></span>

<a name="localizable_ui"></a>
### <a name="localizable-user-interface"></a><span data-ttu-id="ff11c-189">ローカライズ可能なユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ff11c-189">Localizable User Interface</span></span>
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ff11c-190">アプリケーションでは [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] を利用して [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] を定義します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-190">applications use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to define their [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="ff11c-191">で開発すると、オブジェクトの階層に一連のプロパティとロジックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-191">allows developers to specify a hierarchy of objects with a set of properties and logic.</span></span> <span data-ttu-id="ff11c-192">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の主な用途は [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションの開発ですが、共通言語ランタイム (CLR) オブジェクトの階層を指定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-192">The primary use of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is to develop [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications but it can be used to specify a hierarchy of any common language runtime (CLR) objects.</span></span> <span data-ttu-id="ff11c-193">ほとんどの開発者は [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] を利用してアプリケーションの [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] を指定し、C# などのプログラミング言語を利用してユーザーの操作に応答します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-193">Most developers use [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to specify their application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] and use a programming language such as C# to react to user interaction.</span></span>

 <span data-ttu-id="ff11c-194">リソースの観点からは、言語依存の [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] を表すように設計された [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルはリソース要素であり、そのため、その最終的な配布形式はローカライズ可能にして外国の言語に対応できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-194">From a resource point of view, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file designed to describe a language-dependent [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is a resource element and therefore its final distribution format must be localizable to support international languages.</span></span> <span data-ttu-id="ff11c-195">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] はイベントを処理できないため、多くの [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] アプリケーションにはコード ブロックが含まれ、イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-195">Because [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] cannot handle events many [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] applications contain blocks of code to do this.</span></span> <span data-ttu-id="ff11c-196">詳細については、「[XAML の概要 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff11c-196">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span> <span data-ttu-id="ff11c-197">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ファイルがトークン化され、XAML の BAML 形式になるとき、コードは分解され、異なるバイナリにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-197">Code is stripped out and compiled into different binaries when a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is tokenized into the BAML form of XAML.</span></span> <span data-ttu-id="ff11c-198">XAML ファイル、画像、その他の種類の管理対象リソース オブジェクトの BAML 形式はサテライト リソース アセンブリに組み込まれます。サテライト リソース アセンブリに組み込むことで、他の言語にローカライズできます。ローカライズが必要なければ、メイン アセンブリに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-198">The BAML form of XAML files, images, and other types of managed resource objects are embedded in the satellite resource assembly, which can be localized into other languages, or the main assembly when localization is not required.</span></span>

> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ff11c-199">アプリケーションは、文字列テーブルやイメージなど、あらゆる FrameworkCLR リソースに対応しています。</span><span class="sxs-lookup"><span data-stu-id="ff11c-199">applications support all the FrameworkCLR resources including string tables, images, and so forth.</span></span>

<a name="building_localizable_apps"></a>
### <a name="building-localizable-applications"></a><span data-ttu-id="ff11c-200">ローカライズ可能なアプリケーションの構築</span><span class="sxs-lookup"><span data-stu-id="ff11c-200">Building Localizable Applications</span></span>
 <span data-ttu-id="ff11c-201">ローカリゼーションとは、異なる文化に合わせて [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] を調整することです。</span><span class="sxs-lookup"><span data-stu-id="ff11c-201">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="ff11c-202">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションをローカライズ可能にするには、開発者はローカライズ可能なすべてのリソースでリソース アセンブリを構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-202">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="ff11c-203">リソース アセンブリはさまざまな言語にローカライズされ、コードビハインドでリソース管理 API が使用されて読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-203">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span> <span data-ttu-id="ff11c-204">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションに必要なファイルの 1 つは、プロジェクト ファイル (.proj) です。</span><span class="sxs-lookup"><span data-stu-id="ff11c-204">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="ff11c-205">アプリケーションで使用するすべてのリソースをプロジェクト ファイルに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff11c-205">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="ff11c-206">その方法を .csproj ファイルからの次の例で示します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-206">The following example from a .csproj file shows how to do this.</span></span>

```xml
<Resource Include="data\picture1.jpg"/>
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

 <span data-ttu-id="ff11c-207">アプリケーションでリソースを使用するには、<xref:System.Resources.ResourceManager> をインスタンス化し、使用するリソースを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-207">To use a resource in your application instantiate a <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="ff11c-208">この方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-208">The following example demonstrates how to do this.</span></span>

 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

<a name="using_clickonce"></a>
## <a name="using-clickonce-with-localized-applications"></a><span data-ttu-id="ff11c-209">ローカライズされたアプリケーションで ClickOnce を使用する</span><span class="sxs-lookup"><span data-stu-id="ff11c-209">Using ClickOnce with Localized Applications</span></span>
 <span data-ttu-id="ff11c-210">ClickOnce は Visual Studio 2005 に付属する Windows フォームの新しい展開技術です。</span><span class="sxs-lookup"><span data-stu-id="ff11c-210">ClickOnce is a new Windows Forms deployment technology that will ship with Visual Studio 2005.</span></span> <span data-ttu-id="ff11c-211">アプリケーションをインストールしたり、Web アプリケーションをアップグレードしたりできます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-211">It enables application installation and upgrading of Web applications.</span></span> <span data-ttu-id="ff11c-212">ClickOnce で展開されたアプリケーションがローカライズされると、ローカライズされたカルチャでのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-212">When an application that was deployed with ClickOnce is localized it can only be viewed on the localized culture.</span></span> <span data-ttu-id="ff11c-213">たとえば、展開されたアプリケーションが日本語にローカライズされている場合、日本語の Microsoft Windows でのみ表示できます。英語の Windows では表示できません。</span><span class="sxs-lookup"><span data-stu-id="ff11c-213">For example, if a deployed application is localized to Japanese it can only be viewed on Japanese Microsoft Windows not on English Windows.</span></span> <span data-ttu-id="ff11c-214">これは問題になります。日本のユーザーが英語版の Windows を実行することは珍しくないためです。</span><span class="sxs-lookup"><span data-stu-id="ff11c-214">This presents a problem because it is a common scenario for Japanese users to run an English version of Windows.</span></span>

 <span data-ttu-id="ff11c-215">この問題の解決策は、非依存言語フォールバック属性を設定することです。</span><span class="sxs-lookup"><span data-stu-id="ff11c-215">The solution to this problem is setting the neutral language fallback attribute.</span></span> <span data-ttu-id="ff11c-216">アプリケーション開発者はメイン アセンブリからリソースを任意で削除し、特定のカルチャに対応するサテライト アセンブリでそのリソースを見つけられるように指定できます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-216">An application developer can optionally remove resources from the main assembly and specify that the resources can be found in a satellite assembly corresponding to a specific culture.</span></span> <span data-ttu-id="ff11c-217">このプロセスを制御するには、<xref:System.Resources.NeutralResourcesLanguageAttribute> を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-217">To control this process use the <xref:System.Resources.NeutralResourcesLanguageAttribute>.</span></span> <span data-ttu-id="ff11c-218"><xref:System.Resources.NeutralResourcesLanguageAttribute> クラスのコンストラクターには 2 つのシグネチャがあります。1 つは、<xref:System.Resources.UltimateResourceFallbackLocation> パラメーターを受け取り、<xref:System.Resources.ResourceManager> でフォールバック リソースを抽出する場所 (メイン アセンブリまたはサテライト アセンブリ) を指定するものです。</span><span class="sxs-lookup"><span data-stu-id="ff11c-218">The constructor of the <xref:System.Resources.NeutralResourcesLanguageAttribute> class has two signatures, one that takes an <xref:System.Resources.UltimateResourceFallbackLocation> parameter to specify the location where the <xref:System.Resources.ResourceManager> should extract the fallback resources: main assembly or satellite assembly.</span></span> <span data-ttu-id="ff11c-219">この属性を使用する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ff11c-219">The following example shows how to use the attribute.</span></span> <span data-ttu-id="ff11c-220">最終的なフォールバックの場所の場合、コードにより、<xref:System.Resources.ResourceManager> は現在実行中のアセンブリのディレクトリの "de" サブディレクトリ内のリソースが検索されます。</span><span class="sxs-lookup"><span data-stu-id="ff11c-220">For the ultimate fallback location, the code causes the <xref:System.Resources.ResourceManager> to look for the resources in the "de" subdirectory of the directory of the currently executing assembly.</span></span>

```csharp
[assembly: NeutralResourcesLanguageAttribute(
    "de" , UltimateResourceFallbackLocation.Satellite)]
```

## <a name="see-also"></a><span data-ttu-id="ff11c-221">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff11c-221">See also</span></span>

- [<span data-ttu-id="ff11c-222">WPF のグローバリゼーションおよびローカリゼーションの概要</span><span class="sxs-lookup"><span data-stu-id="ff11c-222">WPF Globalization and Localization Overview</span></span>](wpf-globalization-and-localization-overview.md)
