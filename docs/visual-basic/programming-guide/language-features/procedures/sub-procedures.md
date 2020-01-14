---
title: Sub プロシージャ
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
ms.openlocfilehash: 7848dc07d6462622685cdbea92202585f4d5d2c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352532"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="00589-102">Sub プロシージャ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00589-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="00589-103">`Sub` プロシージャは、`Sub` および `End Sub` ステートメントで囲まれた一連の Visual Basic ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="00589-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="00589-104">`Sub` プロシージャはタスクを実行した後、呼び出し元のコードに制御を戻しますが、呼び出し元のコードには値を返しません。</span><span class="sxs-lookup"><span data-stu-id="00589-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="00589-105">プロシージャが呼び出されるたびに、ステートメントが実行されます。これは、`Sub` ステートメントの後の最初の実行可能ステートメントから開始し、最初の `End Sub`、`Exit Sub`、または `Return` ステートメントで終了します。</span><span class="sxs-lookup"><span data-stu-id="00589-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="00589-106">モジュール、クラス、および構造体で `Sub` プロシージャを定義できます。</span><span class="sxs-lookup"><span data-stu-id="00589-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="00589-107">既定では `Public`になっています。これは、アプリケーション内の任意の場所から、これを定義したモジュール、クラス、または構造体にアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="00589-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="00589-108">*メソッド*は、定義されているモジュール、クラス、または構造体の外部からアクセスされる、`Sub` または `Function` プロシージャを記述します。</span><span class="sxs-lookup"><span data-stu-id="00589-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="00589-109">詳細については、「[Visual Basic におけるプロシージャ](./index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00589-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="00589-110">`Sub` プロシージャは、呼び出し元のコードによって渡される定数、変数、式などの引数を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="00589-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="00589-111">宣言の構文</span><span class="sxs-lookup"><span data-stu-id="00589-111">Declaration Syntax</span></span>  
 <span data-ttu-id="00589-112">`Sub` プロシージャを宣言する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00589-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="00589-113">`[`*修飾子*`] Sub`*subname* `[(` *parameterlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="00589-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="00589-114">`modifiers` では、アクセスレベルと、オーバーロード、オーバーライド、共有、およびシャドウに関する情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="00589-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="00589-115">詳細については、「[Sub ステートメント](../../../../visual-basic/language-reference/statements/sub-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00589-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="00589-116">パラメーターの宣言</span><span class="sxs-lookup"><span data-stu-id="00589-116">Parameter Declaration</span></span>  
 <span data-ttu-id="00589-117">パラメーター名とデータ型を指定して、変数を宣言するのと同じように各プロシージャパラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="00589-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="00589-118">また、渡す機構と、パラメーターが省略可能またはパラメーター配列であるかどうかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="00589-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="00589-119">パラメーターリストの各パラメーターの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00589-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="00589-120">`[Optional] [ByVal | ByRef] [ParamArray]`*parametername*`As`*datatype*</span><span class="sxs-lookup"><span data-stu-id="00589-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="00589-121">パラメーターが省略可能な場合は、宣言の一部として既定値を指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="00589-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="00589-122">既定値を指定する構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00589-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="00589-123">`Optional [ByVal | ByRef]`*parametername*`As`*datatype*`=`*defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="00589-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="00589-124">ローカル変数としてのパラメーター</span><span class="sxs-lookup"><span data-stu-id="00589-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="00589-125">コントロールがプロシージャに渡されると、各パラメーターはローカル変数として扱われます。</span><span class="sxs-lookup"><span data-stu-id="00589-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="00589-126">これは、その有効期間がプロシージャの有効期間と同じであり、そのスコープがプロシージャ全体であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="00589-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="00589-127">呼び出し構文</span><span class="sxs-lookup"><span data-stu-id="00589-127">Calling Syntax</span></span>  
 <span data-ttu-id="00589-128">`Sub` プロシージャは、スタンドアロンの呼び出しステートメントを使用して明示的に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="00589-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="00589-129">式で名前を使用して呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="00589-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="00589-130">省略可能なすべての引数の値を指定する必要があり、引数リストをかっこで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="00589-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="00589-131">引数を指定しない場合は、必要に応じてかっこを省略できます。</span><span class="sxs-lookup"><span data-stu-id="00589-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="00589-132">`Call` キーワードの使用は省略可能ですが、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="00589-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="00589-133">`Sub` プロシージャの呼び出しの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00589-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="00589-134">`[Call]`*subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="00589-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="00589-135">`Sub` メソッドは、それを定義するクラスの外部から呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="00589-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="00589-136">最初に、`New` キーワードを使用してクラスのインスタンスを作成するか、クラスのインスタンスを返すメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="00589-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="00589-137">詳細については、「[New 演算子](../../../../visual-basic/language-reference/operators/new-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00589-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="00589-138">その後、次の構文を使用して、インスタンスオブジェクトの `Sub` メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="00589-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="00589-139">*オブジェクト*。*methodname*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="00589-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="00589-140">宣言と呼び出しの図</span><span class="sxs-lookup"><span data-stu-id="00589-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="00589-141">次の `Sub` 手順では、アプリケーションが実行しようとしているタスクをコンピューターオペレーターに指示し、タイムスタンプも表示します。</span><span class="sxs-lookup"><span data-stu-id="00589-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="00589-142">すべてのタスクの開始時にこのコードを複製するのではなく、アプリケーションはさまざまな場所から `tellOperator` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="00589-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="00589-143">各呼び出しは、開始されるタスクを識別する `task` 引数に文字列を渡します。</span><span class="sxs-lookup"><span data-stu-id="00589-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="00589-144">次の例は、`tellOperator`の一般的な呼び出しを示しています。</span><span class="sxs-lookup"><span data-stu-id="00589-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="00589-145">参照</span><span class="sxs-lookup"><span data-stu-id="00589-145">See also</span></span>

- [<span data-ttu-id="00589-146">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="00589-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="00589-147">Function プロシージャ</span><span class="sxs-lookup"><span data-stu-id="00589-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="00589-148">Property プロシージャ</span><span class="sxs-lookup"><span data-stu-id="00589-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="00589-149">演算子プロシージャ</span><span class="sxs-lookup"><span data-stu-id="00589-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="00589-150">プロシージャのパラメーターと引数</span><span class="sxs-lookup"><span data-stu-id="00589-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="00589-151">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="00589-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="00589-152">方法 : 値を返さないプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="00589-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="00589-153">方法: Visual Basic でイベントハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="00589-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
