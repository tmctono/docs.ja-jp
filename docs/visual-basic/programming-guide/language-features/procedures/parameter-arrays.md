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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351124"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="6efec-102">パラメーター配列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6efec-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="6efec-103">通常、プロシージャの宣言よりも多くの引数を指定してプロシージャを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="6efec-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="6efec-104">不特定数の引数が必要な場合は、パラメーター*配列*を宣言して、プロシージャがパラメーターの値の配列を受け取ることができるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6efec-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="6efec-105">プロシージャを定義するときに、パラメーター配列内の要素の数を知る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6efec-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="6efec-106">配列のサイズは、プロシージャの呼び出しごとに個別に決定されます。</span><span class="sxs-lookup"><span data-stu-id="6efec-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="6efec-107">ParamArray の宣言</span><span class="sxs-lookup"><span data-stu-id="6efec-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="6efec-108">パラメーターリストのパラメーター配列を示すには、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6efec-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="6efec-109">次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6efec-109">The following rules apply:</span></span>  
  
- <span data-ttu-id="6efec-110">プロシージャは、パラメーター配列を1つだけ定義できます。また、プロシージャ定義の最後のパラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efec-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="6efec-111">パラメーター配列は、値で渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efec-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="6efec-112">プロシージャの定義に[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)キーワードを明示的に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6efec-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="6efec-113">パラメーター配列は、自動的に省略可能です。</span><span class="sxs-lookup"><span data-stu-id="6efec-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="6efec-114">既定値は、パラメーター配列の要素型の空の1次元配列です。</span><span class="sxs-lookup"><span data-stu-id="6efec-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="6efec-115">パラメーター配列の前にあるすべてのパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="6efec-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="6efec-116">パラメーター配列は、唯一の省略可能なパラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efec-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="6efec-117">ParamArray の呼び出し</span><span class="sxs-lookup"><span data-stu-id="6efec-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="6efec-118">パラメーター配列を定義するプロシージャを呼び出す場合は、次のいずれかの方法で引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6efec-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="6efec-119">Nothing: つまり、 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)引数を省略できます。</span><span class="sxs-lookup"><span data-stu-id="6efec-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="6efec-120">この場合、空の配列がプロシージャに渡されます。</span><span class="sxs-lookup"><span data-stu-id="6efec-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="6efec-121">[Nothing](../../../../visual-basic/language-reference/nothing.md)キーワードを明示的に渡すと、null 配列がプロシージャに渡され、呼び出されたプロシージャがこの条件をチェックしない場合、NullReferenceException が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6efec-121">If you explicitly pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, a null array is passed to the procedure and may result in a NullReferenceException if the called procedure does not check for this condition.</span></span>
  
- <span data-ttu-id="6efec-122">コンマで区切られた任意の数の引数のリスト。</span><span class="sxs-lookup"><span data-stu-id="6efec-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="6efec-123">各引数のデータ型は、`ParamArray` 要素型に暗黙的に変換できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efec-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="6efec-124">パラメーター配列の要素型と同じ要素型を持つ配列。</span><span class="sxs-lookup"><span data-stu-id="6efec-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="6efec-125">どのような場合でも、プロシージャ内のコードは、パラメーター配列を `ParamArray` データ型と同じデータ型の要素を持つ1次元配列として扱います。</span><span class="sxs-lookup"><span data-stu-id="6efec-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6efec-126">無限に大きくなる可能性がある配列を処理する場合、アプリケーションの内部容量がオーバーランするリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="6efec-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="6efec-127">パラメーター配列を受け入れる場合は、呼び出し元のコードが配列のサイズを渡すかどうかをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efec-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="6efec-128">アプリケーションに対して大きすぎる場合は、適切な手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="6efec-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="6efec-129">詳細については、「[配列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6efec-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6efec-130">例</span><span class="sxs-lookup"><span data-stu-id="6efec-130">Example</span></span>  
 <span data-ttu-id="6efec-131">次の例では、関数 `calcSum`を定義して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6efec-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="6efec-132">パラメーター `args` の `ParamArray` 修飾子は、関数が可変個の引数を受け取ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="6efec-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="6efec-133">次の例では、パラメーター配列を使用してプロシージャを定義し、パラメーター配列に渡されたすべての配列要素の値を出力します。</span><span class="sxs-lookup"><span data-stu-id="6efec-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="6efec-134">参照</span><span class="sxs-lookup"><span data-stu-id="6efec-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="6efec-135">手順</span><span class="sxs-lookup"><span data-stu-id="6efec-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6efec-136">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="6efec-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6efec-137">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="6efec-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="6efec-138">位置と名前による引数渡し</span><span class="sxs-lookup"><span data-stu-id="6efec-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="6efec-139">省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="6efec-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="6efec-140">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="6efec-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="6efec-141">配列</span><span class="sxs-lookup"><span data-stu-id="6efec-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="6efec-142">Optional</span><span class="sxs-lookup"><span data-stu-id="6efec-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
