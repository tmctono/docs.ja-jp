---
title: オーケストレーション パターン - サーバーレス アプリ
description: Azure の Durable functions の pr
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 18e13c5355490ef4a019ceda459114bdb6bfd539
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638803"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="2eee2-103">オーケストレーション パターン</span><span class="sxs-lookup"><span data-stu-id="2eee2-103">Orchestration patterns</span></span>

<span data-ttu-id="2eee2-104">Durable Functions は、サーバーレス環境で、個別の実行時間の長いアクティビティで構成されるステートフルなワークフローの作成を容易にします。</span><span class="sxs-lookup"><span data-stu-id="2eee2-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="2eee2-105">Durable Functions では、実行履歴のワークフローと定期的にチェックポイントの進行状況を追跡できます、ために適しているいくつかの興味深いパターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="2eee2-106">関数チェーン</span><span class="sxs-lookup"><span data-stu-id="2eee2-106">Function chaining</span></span>

<span data-ttu-id="2eee2-107">通常の順次プロセス アクティビティを特定の順序で 1 つずつ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eee2-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="2eee2-108">必要に応じて、今後のアクティビティには、前の関数の出力が必要です。</span><span class="sxs-lookup"><span data-stu-id="2eee2-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="2eee2-109">アクティビティの順序付けにおけるこの依存関係は、実行の関数チェーンを作成します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="2eee2-110">このワークフロー パターンを実装するために Durable Functions を使用する利点は、チェックポイント処理を実行するには、その能力から取得されます。</span><span class="sxs-lookup"><span data-stu-id="2eee2-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="2eee2-111">サーバーがクラッシュした場合、ネットワークがタイムアウトになるまたはその他の問題が発生した、Durable functions は、最後の既知の状態から再開し、別のサーバー上にある場合でも、ワークフローの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<bool>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

<span data-ttu-id="2eee2-112">上記のコード サンプル、`CallActivityAsync`関数は、データ センター内の仮想マシンで、特定のアクティビティを実行する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="2eee2-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="2eee2-113">Await 返し、基になるタスクが完了したら、実行は、履歴テーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="2eee2-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="2eee2-114">オーケストレーター関数のコードと、タスク並列ライブラリと async/await キーワードのおなじみの構成要素のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="2eee2-115">次のコードは簡略化された例のような`ProcessPayment`メソッドのようになります。</span><span class="sxs-lookup"><span data-stu-id="2eee2-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

```csharp
[FunctionName("ProcessPayment")]
public static bool ProcessPayment([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    ApplyCoupons(orderData);
    if(IssuePaymentRequest(orderData)) {
        return true;
    }

    return false;
}
```

## <a name="asynchronous-http-apis"></a><span data-ttu-id="2eee2-116">非同期 HTTP Api</span><span class="sxs-lookup"><span data-stu-id="2eee2-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="2eee2-117">ワークフローのアクティビティを完了するまでに比較的長い時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2eee2-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="2eee2-118">Blob ストレージにファイルにこのメディアのバックアップを開始するプロセスを想像してください。</span><span class="sxs-lookup"><span data-stu-id="2eee2-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="2eee2-119">このバックアップ プロセスは、サイズとメディア ファイルの数量に応じて、完了までに時間をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2eee2-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="2eee2-120">このシナリオで、`DurableOrchestrationClient`の実行中のワークフローの状態を確認する機能が便利になります。</span><span class="sxs-lookup"><span data-stu-id="2eee2-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="2eee2-121">使用する場合、 `HttpTrigger` 、ワークフローを開始する、`CreateCheckStatusResponse`メソッドを使用してのインスタンスを返す`HttpResponseMessage`します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="2eee2-122">この応答は、実行中のプロセスの状態を確認に使用できるペイロードの URI を持つクライアントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

