---
title: その他の制御構造
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 758df361f421684655147ae288af3f350e53c4d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348131"
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="b31ce-102">その他の制御構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b31ce-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="b31ce-103">Visual Basic には、リソースを破棄したり、オブジェクト参照を繰り返す回数を減らしたりするのに役立つ制御構造が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b31ce-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="b31ce-104">Using...End Using の構築</span><span class="sxs-lookup"><span data-stu-id="b31ce-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="b31ce-105">`Using...End Using` の構築では、SQL 接続などのリソースを使用するステートメントブロックを確立します。</span><span class="sxs-lookup"><span data-stu-id="b31ce-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="b31ce-106">必要に応じて、`Using` ステートメントを使用してリソースを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="b31ce-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="b31ce-107">`Using` ブロックを終了すると Visual Basic、他のコードが使用できるようにリソースが自動的に破棄されます。</span><span class="sxs-lookup"><span data-stu-id="b31ce-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="b31ce-108">リソースはローカルおよび破棄可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b31ce-108">The resource must be local and disposable.</span></span> <span data-ttu-id="b31ce-109">詳細については、「[Using ステートメント](../../../../visual-basic/language-reference/statements/using-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b31ce-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="b31ce-110">With...End With の構築</span><span class="sxs-lookup"><span data-stu-id="b31ce-110">With...End With Construction</span></span>  
 <span data-ttu-id="b31ce-111">`With...End With` の構築では、オブジェクト参照を一度指定した後、そのメンバーにアクセスする一連のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b31ce-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="b31ce-112">これにより、コードを簡略化し、パフォーマンスを向上させることができます。これは、Visual Basic にアクセスする各ステートメントの参照を再確立する必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="b31ce-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="b31ce-113">詳細については、「」を参照してください。 [End With ステートメント](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b31ce-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31ce-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b31ce-114">See also</span></span>

- [<span data-ttu-id="b31ce-115">制御フロー</span><span class="sxs-lookup"><span data-stu-id="b31ce-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="b31ce-116">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="b31ce-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="b31ce-117">ループ構造</span><span class="sxs-lookup"><span data-stu-id="b31ce-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="b31ce-118">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="b31ce-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="b31ce-119">Using ステートメント</span><span class="sxs-lookup"><span data-stu-id="b31ce-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
- [<span data-ttu-id="b31ce-120">With...End With ステートメント</span><span class="sxs-lookup"><span data-stu-id="b31ce-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
