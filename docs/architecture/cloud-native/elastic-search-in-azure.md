---
title: クラウドネイティブアプリケーションの Elasticsearch
description: クラウドネイティブアプリケーションにエラスティック検索機能を追加する方法について説明します。
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 70d1925d6b8c7bbe515ee4f178513dc61212ebce
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271803"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="bb830-103">クラウドネイティブアプリでの Elasticsearch</span><span class="sxs-lookup"><span data-stu-id="bb830-103">Elasticsearch in a cloud-native app</span></span>

<span data-ttu-id="bb830-104">Elasticsearch は、さまざまな種類のデータに対して複雑な検索機能を有効にする分散検索および分析システムです。</span><span class="sxs-lookup"><span data-stu-id="bb830-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="bb830-105">オープンソースで広く普及しています。</span><span class="sxs-lookup"><span data-stu-id="bb830-105">It's open source and widely popular.</span></span> <span data-ttu-id="bb830-106">次の企業が Elasticsearch をアプリケーションに統合する方法を検討します。</span><span class="sxs-lookup"><span data-stu-id="bb830-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="bb830-107">フルテキストとインクリメンタル (入力時の検索) の[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) 。</span><span class="sxs-lookup"><span data-stu-id="bb830-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="bb830-108">800万コードリポジトリにインデックスを作成して公開する[GitHub](https://www.elastic.co/customers/github) 。</span><span class="sxs-lookup"><span data-stu-id="bb830-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="bb830-109">コンテナーライブラリを検出できるようにするための[Docker](https://www.elastic.co/customers/docker) 。</span><span class="sxs-lookup"><span data-stu-id="bb830-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="bb830-110">Elasticsearch は、 [Apache Lucene](https://lucene.apache.org/core/) フルテキスト検索エンジンの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="bb830-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="bb830-111">Lucene は、高パフォーマンスのドキュメントのインデックス作成とクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="bb830-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="bb830-112">逆インデックススキームを使用してデータのインデックスを作成します。ページをキーワードにマップするのではなく、ブックの最後にある用語集と同じように、キーワードをページにマップします。</span><span class="sxs-lookup"><span data-stu-id="bb830-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="bb830-113">Lucene には強力なクエリ構文機能があり、次の方法でデータを照会できます。</span><span class="sxs-lookup"><span data-stu-id="bb830-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="bb830-114">用語 (完全な単語)</span><span class="sxs-lookup"><span data-stu-id="bb830-114">Term (a full word)</span></span>
- <span data-ttu-id="bb830-115">プレフィックス (先頭は word)</span><span class="sxs-lookup"><span data-stu-id="bb830-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="bb830-116">ワイルドカード (" \* " フィルターまたは "?" フィルターを使用)</span><span class="sxs-lookup"><span data-stu-id="bb830-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="bb830-117">フレーズ (ドキュメント内のテキストのシーケンス)</span><span class="sxs-lookup"><span data-stu-id="bb830-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="bb830-118">ブール値 (複合検索クエリの結合)</span><span class="sxs-lookup"><span data-stu-id="bb830-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="bb830-119">Lucene では検索のための低レベルのプラミングが提供されますが、Elasticsearch は Lucene の上にあるサーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb830-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="bb830-120">Elasticsearch は、Lucene のインデックス作成と検索機能にアクセスする RESTful API など、操作を簡略化するために、より高度な機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="bb830-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene's indexing and searching functionality.</span></span> <span data-ttu-id="bb830-121">また、大規模なスケーラビリティ、フォールトトレランス、高可用性を備えた分散インフラストラクチャも提供します。</span><span class="sxs-lookup"><span data-stu-id="bb830-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="bb830-122">複雑な検索要件を持つ大規模なクラウドネイティブアプリケーションの場合、Elasticsearch は Azure の管理されたサービスとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="bb830-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="bb830-123">Microsoft Azure Marketplace には、Azure で Elasticsearch クラスターをデプロイするために開発者が使用できる事前構成済みのテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bb830-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="bb830-124">Microsoft Azure Marketplace から、開発者は、Azure で Elasticsearch クラスターをすばやくデプロイするために構築された構成済みテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb830-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="bb830-125">Azure で管理されたサービスを使用すると、最大50のデータノード、20個の調整ノード、3つの専用マスターノードをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="bb830-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="bb830-126">まとめ</span><span class="sxs-lookup"><span data-stu-id="bb830-126">Summary</span></span>

<span data-ttu-id="bb830-127">この章では、クラウドネイティブシステムのデータについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="bb830-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="bb830-128">クラウドネイティブシステムのデータストレージパターンを使用してモノリシックアプリケーションのデータストレージを比較することから始めました。</span><span class="sxs-lookup"><span data-stu-id="bb830-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="bb830-129">クラウドネイティブシステムに実装されているデータパターンを見てきました。これには、クロスサービスクエリ、分散トランザクション、および大量システムを扱うためのパターンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb830-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="bb830-130">NoSQL データを使用して SQL を比較しています。</span><span class="sxs-lookup"><span data-stu-id="bb830-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="bb830-131">Microsoft の中心とオープンソースの両方のオプションを含む、Azure で利用可能なデータストレージオプションについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="bb830-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="bb830-132">最後に、クラウドネイティブアプリケーションでのキャッシュと Elasticsearch について説明しました。</span><span class="sxs-lookup"><span data-stu-id="bb830-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="bb830-133">参考資料</span><span class="sxs-lookup"><span data-stu-id="bb830-133">References</span></span>

- [<span data-ttu-id="bb830-134">コマンドクエリ責務分離 (CQRS) パターン</span><span class="sxs-lookup"><span data-stu-id="bb830-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="bb830-135">イベント ソーシング パターン</span><span class="sxs-lookup"><span data-stu-id="bb830-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="bb830-136">定理で RDBMS パーティショントレラントが使用できないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="bb830-136">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="bb830-137">具体化されたビュー</span><span class="sxs-lookup"><span data-stu-id="bb830-137">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="bb830-138">オープンソースデータベースについて理解しておく必要があること</span><span class="sxs-lookup"><span data-stu-id="bb830-138">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="bb830-139">補正トランザクション パターン</span><span class="sxs-lookup"><span data-stu-id="bb830-139">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="bb830-140">Saga パターン</span><span class="sxs-lookup"><span data-stu-id="bb830-140">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="bb830-141">Saga Patterns |マイクロサービスを使用してビジネストランザクションを実装する方法</span><span class="sxs-lookup"><span data-stu-id="bb830-141">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="bb830-142">補正トランザクション パターン</span><span class="sxs-lookup"><span data-stu-id="bb830-142">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="bb830-143">9 ~ ボールの背後: Cosmos DB の一貫性レベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bb830-143">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="bb830-144">さまざまな種類の NoSQL データベースの調査パート II</span><span class="sxs-lookup"><span data-stu-id="bb830-144">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="bb830-145">RDBMS、NoSQL、NewSQL データベースの場合。John ライアンとのインタビュー</span><span class="sxs-lookup"><span data-stu-id="bb830-145">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="bb830-146">SQL vs NoSQL vs NewSQL: 完全な比較</span><span class="sxs-lookup"><span data-stu-id="bb830-146">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="bb830-147">ダッシュ: Kubernetes ネイティブデータベースの4つのプロパティ</span><span class="sxs-lookup"><span data-stu-id="bb830-147">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="bb830-148">CockroachDB</span><span class="sxs-lookup"><span data-stu-id="bb830-148">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="bb830-149">TiDB</span><span class="sxs-lookup"><span data-stu-id="bb830-149">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="bb830-150">YugabyteDB</span><span class="sxs-lookup"><span data-stu-id="bb830-150">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="bb830-151">Vitess</span><span class="sxs-lookup"><span data-stu-id="bb830-151">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="bb830-152">Elasticsearch: 決定版ガイド</span><span class="sxs-lookup"><span data-stu-id="bb830-152">Elasticsearch: The Definitive Guide</span></span>](https://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="bb830-153">Apache Lucene の概要</span><span class="sxs-lookup"><span data-stu-id="bb830-153">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="bb830-154">[前へ](azure-caching.md)
>[次へ](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="bb830-154">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