```csharp
[FunctionName("OrderWorkflow")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient orchestrationClient)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

<span data-ttu-id="2eee2-123">次のサンプルの結果は、応答ペイロードの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="2eee2-124">優先する HTTP クライアントを使用して、GET 要求できる statusQueryGetUri で URI に実行中のワークフローの状態を検査します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="2eee2-125">返された状態の応答は次のコードのようになります。</span><span class="sxs-lookup"><span data-stu-id="2eee2-125">The returned status response should resemble the following code.</span></span>

```json
{
    "runtimeStatus": "Running",
    "input": {
        "$type": "DurableFunctionsDemos.OrderRequestData, DurableFunctionsDemos"
    },
    "output": null,
    "createdTime": "2018-01-01T00:22:05Z",
    "lastUpdatedTime": "2018-01-01T00:22:09Z"
}
```

<span data-ttu-id="2eee2-126">状態の応答がいずれかに変更は、プロセスでは、 **Failed**または**完了**します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="2eee2-127">正常に完了、**出力**ペイロード内のプロパティは、返されるデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="2eee2-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="2eee2-128">監視</span><span class="sxs-lookup"><span data-stu-id="2eee2-128">Monitoring</span></span>

<span data-ttu-id="2eee2-129">単純な定期的なタスクでは、Azure Functions の提供、 `TimerTrigger` CRON 式に基づくをスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2eee2-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="2eee2-130">タイマーは、単純な有効期間の短いタスクに適してより柔軟なスケジューリング機能が必要な場所のシナリオが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2eee2-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="2eee2-131">このシナリオ、監視パターンと永続的な関数が役立つ場合です。</span><span class="sxs-lookup"><span data-stu-id="2eee2-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="2eee2-132">Durable Functions は、柔軟なスケジュールの間隔、有効期間管理、および 1 つのオーケストレーション関数からの複数のモニター プロセスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2eee2-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="2eee2-133">この機能の 1 つのユース ケースは、特定のしきい値が満たされると終了の株価の変更の監視を作成することです。</span><span class="sxs-lookup"><span data-stu-id="2eee2-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

```csharp
[FunctionName("CheckStockPrice")]
public static async Task CheckStockPrice([OrchestrationTrigger] DurableOrchestrationContext context)
{
    StockWatcherInfo stockInfo = context.GetInput<StockWatcherInfo>();
    const int checkIntervalSeconds = 120;
    StockPrice initialStockPrice = null;

    DateTime fireAt;
    DateTime exitTime = context.CurrentUtcDateTime.Add(stockInfo.TimeLimit);

    while (context.CurrentUtcDateTime < exitTime)
    {
        StockPrice currentStockPrice = await context.CallActivityAsync<StockPrice>("GetStockPrice", stockInfo);

        if (initialStockPrice == null)
        {
            initialStockPrice = currentStockPrice;
            fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
            await context.CreateTimer(fireAt, CancellationToken.None);
            continue;
        }

        decimal percentageChange = (initialStockPrice.Price - currentStockPrice.Price) /
                               ((initialStockPrice.Price + currentStockPrice.Price) / 2);

        if (Math.Abs(percentageChange) >= stockInfo.PercentageChange)
        {
            // Change threshold detected
            await context.CallActivityAsync("NotifyStockPercentageChange", currentStockPrice);
            break;
        }

        // Sleep til next polling interval
        fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
        await context.CreateTimer(fireAt, CancellationToken.None);
    }
}
```

<span data-ttu-id="2eee2-134">`DurableOrchestrationContext``CreateTimer`の株価の変更を確認するメソッドが、ループの次の呼び出しに対して、スケジュールを設定します。</span><span class="sxs-lookup"><span data-stu-id="2eee2-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="2eee2-135">`DurableOrchestrationContext` また、 `CurrentUtcDateTime` UTC で現在の DateTime 値を取得するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2eee2-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="2eee2-136">このプロパティの代わりに使用することをお勧め`DateTime.UtcNow`のため、テスト、モックは簡単にします。</span><span class="sxs-lookup"><span data-stu-id="2eee2-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="2eee2-137">推奨リソース</span><span class="sxs-lookup"><span data-stu-id="2eee2-137">Recommended resources</span></span>

* [<span data-ttu-id="2eee2-138">Azure の Durable Functions</span><span class="sxs-lookup"><span data-stu-id="2eee2-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="2eee2-139">.NET Core と .NET Standard の単体テスト</span><span class="sxs-lookup"><span data-stu-id="2eee2-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="2eee2-140">[前へ](durable-azure-functions.md)
>[次へ](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="2eee2-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
