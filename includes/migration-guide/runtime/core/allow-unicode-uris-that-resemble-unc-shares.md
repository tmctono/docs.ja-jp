---
ms.openlocfilehash: fbc39b6e1cc19f6c2846caaabb9a8a721494b4e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804437"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="16717-101">UNC 共有に似た URI での Unicode の許可</span><span class="sxs-lookup"><span data-stu-id="16717-101">Allow Unicode in URIs that resemble UNC shares</span></span>

|   |   |
|---|---|
|<span data-ttu-id="16717-102">説明</span><span class="sxs-lookup"><span data-stu-id="16717-102">Details</span></span>|<span data-ttu-id="16717-103"><xref:System.Uri?displayProperty=fullName> では、UNC 共有名と Unicode 文字の両方を含むファイル URI の構築時に、URI が無効な内部状態にならなくなります。</span><span class="sxs-lookup"><span data-stu-id="16717-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="16717-104">以下のすべてに該当する場合にのみ、動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="16717-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="16717-105">URI にスキーム <code>file:</code> があり、4 つ以上のスラッシュが続く。</span><span class="sxs-lookup"><span data-stu-id="16717-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="16717-106">ホスト名がアンダースコアまたはその他の予約されていないシンボルで始まる。</span><span class="sxs-lookup"><span data-stu-id="16717-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="16717-107">URI に Unicode 文字が含まれている。</span><span class="sxs-lookup"><span data-stu-id="16717-107">The URI contains Unicode characters.</span></span></li></ul>|
|<span data-ttu-id="16717-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="16717-108">Suggestion</span></span>|<span data-ttu-id="16717-109">Unicode を含む URI を一貫して操作するアプリケーションでこの動作を使用して、UNC 共有への参照を許可しないようにした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16717-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="16717-110">これらのアプリケーションでは代わりに <xref:System.Uri.IsUnc> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16717-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>|
|<span data-ttu-id="16717-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="16717-111">Scope</span></span>|<span data-ttu-id="16717-112">エッジ</span><span class="sxs-lookup"><span data-stu-id="16717-112">Edge</span></span>|
|<span data-ttu-id="16717-113">Version</span><span class="sxs-lookup"><span data-stu-id="16717-113">Version</span></span>|<span data-ttu-id="16717-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="16717-114">4.7.2</span></span>|
|<span data-ttu-id="16717-115">型</span><span class="sxs-lookup"><span data-stu-id="16717-115">Type</span></span>|<span data-ttu-id="16717-116">ランタイム</span><span class="sxs-lookup"><span data-stu-id="16717-116">Runtime</span></span>|
|<span data-ttu-id="16717-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="16717-117">Affected APIs</span></span>|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
