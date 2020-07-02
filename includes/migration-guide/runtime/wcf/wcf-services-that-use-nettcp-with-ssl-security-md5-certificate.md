---
ms.openlocfilehash: fb9436ec9e525afb497033775e34b6b636ced22d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621351"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a><span data-ttu-id="96643-101">SSL セキュリティと MD5 証明書認証で NETTCP を使用する WCF サービス</span><span class="sxs-lookup"><span data-stu-id="96643-101">WCF services that use NETTCP with SSL security and MD5 certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="96643-102">説明</span><span class="sxs-lookup"><span data-stu-id="96643-102">Details</span></span>

<span data-ttu-id="96643-103">.NET Framework 4.6 では、WCF SSL の既定のプロトコル一覧に TLS 1.1 および TLS 1.2 が追加されます。</span><span class="sxs-lookup"><span data-stu-id="96643-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="96643-104">クライアントとサーバーの両方のコンピューターに .NET Framework 4.6 以降がインストールされている場合は、TLS 1.2 がネゴシエーションに使用されます。TLS 1.2 では MD5 証明書認証がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="96643-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="96643-105">このため、顧客が MD5 証明書を使用する場合、WCF クライアントでは WCF サービスへ接続できません。</span><span class="sxs-lookup"><span data-stu-id="96643-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="96643-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="96643-106">Suggestion</span></span>

<span data-ttu-id="96643-107">次のいずれかの操作を実行することで、この問題を回避して、WCF クライアントを WCF サーバーに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="96643-107">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="96643-108">MD5 アルゴリズムを使用しないように証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="96643-108">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="96643-109">この解決策をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="96643-109">This is the recommended solution.</span></span>
- <span data-ttu-id="96643-110">バインドがソース コードで動的に構成されていない場合は、TLS 1.1 または以前のバージョンのプロトコルを使用するようにアプリケーションの構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="96643-110">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="96643-111">これにより、引き続き MD5 ハッシュ アルゴリズムによる証明書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="96643-111">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

> [!WARNING]
> <span data-ttu-id="96643-112">MD5 ハッシュ アルゴリズムによる証明書は安全でないと見なされるため、この回避策はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="96643-112">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

<span data-ttu-id="96643-113">次の構成ファイルでこれを行います。</span><span class="sxs-lookup"><span data-stu-id="96643-113">The following configuration file does this:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- <span data-ttu-id="96643-114">バインドがソース コードで動的に構成されている場合は、ソース コード内で TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) または以前のバージョンのプロトコルを使用するように <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="96643-114">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span>

> [!WARNING]
> <span data-ttu-id="96643-115">MD5 ハッシュ アルゴリズムによる証明書は安全でないと見なされるため、この回避策はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="96643-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

| <span data-ttu-id="96643-116">名前</span><span class="sxs-lookup"><span data-stu-id="96643-116">Name</span></span>    | <span data-ttu-id="96643-117">値</span><span class="sxs-lookup"><span data-stu-id="96643-117">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="96643-118">スコープ</span><span class="sxs-lookup"><span data-stu-id="96643-118">Scope</span></span>   | <span data-ttu-id="96643-119">マイナー</span><span class="sxs-lookup"><span data-stu-id="96643-119">Minor</span></span>   |
| <span data-ttu-id="96643-120">バージョン</span><span class="sxs-lookup"><span data-stu-id="96643-120">Version</span></span> | <span data-ttu-id="96643-121">4.6</span><span class="sxs-lookup"><span data-stu-id="96643-121">4.6</span></span>     |
| <span data-ttu-id="96643-122">種類</span><span class="sxs-lookup"><span data-stu-id="96643-122">Type</span></span>    | <span data-ttu-id="96643-123">ランタイム</span><span class="sxs-lookup"><span data-stu-id="96643-123">Runtime</span></span> |
