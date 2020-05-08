---
title: サーバーレス アプリのサンプルのビジネス シナリオとユースケース
description: 画像処理からモバイル サポートや ETL パイプラインまで、サンプルへのアクセスによるハンズオン アプローチを使用してサーバーレスについて学習します。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158451"
---
# <a name="serverless-business-scenarios-and-use-cases"></a><span data-ttu-id="f6479-103">サーバーレスのビジネス シナリオとユース ケース</span><span class="sxs-lookup"><span data-stu-id="f6479-103">Serverless business scenarios and use cases</span></span>

<span data-ttu-id="f6479-104">サーバーレス アプリケーションには、多くのユースケースとシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="f6479-104">There are many use cases and scenarios for serverless applications.</span></span> <span data-ttu-id="f6479-105">この章には、さまざまなシナリオを示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6479-105">This chapter includes samples that illustrate the different scenarios.</span></span> <span data-ttu-id="f6479-106">シナリオには、関連するドキュメントおよびパブリック ソース コード リポジトリへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6479-106">The scenarios include links to related documentation and public source code repositories.</span></span> <span data-ttu-id="f6479-107">この章のサンプルを使用して、サーバーレス ソリューションの独自の構築および実装を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="f6479-107">The samples in this chapter enable you to get started on your own building and implementing serverless solutions.</span></span>

## <a name="big-data-processing"></a><span data-ttu-id="f6479-108">ビッグ データの処理</span><span class="sxs-lookup"><span data-stu-id="f6479-108">Big data processing</span></span>

