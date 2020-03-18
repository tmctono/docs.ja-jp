---
title: 内部結合の実行 (C# での LINQ)
description: C# で LINQ を使用して、内部結合を実行する方法について説明します。
ms.date: 12/01/2016
ms.assetid: 45bceed6-f549-4114-a9b1-b44feb497742
ms.openlocfilehash: a3e8e9bd97ec630797bc48a3302b27ed45d9103e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659840"
---
# <a name="perform-inner-joins"></a><span data-ttu-id="ac967-103">内部結合の実行</span><span class="sxs-lookup"><span data-stu-id="ac967-103">Perform inner joins</span></span>

<span data-ttu-id="ac967-104">リレーショナル データベースでは、"*内部結合*" により、2 番目のコレクション内の一致するすべての要素に対して、最初のコレクションの各要素が一度表示される結果セットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-104">In relational database terms, an *inner join* produces a result set in which each element of the first collection appears one time for every matching element in the second collection.</span></span> <span data-ttu-id="ac967-105">最初のコレクション内の要素に一致する要素が存在しない場合、その要素は結果セットには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac967-105">If an element in the first collection has no matching elements, it does not appear in the result set.</span></span> <span data-ttu-id="ac967-106"><xref:System.Linq.Enumerable.Join%2A> メソッドは、C# の `join` 句によって呼び出され、内部結合を実装します。</span><span class="sxs-lookup"><span data-stu-id="ac967-106">The <xref:System.Linq.Enumerable.Join%2A> method, which is called by the `join` clause in C#, implements an inner join.</span></span>

<span data-ttu-id="ac967-107">この記事では、次の 4 種類の内部結合を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ac967-107">This article shows you how to perform four variations of an inner join:</span></span>

- <span data-ttu-id="ac967-108">簡単なキーに基づいて、2 つのデータ ソースの要素を関連付ける単純な内部結合。</span><span class="sxs-lookup"><span data-stu-id="ac967-108">A simple inner join that correlates elements from two data sources based on a simple key.</span></span>

- <span data-ttu-id="ac967-109">"*複合*" キーに基づいて、2 つのデータ ソースの要素を関連付ける内部結合。</span><span class="sxs-lookup"><span data-stu-id="ac967-109">An inner join that correlates elements from two data sources based on a *composite* key.</span></span> <span data-ttu-id="ac967-110">複合キーは複数の値で構成され、複数のプロパティに基づいて要素を関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ac967-110">A composite key, which is a key that consists of more than one value, enables you to correlate elements based on more than one property.</span></span>

- <span data-ttu-id="ac967-111">一連の結合操作が相互に追加された "*複数の結合*"。</span><span class="sxs-lookup"><span data-stu-id="ac967-111">A *multiple join* in which successive join operations are appended to each other.</span></span>

- <span data-ttu-id="ac967-112">グループ結合を使用して実装された内部結合。</span><span class="sxs-lookup"><span data-stu-id="ac967-112">An inner join that is implemented by using a group join.</span></span>

## <a name="example---simple-key-join"></a><span data-ttu-id="ac967-113">例 - 簡単なキーの結合</span><span class="sxs-lookup"><span data-stu-id="ac967-113">Example - Simple key join</span></span>

<span data-ttu-id="ac967-114">次の例は、2 つのユーザー定義型オブジェクト、`Person` と `Pet` が含まれた 2 つのコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac967-114">The following example creates two collections that contain objects of two user-defined types, `Person` and `Pet`.</span></span> <span data-ttu-id="ac967-115">クエリでは、C# の `join` 句を使用して、`Person` オブジェクトを `Pet` がこの `Owner` である `Person` オブジェクトを照合します。</span><span class="sxs-lookup"><span data-stu-id="ac967-115">The query uses the `join` clause in C# to match `Person` objects with `Pet` objects whose `Owner` is that `Person`.</span></span> <span data-ttu-id="ac967-116">C# の `select` 句では、結果のオブジェクトの表示内容を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac967-116">The `select` clause in C# defines how the resulting objects will look.</span></span> <span data-ttu-id="ac967-117">この例では、結果のオブジェクトは、飼い主の姓とペットの名前で構成される匿名型です。</span><span class="sxs-lookup"><span data-stu-id="ac967-117">In this example the resulting objects are anonymous types that consist of the owner's first name and the pet's name.</span></span>

[!code-csharp[CsLINQProgJoining#1](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_1.cs)]

<span data-ttu-id="ac967-118">`Person` が "Huff" の `LastName` オブジェクトは、`Pet` がその `Pet.Owner` に等しい `Person` オブジェクトがないため、結果セットに表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac967-118">Note that the `Person` object whose `LastName` is "Huff" does not appear in the result set because there is no `Pet` object that has `Pet.Owner` equal to that `Person`.</span></span>

## <a name="example---composite-key-join"></a><span data-ttu-id="ac967-119">例 - 複合キーの結合</span><span class="sxs-lookup"><span data-stu-id="ac967-119">Example - Composite key join</span></span>

<span data-ttu-id="ac967-120">1 つのプロパティだけに基づいて要素を関連付ける代わりに、複合キーを使用して、複数のプロパティに基づいて要素を比較できます。</span><span class="sxs-lookup"><span data-stu-id="ac967-120">Instead of correlating elements based on just one property, you can use a composite key to compare elements based on multiple properties.</span></span> <span data-ttu-id="ac967-121">これを行うには、各コレクションに対してキー セレクター関数を指定し、比較するプロパティで構成された匿名型を返します。</span><span class="sxs-lookup"><span data-stu-id="ac967-121">To do this, specify the key selector function for each collection to return an anonymous type that consists of the properties you want to compare.</span></span> <span data-ttu-id="ac967-122">プロパティにラベルを付ける場合は、各キーの匿名型に同じラベルを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac967-122">If you label the properties, they must have the same label in each key's anonymous type.</span></span> <span data-ttu-id="ac967-123">また、プロパティは、同じ順序で表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac967-123">The properties must also appear in the same order.</span></span>

<span data-ttu-id="ac967-124">次の例は、`Employee` オブジェクトのリストと `Student` オブジェクトのリストを使用して、学生でもある社員を調べます。</span><span class="sxs-lookup"><span data-stu-id="ac967-124">The following example uses a list of `Employee` objects and a list of `Student` objects to determine which employees are also students.</span></span> <span data-ttu-id="ac967-125">これらの型の両方に、`FirstName` 型の `LastName` プロパティと <xref:System.String> プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="ac967-125">Both of these types have a `FirstName` and a `LastName` property of type <xref:System.String>.</span></span> <span data-ttu-id="ac967-126">それぞれのリストの要素から結合キーを作成する関数が、各要素の `FirstName` プロパティと `LastName` プロパティで構成された匿名型を返します。</span><span class="sxs-lookup"><span data-stu-id="ac967-126">The functions that create the join keys from each list's elements return an anonymous type that consists of the `FirstName` and `LastName` properties of each element.</span></span> <span data-ttu-id="ac967-127">結合操作により、これらの複合キーが等しいかどうか比較され、それぞれのリストの氏名が一致するオブジェクトのペアが返されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-127">The join operation compares these composite keys for equality and returns pairs of objects from each list where both the first name and the last name match.</span></span>

[!code-csharp[CsLINQProgJoining#2](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_2.cs)]

## <a name="example---multiple-join"></a><span data-ttu-id="ac967-128">例 - 複数の結合</span><span class="sxs-lookup"><span data-stu-id="ac967-128">Example - Multiple join</span></span>

<span data-ttu-id="ac967-129">任意の数の結合操作を相互に追加して、複数の結合を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ac967-129">Any number of join operations can be appended to each other to perform a multiple join.</span></span> <span data-ttu-id="ac967-130">C# の各 `join` 句は、指定されたデータ ソースを前の結合の結果に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="ac967-130">Each `join` clause in C# correlates a specified data source with the results of the previous join.</span></span>

<span data-ttu-id="ac967-131">次の例は、`Person` オブジェクトのリスト、`Cat` オブジェクトのリスト、`Dog` オブジェクトのリストの 3 つのコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac967-131">The following example creates three collections: a list of `Person` objects, a list of `Cat` objects, and a list of `Dog` objects.</span></span>

<span data-ttu-id="ac967-132">C# の最初の `join` 句では、`Person` と一致する `Cat.Owner` オブジェクトに基づいて飼い主と猫を一致させます。</span><span class="sxs-lookup"><span data-stu-id="ac967-132">The first `join` clause in C# matches people and cats based on a `Person` object matching `Cat.Owner`.</span></span> <span data-ttu-id="ac967-133">この操作で、`Person` オブジェクトと `Cat.Name` が含まれた匿名型のシーケンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-133">It returns a sequence of anonymous types that contain the `Person` object and `Cat.Name`.</span></span>

<span data-ttu-id="ac967-134">C# の 2 番目の `join` 句では、`Dog` 型の `Owner` プロパティと動物の名前の最初の文字で構成される複合キーに基づいて、最初の結合で返された匿名型を、指定された犬のリストの `Person` オブジェクトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="ac967-134">The second `join` clause in C# correlates the anonymous types returned by the first join with `Dog` objects in the supplied list of dogs, based on a composite key that consists of the `Owner` property of type `Person`, and the first letter of the animal's name.</span></span> <span data-ttu-id="ac967-135">この操作で、一致するそれぞれのペアの `Cat.Name` プロパティと `Dog.Name` プロパティが含まれた匿名型のシーケンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-135">It returns a sequence of anonymous types that contain the `Cat.Name` and `Dog.Name` properties from each matching pair.</span></span> <span data-ttu-id="ac967-136">これは内部結合であるため、2 番目のデータ ソースに一致するものが存在する、最初のデータ ソースのオブジェクトのみが返されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-136">Because this is an inner join, only those objects from the first data source that have a match in the second data source are returned.</span></span>

[!code-csharp[CsLINQProgJoining#3](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_3.cs)]

## <a name="example---inner-join-by-using-grouped-join"></a><span data-ttu-id="ac967-137">例 - グループ化結合を使用した内部結合</span><span class="sxs-lookup"><span data-stu-id="ac967-137">Example - Inner join by using grouped join</span></span>

<span data-ttu-id="ac967-138">グループ結合を使用して内部結合を実装する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="ac967-138">The following example shows you how to implement an inner join by using a group join.</span></span>

<span data-ttu-id="ac967-139">`query1` で、`Person` オブジェクトのリストは、`Pet` プロパティと一致する `Person` に基づいて、`Pet.Owner` オブジェクトのリストにグループ結合されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-139">In `query1`, the list of `Person` objects is group-joined to the list of `Pet` objects based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="ac967-140">グループ結合によって、それぞれのグループが `Person` オブジェクトおよび一致する `Pet` オブジェクトのシーケンスで構成された、中間グループのコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-140">The group join creates a collection of intermediate groups, where each group consists of a `Person` object and a sequence of matching `Pet` objects.</span></span>

<span data-ttu-id="ac967-141">2 番目の `from` 句をクエリに追加すると、シーケンスのシーケンスが 1 つの長いシーケンスに結合 (または平坦化) されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-141">By adding a second `from` clause to the query, this sequence of sequences is combined (or flattened) into one longer sequence.</span></span> <span data-ttu-id="ac967-142">最後のシーケンスの要素の型は、`select` 句で指定されます。</span><span class="sxs-lookup"><span data-stu-id="ac967-142">The type of the elements of the final sequence is specified by the `select` clause.</span></span> <span data-ttu-id="ac967-143">この例では、この型は、一致する各ペアの `Person.FirstName` プロパティと `Pet.Name` プロパティで構成された匿名型です。</span><span class="sxs-lookup"><span data-stu-id="ac967-143">In this example, that type is an anonymous type that consists of the `Person.FirstName` and `Pet.Name` properties for each matching pair.</span></span>

<span data-ttu-id="ac967-144">`query1` の結果は、`join` 句のない `into` 句を使用して内部結合を実行することで得られた結果セットと同じです。</span><span class="sxs-lookup"><span data-stu-id="ac967-144">The result of `query1` is equivalent to the result set that would have been obtained by using the `join` clause without the `into` clause to perform an inner join.</span></span> <span data-ttu-id="ac967-145">`query2` 変数は、これと同等のクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ac967-145">The `query2` variable demonstrates this equivalent query.</span></span>

[!code-csharp[CsLINQProgJoining#4](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_4.cs)]

## <a name="see-also"></a><span data-ttu-id="ac967-146">参照</span><span class="sxs-lookup"><span data-stu-id="ac967-146">See also</span></span>

- <xref:System.Linq.Enumerable.Join%2A>
- <xref:System.Linq.Enumerable.GroupJoin%2A>
- [<span data-ttu-id="ac967-147">グループ化結合の実行</span><span class="sxs-lookup"><span data-stu-id="ac967-147">Perform grouped joins</span></span>](perform-grouped-joins.md)
- [<span data-ttu-id="ac967-148">左外部結合の実行</span><span class="sxs-lookup"><span data-stu-id="ac967-148">Perform left outer joins</span></span>](perform-left-outer-joins.md)
- [<span data-ttu-id="ac967-149">匿名型</span><span class="sxs-lookup"><span data-stu-id="ac967-149">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)
