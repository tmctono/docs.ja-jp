---
title: イベントの宣言と発生
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 6f4c303604f9cf55b4ecd500636e0d2772b6234c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345087"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="131eb-102">チュートリアル: イベントの宣言と発生 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131eb-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="131eb-103">このチュートリアルでは、`Widget` という名前のクラスのイベントを宣言し、発生させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="131eb-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="131eb-104">この手順を完了したら、本トピックの対になっている「[チュートリアル: イベントの処理](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)」も読むことをお勧めします。こちらでは、`Widget` オブジェクトのイベントを使用して、アプリケーションの状態に関する情報を示す方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="131eb-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="131eb-105">Widget クラス</span><span class="sxs-lookup"><span data-stu-id="131eb-105">The Widget Class</span></span>  
 <span data-ttu-id="131eb-106">このチュートリアルでは、`Widget` クラスがあるものと仮定します。</span><span class="sxs-lookup"><span data-stu-id="131eb-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="131eb-107">`Widget` クラスには、実行に時間のかかる可能性のあるメソッドが含まれているので、なんらかの完了率インジケーターをアプリケーションに表示することにします。</span><span class="sxs-lookup"><span data-stu-id="131eb-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="131eb-108">もちろん、完了率を示すダイアログ ボックスを `Widget` オブジェクトに表示してもかまいません。ただし、そうすると `Widget` クラスを使用するあらゆるプロジェクトで、このダイアログ ボックスが表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="131eb-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="131eb-109">オブジェクト設計の原則は、オブジェクトの目的がフォームまたはダイアログ ボックスの管理だけである場合を除き、ユーザー インターフェイスの処理はオブジェクトを使用するアプリケーションに任せることです。</span><span class="sxs-lookup"><span data-stu-id="131eb-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="131eb-110">`Widget` の目的は別のタスクの実行ですので、`PercentDone` イベントを追加し、`Widget` のメソッドを呼び出すプロシージャにこのイベントを処理させて、最新の状態を表示させる方が適切です。</span><span class="sxs-lookup"><span data-stu-id="131eb-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="131eb-111">`PercentDone` イベントによって、タスクを取り消すメカニズムも提供できます。</span><span class="sxs-lookup"><span data-stu-id="131eb-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="131eb-112">このトピックのコード例をビルドするには</span><span class="sxs-lookup"><span data-stu-id="131eb-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="131eb-113">新しい Visual Basic Windows アプリケーション プロジェクトを開き、`Form1` という名前のフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="131eb-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="131eb-114">`Form1` にボタン 2 つとラベル 1 つを追加します。</span><span class="sxs-lookup"><span data-stu-id="131eb-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="131eb-115">次の表のように、各オブジェクトに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="131eb-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="131eb-116">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="131eb-116">Object</span></span>|<span data-ttu-id="131eb-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="131eb-117">Property</span></span>|<span data-ttu-id="131eb-118">設定</span><span class="sxs-lookup"><span data-stu-id="131eb-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="131eb-119">タスクの開始</span><span class="sxs-lookup"><span data-stu-id="131eb-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="131eb-120">キャンセル</span><span class="sxs-lookup"><span data-stu-id="131eb-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="131eb-121">`(Name)`、`Text`</span><span class="sxs-lookup"><span data-stu-id="131eb-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="131eb-122">lblPercentDone、0</span><span class="sxs-lookup"><span data-stu-id="131eb-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="131eb-123">**[プロジェクト]** メニューの **[クラスの追加]** を選択して、`Widget.vb` という名前のクラスをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="131eb-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="131eb-124">Widget クラスのイベントを宣言するには</span><span class="sxs-lookup"><span data-stu-id="131eb-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="131eb-125">`Event` キーワードを使用して、`Widget` クラス内でイベントを宣言します。</span><span class="sxs-lookup"><span data-stu-id="131eb-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="131eb-126">次の `Widget` の `PercentDone` イベントに示されているように、イベントには `ByVal` 引数と `ByRef` 引数を設定できます。</span><span class="sxs-lookup"><span data-stu-id="131eb-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="131eb-127">呼び出し元オブジェクトが `PercentDone` イベントを受け取るとき、`Percent` 引数には完了したタスクの割合が含まれています。</span><span class="sxs-lookup"><span data-stu-id="131eb-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="131eb-128">`Cancel` 引数を `True` に設定すると、イベントを発生させたメソッドを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="131eb-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="131eb-129">イベントの引数は、プロシージャの引数と同様に宣言できますが、次のような例外があります。イベントに対して `Optional` 引数または `ParamArray` 引数を指定することはできません。また、イベントは値を返しません。</span><span class="sxs-lookup"><span data-stu-id="131eb-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="131eb-130">`PercentDone` イベントは、`Widget` クラスの `LongTask` メソッドで発生します。</span><span class="sxs-lookup"><span data-stu-id="131eb-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="131eb-131">`LongTask` は、メソッドの仮の実行時間と、`PercentDone` イベントの発生まで `LongTask` が一時停止する最短期間の 2 つを引数に取ります。</span><span class="sxs-lookup"><span data-stu-id="131eb-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="131eb-132">PercentDone イベントを発生させるには</span><span class="sxs-lookup"><span data-stu-id="131eb-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="131eb-133">このクラスで使用する `Timer` プロパティにアクセスしやすくするため、`Imports` ステートメントを、クラス モジュールの宣言セクション先頭、`Class Widget` ステートメントの上に追加します。</span><span class="sxs-lookup"><span data-stu-id="131eb-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="131eb-134">`Widget` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="131eb-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="131eb-135">アプリケーションで `LongTask` メソッドが呼び出されると、`MinimumInterval` 秒ごとに `Widget` クラスで `PercentDone` イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="131eb-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="131eb-136">イベントが返されると、`Cancel` 引数が `True` に設定されているかどうかが `LongTask` により確認されます。</span><span class="sxs-lookup"><span data-stu-id="131eb-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="131eb-137">ここで、いくつかの注意事項があります。</span><span class="sxs-lookup"><span data-stu-id="131eb-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="131eb-138">簡略化のため、`LongTask` プロシージャでは、タスクの実行所要時間があらかじめわかっているものと仮定しています。</span><span class="sxs-lookup"><span data-stu-id="131eb-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="131eb-139">このようなケースはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="131eb-139">This is almost never the case.</span></span> <span data-ttu-id="131eb-140">タスクを均一サイズのチャンクに分割することは困難であり、また多くの場合、ユーザーにとって重要なことは、何かが起きたことを把握できるまでの時間の長さだけです。</span><span class="sxs-lookup"><span data-stu-id="131eb-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="131eb-141">お気付きのとおり、このサンプルには別の欠陥もあります。</span><span class="sxs-lookup"><span data-stu-id="131eb-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="131eb-142">`Timer` プロパティが返すのは、午前 0 時からの経過時間 (秒) です。そのため、アプリケーションは、午前 0 時の直前に開始された場合停止してしまいます。</span><span class="sxs-lookup"><span data-stu-id="131eb-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="131eb-143">より適切に時間を測定する方法としては、このような境界条件を考慮するか、`Now` などのプロパティを使用してこうした条件を完全に回避することが考えられます。</span><span class="sxs-lookup"><span data-stu-id="131eb-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="131eb-144">これで、`Widget` クラスでイベントを発生させられるようになり、次のチュートリアルに進む用意が整いました。</span><span class="sxs-lookup"><span data-stu-id="131eb-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="131eb-145">[チュートリアル: イベントの処理](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)」で、`WithEvents` を使用してイベント ハンドラーを `PercentDone` イベントに関連付ける方法について学びましょう。</span><span class="sxs-lookup"><span data-stu-id="131eb-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131eb-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="131eb-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="131eb-147">チュートリアル: イベントの処理</span><span class="sxs-lookup"><span data-stu-id="131eb-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="131eb-148">イベント</span><span class="sxs-lookup"><span data-stu-id="131eb-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
