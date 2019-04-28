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
ms.openlocfilehash: c4dd249620ba1bf445642ce4600498f6beb30461
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637967"
---
# <a name="goto-statement"></a><span data-ttu-id="a325f-102">GoTo ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-102">GoTo Statement</span></span>
<span data-ttu-id="a325f-103">プロシージャ内の指定した行に無条件に分岐します。</span><span class="sxs-lookup"><span data-stu-id="a325f-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a325f-104">構文</span><span class="sxs-lookup"><span data-stu-id="a325f-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="a325f-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="a325f-105">Part</span></span>  
 `line`  
 <span data-ttu-id="a325f-106">必須。</span><span class="sxs-lookup"><span data-stu-id="a325f-106">Required.</span></span> <span data-ttu-id="a325f-107">任意の行のラベル。</span><span class="sxs-lookup"><span data-stu-id="a325f-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a325f-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="a325f-108">Remarks</span></span>  
 <span data-ttu-id="a325f-109">`GoTo`のみが表示されるプロシージャ内の行にステートメントを分岐できます。</span><span class="sxs-lookup"><span data-stu-id="a325f-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="a325f-110">ラベルを 1 行が必要`GoTo`を参照できます。</span><span class="sxs-lookup"><span data-stu-id="a325f-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="a325f-111">詳細については、「[方法 :ステートメントにラベル付け](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)します。</span><span class="sxs-lookup"><span data-stu-id="a325f-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a325f-112">`GoTo` ステートメントすると、コードが読み取りおよびメンテナンスを困難になります。</span><span class="sxs-lookup"><span data-stu-id="a325f-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="a325f-113">可能であれば、制御構造を使用します。</span><span class="sxs-lookup"><span data-stu-id="a325f-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="a325f-114">詳細については、次を参照してください。[制御フロー](../../../visual-basic/programming-guide/language-features/control-flow/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="a325f-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="a325f-115">使用することはできません、`GoTo`外からの分岐にステートメントを`For`.`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`、または`Using`.`End Using`内のラベルに構築します。</span><span class="sxs-lookup"><span data-stu-id="a325f-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="a325f-116">分岐と構築をお試しください</span><span class="sxs-lookup"><span data-stu-id="a325f-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="a325f-117">内で、 `Try`.`Catch`...`Finally`で分岐に、構築、次の規則の適用、`GoTo`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="a325f-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="a325f-118">ブロックまたは地域</span><span class="sxs-lookup"><span data-stu-id="a325f-118">Block or region</span></span>|<span data-ttu-id="a325f-119">外部からへの分岐</span><span class="sxs-lookup"><span data-stu-id="a325f-119">Branching in from outside</span></span>|<span data-ttu-id="a325f-120">外部への分岐からの内部</span><span class="sxs-lookup"><span data-stu-id="a325f-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="a325f-121">`Try` ブロック</span><span class="sxs-lookup"><span data-stu-id="a325f-121">`Try` block</span></span>|<span data-ttu-id="a325f-122">のみ、`Catch`同じ構築ブロック<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a325f-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="a325f-123">のみ、全体の構造の外部</span><span class="sxs-lookup"><span data-stu-id="a325f-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="a325f-124">`Catch` ブロック</span><span class="sxs-lookup"><span data-stu-id="a325f-124">`Catch` block</span></span>|<span data-ttu-id="a325f-125">許可しません。</span><span class="sxs-lookup"><span data-stu-id="a325f-125">Never allowed</span></span>|<span data-ttu-id="a325f-126">のみ、全体の構造の外部にまたは、`Try`同じ構築ブロック<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a325f-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="a325f-127">`Finally` ブロック</span><span class="sxs-lookup"><span data-stu-id="a325f-127">`Finally` block</span></span>|<span data-ttu-id="a325f-128">許可しません。</span><span class="sxs-lookup"><span data-stu-id="a325f-128">Never allowed</span></span>|<span data-ttu-id="a325f-129">許可しません。</span><span class="sxs-lookup"><span data-stu-id="a325f-129">Never allowed</span></span>|  
  
 <span data-ttu-id="a325f-130"><sup>1</sup>場合`Try`.`Catch`...`Finally`構築が、別の入れ子になった、`Catch`ブロックに分岐、`Try`ブロックの他にコピーせずに、独自の入れ子のレベルにある`Try`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="a325f-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="a325f-131">入れ子になった`Try`.`Catch`...`Finally`構築を完全に含める必要があります、`Try`または`Catch`ブロックを入れ子になってを作成します。</span><span class="sxs-lookup"><span data-stu-id="a325f-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="a325f-132">次の図では 1 つ`Try`別内で入れ子になった構築します。</span><span class="sxs-lookup"><span data-stu-id="a325f-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="a325f-133">2 つの構築ブロック間でさまざまな分岐は、有効または無効と表示されています。</span><span class="sxs-lookup"><span data-stu-id="a325f-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Try 構造内の分岐のグラフィック ダイアグラム](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="a325f-135">例</span><span class="sxs-lookup"><span data-stu-id="a325f-135">Example</span></span>  
 <span data-ttu-id="a325f-136">次の例では、`GoTo`ステートメントをプロシージャ内の行ラベルに分岐します。</span><span class="sxs-lookup"><span data-stu-id="a325f-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="a325f-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="a325f-137">See also</span></span>

- [<span data-ttu-id="a325f-138">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-138">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="a325f-139">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-139">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="a325f-140">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-140">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="a325f-141">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-141">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="a325f-142">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-142">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="a325f-143">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-143">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="a325f-144">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-144">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="a325f-145">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="a325f-145">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
