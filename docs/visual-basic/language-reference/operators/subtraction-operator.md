---
title: '- 演算子 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 5f6b6b67e2999d380cfca078a43162b3e1db2206
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701302"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="15a43-102">- 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15a43-102">- Operator (Visual Basic)</span></span>
<span data-ttu-id="15a43-103">2つの数値式の差、または数値式の負の値を返します。</span><span class="sxs-lookup"><span data-stu-id="15a43-103">Returns the difference between two numeric expressions or the negative value of a numeric expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a43-104">構文</span><span class="sxs-lookup"><span data-stu-id="15a43-104">Syntax</span></span>  
  
```vb  
expression1 – expression2
```
  
<span data-ttu-id="15a43-105">または</span><span class="sxs-lookup"><span data-stu-id="15a43-105">or</span></span>

```vb  
–expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="15a43-106">指定項目</span><span class="sxs-lookup"><span data-stu-id="15a43-106">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="15a43-107">必須。</span><span class="sxs-lookup"><span data-stu-id="15a43-107">Required.</span></span> <span data-ttu-id="15a43-108">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="15a43-108">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="15a43-109">@No__t-0 演算子が負の値を計算する場合を除き、必須です。</span><span class="sxs-lookup"><span data-stu-id="15a43-109">Required unless the `–` operator is calculating a negative value.</span></span> <span data-ttu-id="15a43-110">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="15a43-110">Any numeric expression.</span></span>  
  
## <a name="result"></a><span data-ttu-id="15a43-111">結果</span><span class="sxs-lookup"><span data-stu-id="15a43-111">Result</span></span>  
 <span data-ttu-id="15a43-112">結果として、`expression1` と `expression2` の差、または `expression1` の符号が反転された値が返されます。</span><span class="sxs-lookup"><span data-stu-id="15a43-112">The result is the difference between `expression1` and `expression2`, or the negated value of `expression1`.</span></span>  
  
 <span data-ttu-id="15a43-113">結果のデータ型は、および`expression1` `expression2`のデータ型に適した数値型です。</span><span class="sxs-lookup"><span data-stu-id="15a43-113">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="15a43-114">「[演算子の結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)」の「整数演算」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15a43-114">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="15a43-115">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="15a43-115">Supported Types</span></span>  
 <span data-ttu-id="15a43-116">すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="15a43-116">All numeric types.</span></span> <span data-ttu-id="15a43-117">これには、符号なしおよび浮動小数点`Decimal`型とが含まれます。</span><span class="sxs-lookup"><span data-stu-id="15a43-117">This includes the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15a43-118">コメント</span><span class="sxs-lookup"><span data-stu-id="15a43-118">Remarks</span></span>  
 <span data-ttu-id="15a43-119">前に示した構文に示されている最初の使用法では、`–` 演算子は2つの数値式の差を表す*二項*算術減算演算子です。</span><span class="sxs-lookup"><span data-stu-id="15a43-119">In the first usage shown in the syntax shown previously, the `–` operator is the *binary* arithmetic subtraction operator for the difference between two numeric expressions.</span></span>  
  
 <span data-ttu-id="15a43-120">前に示した構文に示されている2番目の使用法では、`–` 演算子は、式の負の値を表す*単項*否定演算子です。</span><span class="sxs-lookup"><span data-stu-id="15a43-120">In the second usage shown in the syntax shown previously, the `–` operator is the *unary* negation operator for the negative value of an expression.</span></span> <span data-ttu-id="15a43-121">この意味では、否定は `expression1` の符号を反転することで構成され、`expression1` が負の場合は結果が正になります。</span><span class="sxs-lookup"><span data-stu-id="15a43-121">In this sense, the negation consists of reversing the sign of `expression1` so that the result is positive if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="15a43-122">いずれかの式が[Nothing](../../../visual-basic/language-reference/nothing.md)と評価された場合、`–` 演算子はそれを0として扱います。</span><span class="sxs-lookup"><span data-stu-id="15a43-122">If either expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the `–` operator treats it as zero.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15a43-123">@No__t-0 演算子は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="15a43-123">The `–` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="15a43-124">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="15a43-124">If your code uses this operator on such a class or structure, make sure that you understand its redefined behavior.</span></span> <span data-ttu-id="15a43-125">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15a43-125">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="15a43-126">例</span><span class="sxs-lookup"><span data-stu-id="15a43-126">Example</span></span>  
 <span data-ttu-id="15a43-127">次の例では、`–` 演算子を使用して、2つの数値の差を計算して返し、その後で数値を否定します。</span><span class="sxs-lookup"><span data-stu-id="15a43-127">The following example uses the `–` operator to calculate and return the difference between two numbers, and then to negate a number.</span></span>  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 <span data-ttu-id="15a43-128">これらのステートメントの実行後、`binaryResult` には124.45 が含まれ、`unaryResult` は–334.90 を含みます。</span><span class="sxs-lookup"><span data-stu-id="15a43-128">Following the execution of these statements, `binaryResult` contains 124.45 and `unaryResult` contains –334.90.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a43-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="15a43-129">See also</span></span>

- [<span data-ttu-id="15a43-130">-= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15a43-130">-= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [<span data-ttu-id="15a43-131">算術演算子</span><span class="sxs-lookup"><span data-stu-id="15a43-131">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="15a43-132">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="15a43-132">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="15a43-133">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="15a43-133">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="15a43-134">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="15a43-134">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
