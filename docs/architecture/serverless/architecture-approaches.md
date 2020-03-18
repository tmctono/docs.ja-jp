---
title: アーキテクチャ アプローチ - サーバーレス アプリ
description: N 層アーキテクチャからサーバーレスへ、クラウドベースのエンタープライズ アプリケーションを構築するためのアーキテクチャのアプローチについて説明します。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522901"
---
# <a name="architecture-approaches"></a><span data-ttu-id="018a8-103">アーキテクチャのアプローチ</span><span class="sxs-lookup"><span data-stu-id="018a8-103">Architecture approaches</span></span>

<span data-ttu-id="018a8-104">エンタープライズ アプリを設計するための既存のアプローチを理解することは、サーバーレスが果たす役割を明らかにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="018a8-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="018a8-105">数十年にわたるソフトウェア開発で進化した多くのアプローチとパターンがあり、それぞれに固有の長所と短所があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="018a8-106">多くの場合、最終的な解決策は 1 つのアプローチに決定することではなく、複数のアプローチを統合することです。</span><span class="sxs-lookup"><span data-stu-id="018a8-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="018a8-107">移行シナリオでは、ハイブリッド アプローチを使用して 1 つのアーキテクチャ アプローチから別のアプローチに切り替えることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="018a8-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="018a8-108">この章では、エンタープライズ アプリケーションの論理アーキテクチャと物理アーキテクチャの両方の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="018a8-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="018a8-109">アーキテクチャのパターン</span><span class="sxs-lookup"><span data-stu-id="018a8-109">Architecture patterns</span></span>

<span data-ttu-id="018a8-110">最新のビジネス アプリケーションは、さまざまなアーキテクチャ パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="018a8-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="018a8-111">このセクションでは、一般的なパターンの調査について説明します。</span><span class="sxs-lookup"><span data-stu-id="018a8-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="018a8-112">ここに記載されているパターンは、必ずしもすべてがベスト プラクティスではありませんが、さまざまなアプローチを示しています。</span><span class="sxs-lookup"><span data-stu-id="018a8-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="018a8-113">詳細については、「[Azure アプリケーション アーキテクチャ ガイド](https://docs.microsoft.com/azure/architecture/guide/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="018a8-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="018a8-114">モノリス</span><span class="sxs-lookup"><span data-stu-id="018a8-114">Monoliths</span></span>

<span data-ttu-id="018a8-115">多くのビジネス アプリケーションは、モノリス パターンに従います。</span><span class="sxs-lookup"><span data-stu-id="018a8-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="018a8-116">レガシ アプリケーションは、多くの場合、モノリスとして実装されています。</span><span class="sxs-lookup"><span data-stu-id="018a8-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="018a8-117">モノリス パターンでは、すべてのアプリケーションの問題が単一の展開に含まれています。</span><span class="sxs-lookup"><span data-stu-id="018a8-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="018a8-118">ユーザー インターフェイスからデータベースの呼び出しまで、すべてが同じコードベースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="018a8-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![モノリス アーキテクチャ](./media/monolith-architecture.png)

<span data-ttu-id="018a8-120">モノリス アプローチにはいくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="018a8-121">多くの場合、単一のコード ベースを開いて作業を開始するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="018a8-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="018a8-122">準備期間は短くなる可能性があり、テスト環境の作成は新しいコピーを提供するのと同じように簡単です。</span><span class="sxs-lookup"><span data-stu-id="018a8-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="018a8-123">モノリスは、複数のコンポーネントとアプリケーションを含むように設計されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="018a8-124">残念ながら、モノリス パターンは大規模に破綻する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="018a8-125">モノリス アプローチの主な欠点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="018a8-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="018a8-126">同じコード ベースで並行して作業することは困難です。</span><span class="sxs-lookup"><span data-stu-id="018a8-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="018a8-127">変更を行った場合、どれだけ些細な変更であったとしても、アプリケーション全体の新しいバージョンを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="018a8-128">リファクタリングを行うと、アプリケーション全体に影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="018a8-129">多くの場合、スケーリングするための唯一の解決策は、リソースを大量に消費するモノリスの複数のコピーを作成することです。</span><span class="sxs-lookup"><span data-stu-id="018a8-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="018a8-130">システムの拡大や他のシステムの獲得に伴い、統合が困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="018a8-131">モノリス全体を構成する必要があるため、テストが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="018a8-132">コードを再利用することは容易でなく、他のアプリで独自のコードのコピーが作成されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="018a8-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="018a8-133">多くの企業は、モノリス アプリケーションを移行すると同時にもっと使いやすいパターンにリファクタリングする機会として、クラウドに注目しています。</span><span class="sxs-lookup"><span data-stu-id="018a8-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="018a8-134">個々のアプリケーションとコンポーネントを分割して個別に管理、展開、およびスケーリングできるようにするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="018a8-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="018a8-135">N 層アプリケーション</span><span class="sxs-lookup"><span data-stu-id="018a8-135">N-Layer applications</span></span>

