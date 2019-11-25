---
title: '方法 : 演算子プロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: a685be7cc3b346b271413e2c29faae5a839313f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340244"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="bfc45-102">方法: 演算子プロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfc45-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="bfc45-103">You call an operator procedure by using the operator symbol in an expression.</span><span class="sxs-lookup"><span data-stu-id="bfc45-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="bfc45-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span><span class="sxs-lookup"><span data-stu-id="bfc45-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="bfc45-105">You do not call operator procedures explicitly.</span><span class="sxs-lookup"><span data-stu-id="bfc45-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="bfc45-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span><span class="sxs-lookup"><span data-stu-id="bfc45-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="bfc45-107">Visual Basic makes the call to the operator procedure.</span><span class="sxs-lookup"><span data-stu-id="bfc45-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="bfc45-108">Defining an operator on a class or structure is also called *overloading* the operator.</span><span class="sxs-lookup"><span data-stu-id="bfc45-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="bfc45-109">To call an operator procedure</span><span class="sxs-lookup"><span data-stu-id="bfc45-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="bfc45-110">Use the operator symbol in an expression in the ordinary way.</span><span class="sxs-lookup"><span data-stu-id="bfc45-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="bfc45-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span><span class="sxs-lookup"><span data-stu-id="bfc45-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="bfc45-112">The operator contributes to the value of the expression as expected.</span><span class="sxs-lookup"><span data-stu-id="bfc45-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="bfc45-113">To call a conversion operator procedure</span><span class="sxs-lookup"><span data-stu-id="bfc45-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="bfc45-114">Use `CType` inside an expression.</span><span class="sxs-lookup"><span data-stu-id="bfc45-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="bfc45-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span><span class="sxs-lookup"><span data-stu-id="bfc45-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="bfc45-116">`CType` calls the conversion operator procedure and returns the converted value.</span><span class="sxs-lookup"><span data-stu-id="bfc45-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfc45-117">例</span><span class="sxs-lookup"><span data-stu-id="bfc45-117">Example</span></span>  
 <span data-ttu-id="bfc45-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span><span class="sxs-lookup"><span data-stu-id="bfc45-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="bfc45-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span><span class="sxs-lookup"><span data-stu-id="bfc45-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="bfc45-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="bfc45-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="bfc45-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="bfc45-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bfc45-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="bfc45-122">Compiling the Code</span></span>  
 <span data-ttu-id="bfc45-123">Be sure the class or structure you are using defines the operator you want to use.</span><span class="sxs-lookup"><span data-stu-id="bfc45-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc45-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfc45-124">See also</span></span>

- [<span data-ttu-id="bfc45-125">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="bfc45-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="bfc45-126">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="bfc45-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="bfc45-127">方法 : 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="bfc45-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="bfc45-128">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="bfc45-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="bfc45-129">Widening</span><span class="sxs-lookup"><span data-stu-id="bfc45-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="bfc45-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="bfc45-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="bfc45-131">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="bfc45-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="bfc45-132">方法 : 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="bfc45-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="bfc45-133">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="bfc45-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="bfc45-134">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="bfc45-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
