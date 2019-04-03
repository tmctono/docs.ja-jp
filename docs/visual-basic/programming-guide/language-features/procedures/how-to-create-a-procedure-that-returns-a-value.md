---
title: '方法: 値 (Visual Basic) を返すプロシージャを作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 88e30caed97938501302c05830df6546a6822a48
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831255"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="b9d50-102">方法: 値 (Visual Basic) を返すプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="b9d50-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="b9d50-103">使用する、`Function`プロシージャを呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="b9d50-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="b9d50-104">値を返すプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="b9d50-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="b9d50-105">その他のプロシージャの外側を使用して、`Function`ステートメントの後に、`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="b9d50-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="b9d50-106">`Function`ステートメントでは、以下の`Function`キーワード、プロシージャとし、パラメーター リストをかっこでの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b9d50-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="b9d50-107">かっこの後に、`As`句を戻り値のデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9d50-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="b9d50-108">間のプロシージャのコード ステートメントを配置、`Function`と`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="b9d50-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="b9d50-109">使用して、`Return`ステートメントを呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="b9d50-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="b9d50-110">次`Function`プロシージャは、最長の辺またはの他の 2 つの辺の値を指定された直角三角形の斜辺を計算します。</span><span class="sxs-lookup"><span data-stu-id="b9d50-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="b9d50-111">次の例では、一般的な呼び出しを`hypotenuse`します。</span><span class="sxs-lookup"><span data-stu-id="b9d50-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b9d50-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9d50-112">See also</span></span>

- [<span data-ttu-id="b9d50-113">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b9d50-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b9d50-114">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b9d50-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="b9d50-115">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b9d50-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="b9d50-116">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b9d50-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="b9d50-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="b9d50-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b9d50-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="b9d50-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="b9d50-119">方法: プロシージャから値を返す</span><span class="sxs-lookup"><span data-stu-id="b9d50-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="b9d50-120">方法: 値を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="b9d50-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
