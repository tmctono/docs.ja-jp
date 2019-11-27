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
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343618"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="590ca-102">方法: 2 つのオブジェクトが等しいかどうかをテストする (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="590ca-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="590ca-103">オブジェクトを参照する変数が2つある場合は、`Is` または `IsNot` のいずれかの演算子、またはその両方を使用して、同じインスタンスを参照しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="590ca-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="590ca-104">2つのオブジェクトが同一かどうかをテストするには</span><span class="sxs-lookup"><span data-stu-id="590ca-104">To test whether two objects are the same</span></span>  
  
- <span data-ttu-id="590ca-105">2つの変数がオペランドとして使用されて[いる場合は、Is 演算子](../../../../visual-basic/language-reference/operators/is-operator.md)または[IsNot 演算子](../../../../visual-basic/language-reference/operators/isnot-operator.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="590ca-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 <span data-ttu-id="590ca-106">2つのオブジェクトが同じインスタンスを参照しているかどうかによって、特定のアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="590ca-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="590ca-107">前の例では、コントロールの `c` とフォーム `f`のアクティブコントロールとを比較しています。</span><span class="sxs-lookup"><span data-stu-id="590ca-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="590ca-108">アクティブなコントロールがない場合、または存在していても `c`と同じコントロールインスタンスではない場合、`If` ステートメントは失敗し、プロシージャはそれ以上の処理を行わずに戻ります。</span><span class="sxs-lookup"><span data-stu-id="590ca-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="590ca-109">`Is` と `IsNot` のどちらを使用する場合でも、個人的に便利です。</span><span class="sxs-lookup"><span data-stu-id="590ca-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="590ca-110">指定された式では、もう一方の方よりも読みやすくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="590ca-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="590ca-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="590ca-111">See also</span></span>

- [<span data-ttu-id="590ca-112">Visual Basic の比較演算子</span><span class="sxs-lookup"><span data-stu-id="590ca-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
