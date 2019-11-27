---
title: イベントの処理
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: cb42f2e41e366cf8765cb9395d1a5641434bab40
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345084"
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="694ad-102">チュートリアル: イベントの処理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="694ad-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="694ad-103">これは、イベントを操作する方法を示す2つのトピックのうち2番目のトピックです。</span><span class="sxs-lookup"><span data-stu-id="694ad-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="694ad-104">最初のトピック「[チュートリアル: イベントの宣言と発生](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)」では、イベントを宣言して発生させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="694ad-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="694ad-105">このセクションでは、そのチュートリアルのフォームとクラスを使用して、発生したイベントの処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="694ad-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="694ad-106">`Widget` クラスの例では、従来のイベント処理ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="694ad-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="694ad-107">Visual Basic には、イベントを操作するためのその他の手法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="694ad-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="694ad-108">演習として、この例を変更して、`AddHandler` および `Handles` ステートメントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="694ad-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="694ad-109">ウィジェットクラスの PercentDone イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="694ad-109">To handle the PercentDone event of the Widget class</span></span>  
  
1. <span data-ttu-id="694ad-110">`Form1`に次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="694ad-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     <span data-ttu-id="694ad-111">`WithEvents` キーワードは、オブジェクトのイベントを処理するために `mWidget` 変数が使用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="694ad-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="694ad-112">オブジェクトの種類を指定するには、オブジェクトの作成元となるクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="694ad-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="694ad-113">変数 `mWidget` は `Form1` で宣言されています。 `WithEvents` 変数はクラスレベルである必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="694ad-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="694ad-114">これは、配置したクラスの型に関係なく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="694ad-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="694ad-115">`LongTask` メソッドを取り消すには、`mblnCancel` 変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="694ad-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="694ad-116">イベントを処理するコードの記述</span><span class="sxs-lookup"><span data-stu-id="694ad-116">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="694ad-117">`WithEvents`を使用して変数を宣言するとすぐに、クラスの**コードエディター**の左側のドロップダウンリストに変数名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="694ad-118">[`mWidget`] を選択すると、`Widget` クラスのイベントが右のドロップダウンリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="694ad-119">イベントを選択すると、対応するイベントプロシージャにプレフィックス `mWidget` とアンダースコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="694ad-120">`WithEvents` 変数に関連付けられているすべてのイベントプロシージャには、プレフィックスとして変数名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="694ad-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="694ad-121">イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="694ad-121">To handle an event</span></span>  
  
