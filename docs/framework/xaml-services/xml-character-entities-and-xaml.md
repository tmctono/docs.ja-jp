---
title: XML 文字エンティティと XAML
ms.date: 03/30/2017
f1_keywords:
- '&'
- '&amp'
- '&gt'
- '&lt'
helpviewer_keywords:
- XAML [XAML Services], special characters
- ampersand (&) [XAML Services]
- special characters [XAML Services]
- apostrophe (') [XAML Services]
- greater-than (>) character [XAML Services]
- XAML [XAML Services], quotation mark (")
- XAML [XAML Services], apostrophe (')
- '& (ampersand) [XAML Services]'
- XAML [XAML Services], & (ampersand)
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- less-than (<) character [XAML Services]
ms.assetid: 6896d0ce-74f7-420a-9ab4-de9bbf390e8d
ms.openlocfilehash: b4621da21200e6c9e2b174a0e2ba508a4f6bab92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938711"
---
# <a name="xml-character-entities-and-xaml"></a><span data-ttu-id="fe48f-102">XML 文字エンティティと XAML</span><span class="sxs-lookup"><span data-stu-id="fe48f-102">XML Character Entities and XAML</span></span>
<span data-ttu-id="fe48f-103">XAML は、特殊文字に、XML で定義される文字エンティティを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe48f-103">XAML uses character entities defined in XML for special characters.</span></span> <span data-ttu-id="fe48f-104">ここでは、いくつかの特定の文字エンティティ、および XAML における他の XML の概念に関する一般的な考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe48f-104">This topic describes some specific character entities and general considerations for other XML concepts in XAML.</span></span>  
  
<a name="character_entities_and_escaping_issues_that_are_unique_to_xaml"></a>   
## <a name="character-entities-and-escaping-issues-that-are-unique-to-xaml"></a><span data-ttu-id="fe48f-105">XAML に固有の文字のエンティティとエスケープの問題</span><span class="sxs-lookup"><span data-stu-id="fe48f-105">Character Entities and Escaping Issues That Are Unique to XAML</span></span>  
 <span data-ttu-id="fe48f-106">XAML マークアップでは、一般に、XML で定義されているものと同じ文字エンティティおよびエスケープ シーケンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe48f-106">XAML markup typically uses the same character entities and escape sequences that are defined in XML.</span></span>  
  
 <span data-ttu-id="fe48f-107">大きな違いは、XAML では中かっこ ({ と }) が意味を持つ点です。中かっこで囲まれた文字シーケンスは、マークアップ拡張機能として解釈する必要があることを XAML プロセッサに通知します。</span><span class="sxs-lookup"><span data-stu-id="fe48f-107">The main exception is that braces ({ and }) have significance in XAML because these characters inform a XAML processor that a character sequence enclosed by braces must be interpreted as a markup extension.</span></span> <span data-ttu-id="fe48f-108">マークアップ拡張機能について詳しくは、「 [XAML のマークアップ拡張機能の概要](markup-extensions-for-xaml-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe48f-108">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-for-xaml-overview.md).</span></span>  
  
 <span data-ttu-id="fe48f-109">ただし、XML ではなく XAML に固有のエスケープ シーケンスを使用すると、中かっこをリテラル文字として表示できます。</span><span class="sxs-lookup"><span data-stu-id="fe48f-109">However, you can still display the braces as literal characters by using an escape sequence that is particular to XAML instead of XML.</span></span> <span data-ttu-id="fe48f-110">詳細については、次を参照してください。 [ {}エスケープ シーケンス/マークアップ拡張](escape-sequence-markup-extension.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe48f-110">For more information, see [{} Escape Sequence - Markup Extension](escape-sequence-markup-extension.md).</span></span>  
  
 <span data-ttu-id="fe48f-111">なお、円記号 (\\) を文字列として処理されるときに、エスケープ シーケンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fe48f-111">Note that a backslash (\\) does not require an escape sequence when it is handled as a string.</span></span>  
  
<a name="xml_character_entities"></a>   
## <a name="xml-character-entities"></a><span data-ttu-id="fe48f-112">XML 文字エンティティ</span><span class="sxs-lookup"><span data-stu-id="fe48f-112">XML Character Entities</span></span>  
 <span data-ttu-id="fe48f-113">前に述べたように、XAML マークアップを記述するときに一般的に使用する文字エンティティおよびエスケープ シーケンスの大半は、XML で定義されています。</span><span class="sxs-lookup"><span data-stu-id="fe48f-113">As mentioned previously, most character entities and escape sequences that are typically used to write XAML markup are defined by XML.</span></span> <span data-ttu-id="fe48f-114">このトピックでは、こうしたエンティティの一覧は示しません。エンティティの詳細なリファレンスについては、XML 仕様などの外部ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe48f-114">This topic does not provide the complete list of these entities; a detailed reference for the entities can be found in external documentation, such as in XML specifications.</span></span> <span data-ttu-id="fe48f-115">ただし、このトピックでは、便宜を考えて、XAML マークアップでよく使用する XML 文字エンティティを抜粋した一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="fe48f-115">However, for convenience, this topic lists some of the specific XML character entities that are typically used in XAML markup.</span></span>  
  
|<span data-ttu-id="fe48f-116">文字</span><span class="sxs-lookup"><span data-stu-id="fe48f-116">Character</span></span>|<span data-ttu-id="fe48f-117">エンティティ</span><span class="sxs-lookup"><span data-stu-id="fe48f-117">Entity</span></span>|<span data-ttu-id="fe48f-118">メモ</span><span class="sxs-lookup"><span data-stu-id="fe48f-118">Notes</span></span>|  
|---------------|------------|-----------|  
|<span data-ttu-id="fe48f-119">& (アンパサンド)</span><span class="sxs-lookup"><span data-stu-id="fe48f-119">& (ampersand)</span></span>|<span data-ttu-id="fe48f-120">\&amp;</span><span class="sxs-lookup"><span data-stu-id="fe48f-120">\&amp;</span></span>|<span data-ttu-id="fe48f-121">属性値および要素の内容の両方に対して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe48f-121">Must be used both for attribute values and for content of an element.</span></span>|  
|<span data-ttu-id="fe48f-122">> (大きい-より文字)</span><span class="sxs-lookup"><span data-stu-id="fe48f-122">> (greater-than character)</span></span>|<span data-ttu-id="fe48f-123">\&gt;</span><span class="sxs-lookup"><span data-stu-id="fe48f-123">\&gt;</span></span>|<span data-ttu-id="fe48f-124">属性値に対して使用する必要がありますが、> が同じくらい要素のコンテンツとして許容される < 前しません。</span><span class="sxs-lookup"><span data-stu-id="fe48f-124">Must be used for an attribute value, but > is acceptable as the content of an element as long as < does not precede it.</span></span>|  
|<span data-ttu-id="fe48f-125">< (以下の文字よりも)</span><span class="sxs-lookup"><span data-stu-id="fe48f-125">< (less-than character)</span></span>|<span data-ttu-id="fe48f-126">\&lt;</span><span class="sxs-lookup"><span data-stu-id="fe48f-126">\&lt;</span></span>|<span data-ttu-id="fe48f-127">属性値に対して使用する必要がありますが、\<が同じくらい要素のコンテンツとして許容される > それに従っていません。</span><span class="sxs-lookup"><span data-stu-id="fe48f-127">Must be used for an attribute value, but \< is acceptable as the content of an element as long as > does not follow it.</span></span>|  
|<span data-ttu-id="fe48f-128">" (二重引用符)</span><span class="sxs-lookup"><span data-stu-id="fe48f-128">" (straight quotation mark)</span></span>|<span data-ttu-id="fe48f-129">\&quot;</span><span class="sxs-lookup"><span data-stu-id="fe48f-129">\&quot;</span></span>|<span data-ttu-id="fe48f-130">属性値に対しては使用する必要があります。要素の内容としては、二重引用符 (") も受け入れられます、</span><span class="sxs-lookup"><span data-stu-id="fe48f-130">Must be used for an attribute value, but a straight quotation mark (") is acceptable as the content of an element.</span></span> <span data-ttu-id="fe48f-131">属性値は、単一引用符 (') と二重引用符 (") のどちらかで囲むことができます。最初に使用したほうの引用符が、属性値を囲む文字になり、もう一方の引用符は値の中でリテラルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe48f-131">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="fe48f-132">' (単一引用符)</span><span class="sxs-lookup"><span data-stu-id="fe48f-132">' (single straight quotation mark)</span></span>|<span data-ttu-id="fe48f-133">\&apos;</span><span class="sxs-lookup"><span data-stu-id="fe48f-133">\&apos;</span></span>|<span data-ttu-id="fe48f-134">属性値に対しては使用する必要があります。要素の内容としては、単一引用符 (') も受け入れられます、</span><span class="sxs-lookup"><span data-stu-id="fe48f-134">Must be used for an attribute value, but a single straight quotation mark (') is acceptable as the content of an element.</span></span> <span data-ttu-id="fe48f-135">属性値は、単一引用符 (') と二重引用符 (") のどちらかで囲むことができます。最初に使用したほうの引用符が、属性値を囲む文字になり、もう一方の引用符は値の中でリテラルとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe48f-135">Note that attribute values may be enclosed either by a single straight quotation mark (') or by a straight quotation mark ("); whichever character appears first defines the attribute value enclosure, and the alternative quote can then be used as a literal within the value.</span></span>|  
|<span data-ttu-id="fe48f-136">(数値と文字の対応付け)</span><span class="sxs-lookup"><span data-stu-id="fe48f-136">(numeric character mappings)</span></span>|<span data-ttu-id="fe48f-137">&#*[整数]*; または &#x *[進数]*;</span><span class="sxs-lookup"><span data-stu-id="fe48f-137">&#*[integer]*; or &#x *[hex]*;</span></span>|<span data-ttu-id="fe48f-138">XAML では、アクティブなエンコーディングに応じた数値と文字の対応付けがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fe48f-138">XAML supports numeric character mappings into the encoding that is active.</span></span>|  
|<span data-ttu-id="fe48f-139">(改行しないスペース)</span><span class="sxs-lookup"><span data-stu-id="fe48f-139">(nonbreaking space)</span></span>|<span data-ttu-id="fe48f-140">&\#160;(utf-8 エンコードを想定)</span><span class="sxs-lookup"><span data-stu-id="fe48f-140">&\#160; (assuming UTF-8 encoding)</span></span>|<span data-ttu-id="fe48f-141">フロー ドキュメントの要素、または WPF の <xref:System.Windows.Controls.TextBox> などのテキストを受け取る要素では、マークアップからの改行しないスペースの正規化は行われません。これには、`xml:space="default"` の場合も含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe48f-141">For flow document elements, or elements that take text such as the WPF <xref:System.Windows.Controls.TextBox>, nonbreaking spaces are not normalized out of the markup, even for `xml:space="default"`.</span></span> <span data-ttu-id="fe48f-142">(詳細については、次を参照してください[空白 XAML 処理](whitespace-processing-in-xaml.md)。)。</span><span class="sxs-lookup"><span data-stu-id="fe48f-142">(For more information, see [White-space processing in XAML](whitespace-processing-in-xaml.md).)</span></span>|  
  
<a name="xml_comment_format"></a>   
## <a name="xml-comment-format"></a><span data-ttu-id="fe48f-143">XML のコメントの書式</span><span class="sxs-lookup"><span data-stu-id="fe48f-143">XML Comment Format</span></span>  
 <span data-ttu-id="fe48f-144">XAML では、XML のコメントの書式を使用します。つまり、コメントの先頭は `<!--` で表し、コメントの末尾は `-->,` で表します。コメントの中に `--` というシーケンスを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="fe48f-144">XAML uses the XML comment format: the start of the comment is `<!--`, the end of comment is `-->,` and the sequence `--` must not occur within the comment.</span></span>  
  
<a name="xml_processing_instructions"></a>   
## <a name="xml-processing-instructions"></a><span data-ttu-id="fe48f-145">XML 処理命令</span><span class="sxs-lookup"><span data-stu-id="fe48f-145">XML Processing Instructions</span></span>  
 <span data-ttu-id="fe48f-146">XAML では、XML 仕様に従って XML 処理命令が処理されます。つまり、命令は必ず素通しされます。</span><span class="sxs-lookup"><span data-stu-id="fe48f-146">XAML handles XML processing instructions according to XML specifications, which state that the instructions must be passed through.</span></span> <span data-ttu-id="fe48f-147">.NET Framework XAML サービスで処理する XAML では、ある処理命令は使用しません。</span><span class="sxs-lookup"><span data-stu-id="fe48f-147">XAML processing in .NET Framework XAML Services  does not use any processing instructions.</span></span> <span data-ttu-id="fe48f-148">XAML を使用する他の既存のフレームワークでも、XAML の処理命令は使用されません。</span><span class="sxs-lookup"><span data-stu-id="fe48f-148">Other existing frameworks that use XAML also do not use processing instructions from XAML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe48f-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe48f-149">See also</span></span>

- [<span data-ttu-id="fe48f-150">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="fe48f-150">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="fe48f-151">マークアップ拡張機能と WPF XAML</span><span class="sxs-lookup"><span data-stu-id="fe48f-151">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="fe48f-152">XamlName の文法</span><span class="sxs-lookup"><span data-stu-id="fe48f-152">XamlName Grammar</span></span>](xamlname-grammar.md)
- [<span data-ttu-id="fe48f-153">空白 XAML での処理</span><span class="sxs-lookup"><span data-stu-id="fe48f-153">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
