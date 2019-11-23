---
title: Continue ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 9ee5fb19db6eafeb7e4bed12935d0b950d6368d6
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005104"
---
# <a name="continue-statement-visual-basic"></a><span data-ttu-id="6704c-102">Continue ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6704c-102">Continue Statement (Visual Basic)</span></span>
<span data-ttu-id="6704c-103">ループの次の反復処理に制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="6704c-103">Transfers control immediately to the next iteration of a loop.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6704c-104">構文</span><span class="sxs-lookup"><span data-stu-id="6704c-104">Syntax</span></span>  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a><span data-ttu-id="6704c-105">コメント</span><span class="sxs-lookup"><span data-stu-id="6704c-105">Remarks</span></span>  
 <span data-ttu-id="6704c-106">`Do`、`For`、または `While` ループ内から、ループの次の反復処理に転送できます。</span><span class="sxs-lookup"><span data-stu-id="6704c-106">You can transfer from inside a `Do`, `For`, or `While` loop to the next iteration of that loop.</span></span> <span data-ttu-id="6704c-107">制御はすぐにループ条件テストに渡されます。これは、`For` または `While` ステートメントに転送するのと同じです。また、`Until` または `While` 句が含まれている `Do` または `Loop` ステートメントに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="6704c-107">Control passes immediately to the loop condition test, which is equivalent to transferring to the `For` or `While` statement, or to the `Do` or `Loop` statement that contains the `Until` or `While` clause.</span></span>  
  
 <span data-ttu-id="6704c-108">`Continue` は、転送を許可するループ内の任意の場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6704c-108">You can use `Continue` at any location in the loop that allows transfers.</span></span> <span data-ttu-id="6704c-109">制御の転送を許可する規則は、 [GoTo ステートメント](../../../visual-basic/language-reference/statements/goto-statement.md)と同じです。</span><span class="sxs-lookup"><span data-stu-id="6704c-109">The rules allowing transfer of control are the same as with the [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md).</span></span>  
  
 <span data-ttu-id="6704c-110">たとえば、ループが `Try` ブロック、`Catch` ブロック、または `Finally` ブロック内に完全に含まれている場合は、`Continue` を使用してループから転送できます。</span><span class="sxs-lookup"><span data-stu-id="6704c-110">For example, if a loop is totally contained within a `Try` block, a `Catch` block, or a `Finally` block, you can use `Continue` to transfer out of the loop.</span></span> <span data-ttu-id="6704c-111">一方、`Try`...`End Try` 構造がループ内に含まれている場合、`Continue` を使用して `Finally` ブロックから制御を移すことはできません。また、`Try` 構造から完全に転送した場合にのみ、`Catch` または `Try`ブロックから転送することもできます。`End Try`</span><span class="sxs-lookup"><span data-stu-id="6704c-111">If, on the other hand, the `Try`...`End Try` structure is contained within the loop, you cannot use `Continue` to transfer control out of the `Finally` block, and you can use it to transfer out of a `Try` or `Catch` block only if you transfer completely out of the `Try`...`End Try` structure.</span></span>  
  
 <span data-ttu-id="6704c-112">同じ種類のループが入れ子になっている場合 (たとえば、別の `Do` ループ内の `Do` ループ)、`Continue Do` ステートメントは、それを含む最も内側の `Do` ループの次の反復処理にスキップします。</span><span class="sxs-lookup"><span data-stu-id="6704c-112">If you have nested loops of the same type, for example a `Do` loop within another `Do` loop, a `Continue Do` statement skips to the next iteration of the innermost `Do` loop that contains it.</span></span> <span data-ttu-id="6704c-113">`Continue` を使用して、同じ型の含まれているループの次の反復処理にスキップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6704c-113">You cannot use `Continue` to skip to the next iteration of a containing loop of the same type.</span></span>  
  
 <span data-ttu-id="6704c-114">さまざまな種類のループが入れ子になっている場合 (`For` ループ内の `Do` ループなど)、`Continue Do` または `Continue For`を使用して、いずれかのループの次の反復処理に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="6704c-114">If you have nested loops of different types, for example a `Do` loop within a `For` loop, you can skip to the next iteration of either loop by using either `Continue Do` or `Continue For`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6704c-115">例</span><span class="sxs-lookup"><span data-stu-id="6704c-115">Example</span></span>  
 <span data-ttu-id="6704c-116">次のコード例では、除数が0の場合に、`Continue While` ステートメントを使用して、配列の次の列にスキップします。</span><span class="sxs-lookup"><span data-stu-id="6704c-116">The following code example uses the `Continue While` statement to skip to the next column of an array if a divisor is zero.</span></span> <span data-ttu-id="6704c-117">`Continue While` が `For` ループ内にあります。</span><span class="sxs-lookup"><span data-stu-id="6704c-117">The `Continue While` is inside a `For` loop.</span></span> <span data-ttu-id="6704c-118">`While col < lastcol` ステートメントに転送されます。これは、`For` ループを含む最も内側の `While` ループの次の反復です。</span><span class="sxs-lookup"><span data-stu-id="6704c-118">It transfers to the `While col < lastcol` statement, which is the next iteration of the innermost `While` loop that contains the `For` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="6704c-119">参照</span><span class="sxs-lookup"><span data-stu-id="6704c-119">See also</span></span>

- [<span data-ttu-id="6704c-120">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="6704c-120">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="6704c-121">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="6704c-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="6704c-122">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="6704c-122">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="6704c-123">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="6704c-123">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
