---
title: On Error ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OnError
helpviewer_keywords:
- Visual Basic code, control flow
- Resume Next statement [Visual Basic]
- errors [Visual Basic], trapping
- error handling, On Error statement
- Next statement [Visual Basic], On Error
- control flow [Visual Basic], branching
- Error keyword [Visual Basic]
- execution [Visual Basic], conditional
- Resume statement [Visual Basic], and On Error statement
- Error statement [Visual Basic], and On Error statement
- GoTo statement [Visual Basic], and On Error statement
- branching [Visual Basic], on error
- conditional statements [Visual Basic], On Error
- On Error statement [Visual Basic], syntax
- On keyword [Visual Basic]
- run-time errors [Visual Basic], handling
- On Error statement [Visual Basic]
ms.assetid: ff947930-fb84-40cf-bd66-1ea219561d5c
ms.openlocfilehash: 0a5a5261e6b71178adce02a5635c1f91a1469f3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784073"
---
# <a name="on-error-statement-visual-basic"></a><span data-ttu-id="2df82-102">On Error ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2df82-102">On Error Statement (Visual Basic)</span></span>
<span data-ttu-id="2df82-103">エラー処理ルーチンを有効にして、プロシージャ内のルーチンの場所を指定しますエラー処理ルーチンを無効にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2df82-103">Enables an error-handling routine and specifies the location of the routine within a procedure; can also be used to disable an error-handling routine.</span></span>  
  
 <span data-ttu-id="2df82-104">実行時に発生するエラーは致命的なエラー処理がない: エラー メッセージが表示され、実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="2df82-104">Without error handling, any run-time error that occurs is fatal: an error message is displayed, and execution stops.</span></span>  
  
 <span data-ttu-id="2df82-105">非構造化例外処理を使用するのではなく、コードで、処理、構造化例外の使用をお勧め可能であれば、および`On Error`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2df82-105">Whenever possible, we suggest you use structured exception handling in your code, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="2df82-106">詳細については、[Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2df82-106">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df82-107">`Error`キーワードでも使用、 [Error ステートメント](../../../visual-basic/language-reference/statements/error-statement.md)、旧バージョンとの互換性のためサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2df82-107">The `Error` keyword is also used in the [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md), which is supported for backward compatibility.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df82-108">構文</span><span class="sxs-lookup"><span data-stu-id="2df82-108">Syntax</span></span>  
  
```  
On Error { GoTo [ line | 0 | -1 ] | Resume Next }  
```  
  
## <a name="parts"></a><span data-ttu-id="2df82-109">指定項目</span><span class="sxs-lookup"><span data-stu-id="2df82-109">Parts</span></span>  
  
