---
title: 標準クエリ演算子の変換
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: af22b6a895fef8037eb5c069ffb7cb23d1333531
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833678"
---
# <a name="standard-query-operator-translation"></a><span data-ttu-id="0ab8b-102">標準クエリ演算子の変換</span><span class="sxs-lookup"><span data-stu-id="0ab8b-102">Standard Query Operator Translation</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-103">では、標準クエリ演算子から SQL コマンドへの変換が行われます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-103">translates Standard Query Operators to SQL commands.</span></span> <span data-ttu-id="0ab8b-104">データベースのクエリプロセッサによって、SQL 変換の実行セマンティクスが決まります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-104">The query processor of the database determines the execution semantics of SQL translation.</span></span>

<span data-ttu-id="0ab8b-105">標準クエリ演算子は、*シーケンス*に対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-105">Standard Query Operators are defined against *sequences*.</span></span> <span data-ttu-id="0ab8b-106">シーケンスは順序*付け*られ、シーケンスの各要素の参照 id に依存します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-106">A sequence is *ordered* and relies on reference identity for each element of the sequence.</span></span> <span data-ttu-id="0ab8b-107">詳細については、「[標準クエリ演算子C#の概要」 ()](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)または「[標準クエリ演算子の概要 (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-107">For more information, see [Standard Query Operators Overview (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>

<span data-ttu-id="0ab8b-108">SQL は主に、順序付けられていない*値のセット*を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-108">SQL deals primarily with *unordered sets of values*.</span></span> <span data-ttu-id="0ab8b-109">通常、順序付けは、明示的な後処理の操作として、クエリの中間結果ではなく最終結果に対して適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-109">Ordering is typically an explicitly stated, post-processing operation that is applied to the final result of a query rather than to intermediate results.</span></span> <span data-ttu-id="0ab8b-110">ID は値で定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-110">Identity is defined by values.</span></span> <span data-ttu-id="0ab8b-111">このため、SQL クエリは、*セット*ではなくマルチセット (*バッグ*) を処理することを理解しています。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-111">For this reason, SQL queries are understood to deal with multisets (*bags*) instead of *sets*.</span></span>

<span data-ttu-id="0ab8b-112">以下、標準クエリ演算子とその SQL 変換との違いを、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 用 SQL Server プロバイダーの場合について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-112">The following paragraphs describe the differences between the Standard Query Operators and their SQL translation for the SQL Server provider for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

## <a name="operator-support"></a><span data-ttu-id="0ab8b-113">演算子のサポート</span><span class="sxs-lookup"><span data-stu-id="0ab8b-113">Operator Support</span></span>

### <a name="concat"></a><span data-ttu-id="0ab8b-114">Concat</span><span class="sxs-lookup"><span data-stu-id="0ab8b-114">Concat</span></span>

<span data-ttu-id="0ab8b-115"><xref:System.Linq.Enumerable.Concat%2A> メソッドは、受信側と引数の順序が同じである、順序付けされたマルチセットに対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-115">The <xref:System.Linq.Enumerable.Concat%2A> method is defined for ordered multisets where the order of the receiver and the order of the argument are the same.</span></span> <span data-ttu-id="0ab8b-116"><xref:System.Linq.Enumerable.Concat%2A> は、共通の順序に従ったマルチセットに対する `UNION ALL` として機能します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-116"><xref:System.Linq.Enumerable.Concat%2A> works as `UNION ALL` over the multisets followed by the common order.</span></span>

<span data-ttu-id="0ab8b-117">最後の手順は、結果を生成する前の SQL での順序付けです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-117">The final step is ordering in SQL before results are produced.</span></span> <span data-ttu-id="0ab8b-118"><xref:System.Linq.Enumerable.Concat%2A> は、引数の順序を維持しません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-118"><xref:System.Linq.Enumerable.Concat%2A> does not preserve the order of its arguments.</span></span> <span data-ttu-id="0ab8b-119">適切な順序にするには、<xref:System.Linq.Enumerable.Concat%2A> の結果を明示的に順序付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-119">To ensure appropriate ordering, you must explicitly order the results of <xref:System.Linq.Enumerable.Concat%2A>.</span></span>

### <a name="intersect-except-union"></a><span data-ttu-id="0ab8b-120">Intersect、Except、Union</span><span class="sxs-lookup"><span data-stu-id="0ab8b-120">Intersect, Except, Union</span></span>

<span data-ttu-id="0ab8b-121"><xref:System.Linq.Enumerable.Intersect%2A> メソッドと <xref:System.Linq.Enumerable.Except%2A> メソッドは、セットに対してのみ正しく定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-121">The <xref:System.Linq.Enumerable.Intersect%2A> and <xref:System.Linq.Enumerable.Except%2A> methods are well defined only on sets.</span></span> <span data-ttu-id="0ab8b-122">マルチセットのセマンティクスは未定義です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-122">The semantics for multisets is undefined.</span></span>

<span data-ttu-id="0ab8b-123"><xref:System.Linq.Enumerable.Union%2A> メソッドは、マルチセットの順序なし連結メソッドとして、マルチセットに対して定義されます (事実上、SQL の UNION ALL 句の結果)。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-123">The <xref:System.Linq.Enumerable.Union%2A> method is defined for multisets as the unordered concatenation of the multisets (effectively the result of the UNION ALL clause in SQL).</span></span>

### <a name="take-skip"></a><span data-ttu-id="0ab8b-124">Take、Skip</span><span class="sxs-lookup"><span data-stu-id="0ab8b-124">Take, Skip</span></span>

<span data-ttu-id="0ab8b-125"><xref:System.Linq.Enumerable.Take%2A> および <xref:System.Linq.Enumerable.Skip%2A> メソッドは、*順序付け*されたセットに対してのみ定義されています。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-125"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods are well defined only against *ordered sets*.</span></span> <span data-ttu-id="0ab8b-126">順序付けされていないセットまたはマルチセットのセマンティクスは未定義です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-126">The semantics for unordered sets or multisets are undefined.</span></span>

> [!NOTE]
> <span data-ttu-id="0ab8b-127"><xref:System.Linq.Enumerable.Take%2A> と <xref:System.Linq.Enumerable.Skip%2A> を SQL Server 2000 に対するクエリで使用する場合は、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-127"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="0ab8b-128">詳細については、「[トラブルシューティング](troubleshooting.md)」の「SQL Server 2000 でのスキップと Take 例外」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-128">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

<span data-ttu-id="0ab8b-129">SQL での順序付けに関する制限により、@no__t は、これらのメソッドの引数の順序をメソッドの結果に移動しようとします。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-129">Because of limitations on ordering in SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to move the ordering of the argument of these methods to the result of the method.</span></span> <span data-ttu-id="0ab8b-130">たとえば、次のような [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリがあるとします。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-130">For example, consider the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query:</span></span>

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

<span data-ttu-id="0ab8b-131">このコードに対して生成される SQL では、順序が次のように末尾に移動されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-131">The generated SQL for this code moves the ordering to the end, as follows:</span></span>

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

<span data-ttu-id="0ab8b-132"><xref:System.Linq.Enumerable.Take%2A> と <xref:System.Linq.Enumerable.Skip%2A> を連結する場合は、指定されているすべての順序が一致することが当然必要です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-132">It becomes obvious that all the specified ordering must be consistent when <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are chained together.</span></span> <span data-ttu-id="0ab8b-133">それ以外の場合、結果は未定義です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-133">Otherwise, the results are undefined.</span></span>

<span data-ttu-id="0ab8b-134"><xref:System.Linq.Enumerable.Take%2A> と <xref:System.Linq.Enumerable.Skip%2A> はいずれも、標準クエリ演算子の仕様に基づく、負でない定数の整数引数に対して正しく定義されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-134">Both <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> are well-defined for non-negative, constant integral arguments based on the Standard Query Operator specification.</span></span>

### <a name="operators-with-no-translation"></a><span data-ttu-id="0ab8b-135">変換されない演算子</span><span class="sxs-lookup"><span data-stu-id="0ab8b-135">Operators with No Translation</span></span>

<span data-ttu-id="0ab8b-136">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって変換されないメソッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-136">The following methods are not translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="0ab8b-137">最も一般的な理由は、順序なしのマルチセットとシーケンスの違いにあります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-137">The most common reason is the difference between unordered multisets and sequences.</span></span>

|<span data-ttu-id="0ab8b-138">演算子</span><span class="sxs-lookup"><span data-stu-id="0ab8b-138">Operators</span></span>|<span data-ttu-id="0ab8b-139">理論的根拠</span><span class="sxs-lookup"><span data-stu-id="0ab8b-139">Rationale</span></span>|
|---------------|---------------|
|<span data-ttu-id="0ab8b-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span><span class="sxs-lookup"><span data-stu-id="0ab8b-140"><xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A></span></span>|<span data-ttu-id="0ab8b-141">SQL クエリの操作の対象は、シーケンスではなく、マルチセットです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-141">SQL queries operate on multisets, not on sequences.</span></span> <span data-ttu-id="0ab8b-142">結果に対して適用する最後の句が `ORDER BY` であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-142">`ORDER BY` must be the last clause applied to the results.</span></span> <span data-ttu-id="0ab8b-143">このため、これら 2 つのメソッドには、汎用的な変換がありません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-143">For this reason, there is no general-purpose translation for these two methods.</span></span>|
|<xref:System.Linq.Enumerable.Reverse%2A>|<span data-ttu-id="0ab8b-144">順序付けされたセットに対しては、このメソッドの変換が可能ですが、現在の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では変換されません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-144">Translation of this method is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="0ab8b-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="0ab8b-145"><xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A></span></span>|<span data-ttu-id="0ab8b-146">順序付けされたセットに対しては、これらのメソッドの変換が可能ですが、現在の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では変換されません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-146">Translation of these methods is possible for an ordered set but is not currently translated by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|
|<span data-ttu-id="0ab8b-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="0ab8b-147"><xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A></span></span>|<span data-ttu-id="0ab8b-148">SQL クエリの操作の対象は、インデックス可能なシーケンスではなくマルチセットです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-148">SQL queries operate on multisets, not on indexable sequences.</span></span>|
|<span data-ttu-id="0ab8b-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (既定の引数のオーバーロード)</span><span class="sxs-lookup"><span data-stu-id="0ab8b-149"><xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (overload with default arg)</span></span>|<span data-ttu-id="0ab8b-150">一般に、任意のタプルに対して既定値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-150">In general, a default value cannot be specified for an arbitrary tuple.</span></span> <span data-ttu-id="0ab8b-151">場合によっては、外部結合を通じて、タプルに対する null 値の使用が可能です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-151">Null values for tuples are possible in some cases through outer joins.</span></span>|

## <a name="expression-translation"></a><span data-ttu-id="0ab8b-152">式の変換</span><span class="sxs-lookup"><span data-stu-id="0ab8b-152">Expression Translation</span></span>

### <a name="null-semantics"></a><span data-ttu-id="0ab8b-153">null セマンティクス</span><span class="sxs-lookup"><span data-stu-id="0ab8b-153">Null semantics</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-154">は、null 比較セマンティクスを SQL に強制しません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-154">does not impose null comparison semantics on SQL.</span></span> <span data-ttu-id="0ab8b-155">比較演算子は、対応する SQL の演算子に構文上は変換されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-155">Comparison operators are syntactically translated to their SQL equivalents.</span></span> <span data-ttu-id="0ab8b-156">このため、セマンティクスには、サーバーまたは接続の設定で定義された SQL セマンティクスが反映されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-156">For this reason, the semantics reflect SQL semantics that are defined by server or connection settings.</span></span> <span data-ttu-id="0ab8b-157">たとえば、既定の SQL Server 設定では、2つの null 値は等しくないと見なされますが、設定を変更してセマンティクスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-157">For example, two null values are considered unequal under default SQL Server settings, but you can change the settings to change the semantics.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-158">は、クエリを変換するときにサーバーの設定を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-158">does not consider server settings when it translates queries.</span></span>

<span data-ttu-id="0ab8b-159">リテラルの null による比較は適切な SQL 形式 (`is null` または `is not null`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-159">A comparison with the literal null is translated to the appropriate SQL version (`is null` or `is not null`).</span></span>

<span data-ttu-id="0ab8b-160">`null` の値の照合順序は SQL Server で定義されます</span><span class="sxs-lookup"><span data-stu-id="0ab8b-160">The value of `null` in collation is defined by SQL Server.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-161">では変更されません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-161">does not change the collation.</span></span>

### <a name="aggregates"></a><span data-ttu-id="0ab8b-162">集計</span><span class="sxs-lookup"><span data-stu-id="0ab8b-162">Aggregates</span></span>

<span data-ttu-id="0ab8b-163">標準クエリ演算子の集計メソッド <xref:System.Linq.Enumerable.Sum%2A> では、空のシーケンスや null のみを含むシーケンスはゼロに評価されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-163">The Standard Query Operator aggregate method <xref:System.Linq.Enumerable.Sum%2A> evaluates to zero for an empty sequence or for a sequence that contains only nulls.</span></span> <span data-ttu-id="0ab8b-164">@No__t 0 では、SQL のセマンティクスは変更されず、<xref:System.Linq.Enumerable.Sum%2A> は空のシーケンスまたは null のみを含むシーケンスに対しては、0ではなく `null` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-164">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged, and <xref:System.Linq.Enumerable.Sum%2A> evaluates to `null` instead of zero for an empty sequence or for a sequence that contains only nulls.</span></span>

<span data-ttu-id="0ab8b-165">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] での集計には、中間結果に対する SQL の制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-165">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="0ab8b-166">32 ビットの整数の <xref:System.Linq.Enumerable.Sum%2A> の計算では、64 ビットの結果は使用されません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-166">The <xref:System.Linq.Enumerable.Sum%2A> of 32-bit integer quantities is not computed by using 64-bit results.</span></span> <span data-ttu-id="0ab8b-167">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] による <xref:System.Linq.Enumerable.Sum%2A> の変換では、オーバーフローが発生することがあります。これには、標準クエリ演算子の実装で、対応するメモリ内シーケンスでオーバーフローが発生しないケースも含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-167">Overflow might occur for a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Sum%2A>, even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>

