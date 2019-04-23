---
title: '方法: 演算子プロシージャ (Visual Basic) を呼び出す'
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
ms.openlocfilehash: d68781aa12ab7c1c717031ca252c5f3120649edc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335486"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="27191-102">方法: 演算子プロシージャ (Visual Basic) を呼び出す</span><span class="sxs-lookup"><span data-stu-id="27191-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="27191-103">演算子プロシージャを呼び出すには、式で演算子記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="27191-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="27191-104">場合は、変換演算子を呼び出す、 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)に値を別の 1 つのデータ型に変換します。</span><span class="sxs-lookup"><span data-stu-id="27191-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="27191-105">演算子プロシージャを明示的に呼び出すことはありません。</span><span class="sxs-lookup"><span data-stu-id="27191-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="27191-106">同様に、演算子を使用する、または`CType`代入ステートメントまたは式、演算子に通常使用する同じ方法での関数。</span><span class="sxs-lookup"><span data-stu-id="27191-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="27191-107">Visual Basic では、演算子プロシージャ呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="27191-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="27191-108">クラスまたは構造体で演算子を定義が呼び出されますも*オーバー ロード*演算子。</span><span class="sxs-lookup"><span data-stu-id="27191-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="27191-109">演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="27191-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="27191-110">通常の方法で、式の中で演算子記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="27191-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="27191-111">オペランドのデータ型が演算子の場合、正しい順序で適切なであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27191-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="27191-112">演算子は、期待どおりに、式の値に作用します。</span><span class="sxs-lookup"><span data-stu-id="27191-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="27191-113">変換演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="27191-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="27191-114">使用`CType`式の内部。</span><span class="sxs-lookup"><span data-stu-id="27191-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="27191-115">オペランドのデータ型は、変換して、正しい順序で適切なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="27191-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="27191-116">`CType` 変換演算子プロシージャを呼び出し、変換後の値を返します。</span><span class="sxs-lookup"><span data-stu-id="27191-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27191-117">例</span><span class="sxs-lookup"><span data-stu-id="27191-117">Example</span></span>  
 <span data-ttu-id="27191-118">次の例では、2 つ作成されます<xref:System.TimeSpan>構造体を一緒に追加し、3 つ目の結果を格納<xref:System.TimeSpan>構造体。</span><span class="sxs-lookup"><span data-stu-id="27191-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="27191-119"><xref:System.TimeSpan>構造がいくつかの標準的な演算子をオーバー ロードする演算子プロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="27191-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="27191-120"><xref:System.TimeSpan> 、標準のオーバー ロード`+`演算子を前の例では演算子プロシージャの値を計算するとき`combinedSpan`します。</span><span class="sxs-lookup"><span data-stu-id="27191-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="27191-121">メッセージ交換演算子プロシージャの呼び出しの例は、次を参照してください。[方法。演算子を定義するクラスを使用して](./how-to-use-a-class-that-defines-operators.md)します。</span><span class="sxs-lookup"><span data-stu-id="27191-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="27191-122">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="27191-122">Compiling the Code</span></span>  
 <span data-ttu-id="27191-123">必ず、クラスまたは構造体を使用しているが、使用する演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="27191-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27191-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="27191-124">See also</span></span>

- [<span data-ttu-id="27191-125">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="27191-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="27191-126">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="27191-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="27191-127">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="27191-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="27191-128">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="27191-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="27191-129">Widening</span><span class="sxs-lookup"><span data-stu-id="27191-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="27191-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="27191-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="27191-131">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="27191-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="27191-132">方法: 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="27191-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="27191-133">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="27191-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="27191-134">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="27191-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
