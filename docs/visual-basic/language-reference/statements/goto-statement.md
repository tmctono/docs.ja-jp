---
title: GoTo ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 3034c84684e94dfe8c334107a16df8cbd227c4d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912450"
---
# <a name="goto-statement"></a><span data-ttu-id="c3504-102">GoTo ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-102">GoTo Statement</span></span>
<span data-ttu-id="c3504-103">プロシージャ内の指定された行に無条件に分岐します。</span><span class="sxs-lookup"><span data-stu-id="c3504-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3504-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3504-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="c3504-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="c3504-105">Part</span></span>  
 `line`  
 <span data-ttu-id="c3504-106">必須。</span><span class="sxs-lookup"><span data-stu-id="c3504-106">Required.</span></span> <span data-ttu-id="c3504-107">任意の行ラベル。</span><span class="sxs-lookup"><span data-stu-id="c3504-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3504-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3504-108">Remarks</span></span>  
 <span data-ttu-id="c3504-109">ステートメント`GoTo`は、そのステートメントが出現するプロシージャ内の行にのみ分岐できます。</span><span class="sxs-lookup"><span data-stu-id="c3504-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="c3504-110">線には、を参照`GoTo`できる行ラベルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3504-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="c3504-111">詳細については、「[方法 :ラベルステートメント](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3504-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3504-112">`GoTo`ステートメントを使用すると、コードの読み取りと保守が困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c3504-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="c3504-113">可能な限り、代わりに制御構造を使用してください。</span><span class="sxs-lookup"><span data-stu-id="c3504-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="c3504-114">詳細については、「[制御フロー](../../../visual-basic/programming-guide/language-features/control-flow/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3504-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="c3504-115">`GoTo` の`For`外部から分岐するためにステートメントを使用することはできません。`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...、、 `Using`または... `End With``End Using`内のラベルに構築します。</span><span class="sxs-lookup"><span data-stu-id="c3504-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="c3504-116">分岐と Try の構造</span><span class="sxs-lookup"><span data-stu-id="c3504-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="c3504-117">`Try`内部`Catch`...構築では、 `GoTo`ステートメントを使用した分岐に次の規則が適用されます。 `Finally`</span><span class="sxs-lookup"><span data-stu-id="c3504-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="c3504-118">ブロックまたはリージョン</span><span class="sxs-lookup"><span data-stu-id="c3504-118">Block or region</span></span>|<span data-ttu-id="c3504-119">外部からの分岐</span><span class="sxs-lookup"><span data-stu-id="c3504-119">Branching in from outside</span></span>|<span data-ttu-id="c3504-120">内部からの分岐</span><span class="sxs-lookup"><span data-stu-id="c3504-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="c3504-121">`Try`帯</span><span class="sxs-lookup"><span data-stu-id="c3504-121">`Try` block</span></span>|<span data-ttu-id="c3504-122">同じ構築の`Catch`ブロックからのみ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c3504-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="c3504-123">構築全体の外側にのみ</span><span class="sxs-lookup"><span data-stu-id="c3504-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="c3504-124">`Catch`帯</span><span class="sxs-lookup"><span data-stu-id="c3504-124">`Catch` block</span></span>|<span data-ttu-id="c3504-125">許可しない</span><span class="sxs-lookup"><span data-stu-id="c3504-125">Never allowed</span></span>|<span data-ttu-id="c3504-126">構築全体の外側、または同じ構造体`Try`のブロックに対して<sup></sup>のみ</span><span class="sxs-lookup"><span data-stu-id="c3504-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="c3504-127">`Finally`帯</span><span class="sxs-lookup"><span data-stu-id="c3504-127">`Finally` block</span></span>|<span data-ttu-id="c3504-128">許可しない</span><span class="sxs-lookup"><span data-stu-id="c3504-128">Never allowed</span></span>|<span data-ttu-id="c3504-129">許可しない</span><span class="sxs-lookup"><span data-stu-id="c3504-129">Never allowed</span></span>|  
  
 <span data-ttu-id="c3504-130"><sup>1</sup> (存在`Try`する場合)`Catch`...構築は別の構造体に`Catch`入れ子になってい`Try`ます。ブロックは独自の入れ子レベルでブロックに分岐`Try`できますが、他のブロックには分岐できません。 `Finally`</span><span class="sxs-lookup"><span data-stu-id="c3504-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="c3504-131">入れ子に`Try`なった...`Catch`...構築は、入れ子になって`Try`いる`Catch`構造体のまたはブロック内に完全に含まれている必要があります。 `Finally`</span><span class="sxs-lookup"><span data-stu-id="c3504-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="c3504-132">次の図は、 `Try`別の構造に入れ子になった1つの構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="c3504-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="c3504-133">2つの構造のブロック間のさまざまな分岐は、有効または無効として示されます。</span><span class="sxs-lookup"><span data-stu-id="c3504-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Try 構造内の分岐のグラフィック ダイアグラム](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="c3504-135">例</span><span class="sxs-lookup"><span data-stu-id="c3504-135">Example</span></span>  
 <span data-ttu-id="c3504-136">次の例では`GoTo` 、ステートメントを使用して、プロシージャ内の行ラベルに分岐します。</span><span class="sxs-lookup"><span data-stu-id="c3504-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="c3504-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3504-137">See also</span></span>

- [<span data-ttu-id="c3504-138">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="c3504-139">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="c3504-140">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="c3504-141">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="c3504-142">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="c3504-143">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="c3504-144">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="c3504-145">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="c3504-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
