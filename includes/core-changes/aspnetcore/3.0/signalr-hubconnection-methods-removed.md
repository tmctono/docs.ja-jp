---
ms.openlocfilehash: a56c5fc32b5fd274d5da0d9b295918f5ea3b345e
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394231"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a><span data-ttu-id="1748b-101">SignalR: HubConnection の ResetSendPing メソッドと ResetTimeout メソッドが削除された</span><span class="sxs-lookup"><span data-stu-id="1748b-101">SignalR: HubConnection ResetSendPing and ResetTimeout methods removed</span></span>

<span data-ttu-id="1748b-102">`ResetSendPing` メソッドと `ResetTimeout` メソッドが、SignalR の `HubConnection` API から削除されました。</span><span class="sxs-lookup"><span data-stu-id="1748b-102">The `ResetSendPing` and `ResetTimeout` methods were removed from the SignalR `HubConnection` API.</span></span> <span data-ttu-id="1748b-103">これらのメソッドはもともと内部使用のみを目的としていましたが、ASP.NET Core 2.2 で公開されました。</span><span class="sxs-lookup"><span data-stu-id="1748b-103">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span> <span data-ttu-id="1748b-104">これらのメソッドは、ASP.NET Core 3.0 Preview 4 リリース以降では使用できません。</span><span class="sxs-lookup"><span data-stu-id="1748b-104">These methods won't be available starting in the ASP.NET Core 3.0 Preview 4 release.</span></span> <span data-ttu-id="1748b-105">ディスカッションについては、[aspnet/AspNetCore#8543](https://github.com/aspnet/AspNetCore/issues/8543) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1748b-105">For discussion, see [aspnet/AspNetCore#8543](https://github.com/aspnet/AspNetCore/issues/8543).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1748b-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="1748b-106">Version introduced</span></span>

<span data-ttu-id="1748b-107">3.0</span><span class="sxs-lookup"><span data-stu-id="1748b-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1748b-108">以前の動作</span><span class="sxs-lookup"><span data-stu-id="1748b-108">Old behavior</span></span>

<span data-ttu-id="1748b-109">API を使用できました。</span><span class="sxs-lookup"><span data-stu-id="1748b-109">APIs were available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1748b-110">新しい動作</span><span class="sxs-lookup"><span data-stu-id="1748b-110">New behavior</span></span>

<span data-ttu-id="1748b-111">API は削除されています。</span><span class="sxs-lookup"><span data-stu-id="1748b-111">APIs are removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1748b-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="1748b-112">Reason for change</span></span>

<span data-ttu-id="1748b-113">これらのメソッドはもともと内部使用のみを目的としていましたが、ASP.NET Core 2.2 で公開されました。</span><span class="sxs-lookup"><span data-stu-id="1748b-113">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1748b-114">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="1748b-114">Recommended action</span></span>

<span data-ttu-id="1748b-115">これらのメソッドは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="1748b-115">Don't use these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="1748b-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="1748b-116">Category</span></span>

<span data-ttu-id="1748b-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1748b-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1748b-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1748b-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
