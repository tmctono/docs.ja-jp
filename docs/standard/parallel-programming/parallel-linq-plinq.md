---
title: Parallel LINQ (PLINQ)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ, overview
ms.assetid: 3d4d0cd3-bde4-490b-99e7-f4e41be96455
ms.openlocfilehash: 1ea880c6403a5fc8b26ba67fe21dfce79c4683db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140040"
---
# <a name="parallel-linq-plinq"></a><span data-ttu-id="24817-102">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="24817-102">Parallel LINQ (PLINQ)</span></span>
<span data-ttu-id="24817-103">Parallel LINQ (PLINQ) は、LINQ to Objects の並列実装です。</span><span class="sxs-lookup"><span data-stu-id="24817-103">Parallel LINQ (PLINQ) is a parallel implementation of LINQ to Objects.</span></span> <span data-ttu-id="24817-104">PLINQ は、LINQ 標準クエリ演算子の完全なセットを <xref:System.Linq> 名前空間の拡張メソッドとして実装し、並列操作用の追加演算子も備えています。</span><span class="sxs-lookup"><span data-stu-id="24817-104">PLINQ implements the full set of LINQ standard query operators as extension methods for the <xref:System.Linq> namespace and has additional operators for parallel operations.</span></span> <span data-ttu-id="24817-105">PLINQ は、LINQ 構文の単純さと読みやすさに加え、並列プログラミングのパワーを兼ね備えています。</span><span class="sxs-lookup"><span data-stu-id="24817-105">PLINQ combines the simplicity and readability of LINQ syntax with the power of parallel programming.</span></span> <span data-ttu-id="24817-106">タスク並列ライブラリを対象とするコードと同じように、PLINQ クエリのコンカレンシーの程度は、ホスト コンピューターの能力に基づいて調整されます。</span><span class="sxs-lookup"><span data-stu-id="24817-106">Just like code that targets the Task Parallel Library, PLINQ queries scale in the degree of concurrency based on the capabilities of the host computer.</span></span>  
  
 <span data-ttu-id="24817-107">多くのシナリオで、PLINQ は、ホスト コンピューターで使用可能なすべてのコアをより効率的に使用することで、LINQ to Objects クエリの速度を大幅に上昇させることができます。</span><span class="sxs-lookup"><span data-stu-id="24817-107">In many scenarios, PLINQ can significantly increase the speed of LINQ to Objects queries by using all available cores on the host computer more efficiently.</span></span> <span data-ttu-id="24817-108">このパフォーマンスの向上によって、デスクトップに高パフォーマンスの演算能力がもたらされます。</span><span class="sxs-lookup"><span data-stu-id="24817-108">This increased performance brings high-performance computing power onto the desktop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24817-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="24817-109">In This Section</span></span>  
 [<span data-ttu-id="24817-110">PLINQ の概要</span><span class="sxs-lookup"><span data-stu-id="24817-110">Introduction to PLINQ</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)  
  
 [<span data-ttu-id="24817-111">PLINQ での高速化について</span><span class="sxs-lookup"><span data-stu-id="24817-111">Understanding Speedup in PLINQ</span></span>](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)  
  
 [<span data-ttu-id="24817-112">PLINQ における順序維持</span><span class="sxs-lookup"><span data-stu-id="24817-112">Order Preservation in PLINQ</span></span>](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)  
  
 [<span data-ttu-id="24817-113">PLINQ のマージ オプション</span><span class="sxs-lookup"><span data-stu-id="24817-113">Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)  
  
 [<span data-ttu-id="24817-114">方法: 単純な PLINQ クエリを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="24817-114">How to: Create and Execute a Simple PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-create-and-execute-a-simple-plinq-query.md)  
  
 [<span data-ttu-id="24817-115">方法: PLINQ クエリの順序を制御する</span><span class="sxs-lookup"><span data-stu-id="24817-115">How to: Control Ordering in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)  
  
 [<span data-ttu-id="24817-116">方法: 並列および順次の LINQ クエリを連結する</span><span class="sxs-lookup"><span data-stu-id="24817-116">How to: Combine Parallel and Sequential LINQ Queries</span></span>](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)  
  
 [<span data-ttu-id="24817-117">方法: PLINQ クエリの例外を処理する</span><span class="sxs-lookup"><span data-stu-id="24817-117">How to: Handle Exceptions in a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)  
  
 [<span data-ttu-id="24817-118">方法: PLINQ クエリを取り消す</span><span class="sxs-lookup"><span data-stu-id="24817-118">How to: Cancel a PLINQ Query</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)  
  
 [<span data-ttu-id="24817-119">方法: カスタムの PLINQ 集約関数を記述する</span><span class="sxs-lookup"><span data-stu-id="24817-119">How to: Write a Custom PLINQ Aggregate Function</span></span>](../../../docs/standard/parallel-programming/how-to-write-a-custom-plinq-aggregate-function.md)  
  
 [<span data-ttu-id="24817-120">方法: PLINQ の実行モードを指定する</span><span class="sxs-lookup"><span data-stu-id="24817-120">How to: Specify the Execution Mode in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)  
  
 [<span data-ttu-id="24817-121">方法: PLINQ のマージ オプションを指定する</span><span class="sxs-lookup"><span data-stu-id="24817-121">How to: Specify Merge Options in PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)  
  
 [<span data-ttu-id="24817-122">方法: PLINQ を使用してファイル ディレクトリを反復処理する</span><span class="sxs-lookup"><span data-stu-id="24817-122">How to: Iterate File Directories with PLINQ</span></span>](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-plinq.md)  
  
 [<span data-ttu-id="24817-123">方法: PLINQ クエリのパフォーマンスを測定する</span><span class="sxs-lookup"><span data-stu-id="24817-123">How to: Measure PLINQ Query Performance</span></span>](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)  
  
 [<span data-ttu-id="24817-124">PLINQ データのサンプル</span><span class="sxs-lookup"><span data-stu-id="24817-124">PLINQ Data Sample</span></span>](../../../docs/standard/parallel-programming/plinq-data-sample.md)  
  
## <a name="see-also"></a><span data-ttu-id="24817-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="24817-125">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="24817-126">並列プログラミング</span><span class="sxs-lookup"><span data-stu-id="24817-126">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="24817-127">統合言語クエリ (LINQ) - C#</span><span class="sxs-lookup"><span data-stu-id="24817-127">Language-Integrated Query (LINQ) - C#</span></span>](../../csharp/programming-guide/concepts/linq/index.md)  
- [<span data-ttu-id="24817-128">統合言語クエリ (LINQ) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24817-128">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../visual-basic/programming-guide/concepts/linq/index.md)  
