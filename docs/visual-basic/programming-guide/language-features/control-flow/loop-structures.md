---
title: ループ構造 (Visual Basic)
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
ms.openlocfilehash: 56165eecce5e73c4e06235dac1691774fb39b794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906863"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="29dc9-102">ループ構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29dc9-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="29dc9-103">Visual Basic のループ構造を使用して、1 つまたは複数の行のコードを繰り返し実行できます。</span><span class="sxs-lookup"><span data-stu-id="29dc9-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="29dc9-104">条件になるまで、ループ構造でステートメントを繰り返すことができます`True`条件になるまで、`False`コレクションの回数、または 1 回の各要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="29dc9-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="29dc9-105">次の図は、条件が true になるまでは、一連のステートメントを実行するループ構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="29dc9-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![フローを示すグラフが、操作を行います.Until ループします。](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="29dc9-107">While ループ</span><span class="sxs-lookup"><span data-stu-id="29dc9-107">While Loops</span></span>  
 <span data-ttu-id="29dc9-108">`While`.`End While`構築で指定された条件と一連のステートメントが実行される、`While`ステートメントが`True`します。</span><span class="sxs-lookup"><span data-stu-id="29dc9-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="29dc9-109">詳細については、[While ... End While ステートメント](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29dc9-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="29dc9-110">Do ループ</span><span class="sxs-lookup"><span data-stu-id="29dc9-110">Do Loops</span></span>  
 <span data-ttu-id="29dc9-111">`Do`.`Loop`構築では、先頭またはループ構造の末尾のいずれかの条件をテストできます。</span><span class="sxs-lookup"><span data-stu-id="29dc9-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="29dc9-112">条件がループ処理を実行するかどうかを指定することもできます`True`になるまで`True`します。</span><span class="sxs-lookup"><span data-stu-id="29dc9-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="29dc9-113">詳細については、[Do ... Loopステートメント](../../../../visual-basic/language-reference/statements/do-loop-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29dc9-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="29dc9-114">For ループ</span><span class="sxs-lookup"><span data-stu-id="29dc9-114">For Loops</span></span>  
 <span data-ttu-id="29dc9-115">`For`しています.`Next`構築は、指定された回数だけループを実行します。</span><span class="sxs-lookup"><span data-stu-id="29dc9-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="29dc9-116">呼ばれる、ループ コントロール変数を使用して、*カウンター*繰り返しを追跡します。</span><span class="sxs-lookup"><span data-stu-id="29dc9-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="29dc9-117">開始日と終了このカウンターの値を指定して、必要に応じて量で増加している 1 つの繰り返しから、次を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="29dc9-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="29dc9-118">詳細については、[For Each ... Nextステートメント](../../../../visual-basic/language-reference/statements/for-next-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29dc9-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="29dc9-119">For Each ループ</span><span class="sxs-lookup"><span data-stu-id="29dc9-119">For Each Loops</span></span>  
 <span data-ttu-id="29dc9-120">`For Each`.`Next`構築は、コレクション内の各要素に対して 1 回のステートメントのセットを実行します。</span><span class="sxs-lookup"><span data-stu-id="29dc9-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="29dc9-121">ループ コントロール変数を指定するが、開始または終了値を決定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29dc9-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="29dc9-122">詳細については、次を参照してください[ごとにしています...次のステートメントの](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="29dc9-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29dc9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="29dc9-123">See also</span></span>

- [<span data-ttu-id="29dc9-124">制御フロー</span><span class="sxs-lookup"><span data-stu-id="29dc9-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="29dc9-125">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="29dc9-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="29dc9-126">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="29dc9-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="29dc9-127">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="29dc9-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
