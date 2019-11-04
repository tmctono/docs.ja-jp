---
title: 1 次元配列 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 5559acd162b26a94b009ec21691d1501c90db290
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419524"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="a97ae-102">1 次元配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a97ae-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="a97ae-103">次の例のように、5 つの整数の 1 次元配列を宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 <span data-ttu-id="a97ae-104">この配列は、`array[0]` から `array[4]` の要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="a97ae-105">[new](../../language-reference/operators/new-operator.md) 演算子を使用して、配列を作成し、配列要素を既定値に初期化します。</span><span class="sxs-lookup"><span data-stu-id="a97ae-105">The [new](../../language-reference/operators/new-operator.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="a97ae-106">この例では、すべての配列要素はゼロに初期化されます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="a97ae-107">同じ方法では、文字列要素を格納する配列を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="a97ae-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a97ae-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a><span data-ttu-id="a97ae-109">配列の初期化</span><span class="sxs-lookup"><span data-stu-id="a97ae-109">Array Initialization</span></span>

 <span data-ttu-id="a97ae-110">宣言時に配列を初期化することができます。この場合、初期化リスト内の要素の数によって長さが既に提供されているので、長さ指定子は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a97ae-110">It is possible to initialize an array upon declaration, in which case, the length specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="a97ae-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a97ae-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 <span data-ttu-id="a97ae-112">文字列の配列は、同じ方法で初期化できます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="a97ae-113">配列の各要素が曜日の名前で初期化される文字列配列の宣言を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a97ae-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 <span data-ttu-id="a97ae-114">宣言時に配列を初期化する場合は、次のショートカットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 <span data-ttu-id="a97ae-115">初期化せずに配列変数を宣言できますが、配列をこの変数に割り当てるときに、`new` 演算子を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a97ae-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="a97ae-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a97ae-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 <span data-ttu-id="a97ae-117">C# 3.0 で暗黙的に型指定される配列が導入されます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="a97ae-118">詳細については、「[暗黙的に型指定される配列](./implicitly-typed-arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a97ae-118">For more information, see [Implicitly Typed Arrays](./implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="a97ae-119">値の型と参照型の配列</span><span class="sxs-lookup"><span data-stu-id="a97ae-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="a97ae-120">次の配列の宣言を検討してみます。</span><span class="sxs-lookup"><span data-stu-id="a97ae-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 <span data-ttu-id="a97ae-121">このステートメントの結果は、`SomeType` が値型か参照型かによって決まります。</span><span class="sxs-lookup"><span data-stu-id="a97ae-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="a97ae-122">値型の場合、ステートメントはそれそれが型 `SomeType` である 10 個の要素の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="a97ae-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="a97ae-123">`SomeType` が参照型の場合、ステートメントは、それぞれが null 参照に初期化される 10 個の要素の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="a97ae-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="a97ae-124">値型と参照型の詳細については、「[型](/dotnet/csharp/language-reference/keywords)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a97ae-124">For more information about value types and reference types, see [Types](/dotnet/csharp/language-reference/keywords).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97ae-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a97ae-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="a97ae-126">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a97ae-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a97ae-127">配列</span><span class="sxs-lookup"><span data-stu-id="a97ae-127">Arrays</span></span>](./index.md)
- [<span data-ttu-id="a97ae-128">多次元配列</span><span class="sxs-lookup"><span data-stu-id="a97ae-128">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="a97ae-129">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="a97ae-129">Jagged Arrays</span></span>](./jagged-arrays.md)
