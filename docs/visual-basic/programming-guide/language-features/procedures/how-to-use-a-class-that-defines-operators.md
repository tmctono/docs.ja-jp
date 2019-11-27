---
title: '方法: 演算子を定義するクラスを使用する'
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
ms.openlocfilehash: 9ec4b4c07910100dd02cc86e882b44aa7dbd2ced
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346038"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="c71bf-102">方法: 演算子を定義するクラスを使用する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c71bf-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="c71bf-103">独自の演算子を定義するクラスまたは構造体を使用している場合は、Visual Basic からこれらの演算子にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c71bf-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="c71bf-104">クラスまたは構造体に対して演算子を定義することは、演算子の*オーバーロード*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c71bf-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c71bf-105">例</span><span class="sxs-lookup"><span data-stu-id="c71bf-105">Example</span></span>  
 <span data-ttu-id="c71bf-106">次の例では、sql 構造 <xref:System.Data.SqlTypes.SqlString>にアクセスします。これにより、SQL 文字列と Visual Basic 文字列の双方向の変換演算子 ([CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)) が定義されます。</span><span class="sxs-lookup"><span data-stu-id="c71bf-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="c71bf-107">`CType(`*sql 文字列式*、`String)` を使用して sql 文字列を Visual Basic 文字列に変換し、Visual Basic*文字列式*を `CType(`して、他の方向に変換します。<xref:System.Data.SqlTypes.SqlString>`)`</span><span class="sxs-lookup"><span data-stu-id="c71bf-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="c71bf-108"><xref:System.Data.SqlTypes.SqlString> 構造体は、`String` から <xref:System.Data.SqlTypes.SqlString> への変換演算子 (CType 関数) と、<xref:System.Data.SqlTypes.SqlString> から `String`への変換演算子 ([CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)) を定義します。</span><span class="sxs-lookup"><span data-stu-id="c71bf-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="c71bf-109">`jobTitle` に `title` を割り当てるステートメントは、最初の演算子を使用し、<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 関数呼び出しは2番目の演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="c71bf-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c71bf-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c71bf-110">Compiling the Code</span></span>  
 <span data-ttu-id="c71bf-111">使用するクラスまたは構造体で、使用する演算子が定義されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c71bf-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="c71bf-112">クラスまたは構造体で、オーバーロードに使用できるすべての演算子が定義されていると想定しないでください。</span><span class="sxs-lookup"><span data-stu-id="c71bf-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="c71bf-113">使用可能な演算子の一覧については、「 [Operator ステートメント](../../../../visual-basic/language-reference/statements/operator-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c71bf-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="c71bf-114">ソースファイルの先頭にある SQL 文字列に適切な `Imports` ステートメント (この場合は <xref:System.Data.SqlTypes>) を含めます。</span><span class="sxs-lookup"><span data-stu-id="c71bf-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="c71bf-115">プロジェクトは、system.string と SYSTEM.XML への参照を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c71bf-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c71bf-116">参照</span><span class="sxs-lookup"><span data-stu-id="c71bf-116">See also</span></span>

- [<span data-ttu-id="c71bf-117">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c71bf-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="c71bf-118">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="c71bf-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="c71bf-119">方法 : 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="c71bf-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="c71bf-120">方法 : 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="c71bf-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="c71bf-121">Widening</span><span class="sxs-lookup"><span data-stu-id="c71bf-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="c71bf-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="c71bf-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="c71bf-123">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="c71bf-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="c71bf-124">方法 : 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="c71bf-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="c71bf-125">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="c71bf-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="c71bf-126">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="c71bf-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