<span data-ttu-id="018a8-136">N 層アプリケーションでは、アプリケーション ロジックを特定のレイヤーに分割します。</span><span class="sxs-lookup"><span data-stu-id="018a8-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="018a8-137">最も一般的なレイヤーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="018a8-137">The most common layers include:</span></span>

- <span data-ttu-id="018a8-138">ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="018a8-138">User interface</span></span>
- <span data-ttu-id="018a8-139">ビジネス ロジック</span><span class="sxs-lookup"><span data-stu-id="018a8-139">Business logic</span></span>
- <span data-ttu-id="018a8-140">データ アクセス</span><span class="sxs-lookup"><span data-stu-id="018a8-140">Data access</span></span>

<span data-ttu-id="018a8-141">その他のレイヤーには、ミドルウェア、バッチ処理、API などがあります。</span><span class="sxs-lookup"><span data-stu-id="018a8-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="018a8-142">重要なこととして、レイヤーは論理的なものである点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="018a8-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="018a8-143">これらは分離して開発されますが、すべて同じターゲット プラットフォームに展開される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N 層アーキテクチャ](./media/n-layer-architecture.png)

<span data-ttu-id="018a8-145">N 層アプローチには、次のようないくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="018a8-146">リファクタリングはレイヤーに分離されます。</span><span class="sxs-lookup"><span data-stu-id="018a8-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="018a8-147">チームは別々のレイヤーを個別にビルド、テスト、展開、維持できます。</span><span class="sxs-lookup"><span data-stu-id="018a8-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="018a8-148">レイヤーをスワップ アウトすることができます。たとえばデータ レイヤーから、UI レイヤーを変更することなく複数のデータベースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="018a8-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="018a8-149">サーバーレスを使用して 1 つまたは複数のレイヤーを実装できます。</span><span class="sxs-lookup"><span data-stu-id="018a8-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="018a8-150">マイクロサービス</span><span class="sxs-lookup"><span data-stu-id="018a8-150">Microservices</span></span>

<span data-ttu-id="018a8-151">**[マイクロサービス](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** アーキテクチャには、次のような一般的な特性があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="018a8-152">アプリケーションは複数の小さいサービスで構成されています。</span><span class="sxs-lookup"><span data-stu-id="018a8-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="018a8-153">各サービスは独自のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="018a8-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="018a8-154">サービスはビジネス ドメインに合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="018a8-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="018a8-155">サービス間の通信は軽量の API を介して行われ、通常はトランスポートとして HTTP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="018a8-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="018a8-156">サービスは個別に展開およびアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="018a8-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="018a8-157">サービスは 1 つのデータ ストアに依存していません。</span><span class="sxs-lookup"><span data-stu-id="018a8-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="018a8-158">システムはエラーを考慮して設計されており、特定のサービスにエラーが発生した場合でもアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="018a8-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="018a8-159">マイクロサービスは、他のアーキテクチャ アプローチと相互に排他的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="018a8-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="018a8-160">たとえば、N 層アーキテクチャでは、中間層にマイクロサービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="018a8-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="018a8-161">また、IIS ホスト上の仮想ディレクトリからコンテナーまで、さまざまな方法でマイクロサービスを実装することが可能です。</span><span class="sxs-lookup"><span data-stu-id="018a8-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="018a8-162">マイクロサービスの特性は、サーバーレス実装に特に適しています。</span><span class="sxs-lookup"><span data-stu-id="018a8-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![マイクロサービス アーキテクチャ](./media/microservices-architecture.png)

<span data-ttu-id="018a8-164">マイクロサービス アーキテクチャの長所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="018a8-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="018a8-165">リファクタリングは、多くの場合、1 つのサービスに分離されます。</span><span class="sxs-lookup"><span data-stu-id="018a8-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="018a8-166">サービスは互いに独立してアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="018a8-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="018a8-167">回復性と弾力性は、個々のサービスの需要に合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="018a8-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="018a8-168">開発は、異なるチームやプラットフォーム間で並行して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="018a8-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="018a8-169">分離されたサービスの包括的なテストを作成する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="018a8-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="018a8-170">マイクロサービスには、次のような固有の課題があります。</span><span class="sxs-lookup"><span data-stu-id="018a8-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="018a8-171">使用可能なサービスとその呼び出し方法の決定。</span><span class="sxs-lookup"><span data-stu-id="018a8-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="018a8-172">サービスのライフサイクルの管理。</span><span class="sxs-lookup"><span data-stu-id="018a8-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="018a8-173">サービスがアプリケーション全体にどのように適合するかの理解。</span><span class="sxs-lookup"><span data-stu-id="018a8-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="018a8-174">異なるサービス間で行われる呼び出しの完全なシステム テスト。</span><span class="sxs-lookup"><span data-stu-id="018a8-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="018a8-175">最終的には、これらすべての課題に対処するための解決策があります。これには、後で説明するサーバーレスの利点を活用することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="018a8-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="018a8-176">[前へ](index.md)
>[次へ](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="018a8-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
