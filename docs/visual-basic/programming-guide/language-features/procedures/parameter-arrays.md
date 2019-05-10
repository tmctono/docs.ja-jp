---
title: パラメーター配列 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: 372d5fdd2702d6f85f784ee5addea91abe46d3bd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639018"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="a2a0a-102">パラメーター配列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2a0a-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="a2a0a-103">通常、プロシージャ宣言の指定よりも多くの引数を持つプロシージャを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="a2a0a-104">宣言することができます、不特定多数の引数を必要がある場合、*パラメーター配列*、プロシージャ パラメーターの値の配列をそのまま使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="a2a0a-105">プロシージャを定義するときに、パラメーター配列内の要素の数を把握する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="a2a0a-106">配列のサイズは、各プロシージャの呼び出しによって個別に決まります。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="a2a0a-107">ParamArray を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="a2a0a-108">使用する、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)パラメーター リスト内のパラメーター配列を示すキーワードです。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="a2a0a-109">次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-109">The following rules apply:</span></span>  
  
- <span data-ttu-id="a2a0a-110">プロシージャが 1 つだけのパラメーター配列を定義およびプロシージャの定義の最後のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="a2a0a-111">パラメーター配列は、値を渡しする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="a2a0a-112">明示的に指定することをお勧め、 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)プロシージャ定義内のキーワード。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="a2a0a-113">パラメーター配列は、自動的に省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="a2a0a-114">既定値は、パラメーター配列の要素の型の空の 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="a2a0a-115">前に、パラメーター配列のすべてのパラメーターは必須である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="a2a0a-116">パラメーター配列は、唯一のパラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="a2a0a-117">ParamArray を呼び出す</span><span class="sxs-lookup"><span data-stu-id="a2a0a-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="a2a0a-118">パラメーター配列を定義するプロシージャを呼び出すときに、次の方法のいずれかで、引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="a2a0a-119">Nothing-これは省略できます、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)引数。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="a2a0a-120">この場合、空の配列は、プロシージャに渡されます。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="a2a0a-121">渡すことも、 [Nothing](../../../../visual-basic/language-reference/nothing.md)キーワードは、同じ効果を持つ。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
- <span data-ttu-id="a2a0a-122">任意の数の引数、コンマ区切りの一覧。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="a2a0a-123">各引数のデータ型に暗黙的に変換できる必要があります、`ParamArray`要素の型。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="a2a0a-124">パラメーター配列の要素の型と同じ要素型の配列。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="a2a0a-125">すべてのケースで、プロシージャ内のコード、パラメーターは配列として扱いますと同じデータ型の要素を持つ 1 次元配列、`ParamArray`データ型。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a2a0a-126">無限に増大することができる配列を処理するたびに、アプリケーションの内部の容量を超過してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="a2a0a-127">パラメーター配列を受け取る場合は、呼び出し元のコードが渡された配列のサイズをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="a2a0a-128">アプリケーションが大きすぎる場合は、適切な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="a2a0a-129">詳細については、次を参照してください。[配列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a0a-130">例</span><span class="sxs-lookup"><span data-stu-id="a2a0a-130">Example</span></span>  
 <span data-ttu-id="a2a0a-131">次の例を定義し、関数を呼び出す`calcSum`します。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="a2a0a-132">`ParamArray`パラメーター修飾子`args`により、関数を可変個の引数を受け入れるようにできます。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="a2a0a-133">次の例は、パラメーター配列を持つプロシージャを定義し、パラメーター配列に渡されるすべての配列要素の値を出力します。</span><span class="sxs-lookup"><span data-stu-id="a2a0a-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="a2a0a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2a0a-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="a2a0a-135">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a2a0a-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="a2a0a-136">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="a2a0a-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a2a0a-137">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="a2a0a-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="a2a0a-138">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="a2a0a-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="a2a0a-139">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="a2a0a-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="a2a0a-140">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="a2a0a-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="a2a0a-141">配列</span><span class="sxs-lookup"><span data-stu-id="a2a0a-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="a2a0a-142">Optional</span><span class="sxs-lookup"><span data-stu-id="a2a0a-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
