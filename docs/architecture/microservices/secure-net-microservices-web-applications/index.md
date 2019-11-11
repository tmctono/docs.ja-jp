---
title: NET マイクロサービスおよび Web アプリケーションをセキュリティで保護する
description: .NET マイクロサービスおよび Web アプリケーションのセキュリティ - ASP.NET Core Web アプリケーションの認証オプションをご確認ください。
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: b25f02140915ce87c5c478d8a8a5fe28ba7693b3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736955"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="8f368-103">NET マイクロサービスおよび Web アプリケーションをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="8f368-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="8f368-104">マイクロサービスと Web サービスのセキュリティに関するトピックはそれだけで何冊も本が書けるほど多岐にわたるため、このセクションでは、認証、認可、アプリケーション シークレットのみを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="8f368-104">There are so many aspects about security in microservices and web applications that the topic could easy take several books like this one so, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="8f368-105">.NET マイクロサービスおよび Web アプリケーションに認証を実装する</span><span class="sxs-lookup"><span data-stu-id="8f368-105">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="8f368-106">サービスによって発行されるリソースや API を特定の信頼されたユーザーやクライアントに制限しなければならないことはよくあります。</span><span class="sxs-lookup"><span data-stu-id="8f368-106">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="8f368-107">このような API レベルの信頼の決定を行うための最初の手順は、認証です。</span><span class="sxs-lookup"><span data-stu-id="8f368-107">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="8f368-108">認証は、ユーザーの ID を確実に検証するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="8f368-108">Authentication is the process of reliably verify a user’s identity.</span></span>

<span data-ttu-id="8f368-109">マイクロサービスのシナリオでは、通常、認証は一元的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-109">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="8f368-110">API ゲートウェイを使用している場合、図 9-1 に示すように、このゲートウェイから認証することができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-110">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="8f368-111">このアプローチを使用する場合は、メッセージがゲートウェイから来たかどうかに関わらず、メッセージの認証に追加のセキュリティ保護がない限り、(API ゲートウェイなしで) 個々のマイクロサービスに直接到達できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f368-111">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![クライアントのモバイル アプリがバックエンドとやりとりする方法を示した図。](./media/index/api-gateway-centralized-authentication.png)

<span data-ttu-id="8f368-113">**図 9-1**</span><span class="sxs-lookup"><span data-stu-id="8f368-113">**Figure 9-1**.</span></span> <span data-ttu-id="8f368-114">API ゲートウェイによる認証の一元管理</span><span class="sxs-lookup"><span data-stu-id="8f368-114">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="8f368-115">API ゲートウェイで認証が一元化されている場合に要求がマイクロサービスに転送されると、ユーザー情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-115">When the API Gateway centralizes authentication, it adds user information when forwarding requests to the microservices.</span></span> <span data-ttu-id="8f368-116">サービスに直接アクセスできる場合は、Azure Active Directory などの認証サービスやセキュリティ トークン サービス (STS) として機能する専用の認証マイクロサービスは、ユーザーを認証するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f368-116">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="8f368-117">信頼の決定は、サービスとセキュリティ トークンまたは cookie 間で共有されます</span><span class="sxs-lookup"><span data-stu-id="8f368-117">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="8f368-118">(必要に応じて、これらのトークンは、[Cookie の共有](/aspnet/core/security/cookie-sharing)を実装して、ASP.NET Core アプリケーション間で共有できます)。このパターンを示したものが図 9-2 です。</span><span class="sxs-lookup"><span data-stu-id="8f368-118">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![バックエンドのマイクロサービスを介した認証を示す図。](./media/index/identity-microservice-authentication.png)

<span data-ttu-id="8f368-120">**図 9-2**</span><span class="sxs-lookup"><span data-stu-id="8f368-120">**Figure 9-2**.</span></span> <span data-ttu-id="8f368-121">ID マイクロサービスによる認証、信頼は認証トークンを使用して共有</span><span class="sxs-lookup"><span data-stu-id="8f368-121">Authentication by identity microservice; trust is shared using an authorization token</span></span>

