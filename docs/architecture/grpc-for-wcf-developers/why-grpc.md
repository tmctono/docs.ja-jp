---
title: WCF 開発者に gRPC を推奨する理由 - WCF 開発者向け gRPC
description: gRPC が、最新のアーキテクチャとプラットフォームに移行する WCF 開発者に適している理由について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: 664781e94c24c1796eafa6a70eb28d453b530d66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147647"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a><span data-ttu-id="b6258-103">WCF 開発者に gRPC を推奨する理由</span><span class="sxs-lookup"><span data-stu-id="b6258-103">Why we recommend gRPC for WCF developers</span></span>

<span data-ttu-id="b6258-104">gRPC の言語とテクニックについて詳しく説明する前に、.NET Core に移行する Windows コミュニケーション ファウンデーション (WCF) 開発者にとって gRPC が適切なソリューションである理由を説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6258-104">Before we dive deeply into the language and techniques of gRPC, it's worth discussing why gRPC is the right solution for Windows Communication Foundation (WCF) developers who want to migrate to .NET Core.</span></span>

## <a name="similarity-to-wcf"></a><span data-ttu-id="b6258-105">WCF との類似性</span><span class="sxs-lookup"><span data-stu-id="b6258-105">Similarity to WCF</span></span>

<span data-ttu-id="b6258-106">実装とアプローチは gRPC では異なりますが、gRPC を使用したサービスの開発と使用の経験は、WCF 開発者にとって直感的な操作性を備えている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6258-106">Although the implementation and approach are different for gRPC, the experience of developing and consuming services with gRPC should be intuitive for WCF developers.</span></span> <span data-ttu-id="b6258-107">基本的な目標は、クライアントとサーバーが同じプラットフォーム上にあるかのようにコーディングできるように、ネットワークを気にすることなく、同じことです。</span><span class="sxs-lookup"><span data-stu-id="b6258-107">The underlying goal is the same: make it possible to code as though the client and server are on the same platform, without needing to worry about networking.</span></span>

<span data-ttu-id="b6258-108">どちらのプラットフォームも、インターフェイスを宣言し、そのインターフェイスを実装する際のプロセスが異なっていても、インターフェイスを宣言してから実装するという原則を共有しています。</span><span class="sxs-lookup"><span data-stu-id="b6258-108">Both platforms share the principle of declaring and then implementing an interface, even though the process for declaring that interface is different.</span></span> <span data-ttu-id="b6258-109">5 章で説明するように、gRPC がサポートするさまざまな種類の RPC 呼び出しは、WCF サービスで使用できるバインドに適したマップに対応しています。</span><span class="sxs-lookup"><span data-stu-id="b6258-109">And as you'll see in chapter 5, the different types of RPC calls that gRPC supports map well to the bindings available to WCF services.</span></span>

## <a name="benefits-of-grpc"></a><span data-ttu-id="b6258-110">gRPC の利点</span><span class="sxs-lookup"><span data-stu-id="b6258-110">Benefits of gRPC</span></span>

<span data-ttu-id="b6258-111">gRPCは、次の理由で他のソリューションの上に立っています。</span><span class="sxs-lookup"><span data-stu-id="b6258-111">gRPC stands above other solutions for the following reasons.</span></span>

### <a name="performance"></a><span data-ttu-id="b6258-112">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="b6258-112">Performance</span></span>

<span data-ttu-id="b6258-113">HTTP/1.1 ではなく HTTP/2 を使用すると、人間が読めるメッセージの要件がなくなります。</span><span class="sxs-lookup"><span data-stu-id="b6258-113">Using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller, faster binary protocol.</span></span> <span data-ttu-id="b6258-114">これは、コンピューターの解析の方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="b6258-114">This is more efficient for computers to parse.</span></span> <span data-ttu-id="b6258-115">HTTP/2 は、単一の接続での要求の多重化もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b6258-115">HTTP/2 also supports multiplexing requests over a single connection.</span></span> <span data-ttu-id="b6258-116">このサポートにより、応答はキューで待機する必要なく、準備が整ったらすぐに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b6258-116">This support enables responses to be sent as soon as they're ready without the need to wait in a queue.</span></span> <span data-ttu-id="b6258-117">(HTTP/1.1 では、この問題は "ヘッド オブ ライン (HOL) ブロッキング" と呼ばれます。gRPC を使用する場合はリソースが少なくて済むため、モバイル デバイスや低速ネットワークで使用するソリューションとして適しています。</span><span class="sxs-lookup"><span data-stu-id="b6258-117">(In HTTP/1.1, this issue is known as "head-of-line (HOL) blocking.") You need fewer resources when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.</span></span>

### <a name="interoperability"></a><span data-ttu-id="b6258-118">相互運用性</span><span class="sxs-lookup"><span data-stu-id="b6258-118">Interoperability</span></span>

