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
ms.openlocfilehash: 4489f75e50a783a9b1acfb9c30568fdec6614488
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057911"
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="a8f06-102">チュートリアル: イベントの処理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8f06-102">Walkthrough: Handling Events (Visual Basic)</span></span>

<span data-ttu-id="a8f06-103">これは、イベントの処理方法について説明した 2 つのトピックのうちの 2 番目にあたります。</span><span class="sxs-lookup"><span data-stu-id="a8f06-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="a8f06-104">1 番目のトピックである「[チュートリアル: イベントの宣言と発生](walkthrough-declaring-and-raising-events.md)」では、イベントを宣言し、発生させる方法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="a8f06-104">The first topic, [Walkthrough: Declaring and Raising Events](walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="a8f06-105">このセクションでは、そのチュートリアルのフォームとクラスを使用して、イベントの発生時にそれらを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="a8f06-106">`Widget` クラスの例では、従来のイベント処理ステートメントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a8f06-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="a8f06-107">Visual Basic には、別のイベント処理手法も用意されています。</span><span class="sxs-lookup"><span data-stu-id="a8f06-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="a8f06-108">演習として、この例を変更し、`AddHandler` ステートメントと `Handles` ステートメントを使用してみましょう。</span><span class="sxs-lookup"><span data-stu-id="a8f06-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="a8f06-109">Widget クラスの PercentDone イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="a8f06-109">To handle the PercentDone event of the Widget class</span></span>  
  
1. <span data-ttu-id="a8f06-110">`Form1` に次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     <span data-ttu-id="a8f06-111">`WithEvents` キーワードにより、オブジェクトのイベントの処理に変数 `mWidget` が使用されるように指定しています。</span><span class="sxs-lookup"><span data-stu-id="a8f06-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="a8f06-112">オブジェクトの種類は、オブジェクトの作成元にするクラスの名前を記載することで指定します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="a8f06-113">`WithEvents` 変数はクラスレベルである必要があるため、変数 `mWidget` は `Form1` 内で宣言します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="a8f06-114">これは、挿入先のクラスの型に左右されません。</span><span class="sxs-lookup"><span data-stu-id="a8f06-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="a8f06-115">変数 `mblnCancel` は、`LongTask` メソッドを取り消すためのものです。</span><span class="sxs-lookup"><span data-stu-id="a8f06-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="a8f06-116">イベントを処理するコードの作成</span><span class="sxs-lookup"><span data-stu-id="a8f06-116">Writing Code to Handle an Event</span></span>  

 <span data-ttu-id="a8f06-117">`WithEvents` を使用して変数を宣言すると、このクラスの**コード エディター**の左側にあるドロップダウン リストに、その変数の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="a8f06-118">`mWidget` を選択すると、右側のドロップダウン リストに `Widget` クラスのイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="a8f06-119">イベントを選択すると、対応するイベント プロシージャが、接頭辞 `mWidget` とアンダースコア付きで表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="a8f06-120">`WithEvents` 変数に関連するすべてのイベント プロシージャに、変数名が接頭辞として付与されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="a8f06-121">イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="a8f06-121">To handle an event</span></span>  
  
