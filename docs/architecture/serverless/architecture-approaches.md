---
title: アーキテクチャアプローチ-サーバーレスアプリ
description: N 層アーキテクチャからサーバーレスにクラウドベースのエンタープライズアプリケーションを構築するためのアーキテクチャのアプローチについて説明します。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522901"
---
# <a name="architecture-approaches"></a><span data-ttu-id="6e81b-103">アーキテクチャのアプローチ</span><span class="sxs-lookup"><span data-stu-id="6e81b-103">Architecture approaches</span></span>

<span data-ttu-id="6e81b-104">エンタープライズアプリを設計するための既存のアプローチを理解することは、サーバーレスで果たす役割を明確にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="6e81b-105">数十年ものソフトウェア開発に発展したさまざまな手法とパターンがあり、それぞれに独自の長所と短所があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="6e81b-106">多くの場合、ultimate ソリューションでは1つのアプローチを決定する必要はありませんが、複数の方法を統合することがあります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="6e81b-107">移行シナリオでは、多くの場合、ハイブリッドアプローチによって1つのアーキテクチャアプローチから別のアーキテクチャに移行します。</span><span class="sxs-lookup"><span data-stu-id="6e81b-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="6e81b-108">この章では、エンタープライズアプリケーションの論理アーキテクチャと物理アーキテクチャの両方の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e81b-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="6e81b-109">アーキテクチャパターン</span><span class="sxs-lookup"><span data-stu-id="6e81b-109">Architecture patterns</span></span>

<span data-ttu-id="6e81b-110">最新のビジネスアプリケーションは、さまざまなアーキテクチャパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="6e81b-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="6e81b-111">ここでは、一般的なパターンの調査について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e81b-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="6e81b-112">ここに記載されているパターンは必ずしもすべてのベストプラクティスではありませんが、さまざまなアプローチを示しています。</span><span class="sxs-lookup"><span data-stu-id="6e81b-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="6e81b-113">詳細については、「 [Azure アプリケーションアーキテクチャガイド](https://docs.microsoft.com/azure/architecture/guide/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e81b-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="6e81b-114">モノリス</span><span class="sxs-lookup"><span data-stu-id="6e81b-114">Monoliths</span></span>

<span data-ttu-id="6e81b-115">多くのビジネスアプリケーションは、モノリスパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="6e81b-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="6e81b-116">レガシアプリケーションは、多くの場合、モノリスとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="6e81b-117">モノリスパターンでは、すべてのアプリケーションの問題が単一のデプロイに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e81b-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="6e81b-118">ユーザーインターフェイスからデータベースへの呼び出しはすべて、同じコードベースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e81b-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![モノリスアーキテクチャ](./media/monolith-architecture.png)

<span data-ttu-id="6e81b-120">モノリスアプローチにはいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="6e81b-121">多くの場合、単一のコードベースを取得して作業を開始するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="6e81b-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="6e81b-122">増加時間は短くなる可能性があり、テスト環境の作成は新しいコピーを提供するのと同じように簡単です。</span><span class="sxs-lookup"><span data-stu-id="6e81b-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="6e81b-123">モノリスは、複数のコンポーネントとアプリケーションを含むように設計されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="6e81b-124">残念ながら、モノリスパターンは大規模に分割される傾向があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="6e81b-125">モノリスアプローチの主な欠点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e81b-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="6e81b-126">同じコードベースで並行して作業することは困難です。</span><span class="sxs-lookup"><span data-stu-id="6e81b-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="6e81b-127">いかに簡単であるかに関係なく、アプリケーション全体の新しいバージョンを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="6e81b-128">リファクタリングは、アプリケーション全体に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="6e81b-129">多くの場合、スケーリングする唯一のソリューションは、リソースを大量に消費する複数のモノリスのコピーを作成することです。</span><span class="sxs-lookup"><span data-stu-id="6e81b-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="6e81b-130">システムの展開やその他のシステムの獲得に伴い、統合が困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="6e81b-131">モノリス全体を構成する必要があるため、テストが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="6e81b-132">コードを再利用することは困難であり、他のアプリケーションが独自のコードのコピーを作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="6e81b-133">多くの企業では、モノリスアプリケーションを移行する機会としてクラウドに注目し、同時に、より使用しやすいパターンにリファクタリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="6e81b-134">個々のアプリケーションとコンポーネントを分割して、個別に管理、デプロイ、および拡大/縮小することが一般的です。</span><span class="sxs-lookup"><span data-stu-id="6e81b-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="6e81b-135">N 層アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6e81b-135">N-Layer applications</span></span>

<span data-ttu-id="6e81b-136">N レイヤーアプリケーションパーティションアプリケーションロジックを特定のレイヤーに分割します。</span><span class="sxs-lookup"><span data-stu-id="6e81b-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="6e81b-137">最も一般的なレイヤーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e81b-137">The most common layers include:</span></span>

- <span data-ttu-id="6e81b-138">[ユーザー インターフェイス]</span><span class="sxs-lookup"><span data-stu-id="6e81b-138">User interface</span></span>
- <span data-ttu-id="6e81b-139">ビジネスロジック</span><span class="sxs-lookup"><span data-stu-id="6e81b-139">Business logic</span></span>
- <span data-ttu-id="6e81b-140">データ アクセス</span><span class="sxs-lookup"><span data-stu-id="6e81b-140">Data access</span></span>

<span data-ttu-id="6e81b-141">その他のレイヤーには、ミドルウェア、バッチ処理、API などがあります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="6e81b-142">レイヤーは論理的なものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6e81b-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="6e81b-143">これらは分離して開発されていますが、すべて同じターゲットプラットフォームにデプロイされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N 層アーキテクチャ](./media/n-layer-architecture.png)

