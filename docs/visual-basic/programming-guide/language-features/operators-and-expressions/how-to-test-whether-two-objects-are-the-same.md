---
title: '方法: 2 つのオブジェクトが等しいかどうかをテストする'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: b215225dbc2d8c0d2bdfe2206e5d4a4f1faa6d0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403422"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="10e03-102">方法: 2 つのオブジェクトが等しいかどうかをテストする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10e03-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="10e03-103">オブジェクトを参照する 2 つの変数がある場合、`Is` または `IsNot` 演算子のいずれか、または両方を使用して、それらが同じインスタンスを参照するかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="10e03-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="10e03-104">2 つのオブジェクトが等しいかどうかをテストするには</span><span class="sxs-lookup"><span data-stu-id="10e03-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="10e03-105">2 つの変数をオペランドとして、[Is Operator](../../../language-reference/operators/is-operator.md) または [IsNot Operator](../../../language-reference/operators/isnot-operator.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="10e03-105">Use the [Is Operator](../../../language-reference/operators/is-operator.md) or the [IsNot Operator](../../../language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="10e03-106">2 つのオブジェクトが同じインスタンスを参照しているかどうかによって、特定のアクションを実行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="10e03-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="10e03-107">前の例では、コントロール `c` をフォーム `f` のアクティブなコントロールと比較しています。</span><span class="sxs-lookup"><span data-stu-id="10e03-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="10e03-108">アクティブなコントロールがない場合、またはアクティブなコントロールはあるが `c` と同じコントロール インスタンスではない場合、`If` ステートメントは失敗し、プロシージャでは以降の処理を行わずに戻ります。</span><span class="sxs-lookup"><span data-stu-id="10e03-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="10e03-109">`Is` と `IsNot` のどちらを使用するかは、お客様の利便性の問題です。</span><span class="sxs-lookup"><span data-stu-id="10e03-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="10e03-110">指定された式について、読みやすいと思われる方とそうではない方がいるでしょう。</span><span class="sxs-lookup"><span data-stu-id="10e03-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e03-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="10e03-111">See also</span></span>

- [<span data-ttu-id="10e03-112">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="10e03-112">Comparison Operators in Visual Basic</span></span>](comparison-operators.md)
