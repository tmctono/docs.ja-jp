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
ms.openlocfilehash: 2ae32f0ac31c504e86d5cf39ed6a36cc5523a4a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053796"
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="4e914-102">チュートリアル: イベントの処理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e914-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="4e914-103">これは、2 番目のイベントを使用する方法を示す 2 つのトピックです。</span><span class="sxs-lookup"><span data-stu-id="4e914-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="4e914-104">最初のトピックでは、[チュートリアル。イベントを宣言して発生](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)を宣言してイベントを発生させる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4e914-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="4e914-105">このセクションでは、実行するときにイベントを処理するのに方法について説明フォームとそのチュートリアルからクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e914-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="4e914-106">`Widget`クラスの例は、従来のイベント処理ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e914-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="4e914-107">Visual Basic では、イベントの処理を他の手法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e914-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="4e914-108">演習として使用するには、この例を変更することができます、`AddHandler`と`Handles`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="4e914-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="4e914-109">ウィジェットのクラスのことですイベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="4e914-109">To handle the PercentDone event of the Widget class</span></span>  
  
1. <span data-ttu-id="4e914-110">次のコードを配置`Form1`:</span><span class="sxs-lookup"><span data-stu-id="4e914-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     <span data-ttu-id="4e914-111">`WithEvents`キーワードを指定する変数`mWidget`オブジェクトのイベントを処理するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4e914-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="4e914-112">オブジェクトの種類を指定するには、オブジェクトを作成するクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e914-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="4e914-113">変数`mWidget`で宣言されている`Form1`ため`WithEvents`変数はクラス レベルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e914-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="4e914-114">これはクラスの配置の種類に関係なく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="4e914-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="4e914-115">変数`mblnCancel`をキャンセルするために使用、`LongTask`メソッド。</span><span class="sxs-lookup"><span data-stu-id="4e914-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="4e914-116">イベントを処理するコードの記述</span><span class="sxs-lookup"><span data-stu-id="4e914-116">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="4e914-117">使用して変数を宣言するとすぐに`WithEvents`、クラスの左側のドロップダウン リストで、変数名が表示されます。**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="4e914-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="4e914-118">選択すると`mWidget`、`Widget`クラスのイベントが右のドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e914-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="4e914-119">イベントを選択するには、プレフィックスを持つ、対応するイベント プロシージャが表示されます`mWidget`とアンダー スコア。</span><span class="sxs-lookup"><span data-stu-id="4e914-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="4e914-120">関連付けられているすべてのイベント プロシージャを`WithEvents`変数は、プレフィックスとして変数名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e914-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="4e914-121">イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="4e914-121">To handle an event</span></span>  
  
