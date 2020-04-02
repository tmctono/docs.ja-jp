---
ms.openlocfilehash: 329ef39c7626ecd743577f336a4c8cd4a38fb082
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291642"
---
### <a name="signalr-usesignalr-and-useconnections-methods-removed"></a><span data-ttu-id="cfd76-101">SignalR:UseSignalR メソッドと UseConnections メソッドが削除された</span><span class="sxs-lookup"><span data-stu-id="cfd76-101">SignalR: UseSignalR and UseConnections methods removed</span></span>

<span data-ttu-id="cfd76-102">ASP.NET Core 3.0 の SignalR では、エンドポイント ルーティングが採用されました。</span><span class="sxs-lookup"><span data-stu-id="cfd76-102">In ASP.NET Core 3.0, SignalR adopted endpoint routing.</span></span> <span data-ttu-id="cfd76-103">その変更の一環として、<xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>、<xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>、およびいくつかの関連するメソッドが古い機能としてマークされました。</span><span class="sxs-lookup"><span data-stu-id="cfd76-103">As part of that change, the <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A>, <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A>, and some related methods were marked as obsolete.</span></span> <span data-ttu-id="cfd76-104">ASP.NET Core 5.0 では、これらの古いメソッドが削除されました。</span><span class="sxs-lookup"><span data-stu-id="cfd76-104">In ASP.NET Core 5.0, those obsolete methods were removed.</span></span> <span data-ttu-id="cfd76-105">メソッドの完全な一覧については、「[影響を受ける API](#affected-apis)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cfd76-105">For the full list of methods, see [Affected APIs](#affected-apis).</span></span>

<span data-ttu-id="cfd76-106">この問題に関するディスカッションについては、[dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd76-106">For discussion on this issue, see [dotnet/aspnetcore#20082](https://github.com/dotnet/aspnetcore/issues/20082).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cfd76-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cfd76-107">Version introduced</span></span>

<span data-ttu-id="cfd76-108">5.0 Preview 3</span><span class="sxs-lookup"><span data-stu-id="cfd76-108">5.0 Preview 3</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cfd76-109">以前の動作</span><span class="sxs-lookup"><span data-stu-id="cfd76-109">Old behavior</span></span>

<span data-ttu-id="cfd76-110">SignalR のハブと接続ハンドラーは、`UseSignalR` または `UseConnections` メソッドを使用して、ミドルウェア パイプラインで登録できました。</span><span class="sxs-lookup"><span data-stu-id="cfd76-110">SignalR hubs and connection handlers could be registered in the middleware pipeline using the `UseSignalR` or `UseConnections` methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cfd76-111">新しい動作</span><span class="sxs-lookup"><span data-stu-id="cfd76-111">New behavior</span></span>

<span data-ttu-id="cfd76-112">SignalR のハブと接続ハンドラーは、<xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder> の <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> および <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> 拡張メソッドを使用して、<xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> 内で登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfd76-112">SignalR hubs and connection handlers should be registered within <xref:Microsoft.AspNetCore.Builder.EndpointRoutingApplicationBuilderExtensions.UseEndpoints%2A> using the <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A> and <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A> extension methods on <xref:Microsoft.AspNetCore.Routing.IEndpointRouteBuilder>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cfd76-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="cfd76-113">Reason for change</span></span>

<span data-ttu-id="cfd76-114">以前のメソッドには、ASP.NET Core の他のルーティング コンポーネントとやり取りしないカスタム ルーティング ロジックがありました。</span><span class="sxs-lookup"><span data-stu-id="cfd76-114">The old methods had custom routing logic that didn't interact with other routing components in ASP.NET Core.</span></span> <span data-ttu-id="cfd76-115">ASP.NET Core 3.0 では、エンドポイント ルーティングと呼ばれる新しい汎用ルーティング システムが導入されました。</span><span class="sxs-lookup"><span data-stu-id="cfd76-115">In ASP.NET Core 3.0, a new general-purpose routing system, called endpoint routing, was introduced.</span></span> <span data-ttu-id="cfd76-116">エンドポイント ルーティングにより、SignalR は他のルーティング コンポーネントとやり取りできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cfd76-116">Endpoint routing enabled SignalR to interact with other routing components.</span></span> <span data-ttu-id="cfd76-117">このモデルに切り替えることで、ユーザーはエンドポイント ルーティングの利点を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="cfd76-117">Switching to this model allows users to realize the full benefits of endpoint routing.</span></span> <span data-ttu-id="cfd76-118">そのため、古いメソッドは削除されています。</span><span class="sxs-lookup"><span data-stu-id="cfd76-118">Consequently, the old methods have been removed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cfd76-119">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="cfd76-119">Recommended action</span></span>

<span data-ttu-id="cfd76-120">プロジェクトの `Startup.Configure` メソッドから、`UseSignalR` または `UseConnections` を呼び出すコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="cfd76-120">Remove code that calls `UseSignalR` or `UseConnections` from your project's `Startup.Configure` method.</span></span> <span data-ttu-id="cfd76-121">それを、`UseEndpoints` の呼び出しの本体内で、それぞれ `MapHub` または `MapConnectionHandler` の呼び出しに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cfd76-121">Replace it with calls to `MapHub` or `MapConnectionHandler`, respectively, within the body of a call to `UseEndpoints`.</span></span> <span data-ttu-id="cfd76-122">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cfd76-122">For example:</span></span>

<span data-ttu-id="cfd76-123">**古いコード:**</span><span class="sxs-lookup"><span data-stu-id="cfd76-123">**Old code:**</span></span>

```csharp
app.UseSignalR(routes =>
{
    routes.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="cfd76-124">**新しいコード:**</span><span class="sxs-lookup"><span data-stu-id="cfd76-124">**New code:**</span></span>

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapHub<SomeHub>("/path");
});
```

<span data-ttu-id="cfd76-125">一般に、以前の `MapHub` および `MapConnectionHandler` の呼び出しは、ほとんどまたはまったく変更を行わずに、`UseSignalR` および `UseConnections` の本体から `UseEndpoints` に直接移すことができます。</span><span class="sxs-lookup"><span data-stu-id="cfd76-125">In general, your previous `MapHub` and `MapConnectionHandler` calls can be transferred directly from the body of `UseSignalR` and `UseConnections` to `UseEndpoints` with little-to-no change needed.</span></span>

#### <a name="category"></a><span data-ttu-id="cfd76-126">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cfd76-126">Category</span></span>

<span data-ttu-id="cfd76-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cfd76-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cfd76-128">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="cfd76-128">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.ConnectionsAppBuilderExtensions.UseConnections`
- `Overload:Microsoft.AspNetCore.Builder.SignalRAppBuilderExtensions.UseSignalR`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnections`
- `Overload:Microsoft.AspNetCore.Http.Connections.ConnectionsRouteBuilder.MapConnectionHandler`
- `Overload:Microsoft.AspNetCore.SignalR.HubRouteBuilder.MapHub`

-->
