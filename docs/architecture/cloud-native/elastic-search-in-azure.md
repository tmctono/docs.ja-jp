---
title: クラウドネイティブアプリケーションの Elasticsearch
description: クラウドネイティブアプリケーションにエラスティック検索機能を追加する方法について説明します。
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: e956f28877d88ce5279944964a877efc324918b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614085"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="2b132-103">クラウドネイティブアプリでの Elasticsearch</span><span class="sxs-lookup"><span data-stu-id="2b132-103">Elasticsearch in a cloud-native app</span></span>

<span data-ttu-id="2b132-104">Elasticsearch は、さまざまな種類のデータに対して複雑な検索機能を有効にする分散検索および分析システムです。</span><span class="sxs-lookup"><span data-stu-id="2b132-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="2b132-105">オープンソースで広く普及しています。</span><span class="sxs-lookup"><span data-stu-id="2b132-105">It's open source and widely popular.</span></span> <span data-ttu-id="2b132-106">次の企業が Elasticsearch をアプリケーションに統合する方法を検討します。</span><span class="sxs-lookup"><span data-stu-id="2b132-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="2b132-107">フルテキストとインクリメンタル (入力時の検索) の[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) 。</span><span class="sxs-lookup"><span data-stu-id="2b132-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="2b132-108">800万コードリポジトリにインデックスを作成して公開する[GitHub](https://www.elastic.co/customers/github) 。</span><span class="sxs-lookup"><span data-stu-id="2b132-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="2b132-109">コンテナーライブラリを検出できるようにするための[Docker](https://www.elastic.co/customers/docker) 。</span><span class="sxs-lookup"><span data-stu-id="2b132-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="2b132-110">Elasticsearch は、 [Apache Lucene](https://lucene.apache.org/core/)フルテキスト検索エンジンの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="2b132-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="2b132-111">Lucene は、高パフォーマンスのドキュメントのインデックス作成とクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b132-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="2b132-112">逆インデックススキームを使用してデータのインデックスを作成します。ページをキーワードにマップするのではなく、ブックの最後にある用語集と同じように、キーワードをページにマップします。</span><span class="sxs-lookup"><span data-stu-id="2b132-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="2b132-113">Lucene には強力なクエリ構文機能があり、次の方法でデータを照会できます。</span><span class="sxs-lookup"><span data-stu-id="2b132-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="2b132-114">用語 (完全な単語)</span><span class="sxs-lookup"><span data-stu-id="2b132-114">Term (a full word)</span></span>
- <span data-ttu-id="2b132-115">プレフィックス (先頭は word)</span><span class="sxs-lookup"><span data-stu-id="2b132-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="2b132-116">ワイルドカード (" \* " フィルターまたは "?" フィルターを使用)</span><span class="sxs-lookup"><span data-stu-id="2b132-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="2b132-117">フレーズ (ドキュメント内のテキストのシーケンス)</span><span class="sxs-lookup"><span data-stu-id="2b132-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="2b132-118">ブール値 (複合検索クエリの結合)</span><span class="sxs-lookup"><span data-stu-id="2b132-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="2b132-119">Lucene では検索のための低レベルのプラミングが提供されますが、Elasticsearch は Lucene の上にあるサーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="2b132-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="2b132-120">Elasticsearch は、Lucene のインデックス作成と検索機能にアクセスする RESTful API など、操作を簡略化するために、より高度な機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="2b132-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="2b132-121">また、大規模なスケーラビリティ、フォールトトレランス、高可用性を備えた分散インフラストラクチャも提供します。</span><span class="sxs-lookup"><span data-stu-id="2b132-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="2b132-122">複雑な検索要件を持つ大規模なクラウドネイティブアプリケーションの場合、Elasticsearch は Azure の管理されたサービスとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="2b132-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="2b132-123">Microsoft Azure Marketplace には、Azure で Elasticsearch クラスターをデプロイするために開発者が使用できる事前構成済みのテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2b132-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="2b132-124">Microsoft Azure Marketplace から、開発者は、Azure で Elasticsearch クラスターをすばやくデプロイするために構築された構成済みテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b132-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="2b132-125">Azure で管理されたサービスを使用すると、最大50のデータノード、20個の調整ノード、3つの専用マスターノードをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="2b132-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="2b132-126">要約</span><span class="sxs-lookup"><span data-stu-id="2b132-126">Summary</span></span>

<span data-ttu-id="2b132-127">この章では、クラウドネイティブシステムのデータについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2b132-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="2b132-128">クラウドネイティブシステムのデータストレージパターンを使用してモノリシックアプリケーションのデータストレージを比較することから始めました。</span><span class="sxs-lookup"><span data-stu-id="2b132-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="2b132-129">クラウドネイティブシステムに実装されているデータパターンを見てきました。これには、クロスサービスクエリ、分散トランザクション、および大量システムを扱うためのパターンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b132-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="2b132-130">NoSQL データを使用して SQL を比較しています。</span><span class="sxs-lookup"><span data-stu-id="2b132-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="2b132-131">Microsoft の中心とオープンソースの両方のオプションを含む、Azure で利用可能なデータストレージオプションについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="2b132-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="2b132-132">最後に、クラウドネイティブアプリケーションでのキャッシュと Elasticsearch について説明しました。</span><span class="sxs-lookup"><span data-stu-id="2b132-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="2b132-133">References</span><span class="sxs-lookup"><span data-stu-id="2b132-133">References</span></span>

- [<span data-ttu-id="2b132-134">コマンド クエリ責務分離 (CQRS) パターン</span><span class="sxs-lookup"><span data-stu-id="2b132-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="2b132-135">イベントソーシングパターン</span><span class="sxs-lookup"><span data-stu-id="2b132-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="2b132-136">定理で RDBMS パーティショントレラントが使用できないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="2b132-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="2b132-137">具体化されたビュー</span><span class="sxs-lookup"><span data-stu-id="2b132-137">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="2b132-138">オープンソースデータベースについて理解しておく必要があること</span><span class="sxs-lookup"><span data-stu-id="2b132-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="2b132-139">補正トランザクション パターン</span><span class="sxs-lookup"><span data-stu-id="2b132-139">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="2b132-140">Saga パターン</span><span class="sxs-lookup"><span data-stu-id="2b132-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="2b132-141">Saga Patterns |マイクロサービスを使用してビジネストランザクションを実装する方法</span><span class="sxs-lookup"><span data-stu-id="2b132-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="2b132-142">補正トランザクション パターン</span><span class="sxs-lookup"><span data-stu-id="2b132-142">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="2b132-143">9 ~ ボールの背後: Cosmos DB の一貫性レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2b132-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="2b132-144">さまざまな種類の NoSQL データベースの調査パート II</span><span class="sxs-lookup"><span data-stu-id="2b132-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="2b132-145">RDBMS、NoSQL、NewSQL データベースの場合。John ライアンとのインタビュー</span><span class="sxs-lookup"><span data-stu-id="2b132-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="2b132-146">SQL vs NoSQL vs NewSQL: 完全な比較</span><span class="sxs-lookup"><span data-stu-id="2b132-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="2b132-147">ダッシュ: Kubernetes ネイティブデータベースの4つのプロパティ</span><span class="sxs-lookup"><span data-stu-id="2b132-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="2b132-148">CockroachDB</span><span class="sxs-lookup"><span data-stu-id="2b132-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="2b132-149">TiDB</span><span class="sxs-lookup"><span data-stu-id="2b132-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="2b132-150">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="2b132-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="2b132-151">Vitess</span><span class="sxs-lookup"><span data-stu-id="2b132-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="2b132-152">Elasticsearch: 決定版ガイド</span><span class="sxs-lookup"><span data-stu-id="2b132-152">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="2b132-153">Apache Lucene の概要</span><span class="sxs-lookup"><span data-stu-id="2b132-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="2b132-154">[前へ](azure-caching.md)
>[次へ](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="2b132-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
