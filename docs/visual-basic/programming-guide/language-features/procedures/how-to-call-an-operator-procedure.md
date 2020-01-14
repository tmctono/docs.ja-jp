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
ms.openlocfilehash: a977b17d4b2c797bbe38d289a57f3d9d31fa64fa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345967"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="24f44-102">方法: 演算子プロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24f44-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="24f44-103">演算子プロシージャを呼び出すには、式の中で演算子記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="24f44-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="24f44-104">変換演算子の場合は、 [CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)を呼び出して、あるデータ型から別のデータ型に値を変換します。</span><span class="sxs-lookup"><span data-stu-id="24f44-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="24f44-105">演算子プロシージャを明示的に呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="24f44-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="24f44-106">演算子を使用するのは、通常、演算子を使用する場合と同じように、代入ステートメントまたは式で `CType` 関数を使用することだけです。</span><span class="sxs-lookup"><span data-stu-id="24f44-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="24f44-107">Visual Basic は、演算子プロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="24f44-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="24f44-108">クラスまたは構造体に対して演算子を定義することは、演算子の*オーバーロード*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="24f44-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="24f44-109">演算子プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="24f44-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="24f44-110">通常の方法では、演算子記号を式の中で使用します。</span><span class="sxs-lookup"><span data-stu-id="24f44-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="24f44-111">オペランドのデータ型が演算子に適していること、および正しい順序であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24f44-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="24f44-112">演算子は、式の値に想定どおりに貢献します。</span><span class="sxs-lookup"><span data-stu-id="24f44-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="24f44-113">変換演算子プロシージャを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="24f44-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="24f44-114">式の内部で `CType` を使用します。</span><span class="sxs-lookup"><span data-stu-id="24f44-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="24f44-115">オペランドのデータ型が変換に適していること、および正しい順序であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24f44-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="24f44-116">`CType` は変換演算子プロシージャを呼び出し、変換された値を返します。</span><span class="sxs-lookup"><span data-stu-id="24f44-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24f44-117">使用例</span><span class="sxs-lookup"><span data-stu-id="24f44-117">Example</span></span>  
 <span data-ttu-id="24f44-118">次の例では、2つの <xref:System.TimeSpan> 構造体を作成し、それらをまとめて追加し、結果を3番目の <xref:System.TimeSpan> 構造体に格納します。</span><span class="sxs-lookup"><span data-stu-id="24f44-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="24f44-119"><xref:System.TimeSpan> 構造体は、いくつかの標準演算子をオーバーロードする演算子プロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="24f44-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="24f44-120"><xref:System.TimeSpan> は標準の `+` 演算子をオーバーロードするので、前の例では `combinedSpan`の値を計算するときに演算子プロシージャを呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="24f44-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="24f44-121">メッセージ交換演算子プロシージャを呼び出す例については、「[方法: 演算子を定義するクラスを使用する](./how-to-use-a-class-that-defines-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f44-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="24f44-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="24f44-122">Compile the code</span></span>  
 <span data-ttu-id="24f44-123">使用するクラスまたは構造体で、使用する演算子が定義されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24f44-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f44-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="24f44-124">See also</span></span>

- [<span data-ttu-id="24f44-125">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="24f44-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="24f44-126">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="24f44-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="24f44-127">方法 : 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="24f44-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="24f44-128">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="24f44-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="24f44-129">Widening</span><span class="sxs-lookup"><span data-stu-id="24f44-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="24f44-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="24f44-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="24f44-131">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="24f44-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="24f44-132">方法 : 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="24f44-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="24f44-133">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="24f44-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="24f44-134">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="24f44-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
