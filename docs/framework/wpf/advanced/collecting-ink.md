---
title: WPF アプリでインクを収集する
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 8109e0d6a746d6ca23c25643c510014c1a1e656c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740877"
---
# <a name="collect-ink"></a><span data-ttu-id="9ca26-102">インクの収集</span><span class="sxs-lookup"><span data-stu-id="9ca26-102">Collect Ink</span></span>

<span data-ttu-id="9ca26-103">[Windows Presentation Foundation](../index.md) プラットフォームでは、その機能の中核としてデジタル インクが収集されます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="9ca26-104">このトピックでは、Windows Presentation Foundation (WPF) でインクを収集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ca26-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="9ca26-105">Prerequisites</span></span>

<span data-ttu-id="9ca26-106">次の例を使用するには、最初に Visual Studio と Windows SDK をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ca26-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="9ca26-107">WPF 用のアプリケーションを作成する方法についても理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ca26-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="9ca26-108">WPF の概要については、「[チュートリアル: 初めての wpf デスクトップアプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ca26-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="9ca26-109">System.windows.controls.inkcanvas> 要素を使用する</span><span class="sxs-lookup"><span data-stu-id="9ca26-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="9ca26-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> 要素は、WPF でインクを収集する最も簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="9ca26-111"><xref:System.Windows.Controls.InkCanvas> 要素を使用して、インク入力を受信して表示します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="9ca26-112">インクは一般的に、スタイラスを使用して入力します。スタイラスはデジタイザーとの対話により、インク ストロークを生成します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="9ca26-113">また、スタイラスの代わりにマウスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="9ca26-114">作成されたストロークは <xref:System.Windows.Ink.Stroke> オブジェクトとして表され、プログラムとユーザー入力の両方で操作できます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="9ca26-115"><xref:System.Windows.Controls.InkCanvas> を使用すると、ユーザーは既存の <xref:System.Windows.Ink.Stroke>を選択、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="9ca26-116">XAML を使用すると、 **system.windows.controls.inkcanvas>** 要素をツリーに追加するのと同じくらい簡単にインクコレクションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="9ca26-117">次の例では、Visual Studio で作成された既定の WPF プロジェクトに <xref:System.Windows.Controls.InkCanvas> を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="9ca26-118">**System.windows.controls.inkcanvas>** 要素に子要素を含めることもできます。これにより、ほぼすべての種類の XAML 要素にインク注釈機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="9ca26-119">たとえば、テキスト要素にインク機能を追加するには、単に <xref:System.Windows.Controls.InkCanvas>の子にします。</span><span class="sxs-lookup"><span data-stu-id="9ca26-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="9ca26-120">画像をインクでマークするためのサポートを追加するのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="9ca26-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="9ca26-121">InkCollection モード</span><span class="sxs-lookup"><span data-stu-id="9ca26-121">InkCollection Modes</span></span>

<span data-ttu-id="9ca26-122"><xref:System.Windows.Controls.InkCanvas> は、<xref:System.Windows.Controls.InkCanvas.EditingMode%2A> プロパティを通じてさまざまな入力モードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9ca26-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="9ca26-123">インクを操作する</span><span class="sxs-lookup"><span data-stu-id="9ca26-123">Manipulate Ink</span></span>

<span data-ttu-id="9ca26-124"><xref:System.Windows.Controls.InkCanvas> では、多くのインク編集操作がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9ca26-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="9ca26-125">たとえば、<xref:System.Windows.Controls.InkCanvas> では、ペンの前の消去がサポートされており、要素に機能を追加するための追加のコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9ca26-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="9ca26-126">選択ツール</span><span class="sxs-lookup"><span data-stu-id="9ca26-126">Selection</span></span>

<span data-ttu-id="9ca26-127">選択モードの設定は、<xref:System.Windows.Controls.InkCanvasEditingMode> プロパティを **[選択]** に設定するのと同じように簡単です。</span><span class="sxs-lookup"><span data-stu-id="9ca26-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="9ca26-128">次のコードは、<xref:System.Windows.Forms.CheckBox>の値に基づいて編集モードを設定します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="9ca26-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="9ca26-129">DrawingAttributes</span></span>

<span data-ttu-id="9ca26-130">インクストロークの外観を変更するには、<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="9ca26-131">たとえば、<xref:System.Windows.Ink.DrawingAttributes> の <xref:System.Windows.Ink.DrawingAttributes.Color%2A> メンバーは、レンダリングされた <xref:System.Windows.Ink.Stroke>の色を設定します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="9ca26-132">次の例では、選択したストロークの色を赤に変更します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="9ca26-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="9ca26-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="9ca26-134"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> プロパティを使用すると、<xref:System.Windows.Controls.InkCanvas>で作成するストロークの高さ、幅、色などのプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="9ca26-135"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>を変更すると、その後 <xref:System.Windows.Controls.InkCanvas> に入力したすべてのストロークが、新しいプロパティ値と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="9ca26-136">分離コードファイル内の <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> を変更するだけでなく、XAML 構文を使用して <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> プロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="9ca26-137">次の例では、<xref:System.Windows.Ink.DrawingAttributes.Color%2A> プロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="9ca26-138">このコードを使用するには、Visual Studio で "HelloInkCanvas" という名前の新しい WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="9ca26-139">*Mainwindow.xaml*ファイル内のコードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="9ca26-140">次に、次のボタンイベントハンドラーを Mainwindow.xaml クラス内の分離コードファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="9ca26-141">このコードをコピーしたら、Visual Studio で**F5**キーを押して、デバッガーでプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ca26-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="9ca26-142"><xref:System.Windows.Controls.StackPanel> によって、ボタンが <xref:System.Windows.Controls.InkCanvas>の上に配置されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9ca26-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="9ca26-143">ボタンの上部でインクを試すと、<xref:System.Windows.Controls.InkCanvas> はボタンの背後にあるインクを収集してレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="9ca26-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="9ca26-144">これは、ボタンが子ではなく、<xref:System.Windows.Controls.InkCanvas> の兄弟であるためです。</span><span class="sxs-lookup"><span data-stu-id="9ca26-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="9ca26-145">また、ボタンは z オーダーの上位に位置するため、インクはその背後で描画されます。</span><span class="sxs-lookup"><span data-stu-id="9ca26-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ca26-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ca26-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
