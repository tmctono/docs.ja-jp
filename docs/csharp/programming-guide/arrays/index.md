---
title: 配列 - C# プログラミング ガイド
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715057"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="afb51-102">配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="afb51-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="afb51-103">配列データ構造体には、同じ型の複数の変数を格納できます。</span><span class="sxs-lookup"><span data-stu-id="afb51-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="afb51-104">配列は、要素の型を指定することで宣言します。</span><span class="sxs-lookup"><span data-stu-id="afb51-104">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="afb51-105">配列に任意の型の要素を格納する場合は、その型として `object` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="afb51-105">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="afb51-106">C# の統一型システムでは、すべての型 (定義済み、ユーザー定義、参照型、および値型) が、直接または間接的に <xref:System.Object> を継承します。</span><span class="sxs-lookup"><span data-stu-id="afb51-106">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="afb51-107">例</span><span class="sxs-lookup"><span data-stu-id="afb51-107">Example</span></span>

<span data-ttu-id="afb51-108">次の例では、1 次元配列、多次元配列、およびジャグ配列を作成しています。</span><span class="sxs-lookup"><span data-stu-id="afb51-108">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="afb51-109">配列の概要</span><span class="sxs-lookup"><span data-stu-id="afb51-109">Array overview</span></span>

<span data-ttu-id="afb51-110">配列には、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="afb51-110">An array has the following properties:</span></span>

- <span data-ttu-id="afb51-111">配列は、[1 次元配列](single-dimensional-arrays.md)、[多次元配列](multidimensional-arrays.md)、または[ジャグ配列](jagged-arrays.md)のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="afb51-111">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="afb51-112">次元数と各次元の長さは、配列インスタンスの作成時に設定されます。</span><span class="sxs-lookup"><span data-stu-id="afb51-112">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="afb51-113">インスタンスの有効期間中にこれらの値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="afb51-113">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="afb51-114">数値配列要素の既定値はゼロに設定され、参照要素は null に設定されます。</span><span class="sxs-lookup"><span data-stu-id="afb51-114">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="afb51-115">ジャグ配列は配列の配列です。そのため、配列要素は参照型で、`null` に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="afb51-115">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="afb51-116">配列には、ゼロから始まるインデックスが付けられます。`n` 個の要素を含む配列には、`0` から `n-1` までのインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="afb51-116">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="afb51-117">配列の要素および配列型は、どのような型でもかまいません。</span><span class="sxs-lookup"><span data-stu-id="afb51-117">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="afb51-118">配列型は、抽象基本型 <xref:System.Array> から派生した[参照型](../../language-reference/keywords/reference-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="afb51-118">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="afb51-119">この型は <xref:System.Collections.IEnumerable> と <xref:System.Collections.Generic.IEnumerable%601> を実装するので、C# のすべての配列で [foreach](../../language-reference/keywords/foreach-in.md) 反復処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="afb51-119">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="afb51-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="afb51-120">Related sections</span></span>

- [<span data-ttu-id="afb51-121">オブジェクトとしての配列</span><span class="sxs-lookup"><span data-stu-id="afb51-121">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="afb51-122">配列での foreach の使用</span><span class="sxs-lookup"><span data-stu-id="afb51-122">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="afb51-123">引数としての配列の受け渡し</span><span class="sxs-lookup"><span data-stu-id="afb51-123">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="afb51-124">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="afb51-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="afb51-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="afb51-125">See also</span></span>

- [<span data-ttu-id="afb51-126">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="afb51-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="afb51-127">コレクション</span><span class="sxs-lookup"><span data-stu-id="afb51-127">Collections</span></span>](../concepts/collections.md)
