---
title: IsFalse 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 9f25c406038486224c2c4708c86ef86889c44c15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013544"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="bdc02-102">IsFalse 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdc02-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="bdc02-103">式は、かどうかを判断します`False`します。</span><span class="sxs-lookup"><span data-stu-id="bdc02-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="bdc02-104">呼び出すことはできません`IsFalse`明示的に、コードが、Visual Basic のコンパイラが使用できることからコードを生成する`AndAlso`句。</span><span class="sxs-lookup"><span data-stu-id="bdc02-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="bdc02-105">クラスまたは構造体を定義しでその型の変数を使用している場合、`AndAlso`句が定義する必要があります`IsFalse`でそのクラスまたは構造体。</span><span class="sxs-lookup"><span data-stu-id="bdc02-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="bdc02-106">コンパイラは、`IsFalse`と`IsTrue`演算子として、*ペア*します。</span><span class="sxs-lookup"><span data-stu-id="bdc02-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="bdc02-107">つまり、それらのいずれかを定義する場合をする必要がありますも定義、もう 1 つ。</span><span class="sxs-lookup"><span data-stu-id="bdc02-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdc02-108">`IsFalse`演算子は、*オーバー ロードされた*、いるクラスまたは構造体を再定義できますの動作のオペランドがそのクラスまたは構造体の型を持つときにすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bdc02-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="bdc02-109">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="bdc02-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bdc02-110">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdc02-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdc02-111">例</span><span class="sxs-lookup"><span data-stu-id="bdc02-111">Example</span></span>  
 <span data-ttu-id="bdc02-112">次のコード例の定義を含む構造体のアウトラインを定義する、`IsFalse`と`IsTrue`演算子。</span><span class="sxs-lookup"><span data-stu-id="bdc02-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="bdc02-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdc02-113">See also</span></span>

- [<span data-ttu-id="bdc02-114">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="bdc02-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="bdc02-115">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="bdc02-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="bdc02-116">AndAlso 演算子</span><span class="sxs-lookup"><span data-stu-id="bdc02-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