<span data-ttu-id="8f368-122">マイクロ サービスに直接アクセスすると、認証と認可を含む信頼が、マイクロサービス間で共有される専用のマイクロサービスによって発行されたセキュリティ トークンによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-122">When microservices are accessed directly, trust, that includes authentication and authorization, is handled by a security token issued by a dedicated microservice, shared between microservices.</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="8f368-123">ASP.NET Core Identity を使用して認証する</span><span class="sxs-lookup"><span data-stu-id="8f368-123">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="8f368-124">アプリケーションのユーザーを識別するための ASP.NET Core の主要なメカニズムは、[ASP.NET Core Identity](/aspnet/core/security/authentication/identity) メンバーシップ システムです。</span><span class="sxs-lookup"><span data-stu-id="8f368-124">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="8f368-125">ASP.NET Core Identity は、ユーザー情報 (サインイン情報、ロール、およびクレームを含む) を開発者によって構成されたデータ ストアに格納します。</span><span class="sxs-lookup"><span data-stu-id="8f368-125">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="8f368-126">通常、ASP.NET Core Identity データ ストアは、`Microsoft.AspNetCore.Identity.EntityFrameworkCore` パッケージで提供される Entity Framework ストアです。</span><span class="sxs-lookup"><span data-stu-id="8f368-126">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="8f368-127">ただし、カスタム ストアまたはその他のサード パーティのパッケージを使用して、ID 情報を Azure Table Storage、CosmosDB、またはその他の場所に格納することができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-127">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

<span data-ttu-id="8f368-128">次のコードは、個々のユーザー アカウントの認証が選択された ASP.NET Core Web アプリケーション プロジェクト テンプレートから取得されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-128">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="8f368-129">これは Startup.ConfigureServices メソッドで EntityFramework.Core を使用して ASP.NET Core Identity を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f368-129">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="8f368-130">ASP.NET Core Identity が構成されたら、サービスの `Startup.Configure` メソッドで app.UseIdentity を呼び出して有効にします。</span><span class="sxs-lookup"><span data-stu-id="8f368-130">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s `Startup.Configure` method.</span></span>

<span data-ttu-id="8f368-131">ASP.NET Core Identity を使用すると、次の複数のシナリオが実現できます。</span><span class="sxs-lookup"><span data-stu-id="8f368-131">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="8f368-132">UserManager 型 (userManager.CreateAsync) を使用して、新しいユーザー情報を作成する。</span><span class="sxs-lookup"><span data-stu-id="8f368-132">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="8f368-133">SignInManager 型を使用してユーザーを認証する。</span><span class="sxs-lookup"><span data-stu-id="8f368-133">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="8f368-134">`signInManager.SignInAsync` を使用して直接サインインするか、`signInManager.PasswordSignInAsync` を使用してユーザーのパスワードが正しいことを確認し、そのユーザーでサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-134">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user’s password is correct and then sign them in.</span></span>

- <span data-ttu-id="8f368-135">ブラウザーからの後続の要求にサインイン ユーザーの ID とクレームが含まれるように、cookie に格納されている情報 (ASP.NET Core Identity ミドルウェアで読み取られます) に基づいてユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="8f368-135">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="8f368-136">ASP.NET Core Identity は [2 要素認証](/aspnet/core/security/authentication/2fa)もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8f368-136">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="8f368-137">ローカル ユーザーのデータ ストアを利用する認証シナリオや、cookie を使用して要求間で ID を保持する認証シナリオ (MVC web アプリケーションでは一般的) では、ASP.NET Core Identity が推奨されるソリューションです。</span><span class="sxs-lookup"><span data-stu-id="8f368-137">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="8f368-138">外部プロバイダーを使用して認証する</span><span class="sxs-lookup"><span data-stu-id="8f368-138">Authenticate with external providers</span></span>

