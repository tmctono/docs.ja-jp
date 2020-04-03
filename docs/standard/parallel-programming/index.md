---
title: .NET での並列プログラミング
ms.date: 09/12/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
ms.openlocfilehash: 75f5ded48acfb82b0327ead3880ee23e6ef4bc2f
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588148"
---
# <a name="parallel-programming-in-net"></a><span data-ttu-id="1ff7d-102">.NET での並列プログラミング</span><span class="sxs-lookup"><span data-stu-id="1ff7d-102">Parallel Programming in .NET</span></span>

<span data-ttu-id="1ff7d-103">多くのパーソナル コンピューターとワークステーションには、複数スレッドの同時実行を可能にする複数の CPU コアがあります。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-103">Many personal computers and workstations have multiple CPU cores that enable multiple threads to be executed simultaneously.</span></span> <span data-ttu-id="1ff7d-104">ハードウェアを活用するには、コードを並列化して複数のプロセッサに負荷を分散します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-104">To take advantage of the hardware, you can parallelize your code to distribute work across multiple processors.</span></span>

<span data-ttu-id="1ff7d-105">以前は、並列化には低水準のスレッドおよびロックの操作が必要でした。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-105">In the past, parallelization required low-level manipulation of threads and locks.</span></span> <span data-ttu-id="1ff7d-106">Visual Studio と .NET Framework では、ランタイム、クラス ライブラリの型、および診断ツールを提供することで、並列プログラミングのサポートを強化しています。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-106">Visual Studio and the .NET Framework enhance support for parallel programming by providing a runtime, class library types, and diagnostic tools.</span></span> <span data-ttu-id="1ff7d-107">.NET Framework 4 で導入されたこれらの機能によって、並行開発が簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-107">These features, which were introduced with the .NET Framework 4, simplify parallel development.</span></span> <span data-ttu-id="1ff7d-108">スレッドやスレッド プールを直接操作することなく、効率的で詳細な、拡張性のある並列コードを自然な表現方法で記述できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-108">You can write efficient, fine-grained, and scalable parallel code in a natural idiom without having to work directly with threads or the thread pool.</span></span>

<span data-ttu-id="1ff7d-109">.NET Framework の並列プログラミング アーキテクチャの高度な概要を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-109">The following illustration provides a high-level overview of the parallel programming architecture in the .NET Framework:</span></span>

![.NET 並列プログラミング アーキテクチャ](./media/tpl-architecture.png)

## <a name="related-topics"></a><span data-ttu-id="1ff7d-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1ff7d-111">Related Topics</span></span>

|<span data-ttu-id="1ff7d-112">テクノロジ</span><span class="sxs-lookup"><span data-stu-id="1ff7d-112">Technology</span></span>|<span data-ttu-id="1ff7d-113">説明</span><span class="sxs-lookup"><span data-stu-id="1ff7d-113">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="1ff7d-114">タスク並列ライブラリ (TPL)</span><span class="sxs-lookup"><span data-stu-id="1ff7d-114">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|<span data-ttu-id="1ff7d-115">並列バージョンの <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> ループおよび `For` ループを含む `ForEach` クラスに関するドキュメントと、非同期操作の推奨される表現方法を表す <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> クラスに関するドキュメントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-115">Provides documentation for the <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> class, which includes parallel versions of `For` and `ForEach` loops, and also for the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class, which represents the preferred way to express asynchronous operations.</span></span>|
|[<span data-ttu-id="1ff7d-116">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="1ff7d-116">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)|<span data-ttu-id="1ff7d-117">さまざまなシナリオでパフォーマンスを大幅に向上させる、LINQ to Objects の並列実装です。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-117">A parallel implementation of LINQ to Objects that significantly improves performance in many scenarios.</span></span>|
|[<span data-ttu-id="1ff7d-118">並列プログラミングのデータ構造</span><span class="sxs-lookup"><span data-stu-id="1ff7d-118">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|<span data-ttu-id="1ff7d-119">スレッド セーフなコレクション クラス、軽量な同期型、および限定的な初期化の種類に関するドキュメントへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-119">Provides links to documentation for thread-safe collection classes, lightweight synchronization types, and types for lazy initialization.</span></span>|
|[<span data-ttu-id="1ff7d-120">並列診断ツール</span><span class="sxs-lookup"><span data-stu-id="1ff7d-120">Parallel Diagnostic Tools</span></span>](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|<span data-ttu-id="1ff7d-121">タスクと並列スタック向けの Visual Studio デバッガー ウィンドウ、および[コンカレンシー ビジュアライザー](/visualstudio/profiling/concurrency-visualizer)に関するドキュメントへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-121">Provides links to documentation for Visual Studio debugger windows for tasks and parallel stacks, and for the [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>|
|[<span data-ttu-id="1ff7d-122">PLINQ および TPL 用のカスタム パーティショナー</span><span class="sxs-lookup"><span data-stu-id="1ff7d-122">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|<span data-ttu-id="1ff7d-123">パーティションのしくみと、既定のパーティションの設定方法または新しいパーティションの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-123">Describes how partitioners work and how to configure the default partitioners or create a new partitioner.</span></span>|
|[<span data-ttu-id="1ff7d-124">タスク スケジューラ</span><span class="sxs-lookup"><span data-stu-id="1ff7d-124">Task Schedulers</span></span>](xref:System.Threading.Tasks.TaskScheduler)|<span data-ttu-id="1ff7d-125">スケジューラのしくみと既定のスケジューラの構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-125">Describes how schedulers work and how the default schedulers may be configured.</span></span>|
|[<span data-ttu-id="1ff7d-126">PLINQ および TPL のラムダ式</span><span class="sxs-lookup"><span data-stu-id="1ff7d-126">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|<span data-ttu-id="1ff7d-127">C# および Visual Basic のラムダ式について簡単に説明し、PLINQ およびタスク並列ライブラリでラムダ式を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-127">Provides a brief overview of lambda expressions in C# and Visual Basic, and shows how they are used in PLINQ and the Task Parallel Library.</span></span>|
|[<span data-ttu-id="1ff7d-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ff7d-128">For Further Reading</span></span>](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|<span data-ttu-id="1ff7d-129">.NET での並列プログラミングに関する追加の情報とサンプル リソースへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="1ff7d-129">Provides links to additional information and sample resources for parallel programming in .NET.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1ff7d-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ff7d-130">See also</span></span>

- [<span data-ttu-id="1ff7d-131">非同期の概要</span><span class="sxs-lookup"><span data-stu-id="1ff7d-131">Async Overview</span></span>](../async.md)
- [<span data-ttu-id="1ff7d-132">マネージド スレッド処理</span><span class="sxs-lookup"><span data-stu-id="1ff7d-132">Managed Threading</span></span>](../threading/index.md)