|<span data-ttu-id="2df82-110">用語</span><span class="sxs-lookup"><span data-stu-id="2df82-110">Term</span></span>|<span data-ttu-id="2df82-111">定義</span><span class="sxs-lookup"><span data-stu-id="2df82-111">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2df82-112">`GoTo` `line`</span><span class="sxs-lookup"><span data-stu-id="2df82-112">`GoTo` `line`</span></span>|<span data-ttu-id="2df82-113">により、エラー処理ルーチンで必要な指定した行から始まる`line`引数。</span><span class="sxs-lookup"><span data-stu-id="2df82-113">Enables the error-handling routine that starts at the line specified in the required `line` argument.</span></span> <span data-ttu-id="2df82-114">`line`引数が任意の行のラベルまたは行番号。</span><span class="sxs-lookup"><span data-stu-id="2df82-114">The `line` argument is any line label or line number.</span></span> <span data-ttu-id="2df82-115">実行時エラーが発生した場合は、エラー ハンドラーをアクティブにする際、指定した行に分岐を制御します。</span><span class="sxs-lookup"><span data-stu-id="2df82-115">If a run-time error occurs, control branches to the specified line, making the error handler active.</span></span> <span data-ttu-id="2df82-116">指定した行と同じ手順である必要があります、`On Error`ステートメント、または、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2df82-116">The specified line must be in the same procedure as the `On Error` statement, or a compile-time error will occur.</span></span>|  
|<span data-ttu-id="2df82-117">`GoTo` 0</span><span class="sxs-lookup"><span data-stu-id="2df82-117">`GoTo` 0</span></span>|<span data-ttu-id="2df82-118">現在のプロシージャで有効になっているエラー ハンドラーを無効にし、リセット`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="2df82-118">Disables enabled error handler in the current procedure and resets it to `Nothing`.</span></span>|  
|<span data-ttu-id="2df82-119">`GoTo` -1</span><span class="sxs-lookup"><span data-stu-id="2df82-119">`GoTo` -1</span></span>|<span data-ttu-id="2df82-120">現在のプロシージャで有効になっている例外を無効にし、リセット`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="2df82-120">Disables enabled exception in the current procedure and resets it to `Nothing`.</span></span>|  
|`Resume Next`|<span data-ttu-id="2df82-121">実行時エラーが発生したときに、エラーが発生したし、そのポイントから実行が継続のステートメントの直後のステートメントにコントロールが移動を指定します。</span><span class="sxs-lookup"><span data-stu-id="2df82-121">Specifies that when a run-time error occurs, control goes to the statement immediately following the statement where the error occurred, and execution continues from that point.</span></span> <span data-ttu-id="2df82-122">このフォームを使用してなく`On Error GoTo`オブジェクトにアクセスするときにします。</span><span class="sxs-lookup"><span data-stu-id="2df82-122">Use this form rather than `On Error GoTo` when accessing objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2df82-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="2df82-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df82-124">非構造化例外処理を使用するのではなく、可能であれば、コード内の構造化例外処理を使用することをお勧め、`On Error`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2df82-124">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="2df82-125">詳細については、[Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2df82-125">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="2df82-126">"Enabled"のエラー ハンドラーは、いずれかで有効になっている、`On Error`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2df82-126">An "enabled" error handler is one that is turned on by an `On Error` statement.</span></span> <span data-ttu-id="2df82-127">「アクティブ」のエラー ハンドラーは、エラーを処理するプロセスでは有効なハンドラーです。</span><span class="sxs-lookup"><span data-stu-id="2df82-127">An "active" error handler is an enabled handler that is in the process of handling an error.</span></span>  
  
 <span data-ttu-id="2df82-128">エラー ハンドラーがアクティブな間にエラーが発生したかどうか (エラーの発生間と`Resume`、 `Exit Sub`、 `Exit Function`、または`Exit Property`ステートメント)、現在のプロシージャのエラー ハンドラーは、エラーを処理できません。</span><span class="sxs-lookup"><span data-stu-id="2df82-128">If an error occurs while an error handler is active (between the occurrence of the error and a `Resume`, `Exit Sub`, `Exit Function`, or `Exit Property` statement), the current procedure's error handler cannot handle the error.</span></span> <span data-ttu-id="2df82-129">呼び出し元のプロシージャに制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="2df82-129">Control returns to the calling procedure.</span></span>  
  
 <span data-ttu-id="2df82-130">呼び出し元のプロシージャに有効になっているエラー ハンドラーがある場合は、エラーを処理するためにアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="2df82-130">If the calling procedure has an enabled error handler, it is activated to handle the error.</span></span> <span data-ttu-id="2df82-131">呼び出し元のプロシージャのエラー ハンドラーもアクティブな場合は、コントロールは、有効であっても、非アクティブなエラー ハンドラーが見つかるまで呼び出し元の前の手順を遡ってに渡します。</span><span class="sxs-lookup"><span data-stu-id="2df82-131">If the calling procedure's error handler is also active, control passes back through previous calling procedures until an enabled, but inactive, error handler is found.</span></span> <span data-ttu-id="2df82-132">このようなエラー ハンドラーが見つからない場合は、エラーが、実際に発生した時点で致命的です。</span><span class="sxs-lookup"><span data-stu-id="2df82-132">If no such error handler is found, the error is fatal at the point at which it actually occurred.</span></span>  
  
 <span data-ttu-id="2df82-133">エラー ハンドラーは、呼び出し元のプロシージャにコントロールを通過するたびにそのプロシージャには、現在のプロシージャになります。</span><span class="sxs-lookup"><span data-stu-id="2df82-133">Each time the error handler passes control back to a calling procedure, that procedure becomes the current procedure.</span></span> <span data-ttu-id="2df82-134">指定された位置から現在のプロシージャの実行が再開されているいずれかのプロシージャのエラー ハンドラーによってエラーが処理されたら、`Resume`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2df82-134">Once an error is handled by an error handler in any procedure, execution resumes in the current procedure at the point designated by the `Resume` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df82-135">エラー処理ルーチンは、`Sub`プロシージャまたは`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="2df82-135">An error-handling routine is not a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="2df82-136">これは、行ラベルまたは行番号でマークされたコードのセクションです。</span><span class="sxs-lookup"><span data-stu-id="2df82-136">It is a section of code marked by a line label or a line number.</span></span>  
  
## <a name="number-property"></a><span data-ttu-id="2df82-137">Number プロパティ</span><span class="sxs-lookup"><span data-stu-id="2df82-137">Number Property</span></span>  
 <span data-ttu-id="2df82-138">エラー処理ルーチンで値を使用して、`Number`のプロパティ、`Err`エラーの原因を特定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="2df82-138">Error-handling routines rely on the value in the `Number` property of the `Err` object to determine the cause of the error.</span></span> <span data-ttu-id="2df82-139">ルーチンのテストまたはで関連するプロパティの値を保存する必要があります、`Err`前に、その他のエラーが発生する可能性がまたは可能性がある手順の前にエラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2df82-139">The routine should test or save relevant property values in the `Err` object before any other error can occur or before a procedure that might cause an error is called.</span></span> <span data-ttu-id="2df82-140">プロパティの値で、`Err`オブジェクトは、最新のエラーのみを反映します。</span><span class="sxs-lookup"><span data-stu-id="2df82-140">The property values in the `Err` object reflect only the most recent error.</span></span> <span data-ttu-id="2df82-141">エラー メッセージに関連付けられている`Err.Number`に含まれている`Err.Description`します。</span><span class="sxs-lookup"><span data-stu-id="2df82-141">The error message associated with `Err.Number` is contained in `Err.Description`.</span></span>  
  
## <a name="throw-statement"></a><span data-ttu-id="2df82-142">Throw ステートメント</span><span class="sxs-lookup"><span data-stu-id="2df82-142">Throw Statement</span></span>  
 <span data-ttu-id="2df82-143">エラーが発生しますが、`Err.Raise`メソッドのセット、`Exception`プロパティの新しく作成されたインスタンスを<xref:System.Exception>クラス。</span><span class="sxs-lookup"><span data-stu-id="2df82-143">An error that is raised with the `Err.Raise` method sets the `Exception` property to a newly created instance of the <xref:System.Exception> class.</span></span> <span data-ttu-id="2df82-144">派生した例外の種類の例外の発生をサポートするために、`Throw`言語でステートメントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2df82-144">In order to support the raising of exceptions of derived exception types, a `Throw` statement is supported in the language.</span></span> <span data-ttu-id="2df82-145">これがスローされる例外のインスタンスでは 1 つのパラメーターを取ります。</span><span class="sxs-lookup"><span data-stu-id="2df82-145">This takes a single parameter that is the exception instance to be thrown.</span></span> <span data-ttu-id="2df82-146">次の例では、これらの機能を使用して、既存の例外処理のサポートを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2df82-146">The following example shows how these features can be used with the existing exception handling support:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 <span data-ttu-id="2df82-147">なお、`On Error GoTo`ステートメントは、例外クラスに関係なく、すべてのエラーをトラップします。</span><span class="sxs-lookup"><span data-stu-id="2df82-147">Notice that the `On Error GoTo` statement traps all errors, regardless of the exception class.</span></span>  
  
## <a name="on-error-resume-next"></a><span data-ttu-id="2df82-148">次に on Error Resume</span><span class="sxs-lookup"><span data-stu-id="2df82-148">On Error Resume Next</span></span>  
 <span data-ttu-id="2df82-149">`On Error Resume Next` 実行、実行時エラーの原因となったステートメントの直後のステートメントを続行または最新の直後に続くステートメントを使用して、プロシージャを含む外呼び出しを`On Error Resume Next`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="2df82-149">`On Error Resume Next` causes execution to continue with the statement immediately following the statement that caused the run-time error, or with the statement immediately following the most recent call out of the procedure containing the `On Error Resume Next` statement.</span></span> <span data-ttu-id="2df82-150">このステートメントでは、実行、実行時エラーに関係なく続行をできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2df82-150">This statement allows execution to continue despite a run-time error.</span></span> <span data-ttu-id="2df82-151">プロシージャ内の別の場所に制御を転送するのではなく、エラーが発生するか、エラー処理ルーチンを配置することができます。</span><span class="sxs-lookup"><span data-stu-id="2df82-151">You can place the error-handling routine where the error would occur rather than transferring control to another location within the procedure.</span></span> <span data-ttu-id="2df82-152">`On Error Resume Next`ステートメントになり、使用頻度の低い別のプロシージャが呼び出されたときに実行する必要があります、`On Error Resume Next`インライン エラーのルーチン内で処理する場合、各ステートメントがルーチンを呼び出すとします。</span><span class="sxs-lookup"><span data-stu-id="2df82-152">An `On Error Resume Next` statement becomes inactive when another procedure is called, so you should execute an `On Error Resume Next` statement in each called routine if you want inline error handling within that routine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2df82-153">`On Error Resume Next`コンストラクトことをお勧めする`On Error GoTo`他のオブジェクトへのアクセス中にエラーを処理するときにします。</span><span class="sxs-lookup"><span data-stu-id="2df82-153">The `On Error Resume Next` construct may be preferable to `On Error GoTo` when handling errors generated during access to other objects.</span></span> <span data-ttu-id="2df82-154">チェック`Err`オブジェクトと対話は、コードによってアクセスされたオブジェクトがあいまいさを削除します。</span><span class="sxs-lookup"><span data-stu-id="2df82-154">Checking `Err` after each interaction with an object removes ambiguity about which object was accessed by the code.</span></span> <span data-ttu-id="2df82-155">確認するオブジェクトのエラー コードを配置する`Err.Number`、どのオブジェクトが最初に、エラーを生成および (で指定されたオブジェクト`Err.Source`)。</span><span class="sxs-lookup"><span data-stu-id="2df82-155">You can be sure which object placed the error code in `Err.Number`, as well as which object originally generated the error (the object specified in `Err.Source`).</span></span>  
  
## <a name="on-error-goto-0"></a><span data-ttu-id="2df82-156">Error GoTo 0</span><span class="sxs-lookup"><span data-stu-id="2df82-156">On Error GoTo 0</span></span>  
 <span data-ttu-id="2df82-157">`On Error GoTo 0` 現在のプロシージャでのエラー処理を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2df82-157">`On Error GoTo 0` disables error handling in the current procedure.</span></span> <span data-ttu-id="2df82-158">0 行目の手順には、番号 0 の行が含まれている場合でも、エラー処理コードの先頭として指定しません。</span><span class="sxs-lookup"><span data-stu-id="2df82-158">It doesn't specify line 0 as the start of the error-handling code, even if the procedure contains a line numbered 0.</span></span> <span data-ttu-id="2df82-159">なし、`On Error GoTo 0`プロシージャが終了すると、ステートメントでは、エラー ハンドラーが自動的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="2df82-159">Without an `On Error GoTo 0` statement, an error handler is automatically disabled when a procedure is exited.</span></span>  
  
## <a name="on-error-goto--1"></a><span data-ttu-id="2df82-160">Error GoTo-1 で</span><span class="sxs-lookup"><span data-stu-id="2df82-160">On Error GoTo -1</span></span>  
 <span data-ttu-id="2df82-161">`On Error GoTo -1` 現在のプロシージャで例外を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2df82-161">`On Error GoTo -1` disables the exception in the current procedure.</span></span> <span data-ttu-id="2df82-162">指定しません行-1、エラー処理コードの先頭としてプロシージャには、-1 を番号の行が含まれている場合でもです。</span><span class="sxs-lookup"><span data-stu-id="2df82-162">It does not specify line -1 as the start of the error-handling code, even if the procedure contains a line numbered -1.</span></span> <span data-ttu-id="2df82-163">なし、`On Error GoTo -1`プロシージャが終了すると、ステートメントでは、例外が自動的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="2df82-163">Without an `On Error GoTo -1` statement, an exception is automatically disabled when a procedure is exited.</span></span>  
  
 <span data-ttu-id="2df82-164">エラー処理コードが、エラーが発生していないときに実行しないように、配置、 `Exit Sub`、 `Exit Function`、または`Exit Property`次のフラグメントのように、エラー処理ルーチンの直前のステートメント。</span><span class="sxs-lookup"><span data-stu-id="2df82-164">To prevent error-handling code from running when no error has occurred, place an `Exit Sub`, `Exit Function`, or `Exit Property` statement immediately before the error-handling routine, as in the following fragment:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]  
  
 <span data-ttu-id="2df82-165">エラー処理コードを次に示します、`Exit Sub`ステートメントの前と、`End Sub`ステートメント、プロシージャのフローから分離することです。</span><span class="sxs-lookup"><span data-stu-id="2df82-165">Here, the error-handling code follows the `Exit Sub` statement and precedes the `End Sub` statement to separate it from the procedure flow.</span></span> <span data-ttu-id="2df82-166">プロシージャでエラー処理コードをどこでも配置できます。</span><span class="sxs-lookup"><span data-stu-id="2df82-166">You can place error-handling code anywhere in a procedure.</span></span>  
  
## <a name="untrapped-errors"></a><span data-ttu-id="2df82-167">エラーをトラップしません。</span><span class="sxs-lookup"><span data-stu-id="2df82-167">Untrapped Errors</span></span>  
 <span data-ttu-id="2df82-168">オブジェクトでエラーをトラップしないは、オブジェクトが実行可能ファイルとして実行されているときに、制御のアプリケーションに返されます。</span><span class="sxs-lookup"><span data-stu-id="2df82-168">Untrapped errors in objects are returned to the controlling application when the object is running as an executable file.</span></span> <span data-ttu-id="2df82-169">開発環境内でエラーをトラップしないが、適切なオプションが設定されている場合にのみ制御するアプリケーションに返されます。</span><span class="sxs-lookup"><span data-stu-id="2df82-169">Within the development environment, untrapped errors are returned to the controlling application only if the proper options are set.</span></span> <span data-ttu-id="2df82-170">デバッグ中に設定、これらを設定する方法、およびホストがクラスを作成するかどうかをオプションにする説明については、ホスト アプリケーションのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2df82-170">See your host application's documentation for a description of which options should be set during debugging, how to set them, and whether the host can create classes.</span></span>  
  
 <span data-ttu-id="2df82-171">その他のオブジェクトにアクセスするオブジェクトを作成する場合戻す未処理のエラーを処理しようとする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2df82-171">If you create an object that accesses other objects, you should try to handle any unhandled errors they pass back.</span></span> <span data-ttu-id="2df82-172">場合のエラー コードをマップすることはできません、`Err.Number`独自のエラーと、パスのいずれかには、オブジェクトの呼び出し元に戻します。</span><span class="sxs-lookup"><span data-stu-id="2df82-172">If you cannot, map the error codes in `Err.Number` to one of your own errors and then pass them back to the caller of your object.</span></span> <span data-ttu-id="2df82-173">エラー コードを追加して、エラーを指定する必要があります、`VbObjectError`定数。</span><span class="sxs-lookup"><span data-stu-id="2df82-173">You should specify your error by adding your error code to the `VbObjectError` constant.</span></span> <span data-ttu-id="2df82-174">たとえば、エラー コードが 1052 の場合は、そのよう割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2df82-174">For example, if your error code is 1052, assign it as follows:</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]  
  
> [!CAUTION]
>  <span data-ttu-id="2df82-175">Windows ダイナミック リンク ライブラリ (Dll) への呼び出し中にシステム エラーは、例外は発生せず、Visual Basic エラー トラッピングをトラップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2df82-175">System errors during calls to Windows dynamic-link libraries (DLLs) do not raise exceptions and cannot be trapped with Visual Basic error trapping.</span></span> <span data-ttu-id="2df82-176">各戻り値の成功または失敗 (に従って、API の仕様を確認する必要があります DLL 関数を呼び出すときに、障害が発生した場合値を確認し、`Err`オブジェクトの`LastDLLError`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2df82-176">When calling DLL functions, you should check each return value for success or failure (according to the API specifications), and in the event of a failure, check the value in the `Err` object's `LastDLLError` property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df82-177">例</span><span class="sxs-lookup"><span data-stu-id="2df82-177">Example</span></span>  
 <span data-ttu-id="2df82-178">この例を使用して、`On Error GoTo`ステートメント、プロシージャ内のエラー処理ルーチンの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="2df82-178">This example first uses the `On Error GoTo` statement to specify the location of an error-handling routine within a procedure.</span></span> <span data-ttu-id="2df82-179">例では、0 で除算しようとするは、エラー数 6 を生成します。</span><span class="sxs-lookup"><span data-stu-id="2df82-179">In the example, an attempt to divide by zero generates error number 6.</span></span> <span data-ttu-id="2df82-180">エラーは、エラー処理ルーチンで処理され、コントロールは、エラーの原因となったステートメントに返されます。</span><span class="sxs-lookup"><span data-stu-id="2df82-180">The error is handled in the error-handling routine, and control is then returned to the statement that caused the error.</span></span> <span data-ttu-id="2df82-181">`On Error GoTo 0`ステートメントがエラー トラッピングをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2df82-181">The `On Error GoTo 0` statement turns off error trapping.</span></span> <span data-ttu-id="2df82-182">次に、`On Error Resume Next`ステートメントを使用して、次のステートメントによって生成されたエラーのコンテキストが特定の認識されるようにエラーをトラップするを延期します。</span><span class="sxs-lookup"><span data-stu-id="2df82-182">Then the `On Error Resume Next` statement is used to defer error trapping so that the context for the error generated by the next statement can be known for certain.</span></span> <span data-ttu-id="2df82-183">なお`Err.Clear`をオフにするために使用、`Err`エラーを処理した後、オブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2df82-183">Note that `Err.Clear` is used to clear the `Err` object's properties after the error is handled.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]  
  
## <a name="requirements"></a><span data-ttu-id="2df82-184">必要条件</span><span class="sxs-lookup"><span data-stu-id="2df82-184">Requirements</span></span>  
 <span data-ttu-id="2df82-185">**名前空間:**[Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="2df82-185">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="2df82-186">**アセンブリ:** Visual Basic ランタイム ライブラリ (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="2df82-186">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df82-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="2df82-187">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [<span data-ttu-id="2df82-188">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="2df82-188">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="2df82-189">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="2df82-189">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="2df82-190">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="2df82-190">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="2df82-191">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="2df82-191">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
- [<span data-ttu-id="2df82-192">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="2df82-192">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