1. <span data-ttu-id="694ad-122">**コードエディター**の左側のドロップダウンリストから [`mWidget`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="694ad-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="694ad-123">右側のドロップダウンリストから `PercentDone` イベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="694ad-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="694ad-124">**コードエディター**で、`mWidget_PercentDone` イベントプロシージャが開きます。</span><span class="sxs-lookup"><span data-stu-id="694ad-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="694ad-125">**コードエディター**は、新しいイベントハンドラーを挿入する場合には便利ですが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="694ad-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="694ad-126">このチュートリアルでは、コードに直接イベントハンドラーをコピーするだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="694ad-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3. <span data-ttu-id="694ad-127">`mWidget_PercentDone` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="694ad-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     <span data-ttu-id="694ad-128">イベントプロシージャは、`PercentDone` イベントが発生するたびに、`Label` コントロールの完了率を表示します。</span><span class="sxs-lookup"><span data-stu-id="694ad-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="694ad-129">`DoEvents` メソッドを使用すると、ラベルを再描画できます。また、ユーザーは **[キャンセル]** ボタンをクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="694ad-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="694ad-130">`Button2_Click` イベントハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="694ad-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 <span data-ttu-id="694ad-131">`LongTask` の実行中にユーザーが **[キャンセル**] ボタンをクリックした場合、`DoEvents` ステートメントによってイベント処理が可能になるとすぐに、`Button2_Click` イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="694ad-132">クラスレベルの変数 `mblnCancel` が `True`に設定され、`mWidget_PercentDone` イベントによってテストされ、`ByRef Cancel` 引数が `True`に設定されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="694ad-133">WithEvents 変数をオブジェクトに接続する</span><span class="sxs-lookup"><span data-stu-id="694ad-133">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="694ad-134">`Form1` は、`Widget` オブジェクトのイベントを処理するようにセットアップされました。</span><span class="sxs-lookup"><span data-stu-id="694ad-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="694ad-135">残っているのは、どこかの `Widget` を見つけることだけです。</span><span class="sxs-lookup"><span data-stu-id="694ad-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="694ad-136">デザイン時に `WithEvents` 変数を宣言しても、オブジェクトにはオブジェクトが関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="694ad-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="694ad-137">`WithEvents` 変数は、他のオブジェクト変数と同じです。</span><span class="sxs-lookup"><span data-stu-id="694ad-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="694ad-138">オブジェクトを作成し、そのオブジェクトへの参照を `WithEvents` 変数で割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="694ad-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="694ad-139">オブジェクトを作成し、そのオブジェクトへの参照を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="694ad-139">To create an object and assign a reference to it</span></span>  
  
1. <span data-ttu-id="694ad-140">**コードエディター**の左側のドロップダウンリストで **[(Form1 イベント)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="694ad-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="694ad-141">右側のドロップダウンリストから `Load` イベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="694ad-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="694ad-142">**コードエディター**で、`Form1_Load` イベントプロシージャが開きます。</span><span class="sxs-lookup"><span data-stu-id="694ad-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3. <span data-ttu-id="694ad-143">`Widget`を作成するには、`Form1_Load` イベントプロシージャに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="694ad-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 <span data-ttu-id="694ad-144">このコードが実行されると、Visual Basic は `Widget` オブジェクトを作成し、そのイベントを `mWidget`に関連付けられているイベントプロシージャに接続します。</span><span class="sxs-lookup"><span data-stu-id="694ad-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="694ad-145">その時点から、`Widget` が `PercentDone` イベントを発生させるたびに、`mWidget_PercentDone` イベントプロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="694ad-146">LongTask メソッドを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="694ad-146">To call the LongTask method</span></span>  
  
- <span data-ttu-id="694ad-147">`Button1_Click` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="694ad-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 <span data-ttu-id="694ad-148">`LongTask` メソッドが呼び出される前に、完了率を示すラベルを初期化する必要があります。また、メソッドをキャンセルするためのクラスレベルの `Boolean` フラグを `False`に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="694ad-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="694ad-149">`LongTask` は、タスク期間が12.2 秒の場合に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="694ad-150">`PercentDone` イベントは、1秒間に1回発生します。</span><span class="sxs-lookup"><span data-stu-id="694ad-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="694ad-151">イベントが発生するたびに、`mWidget_PercentDone` イベントプロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="694ad-152">`LongTask` が完了すると、`mblnCancel` は `LongTask` が正常に終了したかどうか、または `mblnCancel` が `True`に設定されているために停止したかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="694ad-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="694ad-153">完了率は、前者の場合にのみ更新されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="694ad-154">プログラムを実行するには</span><span class="sxs-lookup"><span data-stu-id="694ad-154">To run the program</span></span>  
  
1. <span data-ttu-id="694ad-155">F5 キーを押して、プロジェクトを実行モードにします。</span><span class="sxs-lookup"><span data-stu-id="694ad-155">Press F5 to put the project in run mode.</span></span>  
  
2. <span data-ttu-id="694ad-156">**[タスクの開始]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="694ad-156">Click the **Start Task** button.</span></span> <span data-ttu-id="694ad-157">`PercentDone` イベントが発生するたびに、完了したタスクの割合でラベルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3. <span data-ttu-id="694ad-158">**[キャンセル]** ボタンをクリックして、タスクを停止します。</span><span class="sxs-lookup"><span data-stu-id="694ad-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="694ad-159">**[キャンセル]** ボタンの外観は、クリックしてもすぐには変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="694ad-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="694ad-160">`My.Application.DoEvents` ステートメントによってイベント処理が許可されるまで、`Click` イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="694ad-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="694ad-161">`My.Application.DoEvents` メソッドは、フォームとまったく同じ方法でイベントを処理しません。</span><span class="sxs-lookup"><span data-stu-id="694ad-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="694ad-162">たとえば、このチュートリアルでは、 **[キャンセル]** ボタンを2回クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="694ad-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="694ad-163">フォームがイベントを直接処理できるようにするには、マルチスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="694ad-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="694ad-164">詳細については、「[マネージスレッド処理](../../../../standard/threading/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="694ad-164">For more information, see [Managed Threading](../../../../standard/threading/index.md).</span></span>
  
 <span data-ttu-id="694ad-165">F11 キーを使用してプログラムを実行し、一度に1行ずつコードをステップ実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="694ad-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="694ad-166">`LongTask`実行がどのようになるかを明確に確認し、`PercentDone` イベントが発生するたびに `Form1` を再入力することができます。</span><span class="sxs-lookup"><span data-stu-id="694ad-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="694ad-167">`Form1`のコードで実行が戻ったときに、`LongTask` メソッドが再度呼び出された場合はどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="694ad-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="694ad-168">最悪の場合、イベントが発生するたびに `LongTask` が呼び出されると、スタックオーバーフローが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="694ad-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="694ad-169">新しい `Widget` への参照を `mWidget`に割り当てることによって、変数 `mWidget` が別の `Widget` オブジェクトのイベントを処理するようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="694ad-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="694ad-170">実際には、ボタンをクリックするたびに、`Button1_Click` コードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="694ad-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="694ad-171">別のウィジェットのイベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="694ad-171">To handle events for a different widget</span></span>  
  
- <span data-ttu-id="694ad-172">`mWidget.LongTask(12.2, 0.33)`を読み取る行の直前に、次のコード行を `Button1_Click` プロシージャに追加します。</span><span class="sxs-lookup"><span data-stu-id="694ad-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 <span data-ttu-id="694ad-173">上記のコードでは、ボタンがクリックされるたびに新しい `Widget` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="694ad-174">`LongTask` メソッドが完了するとすぐに、`Widget` への参照が解放され、`Widget` が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="694ad-175">`WithEvents` 変数には一度に1つのオブジェクト参照のみを含めることができます。したがって、別の `Widget` オブジェクトを `mWidget`に割り当てると、前の `Widget` オブジェクトのイベントは処理されなくなります。</span><span class="sxs-lookup"><span data-stu-id="694ad-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="694ad-176">`mWidget` が古い `Widget`への参照を含む唯一のオブジェクト変数である場合、オブジェクトは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="694ad-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="694ad-177">複数の `Widget` オブジェクトのイベントを処理する場合は、`AddHandler` ステートメントを使用して各オブジェクトのイベントを個別に処理します。</span><span class="sxs-lookup"><span data-stu-id="694ad-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="694ad-178">`WithEvents` 変数は必要な数だけ宣言できますが、`WithEvents` 変数の配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="694ad-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="694ad-179">参照</span><span class="sxs-lookup"><span data-stu-id="694ad-179">See also</span></span>

- [<span data-ttu-id="694ad-180">チュートリアル : イベントの宣言と発生</span><span class="sxs-lookup"><span data-stu-id="694ad-180">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [<span data-ttu-id="694ad-181">イベント</span><span class="sxs-lookup"><span data-stu-id="694ad-181">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
