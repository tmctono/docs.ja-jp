---
title: イベントの処理 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 12267e0a70419298bc581421c4f3a220088d205f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956309"
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="8aeea-102">チュートリアル: イベントの処理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8aeea-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="8aeea-103">これは、イベントを操作する方法を示す2つのトピックのうち2番目のトピックです。</span><span class="sxs-lookup"><span data-stu-id="8aeea-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="8aeea-104">最初のトピック[「チュートリアル:イベント](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)の宣言と発生、イベントを宣言して発生させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="8aeea-105">このセクションでは、そのチュートリアルのフォームとクラスを使用して、発生したイベントの処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="8aeea-106">クラス`Widget`の例では、従来のイベント処理ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="8aeea-107">Visual Basic には、イベントを操作するためのその他の手法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8aeea-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="8aeea-108">演習として、この例を変更`AddHandler`して、ステートメントと`Handles`ステートメントを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="8aeea-109">ウィジェットクラスの PercentDone イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="8aeea-109">To handle the PercentDone event of the Widget class</span></span>  
  
1. <span data-ttu-id="8aeea-110">に`Form1`次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     <span data-ttu-id="8aeea-111">キーワードは、変数`mWidget`がオブジェクトのイベントを処理するために使用されることを指定します。 `WithEvents`</span><span class="sxs-lookup"><span data-stu-id="8aeea-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="8aeea-112">オブジェクトの種類を指定するには、オブジェクトの作成元となるクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="8aeea-113">変数はクラスレベルで`Form1`ある`WithEvents`必要があるため、ではとして宣言されています。 `mWidget`</span><span class="sxs-lookup"><span data-stu-id="8aeea-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="8aeea-114">これは、配置したクラスの型に関係なく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="8aeea-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="8aeea-115">変数`mblnCancel`は、 `LongTask`メソッドを取り消すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="8aeea-116">イベントを処理するコードの記述</span><span class="sxs-lookup"><span data-stu-id="8aeea-116">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="8aeea-117">を使用し`WithEvents`て変数を宣言するとすぐに、クラスの**コードエディター**の左側のドロップダウンリストに変数名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="8aeea-118">を選択`mWidget`すると、 `Widget`クラスのイベントが右のドロップダウンリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="8aeea-119">イベントを選択すると、対応するイベントプロシージャがプレフィックス`mWidget`とアンダースコア付きで表示されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="8aeea-120">`WithEvents`変数に関連付けられているすべてのイベントプロシージャには、プレフィックスとして変数名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="8aeea-121">イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="8aeea-121">To handle an event</span></span>  
  
1. <span data-ttu-id="8aeea-122">`mWidget` **コードエディター**の左側のドロップダウンリストからを選択します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="8aeea-123">右側のドロップダウンリストからイベントを選択します。`PercentDone`</span><span class="sxs-lookup"><span data-stu-id="8aeea-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="8aeea-124">**コードエディター**で`mWidget_PercentDone`イベントプロシージャが開きます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8aeea-125">**コードエディター**は、新しいイベントハンドラーを挿入する場合には便利ですが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="8aeea-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="8aeea-126">このチュートリアルでは、コードに直接イベントハンドラーをコピーするだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3. <span data-ttu-id="8aeea-127">`mWidget_PercentDone` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     <span data-ttu-id="8aeea-128">イベントが`PercentDone`発生するたびに、イベントプロシージャによって`Label`コントロールの完了率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="8aeea-129">メソッドを使用すると、ラベルを再描画できます。また、ユーザーは [キャンセル] ボタンをクリックすることもできます。 `DoEvents`</span><span class="sxs-lookup"><span data-stu-id="8aeea-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="8aeea-130">`Button2_Click`イベントハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 <span data-ttu-id="8aeea-131">が実行`LongTask` `DoEvents`されているときにユーザーが **[キャンセル**] ボタンをクリックすると、イベントは、ステートメントによってイベント処理が許可されるとすぐに実行されます。 `Button2_Click`</span><span class="sxs-lookup"><span data-stu-id="8aeea-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="8aeea-132">クラスレベル`mblnCancel`変数がに`mWidget_PercentDone` `True`設定されている場合、イベントはそれをテストし`ByRef Cancel` 、引数`True`をに設定します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="8aeea-133">WithEvents 変数をオブジェクトに接続する</span><span class="sxs-lookup"><span data-stu-id="8aeea-133">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="8aeea-134">`Form1`は、オブジェクトのイベントを`Widget`処理するように設定されました。</span><span class="sxs-lookup"><span data-stu-id="8aeea-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="8aeea-135">残っているのは、 `Widget`どこかを見つけることだけです。</span><span class="sxs-lookup"><span data-stu-id="8aeea-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="8aeea-136">デザイン時に変数`WithEvents`を宣言しても、オブジェクトにはオブジェクトが関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="8aeea-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="8aeea-137">変数`WithEvents`は、他のオブジェクト変数と同じです。</span><span class="sxs-lookup"><span data-stu-id="8aeea-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="8aeea-138">オブジェクトを作成し、そのオブジェクトへの`WithEvents`参照を変数で割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8aeea-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="8aeea-139">オブジェクトを作成し、そのオブジェクトへの参照を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8aeea-139">To create an object and assign a reference to it</span></span>  
  
