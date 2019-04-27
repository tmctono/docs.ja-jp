---
title: '方法: 演算子 (Visual Basic) を定義するクラスを使用して、'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: bd512adf2f06ed0fbd3d36ed3175a0928bf1c57c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863494"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="f01b2-102">方法: 演算子 (Visual Basic) を定義するクラスを使用して、</span><span class="sxs-lookup"><span data-stu-id="f01b2-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="f01b2-103">クラスまたは独自の演算子を定義する構造体を使用している場合は、これらの演算子を Visual Basic からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f01b2-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="f01b2-104">クラスまたは構造体で演算子を定義が呼び出されますも*オーバー ロード*演算子。</span><span class="sxs-lookup"><span data-stu-id="f01b2-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f01b2-105">例</span><span class="sxs-lookup"><span data-stu-id="f01b2-105">Example</span></span>  
 <span data-ttu-id="f01b2-106">次の例では、SQL 構造<xref:System.Data.SqlTypes.SqlString>、変換演算子を定義する ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) SQL 文字列および Visual Basic の文字列間の双方向でします。</span><span class="sxs-lookup"><span data-stu-id="f01b2-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="f01b2-107">使用`CType(` *SQL 文字列式*、 `String)` SQL 文字列を Visual Basic の文字列に変換して`CType(` *Visual Basic の文字列式*、 <xref:System.Data.SqlTypes.SqlString> `)`に他の方向に変換します。</span><span class="sxs-lookup"><span data-stu-id="f01b2-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="f01b2-108"><xref:System.Data.SqlTypes.SqlString>構造体には、変換演算子が定義されています ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) から`String`に<xref:System.Data.SqlTypes.SqlString>とから<xref:System.Data.SqlTypes.SqlString>に`String`します。</span><span class="sxs-lookup"><span data-stu-id="f01b2-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="f01b2-109">代入するステートメント`title`に`jobTitle`の最初の演算子を使用し、<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>関数呼び出し、2 つ目の使用します。</span><span class="sxs-lookup"><span data-stu-id="f01b2-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f01b2-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f01b2-110">Compiling the Code</span></span>  
 <span data-ttu-id="f01b2-111">必ず、クラスまたは構造体を使用しているが、使用する演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="f01b2-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="f01b2-112">クラスまたは構造体の定義がすべての演算子はオーバー ロード可能なことを前提としてはいません。</span><span class="sxs-lookup"><span data-stu-id="f01b2-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="f01b2-113">利用可能な演算子の一覧は、次を参照してください。 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="f01b2-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="f01b2-114">含める、適切な`Imports`ソース ファイルの先頭にある SQL 文字列の文 (ここで<xref:System.Data.SqlTypes>)。</span><span class="sxs-lookup"><span data-stu-id="f01b2-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="f01b2-115">プロジェクトは、System.Data および System.XML への参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="f01b2-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01b2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f01b2-116">See also</span></span>

- [<span data-ttu-id="f01b2-117">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f01b2-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f01b2-118">方法: 演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="f01b2-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="f01b2-119">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="f01b2-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="f01b2-120">方法: 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="f01b2-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="f01b2-121">Widening</span><span class="sxs-lookup"><span data-stu-id="f01b2-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="f01b2-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="f01b2-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="f01b2-123">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="f01b2-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f01b2-124">方法: 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="f01b2-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="f01b2-125">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="f01b2-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="f01b2-126">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="f01b2-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
