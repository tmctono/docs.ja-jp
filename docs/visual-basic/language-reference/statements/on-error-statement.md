---
title: On Error ステートメント
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
ms.openlocfilehash: d62c2ba1849b7015ed877d503220026a2dfeff57
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353820"
---
# <a name="on-error-statement-visual-basic"></a><span data-ttu-id="ddc24-102">On Error ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddc24-102">On Error Statement (Visual Basic)</span></span>
<span data-ttu-id="ddc24-103">エラー処理ルーチンを有効にし、プロシージャ内でルーチンの場所を指定します。は、エラー処理ルーチンを無効にするためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-103">Enables an error-handling routine and specifies the location of the routine within a procedure; can also be used to disable an error-handling routine.</span></span> <span data-ttu-id="ddc24-104">`On Error` ステートメントは非構造化エラー処理で使用されるため、構造化例外処理の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-104">The `On Error` statement is used in unstructured error handling and can be used instead of structured exception handling.</span></span> <span data-ttu-id="ddc24-105">[構造化例外処理](../../../standard/exceptions/index.md)は .net に組み込まれているので、一般に効率が向上するため、アプリケーションで実行時エラーを処理する場合に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-105">[Structured exception handling](../../../standard/exceptions/index.md) is built into .NET, is generally more efficient, and so is recommended when handling runtime errors in your application.</span></span>

 <span data-ttu-id="ddc24-106">エラー処理または例外処理を使用しない場合、発生したすべての実行時エラーは致命的なエラーであり、エラーメッセージが表示され、実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-106">Without error handling or exception handling, any run-time error that occurs is fatal: an error message is displayed, and execution stops.</span></span>

> [!NOTE]
> <span data-ttu-id="ddc24-107">`Error` キーワードは、旧バージョンとの互換性のためにサポートされている[Error ステートメント](../../../visual-basic/language-reference/statements/error-statement.md)でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-107">The `Error` keyword is also used in the [Error Statement](../../../visual-basic/language-reference/statements/error-statement.md), which is supported for backward compatibility.</span></span>

## <a name="syntax"></a><span data-ttu-id="ddc24-108">構文</span><span class="sxs-lookup"><span data-stu-id="ddc24-108">Syntax</span></span>

```vb
On Error { GoTo [ line | 0 | -1 ] | Resume Next }
```

## <a name="parts"></a><span data-ttu-id="ddc24-109">指定項目</span><span class="sxs-lookup"><span data-stu-id="ddc24-109">Parts</span></span>

