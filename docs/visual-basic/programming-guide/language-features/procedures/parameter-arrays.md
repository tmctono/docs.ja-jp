---
title: パラメーター配列
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
ms.openlocfilehash: ffb532fbac70b9aa8ab210450e4d9207f5e0291f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351124"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="2ed1b-102">パラメーター配列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ed1b-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="2ed1b-103">通常、プロシージャ宣言で指定されている引数よりも多くの引数でプロシージャを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="2ed1b-104">不特定数の引数が必要な場合は、"*パラメーター配列*" を宣言できます。これにより、プロシージャはパラメーターの値の配列を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="2ed1b-105">プロシージャを定義するときに、パラメーター配列の要素の数がわかっている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="2ed1b-106">配列のサイズは、プロシージャの呼び出しごとに個別に決定されます。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="2ed1b-107">ParamArray の宣言</span><span class="sxs-lookup"><span data-stu-id="2ed1b-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="2ed1b-108">[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) キーワードを使用して、パラメーター リスト内のパラメーター配列を示します。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="2ed1b-109">次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-109">The following rules apply:</span></span>  
  
- <span data-ttu-id="2ed1b-110">プロシージャではパラメーター配列を 1 つだけ定義でき、プロシージャ定義の最後のパラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="2ed1b-111">パラメーター配列は値渡しにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="2ed1b-112">プロシージャの定義に [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) キーワードを明示的に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="2ed1b-113">パラメーター配列は自動的に省略可能になります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="2ed1b-114">既定値は、パラメーター配列の要素型の空の 1 次元配列です。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="2ed1b-115">パラメーター配列の前にあるすべてのパラメーターが必須である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="2ed1b-116">パラメーター配列が唯一の省略可能なパラメーターでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="2ed1b-117">ParamArray の呼び出し</span><span class="sxs-lookup"><span data-stu-id="2ed1b-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="2ed1b-118">パラメーター配列が定義されているプロシージャを呼び出すときは、次のいずれかの方法で引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="2ed1b-119">Nothing - つまり、[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 引数を省略できます。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="2ed1b-120">この場合、プロシージャに空の配列が渡されます。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="2ed1b-121">[Nothing](../../../../visual-basic/language-reference/nothing.md) キーワードを明示的に渡すと、プロシージャに null 配列が渡されます。呼び出されたプロシージャがこの条件をチェックしない場合、NullReferenceException が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-121">If you explicitly pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, a null array is passed to the procedure and may result in a NullReferenceException if the called procedure does not check for this condition.</span></span>
  
- <span data-ttu-id="2ed1b-122">コンマで区切られた任意の数の引数のリスト。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="2ed1b-123">各引数のデータ型は、`ParamArray` 要素型に暗黙的に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="2ed1b-124">パラメーター配列の要素型と同じ要素型の配列。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="2ed1b-125">どの場合も、プロシージャ内のコードは、パラメーター配列を、`ParamArray` のデータ型と同じデータ型の要素を含む 1 次元配列として扱います。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2ed1b-126">無限に大きくなる可能性がある配列を処理する場合は常に、アプリケーションの何らかの内部容量が超過するリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="2ed1b-127">パラメーター配列を受け入れる場合は、呼び出し元のコードから渡された配列のサイズをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="2ed1b-128">アプリケーションにとって大きすぎる場合は、適切な手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="2ed1b-129">詳細については、「[配列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ed1b-130">例</span><span class="sxs-lookup"><span data-stu-id="2ed1b-130">Example</span></span>  
 <span data-ttu-id="2ed1b-131">次の例では、`calcSum` 関数を定義して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="2ed1b-132">`args` パラメーターの `ParamArray` 修飾子により、関数は可変数の引数を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="2ed1b-133">次の例では、パラメーター配列を使用するプロシージャを定義し、パラメーター配列に渡されたすべての配列要素の値を出力します。</span><span class="sxs-lookup"><span data-stu-id="2ed1b-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="2ed1b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ed1b-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="2ed1b-135">手順</span><span class="sxs-lookup"><span data-stu-id="2ed1b-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2ed1b-136">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="2ed1b-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2ed1b-137">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="2ed1b-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="2ed1b-138">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="2ed1b-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="2ed1b-139">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="2ed1b-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="2ed1b-140">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="2ed1b-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="2ed1b-141">配列</span><span class="sxs-lookup"><span data-stu-id="2ed1b-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="2ed1b-142">Optional</span><span class="sxs-lookup"><span data-stu-id="2ed1b-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
