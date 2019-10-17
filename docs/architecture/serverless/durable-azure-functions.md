---
title: 持続性のある Azure functions-サーバーレスアプリ
description: 持続性のある Azure functions により、Azure Functions ランタイムが拡張され、コードでステートフルワークフローが有効になります。
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522855"
---
# <a name="durable-azure-functions"></a><span data-ttu-id="fa578-103">永続的な Azure Functions</span><span class="sxs-lookup"><span data-stu-id="fa578-103">Durable Azure functions</span></span>

<span data-ttu-id="fa578-104">Azure Functions でサーバーレスアプリケーションを作成する場合、通常、操作はステートレスな方法で実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="fa578-104">When creating serverless applications with Azure Functions, your operations will typically be designed to run in a stateless manner.</span></span> <span data-ttu-id="fa578-105">この設計を選択する理由は、プラットフォームの規模が拡大するにつれて、コードが実行されているサーバーを把握するのが困難になるためです。</span><span class="sxs-lookup"><span data-stu-id="fa578-105">The reason for this design choice is because as the platform scales, it becomes difficult to know what servers the code is running on.</span></span> <span data-ttu-id="fa578-106">また、特定の時点でアクティブになっているインスタンスの数を把握することも困難になります。</span><span class="sxs-lookup"><span data-stu-id="fa578-106">It also becomes difficult to know how many instances are active at any given point.</span></span> <span data-ttu-id="fa578-107">ただし、プロセスの現在の状態を把握しておく必要があるアプリケーションのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="fa578-107">However, there are classes of applications that require the current state of a process to be known.</span></span> <span data-ttu-id="fa578-108">オンラインストアに注文を送信するプロセスを検討します。</span><span class="sxs-lookup"><span data-stu-id="fa578-108">Consider the process of submitting an order to an online store.</span></span> <span data-ttu-id="fa578-109">チェックアウト操作は、プロセスの状態を知る必要がある複数の操作で構成されるワークフローである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-109">The checkout operation might be a workflow that is composed of multiple operations that need to know the state of the process.</span></span> <span data-ttu-id="fa578-110">このような情報には、顧客が自分のアカウントにクレジットを持っている場合や、クレジットカードを処理した結果が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-110">Such information may include the product inventory, if the customer has any credits on their account, and also the results of processing the credit card.</span></span> <span data-ttu-id="fa578-111">これらの操作は、独自の内部ワークフローや、サードパーティのシステムからのサービスとして簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa578-111">These operations could easily be their own internal workflows or even services from third-party systems.</span></span>

<span data-ttu-id="fa578-112">現在、内部システムと外部システムの間でのアプリケーションの状態の調整に役立つさまざまなパターンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fa578-112">Various patterns exist today that assist with the coordination of application state between internal and external systems.</span></span> <span data-ttu-id="fa578-113">集中管理されたキューシステム、分散キー値ストア、または共有データベースを使用してその状態を管理するソリューションによって、一般的に発生します。</span><span class="sxs-lookup"><span data-stu-id="fa578-113">It's common to come across solutions that rely on centralized queuing systems, distributed key-value stores, or shared databases to manage that state.</span></span> <span data-ttu-id="fa578-114">ただし、これらは、プロビジョニングと管理が必要なすべての追加リソースです。</span><span class="sxs-lookup"><span data-stu-id="fa578-114">However, these are all additional resources that now need to be provisioned and managed.</span></span> <span data-ttu-id="fa578-115">サーバーレス環境では、これらのリソースを手動で調整しようとすると、コードが煩雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-115">In a serverless environment, your code could become cumbersome trying to coordinate with these resources manually.</span></span> <span data-ttu-id="fa578-116">Azure Functions には、Durable Functions と呼ばれるステートフル関数を作成するための代替手段が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fa578-116">Azure Functions offers an alternative for creating stateful functions called Durable Functions.</span></span>

