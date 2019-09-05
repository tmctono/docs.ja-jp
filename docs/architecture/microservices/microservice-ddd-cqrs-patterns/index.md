---
title: マイクロサービスで DDD と CQRS パターンを使ってビジネスの複雑さに取り組む
description: コンテナー化された .NET アプリケーションの .NET マイクロサービス アーキテクチャ | DDD と CQRS パターンを適用して複雑なビジネス シナリオに取り組む方法を理解する
ms.date: 10/08/2018
ms.openlocfilehash: d311641e2ac73205c04c3f1147b54991585ce851
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295103"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="d7ab6-103">マイクロサービスで DDD と CQRS パターンを使ってビジネスの複雑さに取り組む</span><span class="sxs-lookup"><span data-stu-id="d7ab6-103">Tackle Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="d7ab6-104">*ビジネス ドメインの理解を反映するマイクロソフトサービスまたはコンテキスト境界ごとのドメイン モデルを設計する*</span><span class="sxs-lookup"><span data-stu-id="d7ab6-104">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="d7ab6-105">このセクションでは、複雑なサブシステムへの取り組みが必要な場合に実装する高度なマイクロサービスについて、またドメイン専門家の知識と絶えず変化するビジネス ルールに由来するマイクロサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-105">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="d7ab6-106">このセクションで使用するアーキテクチャ パターンは、図 7-1 に示すように、ドメイン駆動設計 (DDD) とコマンドクエリ責務分離 (CQRS) の手法に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-106">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 7-1.</span></span>

![外部アーキテクチャ (マイクロサービス パターン、API ゲートウェイ、回復力のある通信、pub/sub など) と、内部アーキテクチャ (データ駆動型/CRUD、DDD パターン、依存関係の挿入、複数のライブラリなど) の違い。](./media/image1.png)

<span data-ttu-id="d7ab6-108">**図 7-1**。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-108">**Figure 7-1**.</span></span> <span data-ttu-id="d7ab6-109">外部マイクロサービス アーキテクチャとマイクロサービスごとの内部アーキテクチャ パターンとの対比</span><span class="sxs-lookup"><span data-stu-id="d7ab6-109">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="d7ab6-110">ただし、ASP.NET Core Web API サービスの実装方法や、Swashbuckle または NSwag を使った Swagger メタデータの公開方法など、データ駆動型マイクロサービスのテクニックのほとんどは、DDD パターンを使って内部的に実装される高度なマイクロサービスにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-110">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle or NSwag, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="d7ab6-111">前述した実施方法のほとんどはここでも、または任意の種類のマイクロ サービスにも適用されるため、このセクションは前のセクションの内容を増補するものとなっています。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-111">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="d7ab6-112">このセクションでは、まず eShopOnContainers 参照アプリケーションで使用される簡略化された CQRS パターンの詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-112">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="d7ab6-113">後で DDD 手法の概要を説明しますが、そこでは、アプリケーションで再利用できる一般的なパターンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-113">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="d7ab6-114">DDD は、学習用に豊富な技術資料が提供されている大きなテーマです。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-114">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="d7ab6-115">入門書としては、Eric Evans 著の『[Domain-Driven Design](https://domainlanguage.com/ddd/)』 (ドメイン駆動設計)、さらに Vaughn Vernon、Jimmy Nilsson、Greg Young、Udi Dahan、Jimmy Bogard の各氏、およびその他多くの DDD/CQRS の専門家による技術資料などを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-115">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="d7ab6-116">ただし、DDD 手法の適用方法の習得には何より、具体的なビジネス ドメイン内で専門家との対話、ホワイトボードを使った議論、ドメイン モデリングのセッションを利用する試みが必要です。</span><span class="sxs-lookup"><span data-stu-id="d7ab6-116">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="d7ab6-117">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="d7ab6-117">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="d7ab6-118">DDD (ドメイン駆動設計)</span><span class="sxs-lookup"><span data-stu-id="d7ab6-118">DDD (Domain-Driven Design)</span></span>

- <span data-ttu-id="d7ab6-119">**Eric Evans。ドメイン言語** </span><span class="sxs-lookup"><span data-stu-id="d7ab6-119">**Eric Evans. Domain Language** </span></span>\
  <https://domainlanguage.com/>

- <span data-ttu-id="d7ab6-120">**Martin Fowler。ドメイン駆動設計** </span><span class="sxs-lookup"><span data-stu-id="d7ab6-120">**Martin Fowler. Domain-Driven Design** </span></span>\
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- <span data-ttu-id="d7ab6-121">**Jimmy Bogard。ドメインの強化: 入門** </span><span class="sxs-lookup"><span data-stu-id="d7ab6-121">**Jimmy Bogard. Strengthening your domain: a primer** </span></span>\
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a><span data-ttu-id="d7ab6-122">DDD 関連の書籍</span><span class="sxs-lookup"><span data-stu-id="d7ab6-122">DDD books</span></span>

- <span data-ttu-id="d7ab6-123">**Eric Evans。Domain-Driven Design:Tackling Complexity in the Heart of Software (エリック・エヴァンスのドメイン駆動設計)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="d7ab6-124">**Eric Evans。Domain-Driven Design Reference: Definitions and Pattern Summaries (ドメイン駆動設計のリファレンス: 定義とパターンの概要)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- <span data-ttu-id="d7ab6-125">**Vaughn Vernon。Implementing Domain-Driven Design (実践ドメイン駆動設計)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-125">**Vaughn Vernon. Implementing Domain-Driven Design** </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="d7ab6-126">**Vaughn Vernon。Domain-Driven Design Distilled (ドメイン駆動設計の基本)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-126">**Vaughn Vernon. Domain-Driven Design Distilled** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- <span data-ttu-id="d7ab6-127">**Jimmy Nilsson。Applying Domain-Driven Design and Patterns (ドメイン駆動)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns** </span></span>\
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- <span data-ttu-id="d7ab6-128">**Cesar de la Torre。N-Layered Domain-Oriented Architecture Guide with .NET (.NET による N 層ドメイン指向アーキテクチャ ガイド)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET** </span></span>\
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- <span data-ttu-id="d7ab6-129">**Abel Avram および Floyd Marinescu。Domain-Driven Design Quickly (ドメイン駆動設計簡易ガイド)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-129">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- <span data-ttu-id="d7ab6-130">**Scott Millett、Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design (ドメイン駆動設計のパターン、原則、実践)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-130">**Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design** </span></span>\
  <http://www.wrox.com/WileyCDA/WroxTitle/Patterns-Principles-and-Practices-of-Domain-Driven-Design.productCd-1118714709.html>

##### <a name="ddd-training"></a><span data-ttu-id="d7ab6-131">DDD に関するトレーニング</span><span class="sxs-lookup"><span data-stu-id="d7ab6-131">DDD training</span></span>

- <span data-ttu-id="d7ab6-132">**Julie Lerman および Steve Smith。Domain-Driven Design Fundamentals (ドメイン駆動設計の基礎)**  </span><span class="sxs-lookup"><span data-stu-id="d7ab6-132">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals** </span></span>\
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
><span data-ttu-id="d7ab6-133">[前へ](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[次へ](apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="d7ab6-133">[Previous](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
[Next](apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>