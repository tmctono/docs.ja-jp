---
title: ^= 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: a956ffdaa3456ed09443f25c3383b6aab52fb5bf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867057"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="9f023-102">^= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f023-102">^= Operator (Visual Basic)</span></span>

<span data-ttu-id="9f023-103">変数またはプロパティの値を式の値で累乗し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="9f023-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f023-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f023-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9f023-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9f023-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="9f023-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="9f023-106">Required.</span></span> <span data-ttu-id="9f023-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9f023-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="9f023-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="9f023-108">Required.</span></span> <span data-ttu-id="9f023-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="9f023-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f023-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f023-110">Remarks</span></span>  

 <span data-ttu-id="9f023-111">`^=` 演算子の左側の要素には、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9f023-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9f023-112">変数またはプロパティを [ReadOnly](../modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9f023-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="9f023-113">`^=` 演算子は、最初に (演算子の左側にある) 変数またはプロパティの値を (演算子の右側にある) 式の値で累乗します。</span><span class="sxs-lookup"><span data-stu-id="9f023-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="9f023-114">次に、この演算子はその演算の結果を変数またはプロパティに戻して代入します。</span><span class="sxs-lookup"><span data-stu-id="9f023-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="9f023-115">Visual Basic では、常に [Double データ型](../data-types/double-data-type.md)で指数演算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f023-115">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span> <span data-ttu-id="9f023-116">異なる型のオペランドはすべて `Double` に変換され、結果は常に `Double` になります。</span><span class="sxs-lookup"><span data-stu-id="9f023-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="9f023-117">`expression` の値には、小数、負、またはその両方を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9f023-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9f023-118">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="9f023-118">Overloading</span></span>  

 <span data-ttu-id="9f023-119">[^ 演算子](exponentiation-operator.md)は "*オーバーロード*" できます。つまり、オペランドの型がクラスまたは構造体であるとき、そのクラスまたは構造体でその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="9f023-119">The [^ Operator](exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9f023-120">`^` 演算子をオーバーロードすると、`^=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="9f023-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="9f023-121">コードで、`^` をオーバーロードするクラスまたは構造体で `^=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9f023-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9f023-122">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f023-122">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f023-123">例</span><span class="sxs-lookup"><span data-stu-id="9f023-123">Example</span></span>  

 <span data-ttu-id="9f023-124">次の例では、`^=` 演算子を使用して、最初の `Integer` 変数を 2 番目の変数で累乗し、その結果を最初の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="9f023-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="9f023-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f023-125">See also</span></span>

- [<span data-ttu-id="9f023-126">^ 演算子</span><span class="sxs-lookup"><span data-stu-id="9f023-126">^ Operator</span></span>](exponentiation-operator.md)
- [<span data-ttu-id="9f023-127">代入演算子</span><span class="sxs-lookup"><span data-stu-id="9f023-127">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="9f023-128">算術演算子</span><span class="sxs-lookup"><span data-stu-id="9f023-128">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="9f023-129">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="9f023-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="9f023-130">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="9f023-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="9f023-131">ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f023-131">Statements</span></span>](../../programming-guide/language-features/statements.md)
