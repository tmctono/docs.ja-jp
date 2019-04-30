---
title: Azure Event Grid - サーバーレス アプリ
description: Azure Event Grid には、信頼性の高いイベントの配信と、イベントごとに従量課金モデルに非常に大きなスケールでのルーティング、サーバーレス ソリューションです。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 4970130ede0c96c645129ee6c8c7d54cb1114042
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959387"
---
# <a name="event-grid"></a><span data-ttu-id="7ff3d-103">イベント グリッド</span><span class="sxs-lookup"><span data-stu-id="7ff3d-103">Event Grid</span></span>

<span data-ttu-id="7ff3d-104">[Azure Event Grid](/azure/event-grid/overview)サーバーレス インフラストラクチャ イベント ベースのアプリケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-104">[Azure Event Grid](/azure/event-grid/overview) provides serverless infrastructure for event-based applications.</span></span> <span data-ttu-id="7ff3d-105">任意のソースからイベント グリッドに発行し、任意のプラットフォームからのメッセージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-105">You can publish to Event Grid from any source and consume messages from any platform.</span></span> <span data-ttu-id="7ff3d-106">Event Grid では、組み込みのサポートをアプリケーションとの統合を効率化する Azure リソースからのイベントもあります。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-106">Event Grid also has built-in support for events from Azure resources to streamline integration with your applications.</span></span> <span data-ttu-id="7ff3d-107">たとえば、ファイルをアップロードするときに、アプリに通知する blob storage イベントにサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-107">For example, you can subscribe to blob storage events to notify your app when a file is uploaded.</span></span> <span data-ttu-id="7ff3d-108">アプリケーションは、他のクラウドによって消費されるか、オンプレミスのアプリケーションをカスタム イベント グリッドのメッセージを公開できます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-108">Your application can then publish a custom event grid message that is consumed by other cloud or on-premises applications.</span></span> <span data-ttu-id="7ff3d-109">Event Grid は、非常に大きなスケールを確実に処理するために構築されました。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-109">Event Grid was built to reliably handle massive scale.</span></span> <span data-ttu-id="7ff3d-110">発行およびサブスクライブを設定するために必要なインフラストラクチャのオーバーヘッドなしのメッセージのメリットを享受します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-110">You get the benefits of publishing and subscribing to messages without the overhead of setting up the necessary infrastructure.</span></span>

![イベント グリッドのロゴ](./media/event-grid-logo.png)

<span data-ttu-id="7ff3d-112">Event grid の主要な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-112">The major features of event grid include:</span></span>

* <span data-ttu-id="7ff3d-113">完全に管理されたイベントをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-113">Fully managed event routing.</span></span>
* <span data-ttu-id="7ff3d-114">ほぼリアルタイムのイベント配信します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-114">Near real-time event delivery at scale.</span></span>
* <span data-ttu-id="7ff3d-115">Azure の内外両方の広範なカバレッジ。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-115">Broad coverage both inside and outside of Azure.</span></span>

## <a name="scenarios"></a><span data-ttu-id="7ff3d-116">シナリオ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-116">Scenarios</span></span>

<span data-ttu-id="7ff3d-117">Event Grid は、複数の異なるシナリオを説明します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-117">Event Grid addresses several different scenarios.</span></span> <span data-ttu-id="7ff3d-118">このセクションでは、3 つの最も一般的なものについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-118">This section covers three of the most common ones.</span></span>

### <a name="ops-automation"></a><span data-ttu-id="7ff3d-119">操作の自動化</span><span class="sxs-lookup"><span data-stu-id="7ff3d-119">Ops automation</span></span>

![操作の自動化](./media/ops-automation.png)

