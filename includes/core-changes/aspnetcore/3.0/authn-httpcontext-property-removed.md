---
ms.openlocfilehash: 2945465bb6a3a362dc640641056712dffd73d559
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394260"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="7620b-101">認証: HttpContext.Authentication プロパティが削除されました</span><span class="sxs-lookup"><span data-stu-id="7620b-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="7620b-102">`HttpContext` の非推奨の `Authentication` プロパティが削除されました。</span><span class="sxs-lookup"><span data-stu-id="7620b-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7620b-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="7620b-103">Change description</span></span>

<span data-ttu-id="7620b-104">[aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504) の一部として、`HttpContext` の非推奨の `Authentication` プロパティが削除されました。</span><span class="sxs-lookup"><span data-stu-id="7620b-104">As part of [aspnet/AspNetCore#6504](https://github.com/aspnet/AspNetCore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="7620b-105">2\.0 以降、`Authentication` プロパティは非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="7620b-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="7620b-106">この非推奨のプロパティを使用して新しい置換 API にコードを移行するために、[移行ガイド](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)が発行されました。</span><span class="sxs-lookup"><span data-stu-id="7620b-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="7620b-107">古い ASP.NET Core 1.x 認証スタックに関連する残りの未使用のクラス/API が、コミット [aspnet/AspNetCore@d7a7c65](https://github.com/aspnet/AspNetCore/commit/d7a7c65) で削除されました。</span><span class="sxs-lookup"><span data-stu-id="7620b-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [aspnet/AspNetCore@d7a7c65](https://github.com/aspnet/AspNetCore/commit/d7a7c65).</span></span>

<span data-ttu-id="7620b-108">詳細については、[aspnet/AspNetCore#6533](https://github.com/aspnet/AspNetCore/issues/6533) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7620b-108">For discussion, see [aspnet/AspNetCore#6533](https://github.com/aspnet/AspNetCore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7620b-109">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="7620b-109">Version introduced</span></span>

<span data-ttu-id="7620b-110">3.0</span><span class="sxs-lookup"><span data-stu-id="7620b-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7620b-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="7620b-111">Reason for change</span></span>

<span data-ttu-id="7620b-112">ASP.NET Core 1.0 API が <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName> の拡張メソッドに置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="7620b-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7620b-113">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="7620b-113">Recommended action</span></span>

<span data-ttu-id="7620b-114">[移行ガイド](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7620b-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="7620b-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="7620b-115">Category</span></span>

<span data-ttu-id="7620b-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7620b-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7620b-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="7620b-117">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
