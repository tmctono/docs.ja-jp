---
title: 部分式
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: f862730220d0595faecaa915b1eaad2a3cdc0053
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406316"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="7eab1-102">部分式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eab1-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="7eab1-103">サブルーチン ラムダ式を定義するパラメーターとコードを宣言します。</span><span class="sxs-lookup"><span data-stu-id="7eab1-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eab1-104">構文</span><span class="sxs-lookup"><span data-stu-id="7eab1-104">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="7eab1-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7eab1-105">Parts</span></span>  
  
|<span data-ttu-id="7eab1-106">用語</span><span class="sxs-lookup"><span data-stu-id="7eab1-106">Term</span></span>|<span data-ttu-id="7eab1-107">定義</span><span class="sxs-lookup"><span data-stu-id="7eab1-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="7eab1-108">任意。</span><span class="sxs-lookup"><span data-stu-id="7eab1-108">Optional.</span></span> <span data-ttu-id="7eab1-109">プロシージャのパラメーターを表すローカル変数名のリスト。</span><span class="sxs-lookup"><span data-stu-id="7eab1-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="7eab1-110">リストが空の場合でも、かっこが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eab1-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="7eab1-111">詳細については、「 [Parameter List](../statements/parameter-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eab1-111">For more information, see [Parameter List](../statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="7eab1-112">必須です。</span><span class="sxs-lookup"><span data-stu-id="7eab1-112">Required.</span></span> <span data-ttu-id="7eab1-113">1 つのステートメント。</span><span class="sxs-lookup"><span data-stu-id="7eab1-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="7eab1-114">必須です。</span><span class="sxs-lookup"><span data-stu-id="7eab1-114">Required.</span></span> <span data-ttu-id="7eab1-115">ステートメントの一覧。</span><span class="sxs-lookup"><span data-stu-id="7eab1-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7eab1-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="7eab1-116">Remarks</span></span>  
 <span data-ttu-id="7eab1-117">*ラムダ式*は、1 つ以上のステートメントを実行する、名前のないサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="7eab1-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="7eab1-118">ラムダ式は、デリゲート型を使用できる場所であればどこでも使用できます。ただし、`RemoveHandler` の引数として使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7eab1-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="7eab1-119">デリゲートの詳細と、デリゲートでのラムダ式の使用の詳細については、「[Delegate ステートメント](../statements/delegate-statement.md)」と「[厳密でないデリゲート変換](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7eab1-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="7eab1-120">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="7eab1-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="7eab1-121">ラムダ式の構文は、標準のサブルーチンの構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="7eab1-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="7eab1-122">相違点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7eab1-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="7eab1-123">ラムダ式には名前がありません。</span><span class="sxs-lookup"><span data-stu-id="7eab1-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="7eab1-124">ラムダ式には、`Overloads` や `Overrides` などの修飾子を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="7eab1-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="7eab1-125">単一行のラムダ式の本体は、式ではなく、ステートメントでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7eab1-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="7eab1-126">本体は、サブ プロシージャの呼び出しで構成できますが、関数プロシージャの呼び出しでは構成できません。</span><span class="sxs-lookup"><span data-stu-id="7eab1-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="7eab1-127">ラムダ式では、すべてのパラメーターに対してデータ型を指定する必要があります。または、すべてのパラメーターを推論できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eab1-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="7eab1-128">ラムダ式では、省略可能なパラメーターと `ParamArray` パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7eab1-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="7eab1-129">ラムダ式では、ジェネリック パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7eab1-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7eab1-130">例</span><span class="sxs-lookup"><span data-stu-id="7eab1-130">Example</span></span>  
 <span data-ttu-id="7eab1-131">次の例は、コンソールに値を書き込むラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="7eab1-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="7eab1-132">この例は、サブルーチンの単一行および複数行のラムダ式の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="7eab1-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="7eab1-133">その他の例については、「[ラムダ式](../../programming-guide/language-features/procedures/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7eab1-133">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="7eab1-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eab1-134">See also</span></span>

- [<span data-ttu-id="7eab1-135">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eab1-135">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="7eab1-136">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="7eab1-136">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="7eab1-137">演算子および式</span><span class="sxs-lookup"><span data-stu-id="7eab1-137">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="7eab1-138">ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eab1-138">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="7eab1-139">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="7eab1-139">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
