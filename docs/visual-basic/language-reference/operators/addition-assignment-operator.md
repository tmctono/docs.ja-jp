---
title: += 演算子
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
ms.openlocfilehash: a3a37798a3ddb480ac5322c4b2d3e9396e739aa6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873483"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7737a-102">+= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7737a-102">+= Operator (Visual Basic)</span></span>

<span data-ttu-id="7737a-103">数値式の値を数値変数またはプロパティの値に加算し、結果をその変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="7737a-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="7737a-104">また、`String` 式を `String` 変数またはプロパティに連結し、結果をその変数またはプロパティに代入するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7737a-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7737a-105">構文</span><span class="sxs-lookup"><span data-stu-id="7737a-105">Syntax</span></span>  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="7737a-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="7737a-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="7737a-107">必須です。</span><span class="sxs-lookup"><span data-stu-id="7737a-107">Required.</span></span> <span data-ttu-id="7737a-108">任意の数値または `String` 変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="7737a-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="7737a-109">必須です。</span><span class="sxs-lookup"><span data-stu-id="7737a-109">Required.</span></span> <span data-ttu-id="7737a-110">任意の数値または `String` 式。</span><span class="sxs-lookup"><span data-stu-id="7737a-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7737a-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="7737a-111">Remarks</span></span>  

 <span data-ttu-id="7737a-112">`+=` 演算子の左側の要素には、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7737a-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="7737a-113">変数またはプロパティを [ReadOnly](../modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7737a-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="7737a-114">`+=` 演算子は、右側の値を左側の変数またはプロパティに追加し、その結果を左側の変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="7737a-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="7737a-115">`+=` 演算子を使用して、右側の `String` 式を左側の `String` 変数またはプロパティに連結し、その結果を左側の変数またはプロパティに代入することもできます。</span><span class="sxs-lookup"><span data-stu-id="7737a-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7737a-116">`+=` 演算子を使用すると、加算と文字列連結のどちらが行われるのか判断できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7737a-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="7737a-117">あいまいさをなくし、自己文書化コードを実現するために、連結には `&=` 演算子を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7737a-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="7737a-118">コンパイル環境で厳密なセマンティクスが適用されている場合、この代入演算子は拡大変換を暗黙的に実行しますが、縮小変換は実行しません。</span><span class="sxs-lookup"><span data-stu-id="7737a-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="7737a-119">これらの変換の詳細については、「[拡大変換と縮小変換](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7737a-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="7737a-120">厳密なセマンティクスおよび寛容なセマンティクスの詳細については、「[Option Strict ステートメント](../statements/option-strict-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7737a-120">For more information on strict and permissive semantics, see [Option Strict Statement](../statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="7737a-121">寛容なセマンティクスが許可されている場合、`+=` 演算子は、`+` 演算子によって実行されるものと同じ各種変換 (文字列変換および数値変換) を暗黙的に実行します。</span><span class="sxs-lookup"><span data-stu-id="7737a-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="7737a-122">これらの変換の詳細については、「[+ 演算子](addition-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7737a-122">For details on these conversions, see [+ Operator](addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="7737a-123">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="7737a-123">Overloading</span></span>  

 <span data-ttu-id="7737a-124">`+` 演算子は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、このクラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="7737a-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7737a-125">`+` 演算子をオーバーロードすると、`+=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="7737a-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="7737a-126">コードで、`+` をオーバーロードするクラスまたは構造体に `+=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7737a-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7737a-127">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7737a-127">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7737a-128">例</span><span class="sxs-lookup"><span data-stu-id="7737a-128">Example</span></span>  

 <span data-ttu-id="7737a-129">次の例では、`+=` 演算子を使用して、ある変数の値を別の値と結合します。</span><span class="sxs-lookup"><span data-stu-id="7737a-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="7737a-130">最初の部分では `+=` を数値変数と共に使用して、ある値を別の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="7737a-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="7737a-131">2 番目の部分では、`+=` を `String` 変数と共に使用して、ある値を別の値と連結します。</span><span class="sxs-lookup"><span data-stu-id="7737a-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="7737a-132">どちらの場合も、結果は最初の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="7737a-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="7737a-133">`num1` の値は 13 になり、`str1` の値は "103" になりました。</span><span class="sxs-lookup"><span data-stu-id="7737a-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7737a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="7737a-134">See also</span></span>

- [<span data-ttu-id="7737a-135">+ 演算子</span><span class="sxs-lookup"><span data-stu-id="7737a-135">+ Operator</span></span>](addition-operator.md)
- [<span data-ttu-id="7737a-136">代入演算子</span><span class="sxs-lookup"><span data-stu-id="7737a-136">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="7737a-137">算術演算子</span><span class="sxs-lookup"><span data-stu-id="7737a-137">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="7737a-138">連結演算子</span><span class="sxs-lookup"><span data-stu-id="7737a-138">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="7737a-139">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="7737a-139">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="7737a-140">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="7737a-140">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="7737a-141">ステートメント</span><span class="sxs-lookup"><span data-stu-id="7737a-141">Statements</span></span>](../../programming-guide/language-features/statements.md)
