---
title: Continue ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 5523be69f2901851c86f6c0263548e3577507ff9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638247"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="f95cf-102">Continue ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f95cf-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="f95cf-103">ループの次の反復処理に直ちに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="f95cf-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f95cf-104">構文</span><span class="sxs-lookup"><span data-stu-id="f95cf-104">Syntax</span></span>  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="f95cf-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="f95cf-105">Remarks</span></span>  
 <span data-ttu-id="f95cf-106">転送できます内で、 `Do`、 `For`、または`While`ループの次のイテレーションをループします。</span><span class="sxs-lookup"><span data-stu-id="f95cf-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="f95cf-107">パスに転送するのと同じですが、ループ条件テストをすぐに制御、`For`または`While`ステートメント、または、`Do`または`Loop`ステートメントを含む、`Until`または`While`句。</span><span class="sxs-lookup"><span data-stu-id="f95cf-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="f95cf-108">使用することができます`Continue`転送を許可するループ内で任意の位置。</span><span class="sxs-lookup"><span data-stu-id="f95cf-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="f95cf-109">コントロールの転送を許可する規則と同じ、 [GoTo ステートメント](../../../visual-basic/language-reference/statements/goto-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="f95cf-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="f95cf-110">たとえば、ループ処理が完全に含まれて、`Try`ブロック、`Catch`ブロック、または`Finally`ブロックを使用することができます`Continue`ループの外に転送します。</span><span class="sxs-lookup"><span data-stu-id="f95cf-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="f95cf-111">場合、その一方で、 `Try`.`End Try`ループ内で構造体が含まれている、使用することはできません`Continue`の制御を転送する、`Finally`ブロックとすることができます、転送に使用のうち、`Try`または`Catch`ブロックの完全に転送する場合にのみ、`Try`...`End Try`構造体。</span><span class="sxs-lookup"><span data-stu-id="f95cf-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="f95cf-112">たとえば、同じ型の入れ子になったループがあるかどうか、`Do`内に別のループ`Do`ループ、`Continue Do`最も内側の次の反復処理するステートメントをスキップします`Do`それを含んでいるループ。</span><span class="sxs-lookup"><span data-stu-id="f95cf-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="f95cf-113">使用することはできません`Continue`同じ種類の外側のループの次の反復処理をスキップします。</span><span class="sxs-lookup"><span data-stu-id="f95cf-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="f95cf-114">たとえば、さまざまな種類の入れ子になったループがあるかどうか、`Do`内でループを`For`ループに進んで、ループの次のイテレーションを使用して`Continue Do`または`Continue For`。</span><span class="sxs-lookup"><span data-stu-id="f95cf-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f95cf-115">例</span><span class="sxs-lookup"><span data-stu-id="f95cf-115">Example</span></span>  
 <span data-ttu-id="f95cf-116">次のコード例では、`Continue While`除数がゼロの場合は、配列の次の列をスキップするステートメント。</span><span class="sxs-lookup"><span data-stu-id="f95cf-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="f95cf-117">`Continue While`内では、`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="f95cf-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="f95cf-118">転送先、`While col < lastcol`ステートメントでは、最も内側の次のイテレーションである`While`ループが含まれている`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="f95cf-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="f95cf-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f95cf-119">See also</span></span>

- [<span data-ttu-id="f95cf-120">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="f95cf-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="f95cf-121">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="f95cf-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="f95cf-122">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="f95cf-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="f95cf-123">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="f95cf-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
