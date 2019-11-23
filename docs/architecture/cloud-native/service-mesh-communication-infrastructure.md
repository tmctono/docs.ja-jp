---
title: サービス メッシュ通信インフラストラクチャ
description: サービスメッシュテクノロジがクラウドネイティブマイクロサービス通信を効率化するしくみについて説明します
author: robvet
ms.date: 09/10/2019
ms.openlocfilehash: a9192bf9f5827d05b2453c796c72e11782f9f911
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "73841283"
---
# <a name="service-mesh-communication-infrastructure"></a><span data-ttu-id="8832c-103">サービス メッシュ通信インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="8832c-103">Service Mesh communication infrastructure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="8832c-104">この章では、マイクロサービス通信の課題について詳しく説明しました。</span><span class="sxs-lookup"><span data-stu-id="8832c-104">Throughout this chapter, we've explored the challenges of microservice communication.</span></span> <span data-ttu-id="8832c-105">開発チームは、バックエンドサービスが相互に通信する方法を重視する必要があると言いました。</span><span class="sxs-lookup"><span data-stu-id="8832c-105">We said that development teams need to be sensitive to how back-end services communicate with each other.</span></span> <span data-ttu-id="8832c-106">理想的には、サービス間の通信が少なくて済むということです。</span><span class="sxs-lookup"><span data-stu-id="8832c-106">Ideally, the less inter-service communication, the better.</span></span> <span data-ttu-id="8832c-107">ただし、バックエンドサービスが操作の完了に相互に依存していることが多いため、回避することは常に可能であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="8832c-107">However, avoidance isn't always possible as back-end services often rely on one another to complete operations.</span></span>

<span data-ttu-id="8832c-108">同期 HTTP 通信と非同期メッセージングを実装するためのさまざまなアプローチについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8832c-108">We explored different approaches for implementing synchronous HTTP communication and asynchronous messaging.</span></span> <span data-ttu-id="8832c-109">各ケースでは、開発者はコミュニケーションコードを実装する負担になります。</span><span class="sxs-lookup"><span data-stu-id="8832c-109">In each of the cases, the developer is burdened with implementing communication code.</span></span> <span data-ttu-id="8832c-110">通信コードは複雑で時間のかかる作業です。</span><span class="sxs-lookup"><span data-stu-id="8832c-110">Communication code is complex and time intensive.</span></span> <span data-ttu-id="8832c-111">不適切な決定を行うと、パフォーマンスに大きな問題が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8832c-111">Incorrect decisions can lead to significant performance issues.</span></span>