<span data-ttu-id="8f368-139">ASP.NET Core は、ユーザーが [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) フローを経由してサインインできるように、[外部認証プロバイダー](/aspnet/core/security/authentication/social/)の使用もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8f368-139">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="8f368-140">つまり、ユーザーは Microsoft、Google、Facebook、Twitter などのプロバイダーの既存の認証プロセスを使用してサインインし、アプリケーションでこれらの ID を ASP.NET Core Identity に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-140">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="8f368-141">外部認証を使用するには、アプリケーションの HTTP 要求処理パイプラインに適切な認証ミドルウェアを含めます。</span><span class="sxs-lookup"><span data-stu-id="8f368-141">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="8f368-142">このミドルウェアは、認証プロバイダーから URI ルートを返すために要求を処理し、ID 情報をキャプチャし、SignInManager.GetExternalLoginInfo メソッドを介して使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8f368-142">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="8f368-143">よく利用されている外部認証プロバイダーと、関連付けられている NuGet パッケージを以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="8f368-143">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="8f368-144">**プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="8f368-144">**Provider**</span></span>  | <span data-ttu-id="8f368-145">**パッケージ**</span><span class="sxs-lookup"><span data-stu-id="8f368-145">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="8f368-146">**Microsoft**</span><span class="sxs-lookup"><span data-stu-id="8f368-146">**Microsoft**</span></span> | <span data-ttu-id="8f368-147">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="8f368-147">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="8f368-148">**Google**</span><span class="sxs-lookup"><span data-stu-id="8f368-148">**Google**</span></span>    | <span data-ttu-id="8f368-149">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="8f368-149">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="8f368-150">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="8f368-150">**Facebook**</span></span>  | <span data-ttu-id="8f368-151">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="8f368-151">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="8f368-152">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="8f368-152">**Twitter**</span></span>   | <span data-ttu-id="8f368-153">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="8f368-153">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="8f368-154">すべての場合で、`Startup.Configure` の `app.Use{ExternalProvider}Authentication` と同様の、登録メソッドの呼び出しによってミドルウェアが登録されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-154">In all cases, the middleware is registered with a call to a registration method similar to `app.Use{ExternalProvider}Authentication` in `Startup.Configure`.</span></span> <span data-ttu-id="8f368-155">これらの登録メソッドは、プロバイダーが必要とするアプリケーション ID と機密情報 (パスワードなど) を含むオプション オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8f368-155">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="8f368-156">外部認証プロバイダーは、([ASP.NET Core のドキュメントで説明されているように](/aspnet/core/security/authentication/social/)) ユーザーに ID へのアクセスを求めているアプリケーションを通知するため、アプリケーションの登録を求めます。</span><span class="sxs-lookup"><span data-stu-id="8f368-156">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="8f368-157">ミドルウェアが `Startup.Configure` で登録されると、ユーザーに任意のコントローラー アクションからサインインを求めることができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-157">Once the middleware is registered in `Startup.Configure`, you can prompt users to sign in from any controller action.</span></span> <span data-ttu-id="8f368-158">これを行うには、認証プロバイダー名とリダイレクト URL を含む `AuthenticationProperties` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f368-158">To do this, you create an `AuthenticationProperties` object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="8f368-159">そして、`AuthenticationProperties` オブジェクトを渡すチャレンジ応答を返します。</span><span class="sxs-lookup"><span data-stu-id="8f368-159">You then return a Challenge response that passes the `AuthenticationProperties` object.</span></span> <span data-ttu-id="8f368-160">この例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="8f368-160">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="8f368-161">redirectUrl パラメーターには、ユーザーが認証された後に外部プロバイダーがリダイレクトされる URL が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8f368-161">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="8f368-162">URL は、次の簡素化した例のように、外部の ID 情報に基づいてユーザーをサインインさせるアクションを表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f368-162">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