![map/reduce の図](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

<span data-ttu-id="f6479-110">この例では、サーバーレスを使用して、ビッグ データ セットに対して map/reduce 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6479-110">This example uses serverless to do a map/reduce operation on a big data set.</span></span> <span data-ttu-id="f6479-111">ニューヨークのタクシーの 2017 年における 1 日の平均速度を決定します。</span><span class="sxs-lookup"><span data-stu-id="f6479-111">It determines the average speed of New York Yellow taxi trips per day in 2017.</span></span>

[<span data-ttu-id="f6479-112">ビッグ データ処理: Azure でのサーバーレス MapReduce</span><span class="sxs-lookup"><span data-stu-id="f6479-112">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a><span data-ttu-id="f6479-113">サーバーレス アプリケーションを作成する: ハンズオン ラボ</span><span class="sxs-lookup"><span data-stu-id="f6479-113">Create serverless applications: hands-on lab</span></span>

<span data-ttu-id="f6479-114">関数を使用してサーバー側のロジックを実行し、サーバーレス アーキテクチャを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6479-114">Learn how to use functions to execute server-side logic and build serverless architectures.</span></span>

- <span data-ttu-id="f6479-115">ビジネスに最適な Azure サービスの選択</span><span class="sxs-lookup"><span data-stu-id="f6479-115">Choosing the best Azure service for your business</span></span>
- <span data-ttu-id="f6479-116">Azure 関数の作成</span><span class="sxs-lookup"><span data-stu-id="f6479-116">Creating Azure Functions</span></span>
- <span data-ttu-id="f6479-117">トリガーの使用</span><span class="sxs-lookup"><span data-stu-id="f6479-117">Using triggers</span></span>
- <span data-ttu-id="f6479-118">関数のチェーン</span><span class="sxs-lookup"><span data-stu-id="f6479-118">Chaining functions</span></span>
- <span data-ttu-id="f6479-119">実行時間の長いワークフロー</span><span class="sxs-lookup"><span data-stu-id="f6479-119">Long-running workflows</span></span>
- <span data-ttu-id="f6479-120">監視</span><span class="sxs-lookup"><span data-stu-id="f6479-120">Monitoring</span></span>
- <span data-ttu-id="f6479-121">開発、テスト、展開</span><span class="sxs-lookup"><span data-stu-id="f6479-121">Development, testing, and deployment</span></span>

[<span data-ttu-id="f6479-122">サーバーレス アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="f6479-122">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a><span data-ttu-id="f6479-123">顧客レビュー</span><span class="sxs-lookup"><span data-stu-id="f6479-123">Customer reviews</span></span>

<span data-ttu-id="f6479-124">このサンプルでは、Visual Studio の C# クラス ライブラリ用の新しい Azure Functions ツールを紹介します。</span><span class="sxs-lookup"><span data-stu-id="f6479-124">This sample showcases the new Azure Functions tooling for C# Class Libraries in Visual Studio.</span></span> <span data-ttu-id="f6479-125">Azure Storage Blob および CosmosDB に格納される製品レビューを顧客が送信する Web サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6479-125">Create a website where customers submit product reviews that are stored in Azure storage blobs and CosmosDB.</span></span> <span data-ttu-id="f6479-126">Azure Cognitive Services を使用して顧客レビューの自動モデレーションを実行する Azure 関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6479-126">Add an Azure Function to perform automated moderation of the customer reviews using Azure Cognitive Services.</span></span> <span data-ttu-id="f6479-127">Azure ストレージ キューを使用して、Web サイトを関数から分離します。</span><span class="sxs-lookup"><span data-stu-id="f6479-127">Use an Azure storage queue to decouple the website from the function.</span></span>

[<span data-ttu-id="f6479-128">Cognitive Services による顧客レビュー アプリ</span><span class="sxs-lookup"><span data-stu-id="f6479-128">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a><span data-ttu-id="f6479-129">Docker Linux イメージのサポート</span><span class="sxs-lookup"><span data-stu-id="f6479-129">Docker Linux image support</span></span>

<span data-ttu-id="f6479-130">このサンプルでは、Linux Docker コンテナーで Azure 関数をビルドして実行するための `Dockerfile` を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6479-130">This sample demonstrates how to create a `Dockerfile` to build and run Azure Functions on a Linux Docker container.</span></span>

[<span data-ttu-id="f6479-131">Linux 上の Azure 関数</span><span class="sxs-lookup"><span data-stu-id="f6479-131">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a><span data-ttu-id="f6479-132">ファイルの処理と検証</span><span class="sxs-lookup"><span data-stu-id="f6479-132">File processing and validation</span></span>

<span data-ttu-id="f6479-133">この例では、架空の顧客からの一連の CSV ファイルを解析します。</span><span class="sxs-lookup"><span data-stu-id="f6479-133">This example parses a set of CSV files from hypothetical customers.</span></span> <span data-ttu-id="f6479-134">顧客の "バッチ" に必要なすべてのファイルの準備ができていることを確認した後、各ファイルの構造を検証します。</span><span class="sxs-lookup"><span data-stu-id="f6479-134">It ensures that all files required for a customer "batch" are ready, then validates the structure of each file.</span></span> <span data-ttu-id="f6479-135">Azure Functions、Logic Apps、Durable Functions を使用して、異なるソリューションを示します。</span><span class="sxs-lookup"><span data-stu-id="f6479-135">Different solutions are presented using Azure Functions, Logic Apps, and Durable Functions.</span></span>

[<span data-ttu-id="f6479-136">Azure Functions、Logic Apps、Durable Functions を使用した、ファイルの処理と検証</span><span class="sxs-lookup"><span data-stu-id="f6479-136">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a><span data-ttu-id="f6479-137">ゲーム データの視覚化</span><span class="sxs-lookup"><span data-stu-id="f6479-137">Game data visualization</span></span>

![ゲーム テレメトリ](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

<span data-ttu-id="f6479-139">開発者がゲーム用にエディター内データ視覚化ソリューションを実装する方法の例です。</span><span class="sxs-lookup"><span data-stu-id="f6479-139">An example of how a developer could implement an in-editor data visualization solution for their game.</span></span> <span data-ttu-id="f6479-140">実際、Unreal Engine 4 プラグインと Unity プラグインは、このサンプルをバックエンドとして使用して開発されました。</span><span class="sxs-lookup"><span data-stu-id="f6479-140">In fact, an Unreal Engine 4 Plugin and Unity Plugin were developed using this sample as its backend.</span></span> <span data-ttu-id="f6479-141">サービス コンポーネントは、ゲーム エンジンに依存しません。</span><span class="sxs-lookup"><span data-stu-id="f6479-141">The service component is game engine agnostic.</span></span>

[<span data-ttu-id="f6479-142">エディター内でのゲーム テレメトリの視覚化</span><span class="sxs-lookup"><span data-stu-id="f6479-142">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a><span data-ttu-id="f6479-143">GraphQL</span><span class="sxs-lookup"><span data-stu-id="f6479-143">GraphQL</span></span>

<span data-ttu-id="f6479-144">GraphQL API を公開するサーバーレス関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="f6479-144">Create a serverless function that exposes a GraphQL API.</span></span>

[<span data-ttu-id="f6479-145">GraphQL 用のサーバーレス関数</span><span class="sxs-lookup"><span data-stu-id="f6479-145">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a><span data-ttu-id="f6479-146">モノのインターネット (IoT) の高信頼性エッジ リレー</span><span class="sxs-lookup"><span data-stu-id="f6479-146">Internet of Things (IoT) reliable edge relay</span></span>

![IoT アーキテクチャ](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

<span data-ttu-id="f6479-148">このサンプルでは、IoT デバイスからの高信頼性のアップストリーム通信を可能にする新しい通信プロトコルを実装します。</span><span class="sxs-lookup"><span data-stu-id="f6479-148">This sample implements a new communication protocol to enable reliable upstream communication from IoT devices.</span></span> <span data-ttu-id="f6479-149">データ ギャップの検出とバックフィルを自動化します。</span><span class="sxs-lookup"><span data-stu-id="f6479-149">It automates data gap detection and backfill.</span></span>

[<span data-ttu-id="f6479-150">IoT 高信頼性エッジ リレー</span><span class="sxs-lookup"><span data-stu-id="f6479-150">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a><span data-ttu-id="f6479-151">マイクロサービス参照アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f6479-151">Microservices reference architecture</span></span>

![参照アーキテクチャ](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

<span data-ttu-id="f6479-153">Relecloud (架空の会社) による Rideshare アプリケーションの設計、開発、配布に関連する意思決定プロセスの手順を示す参照アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="f6479-153">A reference architecture that walks you through the decision-making process involved in designing, developing, and delivering the Rideshare by Relecloud application (a fictitious company).</span></span> <span data-ttu-id="f6479-154">アーキテクチャのすべてのコンポーネントを構成して展開するための実践的な手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6479-154">It includes hands-on instructions for configuring and deploying all of the architecture's components.</span></span>

[<span data-ttu-id="f6479-155">サーバーレス マイクロサービス参照アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f6479-155">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a><span data-ttu-id="f6479-156">コンソール アプリをサーバーレスに移行する</span><span class="sxs-lookup"><span data-stu-id="f6479-156">Migrate console apps to serverless</span></span>

<span data-ttu-id="f6479-157">このサンプルは、任意のコンソール アプリケーションを Azure Functions の HTTP Web サービスに変換するために使用できる汎用関数 (`.csx` ファイル) です。</span><span class="sxs-lookup"><span data-stu-id="f6479-157">This sample is a generic function (`.csx` file) that can be used to convert any console application to an HTTP web service in Azure Functions.</span></span> <span data-ttu-id="f6479-158">必要な作業は、構成ファイルを編集し、`.exe` に引数として渡す入力パラメーターを指定することだけです。</span><span class="sxs-lookup"><span data-stu-id="f6479-158">All you have to do is edit a configuration file and specify what input parameters will be passed as arguments to the `.exe`.</span></span>

[<span data-ttu-id="f6479-159">Azure Functions でコンソール アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="f6479-159">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a><span data-ttu-id="f6479-160">モバイル用のサーバーレス</span><span class="sxs-lookup"><span data-stu-id="f6479-160">Serverless for mobile</span></span>

<span data-ttu-id="f6479-161">Azure Functions は実装と保守が簡単で、HTTP を介してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f6479-161">Azure Functions are easy to implement and maintain, and accessible through HTTP.</span></span> <span data-ttu-id="f6479-162">モバイル アプリケーション用の API を実装する優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="f6479-162">They are a great way to implement an API for a mobile application.</span></span> <span data-ttu-id="f6479-163">Microsoft では、iOS、Android、Windows 向けの優れたクロスプラットフォーム ツールが Xamarin で提供されています。</span><span class="sxs-lookup"><span data-stu-id="f6479-163">Microsoft offers great cross-platform tools for iOS, Android, and Windows with Xamarin.</span></span> <span data-ttu-id="f6479-164">そのため、Xamarin と Azure Functions は連携して機能します。</span><span class="sxs-lookup"><span data-stu-id="f6479-164">As such, Xamarin and Azure Functions are working great together.</span></span> <span data-ttu-id="f6479-165">この記事では、最初に Azure portal または Visual Studio で Azure 関数を実装してから、Android、iOS、Windows で実行される Xamarin.Forms を使用してクロスプラットフォーム クライアントを構築する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6479-165">This article shows how to implement an Azure Function in the Azure portal or in Visual Studio at first, and build a cross-platform client with Xamarin.Forms running on Android, iOS, and Windows.</span></span>

[<span data-ttu-id="f6479-166">Xamarin.Forms クライアントを使用するシンプルな Azure 関数の実装</span><span class="sxs-lookup"><span data-stu-id="f6479-166">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)

## <a name="serverless-messaging"></a><span data-ttu-id="f6479-167">サーバーレス メッセージング</span><span class="sxs-lookup"><span data-stu-id="f6479-167">Serverless messaging</span></span>

<span data-ttu-id="f6479-168">このサンプルでは、Durable Functions のファンアウト パターンを使用して、任意の数のセッションまたはパーティションから任意の数のメッセージを読み込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6479-168">This sample shows how to utilize Durable Functions' fan-out pattern to load an arbitrary number of messages across any number of sessions/partitions.</span></span> <span data-ttu-id="f6479-169">Service Bus、Event Hubs、またはストレージ キューを対象としています。</span><span class="sxs-lookup"><span data-stu-id="f6479-169">It targets Service Bus, Event Hubs, or Storage Queues.</span></span> <span data-ttu-id="f6479-170">また、このサンプルでは、それらのメッセージを別の Azure 関数で使用し、結果のタイミング データを別のイベント ハブに読み込む機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6479-170">The sample also adds the ability to consume those messages with another Azure Function and load the resulting timing data in to another Event Hub.</span></span> <span data-ttu-id="f6479-171">その後、データは、Azure Data Explorer などの分析サービスに取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="f6479-171">The data is then ingested into analytics services like Azure Data Explorer.</span></span>

[<span data-ttu-id="f6479-172">Service Bus、Event Hubs、ストレージ キューと Azure Functions によりメッセージを生成して使用する</span><span class="sxs-lookup"><span data-stu-id="f6479-172">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a><span data-ttu-id="f6479-173">推奨リソース</span><span class="sxs-lookup"><span data-stu-id="f6479-173">Recommended resources</span></span>

- [<span data-ttu-id="f6479-174">Linux 上の Azure 関数</span><span class="sxs-lookup"><span data-stu-id="f6479-174">Azure Functions on Linux</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [<span data-ttu-id="f6479-175">ビッグ データ処理: Azure でのサーバーレス MapReduce</span><span class="sxs-lookup"><span data-stu-id="f6479-175">Big Data Processing: Serverless MapReduce on Azure</span></span>](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [<span data-ttu-id="f6479-176">サーバーレス アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="f6479-176">Create serverless applications</span></span>](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [<span data-ttu-id="f6479-177">Cognitive Services による顧客レビュー アプリ</span><span class="sxs-lookup"><span data-stu-id="f6479-177">Customer Reviews App with Cognitive Services</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [<span data-ttu-id="f6479-178">Azure Functions、Logic Apps、Durable Functions を使用した、ファイルの処理と検証</span><span class="sxs-lookup"><span data-stu-id="f6479-178">File processing and validation using Azure Functions, Logic Apps, and Durable Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [<span data-ttu-id="f6479-179">Xamarin.Forms クライアントを使用するシンプルな Azure 関数の実装</span><span class="sxs-lookup"><span data-stu-id="f6479-179">Implementing a simple Azure Function with a Xamarin.Forms client</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [<span data-ttu-id="f6479-180">エディター内でのゲーム テレメトリの視覚化</span><span class="sxs-lookup"><span data-stu-id="f6479-180">In-editor game telemetry visualization</span></span>](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [<span data-ttu-id="f6479-181">IoT 高信頼性エッジ リレー</span><span class="sxs-lookup"><span data-stu-id="f6479-181">IoT Reliable Edge Relay</span></span>](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [<span data-ttu-id="f6479-182">Service Bus、Event Hubs、ストレージ キューと Azure Functions によりメッセージを生成して使用する</span><span class="sxs-lookup"><span data-stu-id="f6479-182">Produce and Consume messages through Service Bus, Event Hubs, and Storage Queues with Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [<span data-ttu-id="f6479-183">Azure Functions でコンソール アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="f6479-183">Run Console Apps on Azure Functions</span></span>](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [<span data-ttu-id="f6479-184">GraphQL 用のサーバーレス関数</span><span class="sxs-lookup"><span data-stu-id="f6479-184">Serverless functions for GraphQL</span></span>](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [<span data-ttu-id="f6479-185">サーバーレス マイクロサービス参照アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f6479-185">Serverless Microservices reference architecture</span></span>](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
><span data-ttu-id="f6479-186">[前へ](orchestration-patterns.md)
>[次へ](serverless-conclusion.md)</span><span class="sxs-lookup"><span data-stu-id="f6479-186">[Previous](orchestration-patterns.md)
[Next](serverless-conclusion.md)</span></span>