<span data-ttu-id="0ab8b-168">同様に、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] が整数値の <xref:System.Linq.Enumerable.Average%2A> を変換するときには、`integer` ではなく `double` として計算されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-168">Likewise, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of <xref:System.Linq.Enumerable.Average%2A> of integer values is computed as an `integer`, not as a `double`.</span></span>

### <a name="entity-arguments"></a><span data-ttu-id="0ab8b-169">エンティティ引数</span><span class="sxs-lookup"><span data-stu-id="0ab8b-169">Entity Arguments</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-170">を指定すると、<xref:System.Linq.Enumerable.GroupBy%2A> メソッドと <xref:System.Linq.Enumerable.OrderBy%2A> メソッドでエンティティ型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-170">enables entity types to be used in the <xref:System.Linq.Enumerable.GroupBy%2A> and <xref:System.Linq.Enumerable.OrderBy%2A> methods.</span></span> <span data-ttu-id="0ab8b-171">これらの演算子の変換では、型の引数を使用している場合、その型のすべてのメンバーを指定しているのと同等と見なされます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-171">In the translation of these operators, the use of an argument of a type is considered to be the equivalent to specifying all members of that type.</span></span> <span data-ttu-id="0ab8b-172">たとえば、次のコードは同じ意味です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-172">For example, the following code is equivalent:</span></span>

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a><span data-ttu-id="0ab8b-173">引数の等値性/比較</span><span class="sxs-lookup"><span data-stu-id="0ab8b-173">Equatable / Comparable Arguments</span></span>