<span data-ttu-id="8832c-112">*サービスメッシュ*を利用して、新しい急速に進化するテクノロジを中心としたマイクロサービス通信センターのより新しいアプローチ。</span><span class="sxs-lookup"><span data-stu-id="8832c-112">A more modern approach to microservice communication centers around a new and rapidly evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="8832c-113">[サービスメッシュ](https://www.nginx.com/blog/what-is-a-service-mesh/)は、サービス間の通信、回復性、およびさまざまな横断的懸念を処理する組み込みの機能を備えた、構成可能なインフラストラクチャレイヤーです。</span><span class="sxs-lookup"><span data-stu-id="8832c-113">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service-to-service communication, resiliency, and many cross-cutting concerns.</span></span> <span data-ttu-id="8832c-114">これらの懸念事項については、マイクロサービスからサービスメッシュレイヤーに移行します。</span><span class="sxs-lookup"><span data-stu-id="8832c-114">It moves the responsibility for these concerns out of the microservices and into service mesh layer.</span></span> <span data-ttu-id="8832c-115">マイクロサービスからは、通信が抽象化されます。</span><span class="sxs-lookup"><span data-stu-id="8832c-115">Communication is abstracted away from your microservices.</span></span>

<span data-ttu-id="8832c-116">サービスメッシュの重要なコンポーネントはプロキシです。</span><span class="sxs-lookup"><span data-stu-id="8832c-116">A key component of a service mesh is a proxy.</span></span> <span data-ttu-id="8832c-117">クラウドネイティブアプリケーションでは、通常、プロキシのインスタンスは各マイクロサービスと共存します。</span><span class="sxs-lookup"><span data-stu-id="8832c-117">In a cloud-native application, an instance of a proxy is typically colocated with each microservice.</span></span> <span data-ttu-id="8832c-118">異なるプロセスで実行されますが、2つは密接にリンクされ、同じライフサイクルを共有します。</span><span class="sxs-lookup"><span data-stu-id="8832c-118">While they execute in separate processes, the two are closely linked and share the same lifecycle.</span></span> <span data-ttu-id="8832c-119">このパターンは、サイドカー[パターン](https://docs.microsoft.com/azure/architecture/patterns/sidecar)として知られており、図4-23 に示しています。</span><span class="sxs-lookup"><span data-stu-id="8832c-119">This pattern, known as the [Sidecar pattern](https://docs.microsoft.com/azure/architecture/patterns/sidecar), and is shown in Figure 4-23.</span></span>

![サイドカーを使用したサービスメッシュ](./media/service-mesh-with-side-car.png)

<span data-ttu-id="8832c-121">**図 4-23**.</span><span class="sxs-lookup"><span data-stu-id="8832c-121">**Figure 4-23**.</span></span> <span data-ttu-id="8832c-122">サイドカーを使用したサービスメッシュ</span><span class="sxs-lookup"><span data-stu-id="8832c-122">Service mesh with a side car</span></span>

<span data-ttu-id="8832c-123">前の図では、各マイクロサービスと共に実行されるプロキシによってメッセージが傍受されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8832c-123">Note in the previous figure how messages are intercepted by a proxy that runs alongside each microservice.</span></span> <span data-ttu-id="8832c-124">各プロキシは、マイクロサービスに固有のトラフィックルールを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="8832c-124">Each proxy can be configured with traffic rules specific to the microservice.</span></span> <span data-ttu-id="8832c-125">メッセージを認識し、サービスや外部との間でルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="8832c-125">It understands messages and can route them across your services and the outside world.</span></span>

<span data-ttu-id="8832c-126">サービス間通信の管理と共に、サービスメッシュはサービス検出と負荷分散のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="8832c-126">Along with managing service-to-service communication, the Service Mesh provides support for service discovery and load balancing.</span></span>

<span data-ttu-id="8832c-127">構成が完了すると、サービスメッシュが非常に機能します。</span><span class="sxs-lookup"><span data-stu-id="8832c-127">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="8832c-128">メッシュは、サービス探索エンドポイントから、対応するインスタンスのプールを取得します。</span><span class="sxs-lookup"><span data-stu-id="8832c-128">The mesh retrieves a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="8832c-129">このメソッドは、特定のサービスインスタンスに要求を送信し、結果の待機時間と応答の種類を記録します。</span><span class="sxs-lookup"><span data-stu-id="8832c-129">It sends a request to a specific service instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="8832c-130">これは、最近の要求の待機時間など、さまざまな要因に基づいて高速な応答を返す可能性の高いインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="8832c-130">It chooses the instance most likely to return a fast response based on different factors, including the observed latency for recent requests.</span></span>

<span data-ttu-id="8832c-131">サービスメッシュは、トラフィック、通信、およびネットワークの問題をアプリケーションレベルで管理します。</span><span class="sxs-lookup"><span data-stu-id="8832c-131">A service mesh manages traffic, communication, and networking concerns at the application level.</span></span> <span data-ttu-id="8832c-132">メッセージと要求を認識します。</span><span class="sxs-lookup"><span data-stu-id="8832c-132">It understands messages and requests.</span></span> <span data-ttu-id="8832c-133">通常、サービスメッシュはコンテナー orchestrator と統合されます。</span><span class="sxs-lookup"><span data-stu-id="8832c-133">A service mesh typically integrates with a container orchestrator.</span></span> <span data-ttu-id="8832c-134">Kubernetes は、サービスメッシュを追加できる拡張可能なアーキテクチャをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8832c-134">Kubernetes supports an extensible architecture in which a service mesh can be added.</span></span>

<span data-ttu-id="8832c-135">6章では、アーキテクチャと使用可能なオープンソースの実装に関する議論など、サービスメッシュテクノロジについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8832c-135">In chapter 6, we deep-dive into Service Mesh technologies including a discussion on its architecture and available open-source implementations.</span></span>

## <a name="summary"></a><span data-ttu-id="8832c-136">概要</span><span class="sxs-lookup"><span data-stu-id="8832c-136">Summary</span></span>

<span data-ttu-id="8832c-137">この章では、クラウドネイティブの通信パターンについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="8832c-137">In this chapter, we discussed cloud-native communication patterns.</span></span> <span data-ttu-id="8832c-138">まず、フロントエンドクライアントがバックエンドマイクロサービスと通信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8832c-138">We started by examining how front-end clients communicate with back-end microservices.</span></span> <span data-ttu-id="8832c-139">その過程で、API ゲートウェイのプラットフォームとリアルタイム通信について説明します。</span><span class="sxs-lookup"><span data-stu-id="8832c-139">Along the way, we talked about API Gateway platforms and real-time communication.</span></span> <span data-ttu-id="8832c-140">次に、マイクロサービスが他のバックエンドサービスと通信する方法について見ていきます。</span><span class="sxs-lookup"><span data-stu-id="8832c-140">We then looked at how microservices communicate with other back-end services.</span></span> <span data-ttu-id="8832c-141">サービス間の同期 HTTP 通信と非同期メッセージングの両方を検討しました。</span><span class="sxs-lookup"><span data-stu-id="8832c-141">We looked at both synchronous HTTP communication and asynchronous messaging across services.</span></span> <span data-ttu-id="8832c-142">GRPC は、クラウドネイティブ環境における今後のテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="8832c-142">We covered gRPC, an upcoming technology in the cloud-native world.</span></span> <span data-ttu-id="8832c-143">最後に、マイクロサービスの通信を効率化することができる、サービスメッシュを持つ、急速に進化する新しいテクノロジが導入されました。</span><span class="sxs-lookup"><span data-stu-id="8832c-143">Finally, we introduced a new and rapidly evolving technology entitled Service Mesh that can streamline microservice communication.</span></span>

<span data-ttu-id="8832c-144">クラウドネイティブシステムでの通信の実装に役立つ、管理された Azure サービスに特に重点を置いていました。</span><span class="sxs-lookup"><span data-stu-id="8832c-144">Special emphasis was on managed Azure services that can help implement communication in cloud-native systems:</span></span>

- [<span data-ttu-id="8832c-145">Azure アプリケーションゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="8832c-145">Azure Application Gateway</span></span>](https://docs.microsoft.com/azure/application-gateway/overview)
- [<span data-ttu-id="8832c-146">Azure API Management</span><span class="sxs-lookup"><span data-stu-id="8832c-146">Azure API Management</span></span>](https://azure.microsoft.com/services/api-management/)
- [<span data-ttu-id="8832c-147">Azure SignalR Service</span><span class="sxs-lookup"><span data-stu-id="8832c-147">Azure SignalR Service</span></span>](https://azure.microsoft.com/services/signalr-service/)
- [<span data-ttu-id="8832c-148">Azure Storage キュー</span><span class="sxs-lookup"><span data-stu-id="8832c-148">Azure Storage Queues</span></span>](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [<span data-ttu-id="8832c-149">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="8832c-149">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [<span data-ttu-id="8832c-150">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="8832c-150">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
- [<span data-ttu-id="8832c-151">Azure イベントハブ</span><span class="sxs-lookup"><span data-stu-id="8832c-151">Azure Event Hub</span></span>](https://azure.microsoft.com/services/event-hubs/)

<span data-ttu-id="8832c-152">次に、クラウドネイティブシステムの分散データと、それが提示する利点と課題に移ります。</span><span class="sxs-lookup"><span data-stu-id="8832c-152">We next move to distributed data in cloud-native systems and the benefits and challenges that it presents.</span></span>

### <a name="references"></a><span data-ttu-id="8832c-153">参照</span><span class="sxs-lookup"><span data-stu-id="8832c-153">References</span></span>

- [<span data-ttu-id="8832c-154">.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="8832c-154">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="8832c-155">マイクロサービスのサービス間通信の設計</span><span class="sxs-lookup"><span data-stu-id="8832c-155">Designing Interservice Communication for Microservices</span></span>](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [<span data-ttu-id="8832c-156">リアルタイム機能を追加するための完全に管理されたサービスである Azure SignalR サービス</span><span class="sxs-lookup"><span data-stu-id="8832c-156">Azure SignalR Service, a fully managed service to add real-time functionality</span></span>](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [<span data-ttu-id="8832c-157">Azure API ゲートウェイの受信コントローラー</span><span class="sxs-lookup"><span data-stu-id="8832c-157">Azure API Gateway Ingress Controller</span></span>](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [<span data-ttu-id="8832c-158">Azure Kubernetes Service の受信について (AKS)</span><span class="sxs-lookup"><span data-stu-id="8832c-158">About Ingress in Azure Kubernetes Service (AKS)</span></span>](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [<span data-ttu-id="8832c-159">実用的な gRPC</span><span class="sxs-lookup"><span data-stu-id="8832c-159">Practical gRPC</span></span>](https://www.worldcat.org/title/practical-grpc/oclc/1042342319)

- [<span data-ttu-id="8832c-160">gRPC のドキュメント</span><span class="sxs-lookup"><span data-stu-id="8832c-160">gRPC Documentation</span></span>](https://grpc.io/docs/guides/)

- <span data-ttu-id="8832c-161">[WCF 開発者向け grpc](https://bing.com) [Mark'S grpc book]</span><span class="sxs-lookup"><span data-stu-id="8832c-161">[gRPC for WCF Developers](https://bing.com) [Mark's gRPC book]</span></span>

- [<span data-ttu-id="8832c-162">GRPC サービスと HTTP Api の比較</span><span class="sxs-lookup"><span data-stu-id="8832c-162">Comparing gRPC Services with HTTP APIs</span></span>](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

>[!div class="step-by-step"]
><span data-ttu-id="8832c-163">[前へ](rest-grpc.md)
>[次へ](distributed-data.md)</span><span class="sxs-lookup"><span data-stu-id="8832c-163">[Previous](rest-grpc.md)
[Next](distributed-data.md)</span></span>
