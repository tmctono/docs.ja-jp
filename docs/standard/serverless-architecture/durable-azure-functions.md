---
title: 持続性のある Azure functions でサーバーレス アプリ
description: 持続性のある Azure functions では、コード内のステートフルなワークフローを有効にする Azure Functions ランタイムを拡張します。
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: f7ee74926d6658042120113b49dc763383881423
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643399"
---
# <a name="durable-azure-functions"></a><span data-ttu-id="528b1-103">永続的な Azure Functions</span><span class="sxs-lookup"><span data-stu-id="528b1-103">Durable Azure functions</span></span>

<span data-ttu-id="528b1-104">Azure Functions でサーバーレス アプリケーションを作成するときに、オペレーション通常ステートレスな方法で実行する設計されています。</span><span class="sxs-lookup"><span data-stu-id="528b1-104">When creating serverless applications with Azure Functions, your operations will typically be designed to run in a stateless manner.</span></span> <span data-ttu-id="528b1-105">この設計の選択の理由としてのプラットフォームのスケールがでコードが実行されているどのサーバーがわかりにくいためにです。</span><span class="sxs-lookup"><span data-stu-id="528b1-105">The reason for this design choice is because as the platform scales, it becomes difficult to know what servers the code is running on.</span></span> <span data-ttu-id="528b1-106">難しく特定の時点でアクティブなインスタンスの数を把握します。</span><span class="sxs-lookup"><span data-stu-id="528b1-106">It also becomes difficult to know how many instances are active at any given point.</span></span> <span data-ttu-id="528b1-107">ただし、これには既知であるプロセスの現在の状態を必要とするアプリケーションのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="528b1-107">However, there are classes of applications that require the current state of a process to be known.</span></span> <span data-ttu-id="528b1-108">オンライン ストアへの注文を送信するプロセスを検討してください。</span><span class="sxs-lookup"><span data-stu-id="528b1-108">Consider the process of submitting an order to an online store.</span></span> <span data-ttu-id="528b1-109">チェック アウト操作には、ワークフロー、プロセスの状態を確認する必要がある複数の操作を構成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="528b1-109">The checkout operation might be a workflow that is composed of multiple operations that need to know the state of the process.</span></span> <span data-ttu-id="528b1-110">お客様は、クレジット カードの処理の結果と自分のアカウントでは、上の任意のクレジットを持っている場合、このような情報は、製品在庫を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="528b1-110">Such information may include the product inventory, if the customer has any credits on their account, and also the results of processing the credit card.</span></span> <span data-ttu-id="528b1-111">これらの操作は、独自の内部ワークフローまたはサード パーティ システムからもサービスに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="528b1-111">These operations could easily be their own internal workflows or even services from third-party systems.</span></span>

<span data-ttu-id="528b1-112">さまざまなパターンは、内部および外部のシステム間でアプリケーションの状態の調整時に役立つ今日存在します。</span><span class="sxs-lookup"><span data-stu-id="528b1-112">Various patterns exist today that assist with the coordination of application state between internal and external systems.</span></span> <span data-ttu-id="528b1-113">一元化されたキュー システム、分散キー値ストア、またはその状態を管理する共有データベースに依存するソリューション全体が一般的です。</span><span class="sxs-lookup"><span data-stu-id="528b1-113">It's common to come across solutions that rely on centralized queuing systems, distributed key-value stores, or shared databases to manage that state.</span></span> <span data-ttu-id="528b1-114">ただし、これらは、ここでプロビジョニングし、管理する必要がある他のすべてのリソースです。</span><span class="sxs-lookup"><span data-stu-id="528b1-114">However, these are all additional resources that now need to be provisioned and managed.</span></span> <span data-ttu-id="528b1-115">サーバーレス環境でコードを手動でこれらのリソースと調整しようとしています。 面倒になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="528b1-115">In a serverless environment, your code could become cumbersome trying to coordinate with these resources manually.</span></span> <span data-ttu-id="528b1-116">Azure Functions では、Durable Functions と呼ばれるステートフル関数を作成するための代替を提供します。</span><span class="sxs-lookup"><span data-stu-id="528b1-116">Azure Functions offers an alternative for creating stateful functions called Durable Functions.</span></span>

