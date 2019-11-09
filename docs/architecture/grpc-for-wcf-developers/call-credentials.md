---
title: 資格情報の呼び出し-WCF 開発者向けの gRPC
description: ASP.NET Core 3.0 で gRPC 通話資格情報を実装して使用する方法。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 5f29d69ec37fe60bcd7ca01391001ea9eb71e7e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841673"
---
# <a name="call-credentials"></a><span data-ttu-id="cb922-103">資格情報を呼び出す</span><span class="sxs-lookup"><span data-stu-id="cb922-103">Call credentials</span></span>

<span data-ttu-id="cb922-104">呼び出し資格情報は、すべての要求に対してメタデータで渡される何らかの種類のトークンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="cb922-104">Call credentials are all based on some kind of token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="cb922-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="cb922-105">WS-Federation</span></span>

<span data-ttu-id="cb922-106">ASP.NET Core は、 [wsfederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet パッケージを使用した ws-federation をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cb922-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="cb922-107">WS フェデレーションは、HTTP/2 でサポートされていない Windows 認証の代替として使用できる最も近いものです。</span><span class="sxs-lookup"><span data-stu-id="cb922-107">WS-Federation is the closest available alternative to Windows Authentication, which is not supported over HTTP/2.</span></span> <span data-ttu-id="cb922-108">ユーザーは Active Directory フェデレーションサービス (AD FS) (ADFS) を使用して認証されます。 ADFS は、ASP.NET Core での認証に使用できるトークンを提供します。</span><span class="sxs-lookup"><span data-stu-id="cb922-108">Users are authenticated using Active Directory Federation Services (ADFS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="cb922-109">この認証方法の使用を開始する方法の詳細については、 [ASP.NET Core にある ws-federation を使用したユーザーの認証に](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0)関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb922-109">For more information on how to get started with this authentication method, see the [Authenticate users with WS-Federation in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) article.</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="cb922-110">JWT ベアラートークン</span><span class="sxs-lookup"><span data-stu-id="cb922-110">JWT Bearer tokens</span></span>

<span data-ttu-id="cb922-111">[JSON Web Token](https://jwt.io) standard には、エンコードされた文字列でユーザーとそのクレームに関する情報をエンコードし、コンシューマーが公開キー暗号化を使用してトークンの整合性を検証できるように、そのトークンに署名する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cb922-111">The [JSON Web Token](https://jwt.io) standard provides a way to encode information about a user and their claims in an encoded string, and to sign that token in such a way that the consumer can verify the integrity of the token using public key cryptography.</span></span> <span data-ttu-id="cb922-112">IdentityServer4 などのさまざまなサービスを使用して、ユーザーを認証し、gRPC と HTTP Api で使用する OpenID Connect (OIDC) トークンを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="cb922-112">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="cb922-113">ASP.NET Core 3.0 では、JWT ベアラーパッケージを使用して JSON Web トークンを処理できます。</span><span class="sxs-lookup"><span data-stu-id="cb922-113">ASP.NET Core 3.0 can handle JSON Web Tokens using the JWT Bearer package.</span></span> <span data-ttu-id="cb922-114">GRPC アプリケーションの構成は、ASP.NET Core MVC アプリケーションとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="cb922-114">The configuration is exactly the same for a gRPC application as an ASP.NET Core MVC application.</span></span>

<span data-ttu-id="cb922-115">この章では、WS-FEDERATION を使用した開発が簡単であるため、JWT ベアラートークンに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="cb922-115">This chapter will focus on JWT Bearer tokens as they're easier to develop with than WS-Federation.</span></span>

## <a name="adding-authentication-and-authorization-to-the-server"></a><span data-ttu-id="cb922-116">サーバーへの認証と承認の追加</span><span class="sxs-lookup"><span data-stu-id="cb922-116">Adding authentication and authorization to the server</span></span>

<span data-ttu-id="cb922-117">JWT ベアラーパッケージは、既定では ASP.NET Core 3.0 には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="cb922-117">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="cb922-118">アプリに[AspNetCore JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cb922-118">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="cb922-119">Startup クラスに認証サービスを追加し、JWT ベアラーハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb922-119">Add the Authentication service in the Startup class and configure the JWT Bearer handler.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

<span data-ttu-id="cb922-120">`IssuerSigningKey` プロパティには、署名されたトークンを検証するために必要な暗号化データと共に `Microsoft.IdentityModels.Tokens.SecurityKey` の実装が必要です。</span><span class="sxs-lookup"><span data-stu-id="cb922-120">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="cb922-121">このトークンは、Azure KeyVault などの*シークレットサーバー*に安全に格納されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb922-121">This token should be stored securely in a *secrets server* like Azure KeyVault.</span></span>

<span data-ttu-id="cb922-122">次に、承認サービスを追加します。これにより、システムへのアクセスが制御されます。</span><span class="sxs-lookup"><span data-stu-id="cb922-122">Next add the Authorization service, which controls access to the system.</span></span>

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> <span data-ttu-id="cb922-123">認証と承認は、2つの別個の手順です。</span><span class="sxs-lookup"><span data-stu-id="cb922-123">Authentication and Authorization are two separate steps.</span></span> <span data-ttu-id="cb922-124">認証は、ユーザーの id を決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb922-124">Authentication is used to determine the user's identity.</span></span> <span data-ttu-id="cb922-125">承認は、システムのさまざまな部分へのアクセスがユーザーに許可されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="cb922-125">Authorization decides whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="cb922-126">次に、認証と承認のミドルウェアを `Configure` メソッドの ASP.NET Core パイプラインに追加します。</span><span class="sxs-lookup"><span data-stu-id="cb922-126">Now add the Authentication and Authorization middleware to the ASP.NET Core pipeline in the `Configure` method.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="cb922-127">最後に、`[Authorize]` 属性をセキュリティで保護するすべてのサービスまたはメソッドに適用し、基になる `HttpContext` の `User` プロパティを使用してアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="cb922-127">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="providing-call-credentials-in-the-client-application"></a><span data-ttu-id="cb922-128">クライアントアプリケーションでの呼び出し資格情報の提供</span><span class="sxs-lookup"><span data-stu-id="cb922-128">Providing call credentials in the client application</span></span>

<span data-ttu-id="cb922-129">Id サーバーから JWT トークンを取得したら、それを使用してクライアントからの gRPC 呼び出しを認証できます。そのためには、次のように呼び出しのメタデータヘッダーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="cb922-129">Once you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

<span data-ttu-id="cb922-130">これで、JWT ベアラートークンを呼び出し資格情報として使用して gRPC サービスがセキュリティで保護されました。</span><span class="sxs-lookup"><span data-stu-id="cb922-130">Now, you've secured your gRPC service using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="cb922-131">[認証と承認を追加したポートフォリオサンプル gRPC アプリケーション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth)のバージョンは、GitHub にあります。</span><span class="sxs-lookup"><span data-stu-id="cb922-131">A version of the [Portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cb922-132">[前へ](security.md)
>[次へ](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="cb922-132">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
