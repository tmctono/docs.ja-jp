---
title: 引数としての配列の受け渡し - C# プログラミング ガイド
description: C# の配列は、引数としてメソッド パラメーターに渡すことができます。 配列は参照型であるため、メソッドは要素の値を変更できます。
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 68f174421e56e2cf082fe670f93c4f6627d7c17b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474632"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="e06f6-104">引数としての配列の受け渡し (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e06f6-104">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="e06f6-105">配列は、引数としてメソッド パラメーターに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e06f6-105">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="e06f6-106">配列は参照型であるため、メソッドは要素の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e06f6-106">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="e06f6-107">1 次元配列を引数として渡す</span><span class="sxs-lookup"><span data-stu-id="e06f6-107">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="e06f6-108">初期化された 1 次元配列をメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e06f6-108">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="e06f6-109">たとえば、次のステートメントは、配列を print メソッドに送信します。</span><span class="sxs-lookup"><span data-stu-id="e06f6-109">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="e06f6-110">次のコードは、print メソッドの実装の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="e06f6-110">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="e06f6-111">次の例に示すように、一度に新しい配列を初期化して渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e06f6-111">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="e06f6-112">例</span><span class="sxs-lookup"><span data-stu-id="e06f6-112">Example</span></span>

<span data-ttu-id="e06f6-113">次の例では、文字列の配列が初期化され、引数として文字列の `DisplayArray` メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="e06f6-113">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="e06f6-114">このメソッドは、配列の要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="e06f6-114">The method displays the elements of the array.</span></span> <span data-ttu-id="e06f6-115">次に、`ChangeArray` メソッドで配列の要素を反転させた後、`ChangeArrayElements` メソッドで配列の最初の 3 つの要素を変更します。</span><span class="sxs-lookup"><span data-stu-id="e06f6-115">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="e06f6-116">各メソッドから戻った後、`DisplayArray` メソッドで、配列を値で渡すと配列要素の変更が禁止されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e06f6-116">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="e06f6-117">多次元配列を引数として渡す</span><span class="sxs-lookup"><span data-stu-id="e06f6-117">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="e06f6-118">1 次元配列を渡すのと同じ方法で、初期化された多次元配列をメソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="e06f6-118">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="e06f6-119">次のコードに、2 次元配列を引数として受け取る print メソッドの宣言の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="e06f6-119">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="e06f6-120">次の例に示すように、一度に新しい配列を初期化して渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e06f6-120">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="e06f6-121">例</span><span class="sxs-lookup"><span data-stu-id="e06f6-121">Example</span></span>

<span data-ttu-id="e06f6-122">次の例では、整数の 2 次元配列が初期化され、`Print2DArray` メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="e06f6-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="e06f6-123">このメソッドは、配列の要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="e06f6-123">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="e06f6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="e06f6-124">See also</span></span>

- [<span data-ttu-id="e06f6-125">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="e06f6-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e06f6-126">配列</span><span class="sxs-lookup"><span data-stu-id="e06f6-126">Arrays</span></span>](index.md)
- [<span data-ttu-id="e06f6-127">1 次元配列</span><span class="sxs-lookup"><span data-stu-id="e06f6-127">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="e06f6-128">多次元配列</span><span class="sxs-lookup"><span data-stu-id="e06f6-128">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="e06f6-129">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="e06f6-129">Jagged Arrays</span></span>](jagged-arrays.md)