<span data-ttu-id="fa578-117">Durable Functions は、コードでステートフルワークフローを定義できるようにする、Azure Functions ランタイムの拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="fa578-117">Durable Functions is an extension to the Azure Functions runtime that enables the definition of stateful workflows in code.</span></span> <span data-ttu-id="fa578-118">ワークフローをアクティビティに分割することにより、Durable Functions の拡張機能は、状態の管理、進行状況のチェックポイントの作成、およびサーバー間での関数呼び出しの分散の処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa578-118">By breaking down workflows into activities, the Durable Functions extension can manage state, create progress checkpoints, and handle the distribution of function calls across servers.</span></span> <span data-ttu-id="fa578-119">バックグラウンドでは、Azure Storage アカウントを使用して、実行履歴の保持、アクティビティ関数のスケジュール設定、および応答の取得を行います。</span><span class="sxs-lookup"><span data-stu-id="fa578-119">In the background, it makes use of an Azure Storage account to persist execution history, schedule activity functions and retrieve responses.</span></span> <span data-ttu-id="fa578-120">サーバーレスコードは、そのストレージアカウント内の永続化された情報と対話することはできません。通常、開発者が操作する必要のあるものではありません。</span><span class="sxs-lookup"><span data-stu-id="fa578-120">Your serverless code should never interact with persisted information in that storage account, and is typically not something with which developers need to interact.</span></span>

## <a name="triggering-a-stateful-workflow"></a><span data-ttu-id="fa578-121">ステートフルワークフローのトリガー</span><span class="sxs-lookup"><span data-stu-id="fa578-121">Triggering a stateful workflow</span></span>

<span data-ttu-id="fa578-122">Durable Functions のステートフルワークフローは、次の2つの組み込みコンポーネントに分けることができます。オーケストレーショントリガーとアクティビティトリガー。</span><span class="sxs-lookup"><span data-stu-id="fa578-122">Stateful workflows in Durable Functions can be broken down into two intrinsic components; orchestration and activity triggers.</span></span> <span data-ttu-id="fa578-123">トリガーとバインドは、Azure Functions によって使用されるコアコンポーネントであり、サーバーレス関数が、開始、入力の受信、および結果を返すときに通知を受け取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="fa578-123">Triggers and bindings are core components used by Azure Functions to enable your serverless functions to be notified when to start, receive input, and return results.</span></span>

### <a name="working-with-the-orchestration-client"></a><span data-ttu-id="fa578-124">Orchestration クライアントの操作</span><span class="sxs-lookup"><span data-stu-id="fa578-124">Working with the Orchestration client</span></span>

<span data-ttu-id="fa578-125">オーケストレーションは、Azure Functions でトリガーされた操作の他のスタイルと比較した場合に一意です。</span><span class="sxs-lookup"><span data-stu-id="fa578-125">Orchestrations are unique when compared to other styles of triggered operations in Azure Functions.</span></span> <span data-ttu-id="fa578-126">Durable Functions では、完了までに数時間または数日かかる可能性のある関数を実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-126">Durable Functions enables the execution of functions that may take hours or even days to complete.</span></span> <span data-ttu-id="fa578-127">この種類の動作には、実行中のオーケストレーションの状態を確認したり、事前にを終了したり、外部イベントの通知を送信したりできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-127">That type of behavior comes with the need to able to check the status of a running orchestration, preemptively terminate, or send notifications of external events.</span></span>

<span data-ttu-id="fa578-128">このような場合、Durable Functions 拡張機能は、調整された関数と対話できるようにするための @no__t 0 のクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fa578-128">For such cases, the Durable Functions extension provides the `DurableOrchestrationClient` class that allows you to interact with orchestrated functions.</span></span> <span data-ttu-id="fa578-129">@No__t-0 バインドを使用して、オーケストレーションクライアントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fa578-129">You get access to the orchestration client by using the `OrchestrationClientAttribute` binding.</span></span> <span data-ttu-id="fa578-130">通常は、この属性を別のトリガーの種類 (`HttpTrigger` や `ServiceBusTrigger` など) と共に追加します。</span><span class="sxs-lookup"><span data-stu-id="fa578-130">Generally, you would include this attribute with another trigger type, such as an `HttpTrigger` or `ServiceBusTrigger`.</span></span> <span data-ttu-id="fa578-131">ソース関数がトリガーされたら、オーケストレーションクライアントを使用して orchestrator 関数を開始できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-131">Once the source function has been triggered, the orchestration client can be used to start an orchestrator function.</span></span>

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

