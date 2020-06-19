---
title: Function 式
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: a9b621ff03f833fcf0f07f876fd864ee963bef75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371182"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="e0baf-102">Function 式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0baf-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="e0baf-103">関数ラムダ式を定義するパラメーターとコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e0baf-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0baf-104">構文</span><span class="sxs-lookup"><span data-stu-id="e0baf-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="e0baf-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e0baf-105">Parts</span></span>  
  
|<span data-ttu-id="e0baf-106">用語</span><span class="sxs-lookup"><span data-stu-id="e0baf-106">Term</span></span>|<span data-ttu-id="e0baf-107">定義</span><span class="sxs-lookup"><span data-stu-id="e0baf-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="e0baf-108">任意。</span><span class="sxs-lookup"><span data-stu-id="e0baf-108">Optional.</span></span> <span data-ttu-id="e0baf-109">このプロシージャのパラメーターを表すローカル変数名のリスト。</span><span class="sxs-lookup"><span data-stu-id="e0baf-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="e0baf-110">リストが空の場合でも、かっこが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0baf-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="e0baf-111">「[パラメーター リスト](../statements/parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0baf-111">See [Parameter List](../statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="e0baf-112">必須です。</span><span class="sxs-lookup"><span data-stu-id="e0baf-112">Required.</span></span> <span data-ttu-id="e0baf-113">単一の式。</span><span class="sxs-lookup"><span data-stu-id="e0baf-113">A single expression.</span></span> <span data-ttu-id="e0baf-114">式の型は、関数の戻り値の型です。</span><span class="sxs-lookup"><span data-stu-id="e0baf-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="e0baf-115">必須です。</span><span class="sxs-lookup"><span data-stu-id="e0baf-115">Required.</span></span> <span data-ttu-id="e0baf-116">`Return` ステートメントを使用して値を返すステートメントのリスト。</span><span class="sxs-lookup"><span data-stu-id="e0baf-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="e0baf-117">(「[Return ステートメント](../statements/return-statement.md)」を参照してください。)戻される値の型は、関数の戻り値の型です。</span><span class="sxs-lookup"><span data-stu-id="e0baf-117">(See [Return Statement](../statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0baf-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0baf-118">Remarks</span></span>  
 <span data-ttu-id="e0baf-119">*ラムダ式*は、値を計算して返す、名前を持たない関数です。</span><span class="sxs-lookup"><span data-stu-id="e0baf-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="e0baf-120">ラムダ式は、デリゲート型を使用できる場所であればどこでも使用できます。ただし、`RemoveHandler` の引数として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="e0baf-121">デリゲートの詳細と、デリゲートでのラムダ式の使用の詳細については、「[Delegate ステートメント](../statements/delegate-statement.md)」と「[厳密でないデリゲート変換](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0baf-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="e0baf-122">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="e0baf-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="e0baf-123">ラムダ式の構文は、標準の関数の構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="e0baf-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="e0baf-124">相違点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0baf-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="e0baf-125">ラムダ式には名前はありません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="e0baf-126">ラムダ式には、`Overloads` や `Overrides` などの修飾子を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="e0baf-127">ラムダ式では、関数の戻り値の型を指定するために `As` 句は使用されません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="e0baf-128">代わりに、単一行のラムダ式の本体が評価された結果の値、または複数行のラムダ式の戻り値から型が推論されます。</span><span class="sxs-lookup"><span data-stu-id="e0baf-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="e0baf-129">たとえば、単一行のラムダ式の本体が `Where cust.City = "London"` の場合、戻り値の型は `Boolean` になります。</span><span class="sxs-lookup"><span data-stu-id="e0baf-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="e0baf-130">単一行のラムダ式の本体は、ステートメントではなく、式でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="e0baf-131">本体は、関数プロシージャの呼び出しで構成できますが、サブ プロシージャの呼び出しでは構成できません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="e0baf-132">すべてのパラメーターにデータ型が指定されているか、すべてが推論される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0baf-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="e0baf-133">省略可能なパラメーターと Paramarray パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="e0baf-134">ジェネリック パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e0baf-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0baf-135">例</span><span class="sxs-lookup"><span data-stu-id="e0baf-135">Example</span></span>  
 <span data-ttu-id="e0baf-136">次の例は、単純なラムダ式を作成する 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0baf-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="e0baf-137">最初の方法では、`Dim` を使用して関数の名前を指定しています。</span><span class="sxs-lookup"><span data-stu-id="e0baf-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="e0baf-138">関数を呼び出すには、パラメーターの値を送信します。</span><span class="sxs-lookup"><span data-stu-id="e0baf-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="e0baf-139">例</span><span class="sxs-lookup"><span data-stu-id="e0baf-139">Example</span></span>  
 <span data-ttu-id="e0baf-140">別の方法として、関数の宣言と実行を同時に行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e0baf-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="e0baf-141">例</span><span class="sxs-lookup"><span data-stu-id="e0baf-141">Example</span></span>  
 <span data-ttu-id="e0baf-142">次の例は、引数をインクリメントして値を返すラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="e0baf-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="e0baf-143">この例は、関数の単一行および複数行のラムダ式の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0baf-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="e0baf-144">その他の例については、「[ラムダ式](../../programming-guide/language-features/procedures/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0baf-144">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="e0baf-145">例</span><span class="sxs-lookup"><span data-stu-id="e0baf-145">Example</span></span>  
 <span data-ttu-id="e0baf-146">ラムダ式は、統合言語クエリ (LINQ) のクエリ演算子の多くを基にしており、メソッド ベースのクエリで明示的に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0baf-146">Lambda expressions underlie many of the query operators in Language-Integrated Query (LINQ), and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="e0baf-147">次の例は、一般的な LINQ クエリを示し、続いてそのクエリをメソッド形式のクエリに変換する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0baf-147">The following example shows a typical LINQ query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="e0baf-148">クエリ メソッドの詳細については、「[クエリ](../queries/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0baf-148">For more information about query methods, see [Queries](../queries/index.md).</span></span> <span data-ttu-id="e0baf-149">標準クエリ演算子の詳細については、「[標準クエリ演算子の概要](../../programming-guide/concepts/linq/standard-query-operators-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0baf-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0baf-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0baf-150">See also</span></span>

- [<span data-ttu-id="e0baf-151">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="e0baf-151">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="e0baf-152">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="e0baf-152">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="e0baf-153">演算子および式</span><span class="sxs-lookup"><span data-stu-id="e0baf-153">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="e0baf-154">ステートメント</span><span class="sxs-lookup"><span data-stu-id="e0baf-154">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="e0baf-155">値の比較</span><span class="sxs-lookup"><span data-stu-id="e0baf-155">Value Comparisons</span></span>](../../programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="e0baf-156">ブール式</span><span class="sxs-lookup"><span data-stu-id="e0baf-156">Boolean Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="e0baf-157">If 演算子</span><span class="sxs-lookup"><span data-stu-id="e0baf-157">If Operator</span></span>](if-operator.md)
- [<span data-ttu-id="e0baf-158">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="e0baf-158">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
