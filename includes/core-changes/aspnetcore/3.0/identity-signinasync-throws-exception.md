---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394355"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a><span data-ttu-id="339ab-101">ID:SignInAsync が認証されていない ID に対して例外をスロー</span><span class="sxs-lookup"><span data-stu-id="339ab-101">Identity: SignInAsync throws exception for unauthenticated identity</span></span>

<span data-ttu-id="339ab-102">既定では、`SignInAsync` は、`IsAuthenticated` が `false` であるプリンシパル/ID に対して例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="339ab-102">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="339ab-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="339ab-103">Version introduced</span></span>

<span data-ttu-id="339ab-104">3.0</span><span class="sxs-lookup"><span data-stu-id="339ab-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="339ab-105">以前の動作</span><span class="sxs-lookup"><span data-stu-id="339ab-105">Old behavior</span></span>

<span data-ttu-id="339ab-106">`SignInAsync` は、`IsAuthenticated` が `false` である ID も含め、すべてのプリンシパル/ID を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="339ab-106">`SignInAsync` accepts any principals / identities, including identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="339ab-107">新しい動作</span><span class="sxs-lookup"><span data-stu-id="339ab-107">New behavior</span></span>

<span data-ttu-id="339ab-108">既定では、`SignInAsync` は、`IsAuthenticated` が `false` であるプリンシパル/ID に対して例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="339ab-108">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span> <span data-ttu-id="339ab-109">この動作を抑制する新しいフラグがありますが、既定の動作が変更されました。</span><span class="sxs-lookup"><span data-stu-id="339ab-109">There's a new flag to suppress this behavior, but the default behavior has changed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="339ab-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="339ab-110">Reason for change</span></span>

<span data-ttu-id="339ab-111">既定では、これらのプリンシパルは `[Authorize]` / `RequireAuthenticatedUser()` によって拒否されていたため、以前の動作には問題がありました。</span><span class="sxs-lookup"><span data-stu-id="339ab-111">The old behavior was problematic because, by default, these principals were rejected by `[Authorize]` / `RequireAuthenticatedUser()`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="339ab-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="339ab-112">Recommended action</span></span>

<span data-ttu-id="339ab-113">ASP.NET Core 3.0 Preview 6 では、`AuthenticationOptions` の `RequireAuthenticatedSignIn` フラグが既定で `true` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="339ab-113">In ASP.NET Core 3.0 Preview 6, there's a `RequireAuthenticatedSignIn` flag on `AuthenticationOptions` that is `true` by default.</span></span> <span data-ttu-id="339ab-114">以前の動作を復元するには、このフラグを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="339ab-114">Set this flag to `false` to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="339ab-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="339ab-115">Category</span></span>

<span data-ttu-id="339ab-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="339ab-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="339ab-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="339ab-117">Affected APIs</span></span>

<span data-ttu-id="339ab-118">None</span><span class="sxs-lookup"><span data-stu-id="339ab-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
