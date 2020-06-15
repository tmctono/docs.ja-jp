---
title: 演算子プロシージャ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: b395f5fcf1b89bb49e55e207c4910e95f2aae69d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345999"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="b6a23-102">演算子プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6a23-102">Operator Procedures (Visual Basic)</span></span>

<span data-ttu-id="b6a23-103">演算子プロシージャは、定義済みのクラスまたは構造体での標準演算子 (`*`、`<>`、`And` など) の動作を定義する一連の Visual Basic ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="b6a23-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="b6a23-104">これは、"*演算子のオーバーロード*" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b6a23-104">This is also called *operator overloading*.</span></span>

## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="b6a23-105">演算子プロシージャを定義する場合</span><span class="sxs-lookup"><span data-stu-id="b6a23-105">When to Define Operator Procedures</span></span>

<span data-ttu-id="b6a23-106">クラスまたは構造体を定義したら、そのクラスまたは構造体の型で変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="b6a23-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="b6a23-107">このような変数は、式の一部として演算に関与することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6a23-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="b6a23-108">そのためには、演算子のオペランドである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a23-108">To do this, it must be an operand of an operator.</span></span>

<span data-ttu-id="b6a23-109">Visual Basic では、基本的なデータ型でのみ演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="b6a23-110">オペランドの一方または両方がクラスまたは構造体の型である場合、演算子の動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b6a23-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>

<span data-ttu-id="b6a23-111">詳細については、「[Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b6a23-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>

## <a name="types-of-operator-procedure"></a><span data-ttu-id="b6a23-112">演算子プロシージャの型</span><span class="sxs-lookup"><span data-stu-id="b6a23-112">Types of Operator Procedure</span></span>

<span data-ttu-id="b6a23-113">演算子プロシージャは、次のいずれかの型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6a23-113">An operator procedure can be one of the following types:</span></span>

- <span data-ttu-id="b6a23-114">引数がクラスまたは構造体の型である単項演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="b6a23-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="b6a23-115">引数の少なくとも 1 つがクラスまたは構造体の型である 2 項演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="b6a23-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>

- <span data-ttu-id="b6a23-116">引数がクラスまたは構造体の型である変換演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="b6a23-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>

- <span data-ttu-id="b6a23-117">クラスまたは構造体の型を返す変換演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="b6a23-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>

 <span data-ttu-id="b6a23-118">変換演算子は常に単項であり、定義する演算子として常に `CType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="b6a23-119">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="b6a23-119">Declaration Syntax</span></span>

<span data-ttu-id="b6a23-120">演算子プロシージャを宣言するための構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6a23-120">The syntax for declaring an operator procedure is as follows:</span></span>

```vb
Public Shared [Widening | Narrowing] Operator operatorsymbol ( operand1 [,  operand2 ]) As datatype

' Statements of the operator procedure.

End Operator
```

<span data-ttu-id="b6a23-121">`Widening` または `Narrowing` キーワードは、型変換演算子でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-121">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="b6a23-122">型変換演算子では、演算子記号は常に [CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)です。</span><span class="sxs-lookup"><span data-stu-id="b6a23-122">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>

<span data-ttu-id="b6a23-123">2 項演算子を定義するには、2 つのオペランドを宣言し、型変換演算子を含め、単項演算子を定義するには、1 つのオペランドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-123">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="b6a23-124">すべてのオペランドを `ByVal` で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a23-124">All operands must be declared `ByVal`.</span></span>

<span data-ttu-id="b6a23-125">[Sub プロシージャ](./sub-procedures.md)のパラメーターを宣言する場合と同様に、各オペランドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-125">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="b6a23-126">データの種類</span><span class="sxs-lookup"><span data-stu-id="b6a23-126">Data Type</span></span>

<span data-ttu-id="b6a23-127">定義済みのクラスまたは構造体で演算子を定義するため、オペランドの少なくとも一方は、そのクラスまたは構造体のデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a23-127">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="b6a23-128">型変換演算子の場合、オペランドまたは戻り値の型が、クラスまたは構造体のデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6a23-128">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>

<span data-ttu-id="b6a23-129">詳細については、「[Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b6a23-129">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="b6a23-130">呼び出しの構文</span><span class="sxs-lookup"><span data-stu-id="b6a23-130">Calling Syntax</span></span>

<span data-ttu-id="b6a23-131">演算子プロシージャは、式で演算子記号を使用して暗黙的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-131">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="b6a23-132">事前定義された演算子の場合と同様にオペランドを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-132">You supply the operands the same way you do for predefined operators.</span></span>

<span data-ttu-id="b6a23-133">演算子プロシージャの暗黙的な呼び出しの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6a23-133">The syntax for an implicit call to an operator procedure is as follows:</span></span>

<span data-ttu-id="b6a23-134">`Dim testStruct As`  *構造体名*</span><span class="sxs-lookup"><span data-stu-id="b6a23-134">`Dim testStruct As`  *structurename*</span></span>

<span data-ttu-id="b6a23-135">`Dim testNewStruct As`  *構造体名*  `= testStruct`  *演算子記号*  `10`</span><span class="sxs-lookup"><span data-stu-id="b6a23-135">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="b6a23-136">宣言と呼び出しの実例</span><span class="sxs-lookup"><span data-stu-id="b6a23-136">Illustration of Declaration and Call</span></span>

<span data-ttu-id="b6a23-137">次の構造体は、構成要素の上位および下位の要素として、符号付き 128 ビット整数値を格納します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-137">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="b6a23-138">2 つの `veryLong` 値を加算し、結果の `veryLong` 値を生成する `+` 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="b6a23-138">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>

[!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]

<span data-ttu-id="b6a23-139">次の例は、`veryLong` で定義された `+` 演算子の一般的な呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="b6a23-139">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>

[!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="b6a23-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6a23-140">See also</span></span>

- [<span data-ttu-id="b6a23-141">手順</span><span class="sxs-lookup"><span data-stu-id="b6a23-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b6a23-142">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b6a23-142">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="b6a23-143">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b6a23-143">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="b6a23-144">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b6a23-144">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="b6a23-145">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="b6a23-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b6a23-146">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="b6a23-146">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="b6a23-147">方法: 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="b6a23-147">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="b6a23-148">方法: 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="b6a23-148">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="b6a23-149">方法: 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="b6a23-149">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="b6a23-150">方法: 演算子を定義するクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="b6a23-150">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
