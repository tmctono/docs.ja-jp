---
title: 集計操作 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 72268e27fdf6d573279e98438fd884a076e0c8a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669024"
---
# <a name="aggregation-operations-visual-basic"></a><span data-ttu-id="0d728-102">集計操作 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d728-102">Aggregation Operations (Visual Basic)</span></span>
<span data-ttu-id="0d728-103">集計の操作では、値の集合体から単一の値が計算されます。</span><span class="sxs-lookup"><span data-stu-id="0d728-103">An aggregation operation computes a single value from a collection of values.</span></span> <span data-ttu-id="0d728-104">たとえば、1 か月分の毎日の気温値から 1 日あたりの平均の気温値を計算することが集計操作です。</span><span class="sxs-lookup"><span data-stu-id="0d728-104">An example of an aggregation operation is calculating the average daily temperature from a month's worth of daily temperature values.</span></span>  
  
 <span data-ttu-id="0d728-105">次の図は、数値のシーケンスに対する 2 つの集計処理の結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="0d728-105">The following illustration shows the results of two different aggregation operations on a sequence of numbers.</span></span> <span data-ttu-id="0d728-106">最初の処理で数値が合計されます。</span><span class="sxs-lookup"><span data-stu-id="0d728-106">The first operation sums the numbers.</span></span> <span data-ttu-id="0d728-107">2 つ目の処理でシーケンスの最大値が返されます。</span><span class="sxs-lookup"><span data-stu-id="0d728-107">The second operation returns the maximum value in the sequence.</span></span>  
  
 ![LINQ 集計操作を示す図。](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 <span data-ttu-id="0d728-109">次のセクションでは、集計処理を実行する標準クエリ演算子メソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="0d728-109">The standard query operator methods that perform aggregation operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d728-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="0d728-110">Methods</span></span>  
  
|<span data-ttu-id="0d728-111">メソッド名</span><span class="sxs-lookup"><span data-stu-id="0d728-111">Method Name</span></span>|<span data-ttu-id="0d728-112">説明</span><span class="sxs-lookup"><span data-stu-id="0d728-112">Description</span></span>|<span data-ttu-id="0d728-113">Visual Basic のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="0d728-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="0d728-114">説明</span><span class="sxs-lookup"><span data-stu-id="0d728-114">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="0d728-115">Aggregate</span><span class="sxs-lookup"><span data-stu-id="0d728-115">Aggregate</span></span>|<span data-ttu-id="0d728-116">コレクションの値に対してカスタム集計処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d728-116">Performs a custom aggregation operation on the values of a collection.</span></span>|<span data-ttu-id="0d728-117">該当なし。</span><span class="sxs-lookup"><span data-stu-id="0d728-117">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0d728-118">平均</span><span class="sxs-lookup"><span data-stu-id="0d728-118">Average</span></span>|<span data-ttu-id="0d728-119">値のコレクションの平均値を計算します。</span><span class="sxs-lookup"><span data-stu-id="0d728-119">Calculates the average value of a collection of values.</span></span>|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0d728-120">カウント</span><span class="sxs-lookup"><span data-stu-id="0d728-120">Count</span></span>|<span data-ttu-id="0d728-121">コレクションの要素数をカウントします。述語関数を満たす要素のみをカウントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d728-121">Counts the elements in a collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0d728-122">LongCount</span><span class="sxs-lookup"><span data-stu-id="0d728-122">LongCount</span></span>|<span data-ttu-id="0d728-123">大規模なコレクションの要素数をカウントします。述語関数を満たす要素のみをカウントすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d728-123">Counts the elements in a large collection, optionally only those elements that satisfy a predicate function.</span></span>|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0d728-124">最大</span><span class="sxs-lookup"><span data-stu-id="0d728-124">Max</span></span>|<span data-ttu-id="0d728-125">コレクション内の最大値を決定します。</span><span class="sxs-lookup"><span data-stu-id="0d728-125">Determines the maximum value in a collection.</span></span>|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0d728-126">最小</span><span class="sxs-lookup"><span data-stu-id="0d728-126">Min</span></span>|<span data-ttu-id="0d728-127">コレクション内の最小値を決定します。</span><span class="sxs-lookup"><span data-stu-id="0d728-127">Determines the minimum value in a collection.</span></span>|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="0d728-128">Sum</span><span class="sxs-lookup"><span data-stu-id="0d728-128">Sum</span></span>|<span data-ttu-id="0d728-129">コレクション内にある値の合計を計算します。</span><span class="sxs-lookup"><span data-stu-id="0d728-129">Calculates the sum of the values in a collection.</span></span>|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="0d728-130">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="0d728-130">Query Expression Syntax Examples</span></span>  
  
### <a name="average"></a><span data-ttu-id="0d728-131">平均</span><span class="sxs-lookup"><span data-stu-id="0d728-131">Average</span></span>  
 <span data-ttu-id="0d728-132">次のコード例では、`Aggregate Into Average`温度を表す数値の配列の平均温度を計算する Visual Basic での句。</span><span class="sxs-lookup"><span data-stu-id="0d728-132">The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a><span data-ttu-id="0d728-133">カウント</span><span class="sxs-lookup"><span data-stu-id="0d728-133">Count</span></span>  
 <span data-ttu-id="0d728-134">次のコード例では、 `Aggregate Into Count` 80 以上である、配列の値の数をカウントする Visual Basic での句。</span><span class="sxs-lookup"><span data-stu-id="0d728-134">The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.</span></span>  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a><span data-ttu-id="0d728-135">LongCount</span><span class="sxs-lookup"><span data-stu-id="0d728-135">LongCount</span></span>  
 <span data-ttu-id="0d728-136">次のコード例では、`Aggregate Into LongCount`句は、配列の値の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="0d728-136">The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.</span></span>  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a><span data-ttu-id="0d728-137">最大</span><span class="sxs-lookup"><span data-stu-id="0d728-137">Max</span></span>  
 <span data-ttu-id="0d728-138">次のコード例では、`Aggregate Into Max`温度を表す数値の配列の最大の温度を計算する句。</span><span class="sxs-lookup"><span data-stu-id="0d728-138">The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a><span data-ttu-id="0d728-139">最小</span><span class="sxs-lookup"><span data-stu-id="0d728-139">Min</span></span>  
 <span data-ttu-id="0d728-140">次のコード例では、`Aggregate Into Min`温度を表す数値の配列の最小の温度を計算する句。</span><span class="sxs-lookup"><span data-stu-id="0d728-140">The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.</span></span>  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a><span data-ttu-id="0d728-141">Sum</span><span class="sxs-lookup"><span data-stu-id="0d728-141">Sum</span></span>  
 <span data-ttu-id="0d728-142">次のコード例では、`Aggregate Into Sum`経費を表す値の配列から経費合計金額を計算する句。</span><span class="sxs-lookup"><span data-stu-id="0d728-142">The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.</span></span>  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0d728-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d728-143">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="0d728-144">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d728-144">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0d728-145">Aggregate 句</span><span class="sxs-lookup"><span data-stu-id="0d728-145">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="0d728-146">方法: CSV テキスト ファイル (LINQ) (Visual Basic) で列の値を計算します。</span><span class="sxs-lookup"><span data-stu-id="0d728-146">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [<span data-ttu-id="0d728-147">方法: 数、合計、または平均データ</span><span class="sxs-lookup"><span data-stu-id="0d728-147">How to: Count, Sum, or Average Data</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [<span data-ttu-id="0d728-148">方法: クエリ結果内の最小値と最大値を検索します。</span><span class="sxs-lookup"><span data-stu-id="0d728-148">How to: Find the Minimum or Maximum Value in a Query Result</span></span>](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [<span data-ttu-id="0d728-149">方法: 最大ファイルまたはディレクトリ ツリー (LINQ) (Visual Basic) 内のファイルのクエリ</span><span class="sxs-lookup"><span data-stu-id="0d728-149">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [<span data-ttu-id="0d728-150">方法: 一連のフォルダー (LINQ) (Visual Basic) のバイト数の合計数をクエリ</span><span class="sxs-lookup"><span data-stu-id="0d728-150">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
