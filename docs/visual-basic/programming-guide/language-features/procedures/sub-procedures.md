---
title: Sub プロシージャ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: b70594e002bbf08f0890586e78df901ccb26c7ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791822"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="d15e7-102">Sub プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d15e7-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="d15e7-103">A`Sub`手順は、一連の Visual Basic のステートメントで囲まれた、`Sub`と`End Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="d15e7-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="d15e7-104">`Sub`呼び出しコードに値を返すことはできませんが、プロシージャは、タスクを実行し、呼び出し元のコードにコントロールを返します。</span><span class="sxs-lookup"><span data-stu-id="d15e7-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="d15e7-105">そのステートメントが実行されます、プロシージャが呼び出されるたびに後の最初の実行可能ステートメントで始まる、`Sub`ステートメントと最初の終了`End Sub`、 `Exit Sub`、または`Return`ステートメントが発生しました。</span><span class="sxs-lookup"><span data-stu-id="d15e7-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="d15e7-106">定義することができます、`Sub`プロシージャでは、モジュール、クラス、および構造体。</span><span class="sxs-lookup"><span data-stu-id="d15e7-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="d15e7-107">既定では`Public`、することができるから呼び出せる任意の場所でモジュール、クラス、またはで定義された構造体にアクセスできるアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="d15e7-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="d15e7-108">用語、*メソッド*、について説明します、`Sub`または`Function`プロシージャの定義の外部からアクセスされるモジュール、クラスまたは構造体。</span><span class="sxs-lookup"><span data-stu-id="d15e7-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="d15e7-109">詳細については、「[プロシージャ](./index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d15e7-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="d15e7-110">A`Sub`プロシージャは、定数、変数、または、呼び出し元のコードに渡される式などの引数をとることができます。</span><span class="sxs-lookup"><span data-stu-id="d15e7-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="d15e7-111">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="d15e7-111">Declaration Syntax</span></span>  
 <span data-ttu-id="d15e7-112">宣言の構文、`Sub`手順のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d15e7-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="d15e7-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="d15e7-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="d15e7-114">`modifiers`アクセス レベルとオーバー ロード、オーバーライド、共有、およびシャドウ処理に関する情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d15e7-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="d15e7-115">詳細については、次を参照してください。 [Sub ステートメント](../../../../visual-basic/language-reference/statements/sub-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="d15e7-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="d15e7-116">パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="d15e7-116">Parameter Declaration</span></span>  
 <span data-ttu-id="d15e7-117">各プロシージャのパラメーターと同様にどのように変数を宣言する、パラメーター名とデータ型を指定することを宣言するとします。</span><span class="sxs-lookup"><span data-stu-id="d15e7-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="d15e7-118">引数渡しの方法を指定することもでき、パラメーターは省略可能かどうか、またはパラメーター配列。</span><span class="sxs-lookup"><span data-stu-id="d15e7-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="d15e7-119">パラメーター リスト内の各パラメーターの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d15e7-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="d15e7-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span><span class="sxs-lookup"><span data-stu-id="d15e7-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="d15e7-121">パラメーターが省略可能な場合は、その宣言の一部として既定値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d15e7-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="d15e7-122">既定値を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d15e7-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="d15e7-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="d15e7-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="d15e7-124">ローカル変数とパラメーター</span><span class="sxs-lookup"><span data-stu-id="d15e7-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="d15e7-125">プロシージャに制御が渡される、各パラメーターは、ローカル変数として扱われます。</span><span class="sxs-lookup"><span data-stu-id="d15e7-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="d15e7-126">これは、その有効期間は、プロシージャのと同じことと、そのスコープは、プロシージャ全体を意味します。</span><span class="sxs-lookup"><span data-stu-id="d15e7-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="d15e7-127">呼び出し構文</span><span class="sxs-lookup"><span data-stu-id="d15e7-127">Calling Syntax</span></span>  
 <span data-ttu-id="d15e7-128">呼び出す、`Sub`スタンドアロンのステートメントの呼び出しで明示的にプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="d15e7-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="d15e7-129">式の中でその名前を使用して呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d15e7-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="d15e7-130">省略可能でないすべての引数の値を指定する必要があり、引数リストをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="d15e7-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="d15e7-131">引数が指定されていない場合、かっこを省略することができます。</span><span class="sxs-lookup"><span data-stu-id="d15e7-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="d15e7-132">使用、`Call`キーワードは省略可能ですが、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="d15e7-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="d15e7-133">呼び出しの構文を`Sub`手順のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d15e7-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="d15e7-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="d15e7-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="d15e7-135">呼び出すことができます、`Sub`からそれを定義するクラスの外側のメソッド。</span><span class="sxs-lookup"><span data-stu-id="d15e7-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="d15e7-136">最初に、使用する必要がある、`New`キーワード、クラスのインスタンスを作成またはメソッドを呼び出すには、クラスのインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="d15e7-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="d15e7-137">詳細については、次を参照してください。 [New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="d15e7-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="d15e7-138">次を呼び出す、次の構文を使用することができます、`Sub`インスタンス オブジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="d15e7-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="d15e7-139">*オブジェクト*.*methodname*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="d15e7-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="d15e7-140">宣言と呼び出しの図</span><span class="sxs-lookup"><span data-stu-id="d15e7-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="d15e7-141">次`Sub`の手順では、コンピューターの演算子、アプリケーションを実行する作業はどれもタイムスタンプを表示します。</span><span class="sxs-lookup"><span data-stu-id="d15e7-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="d15e7-142">アプリケーションのすべてのタスクの開始時に、このコードではなく、呼び出しだけ`tellOperator`さまざまな場所からします。</span><span class="sxs-lookup"><span data-stu-id="d15e7-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="d15e7-143">各呼び出しには文字列で、`task`開始されているタスクを識別する引数。</span><span class="sxs-lookup"><span data-stu-id="d15e7-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="d15e7-144">次の例では、一般的な呼び出しを`tellOperator`します。</span><span class="sxs-lookup"><span data-stu-id="d15e7-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d15e7-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="d15e7-145">See also</span></span>

- [<span data-ttu-id="d15e7-146">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d15e7-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d15e7-147">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d15e7-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="d15e7-148">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d15e7-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d15e7-149">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d15e7-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="d15e7-150">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="d15e7-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d15e7-151">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="d15e7-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d15e7-152">方法: 値を返さないプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="d15e7-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="d15e7-153">方法: Visual Basic でイベント ハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="d15e7-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
