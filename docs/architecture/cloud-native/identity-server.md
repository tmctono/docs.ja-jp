---
title: クラウドネイティブアプリ用のサーバー
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |IdentityServer
ms.date: 05/13/2020
ms.openlocfilehash: 81cce30568becacda29f65f9506398790af321e0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614033"
---
# <a name="identityserver-for-cloud-native-applications"></a><span data-ttu-id="1c58b-103">クラウドネイティブアプリケーション用のサーバー</span><span class="sxs-lookup"><span data-stu-id="1c58b-103">IdentityServer for cloud-native applications</span></span>

<span data-ttu-id="1c58b-104">サービスは、OpenID Connect (OIDC) と OAuth 2.0 標準を実装するオープンソースの認証サーバーで、ASP.NET Core に使用します。</span><span class="sxs-lookup"><span data-stu-id="1c58b-104">IdentityServer is an open-source authentication server that implements OpenID Connect (OIDC) and OAuth 2.0 standards for ASP.NET Core.</span></span> <span data-ttu-id="1c58b-105">これは、web、ネイティブ、モバイル、API のいずれのエンドポイントであるかにかかわらず、すべてのアプリケーションに対する要求を認証するための一般的な方法を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1c58b-105">It's designed to provide a common way to authenticate requests to all of your applications, whether they're web, native, mobile, or API endpoints.</span></span> <span data-ttu-id="1c58b-106">サーバーを使用して、複数のアプリケーションとアプリケーションの種類にシングルサインオン (SSO) を実装できます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-106">IdentityServer can be used to implement Single Sign-On (SSO) for multiple applications and application types.</span></span> <span data-ttu-id="1c58b-107">サインインフォームや同様のユーザーインターフェイスを使用して実際のユーザーを認証するために使用できます。また、通常は、ユーザーインターフェイスなしでトークンの発行、検証、更新を含むサービスベースの認証も行います。</span><span class="sxs-lookup"><span data-stu-id="1c58b-107">It can be used to authenticate actual users via sign-in forms and similar user interfaces as well as service-based authentication that typically involves token issuance, verification, and renewal without any user interface.</span></span> <span data-ttu-id="1c58b-108">サービスはカスタマイズ可能なソリューションとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="1c58b-108">IdentityServer is designed to be a customizable solution.</span></span> <span data-ttu-id="1c58b-109">各インスタンスは、通常、個々の組織やアプリケーションのニーズに合わせてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-109">Each instance is typically customized to suit an individual organization and/or set of applications' needs.</span></span>

## <a name="common-web-app-scenarios"></a><span data-ttu-id="1c58b-110">一般的な web アプリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="1c58b-110">Common web app scenarios</span></span>

<span data-ttu-id="1c58b-111">通常、アプリケーションでは、次のシナリオの一部またはすべてをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c58b-111">Typically, applications need to support some or all of the following scenarios:</span></span>

- <span data-ttu-id="1c58b-112">ブラウザーを使用して web アプリケーションにアクセスする人のユーザー。</span><span class="sxs-lookup"><span data-stu-id="1c58b-112">Human users accessing web applications with a browser.</span></span>
- <span data-ttu-id="1c58b-113">ブラウザーベースのアプリからバックエンド Web Api にアクセスする人のユーザー。</span><span class="sxs-lookup"><span data-stu-id="1c58b-113">Human users accessing back-end Web APIs from browser-based apps.</span></span>
- <span data-ttu-id="1c58b-114">バックエンド Web Api にアクセスするモバイル/ネイティブクライアントの人のユーザー。</span><span class="sxs-lookup"><span data-stu-id="1c58b-114">Human users on mobile/native clients accessing back-end Web APIs.</span></span>
- <span data-ttu-id="1c58b-115">バックエンド Web Api にアクセスする他のアプリケーション (アクティブなユーザーまたはユーザーインターフェイスなし)。</span><span class="sxs-lookup"><span data-stu-id="1c58b-115">Other applications accessing back-end Web APIs (without an active user or user interface).</span></span>
- <span data-ttu-id="1c58b-116">アプリケーションは、独自の id を使用するか、ユーザーの id を委任することによって、他の Web Api と対話する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c58b-116">Any application may need to interact with other Web APIs, using its own identity or delegating to the user's identity.</span></span>

