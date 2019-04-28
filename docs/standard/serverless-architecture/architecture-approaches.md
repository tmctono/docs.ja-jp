---
title: サーバーレス アプリのアーキテクチャ アプローチ
description: アーキテクチャの概要については、サーバーレスに N 層アーキテクチャからのクラウド ベースのエンタープライズ アプリケーションを構築するために近くなります。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 04ad383586f974bb2dccc4623a9a254f5668dab4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640199"
---
# <a name="architecture-approaches"></a><span data-ttu-id="f0eae-103">アーキテクチャのアプローチ</span><span class="sxs-lookup"><span data-stu-id="f0eae-103">Architecture approaches</span></span>

<span data-ttu-id="f0eae-104">エンタープライズアプリケーションを設計するために既存のアプローチを理解することは、サーバレスで果たす役割を明確にするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="f0eae-105">ソフトウェア開発は何十年にも渡って進化を遂げた多くのアプローチとパターンがあり、すべてがそれぞれ長所と短所を持っています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="f0eae-106">多くの場合、究極のソリューションは、単一のアプローチを決定するのではなく、いくつかのアプローチを統合することになるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="f0eae-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="f0eae-107">移行シナリオでは、あるアーキテクチャのアプローチから、ハイブリッドなアーキテクチャーのアプローチへのシフトすることがしばしばあります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="f0eae-108">この章では、エンタープライズアプリケーションの論理アーキテクチャ パターンと物理アーキテクチャ パターンの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="f0eae-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="f0eae-109">アーキテクチャーパターン</span><span class="sxs-lookup"><span data-stu-id="f0eae-109">Architecture patterns</span></span>

<span data-ttu-id="f0eae-110">最新のビジネスアプリケーションは、さまざまなアーキテクチャーパターンに従っています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="f0eae-111">このセクションでは、一般的なパターンの調査を表します。</span><span class="sxs-lookup"><span data-stu-id="f0eae-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="f0eae-112">ここで示したパターンでは、必ずしもすべてのベストプラクティスはありませんが、さまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="f0eae-113">詳細については、次を参照してください。 [Azure アプリケーション アーキテクチャ ガイド](https://docs.microsoft.com/azure/architecture/guide/)します。</span><span class="sxs-lookup"><span data-stu-id="f0eae-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="f0eae-114">モノリス</span><span class="sxs-lookup"><span data-stu-id="f0eae-114">Monoliths</span></span>

<span data-ttu-id="f0eae-115">多くのビジネスアプリケーションは、モノリスパターンに従っています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="f0eae-116">レガシーアプリケーションは、モノリスに実装されていることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="f0eae-117">モノリスパターンでは、アプリケーションが1つのデプロイに含まれていることが問題です。</span><span class="sxs-lookup"><span data-stu-id="f0eae-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="f0eae-118">データベースの呼び出しからユーザーインターフェースまですべてが、同じコードベースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![モノリシック アーキテクチャ](./media/monolith-architecture.png)

<span data-ttu-id="f0eae-120">モノリスのアプローチにもいくつかの利点はあります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="f0eae-121">1つのコードベースをプルして作業を開始するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="f0eae-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="f0eae-122">構築時間は短縮され、テスト環境の作成は新しいコピーを提供するのと同じくらいシンプルです。</span><span class="sxs-lookup"><span data-stu-id="f0eae-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="f0eae-123">モノリスは、複数のコンポーネントまたはアプリケーションを含むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="f0eae-124">残念なことに、モノリスパターンはスケールで破綻する傾向があります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="f0eae-125">モノリスのアプローチの主な欠点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0eae-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="f0eae-126">同じコードベースで並列して作業するのは困難</span><span class="sxs-lookup"><span data-stu-id="f0eae-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="f0eae-127">どんな些細な変更でも、アプリケーション全体を新しいバージョンにデプロイする必要がある</span><span class="sxs-lookup"><span data-stu-id="f0eae-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="f0eae-128">リファクタリングは、潜在的にアプリケーション全体に影響を及ぼす</span><span class="sxs-lookup"><span data-stu-id="f0eae-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="f0eae-129">多くの場合、スケールする唯一のソリューションは、リソースが集約されたモノリスのコピーを複数作ることです。</span><span class="sxs-lookup"><span data-stu-id="f0eae-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="f0eae-130">システムの拡張や他システムとの結合といったインテグレーションは難しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="f0eae-131">テストは、モノリス全体の構成をする必要があるため難しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="f0eae-132">コードの再利用は困難であり、多くの場合、他のアプリは元のコードのコピーを持つことになります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="f0eae-133">多くの企業は、モノリスのアプリケーションを移行する機会としてクラウドに注目し、同時により有用なパターンにリファクタリングします。</span><span class="sxs-lookup"><span data-stu-id="f0eae-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="f0eae-134">個々のアプリケーションやコンポーネントを切り離して、個別に保守、デプロイ、およびスケーリングできるようにするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="f0eae-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="f0eae-135">N層アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f0eae-135">N-Layer applications</span></span>

