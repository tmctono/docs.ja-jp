---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901699"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="605f4-101">承認:IAuthorizationPolicyProvider の実装には新しいメソッドが必要です</span><span class="sxs-lookup"><span data-stu-id="605f4-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="605f4-102">ASP.NET Core 3.0 では、`IAuthorizationPolicyProvider` に新しい `GetFallbackPolicyAsync` メソッドが追加されました。</span><span class="sxs-lookup"><span data-stu-id="605f4-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="605f4-103">このフォールバック ポリシーは、ポリシーが指定されていない場合に、承認ミドルウェアによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="605f4-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="605f4-104">詳細については、[dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="605f4-104">For more information, see [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="605f4-105">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="605f4-105">Version introduced</span></span>

<span data-ttu-id="605f4-106">3.0</span><span class="sxs-lookup"><span data-stu-id="605f4-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="605f4-107">以前の動作</span><span class="sxs-lookup"><span data-stu-id="605f4-107">Old behavior</span></span>

<span data-ttu-id="605f4-108">`IAuthorizationPolicyProvider` の実装には、`GetFallbackPolicyAsync` メソッドは必要ありませんでした。</span><span class="sxs-lookup"><span data-stu-id="605f4-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="605f4-109">新しい動作</span><span class="sxs-lookup"><span data-stu-id="605f4-109">New behavior</span></span>

<span data-ttu-id="605f4-110">`IAuthorizationPolicyProvider` の実装には、`GetFallbackPolicyAsync` メソッドが必要です。</span><span class="sxs-lookup"><span data-stu-id="605f4-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="605f4-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="605f4-111">Reason for change</span></span>

<span data-ttu-id="605f4-112">ポリシーが指定されていない場合に新しい `AuthorizationMiddleware` を使用にするには、新しいメソッドが必要でした。</span><span class="sxs-lookup"><span data-stu-id="605f4-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="605f4-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="605f4-113">Recommended action</span></span>

<span data-ttu-id="605f4-114">`IAuthorizationPolicyProvider` の実装に `GetFallbackPolicyAsync` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="605f4-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="605f4-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="605f4-115">Category</span></span>

<span data-ttu-id="605f4-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="605f4-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="605f4-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="605f4-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
