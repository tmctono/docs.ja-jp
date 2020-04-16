---
title: NET 用 Azure SDK でのログ記録
description: Azure SDK for .NET クライアント ライブラリでログ記録を有効にする方法を確認する
ms.date: 03/20/2020
ms.custom: azure-sdk-dotnet
ms.author: casoper
author: camsoper
ms.openlocfilehash: b277045a60ef5cc065d77dad84878872dedc963e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433224"
---
# <a name="logging-with-the-azure-sdk-for-net"></a><span data-ttu-id="85496-103">NET 用 Azure SDK でのログ記録</span><span class="sxs-lookup"><span data-stu-id="85496-103">Logging with the Azure SDK for .NET</span></span>

<span data-ttu-id="85496-104">[Azure SDK](https://azure.microsoft.com/downloads/) for .NET クライアント ライブラリには、クライアント ライブラリ操作をログに記録する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85496-104">The [Azure SDK](https://azure.microsoft.com/downloads/) for .NET client libraries includes the ability to log client library operations.</span></span> <span data-ttu-id="85496-105">これにより、クライアント ライブラリが Azure サービスに対して行っている I/O 要求と応答を監視できます。</span><span class="sxs-lookup"><span data-stu-id="85496-105">This allows you to monitor I/O requests and responses that client libraries are making to Azure services.</span></span> <span data-ttu-id="85496-106">通常、ログは、通信の問題をデバッグまたは診断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="85496-106">Typically, the logs are used to debug or diagnose communication issues.</span></span> <span data-ttu-id="85496-107">この記事では、Azure SDK for .NET でログを記録するための 3 つの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85496-107">This article describes three approaches to enable logging with the Azure SDK for .NET:</span></span>

- <span data-ttu-id="85496-108">コンソール ウィンドウにログを記録する</span><span class="sxs-lookup"><span data-stu-id="85496-108">Log to the console window</span></span>
- <span data-ttu-id="85496-109">NET 診断トレースにログを記録する</span><span class="sxs-lookup"><span data-stu-id="85496-109">Log to .NET diagnostics traces</span></span>
- <span data-ttu-id="85496-110">カスタム ログの構成</span><span class="sxs-lookup"><span data-stu-id="85496-110">Configure custom logging</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85496-111">この記事は、最新バージョンの Azure SDK for .NET を使用するクライアント ライブラリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="85496-111">This article applies to client libraries that use the most recent versions of the Azure SDK for .NET.</span></span> <span data-ttu-id="85496-112">ライブラリがサポートされているかどうかを確認するには[、Azure SDK の最新リリース](https://azure.github.io/azure-sdk/releases/latest/index.html)の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85496-112">To see if a library is supported, refer to the list of [Azure SDK latest releases](https://azure.github.io/azure-sdk/releases/latest/index.html).</span></span> <span data-ttu-id="85496-113">アプリケーションで古いバージョンの Azure SDK クライアント ライブラリを使用している場合は、該当するサービス のドキュメントの特定の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85496-113">If your application is using an older version of the Azure SDK client libraries, refer to specific instructions in the applicable service documentation.</span></span>

## <a name="log-information"></a><span data-ttu-id="85496-114">ログ情報</span><span class="sxs-lookup"><span data-stu-id="85496-114">Log information</span></span>

<span data-ttu-id="85496-115">SDK は、次の情報をログに記録し、パラメーター クエリとヘッダー値をサニタイズして個人データを削除します。</span><span class="sxs-lookup"><span data-stu-id="85496-115">The SDK logs the following information, sanitizing parameter query and header values to remove personal data.</span></span>

<span data-ttu-id="85496-116">HTTP 要求ログエントリ:</span><span class="sxs-lookup"><span data-stu-id="85496-116">HTTP request log entry:</span></span>

- <span data-ttu-id="85496-117">固有の ID</span><span class="sxs-lookup"><span data-stu-id="85496-117">Unique ID</span></span>
- <span data-ttu-id="85496-118">HTTP メソッド</span><span class="sxs-lookup"><span data-stu-id="85496-118">HTTP method</span></span>
- <span data-ttu-id="85496-119">URI</span><span class="sxs-lookup"><span data-stu-id="85496-119">URI</span></span>
- <span data-ttu-id="85496-120">送信要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="85496-120">Outgoing request headers</span></span>

<span data-ttu-id="85496-121">HTTP 応答ログ エントリ:</span><span class="sxs-lookup"><span data-stu-id="85496-121">HTTP response log entry:</span></span>

- <span data-ttu-id="85496-122">I/O操作の継続時間(経過時間)</span><span class="sxs-lookup"><span data-stu-id="85496-122">Duration of I/O operation (time elapsed)</span></span>
- <span data-ttu-id="85496-123">要求 ID</span><span class="sxs-lookup"><span data-stu-id="85496-123">Request ID</span></span>
- <span data-ttu-id="85496-124">HTTP 状態コード</span><span class="sxs-lookup"><span data-stu-id="85496-124">HTTP status code</span></span>
- <span data-ttu-id="85496-125">HTTP 理由句</span><span class="sxs-lookup"><span data-stu-id="85496-125">HTTP reason phrase</span></span>
- <span data-ttu-id="85496-126">応答ヘッダー</span><span class="sxs-lookup"><span data-stu-id="85496-126">Response headers</span></span>
- <span data-ttu-id="85496-127">エラー情報 (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="85496-127">Error information, when applicable</span></span>

<span data-ttu-id="85496-128">要求および応答のコンテンツの場合:</span><span class="sxs-lookup"><span data-stu-id="85496-128">For request and response content:</span></span>

- <span data-ttu-id="85496-129">コンテンツ・ストリームは、コンテンツ・タイプ・ヘッダーに応じてテキストまたはバイトとしてストリームされます。</span><span class="sxs-lookup"><span data-stu-id="85496-129">Content stream as text or bytes depending on the Content-Type header.</span></span>
     > <span data-ttu-id="85496-130">[!NOTE} コンテンツ ログは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="85496-130">[!NOTE} Content logging is disabled by default.</span></span> <span data-ttu-id="85496-131">有効にするには、`Diagnostics.IsLoggingContentEnabled``true`に`ClientOptions`設定します。</span><span class="sxs-lookup"><span data-stu-id="85496-131">To enable it, set `Diagnostics.IsLoggingContentEnabled` to `true` in `ClientOptions`.</span></span>

<span data-ttu-id="85496-132">イベント ログは、通常、次の 3 つのレベルのいずれかで出力されます。</span><span class="sxs-lookup"><span data-stu-id="85496-132">Event logs are output usually at one of these three levels:</span></span>

- <span data-ttu-id="85496-133">要求イベントおよび応答イベントの情報提供</span><span class="sxs-lookup"><span data-stu-id="85496-133">Informational for request and response events</span></span>
- <span data-ttu-id="85496-134">エラーの警告</span><span class="sxs-lookup"><span data-stu-id="85496-134">Warning for errors</span></span>
- <span data-ttu-id="85496-135">詳細メッセージとコンテンツ ログの詳細</span><span class="sxs-lookup"><span data-stu-id="85496-135">Verbose for detailed messages and content logging</span></span>

## <a name="enable-logging-with-built-in-methods"></a><span data-ttu-id="85496-136">組み込みメソッドでログを有効にする</span><span class="sxs-lookup"><span data-stu-id="85496-136">Enable logging with built-in methods</span></span>

<span data-ttu-id="85496-137">Azure SDK for .NET クライアント ライブラリは[`EventSource`、.NET](/dotnet/api/system.diagnostics.tracing.eventsource)の一般的なクラスを介してイベント トレース (ETW) にイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="85496-137">The Azure SDK for .NET client libraries log events to Event Tracing for Windows (ETW) via the [`EventSource` class](/dotnet/api/system.diagnostics.tracing.eventsource), which is typical for .NET.</span></span> <span data-ttu-id="85496-138">イベント ソースを使用すると、アプリケーション コードで構造化ログを使用し、パフォーマンスのオーバーヘッドを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="85496-138">Event sources allow you to use structured logging in your application code with a minimal performance overhead.</span></span> <span data-ttu-id="85496-139">これらのイベント ログにアクセスするには、イベント リスナーを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85496-139">To gain access to these event logs, you need to register event listeners.</span></span>

<span data-ttu-id="85496-140">SDK にはクラス`Azure.Core.Diagnostics.AzureEventSourceListener`(Azure.Core NuGet パッケージで定義) が含まれており、.NET アプリケーションの包括的なログ記録`CreateConsoleLogger`を`CreateTraceLogger`簡素化する 2 つの静的メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85496-140">The SDK includes the `Azure.Core.Diagnostics.AzureEventSourceListener` class (defined in the Azure.Core NuGet package), which contains two static methods that simplify comprehensive logging for your .NET application: `CreateConsoleLogger` and `CreateTraceLogger`.</span></span> <span data-ttu-id="85496-141">これらのメソッドは、ログ レベルを指定する省略可能なパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="85496-141">These methods take an optional parameter that specifies a log level.</span></span>

### <a name="log-to-the-console-window"></a><span data-ttu-id="85496-142">コンソール ウィンドウにログを記録する</span><span class="sxs-lookup"><span data-stu-id="85496-142">Log to the console window</span></span>

<span data-ttu-id="85496-143">Azure SDK for .NET クライアント ライブラリの主要な原則は、包括的なログをリアルタイムで表示する機能を簡略化することです。</span><span class="sxs-lookup"><span data-stu-id="85496-143">A core tenet of the Azure SDK for .NET client libraries is to simplify the ability to view comprehensive logs in real time.</span></span> <span data-ttu-id="85496-144">この`CreateConsoleLogger`メソッドを使用すると、1 行のコードでログをコンソール ウィンドウに送信できます。</span><span class="sxs-lookup"><span data-stu-id="85496-144">The `CreateConsoleLogger` method allows you to send logs to the console window with a single line of code:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateConsoleLogger();
```

### <a name="log-to-diagnostic-traces"></a><span data-ttu-id="85496-145">診断トレースにログを記録する</span><span class="sxs-lookup"><span data-stu-id="85496-145">Log to diagnostic traces</span></span>

<span data-ttu-id="85496-146">トレース リスナーを実装する場合は、このメソッド`CreateTraceLogger`を使用して、標準の .NET イベント[`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)トレース メカニズム ( ) にログを記録できます。</span><span class="sxs-lookup"><span data-stu-id="85496-146">If you implement trace listeners, you can use the `CreateTraceLogger` method to log to the standard .NET event tracing mechanism ([`System.Diagnostics.Tracing`](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing)).</span></span> <span data-ttu-id="85496-147">NET でのイベント トレースの詳細については、「[トレース リスナー](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85496-147">For more information on event tracing in .NET, see [Trace Listeners](https://docs.microsoft.com/dotnet/framework/debug-trace-profile/trace-listeners).</span></span> <span data-ttu-id="85496-148">この例では、詳細のログ レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="85496-148">This example specifies a log level of verbose:</span></span>

```csharp
using AzureEventSourceListener listener = AzureEventSourceListener.CreateTraceLogger(EventLevel.Verbose);
```

## <a name="configure-custom-logging"></a><span data-ttu-id="85496-149">カスタム ログの構成</span><span class="sxs-lookup"><span data-stu-id="85496-149">Configure custom logging</span></span>

<span data-ttu-id="85496-150">前述したように、.NET 用 Azure SDK からログ メッセージを受信するイベント リスナーを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85496-150">As mentioned above, you need to register event listeners to receive log messages from the Azure SDK for .NET.</span></span> <span data-ttu-id="85496-151">上記の単純化されたメソッドを使用して包括的なログを実装しない場合は、`AzureEventSourceListener`クラスのインスタンスを構築し、記述したコールバック関数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="85496-151">If you don’t want to implement comprehensive logging using one the simplified methods above, you can construct an instance of the `AzureEventSourceListener` class and pass it a callback function that you write.</span></span> <span data-ttu-id="85496-152">このメソッドは、必要に応じて処理できるログ メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="85496-152">This method will receive log messages that you can process however you need to.</span></span> <span data-ttu-id="85496-153">また、インスタンスを構築するときに、含めるログレベルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="85496-153">In addition, when you construct the instance, you can specify the log levels to include.</span></span>

<span data-ttu-id="85496-154">次の例では、カスタム メッセージを使用してコンソールにログを記録し、詳細レベルの Azure コア イベントにフィルター処理されるイベント リスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="85496-154">The following example creates an event listener that logs to the console with a custom message, and is filtered to Azure core events of the level verbose.</span></span>

```csharp
using AzureEventSourceListener listener = new AzureEventSourceListener((e, message) =>
    {
        // Only log messages from Azure-Core event source
        if (e.EventSource.Name == "Azure-Core")
        {
            Console.WriteLine($"{DateTime.Now} {message}");
        }
    },
    level: EventLevel.Verbose);
```

## <a name="next-steps"></a><span data-ttu-id="85496-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="85496-155">Next steps</span></span>

- [<span data-ttu-id="85496-156">Azure App Service でのアプリの診断ログの有効化</span><span class="sxs-lookup"><span data-stu-id="85496-156">Enable diagnostics logging for apps in Azure App Service</span></span>](https://docs.microsoft.com/azure/app-service/troubleshoot-diagnostic-logs)
- <span data-ttu-id="85496-157">[Azure のセキュリティ ログと監査](https://docs.microsoft.com/azure/security/fundamentals/log-audit)のオプションを確認する</span><span class="sxs-lookup"><span data-stu-id="85496-157">Review [Azure security logging and auditing](https://docs.microsoft.com/azure/security/fundamentals/log-audit) options</span></span>
- <span data-ttu-id="85496-158">[Azure プラットフォーム ログ](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)の操作方法の詳細</span><span class="sxs-lookup"><span data-stu-id="85496-158">Learn how to work with [Azure platform logs](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview)</span></span>
- <span data-ttu-id="85496-159">[NET Core のログとトレース](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85496-159">Read more about [.NET Core logging and tracing](https://docs.microsoft.com/dotnet/core/diagnostics/logging-tracing)</span></span>
