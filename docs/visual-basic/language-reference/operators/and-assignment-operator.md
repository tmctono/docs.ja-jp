---
title: '&amp;= 演算子'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350260"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="7de39-102">&amp;= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7de39-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="7de39-103">`String` 式を `String` 変数またはプロパティに連結し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="7de39-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de39-104">構文</span><span class="sxs-lookup"><span data-stu-id="7de39-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="7de39-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7de39-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="7de39-106">必須。</span><span class="sxs-lookup"><span data-stu-id="7de39-106">Required.</span></span> <span data-ttu-id="7de39-107">任意の `String` 変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7de39-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="7de39-108">必須。</span><span class="sxs-lookup"><span data-stu-id="7de39-108">Required.</span></span> <span data-ttu-id="7de39-109">任意のブール型 ( `String` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="7de39-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7de39-110">コメント</span><span class="sxs-lookup"><span data-stu-id="7de39-110">Remarks</span></span>  
 <span data-ttu-id="7de39-111">`&=` 演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7de39-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="7de39-112">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7de39-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="7de39-113">`&=` 演算子は、右側にある `String` 式を左側の `String` 変数またはプロパティに連結し、その結果を左側の変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="7de39-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7de39-114">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="7de39-114">Overloading</span></span>  
 <span data-ttu-id="7de39-115">[& 演算子](../../../visual-basic/language-reference/operators/concatenation-operator.md)は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="7de39-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7de39-116">`&` 演算子のオーバーロードは、`&=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="7de39-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="7de39-117">コードで `&`をオーバーロードするクラスまたは構造体の `&=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7de39-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7de39-118">詳細については、「[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7de39-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7de39-119">例</span><span class="sxs-lookup"><span data-stu-id="7de39-119">Example</span></span>  
 <span data-ttu-id="7de39-120">次の例では、`&=` 演算子を使用して2つの `String` 変数を連結し、その結果を最初の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="7de39-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7de39-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="7de39-121">See also</span></span>

- [<span data-ttu-id="7de39-122">& 演算子</span><span class="sxs-lookup"><span data-stu-id="7de39-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="7de39-123">+= 演算子</span><span class="sxs-lookup"><span data-stu-id="7de39-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="7de39-124">代入演算子</span><span class="sxs-lookup"><span data-stu-id="7de39-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="7de39-125">連結演算子</span><span class="sxs-lookup"><span data-stu-id="7de39-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="7de39-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="7de39-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7de39-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="7de39-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7de39-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="7de39-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
