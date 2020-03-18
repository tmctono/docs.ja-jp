---
title: クエリ式の null 値の処理 (C# での LINQ)
description: C# の LINQ クエリ式で null 値を処理する方法について説明します。
ms.date: 12/01/2016
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: c9a3aaec05fa029a8db66826bdcb4a1d106176e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "73736858"
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="35099-103">クエリ式の null 値の処理</span><span class="sxs-lookup"><span data-stu-id="35099-103">Handle null values in query expressions</span></span>

<span data-ttu-id="35099-104">この例では、ソース コレクション内の可能な null 値を処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="35099-104">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="35099-105"><xref:System.Collections.Generic.IEnumerable%601> のようなオブジェクト コレクションには、値が [null](../language-reference/keywords/null.md) の要素を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="35099-105">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="35099-106">ソース コレクションが null であるか null の値を持つ要素を含み、クエリで null 値を処理しない場合、クエリを実行すると <xref:System.NullReferenceException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="35099-106">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>

## <a name="example"></a><span data-ttu-id="35099-107">例</span><span class="sxs-lookup"><span data-stu-id="35099-107">Example</span></span>

<span data-ttu-id="35099-108">次の例に示すように、null 参照の例外を回避する防御的なコーディングをすることができます。</span><span class="sxs-lookup"><span data-stu-id="35099-108">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#82](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]

<span data-ttu-id="35099-109">前の例では、`where` 句によって、カテゴリ シーケンス内のすべての null 要素が除外されます。</span><span class="sxs-lookup"><span data-stu-id="35099-109">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="35099-110">この手法は、join 句での null チェックに依存しません。</span><span class="sxs-lookup"><span data-stu-id="35099-110">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="35099-111">この例の null 条件式が機能する理由は、`Products.CategoryID` が `int?` 型 (`Nullable<int>` の短縮形) であるためです。</span><span class="sxs-lookup"><span data-stu-id="35099-111">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>

## <a name="example"></a><span data-ttu-id="35099-112">例</span><span class="sxs-lookup"><span data-stu-id="35099-112">Example</span></span>

<span data-ttu-id="35099-113">join 句で、比較キーの一方だけが null 許容値型である場合、クエリ式でもう一方のキーを null 許容型にキャストできます。</span><span class="sxs-lookup"><span data-stu-id="35099-113">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="35099-114">次の例では、`EmployeeID` は `int?` 型の値を含む列であるとします。</span><span class="sxs-lookup"><span data-stu-id="35099-114">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>

[!code-csharp[csProgGuideLINQ#83](~/samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="35099-115">参照</span><span class="sxs-lookup"><span data-stu-id="35099-115">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="35099-116">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="35099-116">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="35099-117">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="35099-117">Nullable value types</span></span>](../language-reference/builtin-types/nullable-value-types.md)
