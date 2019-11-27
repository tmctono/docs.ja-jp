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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345087"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="61c1c-102">チュートリアル: イベントの宣言と発生 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61c1c-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="61c1c-103">このチュートリアルでは、`Widget`という名前のクラスのイベントを宣言して発生させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="61c1c-104">手順を完了したら、「[チュートリアル: イベントの処理](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)」の関連トピックを参照することをお勧めします。これは、`Widget` オブジェクトからのイベントを使用してアプリケーションにステータス情報を提供する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="61c1c-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="61c1c-105">ウィジェットクラス</span><span class="sxs-lookup"><span data-stu-id="61c1c-105">The Widget Class</span></span>  
 <span data-ttu-id="61c1c-106">`Widget` クラスがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="61c1c-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="61c1c-107">`Widget` クラスには、実行に時間がかかる可能性があり、アプリケーションで何らかの完了インジケーターを設定できるようにするためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="61c1c-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="61c1c-108">もちろん、`Widget` オブジェクトにパーセント (パーセント) のダイアログボックスを表示させることもできますが、その場合は、`Widget` クラスを使用したすべてのプロジェクトでそのダイアログボックスがスタックします。</span><span class="sxs-lookup"><span data-stu-id="61c1c-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="61c1c-109">オブジェクトの設計では、オブジェクトを使用するアプリケーションで、フォームまたはダイアログボックスを管理するだけではなく、ユーザーインターフェイスを処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61c1c-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="61c1c-110">`Widget` の目的は、他のタスクを実行することです。そのため、`PercentDone` イベントを追加し、`Widget`のメソッドを呼び出すプロシージャでそのイベントを処理し、ステータスの更新を表示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61c1c-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="61c1c-111">`PercentDone` イベントには、タスクを取り消すためのメカニズムも用意されています。</span><span class="sxs-lookup"><span data-stu-id="61c1c-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="61c1c-112">このトピックのコード例をビルドするには</span><span class="sxs-lookup"><span data-stu-id="61c1c-112">To build the code example for this topic</span></span>  
  
1. <span data-ttu-id="61c1c-113">新しい Visual Basic Windows アプリケーションプロジェクトを開き、`Form1`という名前のフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2. <span data-ttu-id="61c1c-114">`Form1`に2つのボタンとラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-114">Add two buttons and a label to `Form1`.</span></span>  
  
3. <span data-ttu-id="61c1c-115">次の表のように、各オブジェクトに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="61c1c-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="61c1c-116">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="61c1c-116">Object</span></span>|<span data-ttu-id="61c1c-117">プロパティ</span><span class="sxs-lookup"><span data-stu-id="61c1c-117">Property</span></span>|<span data-ttu-id="61c1c-118">設定</span><span class="sxs-lookup"><span data-stu-id="61c1c-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="61c1c-119">開始タスク</span><span class="sxs-lookup"><span data-stu-id="61c1c-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="61c1c-120">キャンセル</span><span class="sxs-lookup"><span data-stu-id="61c1c-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="61c1c-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="61c1c-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="61c1c-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="61c1c-122">lblPercentDone, 0</span></span>|  
  
4. <span data-ttu-id="61c1c-123">**[プロジェクト]** メニューの **[クラスの追加]** をクリックして、`Widget.vb` という名前のクラスをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="61c1c-124">ウィジェットクラスのイベントを宣言するには</span><span class="sxs-lookup"><span data-stu-id="61c1c-124">To declare an event for the Widget class</span></span>  
  
- <span data-ttu-id="61c1c-125">`Widget` クラスでイベントを宣言するには、`Event` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="61c1c-126">イベントは `Widget`の `PercentDone` イベントが示すように、`ByVal` 引数と `ByRef` 引数を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="61c1c-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 <span data-ttu-id="61c1c-127">呼び出し元のオブジェクトが `PercentDone` イベントを受け取ると、`Percent` 引数には、完了したタスクの割合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="61c1c-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="61c1c-128">`Cancel` 引数を `True` に設定して、イベントを発生させたメソッドを取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="61c1c-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61c1c-129">イベント引数は、プロシージャの引数と同じように宣言できます。ただし、イベントに `Optional` または `ParamArray` 引数を指定することはできません。また、イベントには戻り値がありません。</span><span class="sxs-lookup"><span data-stu-id="61c1c-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="61c1c-130">`PercentDone` イベントは、`Widget` クラスの `LongTask` メソッドによって発生します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="61c1c-131">`LongTask` は2つの引数を取ります。これは、メソッドが処理を実行している時間の長さと、`LongTask` が一時停止して `PercentDone` イベントが発生するまでの最小時間間隔です。</span><span class="sxs-lookup"><span data-stu-id="61c1c-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="61c1c-132">PercentDone イベントを発生させるには</span><span class="sxs-lookup"><span data-stu-id="61c1c-132">To raise the PercentDone event</span></span>  
  
1. <span data-ttu-id="61c1c-133">このクラスで使用される `Timer` プロパティへのアクセスを簡略化するには、クラスモジュールの宣言セクションの先頭に `Class Widget` ステートメントの上に `Imports` ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. <span data-ttu-id="61c1c-134">`Widget` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 <span data-ttu-id="61c1c-135">アプリケーションが `LongTask` メソッドを呼び出すと、`Widget` クラスは `MinimumInterval` 秒ごとに `PercentDone` イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="61c1c-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="61c1c-136">イベントが返されると、`LongTask` `Cancel` 引数が `True`に設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="61c1c-137">ここでは、いくつかの免責事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="61c1c-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="61c1c-138">わかりやすくするために、`LongTask` の手順では、タスクの実行時間が事前にわかっていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="61c1c-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="61c1c-139">これはほとんどの場合、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="61c1c-139">This is almost never the case.</span></span> <span data-ttu-id="61c1c-140">タスクを均等なサイズのチャンクに分割することは困難です。多くの場合、ユーザーにとって最も重要なのは、何かが発生したことを示す前にが経過した時間だけです。</span><span class="sxs-lookup"><span data-stu-id="61c1c-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="61c1c-141">このサンプルの別の欠陥が発見された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61c1c-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="61c1c-142">`Timer` プロパティは、深夜0時以降に経過した秒数を返します。そのため、深夜の直前にアプリケーションが起動された場合は、アプリケーションが停止します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="61c1c-143">時間を測定するためのより慎重なアプローチは、このような境界条件を考慮に入れるか、`Now`などのプロパティを使用して完全に回避することです。</span><span class="sxs-lookup"><span data-stu-id="61c1c-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="61c1c-144">`Widget` クラスでイベントを発生させることができるようになったので、次のチュートリアルに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="61c1c-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="61c1c-145">[チュートリアル:](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)イベントの処理では、`WithEvents` を使用してイベントハンドラーを `PercentDone` イベントに関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61c1c-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c1c-146">参照</span><span class="sxs-lookup"><span data-stu-id="61c1c-146">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [<span data-ttu-id="61c1c-147">チュートリアル : イベントの処理</span><span class="sxs-lookup"><span data-stu-id="61c1c-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [<span data-ttu-id="61c1c-148">イベント</span><span class="sxs-lookup"><span data-stu-id="61c1c-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
