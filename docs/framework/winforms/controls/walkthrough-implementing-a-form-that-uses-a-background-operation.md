---
title: 'チュートリアル: バックグラウンド操作を使用するフォームの実装'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
ms.openlocfilehash: 60421d6ba634bd7b4107f1c9998fbbe158417c83
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423838"
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a><span data-ttu-id="b34fa-102">チュートリアル: バックグラウンド操作を使用するフォームの実装</span><span class="sxs-lookup"><span data-stu-id="b34fa-102">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>

<span data-ttu-id="b34fa-103">完了するには長い時間がかかる操作がない場合、したくない、ユーザー インターフェイス (UI) 応答を停止するかブロックするを使用することができます、<xref:System.ComponentModel.BackgroundWorker>クラスを別のスレッドで操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-103">If you have an operation that will take a long time to complete, and you do not want your user interface (UI) to stop responding or to block, you can use the <xref:System.ComponentModel.BackgroundWorker> class to execute the operation on another thread.</span></span>

<span data-ttu-id="b34fa-104">このチュートリアルで使用する方法、 <xref:System.ComponentModel.BackgroundWorker> ""バック グラウンドで時間のかかる計算を実行するクラス、ユーザー インターフェイスの応答性の高いままです。</span><span class="sxs-lookup"><span data-stu-id="b34fa-104">This walkthrough illustrates how to use the <xref:System.ComponentModel.BackgroundWorker> class to perform time-consuming computations "in the background," while the user interface remains responsive.</span></span>  <span data-ttu-id="b34fa-105">このチュートリアルを完了すると、フィボナッチ数を非同期に計算するアプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b34fa-105">When you are through, you will have an application that computes Fibonacci numbers asynchronously.</span></span> <span data-ttu-id="b34fa-106">大きなフィボナッチ数の計算にはかなりの時間がかかることがありますが、この遅延によってメイン UI スレッドが中断されることはなく、計算中もフォームは応答性を維持します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-106">Even though computing a large Fibonacci number can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculation.</span></span>

<span data-ttu-id="b34fa-107">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="b34fa-107">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="b34fa-108">Windows ベースのアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="b34fa-108">Creating a Windows-based Application</span></span>

- <span data-ttu-id="b34fa-109">作成、<xref:System.ComponentModel.BackgroundWorker>フォーム</span><span class="sxs-lookup"><span data-stu-id="b34fa-109">Creating a <xref:System.ComponentModel.BackgroundWorker> in Your Form</span></span>

- <span data-ttu-id="b34fa-110">非同期イベント ハンドラーの追加</span><span class="sxs-lookup"><span data-stu-id="b34fa-110">Adding Asynchronous Event Handlers</span></span>

