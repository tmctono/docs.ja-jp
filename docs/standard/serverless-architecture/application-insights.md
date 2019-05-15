---
title: Application Insights - サーバーレス アプリ
description: Application Insights は、サーバーレス診断プラットフォーム開発者を検出、トリアージ、および web アプリ、モバイル アプリ、デスクトップ アプリ、マイクロ サービスでの問題を診断できます。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 1f5b99fba448c2c1c12139524ffdcd3708b3c956
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643351"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="4a343-103">Application Insights のテレメトリ</span><span class="sxs-lookup"><span data-stu-id="4a343-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="4a343-104">[Application Insights](https://docs.microsoft.com/azure/application-insights)サーバーレス診断プラットフォーム開発者を検出、トリアージ、および web アプリ、モバイル アプリ、デスクトップ アプリ、およびマイクロ サービスでの問題を診断できます。</span><span class="sxs-lookup"><span data-stu-id="4a343-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="4a343-105">ポータルで、スイッチを反転するだけで関数アプリで Application Insights にできます。</span><span class="sxs-lookup"><span data-stu-id="4a343-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="4a343-106">Application Insights では、サーバーを構成したり、独自のデータベースを設定することがなくこれらすべての機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a343-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="4a343-107">すべての Application Insights の機能は、自動的に、アプリと統合されたサービスとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="4a343-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Application Insights のロゴ](./media/application-insights-logo.png)

<span data-ttu-id="4a343-109">既存のアプリに Application Insights を追加することは、アプリケーションの設定に、インストルメンテーション キーを追加する同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="4a343-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="4a343-110">Application Insights は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="4a343-110">With Application Insights you can:</span></span>

* <span data-ttu-id="4a343-111">カスタムのグラフと、関数、および例外の実行にかかる時間に、関数の呼び出しの数などのメトリックに基づいてアラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a343-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="4a343-112">サーバー例外とエラーを分析します。</span><span class="sxs-lookup"><span data-stu-id="4a343-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="4a343-113">操作によってパフォーマンスにドリルダウンして、サード パーティの依存関係の呼び出しにかかる時間を測定します。</span><span class="sxs-lookup"><span data-stu-id="4a343-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="4a343-114">関数アプリをホストするすべてのサーバー間での CPU 使用率、メモリ、および料金を監視します。</span><span class="sxs-lookup"><span data-stu-id="4a343-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="4a343-115">要求の数と、関数アプリの待機時間などのメトリックのライブ ストリームを表示します。</span><span class="sxs-lookup"><span data-stu-id="4a343-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="4a343-116">使用[Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)を検索するには、クエリ、および関数、データに対するカスタム グラフを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a343-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![メトリックス エクスプ ローラー](./media/metrics-explorer.png)

<span data-ttu-id="4a343-118">組み込みのテレメトリに加えて、カスタム テレメトリを生成することがもします。</span><span class="sxs-lookup"><span data-stu-id="4a343-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="4a343-119">次のコード スニペットは、インストルメンテーション キーを関数アプリの設定を使用してカスタムのテレメトリ クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a343-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="4a343-120">次のコードに新しい行の挿入にかかる時間を測定する[Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="4a343-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="4a343-121">結果として得られるパフォーマンス グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a343-121">The resulting performance graph is shown:</span></span>

![カスタム テレメトリ](./media/custom-telemetry.png)

<span data-ttu-id="4a343-123">カスタムのテレメトリは、新しい行を挿入する平均時間は 32.6 (ミリ秒) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a343-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="4a343-124">Application Insights では、サーバーレス アプリケーションに関する詳細な製品利用統計情報を記録する強力な便利な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="4a343-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="4a343-125">トレースのレベルに対するフル コントロールがあり、ログが提供されます。</span><span class="sxs-lookup"><span data-stu-id="4a343-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="4a343-126">イベント、依存関係、およびページ ビューなどのカスタムの統計を追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="4a343-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="4a343-127">最後に、強力な分析では、重要な質問したり、グラフと高度な洞察を生成するクエリの作成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4a343-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="4a343-128">詳細については、次を参照してください。 [Azure Functions を監視](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)します。</span><span class="sxs-lookup"><span data-stu-id="4a343-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4a343-129">[前へ](azure-functions.md)
>[次へ](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="4a343-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