![アプリケーションの種類とシナリオ](./media/application-types.png)

<span data-ttu-id="1c58b-118">**図 8-1**。</span><span class="sxs-lookup"><span data-stu-id="1c58b-118">**Figure 8-1**.</span></span> <span data-ttu-id="1c58b-119">アプリケーションの種類とシナリオ。</span><span class="sxs-lookup"><span data-stu-id="1c58b-119">Application types and scenarios.</span></span>

<span data-ttu-id="1c58b-120">これらの各シナリオでは、公開されている機能を承認されていない使用から保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c58b-120">In each of these scenarios, the exposed functionality needs to be secured against unauthorized use.</span></span> <span data-ttu-id="1c58b-121">これは、少なくとも、リソースの要求を行うユーザーまたはプリンシパルを認証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c58b-121">At a minimum, this typically requires authenticating the user or principal making a request for a resource.</span></span> <span data-ttu-id="1c58b-122">この認証では、SAML2p、WS-ATOMICTRANSACTION、OpenID Connect など、いくつかの一般的なプロトコルのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-122">This authentication may use one of several common protocols such as SAML2p, WS-Fed, or OpenID Connect.</span></span> <span data-ttu-id="1c58b-123">Api との通信は、通常、OAuth2 プロトコルとセキュリティトークンのサポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c58b-123">Communicating with APIs typically uses the OAuth2 protocol and its support for security tokens.</span></span> <span data-ttu-id="1c58b-124">これらの重要なクロスカットセキュリティの問題とその実装の詳細をアプリケーション自体から分離することで、一貫性が確保され、セキュリティと保守性が向上します。</span><span class="sxs-lookup"><span data-stu-id="1c58b-124">Separating these critical cross-cutting security concerns and their implementation details from the applications themselves ensures consistency and improves security and maintainability.</span></span> <span data-ttu-id="1c58b-125">このような懸念を、独自の製品にアウトソーシングすると、すべてのアプリケーションがこれらの問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-125">Outsourcing these concerns to a dedicated product like IdentityServer helps the requirement for every application to solve these problems itself.</span></span>

