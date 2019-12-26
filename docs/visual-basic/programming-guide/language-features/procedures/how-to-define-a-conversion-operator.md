---
title: '方法 : 変換演算子を定義する'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344901"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="7b6fc-102">方法: 変換演算子を定義する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b6fc-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="7b6fc-103">クラスまたは構造体を定義している場合は、クラスまたは構造体の型と、別のデータ型 (`Integer`、`Double`、`String`など) の間の型変換演算子を定義できます。</span><span class="sxs-lookup"><span data-stu-id="7b6fc-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="7b6fc-104">クラスまたは構造体内で、型変換を [CType 関数](../../../../visual-basic/language-reference/functions/ctype-function.md)プロシージャとして定義します。</span><span class="sxs-lookup"><span data-stu-id="7b6fc-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="7b6fc-105">すべての変換プロシージャは `Public Shared`である必要があり、それぞれが[拡大](../../../../visual-basic/language-reference/modifiers/widening.md)または[縮小](../../../../visual-basic/language-reference/modifiers/narrowing.md)のどちらかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b6fc-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="7b6fc-106">クラスまたは構造体に対して演算子を定義することは、演算子の*オーバーロード*とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7b6fc-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b6fc-107">例</span><span class="sxs-lookup"><span data-stu-id="7b6fc-107">Example</span></span>  
 <span data-ttu-id="7b6fc-108">次の例では、`digit` という構造体と `Byte`の間の変換演算子を定義します。</span><span class="sxs-lookup"><span data-stu-id="7b6fc-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="7b6fc-109">構造 `digit` をテストするには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b6fc-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="7b6fc-110">参照</span><span class="sxs-lookup"><span data-stu-id="7b6fc-110">See also</span></span>

- [<span data-ttu-id="7b6fc-111">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="7b6fc-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="7b6fc-112">方法 : 演算子を定義する</span><span class="sxs-lookup"><span data-stu-id="7b6fc-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="7b6fc-113">方法 : 演算子プロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="7b6fc-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="7b6fc-114">方法: 演算子を定義するクラスを使用する</span><span class="sxs-lookup"><span data-stu-id="7b6fc-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="7b6fc-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="7b6fc-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="7b6fc-116">Structure ステートメント</span><span class="sxs-lookup"><span data-stu-id="7b6fc-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="7b6fc-117">方法 : 構造体を宣言する</span><span class="sxs-lookup"><span data-stu-id="7b6fc-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="7b6fc-118">暗黙の型変換と明示的な型変換</span><span class="sxs-lookup"><span data-stu-id="7b6fc-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="7b6fc-119">拡大変換と縮小変換</span><span class="sxs-lookup"><span data-stu-id="7b6fc-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