- <span data-ttu-id="b34fa-111">進行状況の報告とキャンセルのサポートの追加</span><span class="sxs-lookup"><span data-stu-id="b34fa-111">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="b34fa-112">この例で使用するコードの完全な一覧については、次を参照してください。[方法。バック グラウンド操作を使用してフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-112">For a complete listing of the code used in this example, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>

## <a name="create-a-form-that-uses-a-background-operation"></a><span data-ttu-id="b34fa-113">バック グラウンド操作を使用するフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-113">Create a form that uses a background operation</span></span>

1. <span data-ttu-id="b34fa-114">Visual Studio で、という名前の Windows ベースのアプリケーション プロジェクトを作成`BackgroundWorkerExample`(**ファイル** > **新規** > **プロジェクト** >  **Visual C#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="b34fa-114">In Visual Studio, create a Windows-based application project called `BackgroundWorkerExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="b34fa-115">**ソリューション エクスプローラー**で、 **[Form1]** を右クリックし、ショートカット メニューの **[名前の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fa-115">In **Solution Explorer**, right-click **Form1** and select **Rename** from the shortcut menu.</span></span> <span data-ttu-id="b34fa-116">ファイル名を `FibonacciCalculator` に変更します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-116">Change the file name to `FibonacciCalculator`.</span></span> <span data-ttu-id="b34fa-117">コード要素 "`Form1`" へのすべての参照の名前を変更するかどうかをたずねられたら、 **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fa-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`Form1`'.</span></span>

3. <span data-ttu-id="b34fa-118">ドラッグ、<xref:System.Windows.Forms.NumericUpDown>コントロールから、**ツールボックス**フォーム上にします。</span><span class="sxs-lookup"><span data-stu-id="b34fa-118">Drag a <xref:System.Windows.Forms.NumericUpDown> control from the **Toolbox** onto the form.</span></span> <span data-ttu-id="b34fa-119">設定、<xref:System.Windows.Forms.NumericUpDown.Minimum%2A>プロパティを`1`と<xref:System.Windows.Forms.NumericUpDown.Maximum%2A>プロパティを`91`します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-119">Set the <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> property to `1` and the <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> property to `91`.</span></span>

4. <span data-ttu-id="b34fa-120">2 つ追加<xref:System.Windows.Forms.Button>フォームのコントロール。</span><span class="sxs-lookup"><span data-stu-id="b34fa-120">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span>

5. <span data-ttu-id="b34fa-121">最初の名前を変更<xref:System.Windows.Forms.Button>コントロール`startAsyncButton`設定と、<xref:System.Windows.Forms.Control.Text%2A>プロパティを`Start Async`します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-121">Rename the first <xref:System.Windows.Forms.Button> control `startAsyncButton` and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Start Async`.</span></span> <span data-ttu-id="b34fa-122">2 つ目の名前を変更<xref:System.Windows.Forms.Button>コントロール`cancelAsyncButton`、設定、<xref:System.Windows.Forms.Control.Text%2A>プロパティを`Cancel Async`します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-122">Rename the second <xref:System.Windows.Forms.Button> control `cancelAsyncButton`, and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Cancel Async`.</span></span> <span data-ttu-id="b34fa-123">設定の<xref:System.Windows.Forms.Control.Enabled%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-123">Set its <xref:System.Windows.Forms.Control.Enabled%2A> property to `false`.</span></span>

6. <span data-ttu-id="b34fa-124">この 2 つのイベント ハンドラーを作成、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="b34fa-124">Create an event handler for both of the <xref:System.Windows.Forms.Button> controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="b34fa-125">詳細については、「[方法: デザイナーを使用してイベント ハンドラーを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-125">For details, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

7. <span data-ttu-id="b34fa-126">ドラッグ、<xref:System.Windows.Forms.Label>コントロールから、**ツールボックス**をフォームに名前を変更し、`resultLabel`します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-126">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the form and rename it `resultLabel`.</span></span>

8. <span data-ttu-id="b34fa-127">ドラッグ、<xref:System.Windows.Forms.ProgressBar>コントロールから、**ツールボックス**フォーム上にします。</span><span class="sxs-lookup"><span data-stu-id="b34fa-127">Drag a <xref:System.Windows.Forms.ProgressBar> control from the **Toolbox** onto the form.</span></span>

## <a name="create-a-backgroundworker-with-the-designer"></a><span data-ttu-id="b34fa-128">デザイナーでの BackgroundWorker を作成します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-128">Create a BackgroundWorker with the Designer</span></span>

<span data-ttu-id="b34fa-129">作成することができます、<xref:System.ComponentModel.BackgroundWorker>を使用して、非同期操作の**Windows** **フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-129">You can create the <xref:System.ComponentModel.BackgroundWorker> for your asynchronous operation using the **Windows** **Forms Designer**.</span></span>

<span data-ttu-id="b34fa-130">**コンポーネント**のタブ、**ツールボックス**、ドラッグ、<xref:System.ComponentModel.BackgroundWorker>フォーム上にします。</span><span class="sxs-lookup"><span data-stu-id="b34fa-130">From the **Components** tab of the **Toolbox**, drag a <xref:System.ComponentModel.BackgroundWorker> onto the form.</span></span>

## <a name="add-asynchronous-event-handlers"></a><span data-ttu-id="b34fa-131">非同期イベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-131">Add asynchronous event handlers</span></span>

<span data-ttu-id="b34fa-132">イベント ハンドラーを追加する準備が整いました、<xref:System.ComponentModel.BackgroundWorker>コンポーネントの非同期イベント。</span><span class="sxs-lookup"><span data-stu-id="b34fa-132">You are now ready to add event handlers for the <xref:System.ComponentModel.BackgroundWorker> component's asynchronous events.</span></span> <span data-ttu-id="b34fa-133">バックグラウンドで実行される時間のかかる操作 (フィボナッチ数の計算) は、これらのイベント ハンドラーのいずれかによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b34fa-133">The time-consuming operation that will run in the background, which computes Fibonacci numbers, is called by one of these event handlers.</span></span>

1. <span data-ttu-id="b34fa-134">**プロパティ** ウィンドウで、<xref:System.ComponentModel.BackgroundWorker>が選択されているコンポーネントをクリックして、**イベント**ボタン。</span><span class="sxs-lookup"><span data-stu-id="b34fa-134">In the **Properties** window, with the <xref:System.ComponentModel.BackgroundWorker> component still selected, click the **Events** button.</span></span> <span data-ttu-id="b34fa-135">ダブルクリックして、<xref:System.ComponentModel.BackgroundWorker.DoWork>と<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベントをイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-135">Double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span> <span data-ttu-id="b34fa-136">イベント ハンドラーを使用する方法の詳細については、次を参照してください。[方法。デザイナーを使用してイベント ハンドラーを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-136">For more information about how to use event handlers, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

2. <span data-ttu-id="b34fa-137">フォームで `ComputeFibonacci` という新しいメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-137">Create a new method, called `ComputeFibonacci`, in your form.</span></span> <span data-ttu-id="b34fa-138">このメソッドがバックグラウンドで実行され、実際の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="b34fa-138">This method does the actual work, and it will run in the background.</span></span> <span data-ttu-id="b34fa-139">このコードは、フィボナッチ アルゴリズムの再帰的実装を示しています。これは、非常に非効率であり、数が大きくなるにつれて、完了までの所要時間が急激に増大します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-139">This code demonstrates the recursive implementation of the Fibonacci algorithm, which is notably inefficient, taking exponentially longer time to complete for larger numbers.</span></span> <span data-ttu-id="b34fa-140">ここでは、アプリケーションで長時間の遅延が発生する可能性のある操作を示すために、このコードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b34fa-140">It is used here for illustrative purposes, to show an operation that can introduce long delays in your application.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]

3. <span data-ttu-id="b34fa-141"><xref:System.ComponentModel.BackgroundWorker.DoWork>イベント ハンドラー呼び出しを追加、`ComputeFibonacci`メソッド。</span><span class="sxs-lookup"><span data-stu-id="b34fa-141">In the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, add a call to the `ComputeFibonacci` method.</span></span> <span data-ttu-id="b34fa-142">最初のパラメーターを受け取る`ComputeFibonacci`から、<xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>のプロパティ、<xref:System.ComponentModel.DoWorkEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-142">Take the first parameter for `ComputeFibonacci` from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="b34fa-143"><xref:System.ComponentModel.BackgroundWorker>と<xref:System.ComponentModel.DoWorkEventArgs>パラメーターが進行状況の報告とキャンセルの後で使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b34fa-143">The <xref:System.ComponentModel.BackgroundWorker> and <xref:System.ComponentModel.DoWorkEventArgs> parameters will be used later for progress reporting and cancellation support.</span></span> <span data-ttu-id="b34fa-144">戻り値を割り当てる`ComputeFibonacci`を<xref:System.ComponentModel.DoWorkEventArgs.Result%2A>のプロパティ、<xref:System.ComponentModel.DoWorkEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-144">Assign the return value from `ComputeFibonacci` to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="b34fa-145">この結果は、使用可能になります、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="b34fa-145">This result will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b34fa-146"><xref:System.ComponentModel.BackgroundWorker.DoWork>イベント ハンドラーを参照していません、`backgroundWorker1`の特定のインスタンスにこのイベント ハンドラーを結合はこのように、変数を直接インスタンス<xref:System.ComponentModel.BackgroundWorker>します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-146">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler does not reference the `backgroundWorker1` instance variable directly, as this would couple this event handler to a specific instance of <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="b34fa-147">代わりへの参照、<xref:System.ComponentModel.BackgroundWorker>これが発生したイベントがから復元、`sender`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b34fa-147">Instead, a reference to the <xref:System.ComponentModel.BackgroundWorker> that raised this event is recovered from the `sender` parameter.</span></span> <span data-ttu-id="b34fa-148">これは、1 つ以上のフォームがホストされる場合に重要な<xref:System.ComponentModel.BackgroundWorker>します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-148">This is important when the form hosts more than one <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="b34fa-149">内の任意のユーザー インターフェイス オブジェクトを操作しないようにする重要なも、<xref:System.ComponentModel.BackgroundWorker.DoWork>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="b34fa-149">It is also important not to manipulate any user-interface objects in your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="b34fa-150">代わりに、を通じてユーザー インターフェイスとの通信、<xref:System.ComponentModel.BackgroundWorker>イベント。</span><span class="sxs-lookup"><span data-stu-id="b34fa-150">Instead, communicate to the user interface through the <xref:System.ComponentModel.BackgroundWorker> events.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]

4. <span data-ttu-id="b34fa-151">`startAsyncButton`コントロールの<xref:System.Windows.Forms.Control.Click>イベント ハンドラー、非同期操作を開始するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-151">In the `startAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that starts the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]

5. <span data-ttu-id="b34fa-152"><xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント ハンドラーでは、計算の結果に割り当てる、`resultLabel`コントロール。</span><span class="sxs-lookup"><span data-stu-id="b34fa-152">In the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler, assign the result of the calculation to the `resultLabel` control.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]

