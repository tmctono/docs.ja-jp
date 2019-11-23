---
title: WCF 開発者向けの gRPC-gRPC の負荷分散
description: GRPC サービスを使用するロードバランサーの選択。
ms.date: 09/02/2019
ms.openlocfilehash: 070fc7fda73988302d15c8cec12b1ac359641317
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967454"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="9568e-103">GRPC の負荷分散</span><span class="sxs-lookup"><span data-stu-id="9568e-103">Load balancing gRPC</span></span>

<span data-ttu-id="9568e-104">GRPC アプリケーションの一般的な展開には、サービスの同じインスタンスが多数含まれており、復元性と水平方向のスケーラビリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="9568e-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="9568e-105">これらのインスタンス間で分散された受信要求を負荷分散して、使用可能なすべてのリソースを完全に使用します。</span><span class="sxs-lookup"><span data-stu-id="9568e-105">Load balancing distributed incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="9568e-106">この負荷分散をクライアントに対して非表示にするには、プロキシロードバランサーサーバーを使用してクライアントからの要求を処理し、バックエンドインスタンスにルーティングするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="9568e-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="9568e-107">ロードバランサーは、操作対象の*レイヤー*に応じて分類されます。</span><span class="sxs-lookup"><span data-stu-id="9568e-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="9568e-108">レイヤー4のロードバランサーは、TCP ソケット、接続、パケットなどを使用して、*トランスポート*レベルで動作します。</span><span class="sxs-lookup"><span data-stu-id="9568e-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections and packets.</span></span> <span data-ttu-id="9568e-109">レイヤー7のロードバランサーは、*アプリケーション*レベルで動作します。具体的には、grpc アプリケーションの HTTP/2 要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="9568e-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="9568e-110">L4 ロードバランサー</span><span class="sxs-lookup"><span data-stu-id="9568e-110">L4 load balancers</span></span>

<span data-ttu-id="9568e-111">L4 ロードバランサーは、クライアントからの TCP 接続要求を受け入れ、いずれかのバックエンドインスタンスへの別の接続を開いて、実際の処理を行わずに2つの接続間でデータをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9568e-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="9568e-112">L4 は優れたパフォーマンスと短い待機時間を提供しますが、制御やインテリジェンスはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="9568e-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="9568e-113">クライアントが接続を開いたままにしている限り、すべての要求は同じバックエンドインスタンスに送られます。</span><span class="sxs-lookup"><span data-stu-id="9568e-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

<span data-ttu-id="9568e-114">L4 ロードバランサーの例としては、 [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/)があります。</span><span class="sxs-lookup"><span data-stu-id="9568e-114">An example of an L4 load balancer is the [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="9568e-115">L7 ロードバランサー</span><span class="sxs-lookup"><span data-stu-id="9568e-115">L7 load balancers</span></span>

<span data-ttu-id="9568e-116">L7 ロードバランサーは、クライアントが接続を保持する時間に関係なく、受信 HTTP/2 要求を解析し、要求ごとにバックエンドインスタンスに渡します。</span><span class="sxs-lookup"><span data-stu-id="9568e-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="9568e-117">L7 ロードバランサーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9568e-117">Examples of L7 load balancers include:</span></span>

- [<span data-ttu-id="9568e-118">Nginx</span><span class="sxs-lookup"><span data-stu-id="9568e-118">Nginx</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="9568e-119">HAproxy</span><span class="sxs-lookup"><span data-stu-id="9568e-119">HAproxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="9568e-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="9568e-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="9568e-121">目安として、L7 ロードバランサーは gRPC やその他の HTTP/2 アプリケーションに最適な選択肢です (通常は HTTP アプリケーションの場合)。</span><span class="sxs-lookup"><span data-stu-id="9568e-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="9568e-122">L4 ロードバランサーは gRPC アプリケーションで*動作*しますが、待機時間が短く、オーバーヘッドが低い場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="9568e-122">L4 load balancers will *work* with gRPC applications, but are primarily useful when low latency and low overhead are of paramount importance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9568e-123">このドキュメントの執筆時点では、すべての L7 ロードバランサーが、後続のヘッダーなど、gRPC サービスで必要とされる HTTP/2 仕様のすべての部分をサポートしているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9568e-123">At the time of this writing, not all L7 load balancers support all parts of the HTTP/2 specification required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="9568e-124">TLS 暗号化を使用する場合、ロードバランサーは TLS 接続を終了し、暗号化されていない要求をバックエンドアプリケーションに渡すか、または暗号化された要求をに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9568e-124">When using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or pass the encrypted request along.</span></span> <span data-ttu-id="9568e-125">どちらの場合も、ロードバランサーは、サーバーの公開キーと秘密キーを使用して構成する必要があります。これにより、処理要求の暗号化を解除できます。</span><span class="sxs-lookup"><span data-stu-id="9568e-125">Either way, the load balancer will need to be configured with the server's public and private key, so that it can decrypt requests for processing.</span></span>

<span data-ttu-id="9568e-126">バックエンドサービスで HTTP/2 要求を処理するように構成する方法については、お好みのロードバランサーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9568e-126">Refer to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="9568e-127">Kubernetes 内での負荷分散</span><span class="sxs-lookup"><span data-stu-id="9568e-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="9568e-128">Kubernetes の内部サービス間の負荷分散の詳細については[、サービスメッシュに関するセクション](service-mesh.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9568e-128">See [the section on Service Meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9568e-129">[前へ](service-mesh.md)
>[次へ](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="9568e-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
