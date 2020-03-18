---
title: Join 演算 (C#)
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 6e2ec1a0c8120f6869b7c0a196b77d118762a8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76868006"
---
# <a name="join-operations-c"></a><span data-ttu-id="bf807-102">結合操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="bf807-102">Join Operations (C#)</span></span>

<span data-ttu-id="bf807-103">2 つのデータ ソースの "*結合*" とは、あるデータ ソースのオブジェクトを、共通の属性を共有する別のデータ ソースのオブジェクトと関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="bf807-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="bf807-104">相互に直接の関連がない 2 つのデータ ソースを対象とするクエリにおいて、結合は重要な操作になります。</span><span class="sxs-lookup"><span data-stu-id="bf807-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="bf807-105">オブジェクト指向プログラミングでは、これは一方向の関係における逆の方向など、モデル化されていないオブジェクト間の相関関係を意味する場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf807-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="bf807-106">一方向の関係の例として、City 型のプロパティを持つ Customer クラスがあるとします。ただし、City クラスには、Customer オブジェクトのコレクションを表すプロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="bf807-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="bf807-107">City オブジェクトのリストから各都市のすべての顧客を取得する場合は、結合演算を使用して顧客を検索できます。</span><span class="sxs-lookup"><span data-stu-id="bf807-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="bf807-108">LINQ framework で用意された結合メソッドは <xref:System.Linq.Enumerable.Join%2A> と <xref:System.Linq.Enumerable.GroupJoin%2A> です。</span><span class="sxs-lookup"><span data-stu-id="bf807-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="bf807-109">この 2 つのメソッドは、等結合 (キーが等しいかどうかに基づいて 2 つのデータ ソースを対応させる結合) を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf807-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="bf807-110">(比較に関して、Transact-SQL では、"小なり" 演算子などの "等値" 以外の結合演算子もサポートされます)。リレーショナル データベース用語で説明すると、<xref:System.Linq.Enumerable.Join%2A> は内部結合 (両方のデータ セットで一致するオブジェクトだけが返される結合) を実装します。</span><span class="sxs-lookup"><span data-stu-id="bf807-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="bf807-111">リレーショナル データベース用語で <xref:System.Linq.Enumerable.GroupJoin%2A> メソッドに直接相当するものはありませんが、このメソッドは内部結合と左外部結合のスーパーセットを実装します。</span><span class="sxs-lookup"><span data-stu-id="bf807-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="bf807-112">左外部結合とは、最初 (左側) のデータ ソースの各要素を返す結合です。これらの要素は、もう一方のデータ ソースの要素と相関関係がなくても返されます。</span><span class="sxs-lookup"><span data-stu-id="bf807-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="bf807-113">次の図は、2 つのセットと、内部結合または左外部結合としてこれらのセットに含まれている要素の概念図を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf807-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 ![内側&#47;外側を示す 2 つの重なり合う円。](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a><span data-ttu-id="bf807-115">メソッド</span><span class="sxs-lookup"><span data-stu-id="bf807-115">Methods</span></span>  
  
|<span data-ttu-id="bf807-116">メソッド名</span><span class="sxs-lookup"><span data-stu-id="bf807-116">Method Name</span></span>|<span data-ttu-id="bf807-117">説明</span><span class="sxs-lookup"><span data-stu-id="bf807-117">Description</span></span>|<span data-ttu-id="bf807-118">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="bf807-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="bf807-119">説明</span><span class="sxs-lookup"><span data-stu-id="bf807-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|<span data-ttu-id="bf807-120">キー セレクター関数に基づいて 2 つのシーケンスを結合し、値のペアを抽出します。</span><span class="sxs-lookup"><span data-stu-id="bf807-120">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|<span data-ttu-id="bf807-121">キー セレクター関数に基づいて 2 つのシーケンスを結合し、各要素について結果として得られる一致をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="bf807-121">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="bf807-122">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="bf807-122">Query expression syntax examples</span></span>
  
### Join  
  
<span data-ttu-id="bf807-123">次の例では、`join … in … on … equals …` 句を使用し、特定の値に基づいて 2 つのシーケンスを結合します。</span><span class="sxs-lookup"><span data-stu-id="bf807-123">The following example uses the `join … in … on … equals …` clause to join two sequences based on specific value:</span></span>
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

<span data-ttu-id="bf807-124">次の例では、`join … in … on … equals … into …` 句を使用し、特定の値に基づいて 2 つのシーケンスを結合し、要素ごとに結果として得られる一致をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="bf807-124">The following example uses the `join … in … on … equals … into …` clause to join two sequences based on specific value and groups the resulting matches for each element:</span></span>
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a><span data-ttu-id="bf807-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf807-125">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="bf807-126">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="bf807-126">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="bf807-127">匿名型</span><span class="sxs-lookup"><span data-stu-id="bf807-127">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="bf807-128">結合およびクロス積クエリの作成</span><span class="sxs-lookup"><span data-stu-id="bf807-128">Formulate Joins and Cross-Product Queries</span></span>](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [<span data-ttu-id="bf807-129">join 句</span><span class="sxs-lookup"><span data-stu-id="bf807-129">join clause</span></span>](../../../language-reference/keywords/join-clause.md)
- <span data-ttu-id="bf807-130">[複合キーを使用した Join](../../../linq/join-by-using-composite-keys.md)</span><span class="sxs-lookup"><span data-stu-id="bf807-130">[Join by using composite keys](../../../linq/join-by-using-composite-keys.md)</span></span>
- [<span data-ttu-id="bf807-131">異種ファイルのコンテンツを結合する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bf807-131">How to join content from dissimilar files (LINQ) (C#)</span></span>](./how-to-join-content-from-dissimilar-files-linq.md)
- [<span data-ttu-id="bf807-132">join 句の結果の順序指定</span><span class="sxs-lookup"><span data-stu-id="bf807-132">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="bf807-133">カスタム結合操作の実行</span><span class="sxs-lookup"><span data-stu-id="bf807-133">Perform custom join operations</span></span>](../../../linq/perform-custom-join-operations.md)
- [<span data-ttu-id="bf807-134">グループ化結合の実行</span><span class="sxs-lookup"><span data-stu-id="bf807-134">Perform grouped joins</span></span>](../../../linq/perform-grouped-joins.md)
- [<span data-ttu-id="bf807-135">内部結合の実行</span><span class="sxs-lookup"><span data-stu-id="bf807-135">Perform inner joins</span></span>](../../../linq/perform-inner-joins.md)
- [<span data-ttu-id="bf807-136">左外部結合の実行</span><span class="sxs-lookup"><span data-stu-id="bf807-136">Perform left outer joins</span></span>](../../../linq/perform-left-outer-joins.md)
- [<span data-ttu-id="bf807-137">複数のソースからオブジェクト コレクションにデータを設定する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bf807-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
