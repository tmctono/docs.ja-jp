---
title: '方法: カスタム コントロールからインクを選択する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 5c9b2f3d64e4cbb309772d6a1d9fa88f589df84c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768412"
---
# <a name="how-to-select-ink-from-a-custom-control"></a><span data-ttu-id="44d73-102">方法: カスタム コントロールからインクを選択する</span><span class="sxs-lookup"><span data-stu-id="44d73-102">How to: Select Ink from a Custom Control</span></span>
<span data-ttu-id="44d73-103">追加することで、 <xref:System.Windows.Ink.IncrementalLassoHitTester> 、カスタム コントロールを有効に、コントロールと同様に、なげなわのツールを使用してインクをユーザーが選択できるように、<xref:System.Windows.Controls.InkCanvas>なげなわを使用してインクを選択します。</span><span class="sxs-lookup"><span data-stu-id="44d73-103">By adding an <xref:System.Windows.Ink.IncrementalLassoHitTester> to your custom control, you can enable your control so that a user can select ink with a lasso tool, similar to the way the <xref:System.Windows.Controls.InkCanvas> selects ink with a lasso.</span></span>  
  
 <span data-ttu-id="44d73-104">この例では、インク対応のカスタム コントロールの作成に慣れてを前提としています。</span><span class="sxs-lookup"><span data-stu-id="44d73-104">This example assumes you are familiar with creating an ink-enabled custom control.</span></span>  <span data-ttu-id="44d73-105">インク入力を受け入れるカスタム コントロールを作成するを参照してください。[インク入力コントロールの作成](creating-an-ink-input-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="44d73-105">To create a custom control that accepts ink input, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44d73-106">例</span><span class="sxs-lookup"><span data-stu-id="44d73-106">Example</span></span>  
 <span data-ttu-id="44d73-107">ユーザーが、なげなわ選択を描画するとき、<xref:System.Windows.Ink.IncrementalLassoHitTester>予測するストロークは、ユーザーに、なげなわが完了したら、なげなわのパスの境界内になります。</span><span class="sxs-lookup"><span data-stu-id="44d73-107">When the user draws a lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> predicts which strokes will be within the lasso path's boundaries after the user completes the lasso.</span></span>  <span data-ttu-id="44d73-108">なげなわのパスの境界内に決定されるストロークは、選択されていると考えることができます。</span><span class="sxs-lookup"><span data-stu-id="44d73-108">Strokes that are determined to be within the lasso path's boundaries can be thought of as being selected.</span></span>  <span data-ttu-id="44d73-109">選択されたストロークは選択されていないもなります。</span><span class="sxs-lookup"><span data-stu-id="44d73-109">Selected strokes can also become unselected.</span></span>  <span data-ttu-id="44d73-110">たとえば、ユーザーに、なげなわの描画中に方向が反転、<xref:System.Windows.Ink.IncrementalLassoHitTester>のストロークに選択を解除します。</span><span class="sxs-lookup"><span data-stu-id="44d73-110">For example, if the user reverses direction while drawing the lasso, the <xref:System.Windows.Ink.IncrementalLassoHitTester> may unselect some strokes.</span></span>  
  
 <span data-ttu-id="44d73-111"><xref:System.Windows.Ink.IncrementalLassoHitTester>発生させる、<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>イベントで、ユーザーは、描画中に応答するカスタム コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="44d73-111">The <xref:System.Windows.Ink.IncrementalLassoHitTester> raises the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, which enables your custom control to respond while the user is drawing the lasso.</span></span>  <span data-ttu-id="44d73-112">たとえば、ユーザーを選択し、それらの選択を解除すると、ストロークの外観を変更できます。</span><span class="sxs-lookup"><span data-stu-id="44d73-112">For example, you can change the appearance of strokes as the user selects and unselects them.</span></span>  
  
## <a name="managing-the-ink-mode"></a><span data-ttu-id="44d73-113">インク モードの管理</span><span class="sxs-lookup"><span data-stu-id="44d73-113">Managing the Ink Mode</span></span>  
 <span data-ttu-id="44d73-114">なげなわがコントロール上のインクが異なって表示される場合、ユーザーに便利です。</span><span class="sxs-lookup"><span data-stu-id="44d73-114">It is helpful to the user if the lasso appears differently than the ink on your control.</span></span> <span data-ttu-id="44d73-115">これを実現するには、カスタム コントロールする必要がありますの追跡、ユーザーが作成またはインクを選択するかどうか。</span><span class="sxs-lookup"><span data-stu-id="44d73-115">To accomplish this, your custom control must keep track of whether the user is writing or selecting ink.</span></span> <span data-ttu-id="44d73-116">これを行う最も簡単な方法が 2 つの値を持つ列挙型を宣言するには: インクと、ユーザーがインクを選択することを示す 1 つに、ユーザーを作成することを示す 1 つ。</span><span class="sxs-lookup"><span data-stu-id="44d73-116">The easiest way to do this is to declare an enumeration with two values: one to indicate that the user is writing ink and one to indicate that the user is selecting ink.</span></span>  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 <span data-ttu-id="44d73-117">次に、2 つ追加<xref:System.Windows.Ink.DrawingAttributes>クラス: ユーザーがインクは、ユーザーがインクを選択したときに使用する 1 つを記述するときに使用する 1 つ。</span><span class="sxs-lookup"><span data-stu-id="44d73-117">Next, add two <xref:System.Windows.Ink.DrawingAttributes> to the class: one to use when the user writes ink, one to use when the user selects ink.</span></span>  <span data-ttu-id="44d73-118">コンス トラクターの初期化、<xref:System.Windows.Ink.DrawingAttributes>両方添付して<xref:System.Windows.Ink.DrawingAttributes.AttributeChanged>同じイベント ハンドラーにイベント。</span><span class="sxs-lookup"><span data-stu-id="44d73-118">In the constructor, initialize the <xref:System.Windows.Ink.DrawingAttributes> and attach both <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> events to the same event handler.</span></span> <span data-ttu-id="44d73-119">設定し、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A>のプロパティ、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>インク<xref:System.Windows.Ink.DrawingAttributes>します。</span><span class="sxs-lookup"><span data-stu-id="44d73-119">Then set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the ink <xref:System.Windows.Ink.DrawingAttributes>.</span></span>  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 <span data-ttu-id="44d73-120">選択モードを公開するプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="44d73-120">Add a property that exposes the selection mode.</span></span> <span data-ttu-id="44d73-121">選択モードを変更するときは、設定、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A>のプロパティ、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>を適切な<xref:System.Windows.Ink.DrawingAttributes>オブジェクトを再アタッチし、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>プロパティを<xref:System.Windows.Controls.InkPresenter>します。</span><span class="sxs-lookup"><span data-stu-id="44d73-121">When the user changes the selection mode, set the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> property of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the appropriate <xref:System.Windows.Ink.DrawingAttributes> object and then reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> Property to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 <span data-ttu-id="44d73-122">公開、<xref:System.Windows.Ink.DrawingAttributes>としてプロパティのアプリケーションは、インク ストロークと選択範囲のストロークの外観を判断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="44d73-122">Expose the <xref:System.Windows.Ink.DrawingAttributes> as properties so applications can determine the appearance of the ink strokes and selection strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <span data-ttu-id="44d73-123">場合のプロパティを<xref:System.Windows.Ink.DrawingAttributes>オブジェクトの変更を<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>に再アタッチする必要があります、<xref:System.Windows.Controls.InkPresenter>します。</span><span class="sxs-lookup"><span data-stu-id="44d73-123">When a property of a <xref:System.Windows.Ink.DrawingAttributes> object changes, the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> must be reattached to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="44d73-124">イベント ハンドラーで、<xref:System.Windows.Ink.DrawingAttributes.AttributeChanged>イベントを再アタッチ、<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>を<xref:System.Windows.Controls.InkPresenter>します。</span><span class="sxs-lookup"><span data-stu-id="44d73-124">In the event handler for the <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> event, reattach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a><span data-ttu-id="44d73-125">IncrementalLassoHitTester を使用します。</span><span class="sxs-lookup"><span data-stu-id="44d73-125">Using the IncrementalLassoHitTester</span></span>  
 <span data-ttu-id="44d73-126">作成し、初期化、<xref:System.Windows.Ink.StrokeCollection>選択されたストロークを格納しています。</span><span class="sxs-lookup"><span data-stu-id="44d73-126">Create and initialize a <xref:System.Windows.Ink.StrokeCollection> that contains the selected strokes.</span></span>  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 <span data-ttu-id="44d73-127">ユーザーがストロークを描画するために起動するときにインクまたはなげなわ選択したストローク選択解除します。</span><span class="sxs-lookup"><span data-stu-id="44d73-127">When the user starts to draw a stroke, either ink or the lasso, unselect any selected strokes.</span></span> <span data-ttu-id="44d73-128">次に、なげなわ選択を描画して、ユーザー場合に作成、<xref:System.Windows.Ink.IncrementalLassoHitTester>呼び出して<xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>、購読、<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>イベント、および呼び出し<xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>。</span><span class="sxs-lookup"><span data-stu-id="44d73-128">Then, if the user is drawing a lasso, create an <xref:System.Windows.Ink.IncrementalLassoHitTester> by calling <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, subscribe to the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event, and call <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>.</span></span> <span data-ttu-id="44d73-129">このコードは、別のメソッドとから呼び出される、<xref:System.Windows.UIElement.OnStylusDown%2A>と<xref:System.Windows.UIElement.OnMouseDown%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="44d73-129">This code can be a separate method and called from the <xref:System.Windows.UIElement.OnStylusDown%2A> and <xref:System.Windows.UIElement.OnMouseDown%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 <span data-ttu-id="44d73-130">スタイラス ポイントを追加、<xref:System.Windows.Ink.IncrementalLassoHitTester>中に、ユーザーになげなわを描画します。</span><span class="sxs-lookup"><span data-stu-id="44d73-130">Add the stylus points to the <xref:System.Windows.Ink.IncrementalLassoHitTester> while the user draws the lasso.</span></span>  <span data-ttu-id="44d73-131">次のメソッドを呼び出し、 <xref:System.Windows.UIElement.OnStylusMove%2A>、 <xref:System.Windows.UIElement.OnStylusUp%2A>、 <xref:System.Windows.UIElement.OnMouseMove%2A>、および<xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="44d73-131">Call the following method from the <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, and <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> methods.</span></span>  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 <span data-ttu-id="44d73-132">処理、<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType>イベント、ユーザーを選択し、ストロークの選択を解除するときに応答します。</span><span class="sxs-lookup"><span data-stu-id="44d73-132">Handle the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> event to respond when the user selects and unselects strokes.</span></span>  <span data-ttu-id="44d73-133"><xref:System.Windows.Ink.LassoSelectionChangedEventArgs>クラスには、<xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A>と<xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A>ストロークを取得するプロパティが選択され、オフの場合、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="44d73-133">The <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> class has the <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> and <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> properties that get the strokes that were selected and unselected, respectively.</span></span>  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 <span data-ttu-id="44d73-134">ユーザーは、描画が完了したら、サブスクリプションの解除、<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>イベントと呼び出し<xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>します。</span><span class="sxs-lookup"><span data-stu-id="44d73-134">When the user finishes drawing the lasso, unsubscribe from the <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> event and call <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.</span></span>  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a><span data-ttu-id="44d73-135">すべてまとめて配置することです。</span><span class="sxs-lookup"><span data-stu-id="44d73-135">Putting it All Together.</span></span>  
 <span data-ttu-id="44d73-136">次の例では、ユーザーがなげなわを使用してインクを選択できるカスタム コントロールです。</span><span class="sxs-lookup"><span data-stu-id="44d73-136">The following example is a custom control that enables a user to select ink with a lasso.</span></span>  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="44d73-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="44d73-137">See also</span></span>

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [<span data-ttu-id="44d73-138">インク入力コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="44d73-138">Creating an Ink Input Control</span></span>](creating-an-ink-input-control.md)
