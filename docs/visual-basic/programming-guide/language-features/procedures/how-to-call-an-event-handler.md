---
title: '方法: イベントハンドラーを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 0c626a9ad92fe2cd0ea117a9abdd2965a09df2ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340428"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a><span data-ttu-id="5570c-102">方法 : Visual Basic でイベント ハンドラーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="5570c-102">How to: Call an Event Handler in Visual Basic</span></span>

<span data-ttu-id="5570c-103">*イベント*は、何らかのプログラムコンポーネントによって認識されるアクションまたは発生 (たとえば、マウスクリックやクレジットの制限を超えた場合) で、応答するコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="5570c-103">An *event* is an action or occurrence — such as a mouse click or a credit limit exceeded — that is recognized by some program component, and for which you can write code to respond.</span></span> <span data-ttu-id="5570c-104">イベント*ハンドラー*は、イベントに応答するために記述するコードです。</span><span class="sxs-lookup"><span data-stu-id="5570c-104">An *event handler* is the code you write to respond to an event.</span></span>

 <span data-ttu-id="5570c-105">Visual Basic のイベントハンドラーは、`Sub` プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="5570c-105">An event handler in Visual Basic is a `Sub` procedure.</span></span> <span data-ttu-id="5570c-106">ただし、通常、他の `Sub` プロシージャと同じ方法で呼び出すことはありません。</span><span class="sxs-lookup"><span data-stu-id="5570c-106">However, you do not normally call it the same way as other `Sub` procedures.</span></span> <span data-ttu-id="5570c-107">代わりに、プロシージャをイベントのハンドラーとして指定します。</span><span class="sxs-lookup"><span data-stu-id="5570c-107">Instead, you identify the procedure as a handler for the event.</span></span> <span data-ttu-id="5570c-108">これは、 [Handles](../../../language-reference/statements/handles-clause.md)句と[WithEvents](../../../language-reference/modifiers/withevents.md)変数、または[AddHandler ステートメント](../../../language-reference/statements/addhandler-statement.md)を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5570c-108">You can do this either with a [Handles](../../../language-reference/statements/handles-clause.md) clause and a [WithEvents](../../../language-reference/modifiers/withevents.md) variable, or with an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="5570c-109">`Handles` 句の使用は、Visual Basic でイベントハンドラーを宣言する既定の方法です。</span><span class="sxs-lookup"><span data-stu-id="5570c-109">Using a `Handles` clause is the default way to declare an event handler in Visual Basic.</span></span> <span data-ttu-id="5570c-110">これは、統合開発環境 (IDE: integrated development environment) でプログラミングするときに、デザイナーによってイベントハンドラーが記述される方法です。</span><span class="sxs-lookup"><span data-stu-id="5570c-110">This is the way the event handlers are written by the designers when you program in the integrated development environment (IDE).</span></span> <span data-ttu-id="5570c-111">`AddHandler` ステートメントは、実行時にイベントを動的に発生させるのに適しています。</span><span class="sxs-lookup"><span data-stu-id="5570c-111">The `AddHandler` statement is suitable for raising events dynamically at run time.</span></span>

 <span data-ttu-id="5570c-112">イベントが発生すると、Visual Basic によってイベントハンドラープロシージャが自動的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5570c-112">When the event occurs, Visual Basic automatically calls the event handler procedure.</span></span> <span data-ttu-id="5570c-113">イベントにアクセスできるコードでは、 [RaiseEvent ステートメント](../../../language-reference/statements/raiseevent-statement.md)を実行することによってイベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5570c-113">Any code that has access to the event can cause it to occur by executing a [RaiseEvent Statement](../../../language-reference/statements/raiseevent-statement.md).</span></span>

 <span data-ttu-id="5570c-114">複数のイベントハンドラーを同じイベントに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5570c-114">You can associate more than one event handler with the same event.</span></span> <span data-ttu-id="5570c-115">場合によっては、イベントからハンドラーの関連付けを解除できます。</span><span class="sxs-lookup"><span data-stu-id="5570c-115">In some cases you can dissociate a handler from an event.</span></span> <span data-ttu-id="5570c-116">詳細については、「[イベント](../events/index.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。</span><span class="sxs-lookup"><span data-stu-id="5570c-116">For more information, see [Events](../events/index.md).</span></span>

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a><span data-ttu-id="5570c-117">ハンドルと WithEvents を使用してイベントハンドラーを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="5570c-117">To call an event handler using Handles and WithEvents</span></span>

1. <span data-ttu-id="5570c-118">イベントが [Event ステートメント](../../../language-reference/statements/event-statement.md)を使用して宣言されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5570c-118">Make sure the event is declared with an [Event Statement](../../../language-reference/statements/event-statement.md).</span></span>

