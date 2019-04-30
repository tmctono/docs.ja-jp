---
title: 部分式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5b26a091dc8eb7415702c3c2853a569324def7d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013505"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="cea46-102">部分式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cea46-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="cea46-103">パラメーターとサブルーチンのラムダ式を定義するコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="cea46-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea46-104">構文</span><span class="sxs-lookup"><span data-stu-id="cea46-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="cea46-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="cea46-105">Parts</span></span>  
  
|<span data-ttu-id="cea46-106">用語</span><span class="sxs-lookup"><span data-stu-id="cea46-106">Term</span></span>|<span data-ttu-id="cea46-107">定義</span><span class="sxs-lookup"><span data-stu-id="cea46-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="cea46-108">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cea46-108">Optional.</span></span> <span data-ttu-id="cea46-109">プロシージャのパラメーターを表すローカル変数名の一覧。</span><span class="sxs-lookup"><span data-stu-id="cea46-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="cea46-110">かっこは、リストが空の場合にも存在である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cea46-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="cea46-111">詳細については、「 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cea46-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="cea46-112">必須。</span><span class="sxs-lookup"><span data-stu-id="cea46-112">Required.</span></span> <span data-ttu-id="cea46-113">1 つのステートメント。</span><span class="sxs-lookup"><span data-stu-id="cea46-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="cea46-114">必須。</span><span class="sxs-lookup"><span data-stu-id="cea46-114">Required.</span></span> <span data-ttu-id="cea46-115">ステートメントの一覧。</span><span class="sxs-lookup"><span data-stu-id="cea46-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cea46-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="cea46-116">Remarks</span></span>  
 <span data-ttu-id="cea46-117">A*ラムダ式*名前がないサブルーチンは、1 つまたは複数のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="cea46-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="cea46-118">ラムダ式を任意の場所に使用できるデリゲート型への引数としてを除き使用できます`RemoveHandler`します。</span><span class="sxs-lookup"><span data-stu-id="cea46-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="cea46-119">デリゲート、およびデリゲートとラムダ式の使用に関する詳細については、次を参照してください。 [Delegate ステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)と[厳密でないデリゲート変換](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)します。</span><span class="sxs-lookup"><span data-stu-id="cea46-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="cea46-120">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="cea46-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="cea46-121">標準的なサブルーチンのラムダ式の構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="cea46-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="cea46-122">相違点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cea46-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="cea46-123">ラムダ式の名前ではありません。</span><span class="sxs-lookup"><span data-stu-id="cea46-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="cea46-124">ラムダ式はなどの修飾子を含めることはできません`Overloads`または`Overrides`します。</span><span class="sxs-lookup"><span data-stu-id="cea46-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="cea46-125">単一行のラムダ式の本体は、ステートメント、式ではないである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cea46-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="cea46-126">本文は、sub プロシージャへの呼び出しが、function プロシージャへの呼び出しではないので構成できます。</span><span class="sxs-lookup"><span data-stu-id="cea46-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="cea46-127">ラムダ式でデータ型またはすべてのパラメーターを推論する必要がありますかすべてのパラメーターが指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cea46-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="cea46-128">省略可能なと`ParamArray`パラメーターはラムダ式で許可されていません。</span><span class="sxs-lookup"><span data-stu-id="cea46-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="cea46-129">ジェネリック パラメーターはラムダ式で許可されていません。</span><span class="sxs-lookup"><span data-stu-id="cea46-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cea46-130">例</span><span class="sxs-lookup"><span data-stu-id="cea46-130">Example</span></span>  
 <span data-ttu-id="cea46-131">値をコンソールに出力するラムダ式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cea46-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="cea46-132">この例では、サブルーチンの両方の単一行および複数行のラムダ式構文を示します。</span><span class="sxs-lookup"><span data-stu-id="cea46-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="cea46-133">例については、次を参照してください。[ラムダ式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="cea46-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="cea46-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="cea46-134">See also</span></span>

- [<span data-ttu-id="cea46-135">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="cea46-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="cea46-136">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="cea46-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="cea46-137">演算子および式</span><span class="sxs-lookup"><span data-stu-id="cea46-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="cea46-138">ステートメント</span><span class="sxs-lookup"><span data-stu-id="cea46-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="cea46-139">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="cea46-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
