---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496864"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="2da8a-101">EventListener は、null が埋め込まれた文字列を切り捨てる</span><span class="sxs-lookup"><span data-stu-id="2da8a-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="2da8a-102">説明</span><span class="sxs-lookup"><span data-stu-id="2da8a-102">Details</span></span>

<span data-ttu-id="2da8a-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> は、埋め込まれた null のある文字列を切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="2da8a-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="2da8a-104">null 文字は <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> クラスでサポートされません。</span><span class="sxs-lookup"><span data-stu-id="2da8a-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="2da8a-105">変更は、プロセスの <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> データを読み取るために <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> を使用し、区切り記号として null 文字を使用するアプリにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="2da8a-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2da8a-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2da8a-106">Suggestion</span></span>

<span data-ttu-id="2da8a-107">可能な場合は、埋め込まれた null 文字を使用しないように <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> データを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2da8a-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="2da8a-108">名前</span><span class="sxs-lookup"><span data-stu-id="2da8a-108">Name</span></span>    | <span data-ttu-id="2da8a-109">[値]</span><span class="sxs-lookup"><span data-stu-id="2da8a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2da8a-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="2da8a-110">Scope</span></span>   |<span data-ttu-id="2da8a-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="2da8a-111">Edge</span></span>|
|<span data-ttu-id="2da8a-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="2da8a-112">Version</span></span>|<span data-ttu-id="2da8a-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="2da8a-113">4.5.1</span></span>|
|<span data-ttu-id="2da8a-114">種類</span><span class="sxs-lookup"><span data-stu-id="2da8a-114">Type</span></span>|<span data-ttu-id="2da8a-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2da8a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2da8a-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2da8a-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
