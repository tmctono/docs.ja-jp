---
title: サービス メッシュ通信インフラストラクチャ
description: サービス メッシュ テクノロジがクラウドネイティブマイクロサービス通信を効率化する方法を学習する
author: robvet
ms.date: 03/03/2020
ms.openlocfilehash: 8bb57e990dbf1baf8c246fe4aacfbb2904a251e6
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805751"
---
# <a name="service-mesh-communication-infrastructure"></a><span data-ttu-id="e24d2-103">サービス メッシュ通信インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="e24d2-103">Service Mesh communication infrastructure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e24d2-104">この章では、マイクロサービス通信の課題について説明しました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-104">Throughout this chapter, we've explored the challenges of microservice communication.</span></span> <span data-ttu-id="e24d2-105">開発チームは、バックエンド サービスが相互に通信する方法に注意を向ける必要があると述べています。</span><span class="sxs-lookup"><span data-stu-id="e24d2-105">We said that development teams need to be sensitive to how back-end services communicate with each other.</span></span> <span data-ttu-id="e24d2-106">理想的には、サービス間通信が少ないほど、より良い方法です。</span><span class="sxs-lookup"><span data-stu-id="e24d2-106">Ideally, the less inter-service communication, the better.</span></span> <span data-ttu-id="e24d2-107">ただし、バックエンド サービスは、多くの場合、操作を完了するために互いに依存しているので、回避は常に可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="e24d2-107">However, avoidance isn't always possible as back-end services often rely on one another to complete operations.</span></span>

<span data-ttu-id="e24d2-108">同期 HTTP 通信と非同期メッセージングを実装するためのさまざまなアプローチを検討しました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-108">We explored different approaches for implementing synchronous HTTP communication and asynchronous messaging.</span></span> <span data-ttu-id="e24d2-109">いずれの場合も、開発者は通信コードの実装に負担をかかえています。</span><span class="sxs-lookup"><span data-stu-id="e24d2-109">In each of the cases, the developer is burdened with implementing communication code.</span></span> <span data-ttu-id="e24d2-110">通信コードは複雑で時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="e24d2-110">Communication code is complex and time intensive.</span></span> <span data-ttu-id="e24d2-111">誤った決定は、パフォーマンス上の重大な問題を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e24d2-111">Incorrect decisions can lead to significant performance issues.</span></span>