1. <span data-ttu-id="8aeea-140">**コードエディター**の左側のドロップダウンリストで **[(Form1 イベント)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="8aeea-141">右側のドロップダウンリストからイベントを選択します。`Load`</span><span class="sxs-lookup"><span data-stu-id="8aeea-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="8aeea-142">**コードエディター**で`Form1_Load`イベントプロシージャが開きます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3. <span data-ttu-id="8aeea-143">`Form1_Load`イベントプロシージャに次のコードを追加して、 `Widget`を作成します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 <span data-ttu-id="8aeea-144">このコードが実行されると、 `Widget` Visual Basic がオブジェクトを作成し、そのイベントをに`mWidget`関連付けられたイベントプロシージャに接続します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="8aeea-145">その時点から、によっ`Widget`て`PercentDone`イベント`mWidget_PercentDone`が発生するたびに、イベントプロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="8aeea-146">LongTask メソッドを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="8aeea-146">To call the LongTask method</span></span>  
  
- <span data-ttu-id="8aeea-147">`Button1_Click` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 <span data-ttu-id="8aeea-148">メソッドが呼び出される前に、完了率を示すラベルを初期化する必要があります。また、 `Boolean`メソッドをキャンセルするためのクラスレベルの`False`フラグをに設定する必要があります。 `LongTask`</span><span class="sxs-lookup"><span data-stu-id="8aeea-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="8aeea-149">`LongTask`は、タスク期間が12.2 秒の場合に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="8aeea-150">`PercentDone`イベントは、1秒間に1回発生します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="8aeea-151">イベントが発生するたびに`mWidget_PercentDone` 、イベントプロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="8aeea-152">が`LongTask`終了すると`mblnCancel` 、 `LongTask`は、が正常に終了したかどうか、 `mblnCancel`またはが`True`に設定されたために停止したかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="8aeea-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="8aeea-153">完了率は、前者の場合にのみ更新されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="8aeea-154">プログラムを実行するには</span><span class="sxs-lookup"><span data-stu-id="8aeea-154">To run the program</span></span>  
  
1. <span data-ttu-id="8aeea-155">F5 キーを押して、プロジェクトを実行モードにします。</span><span class="sxs-lookup"><span data-stu-id="8aeea-155">Press F5 to put the project in run mode.</span></span>  
  
2. <span data-ttu-id="8aeea-156">**[タスクの開始]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8aeea-156">Click the **Start Task** button.</span></span> <span data-ttu-id="8aeea-157">`PercentDone`イベントが発生するたびに、ラベルは、完了したタスクの割合で更新されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3. <span data-ttu-id="8aeea-158">**[キャンセル]** ボタンをクリックして、タスクを停止します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="8aeea-159">**[キャンセル]** ボタンの外観は、クリックしてもすぐには変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8aeea-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="8aeea-160">イベント`Click`は、ステートメントによっ`My.Application.DoEvents`てイベント処理が許可されるまで発生しません。</span><span class="sxs-lookup"><span data-stu-id="8aeea-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8aeea-161">`My.Application.DoEvents`メソッドは、フォームとまったく同じ方法でイベントを処理しません。</span><span class="sxs-lookup"><span data-stu-id="8aeea-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="8aeea-162">たとえば、このチュートリアルでは、 **[キャンセル]** ボタンを2回クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8aeea-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="8aeea-163">フォームがイベントを直接処理できるようにするには、マルチスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="8aeea-164">詳細については、「[マネージスレッド処理](../../../../standard/threading/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aeea-164">For more information, see [Managed Threading](../../../../standard/threading/index.md).</span></span>
  
 <span data-ttu-id="8aeea-165">F11 キーを使用してプログラムを実行し、一度に1行ずつコードをステップ実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8aeea-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="8aeea-166">実行`LongTask`がどのように行われるかを明確に確認し、 `Form1` `PercentDone`イベントが発生するたびに簡単に再入力することができます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="8aeea-167">`Form1`の`LongTask`コードで実行が戻ったときに、メソッドが再度呼び出された場合はどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="8aeea-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="8aeea-168">最悪の場合`LongTask` 、イベントが発生するたびにが呼び出されると、スタックオーバーフローが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8aeea-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="8aeea-169">`mWidget` `Widget`新しい`mWidget`への参照をに割り当てることによって、変数が別のオブジェクトのイベントを処理するようにすることができます。 `Widget`</span><span class="sxs-lookup"><span data-stu-id="8aeea-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="8aeea-170">実際には、ボタンをクリックするたび`Button1_Click`に、このコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="8aeea-171">別のウィジェットのイベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="8aeea-171">To handle events for a different widget</span></span>  
  
- <span data-ttu-id="8aeea-172">`Button1_Click`プロシージャに次のコード行を追加し`mWidget.LongTask(12.2, 0.33)`ます。行の直前にを記述します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 <span data-ttu-id="8aeea-173">上記のコードでは、 `Widget`ボタンがクリックされるたびに新しいが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="8aeea-174">`LongTask`メソッドが完了するとすぐに、への`Widget`参照`Widget`が解放され、が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="8aeea-175">変数には一度に1つのオブジェクト参照のみを含めることができます。 `Widget`したがって`mWidget`、別の`Widget`オブジェクトをに割り当てると、前のオブジェクトのイベントは処理されなくなります。 `WithEvents`</span><span class="sxs-lookup"><span data-stu-id="8aeea-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="8aeea-176">が`mWidget` 古い`Widget`への参照を含む唯一のオブジェクト変数である場合は、オブジェクトが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="8aeea-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="8aeea-177">複数`Widget`のオブジェクトのイベントを処理する場合は、ステートメント`AddHandler`を使用して各オブジェクトのイベントを個別に処理します。</span><span class="sxs-lookup"><span data-stu-id="8aeea-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8aeea-178">必要な数`WithEvents`の変数を宣言できますが、変数の`WithEvents`配列はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8aeea-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aeea-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="8aeea-179">See also</span></span>

- [<span data-ttu-id="8aeea-180">チュートリアル: イベントの宣言と発生</span><span class="sxs-lookup"><span data-stu-id="8aeea-180">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [<span data-ttu-id="8aeea-181">イベント</span><span class="sxs-lookup"><span data-stu-id="8aeea-181">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
