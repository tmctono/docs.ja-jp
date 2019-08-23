---
title: IsFalse 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 49b8493575685a220808df1522ce16835b3ce0ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917156"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="0e217-102">IsFalse 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e217-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="0e217-103">式がで`False`あるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0e217-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="0e217-104">コード内で`IsFalse`を明示的に呼び出すことはできませんが、Visual Basic コンパイラはそれ`AndAlso`を使用して句からコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="0e217-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="0e217-105">クラスまたは構造体を定義し、その型の変数を`AndAlso`句で使用する場合は、そのクラスまたは構造体でを定義`IsFalse`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e217-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="0e217-106">コンパイラは、演算子`IsFalse`と`IsTrue`演算子を*一致するペア*と見なします。</span><span class="sxs-lookup"><span data-stu-id="0e217-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="0e217-107">これは、そのいずれかを定義する場合は、もう一方も定義する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0e217-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e217-108">演算子はオーバーロードできます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。 `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="0e217-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="0e217-109">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0e217-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0e217-110">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e217-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e217-111">例</span><span class="sxs-lookup"><span data-stu-id="0e217-111">Example</span></span>  
 <span data-ttu-id="0e217-112">次のコード例では、演算子`IsFalse`と`IsTrue`演算子の定義を含む構造体のアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="0e217-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="0e217-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e217-113">See also</span></span>

- [<span data-ttu-id="0e217-114">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="0e217-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="0e217-115">方法: 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="0e217-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="0e217-116">AndAlso 演算子</span><span class="sxs-lookup"><span data-stu-id="0e217-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