<span data-ttu-id="528b1-117">Durable Functions では、コード内のステートフルなワークフローの定義をできるようにする Azure Functions ランタイムの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="528b1-117">Durable Functions is an extension to the Azure Functions runtime that enables the definition of stateful workflows in code.</span></span> <span data-ttu-id="528b1-118">Durable Functions 拡張機能が状態を管理できますをアクティビティにワークフローを分解することによってには、進行状況のチェックポイントを作成して、サーバー間で関数呼び出しの配布を処理します。</span><span class="sxs-lookup"><span data-stu-id="528b1-118">By breaking down workflows into activities, the Durable Functions extension can manage state, create progress checkpoints, and handle the distribution of function calls across servers.</span></span> <span data-ttu-id="528b1-119">バック グラウンドでの Azure Storage アカウントを使用して実行履歴が保持、アクティビティ関数をスケジュールし、応答の取得になります。</span><span class="sxs-lookup"><span data-stu-id="528b1-119">In the background, it makes use of an Azure Storage account to persist execution history, schedule activity functions and retrieve responses.</span></span> <span data-ttu-id="528b1-120">サーバーレス コードを使用して、そのストレージ アカウントに永続化された情報ことはありません対話する必要がありますでは通常ありません、開発者は対話する必要があります。</span><span class="sxs-lookup"><span data-stu-id="528b1-120">Your serverless code should never interact with persisted information in that storage account, and is typically not something with which developers need to interact.</span></span>

## <a name="triggering-a-stateful-workflow"></a><span data-ttu-id="528b1-121">ステートフルなワークフローをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="528b1-121">Triggering a stateful workflow</span></span>

<span data-ttu-id="528b1-122">Durable Functions のステートフルなワークフローを 2 つの組み込みコンポーネント; に細分化できます。オーケストレーションとアクティビティがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="528b1-122">Stateful workflows in Durable Functions can be broken down into two intrinsic components; orchestration and activity triggers.</span></span> <span data-ttu-id="528b1-123">トリガーとバインドは、Azure Functions でサーバーレス関数を開始して受信するには、次のように入力、および結果を返すときに通知を有効にするために使用するコア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="528b1-123">Triggers and bindings are core components used by Azure Functions to enable your serverless functions to be notified when to start, receive input, and return results.</span></span>

### <a name="working-with-the-orchestration-client"></a><span data-ttu-id="528b1-124">オーケストレーション クライアントの使用</span><span class="sxs-lookup"><span data-stu-id="528b1-124">Working with the Orchestration client</span></span>

<span data-ttu-id="528b1-125">オーケストレーションは、Azure Functions でトリガーされた操作の他のスタイルと比較した場合に一意です。</span><span class="sxs-lookup"><span data-stu-id="528b1-125">Orchestrations are unique when compared to other styles of triggered operations in Azure Functions.</span></span> <span data-ttu-id="528b1-126">Durable Functions では、時間がかかる場合があります、または完了するまで関数を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="528b1-126">Durable Functions enables the execution of functions that may take hours or even days to complete.</span></span> <span data-ttu-id="528b1-127">その種類の動作を実行中のオーケストレーションの状態を確認することが必要事前終了、または外部イベントの通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="528b1-127">That type of behavior comes with the need to able to check the status of a running orchestration, preemptively terminate, or send notifications of external events.</span></span>

<span data-ttu-id="528b1-128">このような場合は、Durable Functions 拡張機能を提供します、`DurableOrchestrationClient`と対話できるクラスは、関数を調整します。</span><span class="sxs-lookup"><span data-stu-id="528b1-128">For such cases, the Durable Functions extension provides the `DurableOrchestrationClient` class that allows you to interact with orchestrated functions.</span></span> <span data-ttu-id="528b1-129">使用して、オーケストレーション クライアントにアクセスすること、`OrchestrationClientAttribute`バインドします。</span><span class="sxs-lookup"><span data-stu-id="528b1-129">You get access to the orchestration client by using the `OrchestrationClientAttribute` binding.</span></span> <span data-ttu-id="528b1-130">一般に、するはこの属性を含めるもう 1 つのトリガーの種類をなど、`HttpTrigger`または`ServiceBusTrigger`します。</span><span class="sxs-lookup"><span data-stu-id="528b1-130">Generally, you would include this attribute with another trigger type, such as an `HttpTrigger` or `ServiceBusTrigger`.</span></span> <span data-ttu-id="528b1-131">ソース関数がトリガーされると後、は、オーケストレーター関数を開始するオーケストレーション クライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="528b1-131">Once the source function has been triggered, the orchestration client can be used to start an orchestrator function.</span></span>

