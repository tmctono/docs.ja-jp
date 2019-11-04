---
title: Apache Spark とは
description: Apache Spark とビッグ データ シナリオについて説明します。
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458169"
---
# <a name="what-is-apache-spark"></a><span data-ttu-id="1cb21-103">Apache Spark とは</span><span class="sxs-lookup"><span data-stu-id="1cb21-103">What is Apache Spark?</span></span>

<span data-ttu-id="1cb21-104">[Apache Spark](https://spark.apache.org/) は、ビッグ データを分析するアプリケーションのパフォーマンスを向上させるよう、メモリ内処理をサポートするオープンソースの並列処理フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="1cb21-104">[Apache Spark](https://spark.apache.org/) is an open-source parallel processing framework that supports in-memory processing to boost the performance of applications that analyze big data.</span></span> <span data-ttu-id="1cb21-105">ビッグ データ ソリューションは、従来のデータベースでは大きすぎるか、複雑すぎるデータを処理するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1cb21-105">Big data solutions are designed to handle data that is too large or complex for traditional databases.</span></span> <span data-ttu-id="1cb21-106">Spark では、ディスクベースの代替手法よりもかなり速く、メモリ内の大量のデータが処理されます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-106">Spark processes large amounts of data in memory, which is much faster than disk-based alternatives.</span></span>

## <a name="common-big-data-scenarios"></a><span data-ttu-id="1cb21-107">一般的なビッグ データ シナリオ</span><span class="sxs-lookup"><span data-stu-id="1cb21-107">Common big data scenarios</span></span>

<span data-ttu-id="1cb21-108">大量のデータを格納して処理するか、非構造化データを変換するか、あるいはストリーミング データを処理する必要がある場合、ビッグ データ アーキテクチャをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1cb21-108">You might consider a big data architecture if you need to store and process large volumes of data, transform unstructured data, or processes streaming data.</span></span> <span data-ttu-id="1cb21-109">Spark は汎用の分散処理エンジンであり、いくつかのビッグデータ シナリオで利用できます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-109">Spark is a general-purpose distributed processing engine that can be used for several big data scenarios.</span></span>

### <a name="extract-transform-and-load-etl"></a><span data-ttu-id="1cb21-110">抽出、変換、読み込み (ETL)</span><span class="sxs-lookup"><span data-stu-id="1cb21-110">Extract, transform, and load (ETL)</span></span>

<span data-ttu-id="1cb21-111">[抽出、変換、読み込み (ETL)](/azure/architecture/data-guide/relational-data/etl) は、1 つまたは複数のソースからデータを収集し、データを変更し、データを新しいデータ ストアに移動するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1cb21-111">[Extract, transform, and load (ETL)](/azure/architecture/data-guide/relational-data/etl) is the process of collecting data from one or multiple sources, modifying the data, and moving the data to a new data store.</span></span> <span data-ttu-id="1cb21-112">データの変換にはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1cb21-112">There are several ways to transform data, including:</span></span>

* <span data-ttu-id="1cb21-113">フィルター処理</span><span class="sxs-lookup"><span data-stu-id="1cb21-113">Filtering</span></span>
* <span data-ttu-id="1cb21-114">並べ替え</span><span class="sxs-lookup"><span data-stu-id="1cb21-114">Sorting</span></span>
* <span data-ttu-id="1cb21-115">集計</span><span class="sxs-lookup"><span data-stu-id="1cb21-115">Aggregating</span></span>
* <span data-ttu-id="1cb21-116">結合</span><span class="sxs-lookup"><span data-stu-id="1cb21-116">Joining</span></span>
* <span data-ttu-id="1cb21-117">消去</span><span class="sxs-lookup"><span data-stu-id="1cb21-117">Cleaning</span></span>
* <span data-ttu-id="1cb21-118">重複除去</span><span class="sxs-lookup"><span data-stu-id="1cb21-118">Deduplicating</span></span>
* <span data-ttu-id="1cb21-119">Validating</span><span class="sxs-lookup"><span data-stu-id="1cb21-119">Validating</span></span>

### <a name="real-time-data-stream-processing"></a><span data-ttu-id="1cb21-120">リアルタイムのデータ ストリーム処理</span><span class="sxs-lookup"><span data-stu-id="1cb21-120">Real-time data stream processing</span></span>

<span data-ttu-id="1cb21-121">ストリーミング (あるいはリアルタイム) データは移動中のデータです。</span><span class="sxs-lookup"><span data-stu-id="1cb21-121">Streaming, or real-time, data is data in motion.</span></span> <span data-ttu-id="1cb21-122">IoT デバイス、ウェブログ、クリックストリームからのテレメトリはすべて、ストリーミング データの例です。</span><span class="sxs-lookup"><span data-stu-id="1cb21-122">Telemetry from IoT devices, weblogs, and clickstreams are all examples of streaming data.</span></span> <span data-ttu-id="1cb21-123">リアルタイム データを処理し、地理空間分析、リモート監視、異常検出など、有益な情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-123">Real-time data can be processed to provide useful information, such as geospatial analysis, remote monitoring, and anomaly detection.</span></span> <span data-ttu-id="1cb21-124">リレーショナル データと同じように、データを出力シンクに移動する前に、フィルター処理したり、集計したり、ストリーミング データの準備をしたりできます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-124">Just like relational data, you can filter, aggregate, and prepare streaming data before moving the data to an output sink.</span></span> <span data-ttu-id="1cb21-125">Apache Spark では、[Spark Streaming](https://spark.apache.org/streaming/) による[リアルタイムのデータ ストリーム処理](/azure/architecture/data-guide/big-data/real-time-processing)がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1cb21-125">Apache Spark supports [real-time data stream processing](/azure/architecture/data-guide/big-data/real-time-processing) through [Spark Streaming](https://spark.apache.org/streaming/).</span></span>

### <a name="batch-processing"></a><span data-ttu-id="1cb21-126">バッチ処理</span><span class="sxs-lookup"><span data-stu-id="1cb21-126">Batch processing</span></span>

<span data-ttu-id="1cb21-127">[バッチ処理](/azure/architecture/data-guide/big-data/batch-processing)は、保存されているビッグ データの処理です。</span><span class="sxs-lookup"><span data-stu-id="1cb21-127">[Batch processing](/azure/architecture/data-guide/big-data/batch-processing) is the processing of big data at rest.</span></span> <span data-ttu-id="1cb21-128">ジョブを並列で長時間実行し、非常に大きなデータセットをフィルター処理、集計、準備できます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-128">You can filter, aggregate, and prepare very large datasets using long-running jobs in parallel.</span></span>

### <a name="machine-learning-through-mllib"></a><span data-ttu-id="1cb21-129">MLlib による機械学習</span><span class="sxs-lookup"><span data-stu-id="1cb21-129">Machine learning through MLlib</span></span>

<span data-ttu-id="1cb21-130">機械学習は高度な分析問題に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-130">Machine learning is used for advanced analytical problems.</span></span> <span data-ttu-id="1cb21-131">お使いのコンピューターで既存のデータを利用し、将来の行動、成果、傾向を予測できます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-131">Your computer can use existing data to forecast or predict future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="1cb21-132">Apache Spark の機械学習ライブラリである [MLlib](https://spark.apache.org/mllib/) には、機械学習のアルゴリズムとユーティリティがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="1cb21-132">Apache Spark's machine learning library, [MLlib](https://spark.apache.org/mllib/), contains several machine learning algorithms and utilities.</span></span>

### <a name="graph-processing-through-graphx"></a><span data-ttu-id="1cb21-133">GraphX によるグラフ処理</span><span class="sxs-lookup"><span data-stu-id="1cb21-133">Graph processing through GraphX</span></span>

<span data-ttu-id="1cb21-134">グラフは、エッジによって接続されたノードの集まりです。</span><span class="sxs-lookup"><span data-stu-id="1cb21-134">A graph is a collection of nodes connected by edges.</span></span> <span data-ttu-id="1cb21-135">階層式のデータや関係が相互に連結されているデータがある場合、グラフ データベースの利用が便利です。</span><span class="sxs-lookup"><span data-stu-id="1cb21-135">You might use a graph database if you have hierarchial data or data with interconnected relationships.</span></span> <span data-ttu-id="1cb21-136">Apache Spark の [GraphX](https://spark.apache.org/graphx/) API を利用し、このデータを処理できます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-136">You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span></span>

### <a name="sql-and-structured-data-processing-with-spark-sql"></a><span data-ttu-id="1cb21-137">Spark SQL による SQL と構造化データの処理</span><span class="sxs-lookup"><span data-stu-id="1cb21-137">SQL and structured data processing with Spark SQL</span></span>

<span data-ttu-id="1cb21-138">構造化 (書式設定された) データを扱っている場合、[Spark SQL](https://spark.apache.org/sql/) を利用し、Spark アプリケーションで SQL クエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-138">If you're working with structured (formatted) data, you can use SQL queries in your Spark application using [Spark SQL](https://spark.apache.org/sql/).</span></span>

## <a name="apache-spark-architecture"></a><span data-ttu-id="1cb21-139">Apache Spark アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1cb21-139">Apache Spark architecture</span></span>

<span data-ttu-id="1cb21-140">Apache Spark では、マスター/ワーカー アーキテクチャが利用され、ドライバー、エグゼキュータ、クラスター マネージャーという 3 つの主要コンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="1cb21-140">Apache Spark, which uses the master/worker architecture, has three main components: the driver, executors, and cluster manager.</span></span>

![Apache Spark アーキテクチャ](media/spark-architecture.png)

### <a name="driver"></a><span data-ttu-id="1cb21-142">ドライバー</span><span class="sxs-lookup"><span data-stu-id="1cb21-142">Driver</span></span>

<span data-ttu-id="1cb21-143">このドライバーは、C# コンソール アプリのようなプログラムと Spark セッションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="1cb21-143">The driver consists of your program, like a C# console app, and a Spark session.</span></span> <span data-ttu-id="1cb21-144">Spark セッションはプログラムを受け取り、それを小さなタスクに分割します。小さくなったタスクはエグゼキュータで処理されます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-144">The Spark session takes your program and divides it into smaller tasks that are handled by the executors.</span></span>

### <a name="executors"></a><span data-ttu-id="1cb21-145">エグゼキュータ</span><span class="sxs-lookup"><span data-stu-id="1cb21-145">Executors</span></span>

<span data-ttu-id="1cb21-146">各エグゼキュータまたはワーカー ノードはドライバーからタスクを受け取り、そのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="1cb21-146">Each executor, or worker node, receives a task from the driver and executes that task.</span></span> <span data-ttu-id="1cb21-147">エグゼキュータは、クラスターと呼ばれるエンティティ上に存在します。</span><span class="sxs-lookup"><span data-stu-id="1cb21-147">The executors reside on an entity known as a cluster.</span></span>

### <a name="cluster-manager"></a><span data-ttu-id="1cb21-148">クラスター マネージャー</span><span class="sxs-lookup"><span data-stu-id="1cb21-148">Cluster manager</span></span>

<span data-ttu-id="1cb21-149">クラスター マネージャーは、次の目的でドライバーとエグゼキュータの両方と通信します。</span><span class="sxs-lookup"><span data-stu-id="1cb21-149">The cluster manager communicates with both the driver and the executors to:</span></span>

* <span data-ttu-id="1cb21-150">リソースの割り当てを管理する</span><span class="sxs-lookup"><span data-stu-id="1cb21-150">Manage resource allocation</span></span>
* <span data-ttu-id="1cb21-151">プログラム分割を管理する</span><span class="sxs-lookup"><span data-stu-id="1cb21-151">Manage program division</span></span>
* <span data-ttu-id="1cb21-152">プログラム実行を管理する</span><span class="sxs-lookup"><span data-stu-id="1cb21-152">Manage program execution</span></span>

## <a name="language-support"></a><span data-ttu-id="1cb21-153">言語サポート</span><span class="sxs-lookup"><span data-stu-id="1cb21-153">Language support</span></span>

<span data-ttu-id="1cb21-154">Apache Spark では、次のプログラミング言語がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1cb21-154">Apache Spark supports the following programming languages:</span></span>

* <span data-ttu-id="1cb21-155">Scala</span><span class="sxs-lookup"><span data-stu-id="1cb21-155">Scala</span></span>
* <span data-ttu-id="1cb21-156">Python</span><span class="sxs-lookup"><span data-stu-id="1cb21-156">Python</span></span>
* <span data-ttu-id="1cb21-157">Java</span><span class="sxs-lookup"><span data-stu-id="1cb21-157">Java</span></span>
* <span data-ttu-id="1cb21-158">SQL</span><span class="sxs-lookup"><span data-stu-id="1cb21-158">SQL</span></span>
* <span data-ttu-id="1cb21-159">R</span><span class="sxs-lookup"><span data-stu-id="1cb21-159">R</span></span>
* <span data-ttu-id="1cb21-160">.NET</span><span class="sxs-lookup"><span data-stu-id="1cb21-160">.NET</span></span>

## <a name="spark-apis"></a><span data-ttu-id="1cb21-161">Spark API</span><span class="sxs-lookup"><span data-stu-id="1cb21-161">Spark APIs</span></span>

<span data-ttu-id="1cb21-162">Apache Spark では次の API がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1cb21-162">Apache Spark supports the following APIs:</span></span>

* [<span data-ttu-id="1cb21-163">Spark Scala API</span><span class="sxs-lookup"><span data-stu-id="1cb21-163">Spark Scala API</span></span>](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [<span data-ttu-id="1cb21-164">Spark Java API</span><span class="sxs-lookup"><span data-stu-id="1cb21-164">Spark Java API</span></span>](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [<span data-ttu-id="1cb21-165">Spark Python API</span><span class="sxs-lookup"><span data-stu-id="1cb21-165">Spark Python API</span></span>](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [<span data-ttu-id="1cb21-166">Spark R API</span><span class="sxs-lookup"><span data-stu-id="1cb21-166">Spark R API</span></span>](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* <span data-ttu-id="1cb21-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html)、組み込み関数</span><span class="sxs-lookup"><span data-stu-id="1cb21-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), built-in functions</span></span>

## <a name="next-steps"></a><span data-ttu-id="1cb21-168">次の手順</span><span class="sxs-lookup"><span data-stu-id="1cb21-168">Next steps</span></span>

<span data-ttu-id="1cb21-169">自分の .NET アプリケーションで Apache Spark を使用する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="1cb21-169">Learn how you can use Apache Spark in your .NET application.</span></span> <span data-ttu-id="1cb21-170">.NET の経験がある開発者は、ビジネス ロジックが与えられたとき、.NET for Apache Spark を利用し、C# と F# でビッグ データ クエリを記述できます。</span><span class="sxs-lookup"><span data-stu-id="1cb21-170">With .NET for Apache Spark, developers with .NET experience and business logic can write big data queries in C# and F#.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="1cb21-171">.NET for Apache Spark とは</span><span class="sxs-lookup"><span data-stu-id="1cb21-171">What is .NET for Apache Spark</span></span>](what-is-apache-spark-dotnet.md)
