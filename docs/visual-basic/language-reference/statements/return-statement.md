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
ms.openlocfilehash: cdb58e32c30c8e6c1662fb698ac5576c3f71258c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404201"
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="75d7a-102">Return ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75d7a-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="75d7a-103">`Function`、`Sub`、`Get`、`Set`、または `Operator` プロシージャを呼び出したコードに制御を戻します。</span><span class="sxs-lookup"><span data-stu-id="75d7a-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d7a-104">構文</span><span class="sxs-lookup"><span data-stu-id="75d7a-104">Syntax</span></span>  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="75d7a-105">パーツ</span><span class="sxs-lookup"><span data-stu-id="75d7a-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="75d7a-106">`Function`、`Get`、または `Operator` プロシージャで必要です。</span><span class="sxs-lookup"><span data-stu-id="75d7a-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="75d7a-107">呼び出し元のコードに返される値を表す式。</span><span class="sxs-lookup"><span data-stu-id="75d7a-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75d7a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="75d7a-108">Remarks</span></span>  
 <span data-ttu-id="75d7a-109">`Sub` または `Set` プロシージャでは、`Return` ステートメントは `Exit Sub` または `Exit Property` ステートメントと同じです。`expression` は指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="75d7a-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="75d7a-110">`Function`、`Get`、または `Operator` プロシージャでは、`Return` ステートメントに `expression` を含める必要があります。また、`expression` は、プロシージャの戻り値の型に変換可能なデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="75d7a-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="75d7a-111">`Function` または `Get` プロシージャでは、プロシージャ名に式を代入して戻り値として使用し、`Exit Function` または `Exit Property` ステートメントを実行する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="75d7a-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="75d7a-112">`Operator` プロシージャでは、`Return expression` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75d7a-112">In an `Operator` procedure, you must use `Return expression`.</span></span>  
  
 <span data-ttu-id="75d7a-113">`Return` ステートメントは、必要に応じて同じプロシージャにいくつでも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="75d7a-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75d7a-114">`Finally` ブロック内のコードは、`Try` または `Catch` ブロック内で `Return` ステートメントが検出された後、その `Return` ステートメントが実行される前に実行されます。</span><span class="sxs-lookup"><span data-stu-id="75d7a-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="75d7a-115">`Return` ステートメントを `Finally` ブロックに含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="75d7a-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75d7a-116">例</span><span class="sxs-lookup"><span data-stu-id="75d7a-116">Example</span></span>  
 <span data-ttu-id="75d7a-117">次の例では、`Return` ステートメントを複数回使用して、プロシージャが他の操作を行う必要がない場合に、呼び出し元のコードに戻ります。</span><span class="sxs-lookup"><span data-stu-id="75d7a-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a><span data-ttu-id="75d7a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="75d7a-118">See also</span></span>

- [<span data-ttu-id="75d7a-119">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-119">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="75d7a-120">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-120">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="75d7a-121">Get ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-121">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="75d7a-122">Set ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-122">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="75d7a-123">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-123">Operator Statement</span></span>](operator-statement.md)
- [<span data-ttu-id="75d7a-124">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-124">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="75d7a-125">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-125">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="75d7a-126">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="75d7a-126">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
