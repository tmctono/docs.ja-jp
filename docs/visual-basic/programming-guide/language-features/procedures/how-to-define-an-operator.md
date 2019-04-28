---
title: '方法: 定義の演算子 (Visual Basic)'
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
ms.openlocfilehash: 14aa25de78eb357f8474d3828aa45e48e7a4f9c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863846"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="bde2a-102">方法: 定義の演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bde2a-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="bde2a-103">標準の演算子の動作を定義するクラスまたは構造体を定義している場合 (など`*`、 `<>`、または`And`) 1 つまたは両方のオペランドがクラスまたは構造体の型であるとき。</span><span class="sxs-lookup"><span data-stu-id="bde2a-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="bde2a-104">演算子プロシージャ内でクラスまたは構造体として標準の演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="bde2a-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="bde2a-105">演算子のすべてのプロシージャである必要があります`Public``Shared`します。</span><span class="sxs-lookup"><span data-stu-id="bde2a-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="bde2a-106">クラスまたは構造体で演算子を定義が呼び出されますも*オーバー ロード*演算子。</span><span class="sxs-lookup"><span data-stu-id="bde2a-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bde2a-107">例</span><span class="sxs-lookup"><span data-stu-id="bde2a-107">Example</span></span>  
 <span data-ttu-id="bde2a-108">次の例では、定義、`+`構造体の演算子と呼ばれる`height`します。</span><span class="sxs-lookup"><span data-stu-id="bde2a-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="bde2a-109">構造体は、フィートやインチ単位の高さを使用します。</span><span class="sxs-lookup"><span data-stu-id="bde2a-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="bde2a-110">1 つ*インチ*2.54 センチメートル、もう 1 つは、 *foot* 12 インチです。</span><span class="sxs-lookup"><span data-stu-id="bde2a-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="bde2a-111">コンス トラクターを実行する正規化された値 (インチ < 12.0) を確認するには、*剰余*12 の演算です。</span><span class="sxs-lookup"><span data-stu-id="bde2a-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="bde2a-112">`+`演算子では、コンス トラクターを使用して、正規化された値を生成します。</span><span class="sxs-lookup"><span data-stu-id="bde2a-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="bde2a-113">構造体をテストする`height`を次のコード。</span><span class="sxs-lookup"><span data-stu-id="bde2a-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="bde2a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="bde2a-114">See also</span></span>

- [<span data-ttu-id="bde2a-115">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="bde2a-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="bde2a-116">方法: 変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="bde2a-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="bde2a-117">方法: 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="bde2a-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="bde2a-118">方法: 演算子を定義するクラスを使用して、</span><span class="sxs-lookup"><span data-stu-id="bde2a-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="bde2a-119">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="bde2a-119">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="bde2a-120">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="bde2a-120">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="bde2a-121">方法: 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="bde2a-121">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="bde2a-122">Mod 演算子</span><span class="sxs-lookup"><span data-stu-id="bde2a-122">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
