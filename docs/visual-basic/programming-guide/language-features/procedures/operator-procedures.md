---
title: 演算子プロシージャ (Visual Basic)
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
ms.openlocfilehash: cafc742474d6f7b46fbfb73374a59a350812a2a5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639101"
---
# <a name="operator-procedures-visual-basic"></a><span data-ttu-id="09b11-102">演算子プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09b11-102">Operator Procedures (Visual Basic)</span></span>
<span data-ttu-id="09b11-103">演算子プロシージャは、一連の標準の演算子の動作を定義する Visual Basic ステートメント (など`*`、 `<>`、または`And`) クラスまたは定義した構造にします。</span><span class="sxs-lookup"><span data-stu-id="09b11-103">An operator procedure is a series of Visual Basic statements that define the behavior of a standard operator (such as `*`, `<>`, or `And`) on a class or structure you have defined.</span></span> <span data-ttu-id="09b11-104">これもと呼ばれる*演算子のオーバー ロード*します。</span><span class="sxs-lookup"><span data-stu-id="09b11-104">This is also called *operator overloading*.</span></span>  
  
## <a name="when-to-define-operator-procedures"></a><span data-ttu-id="09b11-105">演算子プロシージャを定義する場合</span><span class="sxs-lookup"><span data-stu-id="09b11-105">When to Define Operator Procedures</span></span>  
 <span data-ttu-id="09b11-106">クラスまたは構造体を定義した場合は、そのクラスまたは構造体の型の変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="09b11-106">When you have defined a class or structure, you can declare variables to be of the type of that class or structure.</span></span> <span data-ttu-id="09b11-107">このような変数は、式の一部として操作に参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09b11-107">Sometimes such a variable needs to participate in an operation as part of an expression.</span></span> <span data-ttu-id="09b11-108">これを行うには、演算子のオペランドがあります。</span><span class="sxs-lookup"><span data-stu-id="09b11-108">To do this, it must be an operand of an operator.</span></span>  
  
 <span data-ttu-id="09b11-109">Visual Basic では、その基本データ型でのみ演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="09b11-109">Visual Basic defines operators only on its fundamental data types.</span></span> <span data-ttu-id="09b11-110">両方のオペランドは、クラスまたは構造体の型または 1 つの場合、演算子の動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="09b11-110">You can define the behavior of an operator when one or both of the operands are of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="09b11-111">詳細については、次を参照してください。 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="09b11-111">For more information, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="types-of-operator-procedure"></a><span data-ttu-id="09b11-112">演算子プロシージャの種類</span><span class="sxs-lookup"><span data-stu-id="09b11-112">Types of Operator Procedure</span></span>  
 <span data-ttu-id="09b11-113">演算子プロシージャには、次の種類のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="09b11-113">An operator procedure can be one of the following types:</span></span>  
  
- <span data-ttu-id="09b11-114">引数が、クラスまたは構造体の型の単項演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="09b11-114">A definition of a unary operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="09b11-115">クラスまたは構造体の型の引数の少なくとも 1 つが二項演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="09b11-115">A definition of a binary operator where at least one of the arguments is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="09b11-116">引数が、クラスまたは構造体の型の変換演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="09b11-116">A definition of a conversion operator where the argument is of the type of your class or structure.</span></span>  
  
