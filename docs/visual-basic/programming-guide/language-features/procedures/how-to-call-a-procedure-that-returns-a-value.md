---
title: '方法: 値を返すプロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 7f5d46babf31ea3c6babb29c0f1c08a23e51d598
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340739"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="1f3a5-102">方法: 値を返すプロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f3a5-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="1f3a5-103">`Function` プロシージャは、呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="1f3a5-104">これを呼び出すには、代入ステートメントの右側または式に名前と引数を含めます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="1f3a5-105">式内で関数プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="1f3a5-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="1f3a5-106">`Function` プロシージャ名は、変数を使用する場合と同じ方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="1f3a5-107">式で変数または定数を使用できる場所であればどこでも、`Function` プロシージャ呼び出しを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="1f3a5-108">引数リストを囲むには、プロシージャ名をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1f3a5-109">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="1f3a5-110">ただし、かっこを使用すると、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="1f3a5-111">引数リストに引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1f3a5-112">引数は、`Function` プロシージャが対応するパラメーターを定義する順序と同じ順序で指定してください。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="1f3a5-113">または、名前で1つ以上の引数を渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="1f3a5-114">詳細については、「[位置と名前による引数の引き渡し](./passing-arguments-by-position-and-by-name.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="1f3a5-115">プロシージャから返される値は、変数または定数の値と同じように、式に含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="1f3a5-116">代入ステートメントで Function プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="1f3a5-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="1f3a5-117">代入ステートメントで等号 (`=`) の後に `Function` プロシージャ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="1f3a5-118">引数リストを囲むには、プロシージャ名をかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1f3a5-119">引数がない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="1f3a5-120">ただし、かっこを使用すると、コードが読みやすくなります。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="1f3a5-121">引数リストに引数をコンマで区切ってかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1f3a5-122">引数は、名前で渡す場合を除き、`Function` プロシージャが対応するパラメーターを定義する順序と同じ順序で指定してください。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="1f3a5-123">プロシージャから返される値は、代入ステートメントの左側にある変数またはプロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f3a5-124">例</span><span class="sxs-lookup"><span data-stu-id="1f3a5-124">Example</span></span>  
 <span data-ttu-id="1f3a5-125">次の例では、Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> を呼び出して、オペレーティングシステム環境変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="1f3a5-126">最初の行は、式の中で `Environ` を呼び出し、2番目の行は代入ステートメントでそれを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="1f3a5-127">`Environ` は、変数名を唯一の引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="1f3a5-128">このメソッドは、呼び出し元のコードに変数の値を返します。</span><span class="sxs-lookup"><span data-stu-id="1f3a5-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="1f3a5-129">参照</span><span class="sxs-lookup"><span data-stu-id="1f3a5-129">See also</span></span>

- [<span data-ttu-id="1f3a5-130">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="1f3a5-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="1f3a5-131">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="1f3a5-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1f3a5-132">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="1f3a5-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1f3a5-133">方法 : 値を返すプロシージャを作成する</span><span class="sxs-lookup"><span data-stu-id="1f3a5-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="1f3a5-134">方法 : プロシージャから値を返す</span><span class="sxs-lookup"><span data-stu-id="1f3a5-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="1f3a5-135">方法 : 値を返さないプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="1f3a5-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
