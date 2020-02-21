---
title: Wcf 開発者向けに gRPC を推奨する理由-WCF 開発者向け gRPC
description: GRPC が最新のアーキテクチャやプラットフォームに移行する WCF 開発者に適している理由について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: fc93ca4c8f2a28dc4d3a0b0466d19c86273b40b8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503328"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a><span data-ttu-id="ab0f7-103">WCF 開発者向けに gRPC を推奨する理由</span><span class="sxs-lookup"><span data-stu-id="ab0f7-103">Why we recommend gRPC for WCF developers</span></span>

<span data-ttu-id="ab0f7-104">GRPC の言語と手法について詳しく説明する前に、gRPC が .NET Core に移行する Windows Communication Foundation (WCF) 開発者にとって適切なソリューションである理由について説明しておきます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-104">Before we dive deeply into the language and techniques of gRPC, it's worth discussing why gRPC is the right solution for Windows Communication Foundation (WCF) developers who want to migrate to .NET Core.</span></span>

## <a name="similarity-to-wcf"></a><span data-ttu-id="ab0f7-105">WCF との類似性</span><span class="sxs-lookup"><span data-stu-id="ab0f7-105">Similarity to WCF</span></span>

<span data-ttu-id="ab0f7-106">GRPC での実装とアプローチは異なりますが、gRPC でのサービスの開発と使用の経験は、WCF 開発者にとって直観的である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-106">Although the implementation and approach are different for gRPC, the experience of developing and consuming services with gRPC should be intuitive for WCF developers.</span></span> <span data-ttu-id="ab0f7-107">基礎となる目標は同じです。ネットワークについて心配することなく、クライアントとサーバーが同じプラットフォーム上にあるかのようにコーディングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-107">The underlying goal is the same: make it possible to code as though the client and server are on the same platform, without needing to worry about networking.</span></span> 

<span data-ttu-id="ab0f7-108">どちらのプラットフォームも、そのインターフェイスを宣言するプロセスが異なる場合でも、インターフェイスを宣言して実装するという原則を共有します。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-108">Both platforms share the principle of declaring and then implementing an interface, even though the process for declaring that interface is different.</span></span> <span data-ttu-id="ab0f7-109">また、5章で説明したように、gRPC がサポートするさまざまな種類の RPC 呼び出しは、WCF サービスで使用可能なバインドに適切にマップされています。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-109">And as you'll see in chapter 5, the different types of RPC calls that gRPC supports map well to the bindings available to WCF services.</span></span>

## <a name="benefits-of-grpc"></a><span data-ttu-id="ab0f7-110">GRPC の利点</span><span class="sxs-lookup"><span data-stu-id="ab0f7-110">Benefits of gRPC</span></span>

<span data-ttu-id="ab0f7-111">gRPC は、次の理由により他のソリューションよりも上位にあります。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-111">gRPC stands above other solutions for the following reasons.</span></span>

### <a name="performance"></a><span data-ttu-id="ab0f7-112">パフォーマンス テスト</span><span class="sxs-lookup"><span data-stu-id="ab0f7-112">Performance</span></span>

<span data-ttu-id="ab0f7-113">Http/1.1 ではなく HTTP/2 を使用すると、人間が判読できるメッセージの要件がなくなり、より小規模で高速なバイナリプロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-113">Using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller, faster binary protocol.</span></span> <span data-ttu-id="ab0f7-114">これは、コンピューターを解析する場合により効率的です。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-114">This is more efficient for computers to parse.</span></span> <span data-ttu-id="ab0f7-115">HTTP/2 は、1つの接続での多重化要求もサポートします。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-115">HTTP/2 also supports multiplexing requests over a single connection.</span></span> <span data-ttu-id="ab0f7-116">このサポートにより、キューで待機する必要がなく、準備ができたらすぐに応答を送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-116">This support enables responses to be sent as soon as they're ready without the need to wait in a queue.</span></span> <span data-ttu-id="ab0f7-117">(HTTP/1.1 では、この問題は "ヘッドライン (ホル) ブロック" と呼ばれます)。GRPC を使用する場合、必要なリソースが減少します。これにより、モバイルデバイスや低速のネットワークでの使用に適したソリューションになります。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-117">(In HTTP/1.1, this issue is known as "head-of-line (HOL) blocking.") You need fewer resources when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.</span></span>

### <a name="interoperability"></a><span data-ttu-id="ab0f7-118">相互運用性</span><span class="sxs-lookup"><span data-stu-id="ab0f7-118">Interoperability</span></span>

