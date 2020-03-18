---
ms.openlocfilehash: 494e792d63a611cdaedf3e40aa607cfbb0420ae4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901765"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="a3aee-101">認証:Newtonsoft.Json 型の置き換え</span><span class="sxs-lookup"><span data-stu-id="a3aee-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="a3aee-102">ASP.NET Core 3.0 では、Authentication API で使用される `Newtonsoft.Json` 型が `System.Text.Json` 型に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="a3aee-103">次の場合を除き、Authentication パッケージの基本的な使用方法は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="a3aee-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="a3aee-104">[aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers) のプロバイダーなど、OAuth プロバイダーから派生したクラス。</span><span class="sxs-lookup"><span data-stu-id="a3aee-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="a3aee-105">高度な要求操作の実装。</span><span class="sxs-lookup"><span data-stu-id="a3aee-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="a3aee-106">詳細については、[dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3aee-106">For more information, see [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105).</span></span> <span data-ttu-id="a3aee-107">ディスカッションについては、[dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3aee-107">For discussion, see [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a3aee-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a3aee-108">Version introduced</span></span>

<span data-ttu-id="a3aee-109">3.0</span><span class="sxs-lookup"><span data-stu-id="a3aee-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a3aee-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="a3aee-110">Recommended action</span></span>

<span data-ttu-id="a3aee-111">派生 OAuth 実装の場合、最も一般的な変更は、[こちら](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40)で示すように、`CreateTicketAsync` オーバーライドで `JObject.Parse` を `JsonDocument.Parse` に置き換えることです。</span><span class="sxs-lookup"><span data-stu-id="a3aee-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="a3aee-112">`JsonDocument` は、`IDisposable` を実装します。</span><span class="sxs-lookup"><span data-stu-id="a3aee-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="a3aee-113">既知の変更の概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a3aee-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="a3aee-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> は `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)` になります。</span><span class="sxs-lookup"><span data-stu-id="a3aee-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="a3aee-115">`ClaimAction` のすべての派生実装も同様に影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="a3aee-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="a3aee-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> は `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)` になります。</span><span class="sxs-lookup"><span data-stu-id="a3aee-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="a3aee-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> は `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)` になります。</span><span class="sxs-lookup"><span data-stu-id="a3aee-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="a3aee-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> では、古いコンストラクターの 1 つが削除され、もう 1 つのコンストラクターでは `JObject` が `JsonElement` に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="a3aee-119">これに合わせて、`User` プロパティと `RunClaimActions` メソッドが更新されました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="a3aee-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> は、`JObject` ではなく、`JsonDocument` 型のパラメーターを受け取るようになりました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="a3aee-121">これに合わせて `Response` プロパティが更新されました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="a3aee-122">`OAuthTokenResponse` が破棄可能になり、`OAuthHandler` によって破棄されます。</span><span class="sxs-lookup"><span data-stu-id="a3aee-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="a3aee-123">`ExchangeCodeAsync` をオーバーライドする派生 OAuth 実装では、`JsonDocument` または `OAuthTokenResponse` を破棄する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a3aee-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="a3aee-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> が `JObject` から `JsonDocument` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="a3aee-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> が `JObject` から `JsonElement` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="a3aee-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> が `JObject` の受け入れから `JsonElement` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="a3aee-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> changed from accepting `JObject` to `JsonElement`.</span></span>

#### <a name="category"></a><span data-ttu-id="a3aee-127">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a3aee-127">Category</span></span>

<span data-ttu-id="a3aee-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a3aee-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a3aee-129">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a3aee-129">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
