---
title: '方法: 値 (Visual Basic) を返すプロシージャを作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 115c1df4bd49d5848d72c4cbd0242a49a12740c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335499"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="b0b21-102">方法: 値 (Visual Basic) を返すプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0b21-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="b0b21-103">使用する、`Function`プロシージャを呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="b0b21-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="b0b21-104">値を返すプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="b0b21-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="b0b21-105">その他のプロシージャの外側を使用して、`Function`ステートメントの後に、`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="b0b21-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="b0b21-106">`Function`ステートメントでは、以下の`Function`キーワード、プロシージャとし、パラメーター リストをかっこでの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b0b21-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="b0b21-107">かっこの後に、`As`句を戻り値のデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="b0b21-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="b0b21-108">間のプロシージャのコード ステートメントを配置、`Function`と`End Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="b0b21-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="b0b21-109">使用して、`Return`ステートメントを呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="b0b21-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="b0b21-110">次`Function`プロシージャは、最長の辺またはの他の 2 つの辺の値を指定された直角三角形の斜辺を計算します。</span><span class="sxs-lookup"><span data-stu-id="b0b21-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="b0b21-111">次の例では、一般的な呼び出しを`hypotenuse`します。</span><span class="sxs-lookup"><span data-stu-id="b0b21-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b0b21-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0b21-112">See also</span></span>

- [<span data-ttu-id="b0b21-113">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b0b21-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b0b21-114">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b0b21-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="b0b21-115">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b0b21-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="b0b21-116">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="b0b21-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="b0b21-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="b0b21-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b0b21-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="b0b21-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="b0b21-119">方法: プロシージャから値を返す</span><span class="sxs-lookup"><span data-stu-id="b0b21-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="b0b21-120">方法: 値を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="b0b21-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
