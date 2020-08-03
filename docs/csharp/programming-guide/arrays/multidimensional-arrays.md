---
title: 多次元配列 - C# プログラミング ガイド
description: C# の配列には複数の次元を与えることができます。 この例の宣言では、4 行と 2 列の 2 次元の配列が作成されます。
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a2f204c0866672b317569fbc620aa8af60829ffd
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475009"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="a921e-104">多次元配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="a921e-104">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="a921e-105">配列は 1 つ以上の配列を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a921e-105">Arrays can have more than one dimension.</span></span> <span data-ttu-id="a921e-106">たとえば、次の宣言は、4 行と 2 列の 2 次元の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="a921e-106">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="a921e-107">次の宣言は、4、2、3 の 3 次元配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="a921e-107">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="a921e-108">配列の初期化</span><span class="sxs-lookup"><span data-stu-id="a921e-108">Array Initialization</span></span>

 <span data-ttu-id="a921e-109">次の例に示すように、宣言時に配列を初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="a921e-109">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="a921e-110">また、順位を指定せずに配列を初期化することもできます。</span><span class="sxs-lookup"><span data-stu-id="a921e-110">You can also initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="a921e-111">初期化せずに配列変数を宣言する場合、`new` 演算子を使用して配列を変数に代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a921e-111">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="a921e-112">`new` の使用を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a921e-112">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="a921e-113">次の例では、特定の配列要素に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="a921e-113">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="a921e-114">同様に、次の例では、特定の配列要素の値を取得して、それを変数 `elementValue` に代入します。</span><span class="sxs-lookup"><span data-stu-id="a921e-114">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="a921e-115">次のコード例では、配列要素を既定値に初期化します (ジャグ配列を除く)。</span><span class="sxs-lookup"><span data-stu-id="a921e-115">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="a921e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a921e-116">See also</span></span>

- [<span data-ttu-id="a921e-117">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a921e-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a921e-118">配列</span><span class="sxs-lookup"><span data-stu-id="a921e-118">Arrays</span></span>](./index.md)
- [<span data-ttu-id="a921e-119">1 次元配列</span><span class="sxs-lookup"><span data-stu-id="a921e-119">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="a921e-120">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="a921e-120">Jagged Arrays</span></span>](./jagged-arrays.md)
