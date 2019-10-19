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
ms.openlocfilehash: 4b7a5cce56dfdd2bdc7e068aadbc18b92bba269d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581814"
---
# <a name="goto-statement"></a><span data-ttu-id="57786-102">GoTo ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-102">GoTo Statement</span></span>
<span data-ttu-id="57786-103">プロシージャ内の指定された行に無条件に分岐します。</span><span class="sxs-lookup"><span data-stu-id="57786-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57786-104">構文</span><span class="sxs-lookup"><span data-stu-id="57786-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="57786-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="57786-105">Part</span></span>  
 `line`  
 <span data-ttu-id="57786-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="57786-106">Required.</span></span> <span data-ttu-id="57786-107">任意の行ラベル。</span><span class="sxs-lookup"><span data-stu-id="57786-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57786-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="57786-108">Remarks</span></span>  
 <span data-ttu-id="57786-109">@No__t_0 ステートメントは、そのステートメントが出現するプロシージャ内の行にのみ分岐できます。</span><span class="sxs-lookup"><span data-stu-id="57786-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="57786-110">線には、`GoTo` が参照できる行ラベルが必要です。</span><span class="sxs-lookup"><span data-stu-id="57786-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="57786-111">詳細については、「 [How to: Label ステートメント](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57786-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57786-112">`GoTo` ステートメントを使用すると、コードの読み取りと保守が困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="57786-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="57786-113">可能な限り、代わりに制御構造を使用してください。</span><span class="sxs-lookup"><span data-stu-id="57786-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="57786-114">詳細については、「[制御フロー](../../../visual-basic/programming-guide/language-features/control-flow/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57786-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="57786-115">@No__t_0 ステートメントを使用して `For` の外部から分岐することはできません...`Next`、`For Each`...`Next`、`SyncLock`...`End SyncLock`、`Try`...`Catch`...`Finally`、0...1、または 2...内のラベルに構築 3 ます。</span><span class="sxs-lookup"><span data-stu-id="57786-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="57786-116">分岐と Try の構造</span><span class="sxs-lookup"><span data-stu-id="57786-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="57786-117">@No__t_0 内...`Catch`...`Finally` 構築では、次の規則が `GoTo` ステートメントを使用した分岐に適用されます。</span><span class="sxs-lookup"><span data-stu-id="57786-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="57786-118">ブロックまたはリージョン</span><span class="sxs-lookup"><span data-stu-id="57786-118">Block or region</span></span>|<span data-ttu-id="57786-119">外部からの分岐</span><span class="sxs-lookup"><span data-stu-id="57786-119">Branching in from outside</span></span>|<span data-ttu-id="57786-120">内部からの分岐</span><span class="sxs-lookup"><span data-stu-id="57786-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="57786-121">`Try` ブロック</span><span class="sxs-lookup"><span data-stu-id="57786-121">`Try` block</span></span>|<span data-ttu-id="57786-122">同じ構築の `Catch` ブロックからのみ<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="57786-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="57786-123">構築全体の外側にのみ</span><span class="sxs-lookup"><span data-stu-id="57786-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="57786-124">`Catch` ブロック</span><span class="sxs-lookup"><span data-stu-id="57786-124">`Catch` block</span></span>|<span data-ttu-id="57786-125">許可しない</span><span class="sxs-lookup"><span data-stu-id="57786-125">Never allowed</span></span>|<span data-ttu-id="57786-126">構築全体の外側、または<sup>同じ構造体</sup>の `Try` ブロックにのみ</span><span class="sxs-lookup"><span data-stu-id="57786-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="57786-127">`Finally` ブロック</span><span class="sxs-lookup"><span data-stu-id="57786-127">`Finally` block</span></span>|<span data-ttu-id="57786-128">許可しない</span><span class="sxs-lookup"><span data-stu-id="57786-128">Never allowed</span></span>|<span data-ttu-id="57786-129">許可しない</span><span class="sxs-lookup"><span data-stu-id="57786-129">Never allowed</span></span>|  
  
 <span data-ttu-id="57786-130">1 `Try` の場合は<sup>1</sup>`Catch`...`Finally` 構築は別の構造体に入れ子になっています。 `Catch` ブロックは、独自の入れ子レベルで `Try` ブロックに分岐できますが、他の `Try` ブロックには分岐できません。</span><span class="sxs-lookup"><span data-stu-id="57786-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="57786-131">入れ子になった `Try`...`Catch`...`Finally` の構築は、入れ子になっている構築の `Try` または `Catch` ブロックに完全に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="57786-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="57786-132">次の図は、別の `Try` 構築を入れ子にしたものを示しています。</span><span class="sxs-lookup"><span data-stu-id="57786-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="57786-133">2つの構造のブロック間のさまざまな分岐は、有効または無効として示されます。</span><span class="sxs-lookup"><span data-stu-id="57786-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Try 構造内の分岐のグラフィック ダイアグラム](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="57786-135">例</span><span class="sxs-lookup"><span data-stu-id="57786-135">Example</span></span>  
 <span data-ttu-id="57786-136">次の例では、`GoTo` ステートメントを使用して、プロシージャ内の行ラベルに分岐します。</span><span class="sxs-lookup"><span data-stu-id="57786-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="57786-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="57786-137">See also</span></span>

- [<span data-ttu-id="57786-138">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="57786-139">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="57786-140">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="57786-141">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="57786-142">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="57786-143">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="57786-144">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="57786-145">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="57786-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
