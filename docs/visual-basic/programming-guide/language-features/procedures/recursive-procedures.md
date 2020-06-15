---
title: 再帰プロシージャ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: 646d4e29ed7a0b6367d4b35a7f8641bcf659e616
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352552"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="244d1-102">再帰プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="244d1-102">Recursive Procedures (Visual Basic)</span></span>

<span data-ttu-id="244d1-103">"*再帰*" プロシージャとは、自身を呼び出すプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="244d1-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="244d1-104">一般に、これは Visual Basic コードを記述する最も効果的な方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="244d1-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="244d1-105">次のプロシージャでは、再帰を使用して元の引数の階乗を計算します。</span><span class="sxs-lookup"><span data-stu-id="244d1-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="244d1-106">再帰プロシージャに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="244d1-106">Considerations with Recursive Procedures</span></span>

 <span data-ttu-id="244d1-107">**制限条件**。</span><span class="sxs-lookup"><span data-stu-id="244d1-107">**Limiting Conditions**.</span></span> <span data-ttu-id="244d1-108">再帰を終了できる条件を少なくとも 1 つはテストするように、再帰プロシージャを設計する必要があります。また、妥当な回数の再帰呼び出しでそのような条件が満たされない場合の処理も必要となります。</span><span class="sxs-lookup"><span data-stu-id="244d1-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="244d1-109">必ず満たすことができる条件が少なくとも 1 つはないと、プロシージャが無限ループで実行されるリスクが高くなります。</span><span class="sxs-lookup"><span data-stu-id="244d1-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>

 <span data-ttu-id="244d1-110">**メモリ使用状況**。</span><span class="sxs-lookup"><span data-stu-id="244d1-110">**Memory Usage**.</span></span> <span data-ttu-id="244d1-111">アプリケーションがローカル変数に使用できる領域は限られています。</span><span class="sxs-lookup"><span data-stu-id="244d1-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="244d1-112">プロシージャが自身を呼び出すたびに、ローカル変数のコピーが追加され、その領域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="244d1-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="244d1-113">このプロセスが無期限に続行されると、最終的に <xref:System.StackOverflowException> エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="244d1-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>

 <span data-ttu-id="244d1-114">**効率**。</span><span class="sxs-lookup"><span data-stu-id="244d1-114">**Efficiency**.</span></span> <span data-ttu-id="244d1-115">ほとんどの場合、再帰の代わりにループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="244d1-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="244d1-116">ループには、引数を渡し、追加のストレージを初期化して、値を返すというオーバーヘッドはありません。</span><span class="sxs-lookup"><span data-stu-id="244d1-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="244d1-117">再帰呼び出しがない場合、パフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="244d1-117">Your performance can be much better without recursive calls.</span></span>

 <span data-ttu-id="244d1-118">**相互再帰**。</span><span class="sxs-lookup"><span data-stu-id="244d1-118">**Mutual Recursion**.</span></span> <span data-ttu-id="244d1-119">2 つのプロシージャが相互に呼び出し合うと、パフォーマンスが大幅に低下したり、無限ループが発生したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="244d1-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="244d1-120">このような設計では、単一の再帰プロシージャと同じ問題が発生しますが、検出とデバッグがより困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="244d1-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>

 <span data-ttu-id="244d1-121">**かっこを使用した呼び出し**。</span><span class="sxs-lookup"><span data-stu-id="244d1-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="244d1-122">`Function` プロシージャが自身を再帰的に呼び出すときには、引数リストがない場合でも、プロシージャ名の後にかっこを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="244d1-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="244d1-123">そうしないと、関数名が関数の戻り値を表していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="244d1-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>

 <span data-ttu-id="244d1-124">**テスト**。</span><span class="sxs-lookup"><span data-stu-id="244d1-124">**Testing**.</span></span> <span data-ttu-id="244d1-125">再帰プロシージャを作成した場合は、慎重にテストして、何らかの制限条件を常に満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="244d1-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="244d1-126">また、再帰呼び出しが多すぎるためにメモリ不足にならないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="244d1-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="244d1-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="244d1-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="244d1-128">手順</span><span class="sxs-lookup"><span data-stu-id="244d1-128">Procedures</span></span>](index.md)
- [<span data-ttu-id="244d1-129">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="244d1-129">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="244d1-130">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="244d1-130">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="244d1-131">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="244d1-131">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="244d1-132">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="244d1-132">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="244d1-133">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="244d1-133">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="244d1-134">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="244d1-134">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="244d1-135">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="244d1-135">Troubleshooting Procedures</span></span>](troubleshooting-procedures.md)
- [<span data-ttu-id="244d1-136">ループ構造</span><span class="sxs-lookup"><span data-stu-id="244d1-136">Loop Structures</span></span>](../control-flow/loop-structures.md)
