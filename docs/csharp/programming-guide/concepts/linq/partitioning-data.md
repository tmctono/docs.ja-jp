---
title: データのパーティション分割 (C#)
description: LINQ でデータをパーティション分割する方法について説明します。 パーティション分割操作の結果を示す図を確認してください。
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: 3c85eaec2dc01b683234a27714750354982be440
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302608"
---
# <a name="partitioning-data-c"></a><span data-ttu-id="c8ee3-104">データのパーティション分割 (C#)</span><span class="sxs-lookup"><span data-stu-id="c8ee3-104">Partitioning Data (C#)</span></span>
<span data-ttu-id="c8ee3-105">LINQ におけるパーティション分割とは、要素を並べ替えずに入力シーケンスを 2 つのセクションに分割し、それらのセクションの 1 つを返す操作を指します。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-105">Partitioning in LINQ refers to the operation of dividing an input sequence into two sections, without rearranging the elements, and then returning one of the sections.</span></span>  
  
 <span data-ttu-id="c8ee3-106">次の図は、文字のシーケンスに対して 3 つの異なるパーティション分割操作を実行した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-106">The following illustration shows the results of three different partitioning operations on a sequence of characters.</span></span> <span data-ttu-id="c8ee3-107">最初の操作では、シーケンスの最初の 3 つの要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-107">The first operation returns the first three elements in the sequence.</span></span> <span data-ttu-id="c8ee3-108">2 番目の操作では、最初の 3 つの要素がスキップされ、残りの要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-108">The second operation skips the first three elements and returns the remaining elements.</span></span> <span data-ttu-id="c8ee3-109">3 番目の操作では、シーケンスの最初の 2 つの要素がスキップされ、次の 3 つの要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-109">The third operation skips the first two elements in the sequence and returns the next three elements.</span></span>  
  
 ![LINQ のパーティション操作を示す図。](./media/partitioning-data/linq-partitioning-operations.png)  
  
 <span data-ttu-id="c8ee3-111">次のセクションに、シーケンスのパーティション分割を実行する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-111">The standard query operator methods that partition sequences are listed in the following section.</span></span>  
  
## <a name="operators"></a><span data-ttu-id="c8ee3-112">演算子</span><span class="sxs-lookup"><span data-stu-id="c8ee3-112">Operators</span></span>  
  
|<span data-ttu-id="c8ee3-113">演算子名</span><span class="sxs-lookup"><span data-stu-id="c8ee3-113">Operator Name</span></span>|<span data-ttu-id="c8ee3-114">説明</span><span class="sxs-lookup"><span data-stu-id="c8ee3-114">Description</span></span>|<span data-ttu-id="c8ee3-115">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="c8ee3-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="c8ee3-116">説明</span><span class="sxs-lookup"><span data-stu-id="c8ee3-116">More Information</span></span>|  
|-------------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="c8ee3-117">Skip</span><span class="sxs-lookup"><span data-stu-id="c8ee3-117">Skip</span></span>|<span data-ttu-id="c8ee3-118">シーケンス内の指定した位置まで要素をスキップします。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-118">Skips elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="c8ee3-119">該当なし。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c8ee3-120">SkipWhile</span><span class="sxs-lookup"><span data-stu-id="c8ee3-120">SkipWhile</span></span>|<span data-ttu-id="c8ee3-121">述語関数に基づき、条件を満たさない要素が出現する位置まで要素をスキップします。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-121">Skips elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="c8ee3-122">該当なし。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c8ee3-123">Take</span><span class="sxs-lookup"><span data-stu-id="c8ee3-123">Take</span></span>|<span data-ttu-id="c8ee3-124">シーケンス内の指定した位置までの要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-124">Takes elements up to a specified position in a sequence.</span></span>|<span data-ttu-id="c8ee3-125">該当なし。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="c8ee3-126">TakeWhile</span><span class="sxs-lookup"><span data-stu-id="c8ee3-126">TakeWhile</span></span>|<span data-ttu-id="c8ee3-127">述語関数に基づき、条件を満たさない要素が出現する位置までの要素を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-127">Takes elements based on a predicate function until an element does not satisfy the condition.</span></span>|<span data-ttu-id="c8ee3-128">該当なし。</span><span class="sxs-lookup"><span data-stu-id="c8ee3-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="c8ee3-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8ee3-129">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="c8ee3-130">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="c8ee3-130">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
