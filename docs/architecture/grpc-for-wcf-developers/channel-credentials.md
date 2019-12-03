---
title: チャネル資格情報-WCF 開発者向け gRPC
description: ASP.NET Core 3.0 で gRPC チャネル資格情報を実装して使用する方法について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: 133de2c732e72844f249f11bfe22b5980b828b89
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711500"
---
# <a name="channel-credentials"></a><span data-ttu-id="2ab6c-103">チャンネルの資格情報</span><span class="sxs-lookup"><span data-stu-id="2ab6c-103">Channel credentials</span></span>

<span data-ttu-id="2ab6c-104">名前が示すように、チャネルの資格情報は、基になる gRPC チャネルにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="2ab6c-105">標準形式のチャネル資格情報では、クライアント証明書認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="2ab6c-106">このプロセスでは、クライアントは接続を確立するときに TLS 証明書を提供し、サーバーは呼び出しを許可する前にこれを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="2ab6c-107">チャネル資格情報と呼び出し資格情報を組み合わせて、gRPC サービスに包括的なセキュリティを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="2ab6c-108">チャネル資格情報は、クライアントアプリケーションがサービスへのアクセスを許可されていることを証明し、呼び出し資格情報は、クライアントアプリケーションを使用しているユーザーに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="2ab6c-109">クライアント証明書の認証は、ASP.NET Core と同じように、gRPC に対して機能します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="2ab6c-110">詳細については、「 [ASP.NET Core で証明書認証を構成する](/aspnet/core/security/authentication/certauth)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="2ab6c-111">開発目的では自己署名証明書を使用できますが、運用環境では、信頼された機関によって署名された適切な HTTPS 証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="2ab6c-112">サーバーに証明書認証を追加する</span><span class="sxs-lookup"><span data-stu-id="2ab6c-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="2ab6c-113">証明書認証は、ホストレベル (Kestrel サーバーなど) と ASP.NET Core パイプラインの両方で構成します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="2ab6c-114">Kestrel で証明書の検証を構成する</span><span class="sxs-lookup"><span data-stu-id="2ab6c-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="2ab6c-115">クライアント証明書を要求するように Kestrel (ASP.NET Core HTTP サーバー) を構成し、必要に応じて、入力方向の接続を受け入れる前に、指定された証明書の検証を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="2ab6c-116">これを行うには、`Startup`ではなく、`Program` クラスの `CreateWebHostBuilder` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="2ab6c-117">`ClientCertificateMode.RequireCertificate` 設定を使用すると、Kestrel がクライアント証明書を提供しない接続要求を直ちに拒否しますが、この設定自体によって提供される証明書は検証されません。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="2ab6c-118">`ClientCertificateValidation` コールバックを追加して、接続が確立された時点で、ASP.NET Core パイプラインが実行される前に、Kestrel がクライアント証明書を検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="2ab6c-119">(この場合、コールバックは、サーバー証明書と同じ*証明機関*によって発行されたものであることを保証します。)</span><span class="sxs-lookup"><span data-stu-id="2ab6c-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span> 

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="2ab6c-120">ASP.NET Core 証明書認証の追加</span><span class="sxs-lookup"><span data-stu-id="2ab6c-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="2ab6c-121">証明書認証は、 [AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet パッケージによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="2ab6c-122">`ConfigureServices` メソッドに証明書認証サービスを追加し、`Configure` メソッドで ASP.NET Core パイプラインに認証と承認を追加します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="2ab6c-123">クライアントアプリケーションでチャネル資格情報を指定する</span><span class="sxs-lookup"><span data-stu-id="2ab6c-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="2ab6c-124">`Grpc.Net.Client` パッケージを使用して、接続に使用する `GrpcChannel` に提供される <xref:System.Net.Http.HttpClient> インスタンスで証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="2ab6c-125">ChannelCredentials と CallCredentials を組み合わせる</span><span class="sxs-lookup"><span data-stu-id="2ab6c-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="2ab6c-126">証明書とトークン認証の両方を使用するようにサーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="2ab6c-127">これを行うには、Kestrel サーバーに証明書の変更を適用し、ASP.NET Core で JWT ベアラーミドルウェアを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="2ab6c-128">クライアントに `ChannelCredentials` と `CallCredentials` の両方を提供するには、`ChannelCredentials.Create` メソッドを使用して呼び出し資格情報を適用します。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="2ab6c-129">その場合でも、<xref:System.Net.Http.HttpClient> インスタンスを使用して証明書認証を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="2ab6c-130">`SslCredentials` コンストラクターに任意の引数を渡すと、内部クライアントコードが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="2ab6c-131">`SslCredentials` パラメーターは、`Grpc.Core` パッケージとの互換性を維持するために、`Grpc.Net.Client` パッケージの `Create` メソッドにのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="2ab6c-132">証明書認証を使用しないクライアントには、`ChannelCredentials.Create` 方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="2ab6c-133">これは、チャネルで行われるすべての呼び出しでトークン資格情報を渡すために便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="2ab6c-134">[証明書認証が追加された Fullstockticker サンプル gRPC アプリケーション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)のバージョンは、GitHub にあります。</span><span class="sxs-lookup"><span data-stu-id="2ab6c-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2ab6c-135">[前へ](call-credentials.md)
>[次へ](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="2ab6c-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
