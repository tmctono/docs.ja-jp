---
title: チャネル資格情報 - WCF 開発者向け gRPC
description: ASP.NET Core 3.0 で gRPC チャネル資格情報を実装して使用する方法。
ms.date: 09/02/2019
ms.openlocfilehash: 9ebe0aecb517e4cc2fe280632c4ecb593da9871c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148206"
---
# <a name="channel-credentials"></a><span data-ttu-id="c5cf1-103">チャンネルの資格情報</span><span class="sxs-lookup"><span data-stu-id="c5cf1-103">Channel credentials</span></span>

<span data-ttu-id="c5cf1-104">名前が示すように、チャネル資格情報は基になる gRPC チャネルにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="c5cf1-105">チャネル資格情報の標準形式では、クライアント証明書認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="c5cf1-106">このプロセスでは、クライアントは接続を行うときに TLS 証明書を提供し、サーバーは呼び出しを許可する前にこれを検証します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="c5cf1-107">チャネル資格情報と呼び出し資格情報を組み合わせて、gRPC サービスの包括的なセキュリティを提供できます。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="c5cf1-108">チャネル資格情報は、クライアント アプリケーションがサービスにアクセスすることを許可されていることを証明し、呼び出しの資格情報は、クライアント アプリケーションを使用しているユーザーに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="c5cf1-109">クライアント証明書認証は、gRPC で ASP.NETコアで動作するのと同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="c5cf1-110">詳細については、「 [ASP.NET Core で証明書認証を構成する](/aspnet/core/security/authentication/certauth)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="c5cf1-111">開発目的では自己署名証明書を使用できますが、実稼働環境では、信頼された機関によって署名された適切な HTTPS 証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="c5cf1-112">サーバーに証明書認証を追加する</span><span class="sxs-lookup"><span data-stu-id="c5cf1-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="c5cf1-113">証明書認証は、ホスト レベル (Kestrel サーバーなど) と ASP.NET コア パイプラインの両方で構成します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="c5cf1-114">ケストレルで証明書検証を構成する</span><span class="sxs-lookup"><span data-stu-id="c5cf1-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="c5cf1-115">Kestrel (ASP.NETコア HTTP サーバー) を構成して、クライアント証明書を要求し、必要に応じて、着信接続を受け入れる前に、指定された証明書の検証を実行するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="c5cf1-116">これは、 ではなく`CreateWebHostBuilder`クラスの`Program`メソッドで`Startup`行います。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="c5cf1-117">この`ClientCertificateMode.RequireCertificate`設定により、Kestrel はクライアント証明書を提供しない接続要求を直ちに拒否しますが、この設定だけでは、提供された証明書は検証されません。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="c5cf1-118">コールバックを`ClientCertificateValidation`追加して、kestrel が接続が確立された時点で、ASP.NET Core パイプラインが関与する前にクライアント証明書を検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="c5cf1-119">(この場合、コールバックは、サーバー証明書と同じ*認証局*によって発行されたことを確認します)。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span>

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="c5cf1-120">ASP.NETコア証明書認証を追加する</span><span class="sxs-lookup"><span data-stu-id="c5cf1-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="c5cf1-121">[証明書](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate)の認証を提供する証明書の認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="c5cf1-122">メソッドに証明書認証サービスを`ConfigureServices`追加し、メソッドの ASP.NET Core パイプラインに認証と承認`Configure`を追加します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="c5cf1-123">クライアント アプリケーションでチャネル資格情報を提供する</span><span class="sxs-lookup"><span data-stu-id="c5cf1-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="c5cf1-124">パッケージでは`Grpc.Net.Client`、接続に`GrpcChannel`使用されるに提供される<xref:System.Net.Http.HttpClient>インスタンスに証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="c5cf1-125">チャネル資格情報と呼び出し資格情報の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="c5cf1-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="c5cf1-126">証明書とトークン認証の両方を使用するようにサーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="c5cf1-127">これを行うには、証明書の変更を Kestrel サーバーに適用し、ASP.NET Core の JWT ベアラー ミドルウェアを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="c5cf1-128">クライアント`ChannelCredentials``CallCredentials`の両方を提供するには、メソッドを`ChannelCredentials.Create`使用して呼び出しの資格情報を適用します。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="c5cf1-129">インスタンスを使用して証明書認証を適用する<xref:System.Net.Http.HttpClient>必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="c5cf1-130">`SslCredentials`コンストラクターに引数を渡すと、内部クライアント コードは例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="c5cf1-131">パラメーター`SslCredentials`は、パッケージと`Grpc.Net.Client``Create``Grpc.Core`の互換性を維持するためにパッケージのメソッドにのみ含まれます。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="c5cf1-132">証明書認証なしで`ChannelCredentials.Create`クライアントに対してこのメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="c5cf1-133">これは、チャネルで行われるすべての呼び出しでトークンの資格情報を渡す便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="c5cf1-134">[証明書認証が追加された FullStockTicker サンプル gRPC アプリケーション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker)のバージョンは GitHub にあります。</span><span class="sxs-lookup"><span data-stu-id="c5cf1-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c5cf1-135">[前次](call-credentials.md)
>[Next](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="c5cf1-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
