---
title: Azure Event Grid - サーバーレス アプリ
description: Azure Event Grid は、イベント単位の従量課金モデルで信頼性の高いイベント配信と大規模なルーティングを実現するサーバーレス ソリューションです。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 30937bafd8069eb4508dce18351964103421373a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171885"
---
# <a name="event-grid"></a><span data-ttu-id="536c2-103">Event Grid</span><span class="sxs-lookup"><span data-stu-id="536c2-103">Event Grid</span></span>

<span data-ttu-id="536c2-104">[Azure Event Grid](/azure/event-grid/overview) では、イベントベースのアプリケーションのサーバーレス インフラストラクチャが提供されます。</span><span class="sxs-lookup"><span data-stu-id="536c2-104">[Azure Event Grid](/azure/event-grid/overview) provides serverless infrastructure for event-based applications.</span></span> <span data-ttu-id="536c2-105">任意のソースから Event Grid への発行を行い、任意のプラットフォームからのメッセージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="536c2-105">You can publish to Event Grid from any source and consume messages from any platform.</span></span> <span data-ttu-id="536c2-106">また、Event Grid には、アプリケーションとの統合を効率化するために、Azure リソースのイベントに対するサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="536c2-106">Event Grid also has built-in support for events from Azure resources to streamline integration with your applications.</span></span> <span data-ttu-id="536c2-107">たとえば、BLOB ストレージ イベントをサブスクライブして、ファイルがアップロードされたときにアプリに通知することができます。</span><span class="sxs-lookup"><span data-stu-id="536c2-107">For example, you can subscribe to blob storage events to notify your app when a file is uploaded.</span></span> <span data-ttu-id="536c2-108">その後、アプリケーションでは、他のクラウドまたはオンプレミス アプリケーションで使用されるカスタムの Event Grid メッセージを発行できます。</span><span class="sxs-lookup"><span data-stu-id="536c2-108">Your application can then publish a custom event grid message that is consumed by other cloud or on-premises applications.</span></span> <span data-ttu-id="536c2-109">Event Grid は、大規模な処理を確実に処理するように構築されています。</span><span class="sxs-lookup"><span data-stu-id="536c2-109">Event Grid was built to reliably handle massive scale.</span></span> <span data-ttu-id="536c2-110">必要なインフラストラクチャを設定するオーバーヘッドを発生させることなく、メッセージの発行とサブスクライブの利点を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="536c2-110">You get the benefits of publishing and subscribing to messages without the overhead of setting up the necessary infrastructure.</span></span>

![Event Grid ロゴ](./media/event-grid-logo.png)

<span data-ttu-id="536c2-112">Event Grid の主な特徴は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="536c2-112">The major features of event grid include:</span></span>

- <span data-ttu-id="536c2-113">完全に管理されたイベント ルーティング。</span><span class="sxs-lookup"><span data-stu-id="536c2-113">Fully managed event routing.</span></span>
- <span data-ttu-id="536c2-114">ほぼリアルタイムの大規模なイベント配信。</span><span class="sxs-lookup"><span data-stu-id="536c2-114">Near real-time event delivery at scale.</span></span>
- <span data-ttu-id="536c2-115">Azure の内部と外部の両方で幅広くカバー。</span><span class="sxs-lookup"><span data-stu-id="536c2-115">Broad coverage both inside and outside of Azure.</span></span>

## <a name="scenarios"></a><span data-ttu-id="536c2-116">シナリオ</span><span class="sxs-lookup"><span data-stu-id="536c2-116">Scenarios</span></span>

<span data-ttu-id="536c2-117">Event Grid では、いくつかの異なるシナリオに対処できます。</span><span class="sxs-lookup"><span data-stu-id="536c2-117">Event Grid addresses several different scenarios.</span></span> <span data-ttu-id="536c2-118">このセクションでは、最も一般的な 3 つのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="536c2-118">This section covers three of the most common ones.</span></span>

