---
ms.openlocfilehash: e56d896f093d6cd28ed0d6640ba154e5d4593c6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497631"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a><span data-ttu-id="9b385-101">XmlTextReader DTD エンティティの拡張が、10,000, 000 文字に制限される</span><span class="sxs-lookup"><span data-stu-id="9b385-101">XmlTextReader DTD entity expansion is limited to 10,000,000 characters</span></span>

#### <a name="details"></a><span data-ttu-id="9b385-102">説明</span><span class="sxs-lookup"><span data-stu-id="9b385-102">Details</span></span>

<span data-ttu-id="9b385-103">DTD エンティティの拡張は 10,000,000 文字までに制限されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9b385-103">DTD entity expansion is now limited to 10,000,000 characters.</span></span> <span data-ttu-id="9b385-104">DTD エンティティの展開を使用しない XML ファイルの読み込みや、制限された DTD エンティティの展開を使用した XML ファイルの読み込みは、影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="9b385-104">Loading XML files without DTD entity expansion or with limited DTD entity expansion is unaffected.</span></span> <span data-ttu-id="9b385-105">DTD エンティティの展開が 10,000,000 文字を超えるファイルは読み込みに失敗し、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="9b385-105">Files with DTD entities that expand to more than 10,000,000 characters fail to load, and now throw an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9b385-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="9b385-106">Suggestion</span></span>

<span data-ttu-id="9b385-107">DTD エンティティの拡張の制限が 10,000, 000 では低すぎる場合には、<xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> プロパティで値をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="9b385-107">If the limit of DTD entity expansion is too low 10,000,000, the value can be overridden with the <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> property.</span></span> <span data-ttu-id="9b385-108">適切な <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> 値を持つ <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> を、<xref:System.Xml.XmlReaderSettings?displayProperty=fullName> を受け取る <code>XmlReader.Create</code> に渡すことができます (<xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)> など)</span><span class="sxs-lookup"><span data-stu-id="9b385-108">An <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> with the proper <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> value can be passed to <code>XmlReader.Create</code> that takes <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (ie. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)</span></span>

| <span data-ttu-id="9b385-109">名前</span><span class="sxs-lookup"><span data-stu-id="9b385-109">Name</span></span>    | <span data-ttu-id="9b385-110">[値]</span><span class="sxs-lookup"><span data-stu-id="9b385-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9b385-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="9b385-111">Scope</span></span>   |<span data-ttu-id="9b385-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="9b385-112">Edge</span></span>|
|<span data-ttu-id="9b385-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="9b385-113">Version</span></span>|<span data-ttu-id="9b385-114">4.5</span><span class="sxs-lookup"><span data-stu-id="9b385-114">4.5</span></span>|
|<span data-ttu-id="9b385-115">種類</span><span class="sxs-lookup"><span data-stu-id="9b385-115">Type</span></span>|<span data-ttu-id="9b385-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="9b385-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9b385-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="9b385-117">Affected APIs</span></span>

- <xref:System.Xml.XmlTextReader?displayProperty=nameWithType>
- <xref:System.Xml.XmlTextReader.%23ctor>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)>

<!--

#### Affected APIs

- `T:System.Xml.XmlTextReader`
- `M:System.Xml.XmlTextReader.#ctor`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.Xml.XmlNameTable)`

-->
