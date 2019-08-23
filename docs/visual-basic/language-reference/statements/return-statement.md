---
title: Return ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957672"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="3d754-102">Return ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d754-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="3d754-103">`Function` 、`Sub`、、、または`Operator`プロシージャを呼び出したコードに制御を返します。 `Set` `Get`</span><span class="sxs-lookup"><span data-stu-id="3d754-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d754-104">構文</span><span class="sxs-lookup"><span data-stu-id="3d754-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="3d754-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="3d754-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="3d754-106">`Function` 、`Get`、または`Operator`プロシージャで必要です。</span><span class="sxs-lookup"><span data-stu-id="3d754-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="3d754-107">呼び出し元のコードに返される値を表す式。</span><span class="sxs-lookup"><span data-stu-id="3d754-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d754-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d754-108">Remarks</span></span>  
 <span data-ttu-id="3d754-109">`Exit Sub` `Exit Property`または`Set`プロシージャ`expression`では、ステートメントはまたはステートメントと同じであり、指定することはできません。`Return` `Sub`</span><span class="sxs-lookup"><span data-stu-id="3d754-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="3d754-110">`Function` `expression`、 、また`Operator`はプロシージャでは、ステートメントにを含め、プロシージャの戻り値の型に変換可能なデータ型に評価する必要があります。`expression` `Return` `Get`</span><span class="sxs-lookup"><span data-stu-id="3d754-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="3d754-111">または`Get`プロシージャでは、プロシージャ名に式を代入して戻り値として使用し、ステートメント`Exit Function`または`Exit Property`ステートメントを実行する方法もあります。 `Function`</span><span class="sxs-lookup"><span data-stu-id="3d754-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="3d754-112">プロシージャでは、を使用`Return expression`する必要があります。 `Operator`</span><span class="sxs-lookup"><span data-stu-id="3d754-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="3d754-113">同じ手順で、必要`Return`な数だけステートメントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3d754-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d754-114">`Finally`ブロック内のコードは、 `Try`または`Return` `Catch`ブロック内のステートメントが検出された後、 `Return`そのステートメントが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="3d754-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="3d754-115">ステートメント`Return`を`Finally`ブロックに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="3d754-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d754-116">例</span><span class="sxs-lookup"><span data-stu-id="3d754-116">Example</span></span>  
 <span data-ttu-id="3d754-117">次の例では`Return` 、ステートメントを複数回使用して、プロシージャが他の操作を行う必要がない場合に、呼び出し元のコードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="3d754-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="3d754-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d754-118">See also</span></span>

- [<span data-ttu-id="3d754-119">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="3d754-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="3d754-121">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="3d754-122">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="3d754-123">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="3d754-124">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="3d754-125">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="3d754-126">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="3d754-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
