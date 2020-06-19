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
ms.openlocfilehash: 3f49f05f1deb2027b03bbf3443ca44f30c44344e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404214"
---
# <a name="resume-statement"></a><span data-ttu-id="25bce-102">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="25bce-102">Resume Statement</span></span>
<span data-ttu-id="25bce-103">エラー処理ルーチンが終了した後、実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="25bce-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="25bce-104">コードでは、非構造化例外処理と `On Error` および `Resume` ステートメントを使用するのではなく、可能な限り、構造化例外処理を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="25bce-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="25bce-105">詳しくは、「[Try...Catch...Finally ステートメント](try-catch-finally-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="25bce-105">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25bce-106">構文</span><span class="sxs-lookup"><span data-stu-id="25bce-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="25bce-107">指定項目</span><span class="sxs-lookup"><span data-stu-id="25bce-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="25bce-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="25bce-108">Required.</span></span> <span data-ttu-id="25bce-109">エラー ハンドラーと同じプロシージャでエラーが発生した場合は、エラーの原因となったステートメントを使用して実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="25bce-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="25bce-110">呼び出されたプロシージャでエラーが発生した場合、エラー処理ルーチンを含むプロシージャから最後に呼び出されたステートメントで実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="25bce-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="25bce-111">任意。</span><span class="sxs-lookup"><span data-stu-id="25bce-111">Optional.</span></span> <span data-ttu-id="25bce-112">エラー ハンドラーと同じプロシージャでエラーが発生した場合は、エラーの原因となったステートメントの直後のステートメントを使用して実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="25bce-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="25bce-113">呼び出されたプロシージャでエラーが発生した場合、エラー処理ルーチン (または `On Error Resume Next` ステートメント) を含むプロシージャから最後に呼び出されたステートメントの直後のステートメントを使用して、実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="25bce-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="25bce-114">任意。</span><span class="sxs-lookup"><span data-stu-id="25bce-114">Optional.</span></span> <span data-ttu-id="25bce-115">実行は、必須の引数 `line` で指定した行で再開されます。</span><span class="sxs-lookup"><span data-stu-id="25bce-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="25bce-116">`line` 引数は、行ラベルまたは行番号であり、エラー ハンドラーと同じプロシージャ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="25bce-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25bce-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="25bce-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25bce-118">コードでは、非構造化例外処理と `On Error` および `Resume` ステートメントを使用するのではなく、可能な限り、構造化例外処理を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="25bce-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="25bce-119">詳しくは、「[Try...Catch...Finally ステートメント](try-catch-finally-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="25bce-119">For more information, see [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="25bce-120">エラー処理ルーチン以外の場所で `Resume` ステートメントを使用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="25bce-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="25bce-121">`Resume` ステートメントは、`Try...Catch...Finally` ステートメントを含むプロシージャ内では使用できません。</span><span class="sxs-lookup"><span data-stu-id="25bce-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25bce-122">例</span><span class="sxs-lookup"><span data-stu-id="25bce-122">Example</span></span>  
 <span data-ttu-id="25bce-123">この例では、`Resume` ステートメントを使用してプロシージャのエラー処理を終了し、エラーの原因となったステートメントを使用して実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="25bce-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="25bce-124">`Resume` ステートメントの使用方法を示すために、エラー番号 55 が生成されます。</span><span class="sxs-lookup"><span data-stu-id="25bce-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="25bce-125">必要条件</span><span class="sxs-lookup"><span data-stu-id="25bce-125">Requirements</span></span>  
 <span data-ttu-id="25bce-126">**名前空間:** [Microsoft.VisualBasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="25bce-126">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="25bce-127">**アセンブリ:** Visual Basic ランタイム ライブラリ (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="25bce-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25bce-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="25bce-128">See also</span></span>

- [<span data-ttu-id="25bce-129">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="25bce-129">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="25bce-130">Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="25bce-130">Error Statement</span></span>](error-statement.md)
- [<span data-ttu-id="25bce-131">On Error ステートメント</span><span class="sxs-lookup"><span data-stu-id="25bce-131">On Error Statement</span></span>](on-error-statement.md)
