---
title: WPF アプリでのインクを収集します。
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
ms.openlocfilehash: d2178a4cbf888baaf0ae84b03b3d463b0de658b1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645729"
---
# <a name="collect-ink"></a><span data-ttu-id="26175-102">インクを収集します。</span><span class="sxs-lookup"><span data-stu-id="26175-102">Collect Ink</span></span>

<span data-ttu-id="26175-103">[Windows Presentation Foundation](../index.md) プラットフォームでは、その機能の中核としてデジタル インクが収集されます。</span><span class="sxs-lookup"><span data-stu-id="26175-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="26175-104">このトピックでは、Windows Presentation Foundation (WPF) でのインクの収集方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26175-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26175-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="26175-105">Prerequisites</span></span>

<span data-ttu-id="26175-106">次の例を使用する、Visual Studio をインストールする必要があります最初、[!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="26175-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="26175-107">WPF のアプリケーションを作成する方法を理解することもあります。</span><span class="sxs-lookup"><span data-stu-id="26175-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="26175-108">WPF の概要については、次を参照してください。[チュートリアル。初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="26175-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="26175-109">InkCanvas 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="26175-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="26175-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName>要素は、WPF のインクを収集する最も簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="26175-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="26175-111">使用して、<xref:System.Windows.Controls.InkCanvas>要素を受信し、インク入力を表示します。</span><span class="sxs-lookup"><span data-stu-id="26175-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="26175-112">インクは一般的に、スタイラスを使用して入力します。スタイラスはデジタイザーとの対話により、インク ストロークを生成します。</span><span class="sxs-lookup"><span data-stu-id="26175-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="26175-113">また、スタイラスの代わりにマウスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="26175-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="26175-114">生成されたストロークとして表される<xref:System.Windows.Ink.Stroke>プログラムとユーザーの両方の入力、オブジェクト、およびそれらを操作できます。</span><span class="sxs-lookup"><span data-stu-id="26175-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="26175-115"><xref:System.Windows.Controls.InkCanvas>ユーザーを選択し、変更、または、既存の削除をできるように<xref:System.Windows.Ink.Stroke>します。</span><span class="sxs-lookup"><span data-stu-id="26175-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="26175-116">XAML を使用して設定できますインク コレクションの追加と簡単に、 **InkCanvas**ツリーの要素。</span><span class="sxs-lookup"><span data-stu-id="26175-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="26175-117">次の例では、追加、<xref:System.Windows.Controls.InkCanvas>既定の WPF プロジェクトは Visual Studio で作成します。</span><span class="sxs-lookup"><span data-stu-id="26175-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="26175-118">**InkCanvas**要素は、XAML 要素のほぼすべての種類にインク注釈機能を追加することの子要素を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="26175-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="26175-119">たとえば、テキスト要素には、手描き入力機能を追加するに単に使用するの子、 <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="26175-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="26175-120">インクの画像をマークするためのサポートを追加すると、同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="26175-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="26175-121">InkCollection モード</span><span class="sxs-lookup"><span data-stu-id="26175-121">InkCollection Modes</span></span>

<span data-ttu-id="26175-122"><xref:System.Windows.Controls.InkCanvas>サポートは、さまざまな入力モードをその<xref:System.Windows.Controls.InkCanvas.EditingMode%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="26175-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="26175-123">インクを操作します。</span><span class="sxs-lookup"><span data-stu-id="26175-123">Manipulate Ink</span></span>

<span data-ttu-id="26175-124"><xref:System.Windows.Controls.InkCanvas>多くのインク編集操作のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="26175-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="26175-125">たとえば、<xref:System.Windows.Controls.InkCanvas>サポート ペンのバックアップは、消去、要素に機能を追加する追加のコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="26175-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="26175-126">選択ツール</span><span class="sxs-lookup"><span data-stu-id="26175-126">Selection</span></span>

<span data-ttu-id="26175-127">選択モードの設定だけでは、<xref:System.Windows.Controls.InkCanvasEditingMode>プロパティを**選択**します。</span><span class="sxs-lookup"><span data-stu-id="26175-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="26175-128">次のコードの値に基づいて編集モードの設定、 <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="26175-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="26175-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="26175-129">DrawingAttributes</span></span>

<span data-ttu-id="26175-130">使用して、<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>インク ストロークの外観を変更するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="26175-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="26175-131">たとえば、<xref:System.Windows.Ink.DrawingAttributes.Color%2A>のメンバー <xref:System.Windows.Ink.DrawingAttributes> 、表示の色を設定<xref:System.Windows.Ink.Stroke>します。</span><span class="sxs-lookup"><span data-stu-id="26175-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="26175-132">次の例では、選択したストロークの色を red に変更します。</span><span class="sxs-lookup"><span data-stu-id="26175-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="26175-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="26175-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="26175-134"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>プロパティは、高さ、幅、およびで作成されるストロークの色などのプロパティへのアクセスを提供する<xref:System.Windows.Controls.InkCanvas>します。</span><span class="sxs-lookup"><span data-stu-id="26175-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="26175-135">変更すると、<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>に入力されるストロークはすべて、<xref:System.Windows.Controls.InkCanvas>新しいプロパティ値で表示されます。</span><span class="sxs-lookup"><span data-stu-id="26175-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="26175-136">変更するだけでなく、<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>を指定する XAML 構文を使用する分離コード ファイルで<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="26175-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="26175-137">次の例は、設定する方法を示します、<xref:System.Windows.Ink.DrawingAttributes.Color%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="26175-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="26175-138">このコードを使用するには、Visual Studio で"helloinkcanvas"新しい WPF プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="26175-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="26175-139">コードに置き換えます、 *MainWindow.xaml*を次のコード ファイル。</span><span class="sxs-lookup"><span data-stu-id="26175-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="26175-140">次に、MainWindow クラス内のファイルのコードが次のボタン イベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="26175-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="26175-141">このコードをコピーした後、キーを押して**F5** Visual Studio で、デバッガーでプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="26175-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="26175-142">通知方法、<xref:System.Windows.Controls.StackPanel>ボタンの上に配置、<xref:System.Windows.Controls.InkCanvas>します。</span><span class="sxs-lookup"><span data-stu-id="26175-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="26175-143">ボタンの上にインクを試みると、<xref:System.Windows.Controls.InkCanvas>を収集し、ボタンの背後にある、インクをレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="26175-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="26175-144">これは、ボタンの兄弟であるため、<xref:System.Windows.Controls.InkCanvas>子とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="26175-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="26175-145">また、ボタンは z オーダーの上位に位置するため、インクはその背後で描画されます。</span><span class="sxs-lookup"><span data-stu-id="26175-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="26175-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="26175-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
