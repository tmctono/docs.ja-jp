---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620225"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="edee5-101">EventListener は、null が埋め込まれた文字列を切り捨てる</span><span class="sxs-lookup"><span data-stu-id="edee5-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="edee5-102">説明</span><span class="sxs-lookup"><span data-stu-id="edee5-102">Details</span></span>

<span data-ttu-id="edee5-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> は、埋め込まれた null のある文字列を切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="edee5-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="edee5-104">null 文字は <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> クラスでサポートされません。</span><span class="sxs-lookup"><span data-stu-id="edee5-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="edee5-105">変更は、プロセスの <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> データを読み取るために <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> を使用し、区切り記号として null 文字を使用するアプリにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="edee5-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="edee5-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="edee5-106">Suggestion</span></span>

<span data-ttu-id="edee5-107">可能な場合は、埋め込まれた null 文字を使用しないように <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> データを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edee5-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="edee5-108">名前</span><span class="sxs-lookup"><span data-stu-id="edee5-108">Name</span></span>    | <span data-ttu-id="edee5-109">[値]</span><span class="sxs-lookup"><span data-stu-id="edee5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="edee5-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="edee5-110">Scope</span></span>   |<span data-ttu-id="edee5-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="edee5-111">Edge</span></span>|
|<span data-ttu-id="edee5-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="edee5-112">Version</span></span>|<span data-ttu-id="edee5-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="edee5-113">4.5.1</span></span>|
|<span data-ttu-id="edee5-114">種類</span><span class="sxs-lookup"><span data-stu-id="edee5-114">Type</span></span>|<span data-ttu-id="edee5-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="edee5-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="edee5-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="edee5-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
