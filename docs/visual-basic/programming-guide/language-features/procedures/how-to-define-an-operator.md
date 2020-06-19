---
title: '方法: 演算子を定義する'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 49b9c8d1a6db56a56b50c16b4a6bb5b928df6c7d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388038"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="3bc04-102">方法: 演算子を定義する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bc04-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="3bc04-103">クラスまたは構造体を定義している場合、一方または両方のオペランドがクラスまたは構造体の型である場合の標準演算子 (`*`、`<>`、または `And` など) の動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3bc04-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="3bc04-104">標準演算子をクラスまたは構造体内の演算子プロシージャとして定義します。</span><span class="sxs-lookup"><span data-stu-id="3bc04-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="3bc04-105">すべての演算子プロシージャは、`Public` `Shared` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bc04-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="3bc04-106">クラスまたは構造体での演算子の定義は、演算子の "*オーバーロード*" とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3bc04-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bc04-107">例</span><span class="sxs-lookup"><span data-stu-id="3bc04-107">Example</span></span>  
 <span data-ttu-id="3bc04-108">次の例では、`height` という構造体の `+` 演算子を定義しています。</span><span class="sxs-lookup"><span data-stu-id="3bc04-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="3bc04-109">この構造体では、フィートとインチで計測された高さを使用します。</span><span class="sxs-lookup"><span data-stu-id="3bc04-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="3bc04-110">1 "*インチ*" は 2.54 センチメートルであり、1 "*フィート*" は 12 インチです。</span><span class="sxs-lookup"><span data-stu-id="3bc04-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="3bc04-111">正規化された値 (インチ < 12.0) を確保するために、コンストラクターでは "*剰余*" 12 演算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3bc04-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="3bc04-112">`+` 演算子では、コンストラクターを使用して正規化された値が生成されます。</span><span class="sxs-lookup"><span data-stu-id="3bc04-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="3bc04-113">次のコードで構造体 `height` をテストできます。</span><span class="sxs-lookup"><span data-stu-id="3bc04-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="3bc04-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bc04-114">See also</span></span>

- [<span data-ttu-id="3bc04-115">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="3bc04-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="3bc04-116">方法: 変換演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="3bc04-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="3bc04-117">方法: 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="3bc04-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="3bc04-118">方法: 演算子を定義するクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="3bc04-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="3bc04-119">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="3bc04-119">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3bc04-120">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="3bc04-120">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="3bc04-121">方法: 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="3bc04-121">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="3bc04-122">Mod 演算子</span><span class="sxs-lookup"><span data-stu-id="3bc04-122">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)
