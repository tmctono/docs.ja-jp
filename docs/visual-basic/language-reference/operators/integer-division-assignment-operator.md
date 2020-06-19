---
title: '\= 演算子'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: a546d8b0c9b3852386970f80d3da96794da2351c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370948"
---
# <a name="-operator"></a><span data-ttu-id="4bdfb-102">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="4bdfb-102">\\= Operator</span></span>
<span data-ttu-id="4bdfb-103">変数またはプロパティの値を式の値で除算し、整数の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bdfb-104">構文</span><span class="sxs-lookup"><span data-stu-id="4bdfb-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="4bdfb-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="4bdfb-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="4bdfb-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-106">Required.</span></span> <span data-ttu-id="4bdfb-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="4bdfb-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-108">Required.</span></span> <span data-ttu-id="4bdfb-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bdfb-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="4bdfb-110">Remarks</span></span>  
 <span data-ttu-id="4bdfb-111">`\=` 演算子の左側の要素には、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="4bdfb-112">変数またはプロパティを [ReadOnly](../modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="4bdfb-113">`\=` 演算子は、左側の変数またはプロパティの値を右側の値で除算し、整数の結果を左側の変数またはプロパティに代入します</span><span class="sxs-lookup"><span data-stu-id="4bdfb-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="4bdfb-114">整数除算の詳細については、「[\ 演算子 (Visual Basic)](integer-division-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-114">For further information on integer division, see [\ Operator (Visual Basic)](integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="4bdfb-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="4bdfb-115">Overloading</span></span>  
 <span data-ttu-id="4bdfb-116">`\` 演算子は "*オーバーロード*" できます。つまり、オペランドの型がクラスまたは構造体であるとき、そのクラスまたは構造体で、演算子の動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="4bdfb-117">`\` 演算子をオーバーロードすると、`\=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="4bdfb-118">コードで、`\` をオーバーロードするクラスまたは構造体で `\=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="4bdfb-119">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bdfb-120">例</span><span class="sxs-lookup"><span data-stu-id="4bdfb-120">Example</span></span>  
 <span data-ttu-id="4bdfb-121">次の例では、`\=` 演算子を使用して 1 番目の `Integer` 変数を 2 番目の変数で除算し、整数の結果を 1 番目の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="4bdfb-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="4bdfb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bdfb-122">See also</span></span>

- [<span data-ttu-id="4bdfb-123">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bdfb-123">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="4bdfb-124">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bdfb-124">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="4bdfb-125">代入演算子</span><span class="sxs-lookup"><span data-stu-id="4bdfb-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="4bdfb-126">算術演算子</span><span class="sxs-lookup"><span data-stu-id="4bdfb-126">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="4bdfb-127">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="4bdfb-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="4bdfb-128">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="4bdfb-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="4bdfb-129">ステートメント</span><span class="sxs-lookup"><span data-stu-id="4bdfb-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
