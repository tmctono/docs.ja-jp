---
ms.openlocfilehash: 74b989a2413d2192f7cf5208e400eaed879ea096
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198482"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="deb2d-101">Authorization:IAuthorizationPolicyProvider の実装には新しいメソッドが必要です</span><span class="sxs-lookup"><span data-stu-id="deb2d-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="deb2d-102">ASP.NET Core 3.0 では、`IAuthorizationPolicyProvider` に新しい `GetFallbackPolicyAsync` メソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="deb2d-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="deb2d-103">このフォールバック ポリシーは、ポリシーが指定されていない場合に、承認ミドルウェアによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="deb2d-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="deb2d-104">詳細については、[aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="deb2d-104">For more information, see [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="deb2d-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="deb2d-105">Version introduced</span></span>

<span data-ttu-id="deb2d-106">3.0</span><span class="sxs-lookup"><span data-stu-id="deb2d-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="deb2d-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="deb2d-107">Old behavior</span></span>

<span data-ttu-id="deb2d-108">`IAuthorizationPolicyProvider` の実装には、`GetFallbackPolicyAsync` メソッドは必要ありませんでした。</span><span class="sxs-lookup"><span data-stu-id="deb2d-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="deb2d-109">新しい動作</span><span class="sxs-lookup"><span data-stu-id="deb2d-109">New behavior</span></span>

<span data-ttu-id="deb2d-110">`IAuthorizationPolicyProvider` の実装には、`GetFallbackPolicyAsync` メソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="deb2d-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="deb2d-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="deb2d-111">Reason for change</span></span>

<span data-ttu-id="deb2d-112">ポリシーが指定されていない場合に新しい `AuthorizationMiddleware` を使用にするには、新しいメソッドが必要でした。</span><span class="sxs-lookup"><span data-stu-id="deb2d-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="deb2d-113">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="deb2d-113">Recommended action</span></span>

<span data-ttu-id="deb2d-114">`IAuthorizationPolicyProvider` の実装に `GetFallbackPolicyAsync` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="deb2d-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="deb2d-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="deb2d-115">Category</span></span>

<span data-ttu-id="deb2d-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="deb2d-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="deb2d-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="deb2d-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
