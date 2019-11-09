---
title: 暗号化とネットワークセキュリティ-WCF 開発者向けの gRPC
description: GRPC でのネットワークセキュリティと暗号化に関する注意事項
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 67ee1ffaf00ea0cc6b771ede9f49b6a691af0968
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841619"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="27a88-103">暗号化とネットワークセキュリティ</span><span class="sxs-lookup"><span data-stu-id="27a88-103">Encryption and network security</span></span>

<span data-ttu-id="27a88-104">WCF のネットワークセキュリティモデルは、HTTPS または TLS over TCP を使用したトランスポートレベルのセキュリティ、および WS-SECURITY 仕様を使用して個々のメッセージを暗号化するメッセージレベルのセキュリティなど、広範で複雑なものです。</span><span class="sxs-lookup"><span data-stu-id="27a88-104">WCF's network security model is extensive and complex, including transport-level security using HTTPS or TLS-over-TCP, and message-level security using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="27a88-105">gRPC は、通常の TLS 証明書を使用してセキュリティで保護できる、基になる HTTP/2 プロトコルに安全なネットワークを残します。</span><span class="sxs-lookup"><span data-stu-id="27a88-105">gRPC leaves secure networking to the underlying HTTP/2 protocol, which can be secured using regular TLS certificates.</span></span>

<span data-ttu-id="27a88-106">Web ブラウザーは、HTTP/2 の TLS 接続を使用することを主張していますが、を含むほとんどのプログラム用クライアントです。NET の `HttpClient`では、暗号化されていない接続を介して HTTP/2 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="27a88-106">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="27a88-107">`HttpClient` に*は*既定で暗号化が必要ですが、<xref:System.AppContext> スイッチを使用して上書きできます。</span><span class="sxs-lookup"><span data-stu-id="27a88-107">`HttpClient` *does* require encryption by default, but you can override this using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="27a88-108">パブリック Api の場合、TLS 接続を常に使用し、適切な SSL 機関からサービスに有効な証明書を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27a88-108">For public APIs, you should always use TLS connections and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="27a88-109">現在、最新の自動 SSL 証明書を提供し、ほとんどのホスティングインフラストラクチャでは、一般的なプラグインまたは拡張機能[によって](https://letsencrypt.org)、標準のプラグインまたは拡張機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="27a88-109">[LetsEncrypt](https://letsencrypt.org) provide free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="27a88-110">企業ネットワーク全体の内部サービスについても、TLS を使用して、gRPC サービスとの間のネットワークトラフィックをセキュリティで保護することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27a88-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="27a88-111">Kubernetes や Docker の群れなど、クラスター内のマイクロサービス間の通信は、通常、コンテナーネットワークレイヤーによって自動的に暗号化されます。そのため、このようなクラスターでのみ実行されるサービスに TLS を実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="27a88-111">Communication between microservices in a cluster like Kubernetes or Docker Swarm is in general automatically encrypted by the container networking layer, so implementing TLS in services running exclusively in such a cluster isn't necessary.</span></span> <span data-ttu-id="27a88-112">詳細については、次の章の「サービスメッシュ」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="27a88-112">There will be more on this subject in the "Service Mesh" section of the next chapter.</span></span>

<span data-ttu-id="27a88-113">Kubernetes で実行されているサービス間で明示的な TLS を使用する必要がある場合は、クラスター内の証明機関と、証明[書マネージャーのような](https://docs.cert-manager.io/en/latest/)証明書マネージャーコントローラーを使用して、展開時にサービスに自動的に証明書を割り当てることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="27a88-113">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster Certificate Authority and a Certificate Manager Controller like [cert-manager](https://docs.cert-manager.io/en/latest/) to assign automatically certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="27a88-114">[前へ](channel-credentials.md)
>[次へ](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="27a88-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
