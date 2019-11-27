---
title: Return ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: efc85a3a844898345aa2d16926ba0e35d7346d1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333014"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="73a30-102">Return ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73a30-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="73a30-103">`Function`、`Sub`、`Get`、`Set`、または `Operator` プロシージャを呼び出したコードに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="73a30-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73a30-104">構文</span><span class="sxs-lookup"><span data-stu-id="73a30-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="73a30-105">要素</span><span class="sxs-lookup"><span data-stu-id="73a30-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="73a30-106">`Function`、`Get`、または `Operator` プロシージャで必要です。</span><span class="sxs-lookup"><span data-stu-id="73a30-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="73a30-107">呼び出し元のコードに返される値を表す式。</span><span class="sxs-lookup"><span data-stu-id="73a30-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73a30-108">コメント</span><span class="sxs-lookup"><span data-stu-id="73a30-108">Remarks</span></span>  
 <span data-ttu-id="73a30-109">`Sub` または `Set` プロシージャでは、`Return` ステートメントは `Exit Sub` または `Exit Property` ステートメントと同じであり、`expression` を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="73a30-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="73a30-110">`Function`、`Get`、または `Operator` プロシージャでは、`Return` ステートメントに `expression`を含める必要があります。また、`expression` は、プロシージャの戻り値の型に変換可能なデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="73a30-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="73a30-111">`Function` または `Get` の手順では、プロシージャ名に式を代入して戻り値として使用し、`Exit Function` または `Exit Property` ステートメントを実行する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="73a30-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="73a30-112">`Operator` の手順では、`Return expression`を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73a30-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="73a30-113">同じ手順で、必要に応じて `Return` ステートメントをいくつでも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="73a30-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73a30-114">`Finally` ブロック内のコードは、`Try` または `Catch` ブロック内の `Return` ステートメントが検出された後、その `Return` ステートメントが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="73a30-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="73a30-115">`Return` ステートメントを `Finally` ブロックに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="73a30-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73a30-116">例</span><span class="sxs-lookup"><span data-stu-id="73a30-116">Example</span></span>  
 <span data-ttu-id="73a30-117">次の例では、`Return` ステートメントを複数回使用して、プロシージャが他の操作を行う必要がない場合に、呼び出し元のコードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="73a30-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="73a30-118">参照</span><span class="sxs-lookup"><span data-stu-id="73a30-118">See also</span></span>

- [<span data-ttu-id="73a30-119">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="73a30-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="73a30-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="73a30-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="73a30-121">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="73a30-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="73a30-122">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="73a30-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="73a30-123">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="73a30-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="73a30-124">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="73a30-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="73a30-125">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="73a30-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="73a30-126">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="73a30-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
