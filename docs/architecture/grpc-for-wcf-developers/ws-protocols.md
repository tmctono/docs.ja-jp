---
title: WS-* プロトコル-WCF 開発者向け gRPC
description: WCF でサポートされている WS-* プロトコルと gRPC で使用可能な代替方法の確認
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 4e7b80df182fb69cc51e14738e59ad87efaf5dd2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841313"
---
# <a name="ws--protocols"></a><span data-ttu-id="3dd18-103">WS-MANAGEMENT プロトコル\*</span><span class="sxs-lookup"><span data-stu-id="3dd18-103">WS-\* protocols</span></span>

<span data-ttu-id="3dd18-104">Windows Communication Foundation (WCF) を使用する利点の1つは、既存の_WS\*_ 標準プロトコルの多くをサポートすることでした。</span><span class="sxs-lookup"><span data-stu-id="3dd18-104">One of the real benefits of working with Windows Communication Foundation (WCF) was that it supported many of the existing _WS-\*_ standard protocols.</span></span> <span data-ttu-id="3dd18-105">このセクションでは、gRPC で同じ\* WS-MANAGEMENT プロトコルを管理する方法と、代替手段がない場合に使用できるオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3dd18-105">This section will briefly cover how gRPC manages the same WS-\* protocols and discuss what options are available when there's no alternative.</span></span>

## <a name="metadata-exchange---ws-policy-ws-discovery-and-so-on"></a><span data-ttu-id="3dd18-106">メタデータの交換-WS-POLICY、WS-POLICY など</span><span class="sxs-lookup"><span data-stu-id="3dd18-106">Metadata Exchange - WS-Policy, WS-Discovery, and so on</span></span>

<span data-ttu-id="3dd18-107">SOAP サービスでは、Web サービス記述言語 (WSDL) スキーマドキュメントが、データ形式、操作、通信オプションなどの情報と共に公開されます。</span><span class="sxs-lookup"><span data-stu-id="3dd18-107">SOAP services expose Web Services Description Language (WSDL) schema documents with information such as data formats, operations, or communication options.</span></span> <span data-ttu-id="3dd18-108">このスキーマを使用して、クライアントコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="3dd18-108">This schema could be used to generate the client code.</span></span>