### <a name="the-orchestrator-function"></a><span data-ttu-id="fa578-132">Orchestrator 関数</span><span class="sxs-lookup"><span data-stu-id="fa578-132">The orchestrator function</span></span>

<span data-ttu-id="fa578-133">Azure Functions マークの OrchestrationTriggerAttribute を使用して関数に注釈を付けると、orchestrator 関数として機能します。</span><span class="sxs-lookup"><span data-stu-id="fa578-133">Annotating a function with the OrchestrationTriggerAttribute in Azure Functions marks that function as an orchestrator function.</span></span> <span data-ttu-id="fa578-134">ステートフルワークフローを構成するさまざまなアクティビティを管理する責任があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-134">It's responsible for managing the various activities that make up your stateful workflow.</span></span>

<span data-ttu-id="fa578-135">Orchestrator 関数で、OrchestrationTriggerAttribute 以外のバインドを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa578-135">Orchestrator functions are unable to make use of bindings other than the OrchestrationTriggerAttribute.</span></span> <span data-ttu-id="fa578-136">この属性は、パラメーターの型が DurableOrchestrationContext の場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-136">This attribute can only be used with a parameter type of DurableOrchestrationContext.</span></span> <span data-ttu-id="fa578-137">関数シグネチャの入力の逆シリアル化がサポートされていないため、他の入力を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa578-137">No other inputs can be used since deserialization of inputs in the function signature isn't supported.</span></span> <span data-ttu-id="fa578-138">Orchestration クライアントによって提供される入力を取得するには、GetInput @ no__t-0T @ no__t-1 メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-138">To get inputs provided by the orchestration client, the GetInput\<T\> method must be used.</span></span>

<span data-ttu-id="fa578-139">また、オーケストレーション関数の戻り値の型は、void、Task、または JSON のシリアル化可能な値のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-139">Also, the return types of orchestration functions must be either void, Task, or a JSON serializable value.</span></span>

> <span data-ttu-id="fa578-140">*簡潔にするためにエラー処理コードが残されました*</span><span class="sxs-lookup"><span data-stu-id="fa578-140">*Error handling code has been left out for brevity*</span></span>

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

<span data-ttu-id="fa578-141">オーケストレーションの複数のインスタンスを同時に開始して実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-141">Multiple instances of an orchestration can be started and running at the same time.</span></span> <span data-ttu-id="fa578-142">@No__t で `StartNewAsync` メソッドを呼び出すと、オーケストレーションの新しいインスタンスが起動されます。</span><span class="sxs-lookup"><span data-stu-id="fa578-142">Calling the `StartNewAsync` method on the `DurableOrchestrationClient` launches a new instance of the orchestration.</span></span> <span data-ttu-id="fa578-143">メソッドは、オーケストレーションが開始されたときに完了する @no__t 0 を返します。</span><span class="sxs-lookup"><span data-stu-id="fa578-143">The method returns a `Task<string>` that completes when the orchestration has started.</span></span> <span data-ttu-id="fa578-144">オーケストレーションが30秒以内に開始されなかった場合は、`TimeoutException` 型の例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="fa578-144">An exception of type `TimeoutException` gets thrown if the orchestration hasn't started within 30 seconds.</span></span>