<span data-ttu-id="1c58b-126">サーバーは、ASP.NET Core アプリケーション内で実行されるミドルウェアを提供し、OpenID Connect と OAuth2 のサポートを追加します (「[サポートされる仕様](http://docs.identityserver.io/en/latest/intro/specs.html)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1c58b-126">IdentityServer provides middleware that runs within an ASP.NET Core application and adds support for OpenID Connect and OAuth2 (see [supported specifications](http://docs.identityserver.io/en/latest/intro/specs.html)).</span></span> <span data-ttu-id="1c58b-127">組織は、すべてのトークンベースのセキュリティプロトコルの STS として機能するために、ユーザーが独自の ASP.NET Core アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c58b-127">Organizations would create their own ASP.NET Core app using IdentityServer middleware to act as the STS for all of their token-based security protocols.</span></span> <span data-ttu-id="1c58b-128">サーバーミドルウェアは、次のような標準的な機能をサポートするためにエンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="1c58b-128">The IdentityServer middleware exposes endpoints to support standard functionality, including:</span></span>

- <span data-ttu-id="1c58b-129">承認 (エンドユーザーの認証)</span><span class="sxs-lookup"><span data-stu-id="1c58b-129">Authorize (authenticate the end user)</span></span>
- <span data-ttu-id="1c58b-130">Token (プログラムによるトークンの要求)</span><span class="sxs-lookup"><span data-stu-id="1c58b-130">Token (request a token programmatically)</span></span>
- <span data-ttu-id="1c58b-131">検出 (サーバーに関するメタデータ)</span><span class="sxs-lookup"><span data-stu-id="1c58b-131">Discovery (metadata about the server)</span></span>
- <span data-ttu-id="1c58b-132">ユーザー情報 (有効なアクセストークンを使用してユーザー情報を取得する)</span><span class="sxs-lookup"><span data-stu-id="1c58b-132">User Info (get user information with a valid access token)</span></span>
- <span data-ttu-id="1c58b-133">デバイスの承認 (デバイスフローの承認を開始するために使用)</span><span class="sxs-lookup"><span data-stu-id="1c58b-133">Device Authorization (used to start device flow authorization)</span></span>
- <span data-ttu-id="1c58b-134">イントロスペクション (トークンの検証)</span><span class="sxs-lookup"><span data-stu-id="1c58b-134">Introspection (token validation)</span></span>
- <span data-ttu-id="1c58b-135">失効 (トークンの失効)</span><span class="sxs-lookup"><span data-stu-id="1c58b-135">Revocation (token revocation)</span></span>
- <span data-ttu-id="1c58b-136">セッションの終了 (すべてのアプリでのシングルサインアウトのトリガー)</span><span class="sxs-lookup"><span data-stu-id="1c58b-136">End Session (trigger single sign-out across all apps)</span></span>

## <a name="getting-started"></a><span data-ttu-id="1c58b-137">作業の開始</span><span class="sxs-lookup"><span data-stu-id="1c58b-137">Getting started</span></span>

<span data-ttu-id="1c58b-138">IdentityServer4 はオープンソースであり、自由に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-138">IdentityServer4 is open-source and free to use.</span></span> <span data-ttu-id="1c58b-139">NuGet パッケージを使用して、アプリケーションに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-139">You can add it to your applications using its NuGet packages.</span></span> <span data-ttu-id="1c58b-140">メインパッケージは、400万回以上ダウンロードされた[IdentityServer4](https://www.nuget.org/packages/IdentityServer4/)です。</span><span class="sxs-lookup"><span data-stu-id="1c58b-140">The main package is [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) that has been downloaded over four million times.</span></span> <span data-ttu-id="1c58b-141">基本パッケージには、ユーザーインターフェイスコードは含まれず、メモリ構成でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-141">The base package doesn't include any user interface code and only supports in memory configuration.</span></span> <span data-ttu-id="1c58b-142">データベースで使用するには、Entity Framework Core を使用して、ユーザーの構成データとオペレーションデータを格納する[IdentityServer4](https://www.nuget.org/packages/IdentityServer4.EntityFramework)のようなデータプロバイダーも必要になります。</span><span class="sxs-lookup"><span data-stu-id="1c58b-142">To use it with a database, you'll also want a data provider like [IdentityServer4.EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) that uses Entity Framework Core to store configuration and operational data for IdentityServer.</span></span> <span data-ttu-id="1c58b-143">ユーザーインターフェイスでは、[クイックスタート UI リポジトリ](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI)から ASP.NET Core MVC アプリケーションにファイルをコピーして、ユーザーのサインインとサインアウトのサポートを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-143">For user interface, you can copy files from the [Quickstart UI repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) into your ASP.NET Core MVC application to add support for sign in and sign out using IdentityServer middleware.</span></span>

## <a name="configuration"></a><span data-ttu-id="1c58b-144">構成</span><span class="sxs-lookup"><span data-stu-id="1c58b-144">Configuration</span></span>

<span data-ttu-id="1c58b-145">ユーザーは、各カスタムインストールの一部として構成できるさまざまな種類のプロトコルとソーシャル認証プロバイダーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1c58b-145">IdentityServer supports different kinds of protocols and social authentication providers that can be configured as part of each custom installation.</span></span> <span data-ttu-id="1c58b-146">これは通常、メソッドの ASP.NET Core アプリケーションのクラスで行われ `Startup` `ConfigureServices` ます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-146">This is typically done in the ASP.NET Core application's `Startup` class in the `ConfigureServices` method.</span></span> <span data-ttu-id="1c58b-147">構成には、サポートされるプロトコル、および使用されるサーバーとエンドポイントへのパスの指定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-147">The configuration involves specifying the supported protocols and the paths to the servers and endpoints that will be used.</span></span> <span data-ttu-id="1c58b-148">図8-2 は、IdentityServer4 クイックスタート UI プロジェクトから取得した構成の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="1c58b-148">Figure 8-2 shows an example configuration taken from the IdentityServer4 Quickstart UI project:</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<insert here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

<span data-ttu-id="1c58b-149">**図 8-2**。</span><span class="sxs-lookup"><span data-stu-id="1c58b-149">**Figure 8-2**.</span></span> <span data-ttu-id="1c58b-150">サーバーを構成しています。</span><span class="sxs-lookup"><span data-stu-id="1c58b-150">Configuring IdentityServer.</span></span>

<span data-ttu-id="1c58b-151">また、サービスは、さまざまなプロトコルと構成をテストするために使用できるパブリックデモサイトもホストします。</span><span class="sxs-lookup"><span data-stu-id="1c58b-151">IdentityServer also hosts a public demo site that can be used to test various protocols and configurations.</span></span> <span data-ttu-id="1c58b-152">このファイルはにあり、提供されたに [https://demo.identityserver.io/](https://demo.identityserver.io/) 基づいて動作を構成する方法についての情報が含まれてい `client_id` ます。</span><span class="sxs-lookup"><span data-stu-id="1c58b-152">It's located at [https://demo.identityserver.io/](https://demo.identityserver.io/) and includes information on how to configure its behavior based on the `client_id` provided to it.</span></span>

## <a name="javascript-clients"></a><span data-ttu-id="1c58b-153">JavaScript クライアント</span><span class="sxs-lookup"><span data-stu-id="1c58b-153">JavaScript clients</span></span>

<span data-ttu-id="1c58b-154">多くのクラウドネイティブアプリケーションでは、フロントエンドでサーバー側 Api とリッチクライアントシングルページアプリケーション (spa) を利用しています。</span><span class="sxs-lookup"><span data-stu-id="1c58b-154">Many cloud-native applications leverage server-side APIs and rich client single page applications (SPAs) on the front end.</span></span> <span data-ttu-id="1c58b-155">ユーザーは、NPM を使用して[JavaScript クライアント](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)() を提供し `oidc-client.js` ます。これを spas に追加することで、web api のサインイン、サインアウト、トークンベースの認証に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1c58b-155">IdentityServer ships a [JavaScript client](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) (`oidc-client.js`) via NPM that can be added to SPAs to enable them to use IdentityServer for sign in, sign out, and token-based authentication of web APIs.</span></span>

## <a name="references"></a><span data-ttu-id="1c58b-156">References</span><span class="sxs-lookup"><span data-stu-id="1c58b-156">References</span></span>

- [<span data-ttu-id="1c58b-157">サーバーのドキュメント</span><span class="sxs-lookup"><span data-stu-id="1c58b-157">IdentityServer documentation</span></span>](http://docs.identityserver.io/en/latest/)
- [<span data-ttu-id="1c58b-158">アプリケーションの種類</span><span class="sxs-lookup"><span data-stu-id="1c58b-158">Application types</span></span>](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [<span data-ttu-id="1c58b-159">JavaScript OIDC クライアント</span><span class="sxs-lookup"><span data-stu-id="1c58b-159">JavaScript OIDC client</span></span>](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)

>[!div class="step-by-step"]
><span data-ttu-id="1c58b-160">[前へ](azure-active-directory.md)
>[次へ](security.md)</span><span class="sxs-lookup"><span data-stu-id="1c58b-160">[Previous](azure-active-directory.md)
[Next](security.md)</span></span>
