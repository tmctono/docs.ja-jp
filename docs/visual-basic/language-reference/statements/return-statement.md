---
title: Return ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: 7f8ec0456576133d37dd19b5c0f8878a7ac57dab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783904"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="5a280-102">Return ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a280-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="5a280-103">呼び出したコードに制御が戻ります、 `Function`、 `Sub`、 `Get`、 `Set`、または`Operator`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="5a280-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a280-104">構文</span><span class="sxs-lookup"><span data-stu-id="5a280-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="5a280-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="5a280-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="5a280-106">必要な`Function`、 `Get`、または`Operator`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="5a280-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="5a280-107">呼び出し元のコードに返される値を表す式です。</span><span class="sxs-lookup"><span data-stu-id="5a280-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a280-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5a280-108">Remarks</span></span>  
 <span data-ttu-id="5a280-109">`Sub`または`Set`プロシージャ、`Return`ステートメントは、`Exit Sub`または`Exit Property`ステートメントと`expression`を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="5a280-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="5a280-110">`Function`、 `Get`、または`Operator`、プロシージャ、`Return`ステートメントを含める必要があります`expression`、および`expression`プロシージャの戻り値の型に変換できるデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a280-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="5a280-111">`Function`または`Get`プロシージャ、また、ある別の戻り値として処理するために、プロシージャ名に式を代入し、実行する方法、`Exit Function`または`Exit Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="5a280-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="5a280-112">`Operator`使用する必要がありますプロシージャ、`Return expression`します。</span><span class="sxs-lookup"><span data-stu-id="5a280-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="5a280-113">多くとして含めることができます`Return`同じプロシージャ内に適切なステートメント。</span><span class="sxs-lookup"><span data-stu-id="5a280-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a280-114">コードを`Finally`ブロックを実行した後、`Return`内のステートメントを`Try`または`Catch`ブロックは、発生したが、その前に`Return`ステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a280-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="5a280-115">A`Return`でステートメントを含めることができません、`Finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="5a280-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a280-116">例</span><span class="sxs-lookup"><span data-stu-id="5a280-116">Example</span></span>  
 <span data-ttu-id="5a280-117">次の例では、`Return`ステートメント、プロシージャが他に行うがあるない場合に、呼び出し元のコードに戻るに何度もします。</span><span class="sxs-lookup"><span data-stu-id="5a280-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="5a280-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a280-118">See also</span></span>

- [<span data-ttu-id="5a280-119">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5a280-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5a280-121">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="5a280-122">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="5a280-123">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="5a280-124">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="5a280-125">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="5a280-126">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="5a280-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
