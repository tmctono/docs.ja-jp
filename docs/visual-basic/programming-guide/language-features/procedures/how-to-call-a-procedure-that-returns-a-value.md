---
title: '方法: 値 (Visual Basic) を返すプロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 6f45f01489ee84b6addb1f7c7c8dc584332f38dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864183"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="50cbc-102">方法: 値 (Visual Basic) を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="50cbc-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="50cbc-103">A`Function`プロシージャが呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="50cbc-104">呼び出すことが、名前と引数を含めることによって、式または代入ステートメントの右側にあるいずれか。</span><span class="sxs-lookup"><span data-stu-id="50cbc-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="50cbc-105">式の中で関数のプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="50cbc-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="50cbc-106">使用して、`Function`プロシージャ名の変数を使用する場合と同じ方法です。</span><span class="sxs-lookup"><span data-stu-id="50cbc-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="50cbc-107">使用することができます、`Function`プロシージャを呼び出す任意の場所、式で変数または定数を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="50cbc-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="50cbc-108">引数リストを囲む中かっこでプロシージャ名に従ってください。</span><span class="sxs-lookup"><span data-stu-id="50cbc-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="50cbc-109">引数がない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="50cbc-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="50cbc-110">ただし、かっこを使用して、コードを読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="50cbc-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="50cbc-111">コンマで区切り、かっこ内の引数リストで、引数を配置します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="50cbc-112">同じ順序で引数を指定するかどうかを必ずを`Function`プロシージャが、対応するパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="50cbc-113">また、名前で、1 つまたは複数の引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="50cbc-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="50cbc-114">詳細については、次を参照してください。[位置と名前による引数を渡す](./passing-arguments-by-position-and-by-name.md)します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="50cbc-115">プロシージャから返される値は、式は、変数の値と同じように参加または定数します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="50cbc-116">代入ステートメントでプロシージャを関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="50cbc-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="50cbc-117">使用して、`Function`プロシージャ名の後に続く (`=`) 代入ステートメントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="50cbc-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="50cbc-118">引数リストを囲む中かっこでプロシージャ名に従ってください。</span><span class="sxs-lookup"><span data-stu-id="50cbc-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="50cbc-119">引数がない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="50cbc-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="50cbc-120">ただし、かっこを使用して、コードを読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="50cbc-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="50cbc-121">コンマで区切り、かっこ内の引数リストで、引数を配置します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="50cbc-122">同じ順序で引数を指定するかどうかを必ずを`Function`名で渡すことがない限り、プロシージャが、対応するパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="50cbc-123">プロシージャから返される値は、変数または代入ステートメントの左側にあるプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="50cbc-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50cbc-124">例</span><span class="sxs-lookup"><span data-stu-id="50cbc-124">Example</span></span>  
 <span data-ttu-id="50cbc-125">次の例では、Visual Basic<xref:Microsoft.VisualBasic.Interaction.Environ%2A>オペレーティング システム環境変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="50cbc-126">最初の行呼び出し`Environ`代入ステートメントでその行によって式と、2 つ目の呼び出し。</span><span class="sxs-lookup"><span data-stu-id="50cbc-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="50cbc-127">`Environ` その単一の引数として変数名を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="50cbc-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="50cbc-128">呼び出し元のコードに変数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="50cbc-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="50cbc-129">See also</span></span>

- [<span data-ttu-id="50cbc-130">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="50cbc-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="50cbc-131">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="50cbc-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="50cbc-132">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="50cbc-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="50cbc-133">方法: 値を返すプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="50cbc-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="50cbc-134">方法: プロシージャから値を返す</span><span class="sxs-lookup"><span data-stu-id="50cbc-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="50cbc-135">方法: 値を返さないプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="50cbc-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
