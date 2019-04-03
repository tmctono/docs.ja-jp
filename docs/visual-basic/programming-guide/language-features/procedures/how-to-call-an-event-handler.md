---
title: '方法: Visual Basic でイベント ハンドラーを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: dd21f80e4b3892cbd9db901b619ecff98f6b70bd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837768"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="f1cfe-102">方法: Visual Basic でイベント ハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="f1cfe-102">How to: Call an Event Handler in Visual Basic</span></span>
<span data-ttu-id="f1cfe-103">*イベント*操作または発生は、-クリックやクレジットの上限を超えたマウスなど、応答するコードを記述でき、いくつかのプログラム コンポーネントによってを認識するは。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="f1cfe-104">*イベント ハンドラー*イベントに応答を記述するコードに示します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-104">An *event handler* is the code you write to respond to an event.</span></span>  
  
 <span data-ttu-id="f1cfe-105">Visual Basic でイベント ハンドラーは、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="f1cfe-106">ただし、呼び出すことはありません通常、同じ方法他`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="f1cfe-107">代わりに、イベントのハンドラーとしてプロシージャを識別します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="f1cfe-108">こうことで、[処理](../../../../visual-basic/language-reference/statements/handles-clause.md)句と[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)変数、または、 [AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-108">You can do this either with a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="f1cfe-109">使用して、`Handles`句は、既定の方法が Visual Basic でイベント ハンドラーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="f1cfe-110">これは、イベント ハンドラーは、統合開発環境 (IDE) でプログラミングするときに、デザイナーによって書き込まれる方法です。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="f1cfe-111">`AddHandler`ステートメントは実行時に動的にイベントを発生させるために適しています。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>  
  
 <span data-ttu-id="f1cfe-112">イベントが発生すると、Visual Basic は自動的にイベント ハンドラーのプロシージャを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="f1cfe-113">イベントにアクセスできる任意のコードを実行することによって発生する可能性を[RaiseEvent ステートメント](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
 <span data-ttu-id="f1cfe-114">同じイベントでは、1 つ以上のイベント ハンドラーを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="f1cfe-115">場合によっては、イベントからハンドラーを切り離すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="f1cfe-116">詳細については、「[イベント](../../../../visual-basic/programming-guide/language-features/events/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-116">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="f1cfe-117">ハンドルと WithEvents を使用して、イベント ハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="f1cfe-117">To call an event handler using Handles and WithEvents</span></span>  
  
1.  <span data-ttu-id="f1cfe-118">でイベントが宣言されていることを確認、 [Event ステートメント](../../../../visual-basic/language-reference/statements/event-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-118">Make sure the event is declared with an [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
2.  <span data-ttu-id="f1cfe-119">レベルを使用して、モジュールまたはクラスでオブジェクト変数を宣言、 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-119">Declare an object variable at module or class level, using the [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="f1cfe-120">`As`この変数は、イベントを発生させるクラスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-120">The `As` clause for this variable must specify the class that raises the event.</span></span>  
  
3.  <span data-ttu-id="f1cfe-121">イベント処理の宣言で`Sub`プロシージャを追加、[処理](../../../../visual-basic/language-reference/statements/handles-clause.md)句を指定する、`WithEvents`変数、およびイベント名。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>  
  
4.  <span data-ttu-id="f1cfe-122">Visual Basic を自動的に呼び出して、イベントの発生時に、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="f1cfe-123">コードを使用できます、`RaiseEvent`イベントで発生するステートメント。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="f1cfe-124">次の例では、イベントを定義して、`WithEvents`イベントを発生させるクラスを参照する変数。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="f1cfe-125">イベント処理`Sub`プロシージャは、`Handles`クラスとイベントの処理を指定する句。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>  
  
     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="f1cfe-126">AddHandler を使用して、イベント ハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="f1cfe-126">To call an event handler using AddHandler</span></span>  
  
1.  <span data-ttu-id="f1cfe-127">でイベントが宣言されていることを確認、`Event`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-127">Make sure the event is declared with an `Event` statement.</span></span>  
  
2.  <span data-ttu-id="f1cfe-128">実行、 [AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)イベント処理を動的に接続する`Sub`イベントにプロシージャ。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-128">Execute an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>  
  
3.  <span data-ttu-id="f1cfe-129">Visual Basic を自動的に呼び出して、イベントの発生時に、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="f1cfe-130">コードを使用できます、`RaiseEvent`イベントで発生するステートメント。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>  
  
     <span data-ttu-id="f1cfe-131">次の例では、定義、`Sub`を処理する手順、<xref:System.Windows.Forms.Form.Closing>フォームのイベント。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="f1cfe-132">次を使用して、 [AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)に関連付ける、`catchClose`のイベント ハンドラーとプロシージャ<xref:System.Windows.Forms.Form.Closing>します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-132">It then uses the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>  
  
     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]  
  
     <span data-ttu-id="f1cfe-133">実行することによって、イベントからイベント ハンドラーの関連付けを解除することができます、 [RemoveHandler ステートメント](../../../../visual-basic/language-reference/statements/removehandler-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cfe-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1cfe-134">See also</span></span>

- [<span data-ttu-id="f1cfe-135">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f1cfe-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f1cfe-136">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f1cfe-136">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="f1cfe-137">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="f1cfe-137">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f1cfe-138">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="f1cfe-138">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="f1cfe-139">方法: プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1cfe-139">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="f1cfe-140">方法: 値を返さないプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="f1cfe-140">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
