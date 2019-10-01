---
title: '* 演算子 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: b5b601c7604cb7ce1afaebc98b2157634a77fda4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701092"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f5e16-102">\* 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5e16-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="f5e16-103">2 つの数値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="f5e16-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e16-104">構文</span><span class="sxs-lookup"><span data-stu-id="f5e16-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="f5e16-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f5e16-105">Parts</span></span>  
  
|<span data-ttu-id="f5e16-106">項目</span><span class="sxs-lookup"><span data-stu-id="f5e16-106">Term</span></span>|<span data-ttu-id="f5e16-107">定義</span><span class="sxs-lookup"><span data-stu-id="f5e16-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="f5e16-108">必須。</span><span class="sxs-lookup"><span data-stu-id="f5e16-108">Required.</span></span> <span data-ttu-id="f5e16-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="f5e16-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="f5e16-110">必須。</span><span class="sxs-lookup"><span data-stu-id="f5e16-110">Required.</span></span> <span data-ttu-id="f5e16-111">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="f5e16-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="f5e16-112">結果</span><span class="sxs-lookup"><span data-stu-id="f5e16-112">Result</span></span>  
 <span data-ttu-id="f5e16-113">結果は、`number1` および `number2` の積になります。</span><span class="sxs-lookup"><span data-stu-id="f5e16-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="f5e16-114">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="f5e16-114">Supported Types</span></span>  
 <span data-ttu-id="f5e16-115">符号なしの型および浮動小数点型およびを`Decimal`含む、すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="f5e16-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5e16-116">コメント</span><span class="sxs-lookup"><span data-stu-id="f5e16-116">Remarks</span></span>  
 <span data-ttu-id="f5e16-117">結果のデータ型は、オペランドの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f5e16-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="f5e16-118">次の表は、結果のデータ型がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="f5e16-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="f5e16-119">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="f5e16-119">Operand data types</span></span>|<span data-ttu-id="f5e16-120">結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="f5e16-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="f5e16-121">両方の式は整数データ型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)、 [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)、 [Short](../../../visual-basic/language-reference/data-types/short-data-type.md)、 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)、 [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)、 [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)、 [Long](../../../visual-basic/language-reference/data-types/long-data-type.md)、 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)) です。</span><span class="sxs-lookup"><span data-stu-id="f5e16-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="f5e16-122">@No__t-0 および `number2` のデータ型に適した数値データ型。</span><span class="sxs-lookup"><span data-stu-id="f5e16-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="f5e16-123">「[演算子の結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)」の「整数演算」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5e16-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="f5e16-124">両方の式が[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)です。</span><span class="sxs-lookup"><span data-stu-id="f5e16-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="f5e16-125">両方の式が[Single](../../../visual-basic/language-reference/data-types/single-data-type.md)です。</span><span class="sxs-lookup"><span data-stu-id="f5e16-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="f5e16-126">いずれかの式が浮動小数点データ型 (`Single` または[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) ではなく `Single` (注 `Decimal` は浮動小数点データ型ではありません)</span><span class="sxs-lookup"><span data-stu-id="f5e16-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="f5e16-127">式が[Nothing](../../../visual-basic/language-reference/nothing.md)に評価される場合は、0として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f5e16-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f5e16-128">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="f5e16-128">Overloading</span></span>  
 <span data-ttu-id="f5e16-129">@No__t-0 演算子は*オーバーロード*できます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="f5e16-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f5e16-130">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5e16-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f5e16-131">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5e16-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5e16-132">例</span><span class="sxs-lookup"><span data-stu-id="f5e16-132">Example</span></span>  
 <span data-ttu-id="f5e16-133">この例では、`*` 演算子を使用して2つの数値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="f5e16-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="f5e16-134">結果は、2つのオペランドの積になります。</span><span class="sxs-lookup"><span data-stu-id="f5e16-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f5e16-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5e16-135">See also</span></span>

- [<span data-ttu-id="f5e16-136">\*= 演算子</span><span class="sxs-lookup"><span data-stu-id="f5e16-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="f5e16-137">算術演算子</span><span class="sxs-lookup"><span data-stu-id="f5e16-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f5e16-138">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="f5e16-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f5e16-139">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="f5e16-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f5e16-140">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="f5e16-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