2. <span data-ttu-id="5570c-119">[WithEvents](../../../language-reference/modifiers/withevents.md)キーワードを使用して、モジュールまたはクラスレベルでオブジェクト変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="5570c-119">Declare an object variable at module or class level, using the [WithEvents](../../../language-reference/modifiers/withevents.md) keyword.</span></span> <span data-ttu-id="5570c-120">この変数の `As` 句には、イベントを発生させるクラスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5570c-120">The `As` clause for this variable must specify the class that raises the event.</span></span>

3. <span data-ttu-id="5570c-121">イベント処理 `Sub` プロシージャの宣言で、`WithEvents` 変数とイベント名を指定する[Handles](../../../language-reference/statements/handles-clause.md)句を追加します。</span><span class="sxs-lookup"><span data-stu-id="5570c-121">In the declaration of the event-handling `Sub` procedure, add a [Handles](../../../language-reference/statements/handles-clause.md) clause that specifies the `WithEvents` variable and the event name.</span></span>

4. <span data-ttu-id="5570c-122">イベントが発生すると、Visual Basic は `Sub` プロシージャを自動的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5570c-122">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="5570c-123">コードでは、`RaiseEvent` ステートメントを使用してイベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="5570c-123">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="5570c-124">次の例では、イベントを定義し、イベントを発生させるクラスを参照する `WithEvents` 変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="5570c-124">The following example defines an event and a `WithEvents` variable that refers to the class that raises the event.</span></span> <span data-ttu-id="5570c-125">イベント処理 `Sub` プロシージャは、`Handles` 句を使用して、処理するクラスとイベントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5570c-125">The event-handling `Sub` procedure uses a `Handles` clause to specify the class and event it handles.</span></span>

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a><span data-ttu-id="5570c-126">AddHandler を使用してイベントハンドラーを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="5570c-126">To call an event handler using AddHandler</span></span>

1. <span data-ttu-id="5570c-127">`Event` ステートメントを使用してイベントが宣言されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5570c-127">Make sure the event is declared with an `Event` statement.</span></span>

2. <span data-ttu-id="5570c-128">[AddHandler ステートメント](../../../language-reference/statements/addhandler-statement.md)を実行して、イベント処理 `Sub` プロシージャをイベントに動的に接続します。</span><span class="sxs-lookup"><span data-stu-id="5570c-128">Execute an [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to dynamically connect the event-handling `Sub` procedure with the event.</span></span>

3. <span data-ttu-id="5570c-129">イベントが発生すると、Visual Basic は `Sub` プロシージャを自動的に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5570c-129">When the event occurs, Visual Basic automatically calls the `Sub` procedure.</span></span> <span data-ttu-id="5570c-130">コードでは、`RaiseEvent` ステートメントを使用してイベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="5570c-130">Your code can use a `RaiseEvent` statement to make the event occur.</span></span>

     <span data-ttu-id="5570c-131">次の例では、フォームの <xref:System.Windows.Forms.Form.Closing> イベントを処理するための `Sub` プロシージャを定義します。</span><span class="sxs-lookup"><span data-stu-id="5570c-131">The following example defines a `Sub` procedure to handle the <xref:System.Windows.Forms.Form.Closing> event of a form.</span></span> <span data-ttu-id="5570c-132">次に、 [AddHandler ステートメント](../../../language-reference/statements/addhandler-statement.md)を使用して、`catchClose` プロシージャを <xref:System.Windows.Forms.Form.Closing>のイベントハンドラーとして関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5570c-132">It then uses the [AddHandler Statement](../../../language-reference/statements/addhandler-statement.md) to associate the `catchClose` procedure as an event handler for <xref:System.Windows.Forms.Form.Closing>.</span></span>

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     <span data-ttu-id="5570c-133">[RemoveHandler ステートメント](../../../language-reference/statements/removehandler-statement.md)を実行すると、イベントからイベントハンドラーの関連付けを解除できます。</span><span class="sxs-lookup"><span data-stu-id="5570c-133">You can dissociate an event handler from an event by executing the [RemoveHandler Statement](../../../language-reference/statements/removehandler-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5570c-134">参照</span><span class="sxs-lookup"><span data-stu-id="5570c-134">See also</span></span>

- [<span data-ttu-id="5570c-135">Visual Basic におけるプロシージャ</span><span class="sxs-lookup"><span data-stu-id="5570c-135">Procedures</span></span>](index.md)
- [<span data-ttu-id="5570c-136">Sub プロシージャ</span><span class="sxs-lookup"><span data-stu-id="5570c-136">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="5570c-137">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="5570c-137">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5570c-138">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="5570c-138">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="5570c-139">方法 : プロシージャを作成する</span><span class="sxs-lookup"><span data-stu-id="5570c-139">How to: Create a Procedure</span></span>](how-to-create-a-procedure.md)
- [<span data-ttu-id="5570c-140">方法 : 値を返さないプロシージャを呼び出す</span><span class="sxs-lookup"><span data-stu-id="5570c-140">How to: Call a Procedure that Does Not Return a Value</span></span>](how-to-call-a-procedure-that-does-not-return-a-value.md)
