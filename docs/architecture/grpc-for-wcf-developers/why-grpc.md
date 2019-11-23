---
title: Wcf 開発者向けに gRPC を使用することをお勧めする理由 (WCF 開発者向け)
description: 最新のアーキテクチャとプラットフォームへの移行を検討している WCF 開発者に gRPC が適している理由について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: da712e1ceee92f0a1a2661252dcda602f5dde9a0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966941"
---
# <a name="why-grpc-is-recommended-for-wcf-developers"></a><span data-ttu-id="d4fc2-103">WCF 開発者に gRPC が推奨される理由</span><span class="sxs-lookup"><span data-stu-id="d4fc2-103">Why gRPC is recommended for WCF developers</span></span>

<span data-ttu-id="d4fc2-104">Grpc の言語と手法について詳しく説明する前に、gRPC が、.NET Core に移行する WCF 開発者にとって適切なソリューションである理由について説明します。これは、代替手段があることを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-104">Before diving deeply into the language and techniques of gRPC, it's worth discussing why gRPC is the right solution for WCF developers who want to migrate to .NET Core, given there are alternatives available.</span></span>

## <a name="similarity-to-wcf"></a><span data-ttu-id="d4fc2-105">WCF との類似性</span><span class="sxs-lookup"><span data-stu-id="d4fc2-105">Similarity to WCF</span></span>

<span data-ttu-id="d4fc2-106">実装とアプローチは異なりますが、gRPC でサービスを開発して使用する実際のエクスペリエンスは、WCF 開発者にとって非常に直感的です。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-106">Although its implementation and approach is different, the actual experience of developing and consuming services with gRPC should be very intuitive for WCF developers.</span></span> <span data-ttu-id="d4fc2-107">ネットワークを気にすることなく、クライアントとサーバーが同じプラットフォーム上にあるかのようにコードを記述できるという、根本的な目標は同じです。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-107">The underlying goal of making it possible to code as though the client and server were on the same platform, without needing to worry about networking, is the same.</span></span> <span data-ttu-id="d4fc2-108">どちらのプラットフォームも、そのインターフェイスを宣言するプロセスが異なる場合でも、インターフェイスを宣言して実装するという原則を共有します。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-108">Both platforms share the principle of declaring and then implementing an interface, even though the process for declaring that interface is different.</span></span> <span data-ttu-id="d4fc2-109">また、「5章」に示されているように、gRPC マップでサポートされているさまざまな種類の RPC 呼び出しは、WCF サービスで使用できるさまざまなバインドに対して非常に優れています。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-109">And as you'll see in chapter 5, the different types of RPC calls supported by gRPC map very well to the different bindings available to WCF services.</span></span>

## <a name="benefits-of-grpc"></a><span data-ttu-id="d4fc2-110">GRPC の利点</span><span class="sxs-lookup"><span data-stu-id="d4fc2-110">Benefits of gRPC</span></span>

<span data-ttu-id="d4fc2-111">GRPC が他のソリューションを上回る理由としては、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-111">Additional reasons why gRPC stands above other solutions are:</span></span>

### <a name="performance"></a><span data-ttu-id="d4fc2-112">パフォーマンス テスト</span><span class="sxs-lookup"><span data-stu-id="d4fc2-112">Performance</span></span>

<span data-ttu-id="d4fc2-113">既に説明したように、http/1.1 ではなく HTTP/2 を使用すると、人間が判読できるメッセージの要件がなくなり、より高速なバイナリプロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-113">As already discussed, using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller faster binary protocol.</span></span> <span data-ttu-id="d4fc2-114">これは、コンピューターを解析する場合により効率的です。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-114">This is more efficient for computers to parse.</span></span> <span data-ttu-id="d4fc2-115">また、HTTP/2 では、単一の接続での多重化要求がサポートされています。これにより、キューで待機しなくても応答がすぐに送信されるようになります ("ヘッドライン (ホル) ブロック" と呼ばれる HTTP/1.1 の問題)。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-115">HTTP/2 also supports multiplexing requests over a single connection enabling responses to be sent as soon as they're ready without the need to wait in a queue (an issue in HTTP/1.1 known as "head-of-line (HOL) blocking").</span></span> <span data-ttu-id="d4fc2-116">GRPC を使用する場合に必要なリソースが減少します。これにより、モバイルデバイスや低速のネットワークでの使用に適したソリューションになります。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-116">Fewer resources are needed when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.</span></span>

