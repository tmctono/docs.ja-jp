---
title: Resume ステートメント
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
ms.openlocfilehash: 95137a9f6a4a4a18655b51b95300bfaf93cca193
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333029"
---
# <a name="resume-statement"></a><span data-ttu-id="ee448-102">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="ee448-102">Resume Statement</span></span>
<span data-ttu-id="ee448-103">Resumes execution after an error-handling routine is finished.</span><span class="sxs-lookup"><span data-stu-id="ee448-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="ee448-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span><span class="sxs-lookup"><span data-stu-id="ee448-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="ee448-105">詳しくは、「[Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ee448-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee448-106">構文</span><span class="sxs-lookup"><span data-stu-id="ee448-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ee448-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="ee448-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="ee448-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="ee448-108">Required.</span></span> <span data-ttu-id="ee448-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span><span class="sxs-lookup"><span data-stu-id="ee448-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="ee448-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span><span class="sxs-lookup"><span data-stu-id="ee448-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="ee448-111">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ee448-111">Optional.</span></span> <span data-ttu-id="ee448-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span><span class="sxs-lookup"><span data-stu-id="ee448-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="ee448-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span><span class="sxs-lookup"><span data-stu-id="ee448-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="ee448-114">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ee448-114">Optional.</span></span> <span data-ttu-id="ee448-115">Execution resumes at the line specified in the required `line` argument.</span><span class="sxs-lookup"><span data-stu-id="ee448-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="ee448-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span><span class="sxs-lookup"><span data-stu-id="ee448-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee448-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="ee448-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee448-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span><span class="sxs-lookup"><span data-stu-id="ee448-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="ee448-119">詳しくは、「[Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ee448-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="ee448-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span><span class="sxs-lookup"><span data-stu-id="ee448-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="ee448-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span><span class="sxs-lookup"><span data-stu-id="ee448-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee448-122">例</span><span class="sxs-lookup"><span data-stu-id="ee448-122">Example</span></span>  
 <span data-ttu-id="ee448-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span><span class="sxs-lookup"><span data-stu-id="ee448-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="ee448-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span><span class="sxs-lookup"><span data-stu-id="ee448-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="ee448-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="ee448-125">Requirements</span></span>  
 <span data-ttu-id="ee448-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="ee448-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="ee448-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="ee448-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee448-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee448-128">See also</span></span>

- [<span data-ttu-id="ee448-129">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="ee448-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="ee448-130">Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="ee448-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="ee448-131">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="ee448-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
