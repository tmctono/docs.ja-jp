---
title: 条件判断構造 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: f0df649c4be50e9cadd51258c89137b68b4ffe22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963199"
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="96c97-102">条件判断構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96c97-102">Decision Structures (Visual Basic)</span></span>
<span data-ttu-id="96c97-103">Visual Basic を使用すると、テストの結果に応じて、条件をテストしたり、さまざまな操作を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="96c97-103">Visual Basic lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="96c97-104">true または false の場合、さまざまな値の式、または一連のステートメントを実行するときに生成された例外のさまざまな条件をテストできます。</span><span class="sxs-lookup"><span data-stu-id="96c97-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="96c97-105">次の図は、条件が true であるかどうかをテストし、true であるか false であるかに応じて異なるアクションを実行するデシジョン構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="96c97-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 ![If...Then...Else 構築。](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="96c97-107">If...Then...Else 構造</span><span class="sxs-lookup"><span data-stu-id="96c97-107">If...Then...Else Construction</span></span>  
 <span data-ttu-id="96c97-108">`If...Then...Else`構造を使用すると、1つ以上の条件をテストし、各条件に応じて1つ以上のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="96c97-108">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="96c97-109">条件をテストし、次の方法でアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="96c97-109">You can test conditions and take actions in the following ways:</span></span>  
  
- <span data-ttu-id="96c97-110">条件がの場合に1つ以上のステートメントを実行する`True`</span><span class="sxs-lookup"><span data-stu-id="96c97-110">Run one or more statements if a condition is `True`</span></span>  
  
- <span data-ttu-id="96c97-111">条件がの場合に1つ以上のステートメントを実行する`False`</span><span class="sxs-lookup"><span data-stu-id="96c97-111">Run one or more statements if a condition is `False`</span></span>  
  
- <span data-ttu-id="96c97-112">条件が`True`の場合はステートメントを実行し、それ以外の場合は`False`</span><span class="sxs-lookup"><span data-stu-id="96c97-112">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
- <span data-ttu-id="96c97-113">前の条件がの場合に追加条件をテストする`False`</span><span class="sxs-lookup"><span data-stu-id="96c97-113">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="96c97-114">これらすべての可能性を提供する制御構造が、[If...Then...Else ステートメント](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)です。</span><span class="sxs-lookup"><span data-stu-id="96c97-114">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="96c97-115">1つのテストと1つのステートメントを実行するだけの場合は、単一行バージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96c97-115">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="96c97-116">より複雑な条件とアクションのセットがある場合は、複数行のバージョンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="96c97-116">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="96c97-117">Select...Case 構造</span><span class="sxs-lookup"><span data-stu-id="96c97-117">Select...Case Construction</span></span>  
 <span data-ttu-id="96c97-118">この`Select...Case`構築により、式を1回評価し、さまざまな値に基づいてさまざまなステートメントのセットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="96c97-118">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="96c97-119">詳細については、[Select...Case ステートメント](../../../../visual-basic/language-reference/statements/select-case-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c97-119">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="96c97-120">Try...Catch...Finally 構造</span><span class="sxs-lookup"><span data-stu-id="96c97-120">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="96c97-121">`Try...Catch...Finally`構造を使用すると、ステートメントのいずれかによって例外が発生した場合にコントロールを保持する環境で、一連のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="96c97-121">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="96c97-122">例外ごとに異なるアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="96c97-122">You can take different actions for different exceptions.</span></span> <span data-ttu-id="96c97-123">必要に応じて、実行するコードのブロックを指定して、 `Try...Catch...Finally`何が発生したかにかかわらず、構築全体を終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c97-123">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="96c97-124">詳細については、[Try...Catch...Finally ステートメント](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c97-124">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="96c97-125">多くの制御構造では、キーワードをクリックすると、構造内のすべてのキーワードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="96c97-125">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="96c97-126">たとえば、 `If...Then...Else`構築をクリック`If`すると、、 `Then` `ElseIf`、、 `Else`、および`If` `End If`のすべてのインスタンスが構築されます。</span><span class="sxs-lookup"><span data-stu-id="96c97-126">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="96c97-127">次または前の強調表示されたキーワードに移動するには、CTRL + SHIFT + ↓キーを押すか、CTRL + SHIFT + 上方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="96c97-127">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c97-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="96c97-128">See also</span></span>

- [<span data-ttu-id="96c97-129">制御フロー</span><span class="sxs-lookup"><span data-stu-id="96c97-129">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="96c97-130">ループ構造</span><span class="sxs-lookup"><span data-stu-id="96c97-130">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="96c97-131">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="96c97-131">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="96c97-132">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="96c97-132">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="96c97-133">If 演算子</span><span class="sxs-lookup"><span data-stu-id="96c97-133">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
