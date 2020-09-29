---
title: '方法: 値を返すプロシージャを作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 3d28162d2a2103477a20b08fc03c937de8b5a475
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071873"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="31093-102">方法: 値を返すプロシージャを作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31093-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>

<span data-ttu-id="31093-103">`Function` プロシージャを使用して、呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="31093-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="31093-104">値を返すプロシージャを作成するには</span><span class="sxs-lookup"><span data-stu-id="31093-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="31093-105">他のプロシージャの外部で、`Function` ステートメントを使用し、その後に `End Function` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="31093-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="31093-106">`Function` ステートメントで、`Function` キーワードの後にプロシージャの名前を指定し、その後にかっこで囲んだパラメーター リストを指定します。</span><span class="sxs-lookup"><span data-stu-id="31093-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="31093-107">かっこの後に `As` 句を入力して、戻り値のデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="31093-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="31093-108">`Function` ステートメントと `End Function` ステートメントの間に、プロシージャのコード ステートメントを配置します。</span><span class="sxs-lookup"><span data-stu-id="31093-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="31093-109">`Return` ステートメントを使用して、呼び出し元のコードに値を返します。</span><span class="sxs-lookup"><span data-stu-id="31093-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="31093-110">次の `Function` プロシージャは、他の 2 つの辺の値を指定して、直角三角形の最も長い辺 (斜辺) を計算します。</span><span class="sxs-lookup"><span data-stu-id="31093-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="31093-111">次の例は、`hypotenuse` の一般的な呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="31093-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="31093-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="31093-112">See also</span></span>

- [<span data-ttu-id="31093-113">手順</span><span class="sxs-lookup"><span data-stu-id="31093-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="31093-114">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="31093-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="31093-115">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="31093-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="31093-116">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="31093-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="31093-117">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="31093-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="31093-118">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="31093-118">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="31093-119">方法: プロシージャから値を返す</span><span class="sxs-lookup"><span data-stu-id="31093-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="31093-120">方法: 値を返すプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="31093-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
