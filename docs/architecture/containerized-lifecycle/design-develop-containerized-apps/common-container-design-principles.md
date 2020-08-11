---
title: コンテナー設計の共通原則
description: コンテナーでは 1 つのプロセスのみをホストする必要があるという、適切なコンテナー設計の基本原則について学習します。
ms.date: 08/06/2020
ms.openlocfilehash: 7dcf4b4af3385a2a500c5bc16a889b56fa2c25d5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916004"
---
# <a name="common-container-design-principles"></a><span data-ttu-id="a1703-103">コンテナー設計の共通原則</span><span class="sxs-lookup"><span data-stu-id="a1703-103">Common container design principles</span></span>

<span data-ttu-id="a1703-104">開発プロセスに進む前に、コンテナーの使用方法について言及すべき基本概念がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a1703-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="a1703-105">コンテナーはプロセスと等しい</span><span class="sxs-lookup"><span data-stu-id="a1703-105">Container equals a process</span></span>

<span data-ttu-id="a1703-106">コンテナー モデルでは、コンテナーは単一のプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="a1703-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="a1703-107">コンテナーをプロセス境界として定義することで、プロセスのスケーリング、またはバッチ処理に使用されるプリミティブの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="a1703-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="a1703-108">Docker コンテナーを実行すると、[ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#entrypoint) 定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1703-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#entrypoint) definition.</span></span> <span data-ttu-id="a1703-109">これでプロセスとコンテナーの有効期間が定義されます。</span><span class="sxs-lookup"><span data-stu-id="a1703-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="a1703-110">プロセスが完了すると、コンテナーのライフサイクルが終了します。</span><span class="sxs-lookup"><span data-stu-id="a1703-110">When the process completes, the container life-cycle ends.</span></span> <span data-ttu-id="a1703-111">Web サーバーなどの実行時間の長いプロセス、およびバッチ ジョブなどの短期間のプロセスがあります。これらは、Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/) として実装されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1703-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="a1703-112">プロセスが失敗した場合、コンテナーが終了し、Orchestrator が引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="a1703-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="a1703-113">オーケストレーターが 5 つのインスタンスの実行を維持するように指示されており、1 つが失敗した場合、オーケストレーターでは、失敗したプロセスを置換する別のコンテナーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a1703-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="a1703-114">バッチ ジョブで、プロセスはパラメーターを指定して開始されます。</span><span class="sxs-lookup"><span data-stu-id="a1703-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="a1703-115">プロセスが完了すると、作業が完了します。</span><span class="sxs-lookup"><span data-stu-id="a1703-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="a1703-116">単一のコンテナーで複数のプロセスを実行する必要があるシナリオが見られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1703-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="a1703-117">どのアーキテクチャ ドキュメントでも、絶対に "絶対" は存在せず、また、いつも "いつも" は存在しません。</span><span class="sxs-lookup"><span data-stu-id="a1703-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="a1703-118">複数のプロセスを必要とするシナリオの場合、一般的なパターンは[スーパーバイザー](http://supervisord.org/)を使用することです。</span><span class="sxs-lookup"><span data-stu-id="a1703-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a1703-119">[前へ](design-docker-applications.md)
>[次へ](monolithic-applications.md)</span><span class="sxs-lookup"><span data-stu-id="a1703-119">[Previous](design-docker-applications.md)
[Next](monolithic-applications.md)</span></span>