<span data-ttu-id="6e81b-145">N 層アプローチには、次のようないくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="6e81b-146">リファクタリングはレイヤーに分離されます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="6e81b-147">チームは別々のレイヤーを個別にビルド、テスト、配置、および維持できます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="6e81b-148">レイヤーをスワップアウトすることができます。たとえば、データレイヤーは、UI レイヤーを変更することなく、複数のデータベースにアクセスする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="6e81b-149">サーバーレスは、1つまたは複数のレイヤーを実装するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="6e81b-150">マイクロサービス</span><span class="sxs-lookup"><span data-stu-id="6e81b-150">Microservices</span></span>

<span data-ttu-id="6e81b-151">**[マイクロサービス](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** アーキテクチャには、次のような共通の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="6e81b-152">アプリケーションはいくつかの小規模サービスで構成されています。</span><span class="sxs-lookup"><span data-stu-id="6e81b-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="6e81b-153">各サービスは、独自のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="6e81b-154">サービスは、ビジネスドメインに関連しています。</span><span class="sxs-lookup"><span data-stu-id="6e81b-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="6e81b-155">サービスは軽量の Api を介して通信します。通常、トランスポートとして HTTP を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e81b-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="6e81b-156">サービスは個別に展開およびアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="6e81b-157">サービスが1つのデータストアに依存していません。</span><span class="sxs-lookup"><span data-stu-id="6e81b-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="6e81b-158">システムはエラーを考慮して設計されており、特定のサービスが失敗した場合でもアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="6e81b-159">マイクロサービスは、他のアーキテクチャアプローチと相互に排他的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e81b-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="6e81b-160">たとえば、N 層アーキテクチャでは、中間層にマイクロサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="6e81b-161">また、IIS ホスト上の仮想ディレクトリからコンテナーに、さまざまな方法でマイクロサービスを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="6e81b-162">マイクロサービスの特性は、サーバーレス実装に特に適しています。</span><span class="sxs-lookup"><span data-stu-id="6e81b-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![マイクロサービス アーキテクチャ](./media/microservices-architecture.png)

<span data-ttu-id="6e81b-164">マイクロサービスアーキテクチャの長所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e81b-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="6e81b-165">リファクタリングは、多くの場合、1つのサービスに分離されます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="6e81b-166">サービスは互いに独立してアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="6e81b-167">回復性と弾力性は、個々のサービスの需要に合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="6e81b-168">開発は、さまざまなチームやプラットフォームで並行して行われます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="6e81b-169">分離サービスの包括的なテストを記述する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="6e81b-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="6e81b-170">マイクロサービスには、次のような独自の課題があります。</span><span class="sxs-lookup"><span data-stu-id="6e81b-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="6e81b-171">使用可能なサービスとその呼び出し方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="6e81b-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="6e81b-172">サービスのライフサイクルの管理。</span><span class="sxs-lookup"><span data-stu-id="6e81b-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="6e81b-173">サービスがアプリケーション全体にどのように適合するかを理解します。</span><span class="sxs-lookup"><span data-stu-id="6e81b-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="6e81b-174">さまざまなサービスに対して行われた呼び出しの完全なシステムテスト。</span><span class="sxs-lookup"><span data-stu-id="6e81b-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="6e81b-175">最終的には、このような課題に対処するためのソリューションがあります。これについては、後で説明するサーバーレスの利点を活用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e81b-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6e81b-176">[前へ](index.md)
>[次へ](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="6e81b-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