```csharp
[FunctionName("KickOff")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient<orchestrationClient>)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

### <a name="the-orchestrator-function"></a><span data-ttu-id="528b1-132">オーケストレーター関数</span><span class="sxs-lookup"><span data-stu-id="528b1-132">The orchestrator function</span></span>

<span data-ttu-id="528b1-133">注釈を付けることで Azure Functions OrchestrationTriggerAttribute で関数をその関数、オーケストレーター関数として。</span><span class="sxs-lookup"><span data-stu-id="528b1-133">Annotating a function with the OrchestrationTriggerAttribute in Azure Functions marks that function as an orchestrator function.</span></span> <span data-ttu-id="528b1-134">ステートフルなワークフローを構成するさまざまなアクティビティの管理を担当します。</span><span class="sxs-lookup"><span data-stu-id="528b1-134">It's responsible for managing the various activities that make up your stateful workflow.</span></span>

<span data-ttu-id="528b1-135">オーケストレーター関数は、作成することはできません、OrchestrationTriggerAttribute 以外のバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="528b1-135">Orchestrator functions are unable to make use of bindings other than the OrchestrationTriggerAttribute.</span></span> <span data-ttu-id="528b1-136">この属性は、DurableOrchestrationContext のパラメーターの型でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="528b1-136">This attribute can only be used with a parameter type of DurableOrchestrationContext.</span></span> <span data-ttu-id="528b1-137">関数シグネチャ内で入力の逆シリアル化がサポートされていないために、他の入力は使用されません。</span><span class="sxs-lookup"><span data-stu-id="528b1-137">No other inputs can be used since deserialization of inputs in the function signature isn't supported.</span></span> <span data-ttu-id="528b1-138">オーケストレーション クライアント、GetInput によって指定された入力を取得する\<T\>メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="528b1-138">To get inputs provided by the orchestration client, the GetInput\<T\> method must be used.</span></span>

<span data-ttu-id="528b1-139">また、オーケストレーション関数の戻り値の型がある必要がありますか void、タスク、または JSON のシリアル化可能な値。</span><span class="sxs-lookup"><span data-stu-id="528b1-139">Also, the return types of orchestration functions must be either void, Task, or a JSON serializable value.</span></span>

> <span data-ttu-id="528b1-140">*エラー処理コードが簡潔にするため省略してをいます*</span><span class="sxs-lookup"><span data-stu-id="528b1-140">*Error handling code has been left out for brevity*</span></span>

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<string>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

<span data-ttu-id="528b1-141">オーケストレーションの複数のインスタンスは、同時に開始され、実行中にすることができます。</span><span class="sxs-lookup"><span data-stu-id="528b1-141">Multiple instances of an orchestration can be started and running at the same time.</span></span> <span data-ttu-id="528b1-142">呼び出す、`StartNewAsync`メソッドを`DurableOrchestrationClient`オーケストレーションの新しいインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="528b1-142">Calling the `StartNewAsync` method on the `DurableOrchestrationClient` launches a new instance of the orchestration.</span></span> <span data-ttu-id="528b1-143">メソッドを返します、`Task<string>`オーケストレーションが開始されたときに完了します。</span><span class="sxs-lookup"><span data-stu-id="528b1-143">The method returns a `Task<string>` that completes when the orchestration has started.</span></span> <span data-ttu-id="528b1-144">型の例外`TimeoutException`30 秒以内に、オーケストレーションが開始されていない場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="528b1-144">An exception of type `TimeoutException` gets thrown if the orchestration hasn't started within 30 seconds.</span></span>

<span data-ttu-id="528b1-145">完成した`Task<string>`から`StartNewAsync`オーケストレーション インスタンスの一意の ID を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="528b1-145">The completed `Task<string>` from `StartNewAsync` should contain the unique ID of the orchestration instance.</span></span> <span data-ttu-id="528b1-146">このインスタンス ID は、その特定のオーケストレーションでの操作の呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="528b1-146">This instance ID can be used to invoke operations on that specific orchestration.</span></span> <span data-ttu-id="528b1-147">オーケストレーションの状態の照会またはイベント通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="528b1-147">The orchestration can be queried for the status or sent event notifications.</span></span>

### <a name="the-activity-functions"></a><span data-ttu-id="528b1-148">アクティビティ関数</span><span class="sxs-lookup"><span data-stu-id="528b1-148">The activity functions</span></span>

<span data-ttu-id="528b1-149">アクティビティ関数は、個別の操作をまとめて、ワークフローを作成するオーケストレーション関数内で、構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="528b1-149">Activity functions are the discrete operations that get composed together within an orchestration function to create the workflow.</span></span> <span data-ttu-id="528b1-150">実際の作業のほとんどが行う場所を示します。</span><span class="sxs-lookup"><span data-stu-id="528b1-150">Here is where most of actual work would take place.</span></span> <span data-ttu-id="528b1-151">ビジネス ロジックを表す、実行中のプロセス、および大規模なソリューションにパズルのピースを長いが。</span><span class="sxs-lookup"><span data-stu-id="528b1-151">They represent the business logic, long running processes, and the puzzle pieces to a larger solution.</span></span>

<span data-ttu-id="528b1-152">`ActivityTriggerAttribute`型の関数パラメーターの注釈を設定するために使用`DurableActivityContext`します。</span><span class="sxs-lookup"><span data-stu-id="528b1-152">The `ActivityTriggerAttribute` is used to annotate a function parameter of type `DurableActivityContext`.</span></span> <span data-ttu-id="528b1-153">注釈を使用して通知、ランタイム関数はアクティビティ関数として使用するものであります。</span><span class="sxs-lookup"><span data-stu-id="528b1-153">Using the annotation informs the runtime that the function is intended to be used as an activity function.</span></span> <span data-ttu-id="528b1-154">使用してアクティビティ関数の入力値を取得、`GetInput<T>`のメソッド、`DurableActivityContext`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="528b1-154">Input values to activity functions are retrieved using the `GetInput<T>` method of the `DurableActivityContext` parameter.</span></span>

<span data-ttu-id="528b1-155">オーケストレーション関数と同様に、アクティビティ関数の戻り値の型がである void、タスク、または JSON のシリアル化可能な値。</span><span class="sxs-lookup"><span data-stu-id="528b1-155">Similar to orchestration functions, the return types of activity functions must be either void, Task, or a JSON serializable value.</span></span>

<span data-ttu-id="528b1-156">アクティビティ関数内でスローされる例外を呼び出し元のオーケストレーター関数に送信されとして示されますが取得、`TaskFailedException`します。</span><span class="sxs-lookup"><span data-stu-id="528b1-156">Any unhandled exceptions that get thrown within activity functions will get sent up to the calling orchestrator function and presented as a `TaskFailedException`.</span></span> <span data-ttu-id="528b1-157">この時点では、エラーをキャッチして、orchestrator のログに記録でき、アクティビティを再試行することができます。</span><span class="sxs-lookup"><span data-stu-id="528b1-157">At this point, the error can be caught and logged in the orchestrator, and the activity can be retried.</span></span>

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a><span data-ttu-id="528b1-158">推奨リソース</span><span class="sxs-lookup"><span data-stu-id="528b1-158">Recommended resources</span></span>

* [<span data-ttu-id="528b1-159">Durable Functions</span><span class="sxs-lookup"><span data-stu-id="528b1-159">Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [<span data-ttu-id="528b1-160">Durable Functions のバインド</span><span class="sxs-lookup"><span data-stu-id="528b1-160">Bindings for Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
* [<span data-ttu-id="528b1-161">Durable Functions でのインスタンスを管理します。</span><span class="sxs-lookup"><span data-stu-id="528b1-161">Manage instances in Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
><span data-ttu-id="528b1-162">[前へ](event-grid.md)
>[次へ](orchestration-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="528b1-162">[Previous](event-grid.md)
[Next](orchestration-patterns.md)</span></span>
