---
title: クラウドネイティブアプリケーションでのエラスティックサーチ
description: クラウドネイティブ アプリケーションに Elastic Search 機能を追加する方法について説明します。
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 1bce255b6315006b11e0b6ac77040300f67ed984
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141290"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a><span data-ttu-id="7b058-103">クラウドネイティブ アプリでのエラスティック検索</span><span class="sxs-lookup"><span data-stu-id="7b058-103">Elasticsearch in a cloud-native app</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="7b058-104">Elasticsearch は分散型の検索および分析システムであり、多様な種類のデータに対して複雑な検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b058-104">Elasticsearch is a distributed search and analytics system that enables complex search capabilities across diverse types of data.</span></span> <span data-ttu-id="7b058-105">それはオープンソースで、広く普及しています。</span><span class="sxs-lookup"><span data-stu-id="7b058-105">It's open source and widely popular.</span></span> <span data-ttu-id="7b058-106">次の企業が Elasticsearch をアプリケーションに統合する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="7b058-106">Consider how the following companies integrate Elasticsearch into their application:</span></span>

- <span data-ttu-id="7b058-107">[ウィキペディア](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/)で全文検索とインクリメンタル検索(入力時に検索)</span><span class="sxs-lookup"><span data-stu-id="7b058-107">[Wikipedia](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) for full-text and incremental (search as you type) searching.</span></span>
- <span data-ttu-id="7b058-108">[GitHub](https://www.elastic.co/customers/github)は、800 万を超えるコード リポジトリをインデックス化して公開します。</span><span class="sxs-lookup"><span data-stu-id="7b058-108">[GitHub](https://www.elastic.co/customers/github) to index and expose over 8 million code repositories.</span></span>  
- <span data-ttu-id="7b058-109">コンテナー ライブラリを検出可能にするための[Docker。](https://www.elastic.co/customers/docker)</span><span class="sxs-lookup"><span data-stu-id="7b058-109">[Docker](https://www.elastic.co/customers/docker) for making its container library discoverable.</span></span>

<span data-ttu-id="7b058-110">弾性検索は[、Apache Lucene](https://lucene.apache.org/core/)フルテキスト検索エンジンの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="7b058-110">Elasticsearch is built on top of the [Apache Lucene](https://lucene.apache.org/core/) full-text search engine.</span></span> <span data-ttu-id="7b058-111">Lucene は、高パフォーマンスのドキュメントインデックス作成とクエリを提供します。</span><span class="sxs-lookup"><span data-stu-id="7b058-111">Lucene provides high-performance document indexing and querying.</span></span> <span data-ttu-id="7b058-112">逆インデックス作成スキームでデータをインデックス化し、ページをキーワードにマッピングする代わりに、ブックの最後にある用語集と同じように、キーワードをページにマップします。</span><span class="sxs-lookup"><span data-stu-id="7b058-112">It indexes data with an inverted indexing scheme – instead of mapping pages to keywords, it maps keywords to pages just like a glossary at the end of a book.</span></span> <span data-ttu-id="7b058-113">Lucene には強力なクエリ構文機能があり、次の方法でデータをクエリできます。</span><span class="sxs-lookup"><span data-stu-id="7b058-113">Lucene has powerful query syntax capabilities and can query data by:</span></span>

- <span data-ttu-id="7b058-114">用語 (完全な単語)</span><span class="sxs-lookup"><span data-stu-id="7b058-114">Term (a full word)</span></span>
- <span data-ttu-id="7b058-115">プレフィックス (先頭から単語)</span><span class="sxs-lookup"><span data-stu-id="7b058-115">Prefix (starts-with word)</span></span>
- <span data-ttu-id="7b058-116">ワイルドカード ("" または "?"\*フィルターを使用)</span><span class="sxs-lookup"><span data-stu-id="7b058-116">Wildcard (using "\*" or "?" filters)</span></span>
- <span data-ttu-id="7b058-117">フレーズ (ドキュメント内の一連のテキスト)</span><span class="sxs-lookup"><span data-stu-id="7b058-117">Phrase (a sequence of text in a document)</span></span>
- <span data-ttu-id="7b058-118">ブール値 (クエリを組み合わせた複雑な検索)</span><span class="sxs-lookup"><span data-stu-id="7b058-118">Boolean value (complex searches combining queries)</span></span>

<span data-ttu-id="7b058-119">Lucene は検索用の低レベル配管を提供しますが、Elasticsearch は Lucene の上に位置するサーバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="7b058-119">While Lucene provides low-level plumbing for searching, Elasticsearch provides the server that sits on top of Lucene.</span></span> <span data-ttu-id="7b058-120">Elasticsearch は、Lucene のインデックス作成と検索機能にアクセスするための RESTful API など、作業を簡素化する高レベルの機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="7b058-120">Elasticsearch adds higher-level functionality to simplify working Lucene, including a RESTful API to access Lucene’s indexing and searching functionality.</span></span> <span data-ttu-id="7b058-121">また、大規模な拡張性、フォールト トレランス、および高可用性を実現できる分散インフラストラクチャも提供します。</span><span class="sxs-lookup"><span data-stu-id="7b058-121">It also provides a distributed infrastructure capable of massive scalability, fault tolerance, and high availability.</span></span>

<span data-ttu-id="7b058-122">複雑な検索要件を持つ大規模なクラウド ネイティブ アプリケーションでは、Elasticsearch を Azure のマネージド サービスとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="7b058-122">For larger cloud-native applications with complex search requirements, Elasticsearch is available as managed service in Azure.</span></span> <span data-ttu-id="7b058-123">Microsoft Azure マーケットプレースには、開発者が Azure に Elasticsearch クラスターをデプロイするために使用できる、事前に構成されたテンプレートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7b058-123">The Microsoft Azure Marketplace features preconfigured templates which developers can use to deploy an Elasticsearch cluster on Azure.</span></span>

<span data-ttu-id="7b058-124">開発者は、Microsoft Azure マーケットプレースから、Azure に Elasticsearch クラスターを迅速にデプロイするために構築された構成済みテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b058-124">From the Microsoft Azure Marketplace, developers can use preconfigured templates built to quickly deploy an Elasticsearch cluster on Azure.</span></span> <span data-ttu-id="7b058-125">Azure 管理製品を使用すると、最大 50 個のデータ ノード、20 個の調整ノード、および 3 つの専用マスター ノードをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="7b058-125">Using the Azure-managed offering, you can deploy up to 50 data nodes, 20 coordinating nodes, and three dedicated master nodes.</span></span>

## <a name="summary"></a><span data-ttu-id="7b058-126">まとめ</span><span class="sxs-lookup"><span data-stu-id="7b058-126">Summary</span></span>

<span data-ttu-id="7b058-127">この章では、クラウドネイティブシステムのデータについて詳しく説明しました。</span><span class="sxs-lookup"><span data-stu-id="7b058-127">This chapter presented a detailed look at data in cloud-native systems.</span></span> <span data-ttu-id="7b058-128">まず、モノリシックアプリケーションのデータストレージとクラウドネイティブシステムのデータストレージパターンを比べていました。</span><span class="sxs-lookup"><span data-stu-id="7b058-128">We started by contrasting data storage in monolithic applications with data storage patterns in cloud-native systems.</span></span> <span data-ttu-id="7b058-129">クラウドネイティブシステムに実装されているデータパターン(サービス間のクエリ、分散トランザクション、大量のシステムに対応するパターンなど)を見てきました。</span><span class="sxs-lookup"><span data-stu-id="7b058-129">We looked at data patterns implemented in cloud-native systems, including cross-service queries, distributed transactions, and patterns to deal with high-volume systems.</span></span> <span data-ttu-id="7b058-130">SQL と NoSQL データを対比しました。</span><span class="sxs-lookup"><span data-stu-id="7b058-130">We contrasted SQL with NoSQL data.</span></span> <span data-ttu-id="7b058-131">マイクロソフト中心のオプションとオープン ソース オプションの両方を含む、Azure で利用可能なデータ ストレージ オプションについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="7b058-131">We looked at data storage options available in Azure that include both Microsoft-centric and open-source options.</span></span> <span data-ttu-id="7b058-132">最後に、クラウドネイティブアプリケーションでのキャッシュと Elasticsearch について説明しました。</span><span class="sxs-lookup"><span data-stu-id="7b058-132">Finally, we discussed caching and Elasticsearch in a cloud-native application.</span></span>

### <a name="references"></a><span data-ttu-id="7b058-133">References</span><span class="sxs-lookup"><span data-stu-id="7b058-133">References</span></span>

- [<span data-ttu-id="7b058-134">コマンド クエリ責務分離 (CQRS) パターン</span><span class="sxs-lookup"><span data-stu-id="7b058-134">Command and Query Responsibility Segregation (CQRS) pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [<span data-ttu-id="7b058-135">イベント ソーシング パターン</span><span class="sxs-lookup"><span data-stu-id="7b058-135">Event Sourcing pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [<span data-ttu-id="7b058-136">RDBMS と NoSQL データベース: 概要</span><span class="sxs-lookup"><span data-stu-id="7b058-136">RDBMSs vs. NoSQL Databases: Overview</span></span>](https://maxivak.com/rdbms-vs-nosql-databases/)

- [<span data-ttu-id="7b058-137">CAP 定理で RDBMS パーティショントレラントが使用できないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="7b058-137">Why isn't RDBMS Partition Tolerant in CAP Theorem and why is it Available?</span></span>](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [<span data-ttu-id="7b058-138">マテリアライズビュー</span><span class="sxs-lookup"><span data-stu-id="7b058-138">Materialized View</span></span>](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [<span data-ttu-id="7b058-139">オープンソースデータベースについて本当に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="7b058-139">All you really need to know about open source databases</span></span>](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [<span data-ttu-id="7b058-140">補正トランザクション パターン</span><span class="sxs-lookup"><span data-stu-id="7b058-140">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="7b058-141">佐賀パターン</span><span class="sxs-lookup"><span data-stu-id="7b058-141">Saga Pattern</span></span>](https://microservices.io/patterns/data/saga.html)

- [<span data-ttu-id="7b058-142">サガパターン |マイクロサービスを使用してビジネス トランザクションを実装する方法</span><span class="sxs-lookup"><span data-stu-id="7b058-142">Saga Patterns | How to implement business transactions using microservices</span></span>](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [<span data-ttu-id="7b058-143">補正トランザクション パターン</span><span class="sxs-lookup"><span data-stu-id="7b058-143">Compensating Transaction pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [<span data-ttu-id="7b058-144">9ボールの背後に立つ:コスモスDBの一貫性レベルの説明</span><span class="sxs-lookup"><span data-stu-id="7b058-144">Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained</span></span>](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [<span data-ttu-id="7b058-145">NoSQL データベースの異なるタイプの探索パート II</span><span class="sxs-lookup"><span data-stu-id="7b058-145">Exploring the different types of NoSQL Databases Part II</span></span>](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [<span data-ttu-id="7b058-146">RDBMS、NoSQL、およびニューSQLデータベース。ジョン・ライアンインタビュー</span><span class="sxs-lookup"><span data-stu-id="7b058-146">On RDBMS, NoSQL and NewSQL databases. Interview with John Ryan</span></span>](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [<span data-ttu-id="7b058-147">SQL 対 NoSQL 対 新しい SQL: 完全な比較</span><span class="sxs-lookup"><span data-stu-id="7b058-147">SQL vs NoSQL vs NewSQL: The Full Comparison</span></span>](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [<span data-ttu-id="7b058-148">DASH: クベルネテス-ネイティブデータベースの4つのプロパティ</span><span class="sxs-lookup"><span data-stu-id="7b058-148">DASH: Four Properties of Kubernetes-Native Databases</span></span>](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [<span data-ttu-id="7b058-149">ゴキブリDB</span><span class="sxs-lookup"><span data-stu-id="7b058-149">CockroachDB</span></span>](https://www.cockroachlabs.com/)

- [<span data-ttu-id="7b058-150">ティジド</span><span class="sxs-lookup"><span data-stu-id="7b058-150">TiDB</span></span>](https://pingcap.com/en/)

- [<span data-ttu-id="7b058-151">ユガバイトDB</span><span class="sxs-lookup"><span data-stu-id="7b058-151">YugabyteDB</span></span>](https://www.yugabyte.com/)

- [<span data-ttu-id="7b058-152">ヴィテス</span><span class="sxs-lookup"><span data-stu-id="7b058-152">Vitess</span></span>](https://vitess.io/)

- [<span data-ttu-id="7b058-153">Elasticsearch: 決定版ガイド</span><span class="sxs-lookup"><span data-stu-id="7b058-153">Elasticsearch: The Definitive Guide</span></span>](http://shop.oreilly.com/product/0636920028505.do)
  
- [<span data-ttu-id="7b058-154">アパッチ・ルセンの紹介</span><span class="sxs-lookup"><span data-stu-id="7b058-154">Introduction to Apache Lucene</span></span>](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
><span data-ttu-id="7b058-155">[前次](azure-caching.md)
>[Next](resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="7b058-155">[Previous](azure-caching.md)
[Next](resiliency.md)</span></span> <!-- Next Chapter -->
