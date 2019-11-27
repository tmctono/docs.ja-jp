---
title: ループ構造
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 0a75205a7d52c332094d624d082e5db3e89447f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353915"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="0a0dd-102">ループ構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a0dd-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="0a0dd-103">Visual Basic ループ構造を使用すると、1行または複数行のコードを繰り返し実行できます。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="0a0dd-104">ステートメントは、条件が `True`されるか、条件が `False`、指定された回数、またはコレクション内の要素ごとに1回繰り返されるまで、ループ構造で繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="0a0dd-105">次の図は、条件が true になるまで一連のステートメントを実行するループ構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![実行を示すフローチャートUntil ループ。](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="0a0dd-107">While ループ</span><span class="sxs-lookup"><span data-stu-id="0a0dd-107">While Loops</span></span>  
 <span data-ttu-id="0a0dd-108">`While` ステートメントで指定された条件が `True`されている限り、`While`...`End While` の構築は、一連のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="0a0dd-109">詳細については、「 [While...」を参照してください。End While ステートメント](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="0a0dd-110">Do ループ</span><span class="sxs-lookup"><span data-stu-id="0a0dd-110">Do Loops</span></span>  
 <span data-ttu-id="0a0dd-111">`Do`...`Loop` の構築により、ループ構造の先頭または末尾で条件をテストできます。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="0a0dd-112">また、条件が `True` されている間、または `True`になるまでループを繰り返すかどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="0a0dd-113">詳細については、「 [Do...Loop ステートメント](../../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="0a0dd-114">For ループ</span><span class="sxs-lookup"><span data-stu-id="0a0dd-114">For Loops</span></span>  
 <span data-ttu-id="0a0dd-115">`For`...`Next` の構築によって、ループが設定された回数だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="0a0dd-116">ループコントロール変数 (*カウンター*とも呼ばれます) を使用して、繰り返しを追跡します。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="0a0dd-117">開始日と終了このカウンターの値を指定して、必要に応じて量で増加している 1 つの繰り返しから、次を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="0a0dd-118">詳細については、「」を参照して[ください。次のステートメント](../../../../visual-basic/language-reference/statements/for-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="0a0dd-119">For Each ループ</span><span class="sxs-lookup"><span data-stu-id="0a0dd-119">For Each Loops</span></span>  
 <span data-ttu-id="0a0dd-120">`For Each`...`Next` の構築では、コレクション内の各要素に対して一連のステートメントが1回実行されます。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="0a0dd-121">ループ コントロール変数を指定しますが、その開始または終了値を決定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="0a0dd-122">詳細については、[For Each...Next ステートメント](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a0dd-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0dd-123">参照</span><span class="sxs-lookup"><span data-stu-id="0a0dd-123">See also</span></span>

- [<span data-ttu-id="0a0dd-124">制御フロー</span><span class="sxs-lookup"><span data-stu-id="0a0dd-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="0a0dd-125">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="0a0dd-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="0a0dd-126">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="0a0dd-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="0a0dd-127">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="0a0dd-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
