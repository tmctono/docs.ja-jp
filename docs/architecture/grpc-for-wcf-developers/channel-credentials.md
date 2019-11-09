---
title: チャネル資格情報-WCF 開発者向け gRPC
description: ASP.NET Core 3.0 で gRPC チャネル資格情報を実装して使用する方法について説明します。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 61141dc4143f36f9ac511c3369c3fde668c9d703
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841667"
---
# <a name="channel-credentials"></a><span data-ttu-id="d2f11-103">チャンネルの資格情報</span><span class="sxs-lookup"><span data-stu-id="d2f11-103">Channel credentials</span></span>

<span data-ttu-id="d2f11-104">名前が示すように、チャネルの資格情報は、基になる gRPC チャネルにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="d2f11-105">標準形式のチャネル資格情報では、クライアント証明書認証が使用されます。この場合、クライアントは、接続時に TLS 証明書を提供します。これは、サーバーによって検証されてから、呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-105">The standard form of channel credentials uses Client Certificate authentication, where the client provides a TLS certificate when it's making the connection, which is verified by the server before allowing any calls to be made.</span></span>

<span data-ttu-id="d2f11-106">チャネル資格情報を呼び出し資格情報と組み合わせて、gRPC サービスに包括的なセキュリティを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-106">Channel credentials can be combined with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="d2f11-107">チャネル資格情報は、クライアントアプリケーションがサービスへのアクセスを許可されていることを証明し、呼び出し資格情報は、クライアントアプリケーションを使用しているユーザーに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2f11-107">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person using the client application.</span></span>

<span data-ttu-id="d2f11-108">クライアント証明書の認証は、ASP.NET Core と同じように、gRPC に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="d2f11-108">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="d2f11-109">ここでは構成プロセスについて概要を説明しますが、詳細については、「 [ASP.NET Core での証明書認証の構成](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2f11-109">The configuration process will be summarized here, but more information is available in the [Configure certificate authentication in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) article.</span></span>

<span data-ttu-id="d2f11-110">開発目的では自己署名証明書を使用できますが、運用環境では、信頼された機関によって署名された適切な HTTPS 証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2f11-110">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="adding-certificate-authentication-to-the-server"></a><span data-ttu-id="d2f11-111">サーバーに証明書認証を追加する</span><span class="sxs-lookup"><span data-stu-id="d2f11-111">Adding certificate authentication to the server</span></span>

<span data-ttu-id="d2f11-112">証明書認証は、Kestrel サーバーや ASP.NET Core パイプラインなど、ホストレベルで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2f11-112">You need to configure certificate authentication both at the host level, for example on the Kestrel server, and in the ASP.NET Core pipeline.</span></span>

### <a name="configuring-certificate-validation-on-kestrel"></a><span data-ttu-id="d2f11-113">Kestrel での証明書の検証の構成</span><span class="sxs-lookup"><span data-stu-id="d2f11-113">Configuring certificate validation on Kestrel</span></span>

<span data-ttu-id="d2f11-114">クライアント証明書を要求するように Kestrel (ASP.NET Core HTTP サーバー) を構成し、必要に応じて、受信接続を受け入れる前に指定された証明書の検証を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-114">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate before accepting incoming connections.</span></span> <span data-ttu-id="d2f11-115">この構成は、`Startup`ではなく、`Program` クラスの `CreateWebHostBuilder` メソッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-115">This configuration is done in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            var serverCert = ObtainServerCertificate();
            webBuilder.UseStartup<Startup>()
                .ConfigureKestrel(kestrelServerOptions => {
                    kestrelServerOptions.ConfigureHttpsDefaults(opt =>
                    {
                        opt.ClientCertificateMode = ClientCertificateMode.RequireCertificate;

                        // Verify that client certificate was issued by same CA as server certificate
                        opt.ClientCertificateValidation = (certificate, chain, errors) =>
                            certificate.Issuer == serverCert.Issuer;
                    });
                });
        });

```

<span data-ttu-id="d2f11-116">`ClientCertificateMode.RequireCertificate` 設定を使用すると、Kestrel がクライアント証明書を提供していない接続要求を直ちに拒否しますが、証明書は検証されません。</span><span class="sxs-lookup"><span data-stu-id="d2f11-116">The `ClientCertificateMode.RequireCertificate` setting will cause Kestrel to immediately reject any connection request that doesn't provide a client certificate, but it won't validate the certificate.</span></span> <span data-ttu-id="d2f11-117">`ClientCertificateValidation` コールバックを追加すると、Kestrel は、接続が確立される時点でクライアント証明書 (この場合はサーバー証明書と同じ*証明機関*によって発行されたものであること) を検証することができます。この場合、ASP.NET Core パイプラインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-117">Adding the `ClientCertificateValidation` callback enables Kestrel to validate the client certificate (in this case, ensuring that it was issued by the same *Certificate Authority* as the server certificate) at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span>

### <a name="adding-aspnet-core-certificate-authentication"></a><span data-ttu-id="d2f11-118">ASP.NET Core 証明書認証の追加</span><span class="sxs-lookup"><span data-stu-id="d2f11-118">Adding ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="d2f11-119">証明書の認証は、 [AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet パッケージによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-119">Certificate authentication is provided by the [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package.</span></span>

<span data-ttu-id="d2f11-120">`ConfigureServices` メソッドに証明書認証サービスを追加し、`Configure` メソッドで ASP.NET Core パイプラインに認証と承認を追加します。</span><span class="sxs-lookup"><span data-stu-id="d2f11-120">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

```csharp
public class Startup
{
    private readonly bool _isDevelopment;

