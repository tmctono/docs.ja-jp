---
title: 多次元配列 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: df9063d0616b72ad15c9c48fa4459a6dc98b77c1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972613"
---
# <a name="multidimensional-arrays-c-programming-guide"></a><span data-ttu-id="85a99-102">多次元配列 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="85a99-102">Multidimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="85a99-103">配列は 1 つ以上の配列を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="85a99-103">Arrays can have more than one dimension.</span></span> <span data-ttu-id="85a99-104">たとえば、次の宣言は、4 行と 2 列の 2 次元の配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="85a99-104">For example, the following declaration creates a two-dimensional array of four rows and two columns.</span></span>  
  
 [!code-csharp[csProgGuideArrays#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#11)]  
  
 <span data-ttu-id="85a99-105">次の宣言は、4、2、3 の 3 次元配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="85a99-105">The following declaration creates an array of three dimensions, 4, 2, and 3.</span></span>  
  
 [!code-csharp[csProgGuideArrays#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#12)]  
  
## <a name="array-initialization"></a><span data-ttu-id="85a99-106">配列の初期化</span><span class="sxs-lookup"><span data-stu-id="85a99-106">Array Initialization</span></span>

 <span data-ttu-id="85a99-107">次の例に示すように、宣言時に配列を初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="85a99-107">You can initialize the array upon declaration, as is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#13)]  
  
 <span data-ttu-id="85a99-108">また、順位を指定せずに配列を初期化することもできます。</span><span class="sxs-lookup"><span data-stu-id="85a99-108">You also can initialize the array without specifying the rank.</span></span>  
  
 [!code-csharp[csProgGuideArrays#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#14)]  
  
 <span data-ttu-id="85a99-109">初期化せずに配列変数を宣言する場合、`new` 演算子を使用して配列を変数に代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a99-109">If you choose to declare an array variable without initialization, you must use the `new` operator to assign an array to the variable.</span></span> <span data-ttu-id="85a99-110">`new` の使用を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="85a99-110">The use of `new` is shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideArrays#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#15)]  
  
 <span data-ttu-id="85a99-111">次の例では、特定の配列要素に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="85a99-111">The following example assigns a value to a particular array element.</span></span>  
  
 [!code-csharp[csProgGuideArrays#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#16)]  
  
 <span data-ttu-id="85a99-112">同様に、次の例では、特定の配列要素の値を取得して、それを変数 `elementValue` に代入します。</span><span class="sxs-lookup"><span data-stu-id="85a99-112">Similarly, the following example gets the value of a particular array element and assigns it to variable `elementValue`.</span></span>  
  
 [!code-csharp[csProgGuideArrays#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#42)]  
  
 <span data-ttu-id="85a99-113">次のコード例では、配列要素を既定値に初期化します (ジャグ配列を除く)。</span><span class="sxs-lookup"><span data-stu-id="85a99-113">The following code example initializes the array elements to default values (except for jagged arrays).</span></span>  
  
 [!code-csharp[csProgGuideArrays#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="85a99-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="85a99-114">See also</span></span>

- [<span data-ttu-id="85a99-115">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="85a99-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="85a99-116">配列</span><span class="sxs-lookup"><span data-stu-id="85a99-116">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="85a99-117">1 次元配列</span><span class="sxs-lookup"><span data-stu-id="85a99-117">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)
- [<span data-ttu-id="85a99-118">ジャグ配列</span><span class="sxs-lookup"><span data-stu-id="85a99-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