|<span data-ttu-id="ddc24-110">用語</span><span class="sxs-lookup"><span data-stu-id="ddc24-110">Term</span></span>|<span data-ttu-id="ddc24-111">Definition</span><span class="sxs-lookup"><span data-stu-id="ddc24-111">Definition</span></span>|
|---|---|
|<span data-ttu-id="ddc24-112">`GoTo`*線*</span><span class="sxs-lookup"><span data-stu-id="ddc24-112">`GoTo` *line*</span></span>|<span data-ttu-id="ddc24-113">必須の*line*引数で指定された行から開始するエラー処理ルーチンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-113">Enables the error-handling routine that starts at the line specified in the required *line* argument.</span></span> <span data-ttu-id="ddc24-114">*Line*引数は、任意の行ラベルまたは行番号です。</span><span class="sxs-lookup"><span data-stu-id="ddc24-114">The *line* argument is any line label or line number.</span></span> <span data-ttu-id="ddc24-115">実行時エラーが発生した場合、コントロールは指定された行に分岐し、エラーハンドラーがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-115">If a run-time error occurs, control branches to the specified line, making the error handler active.</span></span> <span data-ttu-id="ddc24-116">指定された行は、`On Error` ステートメントと同じプロシージャ内に存在する必要があります。指定しないと、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-116">The specified line must be in the same procedure as the `On Error` statement or a compile-time error will occur.</span></span>|
|`GoTo 0`|<span data-ttu-id="ddc24-117">現在のプロシージャで有効になっているエラーハンドラーを無効にし、`Nothing`にリセットします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-117">Disables enabled error handler in the current procedure and resets it to `Nothing`.</span></span>|
|`GoTo -1`|<span data-ttu-id="ddc24-118">現在のプロシージャで有効になっている例外を無効にして、`Nothing`にリセットします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-118">Disables enabled exception in the current procedure and resets it to `Nothing`.</span></span>|
|`Resume Next`|<span data-ttu-id="ddc24-119">実行時エラーが発生したときに、エラーが発生したステートメントの直後のステートメントに制御を移動し、その時点から実行を続行することを指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-119">Specifies that when a run-time error occurs, control goes to the statement immediately following the statement where the error occurred, and execution continues from that point.</span></span> <span data-ttu-id="ddc24-120">オブジェクトにアクセスする場合は、`On Error GoTo` ではなく、この形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-120">Use this form rather than `On Error GoTo` when accessing objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ddc24-121">コメント</span><span class="sxs-lookup"><span data-stu-id="ddc24-121">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="ddc24-122">構造化例外処理は、構造化されていない例外処理と `On Error` ステートメントを使用するのではなく、可能な限りコードで使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-122">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` statement.</span></span> <span data-ttu-id="ddc24-123">詳しくは、「[Try...Catch...Finally ステートメント](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ddc24-123">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>

 <span data-ttu-id="ddc24-124">"Enabled" エラーハンドラーは、`On Error` ステートメントによって有効にされているものです。</span><span class="sxs-lookup"><span data-stu-id="ddc24-124">An "enabled" error handler is one that is turned on by an `On Error` statement.</span></span> <span data-ttu-id="ddc24-125">"アクティブ" エラーハンドラーは、エラーを処理するための有効なハンドラーです。</span><span class="sxs-lookup"><span data-stu-id="ddc24-125">An "active" error handler is an enabled handler that is in the process of handling an error.</span></span>

 <span data-ttu-id="ddc24-126">エラーハンドラーがアクティブになっている間にエラーが発生した場合 (エラーが発生した場合と、`Resume`、`Exit Sub`、`Exit Function`、または `Exit Property` ステートメントの場合)、現在のプロシージャのエラーハンドラーではエラーを処理できません。</span><span class="sxs-lookup"><span data-stu-id="ddc24-126">If an error occurs while an error handler is active (between the occurrence of the error and a `Resume`, `Exit Sub`, `Exit Function`, or `Exit Property` statement), the current procedure's error handler cannot handle the error.</span></span> <span data-ttu-id="ddc24-127">呼び出し元のプロシージャに制御が戻ります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-127">Control returns to the calling procedure.</span></span>
  
 <span data-ttu-id="ddc24-128">呼び出し元のプロシージャに有効なエラーハンドラーがある場合は、エラーを処理するためにアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-128">If the calling procedure has an enabled error handler, it is activated to handle the error.</span></span> <span data-ttu-id="ddc24-129">呼び出し元のプロシージャのエラーハンドラーもアクティブになっている場合は、有効になっているが非アクティブなエラーハンドラーが見つかるまで、制御は前の呼び出しプロシージャを通過します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-129">If the calling procedure's error handler is also active, control passes back through previous calling procedures until an enabled, but inactive, error handler is found.</span></span> <span data-ttu-id="ddc24-130">このようなエラーハンドラーが見つからない場合、エラーは実際に発生した時点で致命的です。</span><span class="sxs-lookup"><span data-stu-id="ddc24-130">If no such error handler is found, the error is fatal at the point at which it actually occurred.</span></span>
  
 <span data-ttu-id="ddc24-131">エラーハンドラーが呼び出し元のプロシージャに制御を戻すたびに、そのプロシージャが現在のプロシージャになります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-131">Each time the error handler passes control back to a calling procedure, that procedure becomes the current procedure.</span></span> <span data-ttu-id="ddc24-132">任意のプロシージャのエラーハンドラーによってエラーが処理されると、`Resume` ステートメントによって指定された時点で、現在のプロシージャで実行が再開されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-132">Once an error is handled by an error handler in any procedure, execution resumes in the current procedure at the point designated by the `Resume` statement.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddc24-133">エラー処理ルーチンは、`Sub` プロシージャでも `Function` プロシージャでもありません。</span><span class="sxs-lookup"><span data-stu-id="ddc24-133">An error-handling routine is not a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="ddc24-134">これは、行ラベルまたは行番号でマークされたコードのセクションです。</span><span class="sxs-lookup"><span data-stu-id="ddc24-134">It is a section of code marked by a line label or a line number.</span></span>
  
## <a name="number-property"></a><span data-ttu-id="ddc24-135">Number プロパティ</span><span class="sxs-lookup"><span data-stu-id="ddc24-135">Number Property</span></span>
 <span data-ttu-id="ddc24-136">エラー処理ルーチンは、エラーの原因を特定するために、`Err` オブジェクトの `Number` プロパティの値に依存します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-136">Error-handling routines rely on the value in the `Number` property of the `Err` object to determine the cause of the error.</span></span> <span data-ttu-id="ddc24-137">ルーチンは、他のエラーが発生する前、またはエラーが発生する可能性のあるプロシージャが呼び出される前に、`Err` オブジェクト内の関連するプロパティ値をテストまたは保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-137">The routine should test or save relevant property values in the `Err` object before any other error can occur or before a procedure that might cause an error is called.</span></span> <span data-ttu-id="ddc24-138">`Err` オブジェクトのプロパティ値は、最新のエラーのみを反映します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-138">The property values in the `Err` object reflect only the most recent error.</span></span> <span data-ttu-id="ddc24-139">`Err.Number` に関連付けられたエラーメッセージは `Err.Description`に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ddc24-139">The error message associated with `Err.Number` is contained in `Err.Description`.</span></span>  
  
## <a name="throw-statement"></a><span data-ttu-id="ddc24-140">Throw ステートメント</span><span class="sxs-lookup"><span data-stu-id="ddc24-140">Throw Statement</span></span>  
 <span data-ttu-id="ddc24-141">`Err.Raise` メソッドで発生したエラーは、`Exception` プロパティを <xref:System.Exception> クラスの新しく作成されたインスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-141">An error that is raised with the `Err.Raise` method sets the `Exception` property to a newly created instance of the <xref:System.Exception> class.</span></span> <span data-ttu-id="ddc24-142">派生した例外の種類の例外の発生をサポートするために、言語で `Throw` ステートメントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ddc24-142">In order to support the raising of exceptions of derived exception types, a `Throw` statement is supported in the language.</span></span> <span data-ttu-id="ddc24-143">これは、スローされる例外インスタンスである1つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-143">This takes a single parameter that is the exception instance to be thrown.</span></span> <span data-ttu-id="ddc24-144">次の例は、これらの機能を既存の例外処理サポートと共に使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ddc24-144">The following example shows how these features can be used with the existing exception handling support:</span></span>

 [!code-vb[VbVbalrErrorHandling#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#17)]  
  
 <span data-ttu-id="ddc24-145">`On Error GoTo` ステートメントでは、exception クラスに関係なく、すべてのエラーがトラップされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ddc24-145">Notice that the `On Error GoTo` statement traps all errors, regardless of the exception class.</span></span>
  
## <a name="on-error-resume-next"></a><span data-ttu-id="ddc24-146">エラー時に再開する</span><span class="sxs-lookup"><span data-stu-id="ddc24-146">On Error Resume Next</span></span>
 <span data-ttu-id="ddc24-147">`On Error Resume Next` により、実行は、実行時エラーの原因となったステートメントの直後のステートメント、または、`On Error Resume Next` ステートメントを含むプロシージャの最後の呼び出しの直後にあるステートメントで続行されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-147">`On Error Resume Next` causes execution to continue with the statement immediately following the statement that caused the run-time error, or with the statement immediately following the most recent call out of the procedure containing the `On Error Resume Next` statement.</span></span> <span data-ttu-id="ddc24-148">このステートメントを使用すると、実行時エラーが発生しても実行を続行できます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-148">This statement allows execution to continue despite a run-time error.</span></span> <span data-ttu-id="ddc24-149">プロシージャ内の別の場所に制御を転送するのではなく、エラーが発生するエラー処理ルーチンを配置できます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-149">You can place the error-handling routine where the error would occur rather than transferring control to another location within the procedure.</span></span> <span data-ttu-id="ddc24-150">別のプロシージャが呼び出されると、`On Error Resume Next` ステートメントは非アクティブになります。そのため、ルーチン内でインラインエラー処理が必要な場合は、呼び出された各ルーチンで `On Error Resume Next` ステートメントを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-150">An `On Error Resume Next` statement becomes inactive when another procedure is called, so you should execute an `On Error Resume Next` statement in each called routine if you want inline error handling within that routine.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddc24-151">`On Error Resume Next` コンストラクトは、他のオブジェクトへのアクセス中に発生したエラーを処理する場合に `On Error GoTo` することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-151">The `On Error Resume Next` construct may be preferable to `On Error GoTo` when handling errors generated during access to other objects.</span></span> <span data-ttu-id="ddc24-152">オブジェクトを操作するたびに `Err` をチェックすると、コードによってアクセスされたオブジェクトがあいまいになります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-152">Checking `Err` after each interaction with an object removes ambiguity about which object was accessed by the code.</span></span> <span data-ttu-id="ddc24-153">エラーコードを `Err.Number`に配置したオブジェクトと、最初にエラーを生成したオブジェクト (`Err.Source`で指定されたオブジェクト) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-153">You can be sure which object placed the error code in `Err.Number`, as well as which object originally generated the error (the object specified in `Err.Source`).</span></span>

## <a name="on-error-goto-0"></a><span data-ttu-id="ddc24-154">On Error GoTo 0</span><span class="sxs-lookup"><span data-stu-id="ddc24-154">On Error GoTo 0</span></span>
 <span data-ttu-id="ddc24-155">`On Error GoTo 0` は、現在のプロシージャのエラー処理を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-155">`On Error GoTo 0` disables error handling in the current procedure.</span></span> <span data-ttu-id="ddc24-156">プロシージャに行番号0が含まれている場合でも、エラー処理コードの先頭として行0が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="ddc24-156">It doesn't specify line 0 as the start of the error-handling code, even if the procedure contains a line numbered 0.</span></span> <span data-ttu-id="ddc24-157">`On Error GoTo 0` ステートメントを使用しない場合、プロシージャが終了すると、エラーハンドラーが自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-157">Without an `On Error GoTo 0` statement, an error handler is automatically disabled when a procedure is exited.</span></span>

## <a name="on-error-goto--1"></a><span data-ttu-id="ddc24-158">エラー時の GoTo-1</span><span class="sxs-lookup"><span data-stu-id="ddc24-158">On Error GoTo -1</span></span>
 <span data-ttu-id="ddc24-159">`On Error GoTo -1` は、現在のプロシージャの例外を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-159">`On Error GoTo -1` disables the exception in the current procedure.</span></span> <span data-ttu-id="ddc24-160">プロシージャに1行の番号が含まれている場合でも、エラー処理コードの開始として行-1 を指定しません。</span><span class="sxs-lookup"><span data-stu-id="ddc24-160">It does not specify line -1 as the start of the error-handling code, even if the procedure contains a line numbered -1.</span></span> <span data-ttu-id="ddc24-161">`On Error GoTo -1` ステートメントを使用しない場合、プロシージャが終了すると、例外が自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-161">Without an `On Error GoTo -1` statement, an exception is automatically disabled when a procedure is exited.</span></span>

 <span data-ttu-id="ddc24-162">エラーが発生しなかったときにエラー処理コードが実行されないようにするには、次のように、エラー処理ルーチンの直前に、`Exit Sub`、`Exit Function`、または `Exit Property` ステートメントを配置します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-162">To prevent error-handling code from running when no error has occurred, place an `Exit Sub`, `Exit Function`, or `Exit Property` statement immediately before the error-handling routine, as in the following fragment:</span></span>

 [!code-vb[VbVbalrErrorHandling#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#18)]

 <span data-ttu-id="ddc24-163">ここでは、エラー処理コードは、`Exit Sub` ステートメントに従い、`End Sub` ステートメントの前に、プロシージャフローから分離します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-163">Here, the error-handling code follows the `Exit Sub` statement and precedes the `End Sub` statement to separate it from the procedure flow.</span></span> <span data-ttu-id="ddc24-164">プロシージャ内の任意の場所にエラー処理コードを配置できます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-164">You can place error-handling code anywhere in a procedure.</span></span>

## <a name="untrapped-errors"></a><span data-ttu-id="ddc24-165">トラップエラー</span><span class="sxs-lookup"><span data-stu-id="ddc24-165">Untrapped Errors</span></span>
 <span data-ttu-id="ddc24-166">オブジェクトのトラップされていないエラーは、オブジェクトが実行可能ファイルとして実行されている場合に、制御を行うアプリケーションに返されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-166">Untrapped errors in objects are returned to the controlling application when the object is running as an executable file.</span></span> <span data-ttu-id="ddc24-167">開発環境では、適切なオプションが設定されている場合にのみ、トラップされないエラーが制御アプリケーションに返されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-167">Within the development environment, untrapped errors are returned to the controlling application only if the proper options are set.</span></span> <span data-ttu-id="ddc24-168">デバッグ中に設定するオプション、設定方法、およびホストでクラスを作成できるかどうかの説明については、ホストアプリケーションのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddc24-168">See your host application's documentation for a description of which options should be set during debugging, how to set them, and whether the host can create classes.</span></span>

 <span data-ttu-id="ddc24-169">他のオブジェクトにアクセスするオブジェクトを作成する場合は、返されたハンドルされていないエラーを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-169">If you create an object that accesses other objects, you should try to handle any unhandled errors they pass back.</span></span> <span data-ttu-id="ddc24-170">できない場合は、`Err.Number` のエラーコードを独自のエラーのいずれかにマップし、オブジェクトの呼び出し元に渡します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-170">If you cannot, map the error codes in `Err.Number` to one of your own errors and then pass them back to the caller of your object.</span></span> <span data-ttu-id="ddc24-171">エラーコードを `VbObjectError` 定数に追加して、エラーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-171">You should specify your error by adding your error code to the `VbObjectError` constant.</span></span> <span data-ttu-id="ddc24-172">たとえば、エラーコードが1052の場合は、次のように割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-172">For example, if your error code is 1052, assign it as follows:</span></span>

 [!code-vb[VbVbalrErrorHandling#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#19)]

> [!CAUTION]
> <span data-ttu-id="ddc24-173">Windows ダイナミックリンクライブラリ (Dll) の呼び出し中にシステムエラーが発生しても、例外は発生せず、Visual Basic エラートラップでトラップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ddc24-173">System errors during calls to Windows dynamic-link libraries (DLLs) do not raise exceptions and cannot be trapped with Visual Basic error trapping.</span></span> <span data-ttu-id="ddc24-174">DLL 関数を呼び出すときは、API の仕様に従って、成功または失敗の各戻り値を確認し、エラーが発生した場合は `Err` オブジェクトの `LastDLLError` プロパティの値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddc24-174">When calling DLL functions, you should check each return value for success or failure (according to the API specifications), and in the event of a failure, check the value in the `Err` object's `LastDLLError` property.</span></span>

## <a name="example"></a><span data-ttu-id="ddc24-175">例</span><span class="sxs-lookup"><span data-stu-id="ddc24-175">Example</span></span>
 <span data-ttu-id="ddc24-176">この例では、最初に `On Error GoTo` ステートメントを使用して、プロシージャ内のエラー処理ルーチンの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-176">This example first uses the `On Error GoTo` statement to specify the location of an error-handling routine within a procedure.</span></span> <span data-ttu-id="ddc24-177">この例では、0で除算しようとするとエラー番号6が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-177">In the example, an attempt to divide by zero generates error number 6.</span></span> <span data-ttu-id="ddc24-178">エラー処理ルーチンでエラーが処理され、エラーの原因となったステートメントに制御が返されます。</span><span class="sxs-lookup"><span data-stu-id="ddc24-178">The error is handled in the error-handling routine, and control is then returned to the statement that caused the error.</span></span> <span data-ttu-id="ddc24-179">`On Error GoTo 0` ステートメントは、エラートラップをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ddc24-179">The `On Error GoTo 0` statement turns off error trapping.</span></span> <span data-ttu-id="ddc24-180">次に、`On Error Resume Next` ステートメントを使用して、次のステートメントによって生成されるエラーのコンテキストが特定ので認識されるように、エラートラップを遅延します。</span><span class="sxs-lookup"><span data-stu-id="ddc24-180">Then the `On Error Resume Next` statement is used to defer error trapping so that the context for the error generated by the next statement can be known for certain.</span></span> <span data-ttu-id="ddc24-181">`Err.Clear` は、エラーが処理された後に `Err` オブジェクトのプロパティをクリアするために使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ddc24-181">Note that `Err.Clear` is used to clear the `Err` object's properties after the error is handled.</span></span>

 [!code-vb[VbVbalrErrorHandling#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#20)]

## <a name="requirements"></a><span data-ttu-id="ddc24-182">要件</span><span class="sxs-lookup"><span data-stu-id="ddc24-182">Requirements</span></span>
 <span data-ttu-id="ddc24-183">**名前空間:** [Microsoft. visual basic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="ddc24-183">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>

 <span data-ttu-id="ddc24-184">**アセンブリ:** Visual Basic ランタイムライブラリ (Microsoft... .dll)</span><span class="sxs-lookup"><span data-stu-id="ddc24-184">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>

## <a name="see-also"></a><span data-ttu-id="ddc24-185">参照</span><span class="sxs-lookup"><span data-stu-id="ddc24-185">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Number%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Description%2A>
- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [<span data-ttu-id="ddc24-186">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="ddc24-186">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="ddc24-187">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="ddc24-187">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="ddc24-188">Resume ステートメント</span><span class="sxs-lookup"><span data-stu-id="ddc24-188">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="ddc24-189">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="ddc24-189">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
- [<span data-ttu-id="ddc24-190">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="ddc24-190">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
