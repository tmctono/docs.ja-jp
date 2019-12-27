---
title: IsTrue 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349510"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="ccaa2-102">IsTrue 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccaa2-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="ccaa2-103">式が `True`かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="ccaa2-104">コード内で `IsTrue` を明示的に呼び出すことはできませんが、Visual Basic コンパイラはそれを使用して `OrElse` 句からコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="ccaa2-105">クラスまたは構造体を定義し、その型の変数を `OrElse` 句で使用する場合は、そのクラスまたは構造体で `IsTrue` を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="ccaa2-106">コンパイラは、`IsTrue` と `IsFalse` 演算子を一致する*ペア*と見なします。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="ccaa2-107">これは、そのいずれかを定義する場合は、もう一方も定義する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="ccaa2-108">IsTrue のコンパイラの使用</span><span class="sxs-lookup"><span data-stu-id="ccaa2-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="ccaa2-109">クラスまたは構造体を定義したら、その型の変数を `For`、`If`、`Else If`、または `While` ステートメントで使用することも、`When` 句で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="ccaa2-110">これを行う場合、コンパイラは、条件をテストできるように、型を `Boolean` 値に変換する演算子を必要とします。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="ccaa2-111">適切な演算子を次の順序で検索します。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="ccaa2-112">クラスまたは構造体から `Boolean`への拡大変換演算子。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="ccaa2-113">クラスまたは構造体から `Boolean?`への拡大変換演算子。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="ccaa2-114">クラスまたは構造体の `IsTrue` 演算子。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="ccaa2-115">`Boolean` から `Boolean?`への変換が関係しない `Boolean?` への縮小変換。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="ccaa2-116">クラスまたは構造体から `Boolean`への縮小変換演算子。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="ccaa2-117">`Boolean` または `IsTrue` 演算子への変換が定義されていない場合、コンパイラはエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ccaa2-118">`IsTrue` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="ccaa2-119">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ccaa2-120">詳細については、「[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccaa2-121">例</span><span class="sxs-lookup"><span data-stu-id="ccaa2-121">Example</span></span>  
 <span data-ttu-id="ccaa2-122">次のコード例では、`IsFalse` 演算子と `IsTrue` 演算子の定義を含む構造体のアウトラインを定義します。</span><span class="sxs-lookup"><span data-stu-id="ccaa2-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="ccaa2-123">参照</span><span class="sxs-lookup"><span data-stu-id="ccaa2-123">See also</span></span>

- [<span data-ttu-id="ccaa2-124">IsFalse 演算子</span><span class="sxs-lookup"><span data-stu-id="ccaa2-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="ccaa2-125">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="ccaa2-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="ccaa2-126">OrElse 演算子</span><span class="sxs-lookup"><span data-stu-id="ccaa2-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
