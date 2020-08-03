---
title: Join 演算 (C#)
description: 2 つのデータ ソースの結合により、オブジェクトと、データ ソースとの間で属性を共有するオブジェクトが関連付けられます。 C# での LINQ フレームワークにおける結合メソッドについて学習します。
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 1b453f1752edf0cc126f8e27dbdd9e91ad9143f3
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165689"
---
# <a name="no-locjoin-operations-c"></a><span data-ttu-id="c55f4-104">Join 演算 (C#)</span><span class="sxs-lookup"><span data-stu-id="c55f4-104">Join Operations (C#)</span></span>

<span data-ttu-id="c55f4-105">2 つのデータ ソースの "*結合*" とは、あるデータ ソースのオブジェクトを、共通の属性を共有する別のデータ ソースのオブジェクトと関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="c55f4-105">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="c55f4-106">相互に直接指定することができない関係を持つデータ ソースを対象とするクエリにおいて、Join は重要な操作になります。</span><span class="sxs-lookup"><span data-stu-id="c55f4-106">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="c55f4-107">オブジェクト指向プログラミングでは、これは一方向の関係における逆の方向など、モデル化されていないオブジェクト間の相関関係を意味する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c55f4-107">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="c55f4-108">一方向の関係の例として、City 型のプロパティを持つ Customer クラスがあるとします。ただし、City クラスには、Customer オブジェクトのコレクションを表すプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="c55f4-108">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="c55f4-109">City オブジェクトのリストから各都市のすべての顧客を取得する場合は、結合演算を使用して顧客を検索できます。</span><span class="sxs-lookup"><span data-stu-id="c55f4-109">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="c55f4-110">LINQ framework で用意された結合メソッドは <xref:System.Linq.Enumerable.Join%2A> と <xref:System.Linq.Enumerable.GroupJoin%2A> です。</span><span class="sxs-lookup"><span data-stu-id="c55f4-110">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="c55f4-111">この 2 つのメソッドは、等結合 (キーが等しいかどうかに基づいて 2 つのデータ ソースを対応させる結合) を実行します。</span><span class="sxs-lookup"><span data-stu-id="c55f4-111">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="c55f4-112">(比較に関して、Transact-SQL では、"小なり" 演算子などの "等値" 以外の結合演算子もサポートされます)。リレーショナル データベース用語で説明すると、<xref:System.Linq.Enumerable.Join%2A> は内部結合 (両方のデータ セットで一致するオブジェクトだけが返される結合) を実装します。</span><span class="sxs-lookup"><span data-stu-id="c55f4-112">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="c55f4-113">リレーショナル データベース用語で <xref:System.Linq.Enumerable.GroupJoin%2A> メソッドに直接相当するものはありませんが、このメソッドは内部結合と左外部結合のスーパーセットを実装します。</span><span class="sxs-lookup"><span data-stu-id="c55f4-113">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="c55f4-114">左外部結合とは、最初 (左側) のデータ ソースの各要素を返す結合です。これらの要素は、もう一方のデータ ソースの要素と相関関係がなくても返されます。</span><span class="sxs-lookup"><span data-stu-id="c55f4-114">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="c55f4-115">次の図は、2 つのセットと、内部結合または左外部結合としてこれらのセットに含まれている要素の概念図を示しています。</span><span class="sxs-lookup"><span data-stu-id="c55f4-115">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![内側&#47;外側を示す 2 つの重なり合う円。](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="c55f4-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="c55f4-117">Methods</span></span>  
  
|<span data-ttu-id="c55f4-118">メソッド名</span><span class="sxs-lookup"><span data-stu-id="c55f4-118">Method Name</span></span>|<span data-ttu-id="c55f4-119">説明</span><span class="sxs-lookup"><span data-stu-id="c55f4-119">Description</span></span>|<span data-ttu-id="c55f4-120">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="c55f4-120">C# Query Expression Syntax</span></span>|<span data-ttu-id="c55f4-121">説明</span><span class="sxs-lookup"><span data-stu-id="c55f4-121">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="c55f4-122">キー セレクター関数に基づいて 2 つのシーケンスの Join を行い、値のペアを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c55f4-122">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="c55f4-123">キー セレクター関数に基づいて 2 つのシーケンスの Join を行い、各要素について結果として得られる一致をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="c55f4-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="c55f4-124">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="c55f4-124">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="c55f4-125">次の例では、`join … in … on … equals …` 句を使用し、特定の値に基づいて 2 つのシーケンスを結合します。</span><span class="sxs-lookup"><span data-stu-id="c55f4-125">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="c55f4-126">次の例では、`join … in … on … equals … into …` 句を使用し、特定の値に基づいて 2 つのシーケンスを結合し、要素ごとに結果として得られる一致をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="c55f4-126">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="c55f4-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c55f4-127">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="c55f4-128">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="c55f4-128">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="c55f4-129">匿名型</span><span class="sxs-lookup"><span data-stu-id="c55f4-129">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="c55f4-130">Join およびクロス積クエリの作成</span><span class="sxs-lookup"><span data-stu-id="c55f4-130">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="c55f4-131">join 句</span><span class="sxs-lookup"><span data-stu-id="c55f4-131">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="c55f4-132">複合キーを使用した Join</span><span class="sxs-lookup"><span data-stu-id="c55f4-132">Join by using composite keys</span></span>](../../../linq/join-by-using-composite-keys.md)
- [<span data-ttu-id="c55f4-133">異種ファイルのコンテンツを結合する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c55f4-133">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="c55f4-134">join 句の結果の順序指定</span><span class="sxs-lookup"><span data-stu-id="c55f4-134">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="c55f4-135">カスタム結合操作の実行</span><span class="sxs-lookup"><span data-stu-id="c55f4-135">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="c55f4-136">グループ化結合の実行</span><span class="sxs-lookup"><span data-stu-id="c55f4-136">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="c55f4-137">内部結合の実行</span><span class="sxs-lookup"><span data-stu-id="c55f4-137">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="c55f4-138">左外部結合の実行</span><span class="sxs-lookup"><span data-stu-id="c55f4-138">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="c55f4-139">複数のソースからオブジェクト コレクションにデータを設定する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c55f4-139">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