### <a name="ops-automation"></a><span data-ttu-id="536c2-119">操作の自動化</span><span class="sxs-lookup"><span data-stu-id="536c2-119">Ops automation</span></span>

![操作の自動化](./media/ops-automation.png)

<span data-ttu-id="536c2-121">Event Grid を使用すると、インフラストラクチャがプロビジョニングされたときに [Azure Automation](/azure/automation) に通知することで、自動化を高速化し、ポリシーの適用を簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="536c2-121">Event Grid can help speed automation and simplify policy enforcement by notifying [Azure Automation](/azure/automation) when infrastructure is provisioned.</span></span>

### <a name="application-integration"></a><span data-ttu-id="536c2-122">アプリケーションの統合</span><span class="sxs-lookup"><span data-stu-id="536c2-122">Application integration</span></span>

![アプリケーションの統合](./media/app-integration.png)

<span data-ttu-id="536c2-124">Event Grid を使用して、アプリを他のサービスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="536c2-124">You can use Event Grid to connect your app to other services.</span></span> <span data-ttu-id="536c2-125">標準の HTTP プロトコルを使用すると、従来のアプリでも、Event Grid メッセージを発行するように簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="536c2-125">Using standard HTTP protocols, even legacy apps can be easily modified to publish Event Grid messages.</span></span> <span data-ttu-id="536c2-126">Web フックを使用すると、他のサービスやプラットフォームで Event Grid メッセージを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="536c2-126">Web hooks are available for other services and platforms to consume Event Grid messages.</span></span>

### <a name="serverless-apps"></a><span data-ttu-id="536c2-127">サーバーレス アプリ</span><span class="sxs-lookup"><span data-stu-id="536c2-127">Serverless apps</span></span>

![サーバーレス アプリ](./media/serverless-apps.png)

<span data-ttu-id="536c2-129">Event Grid により、Azure Functions、Logic Apps、または独自のカスタム コードをトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="536c2-129">Event Grid can trigger Azure Functions, Logic Apps, or your own custom code.</span></span> <span data-ttu-id="536c2-130">Event Grid を使用する主な利点は、*プッシュ* メカニズムを使用して、イベントが発生したときにメッセージを送信することにあります。</span><span class="sxs-lookup"><span data-stu-id="536c2-130">A major benefit of using Event Grid is that it uses a *push* mechanism to send messages when events occur.</span></span> <span data-ttu-id="536c2-131">プッシュ アーキテクチャは、*ポーリング* メカニズムよりも使用されるリソースが少なく、拡張性に優れています。</span><span class="sxs-lookup"><span data-stu-id="536c2-131">The push architecture consumes fewer resources and scales better than *polling* mechanisms.</span></span> <span data-ttu-id="536c2-132">ポーリングでは、定期的に更新プログラムをチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="536c2-132">Polling must check for updates on a regular interval.</span></span>

## <a name="event-grid-vs-other-azure-messaging-services"></a><span data-ttu-id="536c2-133">Event Grid と他の Azure メッセージング サービス</span><span class="sxs-lookup"><span data-stu-id="536c2-133">Event Grid vs. other Azure messaging services</span></span>

<span data-ttu-id="536c2-134">Azure には、[Event Hubs](/azure/event-hubs) や [Service Bus](/azure/service-bus-messaging) など、いくつかのメッセージング サービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="536c2-134">Azure provides several messaging services, including [Event Hubs](/azure/event-hubs) and [Service Bus](/azure/service-bus-messaging).</span></span> <span data-ttu-id="536c2-135">それぞれのサービスは、特定のユース ケース セットに対処するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="536c2-135">Each is designed to address a specific set of use cases.</span></span> <span data-ttu-id="536c2-136">次の図は、サービス間の相違点の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="536c2-136">The following diagram provides a high-level overview of the differences between the services.</span></span>

![Azure メッセージングの比較](./media/azure-messaging-services.png)

