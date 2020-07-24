---
ms.openlocfilehash: 2b88ab7cfdd7a0a0a770b305ecd0200afd9a9b4b
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441552"
---
### <a name="authorization-resource-in-endpoint-routing-is-httpcontext"></a><span data-ttu-id="4b60f-101">承認:エンドポイント ルーティングのリソースは HttpContext</span><span class="sxs-lookup"><span data-stu-id="4b60f-101">Authorization: Resource in endpoint routing is HttpContext</span></span>

<span data-ttu-id="4b60f-102">ASP.NET Core 3.1 でエンドポイント ルーティングを使用する場合、承認に使用されるリソースはエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="4b60f-102">When using endpoint routing in ASP.NET Core 3.1, the resource used for authorization is the endpoint.</span></span> <span data-ttu-id="4b60f-103">この方法は、ルート データ (<xref:Microsoft.AspNetCore.Routing.RouteData>) へのアクセスを付与するためには不十分でした。</span><span class="sxs-lookup"><span data-stu-id="4b60f-103">This approach was insufficient for gaining access to the route data (<xref:Microsoft.AspNetCore.Routing.RouteData>).</span></span> <span data-ttu-id="4b60f-104">MVC では以前、エンドポイント (<xref:Microsoft.AspNetCore.Http.Endpoint>) とルート データの両方にアクセスできるようにするため、<xref:Microsoft.AspNetCore.Http.HttpContext> リソースが渡されました。</span><span class="sxs-lookup"><span data-stu-id="4b60f-104">Previously in MVC, an <xref:Microsoft.AspNetCore.Http.HttpContext> resource was passed in, which allows access to both the endpoint (<xref:Microsoft.AspNetCore.Http.Endpoint>) and the route data.</span></span> <span data-ttu-id="4b60f-105">この変更により、承認に渡されるリソースは常に `HttpContext` になります。</span><span class="sxs-lookup"><span data-stu-id="4b60f-105">This change ensures that the resource passed to authorization is always the `HttpContext`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4b60f-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="4b60f-106">Version introduced</span></span>

<span data-ttu-id="4b60f-107">5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="4b60f-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4b60f-108">以前の動作</span><span class="sxs-lookup"><span data-stu-id="4b60f-108">Old behavior</span></span>

<span data-ttu-id="4b60f-109">エンドポイント ルーティングと承認ミドルウェア (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) または [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) 属性を使用する場合、承認に渡されるリソースは一致するエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="4b60f-109">When using endpoint routing and the authorization middleware (<xref:Microsoft.AspNetCore.Authorization.AuthorizationMiddleware>) or [[Authorize]](xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute) attributes, the resource passed to authorization is the matching endpoint.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4b60f-110">新しい動作</span><span class="sxs-lookup"><span data-stu-id="4b60f-110">New behavior</span></span>

<span data-ttu-id="4b60f-111">`HttpContext` がエンドポイント ルーティングから承認に渡されます。</span><span class="sxs-lookup"><span data-stu-id="4b60f-111">Endpoint routing passes the `HttpContext` to authorization.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4b60f-112">変更理由</span><span class="sxs-lookup"><span data-stu-id="4b60f-112">Reason for change</span></span>

<span data-ttu-id="4b60f-113">`HttpContext` からエンドポイントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4b60f-113">You can get to the endpoint from the `HttpContext`.</span></span> <span data-ttu-id="4b60f-114">一方で、エンドポイントからルート データなどにアクセスする方法はありませんでした。</span><span class="sxs-lookup"><span data-stu-id="4b60f-114">However, there was no way to get from the endpoint to things like the route data.</span></span> <span data-ttu-id="4b60f-115">エンドポイント以外のルーティングからの機能に不足がありました。</span><span class="sxs-lookup"><span data-stu-id="4b60f-115">There was a loss in functionality from non-endpoint routing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4b60f-116">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="4b60f-116">Recommended action</span></span>

<span data-ttu-id="4b60f-117">アプリでエンドポイント リソースが使用される場合は、`HttpContext` で <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> を呼び出して、エンドポイントへのアクセスを継続します。</span><span class="sxs-lookup"><span data-stu-id="4b60f-117">If your app uses the endpoint resource, call <xref:Microsoft.AspNetCore.Http.EndpointHttpContextExtensions.GetEndpoint%2A> on the `HttpContext` to continue accessing the endpoint.</span></span>

<span data-ttu-id="4b60f-118">ASP.NET Core 5.0 Preview 8 以降では、<xref:System.AppContext.SetSwitch%2A> を使用して以前の動作に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="4b60f-118">In ASP.NET Core 5.0 Preview 8 and later, you can revert to the old behavior with <xref:System.AppContext.SetSwitch%2A>.</span></span> <span data-ttu-id="4b60f-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4b60f-119">For example:</span></span>

```csharp
AppContext.SetSwitch(
    "Microsoft.AspNetCore.Authorization.SuppressUseHttpContextAsAuthorizationResource",
    isEnabled: true);
```

#### <a name="category"></a><span data-ttu-id="4b60f-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="4b60f-120">Category</span></span>

<span data-ttu-id="4b60f-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4b60f-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4b60f-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="4b60f-122">Affected APIs</span></span>

<span data-ttu-id="4b60f-123">None</span><span class="sxs-lookup"><span data-stu-id="4b60f-123">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
