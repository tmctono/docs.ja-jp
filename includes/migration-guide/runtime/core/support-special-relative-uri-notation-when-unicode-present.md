---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496524"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="11636-101">Unicode が存在する場合の特別な相対 URI 表記のサポート</span><span class="sxs-lookup"><span data-stu-id="11636-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="11636-102">説明</span><span class="sxs-lookup"><span data-stu-id="11636-102">Details</span></span>

<span data-ttu-id="11636-103"><xref:System.Uri> では、Unicode を含む特定の相対 URI で <xref:System.Uri.TryCreate%2A> を呼び出したときに、<xref:System.NullReferenceException> がスローされなくなります。</span><span class="sxs-lookup"><span data-stu-id="11636-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="11636-104"><xref:System.NullReferenceException> の最も単純な再現を以下に示します。2 つのステートメントは同等です。</span><span class="sxs-lookup"><span data-stu-id="11636-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="11636-105"><xref:System.NullReferenceException> を再現するには、次の項目が true である必要があります。</span><span class="sxs-lookup"><span data-stu-id="11636-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="11636-106">URI は、前に "http:" を付加し、その後に "//" を付けずに相対として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11636-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="11636-107">URI には、パーセントでエンコードされた Unicode または予約されていないシンボルを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="11636-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="11636-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="11636-108">Suggestion</span></span>

<span data-ttu-id="11636-109">相対 URI を許可しないようにするためにこの動作に依存しているユーザーは、URI の作成時に代わりに <xref:System.UriKind.Absolute?displayProperty=nameWithType> を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11636-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="11636-110">名前</span><span class="sxs-lookup"><span data-stu-id="11636-110">Name</span></span>    | <span data-ttu-id="11636-111">[値]</span><span class="sxs-lookup"><span data-stu-id="11636-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="11636-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="11636-112">Scope</span></span>   |<span data-ttu-id="11636-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="11636-113">Edge</span></span>|
|<span data-ttu-id="11636-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="11636-114">Version</span></span>|<span data-ttu-id="11636-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="11636-115">4.7.2</span></span>|
|<span data-ttu-id="11636-116">種類</span><span class="sxs-lookup"><span data-stu-id="11636-116">Type</span></span>|<span data-ttu-id="11636-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="11636-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="11636-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="11636-118">Affected APIs</span></span>

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
