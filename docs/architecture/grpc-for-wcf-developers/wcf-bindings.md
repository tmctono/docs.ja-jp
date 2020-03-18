---
title: WCF バインディングとトランスポート - WCF 開発者向け gRPC
description: さまざまな WCF バインドとトランスポートと gRPC の比較について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: 3a295268b486578c70c2c98f1d05f89070daaeb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147725"
---
# <a name="wcf-bindings-and-transports"></a><span data-ttu-id="68a6d-103">WCF のバインドとトランスポート</span><span class="sxs-lookup"><span data-stu-id="68a6d-103">WCF bindings and transports</span></span>

<span data-ttu-id="68a6d-104">Windows 通信基盤 (WCF) には、さまざまなネットワーク プロトコル、ワイヤ形式、およびその他の実装の詳細を指定する組み込みの*バインド*があります。</span><span class="sxs-lookup"><span data-stu-id="68a6d-104">Windows Communication Foundation (WCF) has built-in *bindings* that specify different network protocols, wire formats, and other implementation details.</span></span> <span data-ttu-id="68a6d-105">gRPC は、ネットワークプロトコルと 1 つのワイヤーフォーマットを効果的に持っています。</span><span class="sxs-lookup"><span data-stu-id="68a6d-105">gRPC effectively has just one network protocol and one wire format.</span></span> <span data-ttu-id="68a6d-106">(技術的には、ワイヤ形式をカスタマイズ*できますが*、このマニュアルでは説明できません。ほとんどの場合、gRPCが最良のソリューションを提供していることを発見する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68a6d-106">(Technically you *can* customize the wire format, but that's beyond the scope of this book.) You're likely to discover that gRPC offers the best solution in most cases.</span></span>

<span data-ttu-id="68a6d-107">以下は、最も関連性の高い WCF バインディングと、それらのバインドと gRPC の同等のバインドとの比較について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="68a6d-107">What follows is a short discussion about the most relevant WCF bindings and how they compare to their equivalents in gRPC.</span></span>

## <a name="nettcp"></a><span data-ttu-id="68a6d-108">Nettcp</span><span class="sxs-lookup"><span data-stu-id="68a6d-108">NetTCP</span></span>

<span data-ttu-id="68a6d-109">WCF の NetTCP バインディングでは、永続的な接続、小さなメッセージ、および双方向メッセージングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="68a6d-109">WCF's NetTCP binding allows for persistent connections, small messages, and two-way messaging.</span></span> <span data-ttu-id="68a6d-110">しかし、この機能は .NET クライアントとサーバー間でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="68a6d-110">But it works only between .NET clients and servers.</span></span> <span data-ttu-id="68a6d-111">gRPC は同じ機能を使用できますが、複数のプログラミング言語とプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="68a6d-111">gRPC allows the same functionality but is supported across multiple programming languages and platforms.</span></span>

<span data-ttu-id="68a6d-112">gRPC には WCF の NetTCP バインディングの多くの機能がありますが、常に同じ方法で実装されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="68a6d-112">gRPC has many features of WCF's NetTCP binding, but they're not always implemented in the same way.</span></span> <span data-ttu-id="68a6d-113">たとえば、WCF では、暗号化は構成によって制御され、フレームワークで処理されます。</span><span class="sxs-lookup"><span data-stu-id="68a6d-113">For example, in WCF, encryption is controlled through configuration and handled in the framework.</span></span> <span data-ttu-id="68a6d-114">gRPC では、TLS 経由で HTTP/2 を介して接続レベルで暗号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="68a6d-114">In gRPC, encryption is achieved at the connection level through HTTP/2 over TLS.</span></span>

## <a name="http"></a><span data-ttu-id="68a6d-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="68a6d-115">HTTP</span></span>

<span data-ttu-id="68a6d-116">基本HttpBindingと呼ばれる WCF バインディングは、通常、テキスト ベースであり、ワイヤ形式として SOAP を使用します。</span><span class="sxs-lookup"><span data-stu-id="68a6d-116">The WCF binding called BasicHttpBinding is usually text based and uses SOAP as the wire format.</span></span> <span data-ttu-id="68a6d-117">NetTCP バインディングに比べて遅い。</span><span class="sxs-lookup"><span data-stu-id="68a6d-117">It's slow compared to the NetTCP binding.</span></span> <span data-ttu-id="68a6d-118">一般的に、クロスプラットフォームの相互運用性、またはインターネット インフラストラクチャ経由の接続を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="68a6d-118">It's generally used to provide cross-platform interoperability, or connection over internet infrastructure.</span></span>

<span data-ttu-id="68a6d-119">gRPC の同等の値は、メッセージのバイナリ Protobuf ワイヤー形式を持つ基になるトランスポート層として HTTP/2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="68a6d-119">The equivalent in gRPC uses HTTP/2 as the underlying transport layer with the binary Protobuf wire format for messages.</span></span> <span data-ttu-id="68a6d-120">したがって、NetTCP サービス レベルでのパフォーマンスと、最新のプログラミング言語とフレームワークとの完全なクロスプラットフォーム相互運用性を提供できます。</span><span class="sxs-lookup"><span data-stu-id="68a6d-120">So it can offer performance at the NetTCP service level and full cross-platform interoperability with all modern programming languages and frameworks.</span></span>

## <a name="named-pipes"></a><span data-ttu-id="68a6d-121">名前付きパイプ</span><span class="sxs-lookup"><span data-stu-id="68a6d-121">Named pipes</span></span>

<span data-ttu-id="68a6d-122">WCF では、同じ物理マシン上のプロセス間の通信用に *、名前付きパイプ*のバインドが提供されました。</span><span class="sxs-lookup"><span data-stu-id="68a6d-122">WCF provided a *named pipes* binding for communication between processes on the same physical machine.</span></span> <span data-ttu-id="68a6d-123">ASP.NETコア gRPC の最初のリリースでは、名前付きパイプはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="68a6d-123">The first release of ASP.NET Core gRPC does not support named pipes.</span></span> <span data-ttu-id="68a6d-124">名前付きパイプ (および Unix ドメイン ソケット) にクライアントとサーバーのサポートを追加することは、将来のリリースの目標です。</span><span class="sxs-lookup"><span data-stu-id="68a6d-124">Adding client and server support for named pipes (and Unix domain sockets) is a goal for a future release.</span></span>

## <a name="msmq"></a><span data-ttu-id="68a6d-125">MSMQ (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="68a6d-125">MSMQ</span></span>

<span data-ttu-id="68a6d-126">MSMQ は、Windows メッセージ キューを独自に作成したものです。</span><span class="sxs-lookup"><span data-stu-id="68a6d-126">MSMQ is a proprietary Windows message queue.</span></span> <span data-ttu-id="68a6d-127">WCF の MSMQ へのバインドにより、将来いつでも処理される可能性のあるクライアントからの要求を "起動して忘れる" ことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="68a6d-127">WCF's binding to MSMQ enables "fire and forget" requests from clients that might be processed at any time in the future.</span></span> <span data-ttu-id="68a6d-128">gRPC は、メッセージ キュー機能をネイティブに提供しません。</span><span class="sxs-lookup"><span data-stu-id="68a6d-128">gRPC doesn't natively provide any message queue functionality.</span></span>

<span data-ttu-id="68a6d-129">最良の方法は、Azure サービス バス、RabbitMQ、または Kafka などのメッセージング システムを直接使用することです。</span><span class="sxs-lookup"><span data-stu-id="68a6d-129">The best alternative is to directly use a messaging system like Azure Service Bus, RabbitMQ, or Kafka.</span></span> <span data-ttu-id="68a6d-130">これを実装するには、クライアントがキューに直接メッセージを配置するか、メッセージをキューに入れる gRPC クライアント ストリーミング サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="68a6d-130">You can implement this with the client placing messages directly onto the queue, or a gRPC client streaming service that enqueues the messages.</span></span>

## <a name="webhttpbinding"></a><span data-ttu-id="68a6d-131">WebHttpBinding</span><span class="sxs-lookup"><span data-stu-id="68a6d-131">WebHttpBinding</span></span>

<span data-ttu-id="68a6d-132">属性と属性を持つ`WebGet``WebInvoke`WebHttpBinding (WCF REST とも呼ばれる) を使用すると、これがあまり一般的ではない時期に JSON を話すことができる RESTful API を開発することができました。</span><span class="sxs-lookup"><span data-stu-id="68a6d-132">WebHttpBinding (also known as WCF REST), with the `WebGet` and `WebInvoke` attributes, enabled you to develop RESTful APIs that could speak JSON at a time when this was less common.</span></span> <span data-ttu-id="68a6d-133">WCF REST でビルドされた RESTful API がある場合は、通常の ASP.NETのコア MVC Web API アプリケーションに移行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="68a6d-133">If you have a RESTful API built with WCF REST, consider migrating it to a regular ASP.NET Core MVC Web API application.</span></span> <span data-ttu-id="68a6d-134">この移行は gRPC への変換と同じ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="68a6d-134">This migration would provide the same functionality as a conversion to gRPC.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="68a6d-135">[前次](wcf-endpoints-grpc-methods.md)
>[Next](rpc-types.md)</span><span class="sxs-lookup"><span data-stu-id="68a6d-135">[Previous](wcf-endpoints-grpc-methods.md)
[Next](rpc-types.md)</span></span>
