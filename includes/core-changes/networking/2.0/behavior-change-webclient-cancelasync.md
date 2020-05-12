---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859614"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a><span data-ttu-id="2ce0e-101">WebClient.CancelAsync ですぐにキャンセルされない場合がある</span><span class="sxs-lookup"><span data-stu-id="2ce0e-101">WebClient.CancelAsync doesn't always cancel immediately</span></span>

<span data-ttu-id="2ce0e-102">.NET Core 2.0 以降、<xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> を呼び出したとき、応答がフェッチを開始している場合、要求がすぐにキャンセルされません。</span><span class="sxs-lookup"><span data-stu-id="2ce0e-102">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> doesn't cancel the request immediately if the response has started to fetch.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2ce0e-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="2ce0e-103">Change description</span></span>

<span data-ttu-id="2ce0e-104">以前は、<xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> を呼び出すと要求がすぐにキャンセルされました。</span><span class="sxs-lookup"><span data-stu-id="2ce0e-104">Previously, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> canceled the request immediately.</span></span> <span data-ttu-id="2ce0e-105">.NET Core 2.0 以降、<xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> を呼び出したとき、応答がフェッチを開始していない場合にのみ、要求がすぐにキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="2ce0e-105">Starting in .NET Core 2.0, calling <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> cancels the request immediately only if the response hasn't started fetching.</span></span> <span data-ttu-id="2ce0e-106">応答がフェッチを開始している場合、完全な応答が読み取られた後でのみ、要求がキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="2ce0e-106">If the response has started to fetch, the request is cancelled only after a complete response is read.</span></span>

<span data-ttu-id="2ce0e-107">この変化の理由は、<xref:System.Net.WebClient> API が非推奨になり、<xref:System.Net.Http.HttpClient> に取って代わられたことにあります。</span><span class="sxs-lookup"><span data-stu-id="2ce0e-107">This change was implemented because the <xref:System.Net.WebClient> API is deprecated in favor of <xref:System.Net.Http.HttpClient>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2ce0e-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="2ce0e-108">Version introduced</span></span>

<span data-ttu-id="2ce0e-109">2.0</span><span class="sxs-lookup"><span data-stu-id="2ce0e-109">2.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2ce0e-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="2ce0e-110">Recommended action</span></span>

<span data-ttu-id="2ce0e-111">非推奨になっている <xref:System.Net.WebClient?displayProperty=fullName> ではなく、<xref:System.Net.Http.HttpClient?displayProperty=fullName> クラスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="2ce0e-111">Use the <xref:System.Net.Http.HttpClient?displayProperty=fullName> class instead of <xref:System.Net.WebClient?displayProperty=fullName>, which is deprecated.</span></span>

#### <a name="category"></a><span data-ttu-id="2ce0e-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="2ce0e-112">Category</span></span>

<span data-ttu-id="2ce0e-113">ネットワーキング</span><span class="sxs-lookup"><span data-stu-id="2ce0e-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2ce0e-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2ce0e-114">Affected APIs</span></span>

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