<span data-ttu-id="f0eae-136">N層アプリケーションは、アプリケーションのロジックを特定のレイヤーに分けます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="f0eae-137">最も一般的なレイヤーは次の通りです。</span><span class="sxs-lookup"><span data-stu-id="f0eae-137">The most common layers include:</span></span>

* <span data-ttu-id="f0eae-138">ユーザーインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f0eae-138">User interface</span></span>
* <span data-ttu-id="f0eae-139">ビジネスロジック</span><span class="sxs-lookup"><span data-stu-id="f0eae-139">Business logic</span></span>
* <span data-ttu-id="f0eae-140">データアクセス</span><span class="sxs-lookup"><span data-stu-id="f0eae-140">Data access</span></span>

<span data-ttu-id="f0eae-141">他の層には、ミドルウェア、バッチ処理、および API が含まれるでしょう。</span><span class="sxs-lookup"><span data-stu-id="f0eae-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="f0eae-142">レイヤーは論理的であることに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f0eae-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="f0eae-143">それらは独立して開発されますが、すべて同じターゲットプラットフォームに展開されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N 層アーキテクチャ](./media/n-layer-architecture.png)

<span data-ttu-id="f0eae-145">N層のアプローチには、次のようないくつかの利点があります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="f0eae-146">リファクタリングは、レイヤーで分離されます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="f0eae-147">チームは、分離しているレイヤー個々に、ビルド、テスト、デプロイ、および保守することができます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="f0eae-148">レイヤーをスワップすることができます。例えば、データレイヤーは、UIレイヤーを変更することなく、複数のデータベースにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="f0eae-149">サーバーレスは、1つまたは複数のレイヤーを実装できます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="f0eae-150">マイクロサービス</span><span class="sxs-lookup"><span data-stu-id="f0eae-150">Microservices</span></span>

<span data-ttu-id="f0eae-151">**[マイクロ サービス](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** アーキテクチャは、次のような一般的な特徴があります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="f0eae-152">アプリケーションはいくつかの小さなサービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="f0eae-153">各サービスは独自のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="f0eae-154">各サービスはビジネスドメインを中心に配置されます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="f0eae-155">各サービスは軽量の API を介して通信されます。トランスポートとして HTTP がよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="f0eae-156">各サービスは個別にデプロイおよびアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="f0eae-157">各サービスが単一のデータストアには依存しません。</span><span class="sxs-lookup"><span data-stu-id="f0eae-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="f0eae-158">システムはエラーを考慮して設計されており、特定のサービスに失敗しても、そのアプリは動作するようになっています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="f0eae-159">マイクロサービスは、他のアーキテクチャのアプローチと相互に排他的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f0eae-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="f0eae-160">例えばN層アーキテクチャでは、中間層にマイクロサービスを利用することができます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="f0eae-161">IIS ホスト上の仮想ディレクトリからコンテナーまで、様々な方法でマイクロサービスの実装が可能です。</span><span class="sxs-lookup"><span data-stu-id="f0eae-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="f0eae-162">マイクロサービスの特性は、サーバーレス実装に特に適しています。</span><span class="sxs-lookup"><span data-stu-id="f0eae-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![マイクロサービス アーキテクチャ](./media/microservices-architecture.png)

<span data-ttu-id="f0eae-164">マイクロサービス アーキテクチャの利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0eae-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="f0eae-165">リファクタリングは、単一のサービスごとに分離できます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="f0eae-166">各サービスは互いに独立してアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="f0eae-167">回復性と弾力性は、各サービスの要求に合わせて調整することができます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="f0eae-168">開発は、異なるチームや異なるプラットフォーム間で並行して行われます。</span><span class="sxs-lookup"><span data-stu-id="f0eae-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="f0eae-169">サービスが分離されていることで、包括的なテストの記述が容易です。</span><span class="sxs-lookup"><span data-stu-id="f0eae-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="f0eae-170">マイクロサービスには、以下のような課題があります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="f0eae-171">利用可能なサービスとその呼び出し方法の決定</span><span class="sxs-lookup"><span data-stu-id="f0eae-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="f0eae-172">各サービスのライフサイクルの管理</span><span class="sxs-lookup"><span data-stu-id="f0eae-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="f0eae-173">各サービスがどのようにアプリケーション全体にフィットするかの理解</span><span class="sxs-lookup"><span data-stu-id="f0eae-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="f0eae-174">異なるサービス間で行われた呼び出しの完全なシステムテスト</span><span class="sxs-lookup"><span data-stu-id="f0eae-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="f0eae-175">最終的には、後述するサーバーレスの利点を活用するなど、これらすべての課題に対処するためのソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="f0eae-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f0eae-176">[前へ](index.md)
>[次へ](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="f0eae-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>