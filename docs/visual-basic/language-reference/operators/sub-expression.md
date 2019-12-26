---
title: Sub 式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: d284e629ea0b0a4e9b6eb9e098612bb07c38723b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350899"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="e6535-102">Sub 式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6535-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="e6535-103">サブルーチンラムダ式を定義するパラメーターとコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="e6535-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6535-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6535-104">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="e6535-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="e6535-105">Parts</span></span>  
  
|<span data-ttu-id="e6535-106">用語</span><span class="sxs-lookup"><span data-stu-id="e6535-106">Term</span></span>|<span data-ttu-id="e6535-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e6535-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="e6535-108">省略可。</span><span class="sxs-lookup"><span data-stu-id="e6535-108">Optional.</span></span> <span data-ttu-id="e6535-109">プロシージャのパラメーターを表すローカル変数名の一覧です。</span><span class="sxs-lookup"><span data-stu-id="e6535-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="e6535-110">リストが空の場合でも、かっこは存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6535-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="e6535-111">詳細については、「[パラメーター リスト](../../../visual-basic/language-reference/statements/parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6535-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="e6535-112">必須。</span><span class="sxs-lookup"><span data-stu-id="e6535-112">Required.</span></span> <span data-ttu-id="e6535-113">1つのステートメント。</span><span class="sxs-lookup"><span data-stu-id="e6535-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="e6535-114">必須。</span><span class="sxs-lookup"><span data-stu-id="e6535-114">Required.</span></span> <span data-ttu-id="e6535-115">ステートメントの一覧。</span><span class="sxs-lookup"><span data-stu-id="e6535-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6535-116">コメント</span><span class="sxs-lookup"><span data-stu-id="e6535-116">Remarks</span></span>  
 <span data-ttu-id="e6535-117">*ラムダ式*は、名前がなく、1つ以上のステートメントを実行するサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="e6535-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="e6535-118">ラムダ式は、デリゲート型を使用できる場所であればどこでも使用できます。ただし、`RemoveHandler`の引数として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6535-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="e6535-119">デリゲートの詳細と、デリゲートでのラムダ式の使用については、「[Delegate ステートメント](../../../visual-basic/language-reference/statements/delegate-statement.md)」および「[厳密でないデリゲート変換](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6535-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="e6535-120">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="e6535-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="e6535-121">ラムダ式の構文は、標準のサブルーチンの構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="e6535-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="e6535-122">相違点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e6535-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="e6535-123">ラムダ式に名前がありません。</span><span class="sxs-lookup"><span data-stu-id="e6535-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="e6535-124">ラムダ式には、`Overloads` や `Overrides`などの修飾子を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e6535-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="e6535-125">単一行のラムダ式の本体は、式ではなく、ステートメントでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e6535-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="e6535-126">本文は、Sub プロシージャの呼び出しで構成できますが、Function プロシージャを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e6535-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="e6535-127">ラムダ式では、すべてのパラメーターのデータ型が指定されているか、すべてのパラメーターが推論される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6535-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="e6535-128">ラムダ式では、省略可能なパラメーターと `ParamArray` パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e6535-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="e6535-129">ラムダ式ではジェネリックパラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e6535-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6535-130">例</span><span class="sxs-lookup"><span data-stu-id="e6535-130">Example</span></span>  
 <span data-ttu-id="e6535-131">値をコンソールに書き込むラムダ式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e6535-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="e6535-132">この例では、サブルーチンの単一行と複数行のラムダ式の構文の両方を示しています。</span><span class="sxs-lookup"><span data-stu-id="e6535-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="e6535-133">その他の例については、「[ラムダ式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6535-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="e6535-134">参照</span><span class="sxs-lookup"><span data-stu-id="e6535-134">See also</span></span>

- [<span data-ttu-id="e6535-135">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="e6535-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="e6535-136">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="e6535-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="e6535-137">演算子および式</span><span class="sxs-lookup"><span data-stu-id="e6535-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="e6535-138">ステートメント</span><span class="sxs-lookup"><span data-stu-id="e6535-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="e6535-139">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="e6535-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