<span data-ttu-id="fa578-145">@No__t-1 の完了した `Task<string>` には、オーケストレーションインスタンスの一意の ID が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-145">The completed `Task<string>` from `StartNewAsync` should contain the unique ID of the orchestration instance.</span></span> <span data-ttu-id="fa578-146">このインスタンス ID を使用して、その特定のオーケストレーションに対する操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fa578-146">This instance ID can be used to invoke operations on that specific orchestration.</span></span> <span data-ttu-id="fa578-147">オーケストレーションの状態を照会したり、イベント通知を送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa578-147">The orchestration can be queried for the status or sent event notifications.</span></span>

### <a name="the-activity-functions"></a><span data-ttu-id="fa578-148">アクティビティ関数</span><span class="sxs-lookup"><span data-stu-id="fa578-148">The activity functions</span></span>

<span data-ttu-id="fa578-149">アクティビティ関数は、ワークフローを作成するためにオーケストレーション関数内にまとめて構成される個別の操作です。</span><span class="sxs-lookup"><span data-stu-id="fa578-149">Activity functions are the discrete operations that get composed together within an orchestration function to create the workflow.</span></span> <span data-ttu-id="fa578-150">ここでは、実際の作業のほとんどが行われます。</span><span class="sxs-lookup"><span data-stu-id="fa578-150">Here is where most of actual work would take place.</span></span> <span data-ttu-id="fa578-151">これらは、ビジネスロジック、長時間実行されるプロセス、およびパズルの部分を大規模なソリューションに表します。</span><span class="sxs-lookup"><span data-stu-id="fa578-151">They represent the business logic, long running processes, and the puzzle pieces to a larger solution.</span></span>

<span data-ttu-id="fa578-152">@No__t-0 は、型 `DurableActivityContext` の関数パラメーターに注釈を付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa578-152">The `ActivityTriggerAttribute` is used to annotate a function parameter of type `DurableActivityContext`.</span></span> <span data-ttu-id="fa578-153">注釈を使用すると、関数がアクティビティ関数として使用されることをランタイムに通知します。</span><span class="sxs-lookup"><span data-stu-id="fa578-153">Using the annotation informs the runtime that the function is intended to be used as an activity function.</span></span> <span data-ttu-id="fa578-154">アクティビティ関数への入力値は、`DurableActivityContext` パラメーターの `GetInput<T>` メソッドを使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="fa578-154">Input values to activity functions are retrieved using the `GetInput<T>` method of the `DurableActivityContext` parameter.</span></span>

<span data-ttu-id="fa578-155">オーケストレーション関数と同様に、アクティビティ関数の戻り値の型は、void、Task、または JSON のシリアル化可能な値のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa578-155">Similar to orchestration functions, the return types of activity functions must be either void, Task, or a JSON serializable value.</span></span>

<span data-ttu-id="fa578-156">アクティビティ関数内でスローされた未処理の例外は、呼び出し元の orchestrator 関数に送信され、@no__t 0 として表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa578-156">Any unhandled exceptions that get thrown within activity functions will get sent up to the calling orchestrator function and presented as a `TaskFailedException`.</span></span> <span data-ttu-id="fa578-157">この時点で、エラーが検出され、orchestrator に記録され、アクティビティを再試行できます。</span><span class="sxs-lookup"><span data-stu-id="fa578-157">At this point, the error can be caught and logged in the orchestrator, and the activity can be retried.</span></span>

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a><span data-ttu-id="fa578-158">推奨されるリソース</span><span class="sxs-lookup"><span data-stu-id="fa578-158">Recommended resources</span></span>

- [<span data-ttu-id="fa578-159">Durable Functions</span><span class="sxs-lookup"><span data-stu-id="fa578-159">Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="fa578-160">Durable Functions のバインド</span><span class="sxs-lookup"><span data-stu-id="fa578-160">Bindings for Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [<span data-ttu-id="fa578-161">Durable Functions でのインスタンスの管理</span><span class="sxs-lookup"><span data-stu-id="fa578-161">Manage instances in Durable Functions</span></span>](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
><span data-ttu-id="fa578-162">[前へ](event-grid.md)
>[次へ](orchestration-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="fa578-162">[Previous](event-grid.md)
[Next](orchestration-patterns.md)</span></span>
