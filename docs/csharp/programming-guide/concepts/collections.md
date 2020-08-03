---
title: コレクション (C#)
description: オブジェクトのグループをより柔軟に処理するために使用する C# のコレクションについて説明します。 コレクションは、アプリケーションの変更に伴う必要に応じて、動的に拡大および縮小できます。
ms.date: 07/20/2015
ms.assetid: 317d7dc3-8587-4873-8b3e-556f86497939
ms.openlocfilehash: 2375980e2915d4daa5a221a94eee2aea41959852
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924930"
---
# <a name="collections-c"></a><span data-ttu-id="f929d-104">コレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="f929d-104">Collections (C#)</span></span>

<span data-ttu-id="f929d-105">多くのアプリケーションで、関連するオブジェクトのグループの作成および管理が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f929d-105">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="f929d-106">オブジェクトをグループ化するには、オブジェクトの配列を作成する方法と、オブジェクトのコレクションを作成する方法があります。</span><span class="sxs-lookup"><span data-stu-id="f929d-106">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>

<span data-ttu-id="f929d-107">配列は、数が固定されている厳密に型指定されたオブジェクトの作成および処理に最も適しています。</span><span class="sxs-lookup"><span data-stu-id="f929d-107">Arrays are most useful for creating and working with a fixed number of strongly typed objects.</span></span> <span data-ttu-id="f929d-108">配列の詳細については、「[配列](../arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f929d-108">For information about arrays, see [Arrays](../arrays/index.md).</span></span>

<span data-ttu-id="f929d-109">コレクションは、オブジェクトのグループをより柔軟に処理できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-109">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="f929d-110">配列の場合とは違って、コレクションで扱うオブジェクトのグループは、アプリケーションの変更に伴う必要に応じて動的に拡大および縮小できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-110">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="f929d-111">コレクションによっては、コレクションに含まれるオブジェクトのキーを割り当てると、そのキーを使用してオブジェクトを迅速に取り出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f929d-111">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>

<span data-ttu-id="f929d-112">コレクションはクラスであるため、そのコレクションに要素を追加するには、事前にそのクラスのインスタンスを宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f929d-112">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>

<span data-ttu-id="f929d-113">含まれる要素が 1 つのデータ型だけのコレクションの場合は、<xref:System.Collections.Generic?displayProperty=nameWithType> 名前空間のクラスのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-113">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="f929d-114">ジェネリック コレクションでは、タイプ セーフが強制されるため、他のデータ型を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="f929d-114">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="f929d-115">ジェネリック コレクションから要素を取得する場合は、データ型を判断したり、変換したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f929d-115">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>

> [!NOTE]
> <span data-ttu-id="f929d-116">このトピックの例には、`System.Collections.Generic` 名前空間および `System.Linq` 名前空間の [using](../../language-reference/keywords/using-directive.md) ディレクティブがあります。</span><span class="sxs-lookup"><span data-stu-id="f929d-116">For the examples in this topic, include [using](../../language-reference/keywords/using-directive.md) directives for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>

 <span data-ttu-id="f929d-117">**このトピックの内容**</span><span class="sxs-lookup"><span data-stu-id="f929d-117">**In this topic**</span></span>

- [<span data-ttu-id="f929d-118">単純なコレクションを使用する</span><span class="sxs-lookup"><span data-stu-id="f929d-118">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)

- [<span data-ttu-id="f929d-119">コレクションの種類</span><span class="sxs-lookup"><span data-stu-id="f929d-119">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)

  - [<span data-ttu-id="f929d-120">System.Collections.Generic のクラス</span><span class="sxs-lookup"><span data-stu-id="f929d-120">System.Collections.Generic Classes</span></span>](#BKMK_Generic)

  - [<span data-ttu-id="f929d-121">System.Collections.Concurrent のクラス</span><span class="sxs-lookup"><span data-stu-id="f929d-121">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)

  - [<span data-ttu-id="f929d-122">System.Collections のクラス</span><span class="sxs-lookup"><span data-stu-id="f929d-122">System.Collections Classes</span></span>](#BKMK_Collections)

- [<span data-ttu-id="f929d-123">キーと値のペアのコレクションを実装する</span><span class="sxs-lookup"><span data-stu-id="f929d-123">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)

- [<span data-ttu-id="f929d-124">LINQ を使用してコレクションにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f929d-124">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)

- [<span data-ttu-id="f929d-125">コレクションを並べ替える</span><span class="sxs-lookup"><span data-stu-id="f929d-125">Sorting a Collection</span></span>](#BKMK_Sorting)

- [<span data-ttu-id="f929d-126">カスタム コレクションを定義する</span><span class="sxs-lookup"><span data-stu-id="f929d-126">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)

- [<span data-ttu-id="f929d-127">反復子</span><span class="sxs-lookup"><span data-stu-id="f929d-127">Iterators</span></span>](#BKMK_Iterators)

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a><span data-ttu-id="f929d-128">単純なコレクションを使用する</span><span class="sxs-lookup"><span data-stu-id="f929d-128">Using a Simple Collection</span></span>

<span data-ttu-id="f929d-129">このセクションの例は、厳密に型指定されたオブジェクトの一覧を使用できる、ジェネリックの <xref:System.Collections.Generic.List%601> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f929d-129">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>

<span data-ttu-id="f929d-130">次の例は、文字列の一覧を作成した後、[foreach](../../language-reference/keywords/foreach-in.md) ステートメントを使用して文字列を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="f929d-130">The following example creates a list of strings and then iterates through the strings by using a [foreach](../../language-reference/keywords/foreach-in.md) statement.</span></span>

```csharp
// Create a list of strings.
var salmons = new List<string>();
salmons.Add("chinook");
salmons.Add("coho");
salmons.Add("pink");
salmons.Add("sockeye");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="f929d-131">コレクションのコンテンツが既知の場合、コレクションの初期化に*コレクション初期化子*を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-131">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="f929d-132">詳細については、「[オブジェクト初期化子とコレクション初期化子](../classes-and-structs/object-and-collection-initializers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f929d-132">For more information, see [Object and Collection Initializers](../classes-and-structs/object-and-collection-initializers.md).</span></span>

<span data-ttu-id="f929d-133">次の例は、コレクションへの要素の追加にコレクション初期化子を使用する以外、前の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="f929d-133">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="f929d-134">コレクションを反復処理するには、`foreach` ステートメントの代わりに、[for](../../language-reference/keywords/for.md) ステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-134">You can use a [for](../../language-reference/keywords/for.md) statement instead of a `foreach` statement to iterate through a collection.</span></span> <span data-ttu-id="f929d-135">インデックス位置によってコレクションの要素にアクセスすることで、これを実現します。</span><span class="sxs-lookup"><span data-stu-id="f929d-135">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="f929d-136">要素のインデックスは、0 から開始し、要素の数から 1 少ない値で終了します。</span><span class="sxs-lookup"><span data-stu-id="f929d-136">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>

<span data-ttu-id="f929d-137">次の例は、`for` の代わりに `foreach` を使用して、コレクションの要素を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="f929d-137">The following example iterates through the elements of a collection by using `for` instead of `foreach`.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

for (var index = 0; index < salmons.Count; index++)
{
    Console.Write(salmons[index] + " ");
}
// Output: chinook coho pink sockeye
```

<span data-ttu-id="f929d-138">次の例は、削除するオブジェクトを指定して、コレクションから要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="f929d-138">The following example removes an element from the collection by specifying the object to remove.</span></span>

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Remove an element from the list by specifying
// the object.
salmons.Remove("coho");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook pink sockeye
```

<span data-ttu-id="f929d-139">次の例では、ジェネリック リストからすべての要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="f929d-139">The following example removes elements from a generic list.</span></span> <span data-ttu-id="f929d-140">`foreach` ステートメントの代わりに、降順に反復する [for](../../language-reference/keywords/for.md) ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f929d-140">Instead of a `foreach` statement, a [for](../../language-reference/keywords/for.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="f929d-141">これは、<xref:System.Collections.Generic.List%601.RemoveAt%2A> メソッドを実行すると、削除された要素の後にある各要素のインデックス値が小さくなるためです。</span><span class="sxs-lookup"><span data-stu-id="f929d-141">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>

```csharp
var numbers = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

// Remove odd numbers.
for (var index = numbers.Count - 1; index >= 0; index--)
{
    if (numbers[index] % 2 == 1)
    {
        // Remove the element by specifying
        // the zero-based index in the list.
        numbers.RemoveAt(index);
    }
}

// Iterate through the list.
// A lambda expression is placed in the ForEach method
// of the List(T) object.
numbers.ForEach(
    number => Console.Write(number + " "));
// Output: 0 2 4 6 8
```

<span data-ttu-id="f929d-142"><xref:System.Collections.Generic.List%601> の要素の型は、独自のクラスでも定義できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-142">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="f929d-143">次の例では、`Galaxy` が使用する <xref:System.Collections.Generic.List%601> クラスがコードに定義されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-143">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>

```csharp
private static void IterateThroughList()
{
    var theGalaxies = new List<Galaxy>
        {
            new Galaxy() { Name="Tadpole", MegaLightYears=400},
            new Galaxy() { Name="Pinwheel", MegaLightYears=25},
            new Galaxy() { Name="Milky Way", MegaLightYears=0},
            new Galaxy() { Name="Andromeda", MegaLightYears=3}
        };

    foreach (Galaxy theGalaxy in theGalaxies)
    {
        Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears);
    }

    // Output:
    //  Tadpole  400
    //  Pinwheel  25
    //  Milky Way  0
    //  Andromeda  3
}

public class Galaxy
{
    public string Name { get; set; }
    public int MegaLightYears { get; set; }
}
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a><span data-ttu-id="f929d-144">コレクションの種類</span><span class="sxs-lookup"><span data-stu-id="f929d-144">Kinds of Collections</span></span>

<span data-ttu-id="f929d-145">.NET は、多くの共通のコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="f929d-145">Many common collections are provided by .NET.</span></span> <span data-ttu-id="f929d-146">各コレクションの型は、固有の目的に合わせてデザインされています。</span><span class="sxs-lookup"><span data-stu-id="f929d-146">Each type of collection is designed for a specific purpose.</span></span>

<span data-ttu-id="f929d-147">このセクションでは、次の共通のコレクション クラスをいつくか説明します:</span><span class="sxs-lookup"><span data-stu-id="f929d-147">Some of the common collection classes are described in this section:</span></span>

- <span data-ttu-id="f929d-148"><xref:System.Collections.Generic> クラス</span><span class="sxs-lookup"><span data-stu-id="f929d-148"><xref:System.Collections.Generic> classes</span></span>

- <span data-ttu-id="f929d-149"><xref:System.Collections.Concurrent> クラス</span><span class="sxs-lookup"><span data-stu-id="f929d-149"><xref:System.Collections.Concurrent> classes</span></span>

- <span data-ttu-id="f929d-150"><xref:System.Collections> クラス</span><span class="sxs-lookup"><span data-stu-id="f929d-150"><xref:System.Collections> classes</span></span>

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="f929d-151">System.Collections.Generic のクラス</span><span class="sxs-lookup"><span data-stu-id="f929d-151">System.Collections.Generic Classes</span></span>

<span data-ttu-id="f929d-152"><xref:System.Collections.Generic> 名前空間の 1 つのクラスを使用すると、ジェネリック コレクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-152">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="f929d-153">ジェネリック コレクションは、コレクション内のすべての項目が同じデータ型である場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f929d-153">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="f929d-154">ジェネリック コレクションには該当するデータ型しか追加できないため、厳密な型指定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-154">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>

<span data-ttu-id="f929d-155">次のテーブルは <xref:System.Collections.Generic?displayProperty=nameWithType> 名前空間でよく使用されるクラスの一覧です:</span><span class="sxs-lookup"><span data-stu-id="f929d-155">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="f929d-156">クラス</span><span class="sxs-lookup"><span data-stu-id="f929d-156">Class</span></span>|<span data-ttu-id="f929d-157">説明</span><span class="sxs-lookup"><span data-stu-id="f929d-157">Description</span></span>|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|<span data-ttu-id="f929d-158">キーに基づいて編成された、キーと値のペアのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-158">Represents a collection of key/value pairs that are organized based on the key.</span></span>|
|<xref:System.Collections.Generic.List%601>|<span data-ttu-id="f929d-159">インデックスを使用してアクセスできる、オブジェクトの一覧を表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-159">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="f929d-160">リストの検索、並べ替え、および変更のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="f929d-160">Provides methods to search, sort, and modify lists.</span></span>|
|<xref:System.Collections.Generic.Queue%601>|<span data-ttu-id="f929d-161">先入れ先出し (FIFO) のオブジェクトのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-161">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Generic.SortedList%602>|<span data-ttu-id="f929d-162">関連付けられた <xref:System.Collections.Generic.IComparer%601> 実装に基づいて、キーにより並べ替えられた、キーと値のペアのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-162">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|
|<xref:System.Collections.Generic.Stack%601>|<span data-ttu-id="f929d-163">後入れ先出し (LIFO) のオブジェクトのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-163">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="f929d-164">詳細については、「[一般的に使用されるコレクション型](../../../standard/collections/commonly-used-collection-types.md)」、「[コレクション クラスの選択](../../../standard/collections/selecting-a-collection-class.md)」、「<xref:System.Collections.Generic>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f929d-164">For additional information, see [Commonly Used Collection Types](../../../standard/collections/commonly-used-collection-types.md), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic>.</span></span>

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="f929d-165">System.Collections.Concurrent のクラス</span><span class="sxs-lookup"><span data-stu-id="f929d-165">System.Collections.Concurrent Classes</span></span>

<span data-ttu-id="f929d-166">.NET Framework 4 以降のバージョンでは、<xref:System.Collections.Concurrent> 名前空間のコレクションによって、複数のスレッドからコレクション項目にアクセスするための効率的なスレッド セーフ操作が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f929d-166">In .NET Framework 4 and later versions, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>

<span data-ttu-id="f929d-167"><xref:System.Collections.Concurrent> 名前空間のクラスは、複数のスレッドがコレクションに同時にアクセスするときに、<xref:System.Collections.Generic?displayProperty=nameWithType> 名前空間および <xref:System.Collections?displayProperty=nameWithType> 名前空間の対応する型の代わりに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f929d-167">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=nameWithType> and <xref:System.Collections?displayProperty=nameWithType> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="f929d-168">詳しくは、「[スレッド セーフなコレクション](../../../standard/collections/thread-safe/index.md)」と「<xref:System.Collections.Concurrent>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f929d-168">For more information, see [Thread-Safe Collections](../../../standard/collections/thread-safe/index.md) and <xref:System.Collections.Concurrent>.</span></span>

<span data-ttu-id="f929d-169"><xref:System.Collections.Concurrent> 名前空間には、<xref:System.Collections.Concurrent.BlockingCollection%601>、<xref:System.Collections.Concurrent.ConcurrentDictionary%602>、<xref:System.Collections.Concurrent.ConcurrentQueue%601>、および <xref:System.Collections.Concurrent.ConcurrentStack%601> などのクラスがあります。</span><span class="sxs-lookup"><span data-stu-id="f929d-169">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a><span data-ttu-id="f929d-170">System.Collections のクラス</span><span class="sxs-lookup"><span data-stu-id="f929d-170">System.Collections Classes</span></span>

<span data-ttu-id="f929d-171"><xref:System.Collections?displayProperty=nameWithType> 名前空間のクラスでは、要素は、固有の型のオブジェクトとしてではなく `Object` 型のオブジェクトとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-171">The classes in the <xref:System.Collections?displayProperty=nameWithType> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>

<span data-ttu-id="f929d-172">できる限り、<xref:System.Collections.Generic?displayProperty=nameWithType> 名前空間の従来の型の代わりに、<xref:System.Collections.Concurrent> 名前空間または `System.Collections` 名前空間のジェネリック コレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f929d-172">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>

<span data-ttu-id="f929d-173">次のテーブルは `System.Collections` 名前空間でよく使用されるクラスの一覧です:</span><span class="sxs-lookup"><span data-stu-id="f929d-173">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>

|<span data-ttu-id="f929d-174">クラス</span><span class="sxs-lookup"><span data-stu-id="f929d-174">Class</span></span>|<span data-ttu-id="f929d-175">説明</span><span class="sxs-lookup"><span data-stu-id="f929d-175">Description</span></span>|
|---|---|
|<xref:System.Collections.ArrayList>|<span data-ttu-id="f929d-176">必要に応じてサイズが動的に拡大されるオブジェクトの配列を表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-176">Represents an array of objects whose size is dynamically increased as required.</span></span>|
|<xref:System.Collections.Hashtable>|<span data-ttu-id="f929d-177">キーのハッシュ コードに基づいて編成された、キーと値のペアのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-177">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|
|<xref:System.Collections.Queue>|<span data-ttu-id="f929d-178">先入れ先出し (FIFO) のオブジェクトのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-178">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Stack>|<span data-ttu-id="f929d-179">後入れ先出し (LIFO) のオブジェクトのコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="f929d-179">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="f929d-180"><xref:System.Collections.Specialized> 名前空間には、文字列専用のコレクションやリンク リスト、ハイブリッド ディクショナリなど、厳密に型指定された専用のコレクション クラスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f929d-180">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="f929d-181">キーと値のペアのコレクションを実装する</span><span class="sxs-lookup"><span data-stu-id="f929d-181">Implementing a Collection of Key/Value Pairs</span></span>

<span data-ttu-id="f929d-182"><xref:System.Collections.Generic.Dictionary%602> ジェネリック コレクションでは、各要素のキーを使用してコレクションの要素にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f929d-182">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="f929d-183">ディクショナリに追加される各エントリは、値とその値に関連付けられたキーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-183">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="f929d-184">`Dictionary` クラスはハッシュ テーブルとして実装されているため、キーを使用した値の取得は非常に高速になります。</span><span class="sxs-lookup"><span data-stu-id="f929d-184">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>

<span data-ttu-id="f929d-185">次の例では `Dictionary` のコレクションを作成し、`foreach` ステートメントを使用してディクショナリを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="f929d-185">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `foreach` statement.</span></span>

```csharp
private static void IterateThruDictionary()
{
    Dictionary<string, Element> elements = BuildDictionary();

    foreach (KeyValuePair<string, Element> kvp in elements)
    {
        Element theElement = kvp.Value;

        Console.WriteLine("key: " + kvp.Key);
        Console.WriteLine("values: " + theElement.Symbol + " " +
            theElement.Name + " " + theElement.AtomicNumber);
    }
}

private static Dictionary<string, Element> BuildDictionary()
{
    var elements = new Dictionary<string, Element>();

    AddToDictionary(elements, "K", "Potassium", 19);
    AddToDictionary(elements, "Ca", "Calcium", 20);
    AddToDictionary(elements, "Sc", "Scandium", 21);
    AddToDictionary(elements, "Ti", "Titanium", 22);

    return elements;
}

private static void AddToDictionary(Dictionary<string, Element> elements,
    string symbol, string name, int atomicNumber)
{
    Element theElement = new Element();

    theElement.Symbol = symbol;
    theElement.Name = name;
    theElement.AtomicNumber = atomicNumber;

    elements.Add(key: theElement.Symbol, value: theElement);
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<span data-ttu-id="f929d-186">コレクション初期化子を使用して `Dictionary` コレクションをビルドする代わりに、`BuildDictionary` および `AddToDictionary` メソッドを次のメソッドに置換できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-186">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>

```csharp
private static Dictionary<string, Element> BuildDictionary2()
{
    return new Dictionary<string, Element>
    {
        {"K",
            new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        {"Ca",
            new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        {"Sc",
            new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        {"Ti",
            new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}
```

<span data-ttu-id="f929d-187">次の例では、キーによって項目をすばやく検索するために、<xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> の <xref:System.Collections.Generic.Dictionary%602.Item%2A> メソッドと `Dictionary` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f929d-187">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="f929d-188">`Item` プロパティでは、C# の `elements[symbol]` を使用して `elements` コレクションの項目にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f929d-188">The `Item` property enables you to access an item in the `elements` collection by using the `elements[symbol]` in C#.</span></span>

```csharp
private static void FindInDictionary(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    if (elements.ContainsKey(symbol) == false)
    {
        Console.WriteLine(symbol + " not found");
    }
    else
    {
        Element theElement = elements[symbol];
        Console.WriteLine("found: " + theElement.Name);
    }
}
```

<span data-ttu-id="f929d-189">次の例では、キーによって項目をすばやく検索するために、<xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> メソッドを代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="f929d-189">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>

```csharp
private static void FindInDictionary2(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    Element theElement = null;
    if (elements.TryGetValue(symbol, out theElement) == false)
        Console.WriteLine(symbol + " not found");
    else
        Console.WriteLine("found: " + theElement.Name);
}
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="f929d-190">LINQ を使用してコレクションにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f929d-190">Using LINQ to Access a Collection</span></span>

<span data-ttu-id="f929d-191">統合言語クエリ (LINQ) を使用してコレクションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f929d-191">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="f929d-192">LINQ クエリは、フィルター処理、並べ替え、およびグループ化の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f929d-192">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="f929d-193">詳細については、[C# での LINQ の概要](linq/index.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f929d-193">For more information, see [Getting Started with LINQ in C#](linq/index.md).</span></span>

<span data-ttu-id="f929d-194">次の例では、ジェネリック `List` に対して LINQ クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f929d-194">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="f929d-195">LINQ クエリは、結果が格納されている別のコレクションを戻します。</span><span class="sxs-lookup"><span data-stu-id="f929d-195">The LINQ query returns a different collection that contains the results.</span></span>

```csharp
private static void ShowLINQ()
{
    List<Element> elements = BuildList();

    // LINQ Query.
    var subset = from theElement in elements
                 where theElement.AtomicNumber < 22
                 orderby theElement.Name
                 select theElement;

    foreach (Element theElement in subset)
    {
        Console.WriteLine(theElement.Name + " " + theElement.AtomicNumber);
    }

    // Output:
    //  Calcium 20
    //  Potassium 19
    //  Scandium 21
}

private static List<Element> BuildList()
{
    return new List<Element>
    {
        { new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        { new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        { new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        { new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a><span data-ttu-id="f929d-196">コレクションを並べ替える</span><span class="sxs-lookup"><span data-stu-id="f929d-196">Sorting a Collection</span></span>

<span data-ttu-id="f929d-197">次の例では、コレクションを並べ替えるための手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="f929d-197">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="f929d-198">この例は、`Car` に格納されている <xref:System.Collections.Generic.List%601> クラスのインスタンスの並べ替えを実行します。</span><span class="sxs-lookup"><span data-stu-id="f929d-198">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="f929d-199">`Car` クラスは、<xref:System.IComparable%601> のメソッドの実装を必要とする <xref:System.IComparable%601.CompareTo%2A> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f929d-199">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>

<span data-ttu-id="f929d-200"><xref:System.IComparable%601.CompareTo%2A> メソッドに対する各呼び出しは、並べ替えに使用される単一の比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="f929d-200">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="f929d-201">`CompareTo` メソッドのユーザーが作成したコードは、現在のオブジェクトと別のオブジェクトとの各比較の値を戻します。</span><span class="sxs-lookup"><span data-stu-id="f929d-201">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="f929d-202">現在のオブジェクトが別のオブジェクトよりも小さい場合はゼロ未満の値を、大きい場合はゼロ以上の値を、等しい場合はゼロを戻します。</span><span class="sxs-lookup"><span data-stu-id="f929d-202">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="f929d-203">これによって、より大きい、より小さい、等しい、の条件をコードに定義することができます。</span><span class="sxs-lookup"><span data-stu-id="f929d-203">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>

<span data-ttu-id="f929d-204">`ListCars` のメソッドでは、`cars.Sort()` ステートメントがリストを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="f929d-204">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="f929d-205"><xref:System.Collections.Generic.List%601.Sort%2A> の <xref:System.Collections.Generic.List%601> メソッドへの呼び出しによって、`CompareTo` メソッドは `Car` 内の `List` オブジェクトに自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-205">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>

```csharp
private static void ListCars()
{
    var cars = new List<Car>
    {
        { new Car() { Name = "car1", Color = "blue", Speed = 20}},
        { new Car() { Name = "car2", Color = "red", Speed = 50}},
        { new Car() { Name = "car3", Color = "green", Speed = 10}},
        { new Car() { Name = "car4", Color = "blue", Speed = 50}},
        { new Car() { Name = "car5", Color = "blue", Speed = 30}},
        { new Car() { Name = "car6", Color = "red", Speed = 60}},
        { new Car() { Name = "car7", Color = "green", Speed = 50}}
    };

    // Sort the cars by color alphabetically, and then by speed
    // in descending order.
    cars.Sort();

    // View all of the cars.
    foreach (Car thisCar in cars)
    {
        Console.Write(thisCar.Color.PadRight(5) + " ");
        Console.Write(thisCar.Speed.ToString() + " ");
        Console.Write(thisCar.Name);
        Console.WriteLine();
    }

    // Output:
    //  blue  50 car4
    //  blue  30 car5
    //  blue  20 car1
    //  green 50 car7
    //  green 10 car3
    //  red   60 car6
    //  red   50 car2
}

public class Car : IComparable<Car>
{
    public string Name { get; set; }
    public int Speed { get; set; }
    public string Color { get; set; }

    public int CompareTo(Car other)
    {
        // A call to this method makes a single comparison that is
        // used for sorting.

        // Determine the relative order of the objects being compared.
        // Sort by color alphabetically, and then by speed in
        // descending order.

        // Compare the colors.
        int compare;
        compare = String.Compare(this.Color, other.Color, true);

        // If the colors are the same, compare the speeds.
        if (compare == 0)
        {
            compare = this.Speed.CompareTo(other.Speed);

            // Use descending order for speed.
            compare = -compare;
        }

        return compare;
    }
}
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a><span data-ttu-id="f929d-206">カスタム コレクションを定義する</span><span class="sxs-lookup"><span data-stu-id="f929d-206">Defining a Custom Collection</span></span>

<span data-ttu-id="f929d-207"><xref:System.Collections.Generic.IEnumerable%601> または <xref:System.Collections.IEnumerable> のインターフェイスを実装してコレクションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f929d-207">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span>

<span data-ttu-id="f929d-208">カスタム コレクションを定義できますが、通常は、.NET に含まれるコレクションを使用することが推奨されます。これについては、この記事の[コレクションの種類](#BKMK_KindsOfCollections)で既に説明されています。</span><span class="sxs-lookup"><span data-stu-id="f929d-208">Although you can define a custom collection, it is usually better to instead use the collections that are included in .NET, which are described in [Kinds of Collections](#BKMK_KindsOfCollections) earlier in this article.</span></span>

<span data-ttu-id="f929d-209">次の例は、`AllColors` という名前のカスタム コレクション クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="f929d-209">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="f929d-210">このクラスは、<xref:System.Collections.IEnumerable> メソッドの実装を必要とする <xref:System.Collections.IEnumerable.GetEnumerator%2A> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f929d-210">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>

<span data-ttu-id="f929d-211">`GetEnumerator` メソッドは、`ColorEnumerator` クラスのインスタンスを戻します。</span><span class="sxs-lookup"><span data-stu-id="f929d-211">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="f929d-212">`ColorEnumerator` は、<xref:System.Collections.IEnumerator> プロパティ、<xref:System.Collections.IEnumerator.Current%2A> メソッド、および <xref:System.Collections.IEnumerator.MoveNext%2A> メソッドの実装を必要とする <xref:System.Collections.IEnumerator.Reset%2A> インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f929d-212">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>

```csharp
private static void ListColors()
{
    var colors = new AllColors();

    foreach (Color theColor in colors)
    {
        Console.Write(theColor.Name + " ");
    }
    Console.WriteLine();
    // Output: red blue green
}

// Collection class.
public class AllColors : System.Collections.IEnumerable
{
    Color[] _colors =
    {
        new Color() { Name = "red" },
        new Color() { Name = "blue" },
        new Color() { Name = "green" }
    };

    public System.Collections.IEnumerator GetEnumerator()
    {
        return new ColorEnumerator(_colors);

        // Instead of creating a custom enumerator, you could
        // use the GetEnumerator of the array.
        //return _colors.GetEnumerator();
    }

    // Custom enumerator.
    private class ColorEnumerator : System.Collections.IEnumerator
    {
        private Color[] _colors;
        private int _position = -1;

        public ColorEnumerator(Color[] colors)
        {
            _colors = colors;
        }

        object System.Collections.IEnumerator.Current
        {
            get
            {
                return _colors[_position];
            }
        }

        bool System.Collections.IEnumerator.MoveNext()
        {
            _position++;
            return (_position < _colors.Length);
        }

        void System.Collections.IEnumerator.Reset()
        {
            _position = -1;
        }
    }
}

// Element class.
public class Color
{
    public string Name { get; set; }
}
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a><span data-ttu-id="f929d-213">Iterators</span><span class="sxs-lookup"><span data-stu-id="f929d-213">Iterators</span></span>

<span data-ttu-id="f929d-214">*反復子*は、コレクションに対するカスタム イテレーションを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-214">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="f929d-215">反復子は、メソッドまたは `get` アクセサーのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="f929d-215">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="f929d-216">反復子は、[yield return](../../language-reference/keywords/yield.md) ステートメントを使用して、コレクションの各要素を 1 回に 1 つ返します。</span><span class="sxs-lookup"><span data-stu-id="f929d-216">An iterator uses a [yield return](../../language-reference/keywords/yield.md) statement to return each element of the collection one at a time.</span></span>

<span data-ttu-id="f929d-217">[foreach](../../language-reference/keywords/foreach-in.md) ステートメントを使用して、反復子を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f929d-217">You call an iterator by using a [foreach](../../language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="f929d-218">`foreach` ループの各イテレーションは、反復子を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f929d-218">Each iteration of the `foreach` loop calls the iterator.</span></span> <span data-ttu-id="f929d-219">`yield return` ステートメントが反復子に到達すると、式が戻され、コードの現在の位置が保持されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-219">When a `yield return` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="f929d-220">次回、反復子が呼び出されると、この位置から実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-220">Execution is restarted from that location the next time that the iterator is called.</span></span>

<span data-ttu-id="f929d-221">詳細については、「[反復子 (C#)](./iterators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f929d-221">For more information, see [Iterators (C#)](./iterators.md).</span></span>

<span data-ttu-id="f929d-222">次の例は、反復子メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f929d-222">The following example uses an iterator method.</span></span> <span data-ttu-id="f929d-223">反復子メソッドには、[for](../../language-reference/keywords/for.md) ループ内に `yield return` ステートメントがあります。</span><span class="sxs-lookup"><span data-stu-id="f929d-223">The iterator method has a `yield return` statement that is inside a [for](../../language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="f929d-224">`ListEvenNumbers` メソッドでは、`foreach` ステートメント本文の各イテレーションが、反復子メソッドの呼び出しを作成し、これが次の `yield return` ステートメントに続行されます。</span><span class="sxs-lookup"><span data-stu-id="f929d-224">In the `ListEvenNumbers` method, each iteration of the `foreach` statement body creates a call to the iterator method, which proceeds to the next `yield return` statement.</span></span>

```csharp
private static void ListEvenNumbers()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    Console.WriteLine();
    // Output: 6 8 10 12 14 16 18
}

private static IEnumerable<int> EvenSequence(
    int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (var number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f929d-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="f929d-225">See also</span></span>

- [<span data-ttu-id="f929d-226">オブジェクト初期化子とコレクション初期化子</span><span class="sxs-lookup"><span data-stu-id="f929d-226">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="f929d-227">プログラミングの概念 (C#)</span><span class="sxs-lookup"><span data-stu-id="f929d-227">Programming Concepts (C#)</span></span>](./index.md)
- [<span data-ttu-id="f929d-228">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="f929d-228">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="f929d-229">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="f929d-229">LINQ to Objects (C#)</span></span>](./linq/linq-to-objects.md)
- [<span data-ttu-id="f929d-230">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="f929d-230">Parallel LINQ (PLINQ)</span></span>](../../../standard/parallel-programming/introduction-to-plinq.md)
- [<span data-ttu-id="f929d-231">コレクションとデータ構造体</span><span class="sxs-lookup"><span data-stu-id="f929d-231">Collections and Data Structures</span></span>](../../../standard/collections/index.md)
- [<span data-ttu-id="f929d-232">コレクション クラスの選択</span><span class="sxs-lookup"><span data-stu-id="f929d-232">Selecting a Collection Class</span></span>](../../../standard/collections/selecting-a-collection-class.md)
- [<span data-ttu-id="f929d-233">コレクション内での比較と並べ替え</span><span class="sxs-lookup"><span data-stu-id="f929d-233">Comparisons and Sorts Within Collections</span></span>](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [<span data-ttu-id="f929d-234">ジェネリック コレクションを使用する状況</span><span class="sxs-lookup"><span data-stu-id="f929d-234">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)