1. <span data-ttu-id="4e914-122">選択`mWidget`で、左側のドロップダウン リストから、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="4e914-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="4e914-123">選択、`PercentDone`右のドロップダウン リストからイベント。</span><span class="sxs-lookup"><span data-stu-id="4e914-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="4e914-124">**コード エディター**開きます、`mWidget_PercentDone`イベント プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="4e914-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4e914-125">**コード エディター**は役立ちますが、新しいイベント ハンドラーを挿入するための必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4e914-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="4e914-126">このチュートリアルでは、イベント ハンドラーのコードに直接コピーするより直接的します。</span><span class="sxs-lookup"><span data-stu-id="4e914-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3. <span data-ttu-id="4e914-127">`mWidget_PercentDone` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e914-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     <span data-ttu-id="4e914-128">たびに、`PercentDone`イベントは、イベント プロシージャの完了率が表示されます、`Label`コントロール。</span><span class="sxs-lookup"><span data-stu-id="4e914-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="4e914-129">`DoEvents`メソッドを再描画するラベルを使用し、また、ユーザーがクリックする可能性、**キャンセル**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e914-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="4e914-130">次のコードを追加、`Button2_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="4e914-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 <span data-ttu-id="4e914-131">ユーザーがクリックした場合、**キャンセル**中にボタン`LongTask`が実行されている、`Button2_Click`イベントが実行されるとすぐに、`DoEvents`ステートメントが発生するイベントの処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e914-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="4e914-132">クラス レベルの変数`mblnCancel`に設定されている`True`、および`mWidget_PercentDone`イベントは、ためのテストし、設定、`ByRef Cancel`引数`True`。</span><span class="sxs-lookup"><span data-stu-id="4e914-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="4e914-133">WithEvents 変数をオブジェクトに接続します。</span><span class="sxs-lookup"><span data-stu-id="4e914-133">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="4e914-134">`Form1` 処理するために設定するようになりました、`Widget`オブジェクトのイベント。</span><span class="sxs-lookup"><span data-stu-id="4e914-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="4e914-135">残っているは検索、`Widget`どこか。</span><span class="sxs-lookup"><span data-stu-id="4e914-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="4e914-136">変数を宣言するときに`WithEvents`デザイン時にオブジェクトが関連付けられていないこと。</span><span class="sxs-lookup"><span data-stu-id="4e914-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="4e914-137">A`WithEvents`変数は、他のすべてのオブジェクト変数と同じです。</span><span class="sxs-lookup"><span data-stu-id="4e914-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="4e914-138">オブジェクトを作成しを使って参照を代入する必要がある、`WithEvents`変数。</span><span class="sxs-lookup"><span data-stu-id="4e914-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="4e914-139">オブジェクトを作成してへの参照を割り当てる</span><span class="sxs-lookup"><span data-stu-id="4e914-139">To create an object and assign a reference to it</span></span>  
  
1. <span data-ttu-id="4e914-140">選択 **(Form1 イベント)** で、左側のドロップダウン リストから、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="4e914-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="4e914-141">選択、`Load`右のドロップダウン リストからイベント。</span><span class="sxs-lookup"><span data-stu-id="4e914-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="4e914-142">**コード エディター**開きます、`Form1_Load`イベント プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="4e914-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3. <span data-ttu-id="4e914-143">次のコードを追加、`Form1_Load`イベント プロシージャを作成、 `Widget`:</span><span class="sxs-lookup"><span data-stu-id="4e914-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 <span data-ttu-id="4e914-144">このコードが実行されると、Visual Basic を作成、`Widget`オブジェクトし、そのイベントを接続に関連付けられているイベント プロシージャに`mWidget`します。</span><span class="sxs-lookup"><span data-stu-id="4e914-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="4e914-145">した時点で、ときに、`Widget`を発生させますその`PercentDone`、イベント、`mWidget_PercentDone`イベント プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e914-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="4e914-146">LongTask メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="4e914-146">To call the LongTask method</span></span>  
  
- <span data-ttu-id="4e914-147">`Button1_Click` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e914-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 <span data-ttu-id="4e914-148">前に、`LongTask`メソッドが呼び出されると、ラベルの表示が完了した割合を初期化する必要があり、クラス レベル`Boolean`フラグ設定するメソッドをキャンセルする必要があります`False`します。</span><span class="sxs-lookup"><span data-stu-id="4e914-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="4e914-149">`LongTask` 12.2 秒のタスクの実行時間と呼びます。</span><span class="sxs-lookup"><span data-stu-id="4e914-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="4e914-150">`PercentDone`イベントは、1 回ごとに 3 分の 1、2 つ目の。</span><span class="sxs-lookup"><span data-stu-id="4e914-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="4e914-151">イベントが発生すると、毎回、`mWidget_PercentDone`イベント プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e914-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="4e914-152">ときに`LongTask`が完了したら、`mblnCancel`かどうかをテスト`LongTask`通常は、終了したため、停止した場合、または`mblnCancel`に設定された`True`。</span><span class="sxs-lookup"><span data-stu-id="4e914-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="4e914-153">達成率は、前者の場合にのみ更新されます。</span><span class="sxs-lookup"><span data-stu-id="4e914-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="4e914-154">プログラムを実行するには</span><span class="sxs-lookup"><span data-stu-id="4e914-154">To run the program</span></span>  
  
1. <span data-ttu-id="4e914-155">F5 キーを押して、実行モードで、プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="4e914-155">Press F5 to put the project in run mode.</span></span>  
  
2. <span data-ttu-id="4e914-156">をクリックして、**タスクの開始**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e914-156">Click the **Start Task** button.</span></span> <span data-ttu-id="4e914-157">毎回、`PercentDone`イベントは、ラベルは、タスクが完了の割合で更新されます。</span><span class="sxs-lookup"><span data-stu-id="4e914-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3. <span data-ttu-id="4e914-158">をクリックして、**キャンセル**タスクを停止するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e914-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="4e914-159">注意の外観、**キャンセル**ボタンがクリックするとすぐには変更されません。</span><span class="sxs-lookup"><span data-stu-id="4e914-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="4e914-160">`Click`イベントまで発生することはできません、`My.Application.DoEvents`ステートメントは、イベント処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e914-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4e914-161">`My.Application.DoEvents`フォームは、メソッドがまったく同じ方法でイベントを処理できません。</span><span class="sxs-lookup"><span data-stu-id="4e914-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="4e914-162">たとえば、このチュートリアルでは、する必要があります をクリックして、**キャンセル**2 回ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e914-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="4e914-163">使用することができます、イベントを直接処理するためのフォームは、マルチ スレッドです。</span><span class="sxs-lookup"><span data-stu-id="4e914-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="4e914-164">詳細については、次を参照してください。[マネージ スレッド処理](../../../../standard/threading/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="4e914-164">For more information, see [Managed Threading](../../../../standard/threading/index.md).</span></span>
  
 <span data-ttu-id="4e914-165">F11 キーを押してプログラムを実行し、コードを 1 行ずつ処理するときにあります。</span><span class="sxs-lookup"><span data-stu-id="4e914-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="4e914-166">実行の入力を明確に確認`LongTask`、し、簡単に再入力`Form1`たびに、`PercentDone`イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="4e914-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="4e914-167">何が起こる場合、実行中のコードに戻る`Form1`、`LongTask`メソッドが再度呼び出されたでしょうか。</span><span class="sxs-lookup"><span data-stu-id="4e914-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="4e914-168">場合、スタック オーバーフローが発生する最悪の場合、`LongTask`イベントが発生するたびに呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="4e914-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="4e914-169">変数が可能性`mWidget`、別のイベントを処理する`Widget`新しいへの参照を割り当てることでオブジェクト`Widget`に`mWidget`します。</span><span class="sxs-lookup"><span data-stu-id="4e914-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="4e914-170">コードでは、実際には、行うことができます`Button1_Click`ボタンをクリックするたびにこの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4e914-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="4e914-171">別のウィジェットのイベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="4e914-171">To handle events for a different widget</span></span>  
  
- <span data-ttu-id="4e914-172">次のコードの行を追加、`Button1_Click`という行のすぐ前に、プロシージャ`mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="4e914-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 <span data-ttu-id="4e914-173">上記のコードを作成する新しい`Widget`たびにこのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e914-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="4e914-174">すぐに、`LongTask`メソッドが完了するへの参照、`Widget`がリリースされると、`Widget`は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="4e914-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="4e914-175">A`WithEvents`変数は、一度に 1 つのオブジェクト参照を含めることができます別に割り当てた場合、`Widget`オブジェクトを`mWidget`、前の`Widget`オブジェクトのイベントを処理できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4e914-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="4e914-176">場合`mWidget`古いへの参照を格納している唯一のオブジェクト変数`Widget`オブジェクトは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="4e914-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="4e914-177">いくつかのイベントを処理する場合`Widget`、オブジェクトを使用して、`AddHandler`ステートメントを個別に各オブジェクトからのイベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="4e914-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e914-178">数を宣言する`WithEvents`変数としてする必要がありますの配列が`WithEvents`変数がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4e914-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e914-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e914-179">See also</span></span>

- [<span data-ttu-id="4e914-180">チュートリアル: 宣言とイベントの発生</span><span class="sxs-lookup"><span data-stu-id="4e914-180">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [<span data-ttu-id="4e914-181">イベント</span><span class="sxs-lookup"><span data-stu-id="4e914-181">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
