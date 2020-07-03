---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325211"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a><span data-ttu-id="fd353-101">HttpSys:既定で無効になっているクライアント証明書の再ネゴシエーション</span><span class="sxs-lookup"><span data-stu-id="fd353-101">HttpSys: Client certificate renegotiation disabled by default</span></span>

<span data-ttu-id="fd353-102">接続を再ネゴシエートし、クライアント証明書を要求するオプションは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="fd353-102">The option to renegotiate a connection and request a client certificate has been disabled by default.</span></span> <span data-ttu-id="fd353-103">ディスカッションについては、イシュー [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd353-103">For discussion, see issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fd353-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="fd353-104">Version introduced</span></span>

<span data-ttu-id="fd353-105">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="fd353-105">ASP.NET Core 5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="fd353-106">以前の動作</span><span class="sxs-lookup"><span data-stu-id="fd353-106">Old behavior</span></span>

<span data-ttu-id="fd353-107">接続を再ネゴシエートし、クライアント証明書を要求できます。</span><span class="sxs-lookup"><span data-stu-id="fd353-107">The connection can be renegotiated to request a client certificate.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="fd353-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="fd353-108">New behavior</span></span>

<span data-ttu-id="fd353-109">クライアント証明書は、初回接続ハンドシェイク中にのみ要求できます。</span><span class="sxs-lookup"><span data-stu-id="fd353-109">Client certificates can only be requested during the initial connection handshake.</span></span> <span data-ttu-id="fd353-110">詳細については、pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd353-110">For more information, see pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="fd353-111">変更理由</span><span class="sxs-lookup"><span data-stu-id="fd353-111">Reason for change</span></span>

<span data-ttu-id="fd353-112">再ネゴシエーションによって、パフォーマンスとデッドロックのさまざまな問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="fd353-112">Renegotiation caused a number of performance and deadlock issues.</span></span> <span data-ttu-id="fd353-113">また、HTTP/2 でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fd353-113">It's also not supported in HTTP/2.</span></span> <span data-ttu-id="fd353-114">この動作を制御するオプションが ASP.NET Core 3.1 で導入されて以降の追加コンテキストについては、イシュー [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd353-114">For additional context from when the option to control this behavior was introduced in ASP.NET Core 3.1, see issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fd353-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="fd353-115">Recommended action</span></span>

<span data-ttu-id="fd353-116">クライアント証明書を必要とするアプリでは *netsh.exe* を使用し、`clientcertnegotiation` オプションを `enabled` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd353-116">Apps that require client certificates should use *netsh.exe* to set the `clientcertnegotiation` option to `enabled`.</span></span> <span data-ttu-id="fd353-117">詳細については、「[netsh http コマンド](/windows-server/networking/technologies/netsh/netsh-http)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd353-117">For more information, see [netsh http commands](/windows-server/networking/technologies/netsh/netsh-http).</span></span>

<span data-ttu-id="fd353-118">クライアント証明書をアプリの一部のみで有効にする場合、「[オプションのクライアント証明書](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates)」にあるガイダンスをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fd353-118">If you want client certificates enabled for only some parts of your app, see the guidance at [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span></span>

<span data-ttu-id="fd353-119">以前の再ネゴシエート動作が必要な場合、以前の値である `ClientCertificateMethod.AllowRenegotiate` に `HttpSysOptions.ClientCertificateMethod` を設定してください。</span><span class="sxs-lookup"><span data-stu-id="fd353-119">If you need the old renegotiate behavior, set `HttpSysOptions.ClientCertificateMethod` to the old value `ClientCertificateMethod.AllowRenegotiate`.</span></span> <span data-ttu-id="fd353-120">これは上述の理由から推奨されておらず、リンク先のガイダンスで推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="fd353-120">This isn't recommended for the reasons outlined above and in the linked guidance.</span></span>

#### <a name="category"></a><span data-ttu-id="fd353-121">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="fd353-121">Category</span></span>

<span data-ttu-id="fd353-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fd353-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fd353-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="fd353-123">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