<span data-ttu-id="8f368-163">Visual Studio で ASP.NET コードの Web アプリケーション プロジェクトを作成するときに、 **[個人のユーザー アカウント]** 認証オプションを選択すると、図 9-3 に示すように、外部プロバイダーでサインインするために必要なすべてのコードがすでにプロジェクト内にあります。</span><span class="sxs-lookup"><span data-stu-id="8f368-163">If you choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 9-3.</span></span>

![[新しい ASP.NET Core Web アプリケーション] ダイアログのスクリーンショット。](./media/index/select-external-authentication-option.png)

<span data-ttu-id="8f368-165">**図 9-3**</span><span class="sxs-lookup"><span data-stu-id="8f368-165">**Figure 9-3**.</span></span> <span data-ttu-id="8f368-166">Web アプリケーション プロジェクトを作成するときに、外部の認証を使用するためのオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="8f368-166">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="8f368-167">より多くの外部認証プロバイダーを使用するため、上記で一覧表示した外部の認証プロバイダーの他に、ミドルウェアを提供するサード パーティのパッケージが使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f368-167">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="8f368-168">リストについては、GitHub で [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) のリポジトリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f368-168">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="8f368-169">いくつかの特別なニーズを解決するために、独自の外部認証ミドルウェアを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f368-169">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="8f368-170">ベアラー トークンで認証する</span><span class="sxs-lookup"><span data-stu-id="8f368-170">Authenticate with bearer tokens</span></span>

<span data-ttu-id="8f368-171">ASP.NET Core Identity (または Identity と外部認証プロバイダー) を使用した認証は、ユーザー情報を cookie に格納する多くの Web アプリケーションのシナリオに適してします。</span><span class="sxs-lookup"><span data-stu-id="8f368-171">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="8f368-172">しかし、それ以外のシナリオでは、cookie はデータを保持および送信する通常の方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="8f368-172">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="8f368-173">たとえば、Single Page Application (SPA)、ネイティブ クライアント、または他の Web API によってアクセスできる RESTful エンドポイントを公開する ASP.NET Core Web API では、代わりにベアラー トークン認証を使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="8f368-173">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="8f368-174">この種のアプリケーションでは cookie を使用しませんが、簡単にベアラー トークンを取得してそれを後続の要求の承認ヘッダーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-174">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="8f368-175">トークン認証を有効にするため、ASP.NET Core は [OAuth 2.0](https://oauth.net/2/) および [OpenID Connect](https://openid.net/connect/) を使用するための複数のオプションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8f368-175">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="8f368-176">OpenID Connect または OAuth 2.0 ID プロバイダーで認証する</span><span class="sxs-lookup"><span data-stu-id="8f368-176">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="8f368-177">ユーザー情報が Azure Active Directory または OpenID Connect または OAuth 2.0 をサポートする別の ID ソリューションに格納されている場合は、**Microsoft.AspNetCore.Authentication.OpenIdConnect** パッケージを使用して、OpenID Connect ワークフローの使用を認証することができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-177">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="8f368-178">たとえば、eShopOnContainers の Identity.Api マイクロサービスを認証するには、次の `Startup.cs` の簡易的な例に示すように、ASP.NET Core Web アプリケーションが、そのパッケージのミドルウェアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f368-178">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = OpenIdConnectDefaults.AuthenticationScheme;
    })
    .AddCookie()
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl;
        options.SignedOutRedirectUri = callBackUrl;
        options.ClientSecret = "secret";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

