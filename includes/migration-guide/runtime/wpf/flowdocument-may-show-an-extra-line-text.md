---
ms.openlocfilehash: a61005e317020c47a283dae292236624ec6057ce
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497840"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="1fd15-101">FlowDocument でテキストの余分な行が表示される場合がある</span><span class="sxs-lookup"><span data-stu-id="1fd15-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="1fd15-102">説明</span><span class="sxs-lookup"><span data-stu-id="1fd15-102">Details</span></span>

<span data-ttu-id="1fd15-103">.NET Framework 4.0 での実行時の表示と比べて、.NET Framework 4.5 での実行時に <xref:System.Windows.Documents.FlowDocument> 要素でテキストの余分な行が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1fd15-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="1fd15-104">変更によってテキストが正しく表示されなくなったり、読みにくくなったりするようなことはありませんが、以前は <xref:System.Windows.Documents.FlowDocument> のビューから除外されていたテキストが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fd15-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1fd15-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1fd15-105">Suggestion</span></span>

<span data-ttu-id="1fd15-106">場合によっては、表示要素の PageHeight プロパティを 1 ずつ減らすことで、表示行の以前の数を復元できます。</span><span class="sxs-lookup"><span data-stu-id="1fd15-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="1fd15-107">名前</span><span class="sxs-lookup"><span data-stu-id="1fd15-107">Name</span></span>    | <span data-ttu-id="1fd15-108">[値]</span><span class="sxs-lookup"><span data-stu-id="1fd15-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1fd15-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="1fd15-109">Scope</span></span>   |<span data-ttu-id="1fd15-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="1fd15-110">Edge</span></span>|
|<span data-ttu-id="1fd15-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="1fd15-111">Version</span></span>|<span data-ttu-id="1fd15-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1fd15-112">4.5</span></span>|
|<span data-ttu-id="1fd15-113">種類</span><span class="sxs-lookup"><span data-stu-id="1fd15-113">Type</span></span>|<span data-ttu-id="1fd15-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="1fd15-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1fd15-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1fd15-115">Affected APIs</span></span>

- <xref:System.Windows.Documents.FlowDocument.%23ctor>
- <xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)>
- <xref:System.Windows.Controls.FlowDocumentReader.%23ctor>
- <xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor>
- <xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Documents.FlowDocument.#ctor`
- `M:System.Windows.Documents.FlowDocument.#ctor(System.Windows.Documents.Block)`
- `M:System.Windows.Controls.FlowDocumentReader.#ctor`
- `M:System.Windows.Controls.FlowDocumentPageViewer.#ctor`
- `M:System.Windows.Controls.Primitives.DocumentPageView.#ctor`

-->
