---
ms.openlocfilehash: f95c3916f4da8164cf927344f60f2845f04ddc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394045"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="4618a-101">Kestrel: トランスポートの抽象化を削除して公開</span><span class="sxs-lookup"><span data-stu-id="4618a-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="4618a-102">"pubternal" API からの移行の一環として、Kestrel トランスポート層の API がパブリック インターフェイスとして `Microsoft.AspNetCore.Connections.Abstractions` ライブラリに公開されています。</span><span class="sxs-lookup"><span data-stu-id="4618a-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4618a-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="4618a-103">Version introduced</span></span>

<span data-ttu-id="4618a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="4618a-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4618a-105">以前の動作</span><span class="sxs-lookup"><span data-stu-id="4618a-105">Old behavior</span></span>

- <span data-ttu-id="4618a-106">トランスポート関連の抽象化は、`Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` ライブラリで提供されていました。</span><span class="sxs-lookup"><span data-stu-id="4618a-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="4618a-107">`ListenOptions.NoDelay` プロパティが使用可能でした。</span><span class="sxs-lookup"><span data-stu-id="4618a-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4618a-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="4618a-108">New behavior</span></span>

- <span data-ttu-id="4618a-109">`...Transport.Abstractions` ライブラリの最も使用されている機能を公開するために、`Microsoft.AspNetCore.Connections.Abstractions` ライブラリに `IConnectionListener` インターフェイスが導入されました。</span><span class="sxs-lookup"><span data-stu-id="4618a-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="4618a-110">トランスポート オプション (`LibuvTransportOptions` および `SocketTransportOptions`) で、`NoDelay` が使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4618a-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="4618a-111">`SchedulingMode` は使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="4618a-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4618a-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="4618a-112">Reason for change</span></span>

<span data-ttu-id="4618a-113">ASP.NET Core 3.0 は、"pubternal" API から移行しました。</span><span class="sxs-lookup"><span data-stu-id="4618a-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4618a-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="4618a-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="4618a-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="4618a-115">Category</span></span>

<span data-ttu-id="4618a-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4618a-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4618a-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4618a-117">Affected APIs</span></span>

<span data-ttu-id="4618a-118">None</span><span class="sxs-lookup"><span data-stu-id="4618a-118">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
