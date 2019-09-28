---
title: Function 式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 0ab4a77395b478df06f34240212438f3e6e18f6e
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592204"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="e5fb0-102">Function 式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5fb0-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="e5fb0-103">関数ラムダ式を定義するパラメーターとコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5fb0-104">構文</span><span class="sxs-lookup"><span data-stu-id="e5fb0-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="e5fb0-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e5fb0-105">Parts</span></span>  
  
|<span data-ttu-id="e5fb0-106">項目</span><span class="sxs-lookup"><span data-stu-id="e5fb0-106">Term</span></span>|<span data-ttu-id="e5fb0-107">定義</span><span class="sxs-lookup"><span data-stu-id="e5fb0-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="e5fb0-108">任意。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-108">Optional.</span></span> <span data-ttu-id="e5fb0-109">このプロシージャのパラメーターを表すローカル変数名の一覧です。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="e5fb0-110">リストが空の場合でも、かっこは存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="e5fb0-111">「[パラメーターリスト](../../../visual-basic/language-reference/statements/parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="e5fb0-112">必須。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-112">Required.</span></span> <span data-ttu-id="e5fb0-113">1つの式。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-113">A single expression.</span></span> <span data-ttu-id="e5fb0-114">式の型は、関数の戻り値の型です。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="e5fb0-115">必須。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-115">Required.</span></span> <span data-ttu-id="e5fb0-116">@No__t-0 ステートメントを使用して値を返すステートメントの一覧。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="e5fb0-117">( [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)を参照してください)。返される値の型は、関数の戻り値の型です。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5fb0-118">コメント</span><span class="sxs-lookup"><span data-stu-id="e5fb0-118">Remarks</span></span>  
 <span data-ttu-id="e5fb0-119">*ラムダ式*は、値を計算して返す名前のない関数です。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="e5fb0-120">ラムダ式は、デリゲート型を使用できる場所であればどこでも使用できます。ただし、`RemoveHandler` の引数として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="e5fb0-121">デリゲートの詳細と、デリゲートでのラムダ式の使用については、「[デリゲートステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)」および「厳密でない[デリゲート変換](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="e5fb0-122">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="e5fb0-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="e5fb0-123">ラムダ式の構文は、標準関数の構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="e5fb0-124">違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="e5fb0-125">ラムダ式に名前がありません。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="e5fb0-126">ラムダ式には、`Overloads` や `Overrides` などの修飾子を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="e5fb0-127">ラムダ式では、関数の戻り値の型を指定するために `As` 句を使用しません。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="e5fb0-128">代わりに、型は、単一行のラムダ式の結果が評価される値、または複数行ラムダ式の戻り値から推論されます。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="e5fb0-129">たとえば、単一行のラムダ式の本体が `Where cust.City = "London"` の場合、その戻り値の型は `Boolean` になります。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="e5fb0-130">単一行のラムダ式の本体は、ステートメントではなく、式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="e5fb0-131">本文は、関数プロシージャの呼び出しで構成できますが、サブプロシージャの呼び出しでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="e5fb0-132">すべてのパラメーターのデータ型が指定されているか、すべてのパラメーターが推論される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="e5fb0-133">省略可能なおよび Paramarray パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="e5fb0-134">ジェネリックパラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5fb0-135">例</span><span class="sxs-lookup"><span data-stu-id="e5fb0-135">Example</span></span>  
 <span data-ttu-id="e5fb0-136">次の例は、単純なラムダ式を作成する2つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="e5fb0-137">最初のは、`Dim` を使用して、関数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="e5fb0-138">関数を呼び出すには、パラメーターの値を送信します。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="e5fb0-139">例</span><span class="sxs-lookup"><span data-stu-id="e5fb0-139">Example</span></span>  
 <span data-ttu-id="e5fb0-140">または、関数を同時に宣言して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="e5fb0-141">例</span><span class="sxs-lookup"><span data-stu-id="e5fb0-141">Example</span></span>  
 <span data-ttu-id="e5fb0-142">引数をインクリメントし、値を返すラムダ式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="e5fb0-143">この例では、関数の単一行と複数行のラムダ式の構文を示します。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="e5fb0-144">その他の例については、「[ラムダ式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="e5fb0-145">例</span><span class="sxs-lookup"><span data-stu-id="e5fb0-145">Example</span></span>  
 <span data-ttu-id="e5fb0-146">ラムダ式は @no__t 0 のクエリ演算子の多くを基にしており、メソッドベースのクエリで明示的に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="e5fb0-147">次の例は、一般的な @no__t 0 クエリの後に、クエリをメソッド形式に変換したものを示しています。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="e5fb0-148">クエリメソッドの詳細については、「[クエリ](../../../visual-basic/language-reference/queries/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="e5fb0-149">標準クエリ演算子の詳細については、「[標準クエリ演算子の概要](../../programming-guide/concepts/linq/standard-query-operators-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5fb0-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fb0-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5fb0-150">See also</span></span>

- [<span data-ttu-id="e5fb0-151">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="e5fb0-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e5fb0-152">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="e5fb0-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="e5fb0-153">演算子および式</span><span class="sxs-lookup"><span data-stu-id="e5fb0-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="e5fb0-154">ステートメント</span><span class="sxs-lookup"><span data-stu-id="e5fb0-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="e5fb0-155">値の比較</span><span class="sxs-lookup"><span data-stu-id="e5fb0-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="e5fb0-156">ブール式</span><span class="sxs-lookup"><span data-stu-id="e5fb0-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="e5fb0-157">If 演算子</span><span class="sxs-lookup"><span data-stu-id="e5fb0-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="e5fb0-158">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="e5fb0-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