### <a name="interoperability"></a><span data-ttu-id="d4fc2-117">相互運用性</span><span class="sxs-lookup"><span data-stu-id="d4fc2-117">Interoperability</span></span>

<span data-ttu-id="d4fc2-118">すべての主要なプログラミング言語とプラットフォーム (.NET、Java、Python、ゴー、 C++Node.js、Swift、Dart、RUBY、PHP など) 用の grpc ツールとライブラリがあります。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-118">There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP.</span></span> <span data-ttu-id="d4fc2-119">プロトコルバッファーバイナリワイヤ形式と、各プラットフォームの効率的なコード生成により、開発者は、完全なクロスプラットフォームサポートを引き続き利用しながら、パフォーマンスに優れたアプリを構築できます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-119">Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.</span></span>

### <a name="usability-and-productivity"></a><span data-ttu-id="d4fc2-120">使いやすさと生産性</span><span class="sxs-lookup"><span data-stu-id="d4fc2-120">Usability and productivity</span></span>

<span data-ttu-id="d4fc2-121">gRPC は包括的な RPC ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-121">gRPC is a comprehensive RPC solution.</span></span> <span data-ttu-id="d4fc2-122">この機能は、複数の言語やプラットフォームで一貫して動作し、必要な定型コードの大部分が自動生成された優れたツールを提供します。これにより、ビジネスロジックに重点を置いて開発者の時間を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-122">It works consistently across multiple languages and platforms, and provides excellent tooling, with much of the necessary boilerplate code auto-generated, so more developer time is freed up to focus on business logic.</span></span>

### <a name="streaming"></a><span data-ttu-id="d4fc2-123">ストリーミング</span><span class="sxs-lookup"><span data-stu-id="d4fc2-123">Streaming</span></span>

<span data-ttu-id="d4fc2-124">gRPC には、WCF の完全な双方向サービスに非常に類似した機能を提供する完全な双方向ストリーミングがあります。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-124">gRPC has full bidirectional streaming, which provides very similar functionality to WCF's full duplex services.</span></span> <span data-ttu-id="d4fc2-125">gRPC ストリーミングは、通常のインターネット接続、ロードバランサー、およびサービスメッシュを介して動作できます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-125">gRPC streaming can operate over regular internet connections, load balancers, and service meshes.</span></span>

### <a name="deadlinetimeouts-and-cancellation"></a><span data-ttu-id="d4fc2-126">期限/タイムアウトとキャンセル</span><span class="sxs-lookup"><span data-stu-id="d4fc2-126">Deadline/timeouts and cancellation</span></span>

<span data-ttu-id="d4fc2-127">gRPC を使用すると、クライアントは RPC が完了するまでの最長時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-127">gRPC allows clients to specify a maximum time for an RPC to complete.</span></span> <span data-ttu-id="d4fc2-128">指定した期限を超えた場合、サーバーはクライアントとは無関係に操作を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-128">If the specified deadline is exceeded the server can cancel the operation independently of the client.</span></span> <span data-ttu-id="d4fc2-129">期限とキャンセルは、さらに gRPC 呼び出しを通じて伝達して、リソース使用量の制限を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-129">Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits.</span></span> <span data-ttu-id="d4fc2-130">クライアントは、期限を超過した場合や、必要に応じて (ユーザーの操作によっては) 操作を中止する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-130">Clients may also abort operations when a deadline is exceeded, or earlier if necessary (e.g. due to a user interaction).</span></span>

### <a name="security"></a><span data-ttu-id="d4fc2-131">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d4fc2-131">Security</span></span>

<span data-ttu-id="d4fc2-132">gRPC は、TLS エンドツーエンドの暗号化接続を介して HTTP/2 を使用すると、暗黙的にセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-132">gRPC is implicitly secure when using HTTP/2 over an TLS end-to-end encrypted connection.</span></span> <span data-ttu-id="d4fc2-133">クライアント証明書認証のサポート (第6章を参照) は、クライアントとサーバーの間のセキュリティと信頼をさらに強化します。</span><span class="sxs-lookup"><span data-stu-id="d4fc2-133">Support for Client Certificate authentication (see chapter 6) further increases security and trust between client and server.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d4fc2-134">[前へ](network-protocols.md)
>[次へ](protocol-buffers.md)</span><span class="sxs-lookup"><span data-stu-id="d4fc2-134">[Previous](network-protocols.md)
[Next](protocol-buffers.md)</span></span>
