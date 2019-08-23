---
title: Resume ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 884bdaa0c19508b5a6bf6377568a53acc6880518
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957692"
---
# <a name="resume-statement"></a><span data-ttu-id="efea2-102">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="efea2-102">Resume Statement</span></span>
<span data-ttu-id="efea2-103">エラー処理ルーチンが終了した後、実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="efea2-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="efea2-104">構造化例外処理は、構造化されていない例外処理と`On Error` `Resume`ステートメントおよびステートメントを使用するのではなく、可能な限りコードで使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efea2-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="efea2-105">詳細については、[Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efea2-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efea2-106">構文</span><span class="sxs-lookup"><span data-stu-id="efea2-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="efea2-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="efea2-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="efea2-108">必須。</span><span class="sxs-lookup"><span data-stu-id="efea2-108">Required.</span></span> <span data-ttu-id="efea2-109">エラーがエラーハンドラーと同じ手順で発生した場合は、エラーの原因となったステートメントを使用して実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="efea2-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="efea2-110">呼び出されたプロシージャでエラーが発生した場合、エラー処理ルーチンを含むプロシージャから最後に呼び出されたステートメントで実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="efea2-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="efea2-111">任意。</span><span class="sxs-lookup"><span data-stu-id="efea2-111">Optional.</span></span> <span data-ttu-id="efea2-112">エラーハンドラーと同じプロシージャでエラーが発生した場合は、エラーの原因となったステートメントの直後のステートメントを使用して実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="efea2-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="efea2-113">呼び出されたプロシージャでエラーが発生した場合、エラー処理ルーチン (または`On Error Resume Next`ステートメント) を含むプロシージャから最後に呼び出されたステートメントの直後にあるステートメントを使用して、実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="efea2-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="efea2-114">任意。</span><span class="sxs-lookup"><span data-stu-id="efea2-114">Optional.</span></span> <span data-ttu-id="efea2-115">実行は、必要な`line`引数で指定した行で再開されます。</span><span class="sxs-lookup"><span data-stu-id="efea2-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="efea2-116">`line`引数は、行ラベルまたは行番号であり、エラーハンドラーと同じプロシージャ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="efea2-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efea2-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="efea2-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="efea2-118">構造化例外処理は、構造化されていない例外`On Error`処理、および`Resume`ステートメントおよびステートメントを使用するのではなく、可能な限りコードで使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="efea2-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="efea2-119">詳細については、[Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efea2-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="efea2-120">エラー処理ルーチンで`Resume`以外の場所にあるステートメントを使用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="efea2-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="efea2-121">ステートメントは、ステートメントを`Try...Catch...Finally`含むプロシージャ内では使用できません。 `Resume`</span><span class="sxs-lookup"><span data-stu-id="efea2-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efea2-122">例</span><span class="sxs-lookup"><span data-stu-id="efea2-122">Example</span></span>  
 <span data-ttu-id="efea2-123">この例では`Resume` 、ステートメントを使用してプロシージャ内のエラー処理を終了し、エラーの原因となったステートメントを使用して実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="efea2-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="efea2-124">ステートメントの使用方法を示すために、 `Resume`エラー番号55が生成されます。</span><span class="sxs-lookup"><span data-stu-id="efea2-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="efea2-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="efea2-125">Requirements</span></span>  
 <span data-ttu-id="efea2-126">**名前空間:** [Microsoft. Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="efea2-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="efea2-127">**組み立て**Visual Basic ランタイム ライブラリ (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="efea2-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efea2-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="efea2-128">See also</span></span>

- [<span data-ttu-id="efea2-129">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="efea2-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="efea2-130">Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="efea2-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="efea2-131">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="efea2-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
