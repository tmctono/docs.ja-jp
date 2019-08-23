---
title: += 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: f615df50643912beb12eb89d80b922fc30a3e6df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944483"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="6c91c-102">+= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c91c-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="6c91c-103">数値式の値を数値変数またはプロパティの値に加算し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="6c91c-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="6c91c-104">また、を使用して、 `String` `String`変数またはプロパティに式を連結し、その結果を変数またはプロパティに代入することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c91c-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c91c-105">構文</span><span class="sxs-lookup"><span data-stu-id="6c91c-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6c91c-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="6c91c-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="6c91c-107">必須。</span><span class="sxs-lookup"><span data-stu-id="6c91c-107">Required.</span></span> <span data-ttu-id="6c91c-108">任意の数値`String`または変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="6c91c-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="6c91c-109">必須。</span><span class="sxs-lookup"><span data-stu-id="6c91c-109">Required.</span></span> <span data-ttu-id="6c91c-110">任意の数値`String`または式。</span><span class="sxs-lookup"><span data-stu-id="6c91c-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c91c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="6c91c-111">Remarks</span></span>  
 <span data-ttu-id="6c91c-112">`+=`演算子の左側の要素は、単純なスカラー変数、プロパティ、または配列の要素にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c91c-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="6c91c-113">変数またはプロパティを[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6c91c-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="6c91c-114">演算子`+=`は、右辺の値を左側の変数またはプロパティに追加し、結果を左側の変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="6c91c-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="6c91c-115">演算子を使用すると、右側の`String`式を左側の`String`変数またはプロパティに連結し、その結果を左側の変数またはプロパティに代入することもできます。 `+=`</span><span class="sxs-lookup"><span data-stu-id="6c91c-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6c91c-116">`+=`演算子を使用すると、加算または文字列の連結が行われるかどうかを判断できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c91c-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="6c91c-117">`&=`演算子を連結に使用して、あいまいさをなくし、自己記述型のコードを提供します。</span><span class="sxs-lookup"><span data-stu-id="6c91c-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="6c91c-118">コンパイル環境で厳密なセマンティクスが適用されている場合、この代入演算子は、暗黙的に拡張を実行しますが、縮小変換は実行しません。</span><span class="sxs-lookup"><span data-stu-id="6c91c-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="6c91c-119">これらの変換の詳細については、「[拡大変換と縮小変換](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c91c-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="6c91c-120">厳密なセマンティクスと寛容なセマンティクスの詳細については、「 [Option Strict ステートメント](../../../visual-basic/language-reference/statements/option-strict-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c91c-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="6c91c-121">寛容なセマンティクスが許可され`+=`ている場合、演算子は、 `+`演算子によって実行されるものと同一のさまざまな文字列と数値変換を暗黙的に実行します。</span><span class="sxs-lookup"><span data-stu-id="6c91c-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="6c91c-122">これらの変換の詳細については、「 [+ 演算子](../../../visual-basic/language-reference/operators/addition-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c91c-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="6c91c-123">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="6c91c-123">Overloading</span></span>  
 <span data-ttu-id="6c91c-124">演算子はオーバーロードできます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。 `+`</span><span class="sxs-lookup"><span data-stu-id="6c91c-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6c91c-125">演算子のオーバーロードは、 `+=`演算子の動作に影響します。 `+`</span><span class="sxs-lookup"><span data-stu-id="6c91c-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="6c91c-126">をオーバーロード`+=` `+`するクラスまたは構造体でコードを使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6c91c-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6c91c-127">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c91c-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c91c-128">例</span><span class="sxs-lookup"><span data-stu-id="6c91c-128">Example</span></span>  
 <span data-ttu-id="6c91c-129">次の例では`+=` 、演算子を使用して、ある変数の値を別の変数と結合します。</span><span class="sxs-lookup"><span data-stu-id="6c91c-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="6c91c-130">最初の部分で`+=`は、数値変数と共にを使用して、1つの値を別の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="6c91c-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="6c91c-131">2番目の`+=`部分`String`では、を使用して、1つの値を別の値と連結します。</span><span class="sxs-lookup"><span data-stu-id="6c91c-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="6c91c-132">どちらの場合も、結果は最初の変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6c91c-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="6c91c-133">の`num1`値は13になり、の`str1`値は "103" になります。</span><span class="sxs-lookup"><span data-stu-id="6c91c-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c91c-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c91c-134">See also</span></span>

- [<span data-ttu-id="6c91c-135">+ 演算子</span><span class="sxs-lookup"><span data-stu-id="6c91c-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="6c91c-136">代入演算子</span><span class="sxs-lookup"><span data-stu-id="6c91c-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="6c91c-137">算術演算子</span><span class="sxs-lookup"><span data-stu-id="6c91c-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="6c91c-138">連結演算子</span><span class="sxs-lookup"><span data-stu-id="6c91c-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="6c91c-139">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="6c91c-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6c91c-140">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="6c91c-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6c91c-141">ステートメント</span><span class="sxs-lookup"><span data-stu-id="6c91c-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