<span data-ttu-id="8f368-179">このワークフローを使用すると、すべてのユーザー情報ストレージと認証が ID サービスによって処理されるため、ASP.NET Core Identity ミドルウェアは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8f368-179">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="8f368-180">ASP.NET Core サービスからセキュリティ トークンを発行する</span><span class="sxs-lookup"><span data-stu-id="8f368-180">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="8f368-181">外部 ID プロバイダーを使用するよりも、ローカルの ASP.NET Core Identity ユーザーにセキュリティ トークンを発行する場合は、優れたサード パーティ ライブラリを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-181">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="8f368-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) と [OpenIddict](https://github.com/openiddict/openiddict-core) は、ASP.NET Core Identity と簡単に統合して ASP.NET Core サービスからセキュリティ トークンを発行できるようにする OpenID Connect プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="8f368-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="8f368-183">[IdentityServer4 ドキュメント](https://identityserver4.readthedocs.io/en/latest/)には、ライブラリの詳しい使用方法が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8f368-183">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="8f368-184">ただし、IdentityServer4 を使用してトークンを発行する基本的な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f368-184">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="8f368-185">Startup.Configure メソッドで app.UseIdentityServer を呼び出して、IdentityServer4 をアプリケーションの HTTP 要求処理パイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="8f368-185">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="8f368-186">これにより、ライブラリが /connect/token などの OpenID Connect エンドポイントと OAuth2 エンドポイントに要求を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-186">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="8f368-187">services.AddIdentityServer を呼び出して、Startup.ConfigureServices で IdentityServer4 を構成します。</span><span class="sxs-lookup"><span data-stu-id="8f368-187">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="8f368-188">ID サーバーを構成するには、次のデータを設定します。</span><span class="sxs-lookup"><span data-stu-id="8f368-188">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="8f368-189">署名に使用する[資格情報](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html)。</span><span class="sxs-lookup"><span data-stu-id="8f368-189">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="8f368-190">ユーザーがアクセスを要求する可能性がある [ID と API リソース](https://identityserver4.readthedocs.io/en/latest/topics/resources.html)。</span><span class="sxs-lookup"><span data-stu-id="8f368-190">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="8f368-191">API リソースは、保護されたデータまたはユーザーがアクセス トークンを使用してアクセスできる機能を表します。</span><span class="sxs-lookup"><span data-stu-id="8f368-191">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="8f368-192">認証を必要とする Web API (または API のセット) は、API リソースの一例です。</span><span class="sxs-lookup"><span data-stu-id="8f368-192">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="8f368-193">ID リソースは、ユーザーを識別するためにクライアントに与えられる情報 (クレーム) を表します。</span><span class="sxs-lookup"><span data-stu-id="8f368-193">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="8f368-194">クレームには、ユーザー名、メール アドレスなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f368-194">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="8f368-195">トークンを要求するために接続する[クライアント](https://identityserver4.readthedocs.io/en/latest/topics/clients.html)。</span><span class="sxs-lookup"><span data-stu-id="8f368-195">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="8f368-196">[ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) または代替手段など、ユーザー情報のためのストレージ メカニズム。</span><span class="sxs-lookup"><span data-stu-id="8f368-196">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="8f368-197">使用する IdentityServer4 のクライアントとリソースを指定するときに、適切な型の <xref:System.Collections.Generic.IEnumerable%601> コレクションをメモリ内のクライアントまたはリソースのストアを受け取るメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-197">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="8f368-198">またはより複雑なシナリオでは、依存関係の挿入を通じて、クライアントまたはリソース プロバイダーの型を提供できます。</span><span class="sxs-lookup"><span data-stu-id="8f368-198">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="8f368-199">カスタム IClientStore 型によって渡されるメモリ内のリソースおよびクライアントを使用する IdentityServer4 のサンプル構成は、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="8f368-199">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a><span data-ttu-id="8f368-200">セキュリティ トークンを使用する</span><span class="sxs-lookup"><span data-stu-id="8f368-200">Consume security tokens</span></span>

<span data-ttu-id="8f368-201">OpenID Connect エンドポイントに対して認証する、または独自のセキュリティ トークンを発行することで、いくつかのシナリオをカバーすることはできます。</span><span class="sxs-lookup"><span data-stu-id="8f368-201">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="8f368-202">しかし、異なるサービスで提供された有効なセキュリティ トークンを持つユーザーにアクセスを制限する必要があるサービスの場合はどうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="8f368-202">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="8f368-203">そのシナリオでは、JWT トークンを処理する認証ミドルウェアが **Microsoft.AspNetCore.Authentication.JwtBearer** パッケージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f368-203">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="8f368-204">JWT は "[JSON Web トークン](https://tools.ietf.org/html/rfc7519)" を表し、セキュリティ クレームの通信のための一般的なセキュリティ トークン形式 (RFC 7519 で定義) です。</span><span class="sxs-lookup"><span data-stu-id="8f368-204">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="8f368-205">ミドルウェアを使用してそのようなトークンを使用する方法を簡単に示すと、eShopOnContainers の Ordering.Api マイクロサービスから取得されたこのコードのようになります。</span><span class="sxs-lookup"><span data-stu-id="8f368-205">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="8f368-206">この使用法でのパラメーターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f368-206">The parameters in this usage are:</span></span>

- <span data-ttu-id="8f368-207">`Audience` は、受信トークンの受信者またはそのトークンでアクセスできるリソースを表します。</span><span class="sxs-lookup"><span data-stu-id="8f368-207">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="8f368-208">このパラメーターで指定された値がトークン内のパラメーターと一致しない場合、そのトークンは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-208">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="8f368-209">`Authority` は、トークン発行認証サーバーのアドレスです。</span><span class="sxs-lookup"><span data-stu-id="8f368-209">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="8f368-210">JWT ベアラー認証ミドルウェアでは、この URI を使用して、トークンの署名の検証に使用できる公開キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="8f368-210">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="8f368-211">ミドルウェアは、トークン内の `iss` パラメーターがこの URI と一致していることも確認します。</span><span class="sxs-lookup"><span data-stu-id="8f368-211">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="8f368-212">もう 1 つのパラメーター `RequireHttpsMetadata` はテスト目的に便利です。証明書がない環境でテストができるように、このパラメーターを false に設定します。</span><span class="sxs-lookup"><span data-stu-id="8f368-212">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="8f368-213">実際の展開では、JWT ベアラー トークンは常に HTTPS 経由でのみ渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f368-213">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="8f368-214">このミドルウェアを配置すると、JWT トークンが承認ヘッダーから自動的に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-214">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="8f368-215">これらのトークンは、逆シリアル化され、(`Audience` パラメーターと `Authority` パラメーターの値を使用して) 検証され、MVC アクションまたは認証フィルターが後で参照するユーザー情報として格納されます。</span><span class="sxs-lookup"><span data-stu-id="8f368-215">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="8f368-216">JWT ベアラー認証ミドルウェアは、証明機関が利用できない場合に、ローカルの証明書を使用してトークンを検証するなどの高度なシナリオもサポートできます。</span><span class="sxs-lookup"><span data-stu-id="8f368-216">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="8f368-217">このシナリオでは、`JwtBearerOptions` オブジェクトの `TokenValidationParameters` を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8f368-217">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f368-218">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8f368-218">Additional resources</span></span>

- <span data-ttu-id="8f368-219">**アプリケーション間での Cookie の共有** </span><span class="sxs-lookup"><span data-stu-id="8f368-219">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="8f368-220">**Identity の概要** </span><span class="sxs-lookup"><span data-stu-id="8f368-220">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="8f368-221">**Rick Anderson の SMS での 2 要素認証** </span><span class="sxs-lookup"><span data-stu-id="8f368-221">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="8f368-222">**Facebook、Google、および他の外部プロバイダーを使用する認証の有効化** </span><span class="sxs-lookup"><span data-stu-id="8f368-222">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="8f368-223">**Michell Anicas の OAuth 2 の概要** </span><span class="sxs-lookup"><span data-stu-id="8f368-223">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="8f368-224">**AspNet.Security.OAuth.Providers** (ASP.NET OAuth プロバイダーの GitHub リポジトリ) </span><span class="sxs-lookup"><span data-stu-id="8f368-224">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="8f368-225">**IdentityServer4 の公式ドキュメント** </span><span class="sxs-lookup"><span data-stu-id="8f368-225">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="8f368-226">[前へ](../implement-resilient-applications/monitor-app-health.md)
>[次へ](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="8f368-226">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
