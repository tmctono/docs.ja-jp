---
title: 1 次元配列 - C# プログラミング ガイド
description: 配列要素の型と要素の数を指定する new 演算子を使用して、C# で 1 次元配列を作成します。
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474593"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="4f618-103">1 次元配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="4f618-103">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="4f618-104">配列要素の型と要素の数を指定する [new](../../language-reference/operators/new-operator.md) 演算子を使用して、1 次元配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="4f618-104">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="4f618-105">次の例では、5 つの整数の配列を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="4f618-105">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="4f618-106">この配列は、`array[0]` から `array[4]` の要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="4f618-106">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="4f618-107">配列の要素は、要素型の既定値である整数 `0` に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="4f618-107">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="4f618-108">配列には、次の例のように、文字列の配列を宣言する、指定した要素型を格納できます。</span><span class="sxs-lookup"><span data-stu-id="4f618-108">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="4f618-109">配列の初期化</span><span class="sxs-lookup"><span data-stu-id="4f618-109">Array Initialization</span></span>

<span data-ttu-id="4f618-110">配列を宣言するときに、配列の要素を初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="4f618-110">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="4f618-111">長さ指定子は、初期化リスト内の要素の数から推論されるため、必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="4f618-111">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="4f618-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4f618-112">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="4f618-113">次のコードは、配列の各要素が曜日の名前で初期化される文字列配列の宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="4f618-113">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="4f618-114">次のコードに示すように、宣言時に配列を初期化するときに、`new` 式と配列型を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="4f618-114">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="4f618-115">これは、[暗黙的に型指定される配列](implicitly-typed-arrays.md)と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4f618-115">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="4f618-116">配列変数は作成しなくても宣言できますが、この変数の新しい配列を割り当てるときは `new` 演算子を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f618-116">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="4f618-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4f618-117">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="4f618-118">値の型と参照型の配列</span><span class="sxs-lookup"><span data-stu-id="4f618-118">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="4f618-119">次の配列の宣言を検討してみます。</span><span class="sxs-lookup"><span data-stu-id="4f618-119">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="4f618-120">このステートメントの結果は、`SomeType` が値型か参照型かによって決まります。</span><span class="sxs-lookup"><span data-stu-id="4f618-120">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="4f618-121">値型の場合、ステートメントでは、それぞれに `SomeType` 型が含まれる 10 個の要素の配列が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f618-121">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="4f618-122">`SomeType` が参照型の場合、ステートメントは、それぞれが null 参照に初期化される 10 個の要素の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="4f618-122">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="4f618-123">両方のインスタンスで、要素は要素型の既定値に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="4f618-123">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="4f618-124">値の型と参照型の詳細については、[値の型](../../language-reference/builtin-types/value-types.md)と[参照型](../../language-reference/keywords/reference-types.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f618-124">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4f618-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f618-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="4f618-126">配列</span><span class="sxs-lookup"><span data-stu-id="4f618-126">Arrays</span></span>](./index.md)
- [<span data-ttu-id="4f618-127">多次元配列</span><span class="sxs-lookup"><span data-stu-id="4f618-127">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="4f618-128">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="4f618-128">Jagged Arrays</span></span>](./jagged-arrays.md)