1. <span data-ttu-id="a8f06-122">**コード エディター**の左側のドロップダウン リストで、[`mWidget`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="a8f06-123">右側のドロップダウン リストで `PercentDone` イベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="a8f06-124">**コード エディター**に `mWidget_PercentDone` イベント プロシージャが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a8f06-125">新しいイベント ハンドラーを挿入する場合、**コード エディター**は便利ですが、使用は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="a8f06-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="a8f06-126">今回のチュートリアルでは、コードにイベント ハンドラーを直接コピーする方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="a8f06-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3. <span data-ttu-id="a8f06-127">`mWidget_PercentDone` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     <span data-ttu-id="a8f06-128">`PercentDone` イベントが発生するたびに、イベント プロシージャにより `Label` コントロールに完了率が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="a8f06-129">`DoEvents` メソッドによって、ラベルの再描画を許可すると同時に、 **[キャンセル]** ボタンをクリックする機会をユーザーに提供しています。</span><span class="sxs-lookup"><span data-stu-id="a8f06-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4. <span data-ttu-id="a8f06-130">`Button2_Click` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 <span data-ttu-id="a8f06-131">`LongTask` の実行中にユーザーが **[キャンセル]** ボタンをクリックすると、`DoEvents` ステートメントによりイベント処理の実行が許可されしだい、`Button2_Click` イベントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="a8f06-132">クラスレベルの変数 `mblnCancel` が `True` に設定された後、`mWidget_PercentDone` イベントによりテストが行われ、`ByRef Cancel` 引数が `True` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="a8f06-133">オブジェクトへの WithEvents 変数の接続</span><span class="sxs-lookup"><span data-stu-id="a8f06-133">Connecting a WithEvents Variable to an Object</span></span>  

 <span data-ttu-id="a8f06-134">これで、`Widget` オブジェクトのイベントを処理するように `Form1` を設定できました。</span><span class="sxs-lookup"><span data-stu-id="a8f06-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="a8f06-135">あとは、`Widget` を見つけるだけです。</span><span class="sxs-lookup"><span data-stu-id="a8f06-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="a8f06-136">デザイン時に変数 `WithEvents` を宣言しても、変数にオブジェクトは関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="a8f06-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="a8f06-137">`WithEvents` 変数は、単に他のオブジェクト変数と似たものです。</span><span class="sxs-lookup"><span data-stu-id="a8f06-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="a8f06-138">オブジェクトを作成してから、そのオブジェクトに対する参照を `WithEvents` 変数に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f06-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="a8f06-139">オブジェクトを作成して参照を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="a8f06-139">To create an object and assign a reference to it</span></span>  
  
1. <span data-ttu-id="a8f06-140">**コード エディター**の左側のドロップダウン リストで、 **[(Form1 イベント)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2. <span data-ttu-id="a8f06-141">右側のドロップダウン リストで `Load` イベントを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="a8f06-142">**コード エディター**に `Form1_Load` イベント プロシージャが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3. <span data-ttu-id="a8f06-143">`Form1_Load` イベント プロシージャに、`Widget` を作成する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 <span data-ttu-id="a8f06-144">このコードを実行すると、Visual Basic により `Widget` オブジェクトが作成され、そのイベントが `mWidget` に関連付けられているイベント プロシージャと接続されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="a8f06-145">この時点以降、`Widget` で `PercentDone` イベントが発生するたびに、`mWidget_PercentDone` イベント プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="a8f06-146">LongTask メソッドを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="a8f06-146">To call the LongTask method</span></span>  
  
- <span data-ttu-id="a8f06-147">`Button1_Click` イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 <span data-ttu-id="a8f06-148">`LongTask` メソッドを呼び出す前に、完了率を示すラベルを初期化する必要があります。また、メソッド取り消し用のクラスレベルの `Boolean` フラグを `False` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f06-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="a8f06-149">タスクの実行時間を 12.2 秒に指定したうえで、`LongTask` が呼び出されています。</span><span class="sxs-lookup"><span data-stu-id="a8f06-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="a8f06-150">`PercentDone` イベントは 3 分の 1 秒ごとに発生します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="a8f06-151">イベントが発生するたびに、`mWidget_PercentDone` イベント プロシージャが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="a8f06-152">`LongTask` が完了すると `mblnCancel` がテストされ、`LongTask` が正常に完了したか、または `mblnCancel` が `True` に設定されていたために中止されたかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="a8f06-153">完了率は、前者の場合にのみ更新されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="a8f06-154">プログラムを実行するには</span><span class="sxs-lookup"><span data-stu-id="a8f06-154">To run the program</span></span>  
  
1. <span data-ttu-id="a8f06-155">F5 キーを押して、プロジェクトを実行モードに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-155">Press F5 to put the project in run mode.</span></span>  
  
2. <span data-ttu-id="a8f06-156">**[タスクの開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8f06-156">Click the **Start Task** button.</span></span> <span data-ttu-id="a8f06-157">`PercentDone` イベントが発生するたびにラベルが更新され、完了したタスクの割合が示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3. <span data-ttu-id="a8f06-158">タスクを停止するには、 **[キャンセル]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8f06-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="a8f06-159">**[キャンセル]** ボタンの外観は、クリックしてもすぐには変わらないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a8f06-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="a8f06-160">`Click` イベントは、`My.Application.DoEvents` ステートメントでイベント処理が許可されるまで発生しません。</span><span class="sxs-lookup"><span data-stu-id="a8f06-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a8f06-161">`My.Application.DoEvents` メソッドがイベントを処理する方法は、フォームによる方法とは一部異なります。</span><span class="sxs-lookup"><span data-stu-id="a8f06-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="a8f06-162">たとえば、このチュートリアルでは、 **[キャンセル]** ボタンを 2 回クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f06-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="a8f06-163">フォームでイベントを直接処理できるようにするには、マルチスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="a8f06-164">詳細については、「[マネージド スレッド処理](../../../../standard/threading/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f06-164">For more information, see [Managed Threading](../../../../standard/threading/index.md).</span></span>
  
 <span data-ttu-id="a8f06-165">F11 キーを使用してプログラムを実行し、コードを一度に 1 行ずつステップ実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8f06-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="a8f06-166">`LongTask` の実行が開始された後、`PercentDone` イベントが発生するたびに `Form1` が一時的に再度開始されるようすを明確に確認できます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="a8f06-167">`Form1` のコードが再実行されている間に、`LongTask` メソッドが再び呼び出されたらどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a8f06-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="a8f06-168">イベント発生時に毎回 `LongTask` が呼び出されると、最悪の場合スタック オーバーフローが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8f06-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="a8f06-169">変数 `mWidget` に新しい `Widget` オブジェクトへの参照を割り当てることで、別の `Widget` のイベントを `mWidget` で処理できます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="a8f06-170">実際には、ボタンをクリックするたびに、`Button1_Click` のコードでこの処理を実行可能です。</span><span class="sxs-lookup"><span data-stu-id="a8f06-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="a8f06-171">別のウィジェットのイベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="a8f06-171">To handle events for a different widget</span></span>  
  
- <span data-ttu-id="a8f06-172">`Button1_Click` プロシージャの `mWidget.LongTask(12.2, 0.33)` という行のすぐ下に、次のコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 <span data-ttu-id="a8f06-173">上記のコードでは、ボタンがクリックされるたびに新しい `Widget` を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="a8f06-174">`LongTask` メソッドが完了するとすぐに `Widget` への参照が解放され、`Widget` が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="a8f06-175">`WithEvents` 変数に含められるオブジェクト参照は一度に 1 つだけです。そのため、別の `Widget` オブジェクトを `mWidget` に割り当てると、前の `Widget` オブジェクトのイベントは処理されなくなります。</span><span class="sxs-lookup"><span data-stu-id="a8f06-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="a8f06-176">古い `Widget` への参照を含むオブジェクト変数が `mWidget` のみである場合、オブジェクトは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="a8f06-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="a8f06-177">複数の `Widget` オブジェクトのイベントを処理する場合は、`AddHandler` ステートメントを使用して、各オブジェクトのイベントを個別に処理します。</span><span class="sxs-lookup"><span data-stu-id="a8f06-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8f06-178">`WithEvents` 変数は必要な数だけ宣言できますが、`WithEvents` 変数の配列はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="a8f06-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f06-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8f06-179">See also</span></span>

- [<span data-ttu-id="a8f06-180">チュートリアル: イベントの宣言と発生</span><span class="sxs-lookup"><span data-stu-id="a8f06-180">Walkthrough: Declaring and Raising Events</span></span>](walkthrough-declaring-and-raising-events.md)
- [<span data-ttu-id="a8f06-181">イベント</span><span class="sxs-lookup"><span data-stu-id="a8f06-181">Events</span></span>](index.md)
