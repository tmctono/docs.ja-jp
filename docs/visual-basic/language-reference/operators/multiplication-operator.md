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
ms.openlocfilehash: 09b95585325b05c0b7925c4c1c9e123f45791e10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936644"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f1f47-102">\* 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1f47-102">\* Operator (Visual Basic)</span></span>
<span data-ttu-id="f1f47-103">2 つの数値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f47-104">構文</span><span class="sxs-lookup"><span data-stu-id="f1f47-104">Syntax</span></span>  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="f1f47-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="f1f47-105">Parts</span></span>  
  
|<span data-ttu-id="f1f47-106">用語</span><span class="sxs-lookup"><span data-stu-id="f1f47-106">Term</span></span>|<span data-ttu-id="f1f47-107">定義</span><span class="sxs-lookup"><span data-stu-id="f1f47-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="f1f47-108">必須。</span><span class="sxs-lookup"><span data-stu-id="f1f47-108">Required.</span></span> <span data-ttu-id="f1f47-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="f1f47-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="f1f47-110">必須。</span><span class="sxs-lookup"><span data-stu-id="f1f47-110">Required.</span></span> <span data-ttu-id="f1f47-111">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="f1f47-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="f1f47-112">結果</span><span class="sxs-lookup"><span data-stu-id="f1f47-112">Result</span></span>  
 <span data-ttu-id="f1f47-113">結果は、製品の`number1`と`number2`します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="f1f47-114">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="f1f47-114">Supported Types</span></span>  
 <span data-ttu-id="f1f47-115">符号なしと浮動小数点型を含め、すべての数値型と`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f47-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="f1f47-116">Remarks</span></span>  
 <span data-ttu-id="f1f47-117">結果のデータ型は、オペランドの型に依存します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="f1f47-118">次の表では、結果のデータ型を決定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="f1f47-119">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="f1f47-119">Operand data types</span></span>|<span data-ttu-id="f1f47-120">結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="f1f47-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="f1f47-121">両方の式が整数データ型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)、[バイト](../../../visual-basic/language-reference/data-types/byte-data-type.md)、[短い](../../../visual-basic/language-reference/data-types/short-data-type.md)、 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)、[整数](../../../visual-basic/language-reference/data-types/integer-data-type.md)、[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)、[長い](../../../visual-basic/language-reference/data-types/long-data-type.md)、 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="f1f47-121">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="f1f47-122">数値データ型のデータ型に適した`number1`と`number2`します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="f1f47-123">「整数の算術演算による」のテーブルを参照してください。[演算子結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="f1f47-124">両方の式が[10 進数](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="f1f47-124">Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="f1f47-125">両方の式が[単一](../../../visual-basic/language-reference/data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="f1f47-125">Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="f1f47-126">いずれかの式は、浮動小数点データ型 (`Single`または[二重](../../../visual-basic/language-reference/data-types/double-data-type.md)) 両方ではなく`Single`(注`Decimal`浮動小数点データ型ではありません)</span><span class="sxs-lookup"><span data-stu-id="f1f47-126">Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="f1f47-127">式の評価が場合[Nothing](../../../visual-basic/language-reference/nothing.md)、0 として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f1f47-127">If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f1f47-128">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="f1f47-128">Overloading</span></span>  
 <span data-ttu-id="f1f47-129">`*`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="f1f47-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f1f47-130">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="f1f47-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f1f47-131">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1f47-131">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1f47-132">例</span><span class="sxs-lookup"><span data-stu-id="f1f47-132">Example</span></span>  
 <span data-ttu-id="f1f47-133">この例では、`*`演算子を 2 つの数値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="f1f47-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="f1f47-134">2 つのオペランドの積になります。</span><span class="sxs-lookup"><span data-stu-id="f1f47-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f1f47-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1f47-135">See also</span></span>

- [<span data-ttu-id="f1f47-136">\*= 演算子</span><span class="sxs-lookup"><span data-stu-id="f1f47-136">\*= Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [<span data-ttu-id="f1f47-137">算術演算子</span><span class="sxs-lookup"><span data-stu-id="f1f47-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f1f47-138">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="f1f47-138">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f1f47-139">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="f1f47-139">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f1f47-140">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="f1f47-140">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