<span data-ttu-id="e24d2-112">マイクロサービス通信に対するより現代的なアプローチは、*サービスメッシュ*と題された新しく急速に進化する技術を中心にしています。</span><span class="sxs-lookup"><span data-stu-id="e24d2-112">A more modern approach to microservice communication centers around a new and rapidly evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="e24d2-113">[サービス メッシュ](https://www.nginx.com/blog/what-is-a-service-mesh/)は、サービス間の通信、復元性、および多くの横断的な懸念事項を処理する組み込み機能を備えた構成可能なインフラストラクチャ 層です。</span><span class="sxs-lookup"><span data-stu-id="e24d2-113">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service-to-service communication, resiliency, and many cross-cutting concerns.</span></span> <span data-ttu-id="e24d2-114">これらの懸念事項に対する責任をマイクロサービスからサービス メッシュ層に移動します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-114">It moves the responsibility for these concerns out of the microservices and into service mesh layer.</span></span> <span data-ttu-id="e24d2-115">通信は、マイクロサービスから分離されます。</span><span class="sxs-lookup"><span data-stu-id="e24d2-115">Communication is abstracted away from your microservices.</span></span>

<span data-ttu-id="e24d2-116">サービス メッシュの重要なコンポーネントはプロキシです。</span><span class="sxs-lookup"><span data-stu-id="e24d2-116">A key component of a service mesh is a proxy.</span></span> <span data-ttu-id="e24d2-117">クラウド ネイティブ アプリケーションでは、プロキシのインスタンスは通常、各マイクロサービスと共に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e24d2-117">In a cloud-native application, an instance of a proxy is typically colocated with each microservice.</span></span> <span data-ttu-id="e24d2-118">これらは別々のプロセスで実行されますが、2 つは密接にリンクされており、同じライフサイクルを共有します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-118">While they execute in separate processes, the two are closely linked and share the same lifecycle.</span></span> <span data-ttu-id="e24d2-119">このパターンは[、Sidecar パターン](https://docs.microsoft.com/azure/architecture/patterns/sidecar)と呼ばれ、図 4-24 に示されています。</span><span class="sxs-lookup"><span data-stu-id="e24d2-119">This pattern, known as the [Sidecar pattern](https://docs.microsoft.com/azure/architecture/patterns/sidecar), and is shown in Figure 4-24.</span></span>

![サイドカーを使用したサービスメッシュ](./media/service-mesh-with-side-car.png)

<span data-ttu-id="e24d2-121">**図 4-24**</span><span class="sxs-lookup"><span data-stu-id="e24d2-121">**Figure 4-24**.</span></span> <span data-ttu-id="e24d2-122">サイドカーを使用したサービスメッシュ</span><span class="sxs-lookup"><span data-stu-id="e24d2-122">Service mesh with a side car</span></span>

<span data-ttu-id="e24d2-123">前の図では、各マイクロサービスと一緒に実行されるプロキシによってメッセージが傍受される方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e24d2-123">Note in the previous figure how messages are intercepted by a proxy that runs alongside each microservice.</span></span> <span data-ttu-id="e24d2-124">各プロキシは、マイクロサービスに固有のトラフィック ルールで構成できます。</span><span class="sxs-lookup"><span data-stu-id="e24d2-124">Each proxy can be configured with traffic rules specific to the microservice.</span></span> <span data-ttu-id="e24d2-125">メッセージを理解し、サービスや外部にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="e24d2-125">It understands messages and can route them across your services and the outside world.</span></span>

<span data-ttu-id="e24d2-126">サービス間通信の管理に加えて、サービス・メッシュはサービス検出と負荷分散をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e24d2-126">Along with managing service-to-service communication, the Service Mesh provides support for service discovery and load balancing.</span></span>

<span data-ttu-id="e24d2-127">設定すると、サービス メッシュは高機能になります。</span><span class="sxs-lookup"><span data-stu-id="e24d2-127">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="e24d2-128">メッシュは、サービス検索エンドポイントから対応するインスタンスプールを取得します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-128">The mesh retrieves a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="e24d2-129">要求を特定のサービス インスタンスに送信し、結果の待機時間と応答の種類を記録します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-129">It sends a request to a specific service instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="e24d2-130">最近の要求に対して観察された待機時間など、さまざまな要因に基づいて高速応答を返す可能性が最も高いインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-130">It chooses the instance most likely to return a fast response based on different factors, including the observed latency for recent requests.</span></span>

<span data-ttu-id="e24d2-131">サービス メッシュは、トラフィック、通信、およびネットワークの問題をアプリケーション レベルで管理します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-131">A service mesh manages traffic, communication, and networking concerns at the application level.</span></span> <span data-ttu-id="e24d2-132">メッセージと要求を理解します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-132">It understands messages and requests.</span></span> <span data-ttu-id="e24d2-133">通常、サービス メッシュはコンテナー オーケストレーターと統合されます。</span><span class="sxs-lookup"><span data-stu-id="e24d2-133">A service mesh typically integrates with a container orchestrator.</span></span> <span data-ttu-id="e24d2-134">Kubernetes は、サービス メッシュを追加できる拡張可能なアーキテクチャをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e24d2-134">Kubernetes supports an extensible architecture in which a service mesh can be added.</span></span>

<span data-ttu-id="e24d2-135">第 6 章では、アーキテクチャと利用可能なオープン ソース実装に関する議論を含む、Service Mesh テクノロジについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e24d2-135">In chapter 6, we deep-dive into Service Mesh technologies including a discussion on its architecture and available open-source implementations.</span></span>

## <a name="summary"></a><span data-ttu-id="e24d2-136">まとめ</span><span class="sxs-lookup"><span data-stu-id="e24d2-136">Summary</span></span>

<span data-ttu-id="e24d2-137">この章では、クラウドネイティブの通信パターンについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-137">In this chapter, we discussed cloud-native communication patterns.</span></span> <span data-ttu-id="e24d2-138">まず、フロントエンド クライアントがバックエンド マイクロサービスと通信する方法を調べることから始めました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-138">We started by examining how front-end clients communicate with back-end microservices.</span></span> <span data-ttu-id="e24d2-139">その過程で、APIゲートウェイプラットフォームとリアルタイムコミュニケーションについて話しました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-139">Along the way, we talked about API Gateway platforms and real-time communication.</span></span> <span data-ttu-id="e24d2-140">次に、マイクロサービスが他のバックエンド サービスと通信する方法を確認しました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-140">We then looked at how microservices communicate with other back-end services.</span></span> <span data-ttu-id="e24d2-141">ここでは、同期 HTTP 通信と非同期メッセージングの両方を複数のサービスで見ました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-141">We looked at both synchronous HTTP communication and asynchronous messaging across services.</span></span> <span data-ttu-id="e24d2-142">クラウドネイティブの世界で今後の技術であるgRPCを取り上げました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-142">We covered gRPC, an upcoming technology in the cloud-native world.</span></span> <span data-ttu-id="e24d2-143">最後に、マイクロサービス通信を合理化できる「Service Mesh」という新しい急速に進化する技術を導入しました。</span><span class="sxs-lookup"><span data-stu-id="e24d2-143">Finally, we introduced a new and rapidly evolving technology entitled Service Mesh that can streamline microservice communication.</span></span>

<span data-ttu-id="e24d2-144">クラウド ネイティブ システムでの通信の実装に役立つマネージド Azure サービスに特に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="e24d2-144">Special emphasis was on managed Azure services that can help implement communication in cloud-native systems:</span></span>

- [<span data-ttu-id="e24d2-145">Azure アプリケーション ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="e24d2-145">Azure Application Gateway</span></span>](https://docs.microsoft.com/azure/application-gateway/overview)
- [<span data-ttu-id="e24d2-146">Azure API Management</span><span class="sxs-lookup"><span data-stu-id="e24d2-146">Azure API Management</span></span>](https://azure.microsoft.com/services/api-management/)
- [<span data-ttu-id="e24d2-147">Azure SignalR Service</span><span class="sxs-lookup"><span data-stu-id="e24d2-147">Azure SignalR Service</span></span>](https://azure.microsoft.com/services/signalr-service/)
- [<span data-ttu-id="e24d2-148">Azure Storage キュー</span><span class="sxs-lookup"><span data-stu-id="e24d2-148">Azure Storage Queues</span></span>](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [<span data-ttu-id="e24d2-149">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="e24d2-149">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [<span data-ttu-id="e24d2-150">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="e24d2-150">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
- [<span data-ttu-id="e24d2-151">Azure Event Hub</span><span class="sxs-lookup"><span data-stu-id="e24d2-151">Azure Event Hub</span></span>](https://azure.microsoft.com/services/event-hubs/)

<span data-ttu-id="e24d2-152">次に、クラウドネイティブシステムで分散データを導入し、そのメリットと課題を抱えています。</span><span class="sxs-lookup"><span data-stu-id="e24d2-152">We next move to distributed data in cloud-native systems and the benefits and challenges that it presents.</span></span>

### <a name="references"></a><span data-ttu-id="e24d2-153">References</span><span class="sxs-lookup"><span data-stu-id="e24d2-153">References</span></span>

- [<span data-ttu-id="e24d2-154">.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e24d2-154">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="e24d2-155">マイクロサービスのサービス間通信の設計</span><span class="sxs-lookup"><span data-stu-id="e24d2-155">Designing Interservice Communication for Microservices</span></span>](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [<span data-ttu-id="e24d2-156">Azure SignalR サービスは、リアルタイム機能を追加する完全に管理されたサービスです。</span><span class="sxs-lookup"><span data-stu-id="e24d2-156">Azure SignalR Service, a fully managed service to add real-time functionality</span></span>](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [<span data-ttu-id="e24d2-157">Azure API ゲートウェイイングレス コントローラー</span><span class="sxs-lookup"><span data-stu-id="e24d2-157">Azure API Gateway Ingress Controller</span></span>](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [<span data-ttu-id="e24d2-158">Azure Kubernetes サービス (AKS) での入力について</span><span class="sxs-lookup"><span data-stu-id="e24d2-158">About Ingress in Azure Kubernetes Service (AKS)</span></span>](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [<span data-ttu-id="e24d2-159">gRPC ドキュメント</span><span class="sxs-lookup"><span data-stu-id="e24d2-159">gRPC Documentation</span></span>](https://grpc.io/docs/guides/)

- [<span data-ttu-id="e24d2-160">WCF 開発者向け gRPC</span><span class="sxs-lookup"><span data-stu-id="e24d2-160">gRPC for WCF Developers</span></span>](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)

- [<span data-ttu-id="e24d2-161">gRPC サービスと HTTP API の比較</span><span class="sxs-lookup"><span data-stu-id="e24d2-161">Comparing gRPC Services with HTTP APIs</span></span>](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [<span data-ttu-id="e24d2-162">NET ビデオを使用した gRPC サービスの構築</span><span class="sxs-lookup"><span data-stu-id="e24d2-162">Building gRPC Services with .NET video</span></span>](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
><span data-ttu-id="e24d2-163">[前へ](grpc.md)
>[次へ](database-per-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="e24d2-163">[Previous](grpc.md)
[Next](database-per-microservice.md)</span></span>
