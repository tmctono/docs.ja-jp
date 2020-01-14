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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352552"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="0e07b-102">再帰プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e07b-102">Recursive Procedures (Visual Basic)</span></span>

<span data-ttu-id="0e07b-103">*再帰*プロシージャは、それ自体を呼び出すものです。</span><span class="sxs-lookup"><span data-stu-id="0e07b-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="0e07b-104">一般に、これは Visual Basic コードを記述するための最も効果的な方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="0e07b-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="0e07b-105">次の手順では、再帰を使用して、元の引数の階乗を計算します。</span><span class="sxs-lookup"><span data-stu-id="0e07b-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="0e07b-106">再帰プロシージャに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="0e07b-106">Considerations with Recursive Procedures</span></span>

 <span data-ttu-id="0e07b-107">\*\*条件の制限。</span><span class="sxs-lookup"><span data-stu-id="0e07b-107">**Limiting Conditions**.</span></span> <span data-ttu-id="0e07b-108">再帰プロシージャは、再帰を終了できる条件が少なくとも1つ必要であることをテストするように設計する必要があります。また、適切な数の再帰呼び出しで条件が満たされない場合にも処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="0e07b-109">失敗せずに 1 つ以上の条件を満たすことができない場合、プロシージャは無限ループで実行されるリスクが高くなります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>

 <span data-ttu-id="0e07b-110">\*\*メモリ使用状況。</span><span class="sxs-lookup"><span data-stu-id="0e07b-110">**Memory Usage**.</span></span> <span data-ttu-id="0e07b-111">\*\* アプリケーションのローカル変数には、限られた量の領域があります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="0e07b-112">プロシージャがそれ自体を呼び出すたびに、そのローカル変数のコピーを追加するために、その領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e07b-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="0e07b-113">この処理が無期限に続行されると、最終的に <xref:System.StackOverflowException> エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="0e07b-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>

 <span data-ttu-id="0e07b-114">\*\*効率。</span><span class="sxs-lookup"><span data-stu-id="0e07b-114">**Efficiency**.</span></span> <span data-ttu-id="0e07b-115">\*\* ほとんどの場合、再帰のためにループを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="0e07b-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="0e07b-116">ループには、引数を渡したり、追加のストレージを初期化したり、値を返したりするオーバーヘッドがありません。</span><span class="sxs-lookup"><span data-stu-id="0e07b-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="0e07b-117">再帰呼び出しを行わないと、パフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="0e07b-117">Your performance can be much better without recursive calls.</span></span>

 <span data-ttu-id="0e07b-118">**相互再帰**。</span><span class="sxs-lookup"><span data-stu-id="0e07b-118">**Mutual Recursion**.</span></span> <span data-ttu-id="0e07b-119">2つのプロシージャが互いに呼び出す場合、パフォーマンスが低下したり、無限ループが発生したりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="0e07b-120">このような設計では、単一の再帰プロシージャと同じ問題が発生しますが、検出とデバッグが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>

 <span data-ttu-id="0e07b-121">\*\*かっこを使った呼び出し。</span><span class="sxs-lookup"><span data-stu-id="0e07b-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="0e07b-122">\ \**   `Function` プロシージャがそれ自体を再帰的に呼び出す場合は、引数リストがない場合でも、プロシージャ名の後にかっこを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="0e07b-123">それ以外の場合、関数名は関数の戻り値を表すものとして取得されます。</span><span class="sxs-lookup"><span data-stu-id="0e07b-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>

 <span data-ttu-id="0e07b-124">\*\*テスト。</span><span class="sxs-lookup"><span data-stu-id="0e07b-124">**Testing**.</span></span> <span data-ttu-id="0e07b-125">\*\* 再帰プロシージャを記述する場合は、常に一定の制限条件を満たしていることを確認するために、慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="0e07b-126">また、再帰呼び出しが多すぎるため、メモリが不足することがないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e07b-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e07b-127">参照</span><span class="sxs-lookup"><span data-stu-id="0e07b-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="0e07b-128">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="0e07b-128">Procedures</span></span>](index.md)
- [<span data-ttu-id="0e07b-129">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0e07b-129">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="0e07b-130">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0e07b-130">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="0e07b-131">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0e07b-131">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="0e07b-132">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="0e07b-132">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="0e07b-133">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="0e07b-133">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0e07b-134">プロシージャのオーバーロード</span><span class="sxs-lookup"><span data-stu-id="0e07b-134">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="0e07b-135">プロシージャのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0e07b-135">Troubleshooting Procedures</span></span>](troubleshooting-procedures.md)
- [<span data-ttu-id="0e07b-136">ループ構造</span><span class="sxs-lookup"><span data-stu-id="0e07b-136">Loop Structures</span></span>](../control-flow/loop-structures.md)
