---
title: Function プロシージャ
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: b62a730e8ade211821826afbb55fa8858ea311a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341087"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="82578-102">Function プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82578-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="82578-103">`Function` プロシージャは、`Function` および `End Function` ステートメントで囲まれた一連の Visual Basic ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="82578-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="82578-104">`Function` プロシージャはタスクを実行し、呼び出し元のコードに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="82578-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="82578-105">コントロールが返されると、呼び出し元のコードにも値が返されます。</span><span class="sxs-lookup"><span data-stu-id="82578-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="82578-106">プロシージャが呼び出されるたびに、ステートメントが実行され、`Function` ステートメントの後の最初の実行可能ステートメントから開始し、最初の `End Function`、`Exit Function`、または `Return` ステートメントで終了します。</span><span class="sxs-lookup"><span data-stu-id="82578-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="82578-107">モジュール、クラス、または構造体で `Function` プロシージャを定義できます。</span><span class="sxs-lookup"><span data-stu-id="82578-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="82578-108">既定では `Public` されています。これは、アプリケーション内の任意の場所から、これを定義したモジュール、クラス、または構造体にアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="82578-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="82578-109">`Function` プロシージャは、呼び出し元のコードによって渡される定数、変数、式などの引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="82578-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="82578-110">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="82578-110">Declaration Syntax</span></span>  
 <span data-ttu-id="82578-111">`Function` プロシージャを宣言する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82578-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="82578-112">*修飾子*では、アクセスレベルと、オーバーロード、オーバーライド、共有、およびシャドウに関する情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82578-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="82578-113">詳細については、「[Function ステートメント](../../../../visual-basic/language-reference/statements/function-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82578-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="82578-114">各パラメーターは、[Sub プロシージャ](./sub-procedures.md)に対して実行するのと同じ方法で宣言します。</span><span class="sxs-lookup"><span data-stu-id="82578-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="82578-115">データ型</span><span class="sxs-lookup"><span data-stu-id="82578-115">Data Type</span></span>  
 <span data-ttu-id="82578-116">すべての `Function` プロシージャには、すべての変数と同様にデータ型があります。</span><span class="sxs-lookup"><span data-stu-id="82578-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="82578-117">このデータ型は、`Function` ステートメントの `As` 句によって指定され、関数が呼び出し元のコードに返す値のデータ型を決定します。</span><span class="sxs-lookup"><span data-stu-id="82578-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="82578-118">この例を次の宣言に示します。</span><span class="sxs-lookup"><span data-stu-id="82578-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="82578-119">詳細については、「[Function ステートメント](../../../../visual-basic/language-reference/statements/function-statement.md)」の「Parts」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82578-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="82578-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="82578-120">Returning Values</span></span>  
 <span data-ttu-id="82578-121">`Function` プロシージャから呼び出し元のコードに返される値は、戻り値と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="82578-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="82578-122">このプロシージャは、次の2つの方法のいずれかでこの値を返します。</span><span class="sxs-lookup"><span data-stu-id="82578-122">The procedure returns this value in one of two ways:</span></span>  
  
- <span data-ttu-id="82578-123">`Return` ステートメントを使用して戻り値を指定し、呼び出し元のプログラムに制御を直ちに返します。</span><span class="sxs-lookup"><span data-stu-id="82578-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="82578-124">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="82578-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- <span data-ttu-id="82578-125">このメソッドは、プロシージャの1つ以上のステートメントで、独自の関数名に値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="82578-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="82578-126">`Exit Function` または `End Function` ステートメントが実行されるまで、コントロールは呼び出し元のプログラムに戻りません。</span><span class="sxs-lookup"><span data-stu-id="82578-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="82578-127">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="82578-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="82578-128">関数名に戻り値を代入する利点は、コントロールが、`Exit Function` または `End Function` ステートメントを検出するまでプロシージャから戻らないことです。</span><span class="sxs-lookup"><span data-stu-id="82578-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="82578-129">これにより、必要に応じて暫定値を割り当て、後で調整することができます。</span><span class="sxs-lookup"><span data-stu-id="82578-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="82578-130">値を返す方法の詳細については、「[Function ステートメント](../../../../visual-basic/language-reference/statements/function-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82578-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="82578-131">配列を返す方法については、「[配列](../../../../visual-basic/programming-guide/language-features/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82578-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="82578-132">呼び出し構文</span><span class="sxs-lookup"><span data-stu-id="82578-132">Calling Syntax</span></span>  
 <span data-ttu-id="82578-133">`Function` プロシージャを呼び出すには、代入ステートメントの右側または式に名前と引数を含めます。</span><span class="sxs-lookup"><span data-stu-id="82578-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="82578-134">省略可能なすべての引数の値を指定する必要があり、引数リストをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="82578-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="82578-135">引数を指定しない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="82578-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="82578-136">`Function` プロシージャの呼び出しの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82578-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="82578-137">*左辺*値`=`*functionname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="82578-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="82578-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`*式*`) Then`</span><span class="sxs-lookup"><span data-stu-id="82578-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="82578-139">`Function` プロシージャを呼び出す場合、その戻り値を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="82578-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="82578-140">そうしないと、関数のすべてのアクションが実行されますが、戻り値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="82578-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="82578-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> は、多くの場合、この方法で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="82578-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="82578-142">宣言と呼び出しの図</span><span class="sxs-lookup"><span data-stu-id="82578-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="82578-143">次の `Function` プロシージャは、他の2つの辺の値を指定して、直角三角形の最長の辺 (斜辺) を計算します。</span><span class="sxs-lookup"><span data-stu-id="82578-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="82578-144">次の例は、`hypotenuse`の一般的な呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="82578-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="82578-145">参照</span><span class="sxs-lookup"><span data-stu-id="82578-145">See also</span></span>

- [<span data-ttu-id="82578-146">手順</span><span class="sxs-lookup"><span data-stu-id="82578-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="82578-147">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="82578-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="82578-148">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="82578-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="82578-149">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="82578-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="82578-150">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="82578-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="82578-151">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="82578-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="82578-152">方法 : 値を返すプロシージャを作成する</span><span class="sxs-lookup"><span data-stu-id="82578-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="82578-153">方法 : プロシージャから値を返す</span><span class="sxs-lookup"><span data-stu-id="82578-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="82578-154">方法: 値を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="82578-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