<span data-ttu-id="536c2-138">詳細な比較については、[メッセージング サービスの比較](/azure/event-grid/compare-messaging-services)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="536c2-138">For a more in-depth comparison, see [Compare messaging services](/azure/event-grid/compare-messaging-services).</span></span>

## <a name="performance-targets"></a><span data-ttu-id="536c2-139">パフォーマンスの目標</span><span class="sxs-lookup"><span data-stu-id="536c2-139">Performance targets</span></span>

<span data-ttu-id="536c2-140">Event Grid を使用すると、次のパフォーマンスの保証を活用できます。</span><span class="sxs-lookup"><span data-stu-id="536c2-140">Using Event Grid you can take advantage of the following performance guarantees:</span></span>

- <span data-ttu-id="536c2-141">99 パーセンタイルで秒未満のエンドツーエンドの待機時間。</span><span class="sxs-lookup"><span data-stu-id="536c2-141">Subsecond end-to-end latency in the 99th percentile.</span></span>
- <span data-ttu-id="536c2-142">99.99% の可用性。</span><span class="sxs-lookup"><span data-stu-id="536c2-142">99.99% availability.</span></span>
- <span data-ttu-id="536c2-143">リージョンあたり 1 秒間に 1000 万のイベント。</span><span class="sxs-lookup"><span data-stu-id="536c2-143">10 million events per second per region.</span></span>
- <span data-ttu-id="536c2-144">リージョンあたり 1 億のサブスクライブ数。</span><span class="sxs-lookup"><span data-stu-id="536c2-144">100 million subscriptions per region.</span></span>
- <span data-ttu-id="536c2-145">50 ミリ秒の発行元の待機時間。</span><span class="sxs-lookup"><span data-stu-id="536c2-145">50-ms publisher latency.</span></span>
- <span data-ttu-id="536c2-146">1 日のウィンドウで保証された配信を行うための指数バックオフによる 24 時間の再試行。</span><span class="sxs-lookup"><span data-stu-id="536c2-146">24-hour retry with exponential back-off for guaranteed delivery in the 1-day window.</span></span>
- <span data-ttu-id="536c2-147">透過的なリージョン内フェールオーバー。</span><span class="sxs-lookup"><span data-stu-id="536c2-147">Transparent regional failover.</span></span>

## <a name="event-grid-schema"></a><span data-ttu-id="536c2-148">Event Grid スキーマ</span><span class="sxs-lookup"><span data-stu-id="536c2-148">Event Grid schema</span></span>

<span data-ttu-id="536c2-149">Event Grid では、標準スキーマを使用してカスタムイベントがラップされます。</span><span class="sxs-lookup"><span data-stu-id="536c2-149">Event Grid uses a standard schema to wrap custom events.</span></span> <span data-ttu-id="536c2-150">スキーマは、カスタム データ要素をラップするエンベロープに似ています。</span><span class="sxs-lookup"><span data-stu-id="536c2-150">The schema is like an envelope that wraps your custom data element.</span></span> <span data-ttu-id="536c2-151">Event Grid メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="536c2-151">Here is an example Event Grid message:</span></span>

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

<span data-ttu-id="536c2-152">メッセージに関するすべての項目は、`data` プロパティを除き、標準です。</span><span class="sxs-lookup"><span data-stu-id="536c2-152">Everything about the message is standard except the `data` property.</span></span> <span data-ttu-id="536c2-153">メッセージを調べ、`eventType` と `dataVersion` を使用して、ペイロードのカスタム部分を逆シリアル化することができます。</span><span class="sxs-lookup"><span data-stu-id="536c2-153">You can inspect the message and use the `eventType` and `dataVersion` to de-serialize the custom portion of the payload.</span></span>

## <a name="azure-resources"></a><span data-ttu-id="536c2-154">管理</span><span class="sxs-lookup"><span data-stu-id="536c2-154">Azure resources</span></span>

