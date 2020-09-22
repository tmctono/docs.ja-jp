---
title: グループ結合の実行 (C# での LINQ)
description: C# で LINQ を使用して、グループ結合を実行する方法について説明します。
ms.date: 04/22/2020
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: 6411479c5fe6cb0ee79a0cd3df6de2f4d42c26a2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542810"
---
# <a name="perform-grouped-joins"></a><span data-ttu-id="2809e-103">グループ結合の実行</span><span class="sxs-lookup"><span data-stu-id="2809e-103">Perform grouped joins</span></span>

<span data-ttu-id="2809e-104">グループ結合は、階層データ構造を作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2809e-104">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="2809e-105">これは、最初のコレクションの各要素と、2 番目のコレクションの相関関係を持つ要素のセットを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="2809e-105">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>

<span data-ttu-id="2809e-106">たとえば、`Student` という名前のクラスまたはリレーショナル データベース テーブルに、`Id` と `Name` という 2 つのフィールドが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="2809e-106">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="2809e-107">`Course` という名前の 2 番目のクラスまたはリレーショナル データベース テーブルには、`StudentId` と `CourseTitle` という 2 つのフィールドが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="2809e-107">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="2809e-108">この 2 つのデータ ソースのグループ結合は、`Student.Id` と `Course.StudentId` の一致に基づいて、`Course` オブジェクトのコレクションを持つ各 `Student` をグループ化します (コレクションは空の場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="2809e-108">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>

> [!NOTE]
> <span data-ttu-id="2809e-109">最初のコレクションの各要素は、2 番目のコレクションに相関関係を持つ要素があるかどうかにかかわらず、グループ結合の結果セットに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2809e-109">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="2809e-110">相関関係を持つ要素が見つからない場合、その要素の相関関係を持つ要素のシーケンスは空です。</span><span class="sxs-lookup"><span data-stu-id="2809e-110">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="2809e-111">そのため、結果セレクターは最初のコレクションのすべての要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2809e-111">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="2809e-112">これは、非グループ結合の結果セレクターとは異なります。非グループ結合の結果セレクターは、2 番目のコレクションに一致するものがない最初のコレクションの要素にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2809e-112">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>

> [!WARNING]
> <span data-ttu-id="2809e-113"><xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType> には、従来のリレーショナル データベースの用語に直接相当するものはありません。</span><span class="sxs-lookup"><span data-stu-id="2809e-113"><xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType> has no direct equivalent in traditional relational database terms.</span></span> <span data-ttu-id="2809e-114">ただし、このメソッドでは内部結合と左外部結合のスーパーセットが実装されます。</span><span class="sxs-lookup"><span data-stu-id="2809e-114">However, this method does implement a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="2809e-115">これらの操作はどちらも、グループ化結合の観点から記述できます。</span><span class="sxs-lookup"><span data-stu-id="2809e-115">Both of these operations can be written in terms of a grouped join.</span></span> <span data-ttu-id="2809e-116">詳細については、「[結合操作](../programming-guide/concepts/linq/join-operations.md)」と[「Entity Framework Core」の「GroupJoin」](/ef/core/querying/complex-query-operators#groupjoin)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2809e-116">For more information, see [Join Operations](../programming-guide/concepts/linq/join-operations.md) and [Entity Framework Core, GroupJoin](/ef/core/querying/complex-query-operators#groupjoin).</span></span>

<span data-ttu-id="2809e-117">この記事の最初の例では、グループ結合を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2809e-117">The first example in this article shows you how to perform a group join.</span></span> <span data-ttu-id="2809e-118">2 つ目の例では、グループ結合を使用して XML 要素を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2809e-118">The second example shows you how to use a group join to create XML elements.</span></span>

## <a name="example---group-join"></a><span data-ttu-id="2809e-119">例 - グループ結合</span><span class="sxs-lookup"><span data-stu-id="2809e-119">Example - Group join</span></span>

<span data-ttu-id="2809e-120">次の例では、`Pet.Owner` プロパティと一致する `Person` に基づいて、`Person` 型と `Pet` 型のオブジェクトのグループ結合を実行します。</span><span class="sxs-lookup"><span data-stu-id="2809e-120">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="2809e-121">一致ごとに要素のペアを生成する非グループ結合と異なり、グループ結合は最初のコレクションの要素ごとに 1 つのオブジェクト (この例では `Person` オブジェクト) のみを作成します。</span><span class="sxs-lookup"><span data-stu-id="2809e-121">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="2809e-122">2 番目のコレクションの対応する要素 (この例では `Pet` オブジェクト) が 1 つのコレクションにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="2809e-122">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="2809e-123">最後に、結果セレクター機能により、`Person.FirstName` と、`Pet` オブジェクトのコレクションで構成される一致ごとに匿名型が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2809e-123">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>

[!code-csharp[CsLINQProgJoining#5](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]

## <a name="example---group-join-to-create-xml"></a><span data-ttu-id="2809e-124">例 - XML を作成するグループ結合</span><span class="sxs-lookup"><span data-stu-id="2809e-124">Example - Group join to create XML</span></span>

<span data-ttu-id="2809e-125">グループ結合は、LINQ to XML を使用した XML の作成に適しています。</span><span class="sxs-lookup"><span data-stu-id="2809e-125">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="2809e-126">次の例は前の例に似ていますが、匿名型を作成するのではなく、結果セレクター機能により、結合されたオブジェクトを表す XML 要素を作成する点が異なります。</span><span class="sxs-lookup"><span data-stu-id="2809e-126">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>

[!code-csharp[CsLINQProgJoining#6](~/samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]

## <a name="see-also"></a><span data-ttu-id="2809e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2809e-127">See also</span></span>

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [<span data-ttu-id="2809e-128">内部結合の実行</span><span class="sxs-lookup"><span data-stu-id="2809e-128">Perform inner joins</span></span>](perform-inner-joins.md)
- [<span data-ttu-id="2809e-129">左外部結合の実行</span><span class="sxs-lookup"><span data-stu-id="2809e-129">Perform left outer joins</span></span>](perform-left-outer-joins.md)
- [<span data-ttu-id="2809e-130">匿名型</span><span class="sxs-lookup"><span data-stu-id="2809e-130">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)
