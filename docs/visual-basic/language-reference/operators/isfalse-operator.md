---
title: IsFalse 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: bbcdb9bcf645a4e9cb54c657ccd46e04437d207e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873381"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="fa8c5-102">IsFalse 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa8c5-102">IsFalse Operator (Visual Basic)</span></span>

<span data-ttu-id="fa8c5-103">式が `False` かどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="fa8c5-104">コード内で `IsFalse` を明示的に呼び出すことはできませんが、Visual Basic コンパイラはそれを使用して `AndAlso` 句からコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="fa8c5-105">クラスまたは構造体を定義し、その型の変数を `AndAlso` 句で使用する場合は、そのクラスまたは構造体で `IsFalse` を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="fa8c5-106">コンパイラは、`IsFalse` と `IsTrue` の演算子を "*対応するペア*" と見なします。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="fa8c5-107">つまり、そのいずれかを定義する場合は、もう一方も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa8c5-108">`IsFalse` 演算子は "*オーバーロード*" できます。つまり、オペランドがあるクラスまたは構造体の型を持っているときに、そのクラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="fa8c5-109">コードで、そのようなクラスまたは構造体に対してこの演算子が使用される場合は、再定義された動作を必ず理解してください。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fa8c5-110">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-110">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa8c5-111">例</span><span class="sxs-lookup"><span data-stu-id="fa8c5-111">Example</span></span>  

 <span data-ttu-id="fa8c5-112">次のコード例では、`IsFalse` および `IsTrue` 演算子の定義を含む構造体のアウトラインを定義しています。</span><span class="sxs-lookup"><span data-stu-id="fa8c5-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="fa8c5-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa8c5-113">See also</span></span>

- [<span data-ttu-id="fa8c5-114">IsTrue 演算子</span><span class="sxs-lookup"><span data-stu-id="fa8c5-114">IsTrue Operator</span></span>](istrue-operator.md)
- [<span data-ttu-id="fa8c5-115">方法: 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="fa8c5-115">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="fa8c5-116">AndAlso 演算子</span><span class="sxs-lookup"><span data-stu-id="fa8c5-116">AndAlso Operator</span></span>](andalso-operator.md)