<span data-ttu-id="536c2-155">Event Grid を使用する主な利点は、Azure によって生成される自動メッセージにあります。</span><span class="sxs-lookup"><span data-stu-id="536c2-155">A major benefit of using Event Grid is the automatic messages produced by Azure.</span></span> <span data-ttu-id="536c2-156">Azure では、さまざまなイベントをサブスクライブできるように、リソースが*トピック*に自動的に発行されます。</span><span class="sxs-lookup"><span data-stu-id="536c2-156">In Azure, resources automatically publish to a *topic* that allows you to subscribe for various events.</span></span> <span data-ttu-id="536c2-157">次の表は、自動的に使用できるリソースの種類、メッセージの種類、およびイベントを示しています。</span><span class="sxs-lookup"><span data-stu-id="536c2-157">The following table lists the resource types, message types, and events that are available automatically.</span></span>

| <span data-ttu-id="536c2-158">Azure リソース</span><span class="sxs-lookup"><span data-stu-id="536c2-158">Azure resource</span></span> | <span data-ttu-id="536c2-159">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="536c2-159">Event type</span></span> | <span data-ttu-id="536c2-160">説明</span><span class="sxs-lookup"><span data-stu-id="536c2-160">Description</span></span> |
| -------------- | ---------- | ----------- |
| <span data-ttu-id="536c2-161">Azure サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="536c2-161">Azure subscription</span></span> | <span data-ttu-id="536c2-162">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="536c2-162">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="536c2-163">リソースの作成または更新操作が成功したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-163">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="536c2-164">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="536c2-164">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="536c2-165">リソースの作成または更新操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-165">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="536c2-166">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="536c2-166">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="536c2-167">リソースの作成または更新操作が取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-167">Raised when a resource create or update operation is canceled.</span></span> |
|  | <span data-ttu-id="536c2-168">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="536c2-168">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="536c2-169">リソースの削除操作が成功したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-169">Raised when a resource delete operation succeeds.</span></span> |
|  | <span data-ttu-id="536c2-170">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="536c2-170">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="536c2-171">リソースの削除操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-171">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="536c2-172">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="536c2-172">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="536c2-173">リソースの削除操作が取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-173">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="536c2-174">このイベントは、テンプレートのデプロイが取り消された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-174">This event happens when a template deployment is canceled.</span></span> |
| <span data-ttu-id="536c2-175">BLOB ストレージ</span><span class="sxs-lookup"><span data-stu-id="536c2-175">Blob storage</span></span> | <span data-ttu-id="536c2-176">Microsoft.Storage.BlobCreated</span><span class="sxs-lookup"><span data-stu-id="536c2-176">Microsoft.Storage.BlobCreated</span></span> | <span data-ttu-id="536c2-177">BLOB が作成されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-177">Raised when a blob is created.</span></span> |
| | <span data-ttu-id="536c2-178">Microsoft.Storage.BlobDeleted</span><span class="sxs-lookup"><span data-stu-id="536c2-178">Microsoft.Storage.BlobDeleted</span></span> | <span data-ttu-id="536c2-179">BLOB が削除されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-179">Raised when a blob is deleted.</span></span> |
| <span data-ttu-id="536c2-180">Event Hubs</span><span class="sxs-lookup"><span data-stu-id="536c2-180">Event hubs</span></span> | <span data-ttu-id="536c2-181">Microsoft.EventHub.CaptureFileCreated</span><span class="sxs-lookup"><span data-stu-id="536c2-181">Microsoft.EventHub.CaptureFileCreated</span></span> | <span data-ttu-id="536c2-182">キャプチャ ファイルが作成されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-182">Raised when a capture file is created.</span></span>
| <span data-ttu-id="536c2-183">IoT Hub</span><span class="sxs-lookup"><span data-stu-id="536c2-183">IoT Hub</span></span> | <span data-ttu-id="536c2-184">Microsoft.Devices.DeviceCreated</span><span class="sxs-lookup"><span data-stu-id="536c2-184">Microsoft.Devices.DeviceCreated</span></span> | <span data-ttu-id="536c2-185">デバイスが IoT Hub に登録されると発行されます。</span><span class="sxs-lookup"><span data-stu-id="536c2-185">Published when a device is registered to an IoT hub.</span></span> |
| | <span data-ttu-id="536c2-186">Microsoft.Devices.DeviceDeleted</span><span class="sxs-lookup"><span data-stu-id="536c2-186">Microsoft.Devices.DeviceDeleted</span></span> | <span data-ttu-id="536c2-187">デバイスが IoT Hub から削除されると発行されます。</span><span class="sxs-lookup"><span data-stu-id="536c2-187">Published when a device is deleted from an IoT hub.</span></span> |
| <span data-ttu-id="536c2-188">リソース グループ</span><span class="sxs-lookup"><span data-stu-id="536c2-188">Resource groups</span></span> | <span data-ttu-id="536c2-189">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="536c2-189">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="536c2-190">リソースの作成または更新操作が成功したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-190">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="536c2-191">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="536c2-191">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="536c2-192">リソースの作成または更新操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-192">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="536c2-193">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="536c2-193">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="536c2-194">リソースの作成または更新操作が取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-194">Raised when a resource create or update operation is canceled.</span></span> |
| | <span data-ttu-id="536c2-195">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="536c2-195">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="536c2-196">リソースの削除操作が成功したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-196">Raised when a resource delete operation succeeds.</span></span> |
| | <span data-ttu-id="536c2-197">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="536c2-197">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="536c2-198">リソースの削除操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-198">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="536c2-199">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="536c2-199">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="536c2-200">リソースの削除操作が取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-200">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="536c2-201">このイベントは、テンプレートのデプロイが取り消された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="536c2-201">This event happens when a template deployment is canceled.</span></span> |

