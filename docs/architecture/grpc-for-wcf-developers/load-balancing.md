---
title: WCF 開発者向けの gRPC-gRPC の負荷分散
description: GRPC サービスを使用するロードバランサーの選択。
ms.date: 09/02/2019
ms.openlocfilehash: 215c0983146bbf9168f01956d64733f80cea6faf
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711175"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="a8ef0-103">GRPC の負荷分散</span><span class="sxs-lookup"><span data-stu-id="a8ef0-103">Load balancing gRPC</span></span>

<span data-ttu-id="a8ef0-104">GRPC アプリケーションの一般的な展開には、サービスの同じインスタンスが多数含まれており、復元性と水平方向のスケーラビリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="a8ef0-105">負荷分散では、これらのインスタンスに着信要求を分散して、使用可能なすべてのリソースを完全に使用します。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-105">Load balancing distributes incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="a8ef0-106">この負荷分散をクライアントに対して非表示にするには、プロキシロードバランサーサーバーを使用してクライアントからの要求を処理し、バックエンドインスタンスにルーティングするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="a8ef0-107">ロードバランサーは、操作対象の*レイヤー*に応じて分類されます。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="a8ef0-108">レイヤー4のロードバランサーは、TCP ソケット、接続、パケットなどを使用して、*トランスポート*レベルで動作します。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections, and packets.</span></span> <span data-ttu-id="a8ef0-109">レイヤー7のロードバランサーは、*アプリケーション*レベルで動作します。具体的には、grpc アプリケーションの HTTP/2 要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="a8ef0-110">L4 ロードバランサー</span><span class="sxs-lookup"><span data-stu-id="a8ef0-110">L4 load balancers</span></span>

<span data-ttu-id="a8ef0-111">L4 ロードバランサーは、クライアントからの TCP 接続要求を受け入れ、いずれかのバックエンドインスタンスへの別の接続を開いて、実際の処理を行わずに2つの接続間でデータをコピーします。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="a8ef0-112">L4 は優れたパフォーマンスと短い待機時間を提供しますが、制御やインテリジェンスはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="a8ef0-113">クライアントが接続を開いたままにしている限り、すべての要求は同じバックエンドインスタンスに送られます。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

 <span data-ttu-id="a8ef0-114">[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/)は、L4 ロードバランサーの一例です。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-114">[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) is an example of an L4 load balancer.</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="a8ef0-115">L7 ロードバランサー</span><span class="sxs-lookup"><span data-stu-id="a8ef0-115">L7 load balancers</span></span>

<span data-ttu-id="a8ef0-116">L7 ロードバランサーは、クライアントが接続を保持する時間に関係なく、受信 HTTP/2 要求を解析し、要求ごとにバックエンドインスタンスに渡します。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="a8ef0-117">L7 ロードバランサーの例:</span><span class="sxs-lookup"><span data-stu-id="a8ef0-117">Examples of L7 load balancers:</span></span>

- [<span data-ttu-id="a8ef0-118">NGINX</span><span class="sxs-lookup"><span data-stu-id="a8ef0-118">NGINX</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="a8ef0-119">HAProxy</span><span class="sxs-lookup"><span data-stu-id="a8ef0-119">HAProxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="a8ef0-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="a8ef0-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="a8ef0-121">目安として、L7 ロードバランサーは gRPC やその他の HTTP/2 アプリケーションに最適な選択肢です (通常は HTTP アプリケーションの場合)。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="a8ef0-122">L4 ロードバランサーは gRPC アプリケーションで*動作*しますが、主に低待機時間と低いオーバーヘッドが重要な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-122">L4 load balancers will *work* with gRPC applications, but they're mainly useful when low latency and low overhead are important.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8ef0-123">このドキュメントの執筆時点では、一部の L7 ロードバランサーは、ヘッダーの末尾など、gRPC サービスで必要とされる HTTP/2 仕様のすべての部分をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-123">At the time of this writing, some L7 load balancers don't support all the parts of the HTTP/2 specification that are required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="a8ef0-124">TLS 暗号化を使用している場合、ロードバランサーは TLS 接続を終了し、暗号化されていない要求をバックエンドアプリケーションに渡すことができます。また、暗号化された要求をに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-124">If you're using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or they can pass the encrypted request along.</span></span> <span data-ttu-id="a8ef0-125">どちらの場合も、ロードバランサーは、サーバーの公開キーと秘密キーを使用して構成する必要があります。これにより、処理要求の暗号化が解除されます。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-125">Either way, the load balancer will need to be configured with the server's public and private key so it can decrypt requests for processing.</span></span>

<span data-ttu-id="a8ef0-126">バックエンドサービスで HTTP/2 要求を処理するように構成する方法については、お使いのロードバランサーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-126">See to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="a8ef0-127">Kubernetes 内での負荷分散</span><span class="sxs-lookup"><span data-stu-id="a8ef0-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="a8ef0-128">Kubernetes の内部サービス間の負荷分散の詳細については[、サービスメッシュに関するセクション](service-mesh.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8ef0-128">See [the section on service meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a8ef0-129">[前へ](service-mesh.md)
>[次へ](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="a8ef0-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
