---
title: IsFalse 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349529"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="09e77-102">IsFalse 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09e77-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="09e77-103">式が `False`かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="09e77-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="09e77-104">コード内で `IsFalse` を明示的に呼び出すことはできませんが、Visual Basic コンパイラはそれを使用して `AndAlso` 句からコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="09e77-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="09e77-105">クラスまたは構造体を定義し、その型の変数を `AndAlso` 句で使用する場合は、そのクラスまたは構造体で `IsFalse` を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09e77-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="09e77-106">コンパイラは、`IsFalse` と `IsTrue` 演算子を一致する*ペア*と見なします。</span><span class="sxs-lookup"><span data-stu-id="09e77-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="09e77-107">これは、そのいずれかを定義する場合は、もう一方も定義する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="09e77-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09e77-108">`IsFalse` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="09e77-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="09e77-109">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="09e77-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="09e77-110">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09e77-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="09e77-111">例</span><span class="sxs-lookup"><span data-stu-id="09e77-111">Example</span></span>  
 <span data-ttu-id="09e77-112">次のコード例では、`IsFalse` 演算子と `IsTrue` 演算子の定義を含む構造体のアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="09e77-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="09e77-113">参照</span><span class="sxs-lookup"><span data-stu-id="09e77-113">See also</span></span>

- [<span data-ttu-id="09e77-114">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="09e77-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="09e77-115">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="09e77-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="09e77-116">AndAlso 演算子</span><span class="sxs-lookup"><span data-stu-id="09e77-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