<span data-ttu-id="536c2-202">詳細については、「[Azure Event Grid イベント スキーマ](/azure/event-grid/event-schema)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="536c2-202">For more information, see [Azure Event Grid event schema](/azure/event-grid/event-schema).</span></span>

<span data-ttu-id="536c2-203">オンプレミスで実行されているアプリケーションも含め、任意の種類のアプリケーションから Event Grid にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="536c2-203">You can access Event Grid from any type of application, even one that runs on-premises.</span></span>

## <a name="conclusion"></a><span data-ttu-id="536c2-204">まとめ</span><span class="sxs-lookup"><span data-stu-id="536c2-204">Conclusion</span></span>

<span data-ttu-id="536c2-205">この章では、Azure Functions、Logic Apps、および Event Grid で構成される Azure サーバーレス プラットフォームについて学習しました。</span><span class="sxs-lookup"><span data-stu-id="536c2-205">In this chapter you learned about the Azure serverless platform that is composed of Azure Functions, Logic Apps, and Event Grid.</span></span> <span data-ttu-id="536c2-206">これらのリソースを使用して、完全なサーバーレス アプリ アーキテクチャを構築したり、他のクラウド リソースやオンプレミス サーバーと対話するハイブリッド ソリューションを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="536c2-206">You can use these resources to build an entirely serverless app architecture, or create a hybrid solution that interacts with other cloud resources and on-premises servers.</span></span> <span data-ttu-id="536c2-207">[Azure SQL](/azure/sql-database) や [CosmosDB](/azure/cosmos-db/introduction) などのサーバーレス データ プラットフォームと組み合わせることで、完全に管理されたクラウド ネイティブ アプリケーションをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="536c2-207">Combined with a serverless data platform such as [Azure SQL](/azure/sql-database) or [CosmosDB](/azure/cosmos-db/introduction), you can build fully managed cloud native applications.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="536c2-208">推奨リソース</span><span class="sxs-lookup"><span data-stu-id="536c2-208">Recommended resources</span></span>