    public Startup(IWebHostEnvironment env)
    {
        _isDevelopment = env.IsDevelopment();
    }

    public void ConfigureServices(IServiceCollection services)
    {
        services.AddAuthentication(CertificateAuthenticationDefaults.AuthenticationScheme)
            .AddCertificate(options =>
            {
                if (_isDevelopment)
                {
                    // DO NOT DO THIS IN PRODUCTION!
                    options.RevocationMode = X509RevocationMode.NoCheck;
                }
            });
        services.AddAuthorization();
        services.AddGrpc();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        app.UseRouting();

        app.UseAuthentication();
        app.UseAuthorization();

        app.UseEndpoints(endpoints => { endpoints.MapGrpcService<GreeterService>(); });
    }
}
```

## <a name="providing-channel-credentials-in-the-client-application"></a><span data-ttu-id="d2f11-121">クライアントアプリケーションでのチャネル資格情報の提供</span><span class="sxs-lookup"><span data-stu-id="d2f11-121">Providing channel credentials in the client application</span></span>

<span data-ttu-id="d2f11-122">`Grpc.Net.Client` パッケージでは、接続に使用される `GrpcChannel` に提供される <xref:System.Net.Http.HttpClient> インスタンスで証明書が構成されます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-122">With the `Grpc.Net.Client` package, certificates are configured on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        // Assume path to a client .pfx file and password are passed from command line
        // On Windows this would probably be a reference to the Certificate Store
        var cert = new X509Certificate2(args[0], args[1]);

        var handler = new HttpClientHandler();
        handler.ClientCertificates.Add(cert);
        var httpClient = new HttpClient(handler);

        var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
        {
            HttpClient = httpClient
        });

        var grpc = new Greeter.GreeterClient(channel);
        var response = await grpc.SayHelloAsync(new HelloRequest { Name = "Bob" });
        System.Console.WriteLine(response.Message);
    }
}
```

## <a name="combining-channelcredentials-and-callcredentials"></a><span data-ttu-id="d2f11-123">ChannelCredentials と CallCredentials を組み合わせる</span><span class="sxs-lookup"><span data-stu-id="d2f11-123">Combining ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="d2f11-124">証明書の変更を Kestrel サーバーに適用し、ASP.NET Core で JWT ベアラーミドルウェアを使用することによって、証明書とトークン認証の両方を使用するようにサーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-124">You can configure your server to use both certificate and token authentication by applying the certificate changes to the Kestrel server and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="d2f11-125">ChannelCredentials と CallCredentials の両方をクライアントに提供するには、`ChannelCredentials.Create` メソッドを使用して呼び出し資格情報を適用します。</span><span class="sxs-lookup"><span data-stu-id="d2f11-125">To provide both ChannelCredentials and CallCredentials on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="d2f11-126">証明書の認証は <xref:System.Net.Http.HttpClient> インスタンスを使用して適用する必要があります。 `SslCredentials` コンストラクターに引数を渡すと、内部クライアントコードが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="d2f11-126">Certificate authentication still needs to be applied using the <xref:System.Net.Http.HttpClient> instance: if you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="d2f11-127">`SslCredentials` パラメーターは、`Grpc.Core` パッケージとの互換性を維持するために、`Grpc.Net.Client` パッケージの `Create` メソッドにのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2f11-127">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

```csharp
var handler = new HttpClientHandler();
handler.ClientCertificates.Add(cert);

var httpClient = new HttpClient(handler);

var callCredentials = CallCredentials.FromInterceptor(((context, metadata) =>
    {
        metadata.Add("Authorization", $"Bearer {_token}");
    }));

var channelCredentials = ChannelCredentials.Create(new SslCredentials(), callCredentials);

var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
{
    HttpClient = httpClient,
    Credentials = channelCredentials
});

var grpc = new Portfolios.PortfoliosClient(channel);
```

> [!TIP]
> <span data-ttu-id="d2f11-128">チャネルに対して行われたすべての呼び出しにトークン資格情報を渡す便利な方法として、証明書認証を使用しないクライアントには `ChannelCredentials.Create` メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2f11-128">You can use the `ChannelCredentials.Create` method for a client without certificate authentication, as a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="d2f11-129">[証明書認証が追加された Fullstockticker サンプル gRPC アプリケーション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)のバージョンは、GitHub にあります。</span><span class="sxs-lookup"><span data-stu-id="d2f11-129">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d2f11-130">[前へ](call-credentials.md)
>[次へ](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="d2f11-130">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
