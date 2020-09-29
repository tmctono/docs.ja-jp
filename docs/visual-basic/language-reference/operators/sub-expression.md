---
title: 部分式
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: e564fa3f717fc1a9f4e9961d9b3e961912a4d56b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873332"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="9990d-102">部分式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9990d-102">Sub Expression (Visual Basic)</span></span>

<span data-ttu-id="9990d-103">サブルーチン ラムダ式を定義するパラメーターとコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="9990d-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9990d-104">構文</span><span class="sxs-lookup"><span data-stu-id="9990d-104">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="9990d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9990d-105">Parts</span></span>  
  
|<span data-ttu-id="9990d-106">用語</span><span class="sxs-lookup"><span data-stu-id="9990d-106">Term</span></span>|<span data-ttu-id="9990d-107">定義</span><span class="sxs-lookup"><span data-stu-id="9990d-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="9990d-108">任意。</span><span class="sxs-lookup"><span data-stu-id="9990d-108">Optional.</span></span> <span data-ttu-id="9990d-109">プロシージャのパラメーターを表すローカル変数名のリスト。</span><span class="sxs-lookup"><span data-stu-id="9990d-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="9990d-110">リストが空の場合でも、かっこが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9990d-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="9990d-111">詳細については、「 [Parameter List](../statements/parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9990d-111">For more information, see [Parameter List](../statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="9990d-112">必須です。</span><span class="sxs-lookup"><span data-stu-id="9990d-112">Required.</span></span> <span data-ttu-id="9990d-113">1 つのステートメント。</span><span class="sxs-lookup"><span data-stu-id="9990d-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="9990d-114">必須です。</span><span class="sxs-lookup"><span data-stu-id="9990d-114">Required.</span></span> <span data-ttu-id="9990d-115">ステートメントの一覧。</span><span class="sxs-lookup"><span data-stu-id="9990d-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9990d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="9990d-116">Remarks</span></span>  

 <span data-ttu-id="9990d-117">*ラムダ式*は、1 つ以上のステートメントを実行する、名前のないサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="9990d-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="9990d-118">ラムダ式は、デリゲート型を使用できる場所であればどこでも使用できます。ただし、`RemoveHandler` の引数として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9990d-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="9990d-119">デリゲートの詳細と、デリゲートでのラムダ式の使用の詳細については、「[Delegate ステートメント](../statements/delegate-statement.md)」と「[厳密でないデリゲート変換](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9990d-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="9990d-120">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="9990d-120">Lambda Expression Syntax</span></span>  

 <span data-ttu-id="9990d-121">ラムダ式の構文は、標準のサブルーチンの構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="9990d-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="9990d-122">相違点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9990d-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="9990d-123">ラムダ式には名前がありません。</span><span class="sxs-lookup"><span data-stu-id="9990d-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="9990d-124">ラムダ式には、`Overloads` や `Overrides` などの修飾子を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="9990d-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="9990d-125">単一行のラムダ式の本体は、式ではなく、ステートメントでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9990d-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="9990d-126">本体は、サブ プロシージャの呼び出しで構成できますが、関数プロシージャの呼び出しでは構成できません。</span><span class="sxs-lookup"><span data-stu-id="9990d-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="9990d-127">ラムダ式では、すべてのパラメーターに対してデータ型を指定する必要があります。または、すべてのパラメーターを推論できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9990d-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="9990d-128">ラムダ式では、省略可能なパラメーターと `ParamArray` パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9990d-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="9990d-129">ラムダ式では、ジェネリック パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9990d-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9990d-130">例</span><span class="sxs-lookup"><span data-stu-id="9990d-130">Example</span></span>  

 <span data-ttu-id="9990d-131">次の例は、コンソールに値を書き込むラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="9990d-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="9990d-132">この例は、サブルーチンの単一行および複数行のラムダ式の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="9990d-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="9990d-133">その他の例については、「[ラムダ式](../../programming-guide/language-features/procedures/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9990d-133">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="9990d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="9990d-134">See also</span></span>

- [<span data-ttu-id="9990d-135">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="9990d-135">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="9990d-136">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="9990d-136">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="9990d-137">演算子および式</span><span class="sxs-lookup"><span data-stu-id="9990d-137">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="9990d-138">ステートメント</span><span class="sxs-lookup"><span data-stu-id="9990d-138">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="9990d-139">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="9990d-139">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