<span data-ttu-id="0ab8b-174">以下のメソッドの実装では、引数が等値であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-174">Equality of arguments is required in the implementation of the following methods:</span></span>

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-175">は、*フラット*引数の等値比較をサポートしますが、またはシーケンスを含む引数に対しては使用できません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-175">supports equality and comparison for *flat* arguments, but not for arguments that are or contain sequences.</span></span> <span data-ttu-id="0ab8b-176">フラットな引数とは、SQL の行に対応付けられる型のものです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-176">A flat argument is a type that can be mapped to a SQL row.</span></span> <span data-ttu-id="0ab8b-177">シーケンスを含まないと静的に決定できる 1 つまたは複数のエンティティ型の射影は、フラットな引数と見なされます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-177">A projection of one or more entity types that can be statically determined not to contain a sequence is considered a flat argument.</span></span>

<span data-ttu-id="0ab8b-178">フラット引数の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-178">The following are examples of flat arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#3](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

<span data-ttu-id="0ab8b-179">次に、非フラット (階層) 引数の例を示します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-179">The following are examples of non-flat (hierarchical) arguments:</span></span>

[!code-csharp[DLinqSQOTranslation#4](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a><span data-ttu-id="0ab8b-180">Visual Basic の関数の変換</span><span class="sxs-lookup"><span data-stu-id="0ab8b-180">Visual Basic Function Translation</span></span>

<span data-ttu-id="0ab8b-181">Visual Basic のコンパイラが使用する以下のヘルパー関数は、対応する SQL 演算子および関数に変換されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-181">The following helper functions that are used by the Visual Basic compiler are translated to corresponding SQL operators and functions:</span></span>

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

<span data-ttu-id="0ab8b-182">変換メソッド :</span><span class="sxs-lookup"><span data-stu-id="0ab8b-182">Conversion methods:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="0ab8b-183">ToBoolean</span><span class="sxs-lookup"><span data-stu-id="0ab8b-183">ToBoolean</span></span>|<span data-ttu-id="0ab8b-184">ToSByte</span><span class="sxs-lookup"><span data-stu-id="0ab8b-184">ToSByte</span></span>|<span data-ttu-id="0ab8b-185">ToByte</span><span class="sxs-lookup"><span data-stu-id="0ab8b-185">ToByte</span></span>|<span data-ttu-id="0ab8b-186">ToChar</span><span class="sxs-lookup"><span data-stu-id="0ab8b-186">ToChar</span></span>|
|<span data-ttu-id="0ab8b-187">ToCharArrayRankOne</span><span class="sxs-lookup"><span data-stu-id="0ab8b-187">ToCharArrayRankOne</span></span>|<span data-ttu-id="0ab8b-188">ToDate</span><span class="sxs-lookup"><span data-stu-id="0ab8b-188">ToDate</span></span>|<span data-ttu-id="0ab8b-189">ToDecimal</span><span class="sxs-lookup"><span data-stu-id="0ab8b-189">ToDecimal</span></span>|<span data-ttu-id="0ab8b-190">ToDouble</span><span class="sxs-lookup"><span data-stu-id="0ab8b-190">ToDouble</span></span>|
|<span data-ttu-id="0ab8b-191">ToInteger</span><span class="sxs-lookup"><span data-stu-id="0ab8b-191">ToInteger</span></span>|<span data-ttu-id="0ab8b-192">ToUInteger</span><span class="sxs-lookup"><span data-stu-id="0ab8b-192">ToUInteger</span></span>|<span data-ttu-id="0ab8b-193">ToLong</span><span class="sxs-lookup"><span data-stu-id="0ab8b-193">ToLong</span></span>|<span data-ttu-id="0ab8b-194">ToULong</span><span class="sxs-lookup"><span data-stu-id="0ab8b-194">ToULong</span></span>|
|<span data-ttu-id="0ab8b-195">ToShort</span><span class="sxs-lookup"><span data-stu-id="0ab8b-195">ToShort</span></span>|<span data-ttu-id="0ab8b-196">ToUShort</span><span class="sxs-lookup"><span data-stu-id="0ab8b-196">ToUShort</span></span>|<span data-ttu-id="0ab8b-197">ToSingle</span><span class="sxs-lookup"><span data-stu-id="0ab8b-197">ToSingle</span></span>|<span data-ttu-id="0ab8b-198">ToString</span><span class="sxs-lookup"><span data-stu-id="0ab8b-198">ToString</span></span>|

## <a name="inheritance-support"></a><span data-ttu-id="0ab8b-199">継承のサポート</span><span class="sxs-lookup"><span data-stu-id="0ab8b-199">Inheritance Support</span></span>

### <a name="inheritance-mapping-restrictions"></a><span data-ttu-id="0ab8b-200">継承の対応付けの制限</span><span class="sxs-lookup"><span data-stu-id="0ab8b-200">Inheritance Mapping Restrictions</span></span>

<span data-ttu-id="0ab8b-201">詳細については、「[方法 :継承階層をマップする @ no__t-0。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-201">For more information, see [How to: Map Inheritance Hierarchies](how-to-map-inheritance-hierarchies.md).</span></span>

### <a name="inheritance-in-queries"></a><span data-ttu-id="0ab8b-202">クエリでの継承</span><span class="sxs-lookup"><span data-stu-id="0ab8b-202">Inheritance in Queries</span></span>

<span data-ttu-id="0ab8b-203">C# のキャストは射影でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-203">C# casts are supported only in projection.</span></span> <span data-ttu-id="0ab8b-204">他の場所で使用したキャストは変換されず、無視されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-204">Casts that are used elsewhere are not translated and are ignored.</span></span> <span data-ttu-id="0ab8b-205">SQL 関数名を除き、SQL が実行するのは、共通言語ランタイム (CLR: Common Language Runtime) の <xref:System.Convert> に相当する処理のみです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-205">Aside from SQL function names, SQL really only performs the equivalent of the common language runtime (CLR) <xref:System.Convert>.</span></span> <span data-ttu-id="0ab8b-206">つまり、SQL は、ある型の値を別の型に変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-206">That is, SQL can change the value of one type to another.</span></span> <span data-ttu-id="0ab8b-207">CLR のキャストに相当するものはありません。同じビット列を別の型として再解釈するという概念がないためです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-207">There is no equivalent of CLR cast because there is no concept of reinterpreting the same bits as those of another type.</span></span> <span data-ttu-id="0ab8b-208">したがって、C# のキャストはローカルでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-208">That is why a C# cast works only locally.</span></span> <span data-ttu-id="0ab8b-209">リモート処理はされません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-209">It is not remoted.</span></span>

<span data-ttu-id="0ab8b-210">演算子 `is` と `as`、および `GetType` メソッドは、`Select` 演算子に限定されません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-210">The operators, `is` and `as`, and the `GetType` method are not restricted to the `Select` operator.</span></span> <span data-ttu-id="0ab8b-211">他のクエリ演算子でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-211">They can be used in other query operators also.</span></span>

## <a name="sql-server-2008-support"></a><span data-ttu-id="0ab8b-212">SQL Server 2008 のサポート</span><span class="sxs-lookup"><span data-stu-id="0ab8b-212">SQL Server 2008 Support</span></span>

<span data-ttu-id="0ab8b-213">.NET Framework 3.5 SP1 以降、LINQ to SQL は SQL Server 2008 で導入された新しい日付/時刻型へのマッピングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-213">Starting with the .NET Framework 3.5 SP1, LINQ to SQL supports mapping to new date and time types introduced with SQL Server 2008.</span></span> <span data-ttu-id="0ab8b-214">ただし、これらの新しい型にマッピングされた値を操作するときに使用できる LINQ to SQL のクエリ演算子にはいくつか制限があります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-214">But, there are some limitations to the LINQ to SQL query operators that you can use when operating against values mapped to these new types.</span></span>

### <a name="unsupported-query-operators"></a><span data-ttu-id="0ab8b-215">サポートされていないクエリ演算子</span><span class="sxs-lookup"><span data-stu-id="0ab8b-215">Unsupported Query Operators</span></span>

<span data-ttu-id="0ab8b-216">`DATETIME2`、`DATE`、`TIME`、および `DATETIMEOFFSET` は、SQL Server の新しい日付/時刻型にマッピングされた値ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-216">The following query operators are not supported on values mapped to the new SQL Server date and time types: `DATETIME2`, `DATE`, `TIME`, and `DATETIMEOFFSET`.</span></span>

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

<span data-ttu-id="0ab8b-217">これらの SQL Server の日付と時刻の型へのマッピングの詳細については、「 [SQL-CLR 型のマッピング](sql-clr-type-mapping.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-217">For more information about mapping to these SQL Server date and time types, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>

## <a name="sql-server-2005-support"></a><span data-ttu-id="0ab8b-218">SQL Server 2005 のサポート</span><span class="sxs-lookup"><span data-stu-id="0ab8b-218">SQL Server 2005 Support</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-219">は、SQL Server 2005 の以下の機能をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-219">does not support the following SQL Server 2005 features:</span></span>

- <span data-ttu-id="0ab8b-220">SQL CLR 用に作成されたストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-220">Stored procedures written for SQL CLR.</span></span>

- <span data-ttu-id="0ab8b-221">ユーザー定義型。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-221">User-defined type.</span></span>

- <span data-ttu-id="0ab8b-222">XML クエリ機能。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-222">XML query features.</span></span>

## <a name="sql-server-2000-support"></a><span data-ttu-id="0ab8b-223">SQL Server 2000 のサポート</span><span class="sxs-lookup"><span data-stu-id="0ab8b-223">SQL Server 2000 Support</span></span>

<span data-ttu-id="0ab8b-224">次の SQL Server 2000 の制限 (Microsoft SQL Server 2005 と比較) は、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のサポートに影響します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-224">The following SQL Server 2000 limitations (compared to Microsoft SQL Server 2005) affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>

### <a name="cross-apply-and-outer-apply-operators"></a><span data-ttu-id="0ab8b-225">Cross Apply 演算子および Outer Apply 演算子</span><span class="sxs-lookup"><span data-stu-id="0ab8b-225">Cross Apply and Outer Apply Operators</span></span>

<span data-ttu-id="0ab8b-226">これらの演算子は SQL Server 2000 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-226">These operators are not available in SQL Server 2000.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0ab8b-227">は、一連の書き換えを行って、これらの演算子を適切な結合に置換します。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-227">tries a series of rewrites to replace them with appropriate joins.</span></span>

<span data-ttu-id="0ab8b-228">`Cross Apply` および `Outer Apply` は、リレーションシップ ナビゲーションに対してのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-228">`Cross Apply` and `Outer Apply` are generated for relationship navigations.</span></span> <span data-ttu-id="0ab8b-229">どのようなクエリのセットに対してこのような書き換えが可能かは、正しく定義されていません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-229">The set of queries for which such rewrites are possible is not well defined.</span></span> <span data-ttu-id="0ab8b-230">このため、SQL Server 2000 でサポートされている最小限のクエリセットは、リレーションシップナビゲーションを含まないセットです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-230">For this reason, the minimal set of queries that is supported for SQL Server 2000 is the set that does not involve relationship navigation.</span></span>

### <a name="text--ntext"></a><span data-ttu-id="0ab8b-231">text / ntext</span><span class="sxs-lookup"><span data-stu-id="0ab8b-231">text / ntext</span></span>

<span data-ttu-id="0ab8b-232">データ型 `text` @ no__t @ no__t は、Microsoft SQL Server 2005 でサポートされている `varchar(max)` @ no__t @ no__t に対する特定のクエリ操作では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-232">Data types `text` / `ntext` cannot be used in certain query operations against `varchar(max)` / `nvarchar(max)`, which are supported by Microsoft SQL Server 2005.</span></span>

<span data-ttu-id="0ab8b-233">この制限事項には、対処方法はありません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-233">No resolution is available for this limitation.</span></span> <span data-ttu-id="0ab8b-234">具体的には、`Distinct()` 列または `text` 列に割り当てられているメンバーを含む結果に対して、`ntext` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-234">Specifically, you cannot use `Distinct()` on any result that contains members that are mapped to `text` or `ntext` columns.</span></span>

### <a name="behavior-triggered-by-nested-queries"></a><span data-ttu-id="0ab8b-235">入れ子になったクエリによってトリガーされる動作</span><span class="sxs-lookup"><span data-stu-id="0ab8b-235">Behavior Triggered by Nested Queries</span></span>

<span data-ttu-id="0ab8b-236">SQL Server 2000 (SP4 を通じて) のバインダーには、入れ子になったクエリによってトリガーされる特異性がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-236">SQL Server 2000 (through SP4) binder has some idiosyncrasies that are triggered by nested queries.</span></span> <span data-ttu-id="0ab8b-237">この特異動作をトリガーする SQL クエリのセットは、正しく定義されていません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-237">The set of SQL queries that triggers these idiosyncrasies is not well defined.</span></span> <span data-ttu-id="0ab8b-238">このため、SQL Server 例外が発生する可能性がある @no__t 0 クエリのセットを定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-238">For this reason, you cannot define the set of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries that might cause SQL Server exceptions.</span></span>

### <a name="skip-and-take-operators"></a><span data-ttu-id="0ab8b-239">Skip 演算子および Take 演算子</span><span class="sxs-lookup"><span data-stu-id="0ab8b-239">Skip and Take Operators</span></span>

<span data-ttu-id="0ab8b-240"><xref:System.Linq.Enumerable.Take%2A> と <xref:System.Linq.Enumerable.Skip%2A> を SQL Server 2000 に対するクエリで使用する場合は、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-240"><xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> have certain limitations when they are used in queries against SQL Server 2000.</span></span> <span data-ttu-id="0ab8b-241">詳細については、「[トラブルシューティング](troubleshooting.md)」の「SQL Server 2000 でのスキップと Take 例外」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-241">For more information, see the "Skip and Take Exceptions in SQL Server 2000" entry in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="object-materialization"></a><span data-ttu-id="0ab8b-242">オブジェクトの具体化</span><span class="sxs-lookup"><span data-stu-id="0ab8b-242">Object Materialization</span></span>

<span data-ttu-id="0ab8b-243">実体化とは、1 つまたは複数の SQL クエリで返された行から CLR オブジェクトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-243">Materialization creates CLR objects from rows that are returned by one or more SQL queries.</span></span>

- <span data-ttu-id="0ab8b-244">次の呼び出しは、具体化の一部として*ローカルで実行*されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-244">The following calls are *executed locally* as a part of materialization:</span></span>

  - <span data-ttu-id="0ab8b-245">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="0ab8b-245">Constructors</span></span>

  - <span data-ttu-id="0ab8b-246">射影での `ToString` メソッド</span><span class="sxs-lookup"><span data-stu-id="0ab8b-246">`ToString` methods in projections</span></span>

  - <span data-ttu-id="0ab8b-247">射影での型キャスト</span><span class="sxs-lookup"><span data-stu-id="0ab8b-247">Type casts in projections</span></span>

- <span data-ttu-id="0ab8b-248">@No__t-0 メソッドに続くメソッドは*ローカルで実行*されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-248">Methods that follow the <xref:System.Linq.Enumerable.AsEnumerable%2A> method are *executed locally*.</span></span> <span data-ttu-id="0ab8b-249">このメソッドでは即時実行は行われません。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-249">This method does not cause immediate execution.</span></span>

- <span data-ttu-id="0ab8b-250">`struct` は、クエリ結果の戻り値の型として、または結果の型のメンバーとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-250">You can use a `struct` as the return type of a query result or as a member of the result type.</span></span> <span data-ttu-id="0ab8b-251">エンティティはクラスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-251">Entities are required to be classes.</span></span> <span data-ttu-id="0ab8b-252">匿名型はクラス インスタンスとして実体化されますが、射影では名前付き構造体 (エンティティ以外) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-252">Anonymous types are materialized as class instances, but named structs (non-entities) can be used in projection.</span></span>

- <span data-ttu-id="0ab8b-253">クエリ結果の戻り値の型のメンバーには、<xref:System.Linq.IQueryable%601> 型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-253">A member of the return type of a query result can be of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="0ab8b-254">これはローカル コレクションとして実体化されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-254">It is materialized as a local collection.</span></span>

- <span data-ttu-id="0ab8b-255">次のメソッドを実行すると、メソッドが適用されるシーケンスが*直接具体化*されます。</span><span class="sxs-lookup"><span data-stu-id="0ab8b-255">The following methods cause the *immediate materialization* of the sequence that the methods are applied to:</span></span>

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a><span data-ttu-id="0ab8b-256">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ab8b-256">See also</span></span>

- [<span data-ttu-id="0ab8b-257">リファレンス</span><span class="sxs-lookup"><span data-stu-id="0ab8b-257">Reference</span></span>](reference.md)
- [<span data-ttu-id="0ab8b-258">シーケンスの要素の取得またはスキップ</span><span class="sxs-lookup"><span data-stu-id="0ab8b-258">Return Or Skip Elements in a Sequence</span></span>](return-or-skip-elements-in-a-sequence.md)
- [<span data-ttu-id="0ab8b-259">2 つのシーケンスの連結</span><span class="sxs-lookup"><span data-stu-id="0ab8b-259">Concatenate Two Sequences</span></span>](concatenate-two-sequences.md)
- [<span data-ttu-id="0ab8b-260">2 つのシーケンスの差集合の取得</span><span class="sxs-lookup"><span data-stu-id="0ab8b-260">Return the Set Difference Between Two Sequences</span></span>](return-the-set-difference-between-two-sequences.md)
- [<span data-ttu-id="0ab8b-261">2 つのシーケンスの積集合の取得</span><span class="sxs-lookup"><span data-stu-id="0ab8b-261">Return the Set Intersection of Two Sequences</span></span>](return-the-set-intersection-of-two-sequences.md)
- [<span data-ttu-id="0ab8b-262">2 つのシーケンスの和集合の取得</span><span class="sxs-lookup"><span data-stu-id="0ab8b-262">Return the Set Union of Two Sequences</span></span>](return-the-set-union-of-two-sequences.md)