## <a name="adding-progress-reporting-and-support-for-cancellation"></a><span data-ttu-id="b34fa-153">進行状況の報告とキャンセルのサポートの追加</span><span class="sxs-lookup"><span data-stu-id="b34fa-153">Adding Progress Reporting and Support for Cancellation</span></span>

<span data-ttu-id="b34fa-154">時間のかかる非同期操作では、多くの場合、進行状況をユーザーに報告し、ユーザーが操作をキャンセルできるようにすることが望まれます。</span><span class="sxs-lookup"><span data-stu-id="b34fa-154">For asynchronous operations that will take a long time, it is often desirable to report progress to the user and to allow the user to cancel the operation.</span></span> <span data-ttu-id="b34fa-155"><xref:System.ComponentModel.BackgroundWorker>クラスは、バック グラウンド操作処理の進行状況の進行状況を投稿できるイベントを提供します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-155">The <xref:System.ComponentModel.BackgroundWorker> class provides an event that allows you to post progress as your background operation proceeds.</span></span> <span data-ttu-id="b34fa-156">呼び出しを検出するために、ワーカー コードを許可するフラグも用意されています。<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>自体を中断するとします。</span><span class="sxs-lookup"><span data-stu-id="b34fa-156">It also provides a flag that allows your worker code to detect a call to <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> and interrupt itself.</span></span>

