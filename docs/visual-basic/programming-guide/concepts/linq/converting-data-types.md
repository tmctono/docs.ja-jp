---
title: データ型の変換 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 744dec0093384a15470186fc09695c17e79468fa
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524228"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="40508-102">データ型の変換 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40508-102">Converting Data Types (Visual Basic)</span></span>

<span data-ttu-id="40508-103">変換メソッドは、入力オブジェクトの型を変更します。</span><span class="sxs-lookup"><span data-stu-id="40508-103">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="40508-104">LINQ クエリの変換操作は、さまざまなアプリケーションで役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="40508-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="40508-105">次に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="40508-105">The following are some examples:</span></span>

- <span data-ttu-id="40508-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> メソッドを使用すると、標準クエリ演算子の型のカスタム実装を非表示することができます。</span><span class="sxs-lookup"><span data-stu-id="40508-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="40508-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> メソッドを使用すると、LINQ クエリのパラメーター化されていないコレクションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="40508-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="40508-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>、<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>、および <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> メソッドを使用すると、クエリが列挙されるまで延期させるのではなく、即時のクエリ実行を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="40508-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="40508-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="40508-109">Methods</span></span>

<span data-ttu-id="40508-110">次の表には、データ型の変換を実行する標準クエリ演算子メソッドの一覧が示されています。</span><span class="sxs-lookup"><span data-stu-id="40508-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

<span data-ttu-id="40508-111">名前が "As" で始まるこの表の変換メソッドは、ソース コレクションの静的型を変更しますが、ソース コレクションを列挙しません。</span><span class="sxs-lookup"><span data-stu-id="40508-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="40508-112">名前が "To" で始まるメソッドは、ソース コレクションを列挙し、各項目を対応するコレクション型に変換します。</span><span class="sxs-lookup"><span data-stu-id="40508-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="40508-113">メソッド名</span><span class="sxs-lookup"><span data-stu-id="40508-113">Method Name</span></span>|<span data-ttu-id="40508-114">説明</span><span class="sxs-lookup"><span data-stu-id="40508-114">Description</span></span>|<span data-ttu-id="40508-115">Visual Basic クエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="40508-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="40508-116">説明</span><span class="sxs-lookup"><span data-stu-id="40508-116">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="40508-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="40508-117">AsEnumerable</span></span>|<span data-ttu-id="40508-118"><xref:System.Collections.Generic.IEnumerable%601> として型指定された入力を返します。</span><span class="sxs-lookup"><span data-stu-id="40508-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="40508-119">該当しない。</span><span class="sxs-lookup"><span data-stu-id="40508-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="40508-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="40508-120">AsQueryable</span></span>|<span data-ttu-id="40508-121">(ジェネリック) <xref:System.Collections.IEnumerable> を (ジェネリック) <xref:System.Linq.IQueryable> に変換します。</span><span class="sxs-lookup"><span data-stu-id="40508-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="40508-122">該当しない。</span><span class="sxs-lookup"><span data-stu-id="40508-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="40508-123">Cast</span><span class="sxs-lookup"><span data-stu-id="40508-123">Cast</span></span>|<span data-ttu-id="40508-124">コレクションの要素を指定した型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="40508-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="40508-125">OfType</span><span class="sxs-lookup"><span data-stu-id="40508-125">OfType</span></span>|<span data-ttu-id="40508-126">指定した型にキャストできるかどうかに応じて値をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="40508-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="40508-127">該当しない。</span><span class="sxs-lookup"><span data-stu-id="40508-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="40508-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="40508-128">ToArray</span></span>|<span data-ttu-id="40508-129">コレクションを配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="40508-129">Converts a collection to an array.</span></span> <span data-ttu-id="40508-130">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="40508-130">This method forces query execution.</span></span>|<span data-ttu-id="40508-131">該当しない。</span><span class="sxs-lookup"><span data-stu-id="40508-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="40508-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="40508-132">ToDictionary</span></span>|<span data-ttu-id="40508-133">キー セレクター関数に基づいて、<xref:System.Collections.Generic.Dictionary%602> に要素を変換します。</span><span class="sxs-lookup"><span data-stu-id="40508-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="40508-134">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="40508-134">This method forces query execution.</span></span>|<span data-ttu-id="40508-135">該当しない。</span><span class="sxs-lookup"><span data-stu-id="40508-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="40508-136">ToList</span><span class="sxs-lookup"><span data-stu-id="40508-136">ToList</span></span>|<span data-ttu-id="40508-137">コレクションを <xref:System.Collections.Generic.List%601> に変換します。</span><span class="sxs-lookup"><span data-stu-id="40508-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="40508-138">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="40508-138">This method forces query execution.</span></span>|<span data-ttu-id="40508-139">該当しない。</span><span class="sxs-lookup"><span data-stu-id="40508-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="40508-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="40508-140">ToLookup</span></span>|<span data-ttu-id="40508-141">キー セレクター関数に基づいて、<xref:System.Linq.Lookup%602> (一対多の辞書) に要素を変換します。</span><span class="sxs-lookup"><span data-stu-id="40508-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="40508-142">このメソッドはクエリの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="40508-142">This method forces query execution.</span></span>|<span data-ttu-id="40508-143">該当しない。</span><span class="sxs-lookup"><span data-stu-id="40508-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="40508-144">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="40508-144">Query Expression Syntax Example</span></span>

<span data-ttu-id="40508-145">次のコード例では、`From As` 句を使用して、サブタイプでのみ使用できるメンバーにアクセスする前に型をサブタイプにキャストします。</span><span class="sxs-lookup"><span data-stu-id="40508-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a><span data-ttu-id="40508-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="40508-146">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="40508-147">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40508-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="40508-148">From 句</span><span class="sxs-lookup"><span data-stu-id="40508-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="40508-149">方法: LINQ を使用して ArrayList を照会する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40508-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
