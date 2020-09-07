---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496323"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="380af-101">UNC 共有に似た URI での Unicode の許可</span><span class="sxs-lookup"><span data-stu-id="380af-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="380af-102">説明</span><span class="sxs-lookup"><span data-stu-id="380af-102">Details</span></span>

<span data-ttu-id="380af-103"><xref:System.Uri?displayProperty=fullName> では、UNC 共有名と Unicode 文字の両方を含むファイル URI の構築時に、URI が無効な内部状態にならなくなります。</span><span class="sxs-lookup"><span data-stu-id="380af-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="380af-104">以下のすべてに該当する場合にのみ、動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="380af-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="380af-105">URI にスキーム <code>file:</code> があり、4 つ以上のスラッシュが続く。</span><span class="sxs-lookup"><span data-stu-id="380af-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="380af-106">ホスト名がアンダースコアまたはその他の予約されていないシンボルで始まる。</span><span class="sxs-lookup"><span data-stu-id="380af-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="380af-107">URI に Unicode 文字が含まれている。</span><span class="sxs-lookup"><span data-stu-id="380af-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="380af-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="380af-108">Suggestion</span></span>

<span data-ttu-id="380af-109">Unicode を含む URI を一貫して操作するアプリケーションでこの動作を使用して、UNC 共有への参照を許可しないようにした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="380af-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="380af-110">これらのアプリケーションでは代わりに <xref:System.Uri.IsUnc> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380af-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="380af-111">名前</span><span class="sxs-lookup"><span data-stu-id="380af-111">Name</span></span>    | <span data-ttu-id="380af-112">[値]</span><span class="sxs-lookup"><span data-stu-id="380af-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="380af-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="380af-113">Scope</span></span>   |<span data-ttu-id="380af-114">エッジ</span><span class="sxs-lookup"><span data-stu-id="380af-114">Edge</span></span>|
|<span data-ttu-id="380af-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="380af-115">Version</span></span>|<span data-ttu-id="380af-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="380af-116">4.7.2</span></span>|
|<span data-ttu-id="380af-117">種類</span><span class="sxs-lookup"><span data-stu-id="380af-117">Type</span></span>|<span data-ttu-id="380af-118">ランタイム</span><span class="sxs-lookup"><span data-stu-id="380af-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="380af-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="380af-119">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