- [<span data-ttu-id="536c2-209">App Service のプラン</span><span class="sxs-lookup"><span data-stu-id="536c2-209">App service plans</span></span>](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [<span data-ttu-id="536c2-210">Application Insights</span><span class="sxs-lookup"><span data-stu-id="536c2-210">Application Insights</span></span>](/azure/application-insights)
- [<span data-ttu-id="536c2-211">Application Insights Analytics</span><span class="sxs-lookup"><span data-stu-id="536c2-211">Application Insights Analytics</span></span>](/azure/application-insights/app-insights-analytics)
- [<span data-ttu-id="536c2-212">Azure:サーバーレスの Azure Functions を使用してアプリをクラウドに持ち込む</span><span class="sxs-lookup"><span data-stu-id="536c2-212">Azure: Bring your app to the cloud with serverless Azure Functions</span></span>](https://channel9.msdn.com/events/Connect/2017/E102)
- [<span data-ttu-id="536c2-213">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="536c2-213">Azure Event Grid</span></span>](/azure/event-grid/overview)
- [<span data-ttu-id="536c2-214">Azure Event Grid イベント スキーマ</span><span class="sxs-lookup"><span data-stu-id="536c2-214">Azure Event Grid event schema</span></span>](/azure/event-grid/event-schema)
- [<span data-ttu-id="536c2-215">Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="536c2-215">Azure Event Hubs</span></span>](/azure/event-hubs)
- [<span data-ttu-id="536c2-216">Azure Functions のドキュメント</span><span class="sxs-lookup"><span data-stu-id="536c2-216">Azure Functions documentation</span></span>](/azure/azure-functions)
- [<span data-ttu-id="536c2-217">Azure Functions でのトリガーとバインドの概念</span><span class="sxs-lookup"><span data-stu-id="536c2-217">Azure Functions triggers and bindings concepts</span></span>](/azure/azure-functions/functions-triggers-bindings)
- [<span data-ttu-id="536c2-218">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="536c2-218">Azure Logic Apps</span></span>](/azure/logic-apps)
- [<span data-ttu-id="536c2-219">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="536c2-219">Azure Service Bus</span></span>](/azure/service-bus-messaging)
- [<span data-ttu-id="536c2-220">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="536c2-220">Azure Table Storage</span></span>](/azure/cosmos-db/table-storage-overview)
- [<span data-ttu-id="536c2-221">Azure のオンプレミス データ ゲートウェイを使用してオンプレミスのデータ ソースに接続する</span><span class="sxs-lookup"><span data-stu-id="536c2-221">Connecting to on-premises data sources with Azure On-premises Data Gateway</span></span>](/azure/analysis-services/analysis-services-gateway)
- [<span data-ttu-id="536c2-222">Azure portal で初めての関数を作成する</span><span class="sxs-lookup"><span data-stu-id="536c2-222">Create your first function in the Azure portal</span></span>](/azure/azure-functions/functions-create-first-azure-function)
- [<span data-ttu-id="536c2-223">Azure CLI での初めての関数の作成</span><span class="sxs-lookup"><span data-stu-id="536c2-223">Create your first function using the Azure CLI</span></span>](/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [<span data-ttu-id="536c2-224">Visual Studio での初めての関数の作成</span><span class="sxs-lookup"><span data-stu-id="536c2-224">Create your first function using Visual Studio</span></span>](/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [<span data-ttu-id="536c2-225">Functions でサポートされる言語</span><span class="sxs-lookup"><span data-stu-id="536c2-225">Functions supported languages</span></span>](/azure/azure-functions/supported-languages)
- [<span data-ttu-id="536c2-226">Azure Functions の監視</span><span class="sxs-lookup"><span data-stu-id="536c2-226">Monitor Azure Functions</span></span>](/azure/azure-functions/functions-monitoring)

>[!div class="step-by-step"]
><span data-ttu-id="536c2-227">[前へ](logic-apps.md)
>[次へ](durable-azure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="536c2-227">[Previous](logic-apps.md)
[Next](durable-azure-functions.md)</span></span>
