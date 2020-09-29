---
title: GoTo ステートメント
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
ms.openlocfilehash: 000f6754575bcce6b2d79d85541e755219aca956
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866625"
---
# <a name="goto-statement"></a><span data-ttu-id="bce59-102">GoTo ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-102">GoTo Statement</span></span>

<span data-ttu-id="bce59-103">プロシージャ内の指定した行に無条件に分岐します。</span><span class="sxs-lookup"><span data-stu-id="bce59-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce59-104">構文</span><span class="sxs-lookup"><span data-stu-id="bce59-104">Syntax</span></span>  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="bce59-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="bce59-105">Part</span></span>  

 `line`  
 <span data-ttu-id="bce59-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="bce59-106">Required.</span></span> <span data-ttu-id="bce59-107">任意の行ラベル。</span><span class="sxs-lookup"><span data-stu-id="bce59-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bce59-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="bce59-108">Remarks</span></span>  

 <span data-ttu-id="bce59-109">`GoTo` ステートメントでは、それが存在するプロシージャ内の行にのみ分岐できます。</span><span class="sxs-lookup"><span data-stu-id="bce59-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="bce59-110">行には、`GoTo` で参照できる行ラベルが必要です。</span><span class="sxs-lookup"><span data-stu-id="bce59-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="bce59-111">詳細については、「[方法:ステートメントへのラベル付け](../../programming-guide/program-structure/how-to-label-statements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce59-111">For more information, see [How to: Label Statements](../../programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bce59-112">`GoTo` ステートメントによって、コードの読み取りと保守が困難になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bce59-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="bce59-113">可能な限り、代わりに制御構造を使用してください。</span><span class="sxs-lookup"><span data-stu-id="bce59-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="bce59-114">詳細については、「 [Control Flow](../../programming-guide/language-features/control-flow/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce59-114">For more information, see [Control Flow](../../programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="bce59-115">`GoTo` ステートメントを使用して、`For`...`Next`、`For Each`...`Next`、`SyncLock`...`End SyncLock`、`Try`...`Catch`...`Finally`、`With`...`End With`、または `Using`...`End Using` コンストラクションの外部から、内部のラベルに分岐することはできません。</span><span class="sxs-lookup"><span data-stu-id="bce59-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="bce59-116">分岐と Try コンストラクション</span><span class="sxs-lookup"><span data-stu-id="bce59-116">Branching and Try Constructions</span></span>  

 <span data-ttu-id="bce59-117">`Try`...`Catch``Finally` コンストラクション内では、`GoTo` ステートメントによる分岐に、次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="bce59-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="bce59-118">ブロックまたは領域</span><span class="sxs-lookup"><span data-stu-id="bce59-118">Block or region</span></span>|<span data-ttu-id="bce59-119">外部からの分岐</span><span class="sxs-lookup"><span data-stu-id="bce59-119">Branching in from outside</span></span>|<span data-ttu-id="bce59-120">内部からの分岐</span><span class="sxs-lookup"><span data-stu-id="bce59-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="bce59-121">`Try` ブロック</span><span class="sxs-lookup"><span data-stu-id="bce59-121">`Try` block</span></span>|<span data-ttu-id="bce59-122">同じコンストラクションの `Catch` ブロックからのみ <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bce59-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="bce59-123">コンストラクション全体の外部へのみ</span><span class="sxs-lookup"><span data-stu-id="bce59-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="bce59-124">`Catch` ブロック</span><span class="sxs-lookup"><span data-stu-id="bce59-124">`Catch` block</span></span>|<span data-ttu-id="bce59-125">許可されない</span><span class="sxs-lookup"><span data-stu-id="bce59-125">Never allowed</span></span>|<span data-ttu-id="bce59-126">コンストラクション全体の外部、または同じコンストラクションの `Try` ブロックへのみ <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bce59-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="bce59-127">`Finally` ブロック</span><span class="sxs-lookup"><span data-stu-id="bce59-127">`Finally` block</span></span>|<span data-ttu-id="bce59-128">許可されない</span><span class="sxs-lookup"><span data-stu-id="bce59-128">Never allowed</span></span>|<span data-ttu-id="bce59-129">許可されない</span><span class="sxs-lookup"><span data-stu-id="bce59-129">Never allowed</span></span>|  
  
 <span data-ttu-id="bce59-130"><sup>1</sup> 1 つの `Try`...`Catch`...`Finally` コンストラクションが別のコンストラクション内に入れ子になっている場合、`Catch` ブロックは自身の入れ子レベルにある `Try` ブロックに分岐できますが、他の `Try` ブロックには分岐できません。</span><span class="sxs-lookup"><span data-stu-id="bce59-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="bce59-131">入れ子になった `Try`...`Catch`...`Finally` コンストラクションは、それが中で入れ子になっているコンストラクションの `Try` または `Catch` ブロックに完全に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bce59-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="bce59-132">次の図は、別のコンストラクション内に入れ子になっている `Try` コンストラクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="bce59-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="bce59-133">2 つのコンストラクションのブロック間のさまざまな分岐は、有効または無効として示されます。</span><span class="sxs-lookup"><span data-stu-id="bce59-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 ![Try 構造内の分岐のグラフィック ダイアグラム](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a><span data-ttu-id="bce59-135">例</span><span class="sxs-lookup"><span data-stu-id="bce59-135">Example</span></span>  

 <span data-ttu-id="bce59-136">次の例では、`GoTo` ステートメントを使用して、プロシージャ内の行ラベルに分岐します。</span><span class="sxs-lookup"><span data-stu-id="bce59-136">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="bce59-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="bce59-137">See also</span></span>

- [<span data-ttu-id="bce59-138">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-138">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="bce59-139">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-139">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="bce59-140">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-140">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="bce59-141">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-141">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="bce59-142">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-142">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="bce59-143">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-143">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="bce59-144">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-144">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="bce59-145">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="bce59-145">With...End With Statement</span></span>](with-end-with-statement.md)