### <a name="implement-progress-reporting"></a><span data-ttu-id="b34fa-157">進行状況レポートを実装します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-157">Implement progress reporting</span></span>

1. <span data-ttu-id="b34fa-158">**[プロパティ]** ウィンドウで `backgroundWorker1` を選択します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-158">In the **Properties**, window, select `backgroundWorker1`.</span></span> <span data-ttu-id="b34fa-159">  <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> と <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを `true\` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-159">Set the <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span>

2. <span data-ttu-id="b34fa-160">`FibonacciCalculator` フォームで 2 つの変数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-160">Declare two variables in the `FibonacciCalculator` form.</span></span> <span data-ttu-id="b34fa-161">これらの変数を使用して進行状況を追跡します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-161">These will be used to track progress.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]

3. <span data-ttu-id="b34fa-162">  <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> イベントのイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-162">Add an event handler for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="b34fa-163"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged>イベント ハンドラー、update、<xref:System.Windows.Forms.ProgressBar>で、<xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A>のプロパティ、<xref:System.ComponentModel.ProgressChangedEventArgs>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b34fa-163">In the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler, update the <xref:System.Windows.Forms.ProgressBar> with the <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> property of the <xref:System.ComponentModel.ProgressChangedEventArgs> parameter.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]

### <a name="implement-support-for-cancellation"></a><span data-ttu-id="b34fa-164">キャンセルのサポートを実装します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-164">Implement support for cancellation</span></span>

1. <span data-ttu-id="b34fa-165">`cancelAsyncButton`コントロールの<xref:System.Windows.Forms.Control.Click>イベント ハンドラー、非同期操作をキャンセルするコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-165">In the `cancelAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that cancels the asynchronous operation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]

2. <span data-ttu-id="b34fa-166">`ComputeFibonacci` メソッドの次のコード フラグメントは、進行状況の報告とキャンセルのサポートを示しています。</span><span class="sxs-lookup"><span data-stu-id="b34fa-166">The following code fragments in the `ComputeFibonacci` method report progress and support cancellation.</span></span>

     [!code-cpp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]

## <a name="checkpoint"></a><span data-ttu-id="b34fa-167">チェックポイント</span><span class="sxs-lookup"><span data-stu-id="b34fa-167">Checkpoint</span></span>

<span data-ttu-id="b34fa-168">この時点で、フィボナッチ電卓アプリケーションをコンパイルして実行できます。</span><span class="sxs-lookup"><span data-stu-id="b34fa-168">At this point, you can compile and run the Fibonacci Calculator application.</span></span>

<span data-ttu-id="b34fa-169">キーを押して**F5**をコンパイルして、アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-169">Press **F5** to compile and run the application.</span></span>

