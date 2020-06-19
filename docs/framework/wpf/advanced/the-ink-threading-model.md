---
title: インク スレッド モデル
ms.date: 03/30/2017
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
ms.openlocfilehash: b753fcffbdaa1cc9ba960a774077457dd0263e0a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621371"
---
# <a name="the-ink-threading-model"></a><span data-ttu-id="eca20-102">インク スレッド モデル</span><span class="sxs-lookup"><span data-stu-id="eca20-102">The Ink Threading Model</span></span>
<span data-ttu-id="eca20-103">タブレット PC のインクの利点の 1 つが、通常のペンを使って紙に書く感覚に非常に似ていることです。</span><span class="sxs-lookup"><span data-stu-id="eca20-103">One of the benefits of ink on a Tablet PC is that it feels a lot like writing with a regular pen and paper.</span></span>  <span data-ttu-id="eca20-104">これを実現するために、タブレット ペンでは、マウスよりもはるかに高速に入力データが収集され、ユーザーが書くときに、インクがレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-104">To accomplish this, the tablet pen collects input data at a much higher rate than a mouse does and renders the ink as the user writes.</span></span>  <span data-ttu-id="eca20-105">アプリケーションのユーザー インターフェイス (UI) スレッドは、ペン データを収集してインクをレンダリングするのに十分ではありません。ブロックされる可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="eca20-105">The application's user interface (UI) thread is not sufficient for collecting pen data and rendering ink, because it can become blocked.</span></span>  <span data-ttu-id="eca20-106">これを解決するには、ユーザーがインクを書き込むときに、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] アプリケーションで、2 つの追加のスレッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="eca20-106">To solve this, a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application uses two additional threads when a user writes ink.</span></span>  
  
 <span data-ttu-id="eca20-107">次の一覧は、デジタル インクの収集とレンダリングに参加するスレッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="eca20-107">The following list describes the threads that take part in collecting and rendering digital ink:</span></span>  
  
- <span data-ttu-id="eca20-108">ペン スレッド - スタイラスからの入力を受け取るスレッド</span><span class="sxs-lookup"><span data-stu-id="eca20-108">Pen thread - the thread that takes input from the stylus.</span></span>  <span data-ttu-id="eca20-109">(実際には、これはスレッド プールですが、このトピックではペン スレッドと呼びます)。</span><span class="sxs-lookup"><span data-stu-id="eca20-109">(In reality, this is a thread pool, but this topic refers to it as a pen thread.)</span></span>  
  
- <span data-ttu-id="eca20-110">アプリケーション ユーザー インターフェイス スレッド - アプリケーションのユーザー インターフェイスを制御するスレッド。</span><span class="sxs-lookup"><span data-stu-id="eca20-110">Application user interface thread - the thread that controls the user interface of the application.</span></span>  
  
