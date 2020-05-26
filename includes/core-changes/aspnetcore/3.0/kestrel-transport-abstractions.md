---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721105"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="f3c5f-101">Kestrel: トランスポートの抽象化を削除して公開</span><span class="sxs-lookup"><span data-stu-id="f3c5f-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="f3c5f-102">"pubternal" API からの移行の一環として、Kestrel トランスポート層の API がパブリック インターフェイスとして `Microsoft.AspNetCore.Connections.Abstractions` ライブラリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="f3c5f-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f3c5f-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f3c5f-103">Version introduced</span></span>

<span data-ttu-id="f3c5f-104">3.0</span><span class="sxs-lookup"><span data-stu-id="f3c5f-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f3c5f-105">以前の動作</span><span class="sxs-lookup"><span data-stu-id="f3c5f-105">Old behavior</span></span>

- <span data-ttu-id="f3c5f-106">トランスポート関連の抽象化は、`Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` ライブラリで提供されていました。</span><span class="sxs-lookup"><span data-stu-id="f3c5f-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="f3c5f-107">`ListenOptions.NoDelay` プロパティが使用可能でした。</span><span class="sxs-lookup"><span data-stu-id="f3c5f-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f3c5f-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="f3c5f-108">New behavior</span></span>

- <span data-ttu-id="f3c5f-109">`...Transport.Abstractions` ライブラリの最も使用されている機能を公開するために、`Microsoft.AspNetCore.Connections.Abstractions` ライブラリに `IConnectionListener` インターフェイスが導入されました。</span><span class="sxs-lookup"><span data-stu-id="f3c5f-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="f3c5f-110">トランスポート オプション (`LibuvTransportOptions` および `SocketTransportOptions`) で、`NoDelay` が使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f3c5f-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="f3c5f-111">`SchedulingMode` は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f3c5f-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f3c5f-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="f3c5f-112">Reason for change</span></span>

<span data-ttu-id="f3c5f-113">ASP.NET Core 3.0 は、"pubternal" API から移行しました。</span><span class="sxs-lookup"><span data-stu-id="f3c5f-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f3c5f-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="f3c5f-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="f3c5f-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f3c5f-115">Category</span></span>

<span data-ttu-id="f3c5f-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f3c5f-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3c5f-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f3c5f-117">Affected APIs</span></span>

<span data-ttu-id="f3c5f-118">None</span><span class="sxs-lookup"><span data-stu-id="f3c5f-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