- <span data-ttu-id="09b11-117">クラスまたは構造体の型を返す変換演算子の定義。</span><span class="sxs-lookup"><span data-stu-id="09b11-117">A definition of a conversion operator that returns the type of your class or structure.</span></span>  
  
 <span data-ttu-id="09b11-118">変換演算子は、単項では常に、常に使用して`CType`として定義する演算子。</span><span class="sxs-lookup"><span data-stu-id="09b11-118">Conversion operators are always unary, and you always use `CType` as the operator you are defining.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="09b11-119">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="09b11-119">Declaration Syntax</span></span>  
 <span data-ttu-id="09b11-120">演算子プロシージャを宣言する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09b11-120">The syntax for declaring an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="09b11-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="09b11-121">`Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*</span></span>  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 <span data-ttu-id="09b11-122">使用する、`Widening`または`Narrowing`型変換演算子でのみキーワード。</span><span class="sxs-lookup"><span data-stu-id="09b11-122">You use the `Widening` or `Narrowing` keyword only on a type conversion operator.</span></span> <span data-ttu-id="09b11-123">演算子記号は常に[CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)型変換演算子。</span><span class="sxs-lookup"><span data-stu-id="09b11-123">The operator symbol is always [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) for a type conversion operator.</span></span>  
  
 <span data-ttu-id="09b11-124">二項の演算子を定義する 2 つのオペランドを宣言して、型変換演算子を含む、単項演算子を定義する 1 つのオペランドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="09b11-124">You declare two operands to define a binary operator, and you declare one operand to define a unary operator, including a type conversion operator.</span></span> <span data-ttu-id="09b11-125">すべてのオペランドを宣言する必要があります`ByVal`します。</span><span class="sxs-lookup"><span data-stu-id="09b11-125">All operands must be declared `ByVal`.</span></span>  
  
 <span data-ttu-id="09b11-126">各オペランドを宣言すると、同様のパラメーターを宣言する[Sub プロシージャ](./sub-procedures.md)します。</span><span class="sxs-lookup"><span data-stu-id="09b11-126">You declare each operand the same way you declare parameters for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="09b11-127">データの種類</span><span class="sxs-lookup"><span data-stu-id="09b11-127">Data Type</span></span>  
 <span data-ttu-id="09b11-128">クラスまたは定義した構造体で演算子を定義しているため、そのクラスまたは構造体のデータ型のオペランドの少なくとも 1 つがあります。</span><span class="sxs-lookup"><span data-stu-id="09b11-128">Because you are defining an operator on a class or structure you have defined, at least one of the operands must be of the data type of that class or structure.</span></span> <span data-ttu-id="09b11-129">型の変換演算子のオペランドまたは戻り値の型がクラスまたは構造体のデータ型でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="09b11-129">For a type conversion operator, either the operand or the return type must be of the data type of the class or structure.</span></span>  
  
 <span data-ttu-id="09b11-130">詳細については、次を参照してください。 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="09b11-130">For more details, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="09b11-131">呼び出し構文</span><span class="sxs-lookup"><span data-stu-id="09b11-131">Calling Syntax</span></span>  
 <span data-ttu-id="09b11-132">演算子プロシージャは、式の中で演算子記号を使用して暗黙的を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="09b11-132">You invoke an operator procedure implicitly by using the operator symbol in an expression.</span></span> <span data-ttu-id="09b11-133">定義済みの演算子のと同じ方法で、オペランドを指定します。</span><span class="sxs-lookup"><span data-stu-id="09b11-133">You supply the operands the same way you do for predefined operators.</span></span>  
  
 <span data-ttu-id="09b11-134">演算子プロシージャへの暗黙の呼び出しの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09b11-134">The syntax for an implicit call to an operator procedure is as follows:</span></span>  
  
 <span data-ttu-id="09b11-135">`Dim testStruct As`  *structurename*</span><span class="sxs-lookup"><span data-stu-id="09b11-135">`Dim testStruct As`  *structurename*</span></span>  
  
 <span data-ttu-id="09b11-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span><span class="sxs-lookup"><span data-stu-id="09b11-136">`Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="09b11-137">宣言と呼び出しの図</span><span class="sxs-lookup"><span data-stu-id="09b11-137">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="09b11-138">次の構造は、構成の上位と下位の要素として 128 ビットの符号付き整数値を格納します。</span><span class="sxs-lookup"><span data-stu-id="09b11-138">The following structure stores a signed 128-bit integer value as the constituent high-order and low-order parts.</span></span> <span data-ttu-id="09b11-139">定義、`+`演算子を 2 つ`veryLong`値し、その結果を生成`veryLong`値。</span><span class="sxs-lookup"><span data-stu-id="09b11-139">It defines the `+` operator to add two `veryLong` values and generate a resulting `veryLong` value.</span></span>  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 <span data-ttu-id="09b11-140">次の例では、一般的な呼び出しを`+`で定義されたオペレーター`veryLong`します。</span><span class="sxs-lookup"><span data-stu-id="09b11-140">The following example shows a typical call to the `+` operator defined on `veryLong`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a><span data-ttu-id="09b11-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="09b11-141">See also</span></span>

- [<span data-ttu-id="09b11-142">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="09b11-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="09b11-143">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="09b11-143">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="09b11-144">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="09b11-144">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="09b11-145">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="09b11-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="09b11-146">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="09b11-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="09b11-147">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="09b11-147">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="09b11-148">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="09b11-148">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="09b11-149">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="09b11-149">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="09b11-150">方法: 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="09b11-150">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="09b11-151">方法: 演算子を定義するクラスを使用して、</span><span class="sxs-lookup"><span data-stu-id="09b11-151">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
