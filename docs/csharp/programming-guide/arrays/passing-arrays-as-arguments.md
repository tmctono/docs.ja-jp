---
title: 引数としての配列の受け渡し - C# プログラミング ガイド
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 2e53008910a9062ada25680eb4b8e54a225fd226
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705692"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="44a44-102">引数としての配列の受け渡し (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="44a44-102">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="44a44-103">配列は、引数としてメソッド パラメーターに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="44a44-103">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="44a44-104">配列は参照型であるため、メソッドは要素の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="44a44-104">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="44a44-105">1 次元配列を引数として渡す</span><span class="sxs-lookup"><span data-stu-id="44a44-105">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="44a44-106">初期化された 1 次元配列をメソッドに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="44a44-106">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="44a44-107">たとえば、次のステートメントは、配列を print メソッドに送信します。</span><span class="sxs-lookup"><span data-stu-id="44a44-107">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="44a44-108">次のコードは、print メソッドの実装の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="44a44-108">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="44a44-109">次の例に示すように、一度に新しい配列を初期化して渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="44a44-109">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="44a44-110">例</span><span class="sxs-lookup"><span data-stu-id="44a44-110">Example</span></span>

<span data-ttu-id="44a44-111">次の例では、文字列の配列が初期化され、引数として文字列の `DisplayArray` メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="44a44-111">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="44a44-112">このメソッドは、配列の要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="44a44-112">The method displays the elements of the array.</span></span> <span data-ttu-id="44a44-113">次に、`ChangeArray` メソッドで配列の要素を反転させた後、`ChangeArrayElements` メソッドで配列の最初の 3 つの要素を変更します。</span><span class="sxs-lookup"><span data-stu-id="44a44-113">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="44a44-114">各メソッドから戻った後、`DisplayArray` メソッドで、配列を値で渡すと配列要素の変更が禁止されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="44a44-114">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="44a44-115">多次元配列を引数として渡す</span><span class="sxs-lookup"><span data-stu-id="44a44-115">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="44a44-116">1 次元配列を渡すのと同じ方法で、初期化された多次元配列をメソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="44a44-116">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="44a44-117">次のコードに、2 次元配列を引数として受け取る print メソッドの宣言の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="44a44-117">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="44a44-118">次の例に示すように、一度に新しい配列を初期化して渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="44a44-118">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="44a44-119">例</span><span class="sxs-lookup"><span data-stu-id="44a44-119">Example</span></span>

<span data-ttu-id="44a44-120">次の例では、整数の 2 次元配列が初期化され、`Print2DArray` メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="44a44-120">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="44a44-121">このメソッドは、配列の要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="44a44-121">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="44a44-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="44a44-122">See also</span></span>

- [<span data-ttu-id="44a44-123">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="44a44-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="44a44-124">配列</span><span class="sxs-lookup"><span data-stu-id="44a44-124">Arrays</span></span>](index.md)
- [<span data-ttu-id="44a44-125">1 次元配列</span><span class="sxs-lookup"><span data-stu-id="44a44-125">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="44a44-126">多次元配列</span><span class="sxs-lookup"><span data-stu-id="44a44-126">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="44a44-127">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="44a44-127">Jagged Arrays</span></span>](jagged-arrays.md)
