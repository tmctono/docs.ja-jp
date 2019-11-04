---
title: データ型の変換 (C#)
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: ddd9407c3b7e25dbfb8fc0bddb5daab7db2e4e53
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418614"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="8c771-102">データ型の変換 (C#)</span><span class="sxs-lookup"><span data-stu-id="8c771-102">Converting Data Types (C#)</span></span>
<span data-ttu-id="8c771-103">変換メソッドは、入力オブジェクトの型を変更します。</span><span class="sxs-lookup"><span data-stu-id="8c771-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="8c771-104">LINQ クエリの変換操作は、さまざまなアプリケーションで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="8c771-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="8c771-105">次にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="8c771-105">Following are some examples:</span></span>  
  
- <span data-ttu-id="8c771-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> メソッドを使用すると、標準クエリ演算子の型のカスタム実装を非表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8c771-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
- <span data-ttu-id="8c771-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> メソッドを使用すると、LINQ クエリのパラメーター化されていないコレクションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c771-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
- <span data-ttu-id="8c771-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>、および <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> メソッドを使用すると、クエリが列挙されるまで延期させるのではなく、即時のクエリ実行を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="8c771-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c771-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="8c771-109">Methods</span></span>  
 <span data-ttu-id="8c771-110">次の表には、データ型の変換を実行する標準クエリ演算子メソッドの一覧が示されています。</span><span class="sxs-lookup"><span data-stu-id="8c771-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="8c771-111">名前が "As" で始まるこの表の変換メソッドは、ソース コレクションの静的型を変更しますが、ソース コレクションを列挙しません。</span><span class="sxs-lookup"><span data-stu-id="8c771-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="8c771-112">名前が "To" で始まるメソッドは、ソース コレクションを列挙し、各項目を対応するコレクション型に変換します。</span><span class="sxs-lookup"><span data-stu-id="8c771-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="8c771-113">メソッド名</span><span class="sxs-lookup"><span data-stu-id="8c771-113">Method Name</span></span>|<span data-ttu-id="8c771-114">説明</span><span class="sxs-lookup"><span data-stu-id="8c771-114">Description</span></span>|<span data-ttu-id="8c771-115">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="8c771-115">C# Query Expression Syntax</span></span>|<span data-ttu-id="8c771-116">説明</span><span class="sxs-lookup"><span data-stu-id="8c771-116">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="8c771-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="8c771-117">AsEnumerable</span></span>|<span data-ttu-id="8c771-118"><xref:System.Collections.Generic.IEnumerable%601> として型指定された入力を返します。</span><span class="sxs-lookup"><span data-stu-id="8c771-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="8c771-119">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8c771-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c771-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="8c771-120">AsQueryable</span></span>|<span data-ttu-id="8c771-121">(ジェネリック) <xref:System.Collections.IEnumerable> を (ジェネリック) <xref:System.Linq.IQueryable> に変換します。</span><span class="sxs-lookup"><span data-stu-id="8c771-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="8c771-122">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8c771-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c771-123">Cast</span><span class="sxs-lookup"><span data-stu-id="8c771-123">Cast</span></span>|<span data-ttu-id="8c771-124">コレクションの要素を指定した型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="8c771-124">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="8c771-125">明示的に型指定された範囲変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c771-125">Use an explicitly typed range variable.</span></span> <span data-ttu-id="8c771-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8c771-126">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c771-127">OfType</span><span class="sxs-lookup"><span data-stu-id="8c771-127">OfType</span></span>|<span data-ttu-id="8c771-128">指定した型にキャストできるかどうかに応じて値をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="8c771-128">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="8c771-129">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8c771-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c771-130">ToArray</span><span class="sxs-lookup"><span data-stu-id="8c771-130">ToArray</span></span>|<span data-ttu-id="8c771-131">コレクションを配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="8c771-131">Converts a collection to an array.</span></span> <span data-ttu-id="8c771-132">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="8c771-132">This method forces query execution.</span></span>|<span data-ttu-id="8c771-133">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8c771-133">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c771-134">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="8c771-134">ToDictionary</span></span>|<span data-ttu-id="8c771-135">キー セレクター関数に基づいて、<xref:System.Collections.Generic.Dictionary%602> に要素を変換します。</span><span class="sxs-lookup"><span data-stu-id="8c771-135">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="8c771-136">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="8c771-136">This method forces query execution.</span></span>|<span data-ttu-id="8c771-137">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8c771-137">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c771-138">ToList</span><span class="sxs-lookup"><span data-stu-id="8c771-138">ToList</span></span>|<span data-ttu-id="8c771-139">コレクションを <xref:System.Collections.Generic.List%601> に変換します。</span><span class="sxs-lookup"><span data-stu-id="8c771-139">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="8c771-140">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="8c771-140">This method forces query execution.</span></span>|<span data-ttu-id="8c771-141">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8c771-141">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="8c771-142">ToLookup</span><span class="sxs-lookup"><span data-stu-id="8c771-142">ToLookup</span></span>|<span data-ttu-id="8c771-143">キー セレクター関数に基づいて、<xref:System.Linq.Lookup%602> (一対多の辞書) に要素を変換します。</span><span class="sxs-lookup"><span data-stu-id="8c771-143">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="8c771-144">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="8c771-144">This method forces query execution.</span></span>|<span data-ttu-id="8c771-145">該当なし。</span><span class="sxs-lookup"><span data-stu-id="8c771-145">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="8c771-146">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="8c771-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="8c771-147">次のコード例では、サブタイプでのみ使用できるメンバーにアクセスする前に、明示的に型指定された範囲変数を使用して、型をそのサブタイプにキャストしています。</span><span class="sxs-lookup"><span data-stu-id="8c771-147">The following code example uses an explicitly-typed range variable  to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```csharp  
class Plant  
{  
    public string Name { get; set; }  
}  
  
class CarnivorousPlant : Plant  
{  
    public string TrapType { get; set; }  
}  
  
static void Cast()  
{  
    Plant[] plants = new Plant[] {  
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },  
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },  
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },  
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }  
    };  
  
    var query = from CarnivorousPlant cPlant in plants  
                where cPlant.TrapType == "Snap Trap"  
                select cPlant;  
  
    foreach (Plant plant in query)  
        Console.WriteLine(plant.Name);  
  
    /* This code produces the following output:  
  
        Venus Fly Trap  
        Waterwheel Plant  
    */  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c771-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c771-148">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="8c771-149">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="8c771-149">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="8c771-150">from 句</span><span class="sxs-lookup"><span data-stu-id="8c771-150">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="8c771-151">LINQ クエリ式</span><span class="sxs-lookup"><span data-stu-id="8c771-151">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="8c771-152">方法: LINQ を使用して ArrayList を照会する (C#)</span><span class="sxs-lookup"><span data-stu-id="8c771-152">How to: Query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