<span data-ttu-id="b34fa-170">計算がバック グラウンドで実行しているときに表示されます、<xref:System.Windows.Forms.ProgressBar>完了するまでの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-170">While the calculation is running in the background, you will see the <xref:System.Windows.Forms.ProgressBar> displaying the progress of the calculation toward completion.</span></span> <span data-ttu-id="b34fa-171">また、保留中の操作をキャンセルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b34fa-171">You can also cancel the pending operation.</span></span>

<span data-ttu-id="b34fa-172">数値が小さい場合、計算に時間はかかりませんが、数値が大きくなると、大幅な遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-172">For small numbers, the calculation should be very fast, but for larger numbers, you should see a noticeable delay.</span></span> <span data-ttu-id="b34fa-173">30 以上の値を入力した場合、コンピューターの速度によっては数秒の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-173">If you enter a value of 30 or greater, you should see a delay of several seconds, depending on the speed of your computer.</span></span> <span data-ttu-id="b34fa-174">値が 40 を超えると、計算が終了するまでに数分から数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b34fa-174">For values greater than 40, it may take minutes or hours to finish the calculation.</span></span> <span data-ttu-id="b34fa-175">電卓が大きなフィボナッチ数を計算している間も、フォームの移動、最小化、最大化を自由に行うことができ、フォームを閉じることもできます。</span><span class="sxs-lookup"><span data-stu-id="b34fa-175">While the calculator is busy computing a large Fibonacci number, notice that you can freely move the form around, minimize, maximize, and even dismiss it.</span></span> <span data-ttu-id="b34fa-176">これは、メイン UI スレッドが計算の終了を待機していないためです。</span><span class="sxs-lookup"><span data-stu-id="b34fa-176">This is because the main UI thread is not waiting for the calculation to finish.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b34fa-177">次の手順</span><span class="sxs-lookup"><span data-stu-id="b34fa-177">Next steps</span></span>

<span data-ttu-id="b34fa-178">使用するフォームを実装している、<xref:System.ComponentModel.BackgroundWorker>バック グラウンドで計算を実行するコンポーネントの他の非同期操作の可能性を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="b34fa-178">Now that you have implemented a form that uses a <xref:System.ComponentModel.BackgroundWorker> component to execute a computation in the background, you can explore other possibilities for asynchronous operations:</span></span>

- <span data-ttu-id="b34fa-179">複数回使用<xref:System.ComponentModel.BackgroundWorker>複数の同時操作のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b34fa-179">Use multiple <xref:System.ComponentModel.BackgroundWorker> objects for several simultaneous operations.</span></span>

- <span data-ttu-id="b34fa-180">マルチ スレッド アプリケーションをデバッグするを参照してください。[方法。[スレッド] ウィンドウを使用して、](/visualstudio/debugger/how-to-use-the-threads-window)します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-180">To debug your multithreaded application, see [How to: Use the Threads Window](/visualstudio/debugger/how-to-use-the-threads-window).</span></span>

- <span data-ttu-id="b34fa-181">非同期プログラミング モデルをサポートする独自のコンポーネントを実装する。</span><span class="sxs-lookup"><span data-stu-id="b34fa-181">Implement your own component that supports the asynchronous programming model.</span></span> <span data-ttu-id="b34fa-182">詳細については、「[イベント ベースの非同期パターンの概要](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fa-182">For more information, see [Event-based Asynchronous Pattern Overview](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="b34fa-183">どのような種類のマルチスレッドを使用している場合でも、非常に深刻で複雑なバグを引き起こしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b34fa-183">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="b34fa-184">マルチスレッドを使用するソリューションを実装する前に、「[マネージド スレッド処理の実施](../../../standard/threading/managed-threading-best-practices.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fa-184">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>

## <a name="see-also"></a><span data-ttu-id="b34fa-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="b34fa-185">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- [<span data-ttu-id="b34fa-186">マネージド スレッド処理</span><span class="sxs-lookup"><span data-stu-id="b34fa-186">Managed Threading</span></span>](../../../standard/threading/index.md)
- [<span data-ttu-id="b34fa-187">マネージド スレッド処理の実施</span><span class="sxs-lookup"><span data-stu-id="b34fa-187">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)
- [<span data-ttu-id="b34fa-188">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="b34fa-188">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="b34fa-189">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="b34fa-189">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="b34fa-190">チュートリアル: バック グラウンドで操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b34fa-190">Walkthrough: Running an Operation in the Background</span></span>](walkthrough-running-an-operation-in-the-background.md)
- [<span data-ttu-id="b34fa-191">BackgroundWorker コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b34fa-191">BackgroundWorker Component</span></span>](backgroundworker-component.md)
