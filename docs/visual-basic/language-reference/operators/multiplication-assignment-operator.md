---
title: '*= 演算子'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 4e2f18fb2b8110d97390390b3934d3c1761baa35
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866736"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="cd846-102">\*= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd846-102">\*= Operator (Visual Basic)</span></span>

<span data-ttu-id="cd846-103">変数またはプロパティの値を式の値で乗算し、その結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="cd846-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd846-104">構文</span><span class="sxs-lookup"><span data-stu-id="cd846-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="cd846-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="cd846-105">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="cd846-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="cd846-106">Required.</span></span> <span data-ttu-id="cd846-107">任意の数値変数またはプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cd846-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="cd846-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="cd846-108">Required.</span></span> <span data-ttu-id="cd846-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="cd846-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd846-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="cd846-110">Remarks</span></span>  

 <span data-ttu-id="cd846-111">`*=` 演算子の左側の要素には、単純なスカラー変数、プロパティ、または配列の要素を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cd846-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="cd846-112">変数またはプロパティを [ReadOnly](../modifiers/readonly.md) にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cd846-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="cd846-113">`*=` 演算子は、最初に (演算子の右側にある) 式の値に、(演算子の左側にある) 変数またはプロパティの値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="cd846-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="cd846-114">次に、その演算の結果を変数またはプロパティに代入します。</span><span class="sxs-lookup"><span data-stu-id="cd846-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="cd846-115">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="cd846-115">Overloading</span></span>  

 <span data-ttu-id="cd846-116">[\* 演算子](multiplication-operator.md)は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、クラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="cd846-116">The [\* Operator](multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="cd846-117">`*` 演算子をオーバーロードすると、`*=` 演算子の動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="cd846-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="cd846-118">コードで、`*` をオーバーロードするクラスまたは構造体で `*=` を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cd846-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cd846-119">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd846-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd846-120">例</span><span class="sxs-lookup"><span data-stu-id="cd846-120">Example</span></span>  

 <span data-ttu-id="cd846-121">次の例では、`*=` 演算子を使用して、最初の `Integer` 変数に 2 番目の変数を乗算し、その結果を最初の変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="cd846-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="cd846-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd846-122">See also</span></span>

- [<span data-ttu-id="cd846-123">\* 演算子</span><span class="sxs-lookup"><span data-stu-id="cd846-123">\* Operator</span></span>](multiplication-operator.md)
- [<span data-ttu-id="cd846-124">代入演算子</span><span class="sxs-lookup"><span data-stu-id="cd846-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="cd846-125">算術演算子</span><span class="sxs-lookup"><span data-stu-id="cd846-125">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="cd846-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="cd846-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="cd846-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="cd846-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="cd846-128">ステートメント</span><span class="sxs-lookup"><span data-stu-id="cd846-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
