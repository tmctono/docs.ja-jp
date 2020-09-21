---
ms.openlocfilehash: 97870553d4ec66a569ba63cd945639b03bbbd6df
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539504"
---
### <a name="kestrel-default-supported-tls-protocol-versions-changed"></a><span data-ttu-id="dec0e-101">Kestrel: 既定でサポートされている TLS プロトコル バージョンの変更</span><span class="sxs-lookup"><span data-stu-id="dec0e-101">Kestrel: Default supported TLS protocol versions changed</span></span>

<span data-ttu-id="dec0e-102">Kestrel では現在、以前のように TLS 1.1 プロトコルと TLS 1.2 プロトコルへの接続を制限するのではなく、システム既定の TLS プロトコル バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="dec0e-102">Kestrel now uses the system default TLS protocol versions rather than restricting connections to the TLS 1.1 and TLS 1.2 protocols like it did previously.</span></span>

<span data-ttu-id="dec0e-103">この変更で可能になること:</span><span class="sxs-lookup"><span data-stu-id="dec0e-103">This change allows:</span></span>

* <span data-ttu-id="dec0e-104">それをサポートする環境で TLS 1.3 を既定で使用できます。</span><span class="sxs-lookup"><span data-stu-id="dec0e-104">TLS 1.3 to be used by default in environments that support it.</span></span>
* <span data-ttu-id="dec0e-105">TLS 1.0 を一部の環境 (既定の Windows Server 2016 など) で使用できます。通常、これは[望ましくありません](/security/engineering/solving-tls1-problem)。</span><span class="sxs-lookup"><span data-stu-id="dec0e-105">TLS 1.0 to be used in some environments (such as Windows Server 2016 by default), which is usually [not desirable](/security/engineering/solving-tls1-problem).</span></span>

<span data-ttu-id="dec0e-106">ディスカッションについては、イシュー [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dec0e-106">For discussion, see issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="dec0e-107">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="dec0e-107">Version introduced</span></span>

<span data-ttu-id="dec0e-108">5.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="dec0e-108">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="dec0e-109">以前の動作</span><span class="sxs-lookup"><span data-stu-id="dec0e-109">Old behavior</span></span>

<span data-ttu-id="dec0e-110">Kestrel では既定で、TLS 1.1 または TLS 1.2 を接続に使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="dec0e-110">Kestrel required that connections use TLS 1.1 or TLS 1.2 by default.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="dec0e-111">新しい動作</span><span class="sxs-lookup"><span data-stu-id="dec0e-111">New behavior</span></span>

<span data-ttu-id="dec0e-112">Kestrel では、使用に最適なプロトコルを選択し、セキュリティに保護されていないプロトコルをブロックすることがオペレーティング システムに許可されます。</span><span class="sxs-lookup"><span data-stu-id="dec0e-112">Kestrel allows the operating system to choose the best protocol to use and to block insecure protocols.</span></span> <span data-ttu-id="dec0e-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> は既定で `SslProtocols.Tls12 | SslProtocols.Tls11` ではなく `SslProtocols.None` になりました。</span><span class="sxs-lookup"><span data-stu-id="dec0e-113"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> now defaults to `SslProtocols.None` instead of `SslProtocols.Tls12 | SslProtocols.Tls11`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="dec0e-114">変更理由</span><span class="sxs-lookup"><span data-stu-id="dec0e-114">Reason for change</span></span>

<span data-ttu-id="dec0e-115">TLS 1.3 と、将来の TLS バージョンが利用できるようになったときにそれをサポートする目的で変更が行われました。</span><span class="sxs-lookup"><span data-stu-id="dec0e-115">The change was made to support TLS 1.3 and future TLS versions by default as they become available.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dec0e-116">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="dec0e-116">Recommended action</span></span>

<span data-ttu-id="dec0e-117">アプリケーション側に特別な理由がある場合を除き、新しい既定値を使用してください。</span><span class="sxs-lookup"><span data-stu-id="dec0e-117">Unless your app has a specific reason not to, you should use the new defaults.</span></span> <span data-ttu-id="dec0e-118">セキュリティで保護されているプロトコルのみを許可するようにシステムが構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dec0e-118">Verify your system is configured to allow only secure protocols.</span></span>

<span data-ttu-id="dec0e-119">以前のプロトコルを無効にするには、次のいずれかのアクションを行います。</span><span class="sxs-lookup"><span data-stu-id="dec0e-119">To disable older protocols, take one of the following actions:</span></span>

* <span data-ttu-id="dec0e-120">[Windows の指示に従い](../../../../docs/framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry)、TLS 1.0 など、古いプロトコルをシステム全体で無効にします。</span><span class="sxs-lookup"><span data-stu-id="dec0e-120">Disable older protocols, such as TLS 1.0, system-wide with the [Windows instructions](../../../../docs/framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry).</span></span> <span data-ttu-id="dec0e-121">現在のところ、すべての Windows バージョンで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="dec0e-121">It's currently enabled by default on all Windows versions.</span></span>
* <span data-ttu-id="dec0e-122">コードでサポートするプロトコルを次のように手動で選択します。</span><span class="sxs-lookup"><span data-stu-id="dec0e-122">Manually select which protocols you want to support in code as follows:</span></span>

    ```csharp
    using System.Security.Authentication;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="dec0e-123">残念ながら、特定のプロトコルを除外する API はありません。</span><span class="sxs-lookup"><span data-stu-id="dec0e-123">Unfortunately, there's no API to exclude specific protocols.</span></span>

#### <a name="category"></a><span data-ttu-id="dec0e-124">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dec0e-124">Category</span></span>

<span data-ttu-id="dec0e-125">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dec0e-125">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dec0e-126">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dec0e-126">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
