---
title: コンテナー設計の共通原則
description: コンテナーでは 1 つのプロセスのみをホストする必要があるという、適切なコンテナー設計の基本原則について学習します。
ms.date: 02/15/2019
ms.openlocfilehash: 69f3ff6c9303f0c4082695d861a8c90031295b6a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68672499"
---
# <a name="common-container-design-principles"></a><span data-ttu-id="9a441-103">コンテナー設計の共通原則</span><span class="sxs-lookup"><span data-stu-id="9a441-103">Common container design principles</span></span>

<span data-ttu-id="9a441-104">開発プロセスに進む前に、コンテナーの使用方法について言及すべき基本概念がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9a441-104">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="9a441-105">コンテナーはプロセスと等しい</span><span class="sxs-lookup"><span data-stu-id="9a441-105">Container equals a process</span></span>

<span data-ttu-id="9a441-106">コンテナー モデルでは、コンテナーは単一のプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="9a441-106">In the container model, a container represents a single process.</span></span> <span data-ttu-id="9a441-107">コンテナーをプロセス境界として定義することで、プロセスのスケーリング、またはバッチ処理に使用されるプリミティブの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="9a441-107">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="9a441-108">Docker コンテナーを実行すると、[ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) 定義が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a441-108">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="9a441-109">これでプロセスとコンテナーの有効期間が定義されます。</span><span class="sxs-lookup"><span data-stu-id="9a441-109">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="9a441-110">プロセスが完了すると、コンテナーのライフサイクルが終了します。</span><span class="sxs-lookup"><span data-stu-id="9a441-110">When the process completes, the container life-cycle ends.</span></span> <span data-ttu-id="9a441-111">Web サーバーなどの実行時間の長いプロセス、およびバッチ ジョブなどの短期間のプロセスがあります。これらは、Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/) として実装されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a441-111">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="9a441-112">プロセスが失敗した場合、コンテナーが終了し、Orchestrator が引き継ぎます。</span><span class="sxs-lookup"><span data-stu-id="9a441-112">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="9a441-113">オーケストレーターが 5 つのインスタンスの実行を維持するように指示されており、1 つが失敗した場合、オーケストレーターでは、失敗したプロセスを置換する別のコンテナーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9a441-113">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="9a441-114">バッチ ジョブで、プロセスはパラメーターを指定して開始されます。</span><span class="sxs-lookup"><span data-stu-id="9a441-114">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="9a441-115">プロセスが完了すると、作業が完了します。</span><span class="sxs-lookup"><span data-stu-id="9a441-115">When the process completes, the work is complete.</span></span>

<span data-ttu-id="9a441-116">単一のコンテナーで複数のプロセスを実行する必要があるシナリオが見られる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a441-116">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="9a441-117">どのアーキテクチャ ドキュメントでも、絶対に "絶対" は存在せず、また、いつも "いつも" は存在しません。</span><span class="sxs-lookup"><span data-stu-id="9a441-117">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="9a441-118">複数のプロセスを必要とするシナリオの場合、一般的なパターンは[スーパーバイザー](http://supervisord.org/)を使用することです。</span><span class="sxs-lookup"><span data-stu-id="9a441-118">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9a441-119">[前へ](design-docker-applications.md)
>[次へ](monolithic-applications.md)</span><span class="sxs-lookup"><span data-stu-id="9a441-119">[Previous](design-docker-applications.md)
[Next](monolithic-applications.md)</span></span>