<span data-ttu-id="7ff3d-121">Event Grid は速度の自動化を支援して、ポリシーの適用を通知することにより簡素化[Azure Automation](https://docs.microsoft.com/azure/automation)インフラストラクチャのプロビジョニング時にします。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-121">Event Grid can help speed automation and simplify policy enforcement by notifying [Azure Automation](https://docs.microsoft.com/azure/automation) when infrastructure is provisioned.</span></span>

### <a name="application-integration"></a><span data-ttu-id="7ff3d-122">アプリケーションの統合</span><span class="sxs-lookup"><span data-stu-id="7ff3d-122">Application integration</span></span>

![アプリケーションの統合](./media/app-integration.png)

<span data-ttu-id="7ff3d-124">Event Grid を使用すると、アプリの他のサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-124">You can use Event Grid to connect your app to other services.</span></span> <span data-ttu-id="7ff3d-125">標準の HTTP プロトコルを使用しても従来のアプリに簡単に変更できます Event Grid メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-125">Using standard HTTP protocols, even legacy apps can be easily modified to publish Event Grid messages.</span></span> <span data-ttu-id="7ff3d-126">Web フックの他のサービスと Event Grid メッセージを使用するプラットフォームを利用できます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-126">Web hooks are available for other services and platforms to consume Event Grid messages.</span></span>

### <a name="serverless-apps"></a><span data-ttu-id="7ff3d-127">サーバーレス アプリ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-127">Serverless apps</span></span>

![サーバーレス アプリ](./media/serverless-apps.png)

<span data-ttu-id="7ff3d-129">Event Grid には、Azure Functions、Logic Apps、または独自のカスタム コードをトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-129">Event Grid can trigger Azure Functions, Logic Apps, or your own custom code.</span></span> <span data-ttu-id="7ff3d-130">Event Grid の使用の大きな利点は、使用するという、*プッシュ*イベントが発生したときにメッセージを送信するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-130">A major benefit of using Event Grid is that it uses a *push* mechanism to send messages when events occur.</span></span> <span data-ttu-id="7ff3d-131">プッシュ アーキテクチャがより少ないリソースを消費しよりの方がスケーラビリティ*ポーリング*メカニズム。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-131">The push architecture consumes fewer resources and scales better than *polling* mechanisms.</span></span> <span data-ttu-id="7ff3d-132">ポーリングは、一定の間隔で更新プログラムを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-132">Polling must check for updates on a regular interval.</span></span>

## <a name="event-grid-vs-other-azure-messaging-services"></a><span data-ttu-id="7ff3d-133">他の Azure メッセージング サービスとのイベント グリッド</span><span class="sxs-lookup"><span data-stu-id="7ff3d-133">Event Grid vs. other Azure messaging services</span></span>

<span data-ttu-id="7ff3d-134">Azure など、いくつかのメッセージング サービスを提供する[Event Hubs](https://docs.microsoft.com/azure/event-hubs)と[Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-134">Azure provides several messaging services, including [Event Hubs](https://docs.microsoft.com/azure/event-hubs) and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging).</span></span> <span data-ttu-id="7ff3d-135">特定の一連のユース ケースに対処する各設計されています。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-135">Each is designed to address a specific set of use cases.</span></span> <span data-ttu-id="7ff3d-136">次の図では、サービスの違いの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-136">The following diagram provides a high-level overview of the differences between the services.</span></span>

![Azure メッセージングの比較](./media/azure-messaging-services.png)

<span data-ttu-id="7ff3d-138">詳細な比較を参照してください。[メッセージング サービスの比較](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-138">For a more in-depth comparison, see [Compare messaging services](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).</span></span>

## <a name="performance-targets"></a><span data-ttu-id="7ff3d-139">パフォーマンスのターゲット</span><span class="sxs-lookup"><span data-stu-id="7ff3d-139">Performance targets</span></span>

<span data-ttu-id="7ff3d-140">次のパフォーマンスの利用、Event Grid の使用を保証します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-140">Using Event Grid you can take advantage of the following performance guarantees:</span></span>

* <span data-ttu-id="7ff3d-141">99 パーセン タイルでエンド ツー エンドの待機時間を未満にします。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-141">Subsecond end-to-end latency in the 99th percentile.</span></span>
* <span data-ttu-id="7ff3d-142">99.99% の可用性。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-142">99.99% availability.</span></span>
* <span data-ttu-id="7ff3d-143">リージョンごとの 1 秒あたり 10,000, 000 イベント。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-143">10 million events per second per region.</span></span>
* <span data-ttu-id="7ff3d-144">リージョンあたり 1億サブスクリプション。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-144">100 million subscriptions per region.</span></span>
* <span data-ttu-id="7ff3d-145">パブリッシャーの待機時間の 50 ms。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-145">50-ms publisher latency.</span></span>
* <span data-ttu-id="7ff3d-146">24 時間は 1 日のウィンドウで保証された配信の指数のバックオフで再試行してください。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-146">24-hour retry with exponential back-off for guaranteed delivery in the 1-day window.</span></span>
* <span data-ttu-id="7ff3d-147">透過的な地域フェールオーバーします。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-147">Transparent regional failover.</span></span>

## <a name="event-grid-schema"></a><span data-ttu-id="7ff3d-148">Event Grid スキーマ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-148">Event Grid schema</span></span>

<span data-ttu-id="7ff3d-149">Event Grid は、カスタム イベントをラップするのに標準スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-149">Event Grid uses a standard schema to wrap custom events.</span></span> <span data-ttu-id="7ff3d-150">スキーマは、カスタム データ要素をラップするエンベロープ似ています。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-150">The schema is like an envelope that wraps your custom data element.</span></span> <span data-ttu-id="7ff3d-151">Event Grid メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-151">Here is an example Event Grid message:</span></span>

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

<span data-ttu-id="7ff3d-152">除く標準のすべてのメッセージについては、`data`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-152">Everything about the message is standard except the `data` property.</span></span> <span data-ttu-id="7ff3d-153">メッセージを検査して、使用することができます、`eventType`と`dataVersion`ペイロードのカスタム部分を逆シリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-153">You can inspect the message and use the `eventType` and `dataVersion` to de-serialize the custom portion of the payload.</span></span>

## <a name="azure-resources"></a><span data-ttu-id="7ff3d-154">管理</span><span class="sxs-lookup"><span data-stu-id="7ff3d-154">Azure resources</span></span>

<span data-ttu-id="7ff3d-155">Event Grid の使用の大きな利点は、Azure によって生成された自動メッセージです。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-155">A major benefit of using Event Grid is the automatic messages produced by Azure.</span></span> <span data-ttu-id="7ff3d-156">Azure では、リソースに自動で発行、*トピック*さまざまなイベントをサブスクライブすることができます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-156">In Azure, resources automatically publish to a *topic* that allows you to subscribe for various events.</span></span> <span data-ttu-id="7ff3d-157">次の表には、リソースの種類、メッセージの種類、および自動的に利用できるイベントが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-157">The following table lists the resource types, message types, and events that are available automatically.</span></span>

| <span data-ttu-id="7ff3d-158">Azure リソース</span><span class="sxs-lookup"><span data-stu-id="7ff3d-158">Azure resource</span></span> | <span data-ttu-id="7ff3d-159">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="7ff3d-159">Event type</span></span> | <span data-ttu-id="7ff3d-160">説明</span><span class="sxs-lookup"><span data-stu-id="7ff3d-160">Description</span></span> |
| -------------- | ---------- | ----------- |
| <span data-ttu-id="7ff3d-161">Azure サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="7ff3d-161">Azure subscription</span></span> | <span data-ttu-id="7ff3d-162">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="7ff3d-162">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="7ff3d-163">発生したときに、リソースの作成または更新操作は成功します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-163">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="7ff3d-164">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="7ff3d-164">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="7ff3d-165">リソースの作成または更新操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-165">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="7ff3d-166">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="7ff3d-166">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="7ff3d-167">リソースが作成または更新操作が取り消された発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-167">Raised when a resource create or update operation is canceled.</span></span> |
|  | <span data-ttu-id="7ff3d-168">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="7ff3d-168">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="7ff3d-169">リソースの削除操作が成功したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-169">Raised when a resource delete operation succeeds.</span></span> |
|  | <span data-ttu-id="7ff3d-170">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="7ff3d-170">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="7ff3d-171">リソースの削除操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-171">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="7ff3d-172">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="7ff3d-172">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="7ff3d-173">リソースの削除操作が取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-173">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="7ff3d-174">このイベントは、テンプレートのデプロイが取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-174">This event happens when a template deployment is canceled.</span></span> |
| <span data-ttu-id="7ff3d-175">BLOB ストレージ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-175">Blob storage</span></span> | <span data-ttu-id="7ff3d-176">Microsoft.Storage.BlobCreated</span><span class="sxs-lookup"><span data-stu-id="7ff3d-176">Microsoft.Storage.BlobCreated</span></span> | <span data-ttu-id="7ff3d-177">Blob が作成されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-177">Raised when a blob is created.</span></span> |
| | <span data-ttu-id="7ff3d-178">Microsoft.Storage.BlobDeleted</span><span class="sxs-lookup"><span data-stu-id="7ff3d-178">Microsoft.Storage.BlobDeleted</span></span> | <span data-ttu-id="7ff3d-179">Blob が削除されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-179">Raised when a blob is deleted.</span></span> |
| <span data-ttu-id="7ff3d-180">イベント ハブ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-180">Event hubs</span></span> | <span data-ttu-id="7ff3d-181">Microsoft.EventHub.CaptureFileCreated</span><span class="sxs-lookup"><span data-stu-id="7ff3d-181">Microsoft.EventHub.CaptureFileCreated</span></span> | <span data-ttu-id="7ff3d-182">キャプチャ ファイルが作成されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-182">Raised when a capture file is created.</span></span>
| <span data-ttu-id="7ff3d-183">IoT Hub</span><span class="sxs-lookup"><span data-stu-id="7ff3d-183">IoT Hub</span></span> | <span data-ttu-id="7ff3d-184">Microsoft.Devices.DeviceCreated</span><span class="sxs-lookup"><span data-stu-id="7ff3d-184">Microsoft.Devices.DeviceCreated</span></span> | <span data-ttu-id="7ff3d-185">デバイスが IoT hub に登録されているときに発行します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-185">Published when a device is registered to an IoT hub.</span></span> |
| | <span data-ttu-id="7ff3d-186">Microsoft.Devices.DeviceDeleted</span><span class="sxs-lookup"><span data-stu-id="7ff3d-186">Microsoft.Devices.DeviceDeleted</span></span> | <span data-ttu-id="7ff3d-187">デバイスが IoT hub から削除されたときに発行します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-187">Published when a device is deleted from an IoT hub.</span></span> |
| <span data-ttu-id="7ff3d-188">リソース グループ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-188">Resource groups</span></span> | <span data-ttu-id="7ff3d-189">Microsoft.Resources.ResourceWriteSuccess</span><span class="sxs-lookup"><span data-stu-id="7ff3d-189">Microsoft.Resources.ResourceWriteSuccess</span></span> | <span data-ttu-id="7ff3d-190">発生したときに、リソースの作成または更新操作は成功します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-190">Raised when a resource create or update operation succeeds.</span></span> |
| | <span data-ttu-id="7ff3d-191">Microsoft.Resources.ResourceWriteFailure</span><span class="sxs-lookup"><span data-stu-id="7ff3d-191">Microsoft.Resources.ResourceWriteFailure</span></span> | <span data-ttu-id="7ff3d-192">リソースの作成または更新操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-192">Raised when a resource create or update operation fails.</span></span> |
| | <span data-ttu-id="7ff3d-193">Microsoft.Resources.ResourceWriteCancel</span><span class="sxs-lookup"><span data-stu-id="7ff3d-193">Microsoft.Resources.ResourceWriteCancel</span></span> | <span data-ttu-id="7ff3d-194">リソースが作成または更新操作が取り消された発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-194">Raised when a resource create or update operation is canceled.</span></span> |
| | <span data-ttu-id="7ff3d-195">Microsoft.Resources.ResourceDeleteSuccess</span><span class="sxs-lookup"><span data-stu-id="7ff3d-195">Microsoft.Resources.ResourceDeleteSuccess</span></span> | <span data-ttu-id="7ff3d-196">リソースの削除操作が成功したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-196">Raised when a resource delete operation succeeds.</span></span> |
| | <span data-ttu-id="7ff3d-197">Microsoft.Resources.ResourceDeleteFailure</span><span class="sxs-lookup"><span data-stu-id="7ff3d-197">Microsoft.Resources.ResourceDeleteFailure</span></span> | <span data-ttu-id="7ff3d-198">リソースの削除操作が失敗したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-198">Raised when a resource delete operation fails.</span></span> |
| | <span data-ttu-id="7ff3d-199">Microsoft.Resources.ResourceDeleteCancel</span><span class="sxs-lookup"><span data-stu-id="7ff3d-199">Microsoft.Resources.ResourceDeleteCancel</span></span> | <span data-ttu-id="7ff3d-200">リソースの削除操作が取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-200">Raised when a resource delete operation is canceled.</span></span> <span data-ttu-id="7ff3d-201">このイベントは、テンプレートのデプロイが取り消されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-201">This event happens when a template deployment is canceled.</span></span> |

<span data-ttu-id="7ff3d-202">詳細については、次を参照してください。 [Azure Event Grid イベント スキーマ](https://docs.microsoft.com/azure/event-grid/event-schema)します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-202">For more information, see [Azure Event Grid event schema](https://docs.microsoft.com/azure/event-grid/event-schema).</span></span>

<span data-ttu-id="7ff3d-203">Event Grid は、あらゆる種類のオンプレミスで実行されるものも含めて、アプリケーションからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-203">You can access Event Grid from any type of application, even one that runs on-premises.</span></span>

## <a name="conclusion"></a><span data-ttu-id="7ff3d-204">まとめ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-204">Conclusion</span></span>

<span data-ttu-id="7ff3d-205">この章では、Azure Functions、Logic Apps、および Event Grid を構成している Azure のサーバーレス プラットフォームについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-205">In this chapter you learned about the Azure serverless platform that is composed of Azure Functions, Logic Apps, and Event Grid.</span></span> <span data-ttu-id="7ff3d-206">これらのリソースを使用して、すべてサーバーレス アプリケーション アーキテクチャを構築するまたは他のクラウド リソースと対話し、オンプレミス サーバーをハイブリッド ソリューションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-206">You can use these resources to build an entirely serverless app architecture, or create a hybrid solution that interacts with other cloud resources and on-premises servers.</span></span> <span data-ttu-id="7ff3d-207">などのサーバーレス データ プラットフォームと組み合わせて[Azure SQL](https://docs.microsoft.com/azure/sql-database)または[CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction)、完全に管理されたクラウド ネイティブ アプリケーションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-207">Combined with a serverless data platform such as [Azure SQL](https://docs.microsoft.com/azure/sql-database) or [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), you can build fully managed cloud native applications.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="7ff3d-208">推奨リソース</span><span class="sxs-lookup"><span data-stu-id="7ff3d-208">Recommended resources</span></span>

* [<span data-ttu-id="7ff3d-209">App service プラン</span><span class="sxs-lookup"><span data-stu-id="7ff3d-209">App service plans</span></span>](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [<span data-ttu-id="7ff3d-210">Application Insights</span><span class="sxs-lookup"><span data-stu-id="7ff3d-210">Application Insights</span></span>](https://docs.microsoft.com/azure/application-insights)
* [<span data-ttu-id="7ff3d-211">Application Insights Analytics</span><span class="sxs-lookup"><span data-stu-id="7ff3d-211">Application Insights Analytics</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [<span data-ttu-id="7ff3d-212">Azure:サーバーレス Azure Functions を使用してクラウドにアプリを表示します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-212">Azure: Bring your app to the cloud with serverless Azure Functions</span></span>](https://channel9.msdn.com/events/Connect/2017/E102)
* [<span data-ttu-id="7ff3d-213">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="7ff3d-213">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
* [<span data-ttu-id="7ff3d-214">Azure Event Grid イベント スキーマ</span><span class="sxs-lookup"><span data-stu-id="7ff3d-214">Azure Event Grid event schema</span></span>](https://docs.microsoft.com/azure/event-grid/event-schema)
* [<span data-ttu-id="7ff3d-215">Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="7ff3d-215">Azure Event Hubs</span></span>](https://docs.microsoft.com/azure/event-hubs)
* [<span data-ttu-id="7ff3d-216">Azure Functions のドキュメント</span><span class="sxs-lookup"><span data-stu-id="7ff3d-216">Azure Functions documentation</span></span>](https://docs.microsoft.com/azure/azure-functions)
* [<span data-ttu-id="7ff3d-217">Azure Functions のトリガーとバインドの概念</span><span class="sxs-lookup"><span data-stu-id="7ff3d-217">Azure Functions triggers and bindings concepts</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [<span data-ttu-id="7ff3d-218">Azure Logic Apps</span><span class="sxs-lookup"><span data-stu-id="7ff3d-218">Azure Logic Apps</span></span>](https://docs.microsoft.com/azure/logic-apps)
* [<span data-ttu-id="7ff3d-219">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="7ff3d-219">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging)
* [<span data-ttu-id="7ff3d-220">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="7ff3d-220">Azure Table Storage</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [<span data-ttu-id="7ff3d-221">1.x と 2.x の比較関数</span><span class="sxs-lookup"><span data-stu-id="7ff3d-221">Compare functions 1.x and 2.x</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [<span data-ttu-id="7ff3d-222">Azure をオンプレミス データ ゲートウェイとオンプレミス データ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-222">Connecting to on-premises data sources with Azure On-premises Data Gateway</span></span>](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [<span data-ttu-id="7ff3d-223">Azure portal で初めての関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-223">Create your first function in the Azure portal</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [<span data-ttu-id="7ff3d-224">Azure CLI を使用した初めての関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-224">Create your first function using the Azure CLI</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [<span data-ttu-id="7ff3d-225">Visual Studio を使用した初めての関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-225">Create your first function using Visual Studio</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [<span data-ttu-id="7ff3d-226">関数がサポートされている言語</span><span class="sxs-lookup"><span data-stu-id="7ff3d-226">Functions supported languages</span></span>](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [<span data-ttu-id="7ff3d-227">Azure Functions を監視</span><span class="sxs-lookup"><span data-stu-id="7ff3d-227">Monitor Azure Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [<span data-ttu-id="7ff3d-228">Azure Functions プロキシを操作します。</span><span class="sxs-lookup"><span data-stu-id="7ff3d-228">Work with Azure Functions Proxies</span></span>](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
><span data-ttu-id="7ff3d-229">[前へ](logic-apps.md)
>[次へ](durable-azure-functions.md)</span><span class="sxs-lookup"><span data-stu-id="7ff3d-229">[Previous](logic-apps.md)
[Next](durable-azure-functions.md)</span></span>