<span data-ttu-id="ab0f7-119">すべての主要なプログラミング言語とプラットフォーム (.NET、Java、Python、ゴー、 C++Node.js、Swift、Dart、RUBY、PHP など) 用の grpc ツールとライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-119">There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP.</span></span> <span data-ttu-id="ab0f7-120">プロトコルバッファーバイナリワイヤ形式と、各プラットフォームの効率的なコード生成により、開発者は、完全なクロスプラットフォームサポートを引き続き利用しながら、パフォーマンスに優れたアプリを構築できます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-120">Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.</span></span>

### <a name="usability-and-productivity"></a><span data-ttu-id="ab0f7-121">使いやすさと生産性</span><span class="sxs-lookup"><span data-stu-id="ab0f7-121">Usability and productivity</span></span>

<span data-ttu-id="ab0f7-122">gRPC は包括的な RPC ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-122">gRPC is a comprehensive RPC solution.</span></span> <span data-ttu-id="ab0f7-123">複数の言語とプラットフォームで一貫して動作します。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-123">It works consistently across multiple languages and platforms.</span></span> <span data-ttu-id="ab0f7-124">また、必要な定型コードの多くが自動的に生成される優れたツールも用意されています。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-124">It also provides excellent tooling, with much of the necessary boilerplate code automatically generated.</span></span> <span data-ttu-id="ab0f7-125">ビジネスロジックに専念するために、より多くの開発者時間が解放されます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-125">So more developer time is freed up to focus on business logic.</span></span>

### <a name="streaming"></a><span data-ttu-id="ab0f7-126">ストリーミング</span><span class="sxs-lookup"><span data-stu-id="ab0f7-126">Streaming</span></span>

<span data-ttu-id="ab0f7-127">gRPC には、WCF の全二重サービスに同様の機能を提供する、完全な双方向ストリーミングがあります。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-127">gRPC has full bidirectional streaming, which provides similar functionality to WCF's full duplex services.</span></span> <span data-ttu-id="ab0f7-128">gRPC ストリーミングは、通常のインターネット接続、ロードバランサー、およびサービスメッシュを介して動作できます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-128">gRPC streaming can operate over regular internet connections, load balancers, and service meshes.</span></span>

### <a name="deadlinetimeouts-and-cancellation"></a><span data-ttu-id="ab0f7-129">期限/タイムアウトとキャンセル</span><span class="sxs-lookup"><span data-stu-id="ab0f7-129">Deadline/timeouts and cancellation</span></span>

<span data-ttu-id="ab0f7-130">gRPC を使用すると、クライアントは RPC が終了するまでの最長時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-130">gRPC allows clients to specify a maximum time for an RPC to finish.</span></span> <span data-ttu-id="ab0f7-131">指定した期限を超えた場合、サーバーはクライアントとは無関係に操作を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-131">If the specified deadline is exceeded, the server can cancel the operation independently of the client.</span></span> <span data-ttu-id="ab0f7-132">期限とキャンセルは、さらに gRPC 呼び出しを通じて伝達して、リソース使用量の制限を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-132">Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits.</span></span> <span data-ttu-id="ab0f7-133">クライアントは、期限を超過した場合や、必要に応じて (ユーザーの操作によっては) 操作を停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-133">Clients can also stop operations when a deadline is exceeded, or earlier if necessary (for example, because of a user interaction).</span></span>

### <a name="security"></a><span data-ttu-id="ab0f7-134">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="ab0f7-134">Security</span></span>

<span data-ttu-id="ab0f7-135">gRPC は、TLS エンドツーエンドの暗号化接続を介して HTTP/2 を使用している場合に、暗黙的にセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-135">gRPC is implicitly secure when it's using HTTP/2 over a TLS end-to-end encrypted connection.</span></span> <span data-ttu-id="ab0f7-136">クライアント証明書認証のサポート ([第6章](security.md)を参照) は、クライアントとサーバーの間のセキュリティと信頼をさらに強化します。</span><span class="sxs-lookup"><span data-stu-id="ab0f7-136">Support for client certificate authentication (see [chapter 6](security.md)) further increases security and trust between client and server.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ab0f7-137">[前へ](network-protocols.md)
>[次へ](protocol-buffers.md)</span><span class="sxs-lookup"><span data-stu-id="ab0f7-137">[Previous](network-protocols.md)
[Next](protocol-buffers.md)</span></span>
