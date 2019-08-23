---
title: IsTrue 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 1152f4b512a85ae183f8fc8d476b69685e2926ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966920"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="eb779-102">IsTrue 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb779-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="eb779-103">式がで`True`あるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="eb779-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="eb779-104">コード内で`IsTrue`を明示的に呼び出すことはできませんが、Visual Basic コンパイラはそれ`OrElse`を使用して句からコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="eb779-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="eb779-105">クラスまたは構造体を定義し、その型の変数を`OrElse`句で使用する場合は、そのクラスまたは構造体でを定義`IsTrue`する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb779-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="eb779-106">コンパイラは、演算子`IsTrue`と`IsFalse`演算子を*一致するペア*と見なします。</span><span class="sxs-lookup"><span data-stu-id="eb779-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="eb779-107">これは、そのいずれかを定義する場合は、もう一方も定義する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="eb779-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="eb779-108">IsTrue のコンパイラの使用</span><span class="sxs-lookup"><span data-stu-id="eb779-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="eb779-109">クラスまたは構造体を定義した場合は`For` `Else If`、 `If`、、、または`While`の各ステートメント`When`で、その型の変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb779-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="eb779-110">これを行う場合、コンパイラは、条件をテストできるように型を`Boolean`値に変換する演算子を必要とします。</span><span class="sxs-lookup"><span data-stu-id="eb779-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="eb779-111">適切な演算子を次の順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="eb779-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="eb779-112">クラスまたは構造体からへ`Boolean`の拡大変換演算子。</span><span class="sxs-lookup"><span data-stu-id="eb779-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="eb779-113">クラスまたは構造体からへ`Boolean?`の拡大変換演算子。</span><span class="sxs-lookup"><span data-stu-id="eb779-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="eb779-114">クラスまたは構造体の演算子。`IsTrue`</span><span class="sxs-lookup"><span data-stu-id="eb779-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="eb779-115">からへの`Boolean`変換`Boolean?`を行わないへの縮小変換。 `Boolean?`</span><span class="sxs-lookup"><span data-stu-id="eb779-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="eb779-116">クラスまたは構造体からへ`Boolean`の縮小変換演算子。</span><span class="sxs-lookup"><span data-stu-id="eb779-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="eb779-117">または`Boolean`演算子への変換を定義していない場合、コンパイラはエラーを通知します。 `IsTrue`</span><span class="sxs-lookup"><span data-stu-id="eb779-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb779-118">演算子はオーバーロードできます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。 `IsTrue`</span><span class="sxs-lookup"><span data-stu-id="eb779-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="eb779-119">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eb779-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="eb779-120">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb779-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb779-121">例</span><span class="sxs-lookup"><span data-stu-id="eb779-121">Example</span></span>  
 <span data-ttu-id="eb779-122">次のコード例では、演算子`IsFalse`と`IsTrue`演算子の定義を含む構造体のアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="eb779-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="eb779-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb779-123">See also</span></span>

- [<span data-ttu-id="eb779-124">IsFalse 演算子</span><span class="sxs-lookup"><span data-stu-id="eb779-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="eb779-125">方法: 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="eb779-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="eb779-126">OrElse 演算子</span><span class="sxs-lookup"><span data-stu-id="eb779-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
