---
title: Function 式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 4bef609289cdbb192116469bac4fca66ee10fd09
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662518"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="5aeea-102">Function 式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5aeea-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="5aeea-103">パラメーターと、関数ラムダ式を定義するコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aeea-104">構文</span><span class="sxs-lookup"><span data-stu-id="5aeea-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="5aeea-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="5aeea-105">Parts</span></span>  
  
|<span data-ttu-id="5aeea-106">用語</span><span class="sxs-lookup"><span data-stu-id="5aeea-106">Term</span></span>|<span data-ttu-id="5aeea-107">定義</span><span class="sxs-lookup"><span data-stu-id="5aeea-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="5aeea-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5aeea-108">Optional.</span></span> <span data-ttu-id="5aeea-109">このプロシージャのパラメーターを表すローカル変数名の一覧。</span><span class="sxs-lookup"><span data-stu-id="5aeea-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="5aeea-110">かっこは、リストが空の場合にも存在である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aeea-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="5aeea-111">参照してください[パラメーター リスト](../../../visual-basic/language-reference/statements/parameter-list.md)します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="5aeea-112">必須。</span><span class="sxs-lookup"><span data-stu-id="5aeea-112">Required.</span></span> <span data-ttu-id="5aeea-113">1 つの式。</span><span class="sxs-lookup"><span data-stu-id="5aeea-113">A single expression.</span></span> <span data-ttu-id="5aeea-114">式の型は、関数の戻り値の型です。</span><span class="sxs-lookup"><span data-stu-id="5aeea-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="5aeea-115">必須。</span><span class="sxs-lookup"><span data-stu-id="5aeea-115">Required.</span></span> <span data-ttu-id="5aeea-116">使用して値を返すステートメントの一覧、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="5aeea-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="5aeea-117">(を参照してください[Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md))。返される値の型は、関数の戻り値の型です。</span><span class="sxs-lookup"><span data-stu-id="5aeea-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5aeea-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="5aeea-118">Remarks</span></span>  
 <span data-ttu-id="5aeea-119">A*ラムダ式*を計算し、値を返します名のない関数です。</span><span class="sxs-lookup"><span data-stu-id="5aeea-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="5aeea-120">ラムダ式を使用することができますを引数としてを除く、デリゲート型を使用する任意の場所`RemoveHandler`します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="5aeea-121">デリゲート、およびデリゲートとラムダ式の使用に関する詳細については、次を参照してください。 [Delegate ステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)と[厳密でないデリゲート変換](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="5aeea-122">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="5aeea-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="5aeea-123">ラムダ式の構文では、標準的な関数に似ています。</span><span class="sxs-lookup"><span data-stu-id="5aeea-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="5aeea-124">相違点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5aeea-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="5aeea-125">ラムダ式の名前ではありません。</span><span class="sxs-lookup"><span data-stu-id="5aeea-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="5aeea-126">ラムダ式などで、修飾子を含めることはできません`Overloads`または`Overrides`します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="5aeea-127">ラムダ式は使用しないでください、`As`関数の戻り値の型を指定する句。</span><span class="sxs-lookup"><span data-stu-id="5aeea-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="5aeea-128">代わりに、型は、1 行のラムダ式の本体が評価される値または複数行のラムダ式の戻り値から推論されます。</span><span class="sxs-lookup"><span data-stu-id="5aeea-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="5aeea-129">たとえば、1 行のラムダ式の本体が`Where cust.City = "London"`、戻り値の型は`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="5aeea-130">単一行のラムダ式の本体は、ステートメントではなく、式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aeea-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="5aeea-131">本文は、関数、プロシージャの呼び出しが sub プロシージャへの呼び出しではないので構成できます。</span><span class="sxs-lookup"><span data-stu-id="5aeea-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="5aeea-132">すべてのパラメーターまたはすべてのデータ型を推論する必要があります指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aeea-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="5aeea-133">(省略可能) と Paramarray パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5aeea-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="5aeea-134">ジェネリック パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5aeea-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aeea-135">例</span><span class="sxs-lookup"><span data-stu-id="5aeea-135">Example</span></span>  
 <span data-ttu-id="5aeea-136">次の例では、単純なラムダ式を作成する 2 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="5aeea-137">最初の使用、`Dim`関数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="5aeea-138">関数を呼び出すには、パラメーターの値で送信します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="5aeea-139">例</span><span class="sxs-lookup"><span data-stu-id="5aeea-139">Example</span></span>  
 <span data-ttu-id="5aeea-140">またはを宣言し、同時に、関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="5aeea-141">例</span><span class="sxs-lookup"><span data-stu-id="5aeea-141">Example</span></span>  
 <span data-ttu-id="5aeea-142">引数をインクリメントし、値を返すラムダ式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="5aeea-143">この例では、単一行および複数行のラムダ式の両方の構文、関数を示します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="5aeea-144">例については、次を参照してください。[ラムダ式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="5aeea-145">例</span><span class="sxs-lookup"><span data-stu-id="5aeea-145">Example</span></span>  
 <span data-ttu-id="5aeea-146">ラムダ式では、多くのクエリ演算子の基本となる[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]、メソッド ベースのクエリで明示的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5aeea-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="5aeea-147">次の例は、一般的な[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]メソッドの形式に、クエリの変換後にクエリします。</span><span class="sxs-lookup"><span data-stu-id="5aeea-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="5aeea-148">クエリ メソッドの詳細については、次を参照してください。[クエリ](../../../visual-basic/language-reference/queries/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="5aeea-149">標準クエリ演算子の詳細については、次を参照してください。[標準クエリ演算子の概要](../../programming-guide/concepts/linq/standard-query-operators-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="5aeea-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aeea-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="5aeea-150">See also</span></span>

- [<span data-ttu-id="5aeea-151">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="5aeea-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5aeea-152">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="5aeea-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="5aeea-153">演算子および式</span><span class="sxs-lookup"><span data-stu-id="5aeea-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="5aeea-154">ステートメント</span><span class="sxs-lookup"><span data-stu-id="5aeea-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="5aeea-155">値の比較</span><span class="sxs-lookup"><span data-stu-id="5aeea-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="5aeea-156">ブール式</span><span class="sxs-lookup"><span data-stu-id="5aeea-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="5aeea-157">If 演算子</span><span class="sxs-lookup"><span data-stu-id="5aeea-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="5aeea-158">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="5aeea-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
