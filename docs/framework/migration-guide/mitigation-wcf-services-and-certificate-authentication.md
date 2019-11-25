---
title: 軽減策:WCF サービスと証明書認証
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
ms.openlocfilehash: 8c8493efa2c3223809ad87e01e3faddaea859ca8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457796"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="85ef5-102">軽減策:WCF サービスと証明書認証</span><span class="sxs-lookup"><span data-stu-id="85ef5-102">Mitigation: WCF Services and Certificate Authentication</span></span>

<span data-ttu-id="85ef5-103">.NET Framework 4.6 では、WCF SSL プロトコルの既定の一覧に TLS 1.1 および TLS 1.2 が追加されます。</span><span class="sxs-lookup"><span data-stu-id="85ef5-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="85ef5-104">クライアントとサーバーの両方のマシンに .NET Framework 4.6 以降がインストールされている場合は、TLS 1.2 がネゴシエーションに使用されます。</span><span class="sxs-lookup"><span data-stu-id="85ef5-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>

## <a name="impact"></a><span data-ttu-id="85ef5-105">影響</span><span class="sxs-lookup"><span data-stu-id="85ef5-105">Impact</span></span>

<span data-ttu-id="85ef5-106">TLS 1.2 では MD5 証明書認証がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="85ef5-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="85ef5-107">そのため、顧客がハッシュ アルゴリズムで MD5 を使用する SSL 証明書を使用すると、WCF クライアントは WCF サービスに接続できません。</span><span class="sxs-lookup"><span data-stu-id="85ef5-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="85ef5-108">詳細については、「[軽減策:WCF サービスと証明書認証](mitigation-wcf-services-and-certificate-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ef5-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](mitigation-wcf-services-and-certificate-authentication.md).</span></span>

## <a name="mitigation"></a><span data-ttu-id="85ef5-109">軽減策</span><span class="sxs-lookup"><span data-stu-id="85ef5-109">Mitigation</span></span>

<span data-ttu-id="85ef5-110">次のいずれかの操作を実行することで、この問題を回避して、WCF クライアントを WCF サーバーに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="85ef5-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="85ef5-111">MD5 アルゴリズムを使用しないように証明書を更新します。</span><span class="sxs-lookup"><span data-stu-id="85ef5-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="85ef5-112">この解決策をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="85ef5-112">This is the recommended solution.</span></span>

- <span data-ttu-id="85ef5-113">バインドがソース コードで動的に構成されていない場合は、TLS 1.1 または以前のバージョンのプロトコルを使用するようにアプリケーションの構成ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="85ef5-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="85ef5-114">これにより、引き続き MD5 ハッシュ アルゴリズムによる証明書を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="85ef5-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="85ef5-115">MD5 ハッシュ アルゴリズムによる証明書は安全でないと見なされるため、この回避策はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="85ef5-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

  <span data-ttu-id="85ef5-116">次の構成ファイルでこれを行います。</span><span class="sxs-lookup"><span data-stu-id="85ef5-116">The following configuration file does this:</span></span>

  ```xml
  <configuration>
      <system.serviceModel>
          <bindings>
              <netTcpBinding>
                  <binding>
                      <security mode= "None|Transport|Message|TransportWithMessageCredential" >
                          <transport clientCredentialType="None|Windows|Certificate"
                                              protectionLevel="None|Sign|EncryptAndSign"
                                              sslProtocols="Ssl3|Tls1|Tls11">
                          </transport>
                      </security>
                  </binding>
              </netTcpBinding>
          </bindings>
      </system.serviceModel>
  </configuration>
  ```

- <span data-ttu-id="85ef5-117">バインドがソース コードで動的に構成されている場合は、ソース コード内で TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) または以前のバージョンのプロトコルを使用するように <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="85ef5-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="85ef5-118">MD5 ハッシュ アルゴリズムによる証明書は安全でないと見なされるため、この回避策はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="85ef5-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

## <a name="see-also"></a><span data-ttu-id="85ef5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="85ef5-119">See also</span></span>

- [<span data-ttu-id="85ef5-120">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="85ef5-120">Application compatibility</span></span>](application-compatibility.md)