<span data-ttu-id="3dd18-109">gRPC は、サーバーとクライアントが同じ `.proto` ファイルから生成された場合に最適に機能しますが、サーバーリフレクションのオプションの拡張機能を使用すると、実行中のサーバーから動的な情報を公開することができます。</span><span class="sxs-lookup"><span data-stu-id="3dd18-109">gRPC works best when servers and clients are generated from the same `.proto` files, but a server reflection optional extension does provide a way to expose dynamic information from a running server.</span></span> <span data-ttu-id="3dd18-110">詳細については、「 [grpc. リフレクション](https://nuget.org/packages/Grpc.Reflection)NuGet パッケージ」と「 [grpc C#サーバーリフレクション](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dd18-110">For more information, see the [Grpc.Reflection](https://nuget.org/packages/Grpc.Reflection) NuGet package and the [gRPC C# Server Reflection](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) article.</span></span>

<span data-ttu-id="3dd18-111">WS-MANAGEMENT プロトコルは、ローカルネットワーク上のサービスを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3dd18-111">The WS-Discovery protocol is used to locate services on a local network.</span></span> <span data-ttu-id="3dd18-112">gRPC サービスは、通常、DNS または Consul や飼育係などのサービスレジストリを使用して配置されます。</span><span class="sxs-lookup"><span data-stu-id="3dd18-112">gRPC services are generally located using DNS or a service registry such as Consul or ZooKeeper.</span></span>

## <a name="security--ws-security-ws-federation-xml-encryption-and-so-on"></a><span data-ttu-id="3dd18-113">セキュリティ-WS-SECURITY、WS-FEDERATION、XML 暗号化などの機能</span><span class="sxs-lookup"><span data-stu-id="3dd18-113">Security – WS-Security, WS-Federation, XML Encryption, and so on</span></span>

<span data-ttu-id="3dd18-114">セキュリティ、認証、および承認の詳細については、[第6章](security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dd18-114">Security, authentication, and authorization are covered in much more detail in [Chapter 6](security.md).</span></span> <span data-ttu-id="3dd18-115">ただし、WCF とは異なり、gRPC は WS-SECURITY、WS フェデレーション、または XML 暗号化をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3dd18-115">But it's worth noting here that, unlike WCF, gRPC doesn't support WS-Security, WS Federation, or XML Encryption.</span></span> <span data-ttu-id="3dd18-116">それでも、gRPC は優れたセキュリティを提供しています。すべての gRPC ネットワークトラフィックは、HTTP/2 over TLS を使用するときに自動的に暗号化され、X509 証明書は相互クライアント/サーバー認証に使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3dd18-116">Even so, gRPC provides excellent security; all gRPC network traffic is automatically encrypted when using HTTP/2 over TLS, and X509 certificates may be used for mutual client/server authentication.</span></span>

## <a name="ws-reliablemessaging"></a><span data-ttu-id="3dd18-117">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="3dd18-117">WS-ReliableMessaging</span></span>

<span data-ttu-id="3dd18-118">gRPC では、ws-reliablemessaging に相当するものは提供されません。</span><span class="sxs-lookup"><span data-stu-id="3dd18-118">gRPC does not provide an equivalent to WS-ReliableMessaging.</span></span> <span data-ttu-id="3dd18-119">再試行のセマンティクスは、コードで処理する必要があります[。たとえば](https://github.com/App-vNext/Polly)、通常のようなライブラリを使用します。</span><span class="sxs-lookup"><span data-stu-id="3dd18-119">Retry semantics should be handled in code, possibly with a library like [Polly](https://github.com/App-vNext/Polly).</span></span> <span data-ttu-id="3dd18-120">Kubernetes または同様のオーケストレーション環境で実行されている場合、[サービスメッシュ](service-mesh.md)はサービス間の信頼性の高いメッセージングを提供するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3dd18-120">When running in Kubernetes or similar orchestration environments, [service meshes](service-mesh.md) can also help to provide reliable messaging between services.</span></span>

## <a name="ws-transaction-ws-coordination"></a><span data-ttu-id="3dd18-121">WS-ATOMICTRANSACTION、WS-ATOMICTRANSACTION</span><span class="sxs-lookup"><span data-stu-id="3dd18-121">WS-Transaction, WS-Coordination</span></span>

<span data-ttu-id="3dd18-122">WCF による分散トランザクションの実装では、Windows の Microsoft 分散トランザクションコーディネーターまたは MSDTC を使用します。</span><span class="sxs-lookup"><span data-stu-id="3dd18-122">WCF's implementation of distributed transactions uses Windows’ Microsoft Distributed Transaction Coordinator or MSDTC.</span></span> <span data-ttu-id="3dd18-123">これは、SQL Server、MSMQ、Windows ファイルシステムなど、特にサポートされているリソースマネージャーと連携します。</span><span class="sxs-lookup"><span data-stu-id="3dd18-123">It works with resource managers that specifically support it, like SQL Server, MSMQ, or Windows file systems.</span></span> <span data-ttu-id="3dd18-124">最新のマイクロサービスの世界では、使用されているテクノロジの範囲が広いため、それと同等の機能はありません。</span><span class="sxs-lookup"><span data-stu-id="3dd18-124">In the modern microservices world, in part due to the wider range of technologies in use, there is no equivalent as yet.</span></span> <span data-ttu-id="3dd18-125">トランザクションの詳細については、「[付録 a](appendix.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3dd18-125">For a discussion of transactions, see [Appendix A](appendix.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3dd18-126">[前へ](error-handling.md)
>[次へ](migrate-wcf-to-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="3dd18-126">[Previous](error-handling.md)
[Next](migrate-wcf-to-grpc.md)</span></span>