<span data-ttu-id="b6258-119">.NET、Java、Python、Go、C++、Node.js、スウィフト、ダート、ルビー、PHPなど、すべての主要なプログラミング言語とプラットフォーム用のgRPCツールとライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="b6258-119">There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP.</span></span> <span data-ttu-id="b6258-120">Protocol Buffers バイナリ ワイヤ形式と各プラットフォームの効率的なコード生成により、開発者は完全なクロスプラットフォーム サポートを利用しながら、パフォーマンスの高いアプリを構築できます。</span><span class="sxs-lookup"><span data-stu-id="b6258-120">Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.</span></span>

### <a name="usability-and-productivity"></a><span data-ttu-id="b6258-121">使いやすさと生産性</span><span class="sxs-lookup"><span data-stu-id="b6258-121">Usability and productivity</span></span>

<span data-ttu-id="b6258-122">gRPC は包括的な RPC ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b6258-122">gRPC is a comprehensive RPC solution.</span></span> <span data-ttu-id="b6258-123">複数の言語とプラットフォームで一貫して動作します。</span><span class="sxs-lookup"><span data-stu-id="b6258-123">It works consistently across multiple languages and platforms.</span></span> <span data-ttu-id="b6258-124">また、必要な定型コードの多くが自動的に生成され、優れたツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="b6258-124">It also provides excellent tooling, with much of the necessary boilerplate code automatically generated.</span></span> <span data-ttu-id="b6258-125">そのため、ビジネス ロジックに集中するために、開発者の時間が増えます。</span><span class="sxs-lookup"><span data-stu-id="b6258-125">So more developer time is freed up to focus on business logic.</span></span>

### <a name="streaming"></a><span data-ttu-id="b6258-126">ストリーミング</span><span class="sxs-lookup"><span data-stu-id="b6258-126">Streaming</span></span>

<span data-ttu-id="b6258-127">gRPC には、WCF の全二重サービスと同様の機能を提供する、双方向の全方向ストリーミングがあります。</span><span class="sxs-lookup"><span data-stu-id="b6258-127">gRPC has full bidirectional streaming, which provides similar functionality to WCF's full duplex services.</span></span> <span data-ttu-id="b6258-128">gRPC ストリーミングは、通常のインターネット接続、ロード バランサー、サービス メッシュを介して動作できます。</span><span class="sxs-lookup"><span data-stu-id="b6258-128">gRPC streaming can operate over regular internet connections, load balancers, and service meshes.</span></span>

### <a name="deadlinetimeouts-and-cancellation"></a><span data-ttu-id="b6258-129">締切/タイムアウトとキャンセル</span><span class="sxs-lookup"><span data-stu-id="b6258-129">Deadline/timeouts and cancellation</span></span>

<span data-ttu-id="b6258-130">gRPC を使用すると、クライアントは RPC が終了するまでの最大時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6258-130">gRPC allows clients to specify a maximum time for an RPC to finish.</span></span> <span data-ttu-id="b6258-131">指定された期限を超えた場合、サーバーはクライアントとは別に操作を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="b6258-131">If the specified deadline is exceeded, the server can cancel the operation independently of the client.</span></span> <span data-ttu-id="b6258-132">期限と取り消しは、リソースの使用制限を強制するために、さらに gRPC 呼び出しを通じて伝達できます。</span><span class="sxs-lookup"><span data-stu-id="b6258-132">Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits.</span></span> <span data-ttu-id="b6258-133">クライアントは、期限を超えた場合や、必要に応じて (たとえば、ユーザー操作が原因で) 操作を停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6258-133">Clients can also stop operations when a deadline is exceeded, or earlier if necessary (for example, because of a user interaction).</span></span>

### <a name="security"></a><span data-ttu-id="b6258-134">Security</span><span class="sxs-lookup"><span data-stu-id="b6258-134">Security</span></span>

<span data-ttu-id="b6258-135">gRPC は、TLS エンドツーエンドの暗号化接続で HTTP/2 を使用している場合、暗黙的にセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="b6258-135">gRPC is implicitly secure when it's using HTTP/2 over a TLS end-to-end encrypted connection.</span></span> <span data-ttu-id="b6258-136">クライアント証明書認証のサポート ([第 6 章](security.md)を参照) により、クライアントとサーバー間のセキュリティと信頼がさらに強化されます。</span><span class="sxs-lookup"><span data-stu-id="b6258-136">Support for client certificate authentication (see [chapter 6](security.md)) further increases security and trust between client and server.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b6258-137">[前次](network-protocols.md)
>[Next](protocol-buffers.md)</span><span class="sxs-lookup"><span data-stu-id="b6258-137">[Previous](network-protocols.md)
[Next](protocol-buffers.md)</span></span>
