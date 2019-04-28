---
title: 'チュートリアル: 操作をバックグラウンドで実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: c1881ffa1c6fca546b086efea59d2263af853949
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792172"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a><span data-ttu-id="cafd1-102">チュートリアル: 操作をバックグラウンドで実行する</span><span class="sxs-lookup"><span data-stu-id="cafd1-102">Walkthrough: Running an Operation in the Background</span></span>
<span data-ttu-id="cafd1-103">完了に長い時間がかかる操作を実行しており、ユーザー インターフェイスで遅延が発生しないようにするには<xref:System.ComponentModel.BackgroundWorker> クラスを使用して別のスレッドで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="cafd1-104">この例で使用するコードの完全な一覧については、次を参照してください。[方法。バックグラウンドで操作を実行する](how-to-run-an-operation-in-the-background.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cafd1-104">For a complete listing of the code used in this example, see [How to: Run an Operation in the Background](how-to-run-an-operation-in-the-background.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cafd1-105">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cafd1-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cafd1-106">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cafd1-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cafd1-107">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cafd1-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-run-an-operation-in-the-background"></a><span data-ttu-id="cafd1-108">バック グラウンドで操作を実行するには</span><span class="sxs-lookup"><span data-stu-id="cafd1-108">To run an operation in the background</span></span>  
  
1. <span data-ttu-id="cafd1-109">2 つの Windows フォーム デザイナーでアクティブなフォームにドラッグ<xref:System.Windows.Forms.Button>コントロールを**ツールボックス**フォームを設定して、`Name`と<xref:System.Windows.Forms.Control.Text%2A>次の表に従って、ボタンのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cafd1-109">With your form active in the Windows Forms Designer, drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to the form, and then set the `Name` and <xref:System.Windows.Forms.Control.Text%2A> properties of the buttons according to the following table.</span></span>  
  
    |<span data-ttu-id="cafd1-110">ボタン</span><span class="sxs-lookup"><span data-stu-id="cafd1-110">Button</span></span>|<span data-ttu-id="cafd1-111">名前</span><span class="sxs-lookup"><span data-stu-id="cafd1-111">Name</span></span>|<span data-ttu-id="cafd1-112">テキスト</span><span class="sxs-lookup"><span data-stu-id="cafd1-112">Text</span></span>|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|<span data-ttu-id="cafd1-113">**[開始]**</span><span class="sxs-lookup"><span data-stu-id="cafd1-113">**Start**</span></span>|  
    |`button2`|`cancelBtn`|<span data-ttu-id="cafd1-114">**キャンセル**</span><span class="sxs-lookup"><span data-stu-id="cafd1-114">**Cancel**</span></span>|  
  
2. <span data-ttu-id="cafd1-115">開く、**ツールボックス**、クリックして、**コンポーネント**タブをクリックし、ドラッグ、<xref:System.ComponentModel.BackgroundWorker>コンポーネントをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="cafd1-115">Open the **Toolbox**, click the **Components** tab, and then drag the <xref:System.ComponentModel.BackgroundWorker> component onto your form.</span></span>  
  
     <span data-ttu-id="cafd1-116">`backgroundWorker1`コンポーネントに表示されます、**コンポーネント トレイ**します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-116">The `backgroundWorker1` component appears in the **Component Tray**.</span></span>  
  
3. <span data-ttu-id="cafd1-117">**[プロパティ]** ウィンドウで、 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-117">In the **Properties** window, set the <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> property to `true`.</span></span>  
  
4. <span data-ttu-id="cafd1-118">**プロパティ**ウィンドウの**イベント**ボタンをクリックし、ダブルクリック、<xref:System.ComponentModel.BackgroundWorker.DoWork>と<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベントをイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-118">In the **Properties** window, click on the **Events** button, and then double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span>  
  
5. <span data-ttu-id="cafd1-119">挿入に時間のかかるコード、<xref:System.ComponentModel.BackgroundWorker.DoWork>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="cafd1-119">Insert your time-consuming code into the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span>  
  
6. <span data-ttu-id="cafd1-120">操作に必要なすべてのパラメーターを抽出、<xref:System.ComponentModel.DoWorkEventArgs.Argument%2A>のプロパティ、<xref:System.ComponentModel.DoWorkEventArgs>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="cafd1-120">Extract any parameters required by the operation from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs> parameter.</span></span>  
  
7. <span data-ttu-id="cafd1-121">計算の結果に割り当てる、<xref:System.ComponentModel.DoWorkEventArgs.Result%2A>のプロパティ、<xref:System.ComponentModel.DoWorkEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-121">Assign the result of the computation to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span>  
  
     <span data-ttu-id="cafd1-122">これは使用できる、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="cafd1-122">This is will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8. <span data-ttu-id="cafd1-123">操作の結果を取得するためのコードを挿入、<xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="cafd1-123">Insert code for retrieving the result of your operation in the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. <span data-ttu-id="cafd1-124">`TimeConsumingOperation` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-124">Implement the `TimeConsumingOperation` method.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="cafd1-125">Windows フォーム デザイナーで、ダブルクリック`startButton`を作成する、<xref:System.Windows.Forms.Control.Click>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="cafd1-125">In the Windows Forms Designer, double-click `startButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
11. <span data-ttu-id="cafd1-126">呼び出す、<xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A>メソッドで、<xref:System.Windows.Forms.Control.Click>のイベント ハンドラー`startButton`します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-126">Call the <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `startButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. <span data-ttu-id="cafd1-127">Windows フォーム デザイナーで、ダブルクリック`cancelButton`を作成する、<xref:System.Windows.Forms.Control.Click>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="cafd1-127">In the Windows Forms Designer, double-click `cancelButton` to create the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
13. <span data-ttu-id="cafd1-128">呼び出す、<xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>メソッドで、<xref:System.Windows.Forms.Control.Click>のイベント ハンドラー`cancelButton`します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-128">Call the <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> method in the <xref:System.Windows.Forms.Control.Click> event handler for `cancelButton`.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. <span data-ttu-id="cafd1-129">ファイルの上部にある、System.ComponentModel および System.Threading 名前空間をインポートします。</span><span class="sxs-lookup"><span data-stu-id="cafd1-129">At the top of the file, import the System.ComponentModel and System.Threading namespaces.</span></span>  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. <span data-ttu-id="cafd1-130">ソリューションをビルドする f6 キーを押すし、デバッガーの外部のアプリケーションを実行する ctrl + f5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-130">Press F6 to build the solution, and then press CTRL-F5 to run the application outside the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cafd1-131">例外が発生した場合は、デバッガーの下でアプリケーションの実行に f5 キーを押すと、`TimeConsumingOperation`メソッドがキャッチされ、デバッガーによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-131">If you press F5 to run the application under the debugger, the exception raised in the `TimeConsumingOperation` method is caught and displayed by the debugger.</span></span> <span data-ttu-id="cafd1-132">デバッガーの外部のアプリケーションを実行すると、 <xref:System.ComponentModel.BackgroundWorker> 、例外を処理し、キャッシュで、<xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A>のプロパティ、<xref:System.ComponentModel.RunWorkerCompletedEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-132">When you run the application outside the debugger, the <xref:System.ComponentModel.BackgroundWorker> handles the exception and caches it in the <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> property of the <xref:System.ComponentModel.RunWorkerCompletedEventArgs>.</span></span>  
  
1. <span data-ttu-id="cafd1-133">をクリックして、**開始**、非同期操作を実行するボタンをクリックし、をクリックし、**キャンセル**実行中の非同期操作を停止するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cafd1-133">Click the **Start** button to run an asynchronous operation, and then click the **Cancel** button to stop a running asynchronous operation.</span></span>  
  
     <span data-ttu-id="cafd1-134">各操作の結果は、<xref:System.Windows.Forms.MessageBox> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cafd1-134">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cafd1-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="cafd1-135">Next Steps</span></span>  
  
- <span data-ttu-id="cafd1-136">非同期操作の進行に伴って進行状況を報告するフォームを実装します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-136">Implement a form that reports progress as an asynchronous operation proceeds.</span></span> <span data-ttu-id="cafd1-137">詳細については、「[方法 :バック グラウンド操作を使用してフォームを実装する](how-to-implement-a-form-that-uses-a-background-operation.md)します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-137">For more information, see [How to: Implement a Form That Uses a Background Operation](how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
- <span data-ttu-id="cafd1-138">コンポーネントの非同期パターンをサポートするクラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-138">Implement a class that supports the Asynchronous Pattern for Components.</span></span> <span data-ttu-id="cafd1-139">詳細については、次を参照してください。[イベント ベースの非同期パターンを実装する](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)します。</span><span class="sxs-lookup"><span data-stu-id="cafd1-139">For more information, see [Implementing the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cafd1-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="cafd1-140">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="cafd1-141">方法: バックグラウンド操作を使用するフォームを実装する</span><span class="sxs-lookup"><span data-stu-id="cafd1-141">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="cafd1-142">方法: バックグラウンドで操作を実行する</span><span class="sxs-lookup"><span data-stu-id="cafd1-142">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)
- [<span data-ttu-id="cafd1-143">BackgroundWorker コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cafd1-143">BackgroundWorker Component</span></span>](backgroundworker-component.md)
