---
title: Application Insights - サーバーレス アプリ
description: Application Insights は、開発者が Web アプリ、モバイル アプリ、デスクトップ アプリ、マイクロサービスの問題を検出、トリアージ、診断できるサーバーレス診断プラットフォームです。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7c1013ac029645a2da44aaf1c3b6ba74ca3f3dde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522737"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="a0701-103">Application Insights のテレメトリ</span><span class="sxs-lookup"><span data-stu-id="a0701-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="a0701-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) は、開発者が Web アプリ、モバイル アプリ、デスクトップ アプリ、マイクロサービスの問題を検出、トリアージ、診断できるサーバーレス診断プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="a0701-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="a0701-105">ポータルでスイッチを切り換えるだけで、関数アプリに対して Application Insights を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0701-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="a0701-106">Application Insights を使用すると、サーバーを構成したり、独自のデータベースを設定したりする必要なく、これらの機能すべてが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a0701-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="a0701-107">Application Insights のすべての機能は、アプリと自動的に統合されるサービスとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="a0701-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Application Insights のロゴ](./media/application-insights-logo.png)

<span data-ttu-id="a0701-109">既存のアプリに Application Insights を追加することは、アプリケーションの設定にインストルメンテーション キーを追加するのと同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="a0701-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="a0701-110">Application Insights を使用して次のことができます。</span><span class="sxs-lookup"><span data-stu-id="a0701-110">With Application Insights you can:</span></span>

- <span data-ttu-id="a0701-111">関数呼び出しの回数、関数の実行にかかる時間、例外などのメトリクスに基づいて、カスタム グラフとカスタム アラートを作成する</span><span class="sxs-lookup"><span data-stu-id="a0701-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="a0701-112">エラーとサーバーの例外を分析する</span><span class="sxs-lookup"><span data-stu-id="a0701-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="a0701-113">操作別にパフォーマンスを掘り下げ、サードパーティの依存関係の呼び出しにかかる時間を測定する</span><span class="sxs-lookup"><span data-stu-id="a0701-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="a0701-114">関数アプリをホストするすべてのサーバーの CPU 使用率、メモリ、速度を監視する</span><span class="sxs-lookup"><span data-stu-id="a0701-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="a0701-115">関数アプリの要求数や待機時間といったメトリクスのライブ ストリームを表示する</span><span class="sxs-lookup"><span data-stu-id="a0701-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="a0701-116">[Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) を使用して関数データの検索、クエリ、カスタム グラフの作成を行う</span><span class="sxs-lookup"><span data-stu-id="a0701-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![メトリックス エクスプローラー](./media/metrics-explorer.png)

<span data-ttu-id="a0701-118">組み込みのテレメトリに加えて、カスタム テレメトリを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0701-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="a0701-119">次のコード スニペットは、関数アプリ用に設定したインストルメンテーション キーを使用して、カスタム テレメトリ クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0701-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="a0701-120">次のコードは、[Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) インスタンスに新しい行を挿入するのにかかる時間を測定します。</span><span class="sxs-lookup"><span data-stu-id="a0701-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="a0701-121">結果のパフォーマンス グラフは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a0701-121">The resulting performance graph is shown:</span></span>

![カスタムのテレメトリ](./media/custom-telemetry.png)

<span data-ttu-id="a0701-123">カスタム テレメトリは、新しい行の挿入にかかる平均時間が 32.6 ミリ秒であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a0701-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="a0701-124">Application Insights には、サーバーレス アプリケーションに関する詳細なテレメトリをログに記録するための強力で便利な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="a0701-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="a0701-125">提供されるトレースとログ記録のレベルを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="a0701-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="a0701-126">イベント、依存関係、ページ ビューなどのカスタム統計情報を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="a0701-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="a0701-127">最後に、高機能の分析によって、重要な質問をしてグラフや高度な分析情報を生成するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a0701-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="a0701-128">詳しくは、「[Azure Functions を監視する](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a0701-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a0701-129">[前へ](azure-functions.md)
>[次へ](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a0701-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
