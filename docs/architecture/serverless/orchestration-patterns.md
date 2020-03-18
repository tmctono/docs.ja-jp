---
title: オーケストレーションのパターン - サーバーレス アプリ
description: Azure Durable Functions
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522638"
---
# <a name="orchestration-patterns"></a><span data-ttu-id="ba29b-103">オーケストレーションのパターン</span><span class="sxs-lookup"><span data-stu-id="ba29b-103">Orchestration patterns</span></span>

<span data-ttu-id="ba29b-104">Durable Functions を使用すると、サーバーレス環境で、実行時間の長い個別のアクティビティで構成されるステートフル ワークフローを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="ba29b-105">Durable Functions ではワークフローの進行状況を追跡でき、実行履歴が定期的にチェックポイント処理されるため、いくつかの興味深いパターンを実装するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="ba29b-106">関数チェーン</span><span class="sxs-lookup"><span data-stu-id="ba29b-106">Function chaining</span></span>

<span data-ttu-id="ba29b-107">一般的な連続プロセスでは、アクティビティを特定の順序で 1 つずつ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="ba29b-108">必要に応じて、次回のアクティビティで、前の関数からの出力が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="ba29b-109">このようにアクティビティの順序に依存することで、実行の関数チェーンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="ba29b-110">Durable Functions を使用してこのワークフロー パターンを実装する利点は、チェックポイント処理を実行できることにあります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="ba29b-111">サーバーがクラッシュした場合、ネットワークがタイムアウトした場合、またはその他の問題が発生した場合、Durable Functions では、別のサーバー上にある場合でも最後の既知の状態から再開し、ワークフローの実行を継続することができます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="ba29b-112">前のコード サンプルでは、`CallActivityAsync` 関数により、データ センター内の仮想マシンで特定のアクティビティが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="ba29b-113">await が返され、基になるタスクが完了すると、実行が履歴テーブルに記録されます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="ba29b-114">オーケストレーター関数のコードでは、タスク並列ライブラリの任意の使い慣れた構造と async/await キーワードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="ba29b-115">次のコードは、`ProcessPayment` メソッドがどのようになるかを示す簡単な例です。</span><span class="sxs-lookup"><span data-stu-id="ba29b-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="ba29b-116">非同期 HTTP API</span><span class="sxs-lookup"><span data-stu-id="ba29b-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="ba29b-117">場合によっては、ワークフローに含まれるアクティビティが、完了するのに比較的長い時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="ba29b-118">BLOB ストレージへのメディア ファイルのバックアップを開始するプロセスを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="ba29b-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="ba29b-119">メディア ファイルのサイズと数によっては、このバックアップ プロセスが完了するまでに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="ba29b-120">このシナリオでは、実行中のワークフローの状態を確認する `DurableOrchestrationClient` の機能が有用になります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="ba29b-121">`HttpTrigger` を使用してワークフローを開始する場合は、`CreateCheckStatusResponse` メソッドを使用して `HttpResponseMessage`のインスタンスを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="ba29b-122">この応答により、実行中のプロセスの状態を確認するために使用できるペイロードの URI がクライアントに提供されます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="ba29b-123">次のサンプル結果は、応答ペイロードの構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="ba29b-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="ba29b-124">任意の HTTP クライアントを使用して、statusQueryGetUri の URI に対して GET 要求を作成し、実行中のワークフローの状態を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="ba29b-125">返される状態の応答は、次のコードのようになります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="ba29b-126">プロセスが続行されると、状態の応答は **Failed** または **Completed** に変わります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="ba29b-127">正常に完了した場合、ペイロード内の **output** プロパティには、返されたデータがすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="ba29b-128">監視</span><span class="sxs-lookup"><span data-stu-id="ba29b-128">Monitoring</span></span>

<span data-ttu-id="ba29b-129">単純な定期的なタスクの場合、Azure Functions では、CRON 式に基づいてスケジュールできる `TimerTrigger` が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="ba29b-130">タイマーは、単純で短時間のタスクには適していますが、より柔軟なスケジュール設定が必要なシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="ba29b-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="ba29b-131">このようなシナリオでは、監視パターンと Durable Functions が役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="ba29b-132">Durable Functions では、柔軟なスケジュール設定間隔と有効期間の管理を実現できるほか、1 つのオーケストレーション関数から複数の監視プロセスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="ba29b-133">この機能のユース ケースの 1 つとして、特定のしきい値が満たされると完了する株価の変動に対してウォッチャーを作成することが考えられます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="ba29b-134">`DurableOrchestrationContext` の `CreateTimer` メソッドにより、株価の変動を確認するために、ループの次回の呼び出しのスケジュールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="ba29b-135">`DurableOrchestrationContext` には、現在の DateTime 値 (UTC) を取得するための `CurrentUtcDateTime` プロパティも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba29b-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="ba29b-136">テスト用に簡単にモックできるため、`DateTime.UtcNow` の代わりにこのプロパティを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ba29b-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="ba29b-137">推奨リソース</span><span class="sxs-lookup"><span data-stu-id="ba29b-137">Recommended resources</span></span>

- [<span data-ttu-id="ba29b-138">Azure Durable Functions</span><span class="sxs-lookup"><span data-stu-id="ba29b-138">Azure Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="ba29b-139">.NET Core と .NET Standard の単体テスト</span><span class="sxs-lookup"><span data-stu-id="ba29b-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="ba29b-140">[前へ](durable-azure-functions.md)
>[次へ](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="ba29b-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
