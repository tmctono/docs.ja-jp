---
title: 分散データ
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |クラウドネイティブアプリの分散データ
ms.date: 06/30/2019
ms.openlocfilehash: b715ae5203264a023bc9f911aa74ee222afe3d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841811"
---
# <a name="distributed-data-for-cloud-native-apps"></a><span data-ttu-id="98abc-103">クラウドネイティブアプリの分散データ</span><span class="sxs-lookup"><span data-stu-id="98abc-103">Distributed data for cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="98abc-104">さまざまな独立したマイクロサービスで構成されるクラウドネイティブシステムを構築する場合、データストレージの変更について考えてみる方法。</span><span class="sxs-lookup"><span data-stu-id="98abc-104">When constructing a cloud-native system that consists of many independent microservices, the way you think about data storage changes.</span></span>

<span data-ttu-id="98abc-105">従来のモノリシックアプリケーションは、図5-1 に示す一元化されたデータストアを優先します。</span><span class="sxs-lookup"><span data-stu-id="98abc-105">Traditional monolithic applications favor a centralized data store shown in Figure 5-1.</span></span>

![単一のモノリシックデータベース](./media/single-monolithic-database.png)

<span data-ttu-id="98abc-107">**図 5-1**.</span><span class="sxs-lookup"><span data-stu-id="98abc-107">**Figure 5-1**.</span></span> <span data-ttu-id="98abc-108">単一のモノリシックデータベース</span><span class="sxs-lookup"><span data-stu-id="98abc-108">Single monolithic database</span></span>

<span data-ttu-id="98abc-109">前の図では、すべてのアプリケーションコンポーネントが1つのリレーショナルデータベースを使用していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="98abc-109">Note in the previous figure how all of the application components consume a single relational database.</span></span>

<span data-ttu-id="98abc-110">このアプローチには多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="98abc-110">There are many benefits to this approach.</span></span> <span data-ttu-id="98abc-111">複数のテーブルにまたがるデータをクエリするのは簡単で、データの一貫性を保証する[ACID トランザクション](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties)を簡単に実装できます。</span><span class="sxs-lookup"><span data-stu-id="98abc-111">It's straightforward to query data spread across  multiple tables, and it's straightforward to implement [ACID transactions](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) that ensure data consistency.</span></span> <span data-ttu-id="98abc-112">常に、すぐに*整合性が保た*れます。すべてのデータ更新またはいずれも実行されません。</span><span class="sxs-lookup"><span data-stu-id="98abc-112">You always end up with *immediate consistency*: either all your data updates or none of it does.</span></span>

<span data-ttu-id="98abc-113">クラウドネイティブシステムは、図5-2 に示されているデータアーキテクチャを優先します。このアーキテクチャでは、各マイクロサービスが独自のデータを所有してカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="98abc-113">Cloud-native systems favor a data architecture shown in Figure 5-2 in which each microservice owns and encapsulates its own data.</span></span>

![マイクロサービス間で複数のデータベース](./media/data-across-microservices.png)

<span data-ttu-id="98abc-115">**図 5-2**</span><span class="sxs-lookup"><span data-stu-id="98abc-115">**Figure 5-2**.</span></span> <span data-ttu-id="98abc-116">マイクロサービス間で複数のデータベース</span><span class="sxs-lookup"><span data-stu-id="98abc-116">Multiple databases across microservices</span></span>

<span data-ttu-id="98abc-117">前の図では、各マイクロサービスがそのデータストアを所有およびカプセル化し、パブリック API から外部のデータのみを公開することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="98abc-117">Note how in the previous figure each microservice owns and encapsulates it data store and only exposes data to the outside world from its public API.</span></span>

<span data-ttu-id="98abc-118">このモデルでは、他のマイクロサービスを使用してデータスキーマの変更を調整することなく、各マイクロサービスを独立して進化させることができます。</span><span class="sxs-lookup"><span data-stu-id="98abc-118">This model enables each microservice to evolve independently without having to coordinate data schema changes with other microservices.</span></span> <span data-ttu-id="98abc-119">各マイクロサービスは、ニーズに最も合ったデータストア (リレーショナルデータベース、ドキュメントデータベース、キー値ストア) を自由に実装できます。</span><span class="sxs-lookup"><span data-stu-id="98abc-119">Each microservice is free to implement the data store (relational database, document database, key-value store) type that best matches its needs.</span></span> <span data-ttu-id="98abc-120">実行時に、各マイクロサービスはそれに応じてデータをスケーリングできます。</span><span class="sxs-lookup"><span data-stu-id="98abc-120">At runtime, each microservice can scale its data accordingly.</span></span> <span data-ttu-id="98abc-121">これを図5-3 に示します。</span><span class="sxs-lookup"><span data-stu-id="98abc-121">This is shown in Figure 5-3:</span></span>

![多言語データ永続化](./media/polyglot-data-persistence.png)

<span data-ttu-id="98abc-123">**図 5-3**</span><span class="sxs-lookup"><span data-stu-id="98abc-123">**Figure 5-3**.</span></span> <span data-ttu-id="98abc-124">多言語データ永続化</span><span class="sxs-lookup"><span data-stu-id="98abc-124">Polyglot data persistence</span></span>

<span data-ttu-id="98abc-125">前の図では、製品カタログと在庫マイクロサービスによって、リレーショナルデータベース、注文マイクロサービス、NoSql ドキュメントデータベース、および外部キーと値のストアであるショッピングカートマイクロサービスが採用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="98abc-125">Note how in the previous figure the product catalog and inventory microservices adopt relational databases, the ordering microservice, a NoSql document database, and the shopping cart microservice, which is an external key-value store.</span></span> <span data-ttu-id="98abc-126">リレーショナルデータベースは、複雑なデータを含むマイクロサービスに関連していますが、NoSQL データベースでは、適応性、高速検索、高可用性を提供することで、非常に多くの人気を獲得しています。</span><span class="sxs-lookup"><span data-stu-id="98abc-126">While relational databases remain relevant for microservices with complex data, NoSQL databases have gained considerable popularity, providing adaptability, fast lookup, and high availability.</span></span> <span data-ttu-id="98abc-127">これらのスキーマを使用すると、開発者は、型指定されたデータクラスのアーキテクチャから移動したり、変更をコストのかかる時間がかかるようにしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="98abc-127">Their schemaless nature allows developers to move away from an architecture of typed data classes and ORMs that make change expensive and time-consuming.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="98abc-128">[前へ](service-mesh-communication-infrastructure.md)
>[次へ](data-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="98abc-128">[Previous](service-mesh-communication-infrastructure.md)
[Next](data-patterns.md)</span></span>
