---
title: '* 演算子'
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
ms.openlocfilehash: 7038fef4258d190b726a851b26f2a2840ff3c0ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873367"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="0041d-102">\* 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0041d-102">\* Operator (Visual Basic)</span></span>

<span data-ttu-id="0041d-103">2 つの数値を乗算します。</span><span class="sxs-lookup"><span data-stu-id="0041d-103">Multiplies two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0041d-104">構文</span><span class="sxs-lookup"><span data-stu-id="0041d-104">Syntax</span></span>  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a><span data-ttu-id="0041d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="0041d-105">Parts</span></span>  
  
|<span data-ttu-id="0041d-106">用語</span><span class="sxs-lookup"><span data-stu-id="0041d-106">Term</span></span>|<span data-ttu-id="0041d-107">定義</span><span class="sxs-lookup"><span data-stu-id="0041d-107">Definition</span></span>|  
|---|---|  
|`number1`|<span data-ttu-id="0041d-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="0041d-108">Required.</span></span> <span data-ttu-id="0041d-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="0041d-109">Any numeric expression.</span></span>|  
|`number2`|<span data-ttu-id="0041d-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="0041d-110">Required.</span></span> <span data-ttu-id="0041d-111">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="0041d-111">Any numeric expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="0041d-112">結果</span><span class="sxs-lookup"><span data-stu-id="0041d-112">Result</span></span>  

 <span data-ttu-id="0041d-113">結果は `number1` と `number2` の積になります。</span><span class="sxs-lookup"><span data-stu-id="0041d-113">The result is the product of `number1` and `number2`.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="0041d-114">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="0041d-114">Supported Types</span></span>  

 <span data-ttu-id="0041d-115">すべての数値型。これには、符号なしおよび浮動小数点型と `Decimal` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0041d-115">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0041d-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="0041d-116">Remarks</span></span>  

 <span data-ttu-id="0041d-117">結果のデータ型は、オペランドの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0041d-117">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="0041d-118">次の表は、結果のデータ型がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0041d-118">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="0041d-119">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="0041d-119">Operand data types</span></span>|<span data-ttu-id="0041d-120">結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="0041d-120">Result data type</span></span>|  
|---|---|  
|<span data-ttu-id="0041d-121">両方の式が整数データ型 ([SByte](../data-types/sbyte-data-type.md)、[Byte](../data-types/byte-data-type.md)、[Short](../data-types/short-data-type.md)、[UShort](../data-types/ushort-data-type.md)、[Integer](../data-types/integer-data-type.md)、[UInteger](../data-types/uinteger-data-type.md)、[Long](../data-types/long-data-type.md)、[ULong](../data-types/ulong-data-type.md))</span><span class="sxs-lookup"><span data-stu-id="0041d-121">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|<span data-ttu-id="0041d-122">`number1` と `number2` のデータ型に適した数値データ型。</span><span class="sxs-lookup"><span data-stu-id="0041d-122">A numeric data type appropriate for the data types of `number1` and `number2`.</span></span> <span data-ttu-id="0041d-123">「[演算子の結果のデータ型](data-types-of-operator-results.md)」の「整数演算」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0041d-123">See the "Integer Arithmetic" tables in [Data Types of Operator Results](data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="0041d-124">両方の式が [decimal](../data-types/decimal-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="0041d-124">Both expressions are [Decimal](../data-types/decimal-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="0041d-125">両方の式が [Single](../data-types/single-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="0041d-125">Both expressions are [Single](../data-types/single-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="0041d-126">一方の式が浮動小数点データ型 (`Single` または [Double](../data-types/double-data-type.md)) で、両方が `Single` ではない (`Decimal` は浮動小数点データ型ではないので注意してください)</span><span class="sxs-lookup"><span data-stu-id="0041d-126">Either expression is a floating-point data type (`Single` or [Double](../data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)</span></span>|`Double`|  
  
 <span data-ttu-id="0041d-127">式が [Nothing](../nothing.md) に評価される場合、0 として扱われます。</span><span class="sxs-lookup"><span data-stu-id="0041d-127">If an expression evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0041d-128">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="0041d-128">Overloading</span></span>  

 <span data-ttu-id="0041d-129">`*` 演算子は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、クラスまたは構造体はその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="0041d-129">The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0041d-130">コードで、そのようなクラスまたは構造体に対してこの演算子が使用される場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0041d-130">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0041d-131">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0041d-131">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0041d-132">例</span><span class="sxs-lookup"><span data-stu-id="0041d-132">Example</span></span>  

 <span data-ttu-id="0041d-133">この例では、`*` 演算子を使用して 2 つの数値を乗算しています。</span><span class="sxs-lookup"><span data-stu-id="0041d-133">This example uses the `*` operator to multiply two numbers.</span></span> <span data-ttu-id="0041d-134">結果は 2 つのオペランドの積になります。</span><span class="sxs-lookup"><span data-stu-id="0041d-134">The result is the product of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="0041d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="0041d-135">See also</span></span>

- [<span data-ttu-id="0041d-136">\*= 演算子</span><span class="sxs-lookup"><span data-stu-id="0041d-136">\*= Operator</span></span>](multiplication-assignment-operator.md)
- [<span data-ttu-id="0041d-137">算術演算子</span><span class="sxs-lookup"><span data-stu-id="0041d-137">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="0041d-138">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="0041d-138">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="0041d-139">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="0041d-139">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="0041d-140">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="0041d-140">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