- <span data-ttu-id="eca20-111">動的レンダリング スレッド - ユーザーがストロークを描画している間、インクをレンダリングするスレッド。</span><span class="sxs-lookup"><span data-stu-id="eca20-111">Dynamic rendering thread - the thread that renders the ink while the user draws a stroke.</span></span> <span data-ttu-id="eca20-112">動的レンダリング スレッドは、Window Presentation Foundation [スレッド モデル](threading-model.md)に説明されているように、アプリケーションの他の UI 要素をレンダリングするスレッドとは別です。</span><span class="sxs-lookup"><span data-stu-id="eca20-112">The dynamic rendering thread is different than the thread that renders other UI elements for the application, as mentioned in Window Presentation Foundation [Threading Model](threading-model.md).</span></span>  
  
 <span data-ttu-id="eca20-113">アプリケーションで使用されるのが、<xref:System.Windows.Controls.InkCanvas> でも、[インク入力コントロール作成](creating-an-ink-input-control.md)時のものに似たカスタム コントロールでも、インク モデルは同じです。</span><span class="sxs-lookup"><span data-stu-id="eca20-113">The inking model is the same whether the application uses the <xref:System.Windows.Controls.InkCanvas> or a custom control similar to the one in [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  <span data-ttu-id="eca20-114">このトピックでは、スレッドについて <xref:System.Windows.Controls.InkCanvas> の観点から説明しますが、カスタム コントロールを作成する場合も同じ概念が適用されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-114">Although this topic discusses threading in terms of the <xref:System.Windows.Controls.InkCanvas>, the same concepts apply when you create a custom control.</span></span>  
  
## <a name="threading-overview"></a><span data-ttu-id="eca20-115">スレッドの概要</span><span class="sxs-lookup"><span data-stu-id="eca20-115">Threading Overview</span></span>  
 <span data-ttu-id="eca20-116">次の図は、ユーザーがストロークを描画するときのスレッド モデルを示しています。</span><span class="sxs-lookup"><span data-stu-id="eca20-116">The following diagram illustrates the threading model when a user draws a stroke:</span></span>  
  
 <span data-ttu-id="eca20-117">![ストローク描画中のスレッド モデル。](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span><span class="sxs-lookup"><span data-stu-id="eca20-117">![Threading model while drawing a stroke.](./media/inkthreading-drawingink.png "InkThreading_DrawingInk")</span></span>  
  
1. <span data-ttu-id="eca20-118">ユーザーがストロークを描画している間発生するアクション</span><span class="sxs-lookup"><span data-stu-id="eca20-118">Actions occurring while the user draws the stroke</span></span>  
  
    1. <span data-ttu-id="eca20-119">ユーザーがストロークを描画すると、スタイラス ポイントがペン スレッドに送られます。</span><span class="sxs-lookup"><span data-stu-id="eca20-119">When the user draws a stroke, the stylus points come in on the pen thread.</span></span>  <span data-ttu-id="eca20-120">ペン スレッドで、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> などのスタイラス プラグインにより、スタイラス ポイントが受け入れられ、<xref:System.Windows.Controls.InkCanvas> によって受け取られる前に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="eca20-120">Stylus plug-ins, including the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, accept the stylus points on the pen thread and have the chance to modify them before the <xref:System.Windows.Controls.InkCanvas> receives them.</span></span>  
  
    2. <span data-ttu-id="eca20-121">動的レンダリング スレッドで、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> により、スタイラス ポイントがレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-121">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the stylus points on the dynamic rendering thread.</span></span> <span data-ttu-id="eca20-122">これは、前のステップと同時に発生します。</span><span class="sxs-lookup"><span data-stu-id="eca20-122">This happens at the same time as the previous step.</span></span>  
  
    3. <span data-ttu-id="eca20-123">UI スレッドで、<xref:System.Windows.Controls.InkCanvas> により、スタイラス ポイントが受け取られます。</span><span class="sxs-lookup"><span data-stu-id="eca20-123">The <xref:System.Windows.Controls.InkCanvas> receives the stylus points on the UI thread.</span></span>  
  
2. <span data-ttu-id="eca20-124">ユーザーがストロークを終了した後に発生するアクション</span><span class="sxs-lookup"><span data-stu-id="eca20-124">Actions occurring after the user ends the stroke</span></span>  
  
    1. <span data-ttu-id="eca20-125">ユーザーがストロークの描画を終了すると、<xref:System.Windows.Controls.InkCanvas> により <xref:System.Windows.Ink.Stroke> オブジェクトが作成され、<xref:System.Windows.Controls.InkPresenter> に追加されます。これにより、静的にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-125">When the user finishes drawing the stroke, the <xref:System.Windows.Controls.InkCanvas> creates a <xref:System.Windows.Ink.Stroke> object and adds it to the <xref:System.Windows.Controls.InkPresenter>, which statically renders it.</span></span>  
  
    2. <span data-ttu-id="eca20-126">UI スレッドにより、ストロークが静的にレンダリングされたことが <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> に警告され、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、ストロークの視覚表示が削除されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-126">The UI thread alerts the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> that the stroke is statically rendered, so the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> removes its visual representation of the stroke.</span></span>  
  
## <a name="ink-collection-and-stylus-plug-ins"></a><span data-ttu-id="eca20-127">インク コレクションとスタイラス プラグイン</span><span class="sxs-lookup"><span data-stu-id="eca20-127">Ink collection and Stylus Plug-ins</span></span>  
 <span data-ttu-id="eca20-128">各 <xref:System.Windows.UIElement> には <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eca20-128">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  <span data-ttu-id="eca20-129"><xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 内の <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> オブジェクトで、ペン スレッドのスタイラス ポイントを受け取り、変更することができます。</span><span class="sxs-lookup"><span data-stu-id="eca20-129">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> receive and can modify the stylus points on the pen thread.</span></span> <span data-ttu-id="eca20-130"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> オブジェクトにより、<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> の順序に従ってスタイラス ポイントを受け取られます。</span><span class="sxs-lookup"><span data-stu-id="eca20-130">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects receive the stylus points according to their order in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span>  
  
 <span data-ttu-id="eca20-131">次の図は、<xref:System.Windows.UIElement> の <xref:System.Windows.UIElement.StylusPlugIns%2A> コレクションに `stylusPlugin1`、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>、`stylusPlugin2` がこの順序で含まれているという仮定の状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="eca20-131">The following diagram illustrates the hypothetical situation where the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection of a <xref:System.Windows.UIElement> contains `stylusPlugin1`, a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, and `stylusPlugin2`, in that order.</span></span>  
  
 <span data-ttu-id="eca20-132">![スタイラス プラグインの順序が出力に影響する。](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span><span class="sxs-lookup"><span data-stu-id="eca20-132">![Order of Stylus Plugins affect output.](./media/inkthreading-pluginorder.png "InkThreading_PluginOrder")</span></span>  
  
 <span data-ttu-id="eca20-133">上の図では、次の動作が行われます。</span><span class="sxs-lookup"><span data-stu-id="eca20-133">In the previous diagram, the following behavior takes place:</span></span>  
  
1. <span data-ttu-id="eca20-134">`StylusPlugin1` で、x と y の値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-134">`StylusPlugin1` modifies the values for x and y.</span></span>  
  
2. <span data-ttu-id="eca20-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、変更されたスタイラス ポイントが受け取られ、動的レンダリング スレッド上にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-135"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the modified stylus points and renders them on the dynamic rendering thread.</span></span>  
  
3. <span data-ttu-id="eca20-136">`StylusPlugin2` で、変更されたスタイラス ポイントが受け取られ、x と y の値がさらに変更されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-136">`StylusPlugin2` receives the modified stylus points and further modifies the values for x and y.</span></span>  
  
4. <span data-ttu-id="eca20-137">アプリケーションで、スタイラス ポイントが収集され、ユーザーがストロークを終了したときに、ストロークが静的にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-137">The application collects the stylus points, and, when the user finishes the stroke, statically renders the stroke.</span></span>  
  
 <span data-ttu-id="eca20-138">`stylusPlugin1` で、スタイラス ポイントが四角形に制限され、`stylusPlugin2` で、スタイラス ポイントを右に移動するとします。</span><span class="sxs-lookup"><span data-stu-id="eca20-138">Suppose that `stylusPlugin1` restricts the stylus points to a rectangle and `stylusPlugin2` translates the stylus points to the right.</span></span>  <span data-ttu-id="eca20-139">前のシナリオでは、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、制限付きのスタイラス ポイントを受け取りますが、移動されたスタイラス ポイントは受け取りません。</span><span class="sxs-lookup"><span data-stu-id="eca20-139">In the previous scenario, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives the restricted stylus points, but not the translated stylus points.</span></span>  <span data-ttu-id="eca20-140">ユーザーがストロークを描画すると、ストロークは四角形の境界内にレンダリングされますが、ユーザーがペンを持ち上げるまでストロークは移動したようには見えません。</span><span class="sxs-lookup"><span data-stu-id="eca20-140">When the user draws the stroke, the stroke is rendered within the bounds of the rectangle, but the stroke doesn't appear to be translated until the user lifts the pen.</span></span>  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a><span data-ttu-id="eca20-141">UI スレッドでスタイラス プラグインを使用して操作を実行する</span><span class="sxs-lookup"><span data-stu-id="eca20-141">Performing operations with a Stylus Plug-in on the UI thread</span></span>  
 <span data-ttu-id="eca20-142">ペン スレッドでは正確なヒットテストを実行できないため、一部の要素で、他の要素向けのスタイラス入力が受け取られることがあります。</span><span class="sxs-lookup"><span data-stu-id="eca20-142">Because accurate hit-testing cannot be performed on the pen thread, some elements might occasionally receive stylus input intended for other elements.</span></span> <span data-ttu-id="eca20-143">操作を実行する前に入力が正しくルーティングされたことを確認する必要がある場合は、<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>、<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>、または <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> メソッドをサブスクライブし、操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="eca20-143">If you need to make sure the input was routed correctly before performing an operation, subscribe to and perform the operation in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>, or <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A> method.</span></span> <span data-ttu-id="eca20-144">これらのメソッドは、正確なヒットテストが実行された後に、アプリケーション スレッドから呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-144">These methods are invoked by the application thread after accurate hit-testing has been performed.</span></span> <span data-ttu-id="eca20-145">これらのメソッドをサブスクライブするには、ペン スレッドで発生するメソッド内で <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eca20-145">To subscribe to these methods, call the <xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A> method in the method that occurs on the pen thread.</span></span>  
  
 <span data-ttu-id="eca20-146">次の図は、<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> のスタイラス イベントに関するペン スレッドと UI スレッドの関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="eca20-146">The following diagram illustrates the relationship between the pen thread and UI thread with respect to the stylus events of a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span>  
  
 <span data-ttu-id="eca20-147">![インク スレッド モデル &#40;UI とペン&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span><span class="sxs-lookup"><span data-stu-id="eca20-147">![Ink Threading Models &#40;UI and Pen&#41;](./media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")</span></span>  
  
## <a name="rendering-ink"></a><span data-ttu-id="eca20-148">インクのレンダリング</span><span class="sxs-lookup"><span data-stu-id="eca20-148">Rendering Ink</span></span>  
 <span data-ttu-id="eca20-149">ユーザーがストロークを描画すると、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、インクが別のスレッドにレンダリングされます。これにより、UI スレッドがビジー状態の場合でも、ペンからインクが "流れている" ように見えます。</span><span class="sxs-lookup"><span data-stu-id="eca20-149">As the user draws a stroke, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> renders the ink on a separate thread so the ink appears to "flow" from the pen even when the UI thread is busy.</span></span>  <span data-ttu-id="eca20-150"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、スタイラス ポイントが収集されるときに、動的レンダリング スレッドにビジュアル ツリーが構築されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-150">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds a visual tree on the dynamic rendering thread as it collects stylus points.</span></span>  <span data-ttu-id="eca20-151">ユーザーがストロークを終了すると、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> により、アプリケーションで次のレンダリング パスを実行したときに通知を受け取るように要求されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-151">When the user finishes the stroke, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> asks to be notified when the application does the next rendering pass.</span></span>  <span data-ttu-id="eca20-152">アプリケーションで次のレンダリング パスが完了した後、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> では、ビジュアル ツリーがクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-152">After the application completes the next rendering pass, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up its visual tree.</span></span>  <span data-ttu-id="eca20-153">このプロセスを説明する図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eca20-153">The following diagram illustrates this process.</span></span>  
  
 <span data-ttu-id="eca20-154">![インク スレッドの図](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span><span class="sxs-lookup"><span data-stu-id="eca20-154">![Ink threading diagram](./media/inkthreading-visualtree.png "InkThreading_VisualTree")</span></span>  
  
1. <span data-ttu-id="eca20-155">ユーザーがストロークを開始します。</span><span class="sxs-lookup"><span data-stu-id="eca20-155">The user begins the stroke.</span></span>  
  
    1. <span data-ttu-id="eca20-156"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、ビジュアル ツリーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-156">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> creates the visual tree.</span></span>  
  
2. <span data-ttu-id="eca20-157">ユーザーがストロークを描画し続けています。</span><span class="sxs-lookup"><span data-stu-id="eca20-157">The user is drawing the stroke.</span></span>  
  
    1. <span data-ttu-id="eca20-158"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、ビジュアル ツリーが構築されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-158">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> builds the visual tree.</span></span>  
  
3. <span data-ttu-id="eca20-159">ユーザーがストロークを終了します。</span><span class="sxs-lookup"><span data-stu-id="eca20-159">The user ends the stroke.</span></span>  
  
    1. <span data-ttu-id="eca20-160"><xref:System.Windows.Controls.InkPresenter> により、そのビジュアル ツリーにストロークが追加されます。</span><span class="sxs-lookup"><span data-stu-id="eca20-160">The <xref:System.Windows.Controls.InkPresenter> adds the stroke to its visual tree.</span></span>  
  
    2. <span data-ttu-id="eca20-161">メディア統合レイヤー (MIL) により、ストロークが静的にレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-161">The Media Integration Layer (MIL) statically renders the strokes.</span></span>  
  
    3. <span data-ttu-id="eca20-162"><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> で、ビジュアルがクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="eca20-162">The <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> cleans up the visuals.</span></span>
