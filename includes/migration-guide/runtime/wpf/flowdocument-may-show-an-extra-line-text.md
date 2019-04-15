---
ms.openlocfilehash: 6c1740df66ead271afa5f97dc125587810946bc6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235444"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="38774-101">FlowDocument でテキストの余分な行が表示される場合がある</span><span class="sxs-lookup"><span data-stu-id="38774-101">FlowDocument may show an extra line of text</span></span>

|   |   |
|---|---|
|<span data-ttu-id="38774-102">説明</span><span class="sxs-lookup"><span data-stu-id="38774-102">Details</span></span>|<span data-ttu-id="38774-103">.NET Framework 4.0 での実行時の表示と比べて、.NET Framework 4.5 での実行時に <xref:System.Windows.Documents.FlowDocument> 要素でテキストの余分な行が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="38774-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="38774-104">変更によってテキストが正しく表示されなくなったり、読みにくくなったりするようなことはありませんが、以前は <xref:System.Windows.Documents.FlowDocument> のビューから除外されていたテキストが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38774-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>|
|<span data-ttu-id="38774-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="38774-105">Suggestion</span></span>|<span data-ttu-id="38774-106">場合によっては、表示要素の PageHeight プロパティを 1 ずつ減らすことで、表示行の以前の数を復元できます。</span><span class="sxs-lookup"><span data-stu-id="38774-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>|
|<span data-ttu-id="38774-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="38774-107">Scope</span></span>|<span data-ttu-id="38774-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="38774-108">Edge</span></span>|
|<span data-ttu-id="38774-109">Version</span><span class="sxs-lookup"><span data-stu-id="38774-109">Version</span></span>|<span data-ttu-id="38774-110">4.5</span><span class="sxs-lookup"><span data-stu-id="38774-110">4.5</span></span>|
|<span data-ttu-id="38774-111">型</span><span class="sxs-lookup"><span data-stu-id="38774-111">Type</span></span>|<span data-ttu-id="38774-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="38774-112">Runtime</span></span>|
|<span data-ttu-id="38774-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="38774-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|
