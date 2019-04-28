---
title: その他の制御構造 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: c42070ce2ea866e59e1b2e190f7c05e1ee7cc922
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907843"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="75ea6-102">その他の制御構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75ea6-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="75ea6-103">Visual Basic では、リソースを破棄またはオブジェクト参照を繰り返すことが必要とする回数を削減するのに役立つ制御構造を提供します。</span><span class="sxs-lookup"><span data-stu-id="75ea6-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="75ea6-104">Using...End Using の構築</span><span class="sxs-lookup"><span data-stu-id="75ea6-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="75ea6-105">`Using...End Using`構築の確立を行うステートメント ブロックの SQL 接続などのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="75ea6-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="75ea6-106">リソースを取得することができます必要に応じて、`Using`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="75ea6-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="75ea6-107">終了すると、`Using`を使用するには、他のコードで使用できるように、このブロックでは、Visual Basic は、自動的にリソースの破棄します。</span><span class="sxs-lookup"><span data-stu-id="75ea6-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="75ea6-108">ローカルで破棄可能なリソースである必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ea6-108">The resource must be local and disposable.</span></span> <span data-ttu-id="75ea6-109">詳細については、[Using ステートメント](../../../../visual-basic/language-reference/statements/using-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75ea6-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="75ea6-110">With...End With の構築</span><span class="sxs-lookup"><span data-stu-id="75ea6-110">With...End With Construction</span></span>  
 <span data-ttu-id="75ea6-111">`With...End With`構築では、オブジェクト参照を 1 回指定することができ、一連のメンバーにアクセスするステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="75ea6-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="75ea6-112">これは、コードを簡略化、Visual Basic がそれにアクセスする各ステートメントの参照を再確立があるないために、パフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="75ea6-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="75ea6-113">詳細については、[With...End With ステートメント](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75ea6-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ea6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="75ea6-114">See also</span></span>

- [<span data-ttu-id="75ea6-115">制御フロー</span><span class="sxs-lookup"><span data-stu-id="75ea6-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="75ea6-116">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="75ea6-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="75ea6-117">ループ構造</span><span class="sxs-lookup"><span data-stu-id="75ea6-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="75ea6-118">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="75ea6-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="75ea6-119">Using ステートメント</span><span class="sxs-lookup"><span data-stu-id="75ea6-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="75ea6-120">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="75ea6-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
