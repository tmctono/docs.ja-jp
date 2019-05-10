---
title: 'チュートリアル: ユーザー コントロールでのドラッグ アンド ドロップの有効化'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 7fbda381b6c60398ef89e11416cafedcf19eec65
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605666"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="6d291-102">チュートリアル: ユーザー コントロールでのドラッグ アンド ドロップの有効化</span><span class="sxs-lookup"><span data-stu-id="6d291-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="6d291-103">このチュートリアルでのドラッグ アンド ドロップのデータ転送に含めることができるカスタム ユーザー コントロールを作成する方法について説明[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6d291-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="6d291-104">このチュートリアルでは、カスタムの WPF を作成します<xref:System.Windows.Controls.UserControl>を表す円を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d291-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="6d291-105">ドラッグ アンド ドロップを介したデータ転送を有効にするコントロールの機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="6d291-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="6d291-106">たとえば、別に 1 つの円コントロールからドラッグすると、塗りつぶしの色のデータはターゲットにでコピーに円のソースから。</span><span class="sxs-lookup"><span data-stu-id="6d291-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="6d291-107">円のコントロールからドラッグした場合、 <xref:System.Windows.Controls.TextBox>、塗りつぶしの色の文字列形式にコピー、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="6d291-108">2 つのパネル コントロールを含む小さなアプリケーションを作成することも、および<xref:System.Windows.Controls.TextBox>ドラッグ アンド ドロップ機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="6d291-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="6d291-109">パネルは、円を 1 つのパネルの子のコレクションから、もう一方にコピーまたは移動することが可能にする、ドロップされた円のデータを処理できるようにするコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="6d291-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="6d291-110">このチュートリアルでは、次の作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d291-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="6d291-111">カスタム ユーザー コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d291-111">Create a custom user control.</span></span>

- <span data-ttu-id="6d291-112">ドラッグ元にユーザー コントロールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6d291-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="6d291-113">ドロップ ターゲットにするユーザー コントロールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6d291-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="6d291-114">ユーザー コントロールから削除されるデータを受信するパネルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6d291-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d291-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6d291-115">Prerequisites</span></span>

<span data-ttu-id="6d291-116">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="6d291-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="6d291-117">アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d291-117">Create the Application Project</span></span>
 <span data-ttu-id="6d291-118">このセクションでは、2 つのパネルでのメイン ページを含むアプリケーション インフラストラクチャを作成します、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="6d291-119">Visual Basic または Visual c# のという名前で新しい WPF アプリケーション プロジェクトを作成する`DragDropExample`します。</span><span class="sxs-lookup"><span data-stu-id="6d291-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="6d291-120">詳細については、「[チュートリアル:初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6d291-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="6d291-121">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="6d291-122">開始タグと終了の間で、次のマークアップを追加<xref:System.Windows.Controls.Grid>タグ。</span><span class="sxs-lookup"><span data-stu-id="6d291-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="6d291-123">このマークアップは、テスト アプリケーションのユーザー インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d291-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="6d291-124">プロジェクトに新しいユーザー コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="6d291-125">このセクションでは、プロジェクトに新しいユーザー コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="6d291-126">[プロジェクト] メニューで、次のように選択します。**ユーザー コントロールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="6d291-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="6d291-127">**新しい項目の追加** ダイアログ ボックスで、名を変更して`Circle.xaml`、 をクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="6d291-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="6d291-128">Circle.xaml とその分離コードは、プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6d291-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="6d291-129">Circle.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="6d291-130">このファイルは、ユーザー コントロールのユーザー インターフェイス要素が格納されます。</span><span class="sxs-lookup"><span data-stu-id="6d291-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="6d291-131">ルートに次のマークアップを追加<xref:System.Windows.Controls.Grid>シンプルなユーザー コントロールがその UI として、青色の円を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d291-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="6d291-132">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="6d291-133">C# では、コピー コンス トラクターを作成する既定のコンス トラクターの後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-133">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="6d291-134">Visual basic では、既定のコンス トラクターとコピー コンス トラクターの両方を作成するには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-134">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>

     <span data-ttu-id="6d291-135">コピーするユーザー コントロールを許可するためには、分離コード ファイルのコピー コンス トラクター メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="6d291-136">簡略化された円ユーザー コントロールではのみをコピーする、塗りつぶしとのサイズ、ユーザー コントロールの。</span><span class="sxs-lookup"><span data-stu-id="6d291-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="6d291-137">メイン ウィンドウに、ユーザー コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="6d291-138">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="6d291-139">開始する次の XAML を追加<xref:System.Windows.Window>タグが現在のアプリケーションに XML 名前空間参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d291-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="6d291-140">最初の<xref:System.Windows.Controls.StackPanel>、最初のパネルで、円のユーザー コントロールの 2 つのインスタンスを作成する次の XAML を追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="6d291-141">パネルの完全な XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6d291-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="6d291-142">ユーザー コントロールでドラッグ ソースのイベントを実装します。</span><span class="sxs-lookup"><span data-stu-id="6d291-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="6d291-143">このセクションでをオーバーライドして、<xref:System.Windows.UIElement.OnMouseMove%2A>メソッドと、ドラッグ アンド ドロップ操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="6d291-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="6d291-144">ドラッグを開始する場合 (マウス ボタンが押され、マウスを移動) に転送されるデータをパッケージ化は、<xref:System.Windows.DataObject>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="6d291-145">ここでは、円コントロールが; 3 つのデータ項目をパッケージします。塗りつぶしの色、高さの二重表現自体のコピーの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="6d291-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="6d291-146">ドラッグ アンド ドロップ操作を開始するには</span><span class="sxs-lookup"><span data-stu-id="6d291-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="6d291-147">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="6d291-148">次の追加<xref:System.Windows.UIElement.OnMouseMove%2A>のクラス処理を提供するオーバーライド、<xref:System.Windows.UIElement.MouseMove>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="6d291-149">これは、<xref:System.Windows.UIElement.OnMouseMove%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-150">マウスが移動中に、マウスの左ボタンが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d291-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="6d291-151">パッケージにデータを円、<xref:System.Windows.DataObject>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="6d291-152">この場合、円コントロール パッケージを 3 つのデータ項目。塗りつぶしの色、高さの二重表現自体のコピーの文字列表現。</span><span class="sxs-lookup"><span data-stu-id="6d291-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="6d291-153">静的な呼び出し<xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType>ドラッグ アンド ドロップ操作を開始するメソッド。</span><span class="sxs-lookup"><span data-stu-id="6d291-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="6d291-154">次の 3 つのパラメーターを渡す、<xref:System.Windows.DragDrop.DoDragDrop%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="6d291-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="6d291-155">`dragSource` – このコントロールへの参照。</span><span class="sxs-lookup"><span data-stu-id="6d291-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="6d291-156">`data` –<xref:System.Windows.DataObject>前のコードで作成します。</span><span class="sxs-lookup"><span data-stu-id="6d291-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="6d291-157">`allowedEffects` – の許可されているドラッグ アンド ドロップ操作<xref:System.Windows.DragDropEffects.Copy>または<xref:System.Windows.DragDropEffects.Move>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="6d291-158">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="6d291-159">円のコントロールのいずれかをクリックし、パネル、他の円をドラッグし、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="6d291-160">ドラッグしたとき、<xref:System.Windows.Controls.TextBox>カーソルが移動を示すために変わります。</span><span class="sxs-lookup"><span data-stu-id="6d291-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="6d291-161">経由で円をドラッグするときに、 <xref:System.Windows.Controls.TextBox>、キーを押して、 **Ctrl**キー。</span><span class="sxs-lookup"><span data-stu-id="6d291-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="6d291-162">コピーを示すために、カーソルの変更に注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d291-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="6d291-163">ドラッグ アンド ドロップ上の円、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="6d291-164">円の塗りつぶしの色の文字列表現を追加、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="6d291-165">![円の塗りつぶしの色の文字列表現](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="6d291-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="6d291-166">既定では、カーソルは、どのようなデータを削除する効果を持つが示すにドラッグ アンド ドロップ操作中に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6d291-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="6d291-167">処理することにより、ユーザーにフィードバックをカスタマイズすることができます、<xref:System.Windows.UIElement.GiveFeedback>イベントと異なるカーソルを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d291-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="6d291-168">ユーザーにフィードバックします。</span><span class="sxs-lookup"><span data-stu-id="6d291-168">Give feedback to the user</span></span>

1. <span data-ttu-id="6d291-169">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="6d291-170">次の追加<xref:System.Windows.UIElement.OnGiveFeedback%2A>のクラス処理を提供するオーバーライド、<xref:System.Windows.UIElement.GiveFeedback>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="6d291-171">これは、<xref:System.Windows.UIElement.OnGiveFeedback%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-172">チェック、<xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>でドロップ先の設定されている値<xref:System.Windows.UIElement.DragOver>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="6d291-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="6d291-173">基づくカスタム カーソル設定、<xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>値。</span><span class="sxs-lookup"><span data-stu-id="6d291-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="6d291-174">カーソルは、どのようなデータを削除する効果は必要があります。 詳細については、ユーザーに視覚的なフィードバックを提供するものです。</span><span class="sxs-lookup"><span data-stu-id="6d291-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="6d291-175">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="6d291-176">円の 1 つを管理パネル、他の円の上をドラッグし、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="6d291-177">カーソルがで指定したカスタム カーソル、<xref:System.Windows.UIElement.OnGiveFeedback%2A>をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6d291-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="6d291-178">![カスタム カーソルによるドラッグ アンド ドロップ](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="6d291-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="6d291-179">テキスト選択`green`から、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="6d291-180">ドラッグ、`green`円コントロールにテキスト。</span><span class="sxs-lookup"><span data-stu-id="6d291-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="6d291-181">ドラッグ アンド ドロップ操作の効果を示すために既定のカーソルが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d291-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="6d291-182">フィードバックのカーソルは、ドラッグ ソースが常に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6d291-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="6d291-183">ユーザー コントロールのドロップ先のイベントを実装します。</span><span class="sxs-lookup"><span data-stu-id="6d291-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="6d291-184">このセクションでは、ユーザー コントロールがドロップ ターゲットでは、上書き、ユーザーを有効にするメソッドは、ドロップ先を制御し、その上にドロップしたデータを処理であるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d291-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="6d291-185">ドロップ ターゲットにするユーザー コントロールを有効にするには</span><span class="sxs-lookup"><span data-stu-id="6d291-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="6d291-186">Circle.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="6d291-187">オープンで<xref:System.Windows.Controls.UserControl>タグを追加、<xref:System.Windows.UIElement.AllowDrop%2A>プロパティに設定し、`true`します。</span><span class="sxs-lookup"><span data-stu-id="6d291-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="6d291-188"><xref:System.Windows.UIElement.OnDrop%2A>メソッドが呼び出されます、<xref:System.Windows.UIElement.AllowDrop%2A>プロパティに設定されて`true`円ユーザー コントロールでドラッグ ソースからデータが削除されるとします。</span><span class="sxs-lookup"><span data-stu-id="6d291-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="6d291-189">このメソッドでは、ドロップされたデータを処理し、データを円に適用します。</span><span class="sxs-lookup"><span data-stu-id="6d291-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="6d291-190">削除されたデータを処理する</span><span class="sxs-lookup"><span data-stu-id="6d291-190">To process the dropped data</span></span>

1. <span data-ttu-id="6d291-191">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="6d291-192">次の追加<xref:System.Windows.UIElement.OnDrop%2A>のクラス処理を提供するオーバーライド、<xref:System.Windows.UIElement.Drop>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="6d291-193">これは、<xref:System.Windows.UIElement.OnDrop%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-194">使用して、<xref:System.Windows.DataObject.GetDataPresent%2A>ドラッグ中のデータに文字列オブジェクトが含まれているかどうかをチェックするメソッド。</span><span class="sxs-lookup"><span data-stu-id="6d291-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="6d291-195">使用して、<xref:System.Windows.DataObject.GetData%2A>メソッドが存在する場合は、文字列データを抽出します。</span><span class="sxs-lookup"><span data-stu-id="6d291-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="6d291-196">使用して、<xref:System.Windows.Media.BrushConverter>を文字列に変換しようとする、<xref:System.Windows.Media.Brush>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="6d291-197">変換が成功した場合は、適用するブラシ、<xref:System.Windows.Shapes.Shape.Fill%2A>の<xref:System.Windows.Shapes.Ellipse>円コントロールの UI を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d291-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="6d291-198">マーク、<xref:System.Windows.UIElement.Drop>イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="6d291-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="6d291-199">このイベントを受信する他の要素が円のユーザー コントロールに処理を認識できるように処理済みとしてドロップ イベントをマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d291-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="6d291-200">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="6d291-201">テキスト選択`green`で、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="6d291-202">円のコントロールにテキストをドラッグし、ドロップします。</span><span class="sxs-lookup"><span data-stu-id="6d291-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="6d291-203">円は、青から緑に変更します。</span><span class="sxs-lookup"><span data-stu-id="6d291-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="6d291-204">![文字列、ブラシを変換](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="6d291-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="6d291-205">テキスト入力`green`で、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="6d291-206">テキスト選択`gre`で、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="6d291-207">円のコントロールにドラッグし、ドロップします。</span><span class="sxs-lookup"><span data-stu-id="6d291-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="6d291-208">カーソルの変化を示すために、円の色が変更されませんが、ドロップは許可されて`gre`は有効な色ではありません。</span><span class="sxs-lookup"><span data-stu-id="6d291-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="6d291-209">緑色の円のコントロールをドラッグし、青い円コントロールにドロップします。</span><span class="sxs-lookup"><span data-stu-id="6d291-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="6d291-210">円は、青から緑に変更します。</span><span class="sxs-lookup"><span data-stu-id="6d291-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="6d291-211">カーソルが表示されるかどうかによって異なりますが、<xref:System.Windows.Controls.TextBox>円はドラッグ元であるか。</span><span class="sxs-lookup"><span data-stu-id="6d291-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="6d291-212">設定、<xref:System.Windows.UIElement.AllowDrop%2A>プロパティを`true`要素になるドロップ ターゲットを有効にするために必要なは、ドロップしたデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="6d291-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="6d291-213">ただし、優れたユーザー エクスペリエンスを提供する必要がありますも処理する、 <xref:System.Windows.UIElement.DragEnter>、 <xref:System.Windows.UIElement.DragLeave>、および<xref:System.Windows.UIElement.DragOver>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="6d291-214">これらのイベントでは、チェックを実行し、データが削除される前に、追加のフィードバックをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="6d291-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="6d291-215">データが円のユーザー コントロールの上にドラッグされるときに、コントロールはドラッグされているデータを処理するかどうか、ドラッグ元で通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d291-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="6d291-216">コントロールにデータを処理する方法を把握していない場合、削除を拒否する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d291-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="6d291-217">処理するのには、<xref:System.Windows.UIElement.DragOver>イベントとセット、<xref:System.Windows.DragEventArgs.Effects%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6d291-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="6d291-218">データの削除が許可されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="6d291-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="6d291-219">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="6d291-220">次の追加<xref:System.Windows.UIElement.OnDragOver%2A>のクラス処理を提供するオーバーライド、<xref:System.Windows.UIElement.DragOver>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="6d291-221">これは、<xref:System.Windows.UIElement.OnDragOver%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-222"><xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.None> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6d291-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="6d291-223">実行される同じチェックが実行、<xref:System.Windows.UIElement.OnDrop%2A>円ユーザー コントロールがドラッグしたデータを処理できるかどうかを判断するメソッド。</span><span class="sxs-lookup"><span data-stu-id="6d291-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="6d291-224">ユーザー コントロールには、データを処理できますが、設定、<xref:System.Windows.DragEventArgs.Effects%2A>プロパティを<xref:System.Windows.DragDropEffects.Copy>または<xref:System.Windows.DragDropEffects.Move>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="6d291-225">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="6d291-226">テキスト選択`gre`で、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="6d291-227">円のコントロールにテキストをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6d291-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="6d291-228">カーソルが今すぐに変化を示すため、ドロップは許可されません`gre`は有効な色ではありません。</span><span class="sxs-lookup"><span data-stu-id="6d291-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="6d291-229">ドロップ操作のプレビューを適用することで、ユーザー エクスペリエンスをさらに強化できます。</span><span class="sxs-lookup"><span data-stu-id="6d291-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="6d291-230">オーバーライド円ユーザー コントロールの場合、<xref:System.Windows.UIElement.OnDragEnter%2A>と<xref:System.Windows.UIElement.OnDragLeave%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="6d291-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="6d291-231">データが、コントロールの現在の背景上にドラッグされるときに<xref:System.Windows.Shapes.Shape.Fill%2A>プレース ホルダー変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6d291-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="6d291-232">文字列は、ブラシに変換されに適用される、<xref:System.Windows.Shapes.Ellipse>円を提供する UI。</span><span class="sxs-lookup"><span data-stu-id="6d291-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="6d291-233">データが元、ドロップされることがなく円からドラッグした場合<xref:System.Windows.Shapes.Shape.Fill%2A>値は円に再適用されます。</span><span class="sxs-lookup"><span data-stu-id="6d291-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="6d291-234">ドラッグ アンド ドロップ操作の効果をプレビューするには</span><span class="sxs-lookup"><span data-stu-id="6d291-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="6d291-235">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="6d291-236">円クラスで宣言プライベート<xref:System.Windows.Media.Brush>という名前の変数`_previousFill`し初期化`null`します。</span><span class="sxs-lookup"><span data-stu-id="6d291-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="6d291-237">次の追加<xref:System.Windows.UIElement.OnDragEnter%2A>のクラス処理を提供するオーバーライド、<xref:System.Windows.UIElement.DragEnter>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="6d291-238">これは、<xref:System.Windows.UIElement.OnDragEnter%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-239">保存、<xref:System.Windows.Shapes.Shape.Fill%2A>のプロパティ、<xref:System.Windows.Shapes.Ellipse>で、`_previousFill`変数。</span><span class="sxs-lookup"><span data-stu-id="6d291-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="6d291-240">実行される同じチェックが実行、<xref:System.Windows.UIElement.OnDrop%2A>にデータを変換できるかどうかを判断するメソッド、<xref:System.Windows.Media.Brush>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="6d291-241">有効なデータが変換される場合<xref:System.Windows.Media.Brush>、それを適用、<xref:System.Windows.Shapes.Shape.Fill%2A>の<xref:System.Windows.Shapes.Ellipse>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="6d291-242">次の追加<xref:System.Windows.UIElement.OnDragLeave%2A>のクラス処理を提供するオーバーライド、<xref:System.Windows.UIElement.DragLeave>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="6d291-243">これは、<xref:System.Windows.UIElement.OnDragLeave%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-244">適用される、<xref:System.Windows.Media.Brush>に保存されている、`_previousFill`変数を<xref:System.Windows.Shapes.Shape.Fill%2A>の<xref:System.Windows.Shapes.Ellipse>円ユーザー コントロールの UI を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d291-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="6d291-245">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="6d291-246">テキスト選択`green`で、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="6d291-247">円のコントロールを削除しないテキストをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6d291-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="6d291-248">円は、青から緑に変更します。</span><span class="sxs-lookup"><span data-stu-id="6d291-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="6d291-249">![ドラッグの効果のプレビュー&#45;と&#45;ドロップ操作](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="6d291-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="6d291-250">円コントロールからテキストをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="6d291-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="6d291-251">円を青に緑色のバックアップから変更します。</span><span class="sxs-lookup"><span data-stu-id="6d291-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="6d291-252">ドロップしたデータを受信するパネルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6d291-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="6d291-253">このセクションでは、円のドラッグしたデータのドロップ ターゲットとして機能する円のユーザー コントロールをホストするパネルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6d291-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="6d291-254">円を別の 1 つのパネルに移動するかを押しながら Circle コントロールのコピーを作成することができるコードを実装する、 **Ctrl**ドラッグ アンド ドロップ、円の中にキー。</span><span class="sxs-lookup"><span data-stu-id="6d291-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="6d291-255">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="6d291-256">それぞれで、次の XAML に示すように、<xref:System.Windows.Controls.StackPanel>のハンドラーの追加、コントロール、<xref:System.Windows.UIElement.DragOver>と<xref:System.Windows.UIElement.Drop>イベント。</span><span class="sxs-lookup"><span data-stu-id="6d291-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="6d291-257">名前、<xref:System.Windows.UIElement.DragOver>イベント ハンドラー、 `panel_DragOver`、し、名前、<xref:System.Windows.UIElement.Drop>イベント ハンドラー、`panel_Drop`します。</span><span class="sxs-lookup"><span data-stu-id="6d291-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="6d291-258">MainWindows.xaml.cs または MainWindow.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d291-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="6d291-259">次のコードを追加、<xref:System.Windows.UIElement.DragOver>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="6d291-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="6d291-260">これは、<xref:System.Windows.UIElement.DragOver>イベント ハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-261">パッケージ化された「オブジェクト」のデータにはドラッグしたデータが含まれているを確認します、<xref:System.Windows.DataObject>円のユーザー コントロールへの呼び出しで渡されると<xref:System.Windows.DragDrop.DoDragDrop%2A>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="6d291-262">「オブジェクト」のデータが存在する場合、チェックするかどうか、 **Ctrl**キーが押されました。</span><span class="sxs-lookup"><span data-stu-id="6d291-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="6d291-263">場合、 **Ctrl**キーを押す、セット、<xref:System.Windows.DragEventArgs.Effects%2A>プロパティを<xref:System.Windows.DragDropEffects.Copy>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="6d291-264">それ以外の場合、設定、<xref:System.Windows.DragEventArgs.Effects%2A>プロパティを<xref:System.Windows.DragDropEffects.Move>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="6d291-265">次のコードを追加、<xref:System.Windows.UIElement.Drop>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="6d291-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="6d291-266">これは、<xref:System.Windows.UIElement.Drop>イベント ハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="6d291-267">チェックするかどうか、<xref:System.Windows.UIElement.Drop>イベントが既に処理されました。</span><span class="sxs-lookup"><span data-stu-id="6d291-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="6d291-268">別の円が削除された場合 Circle をたとえば、ハンドル、<xref:System.Windows.UIElement.Drop>イベント、たくも処理する円形を格納しているパネル。</span><span class="sxs-lookup"><span data-stu-id="6d291-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="6d291-269">場合、<xref:System.Windows.UIElement.Drop>イベントが処理されない、チェックするかどうか、 **Ctrl**キーが押されました。</span><span class="sxs-lookup"><span data-stu-id="6d291-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="6d291-270">場合、 **Ctrl**キーが押されたときに、<xref:System.Windows.UIElement.Drop>が発生し、制御が円のコピーに追加、<xref:System.Windows.Controls.Panel.Children%2A>のコレクション、<xref:System.Windows.Controls.StackPanel>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="6d291-271">場合、 **Ctrl**から円を移動キーが押されていない、<xref:System.Windows.Controls.Panel.Children%2A>をその親パネルのコレクション、<xref:System.Windows.Controls.Panel.Children%2A>上にドロップされたパネルのコレクション。</span><span class="sxs-lookup"><span data-stu-id="6d291-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="6d291-272">セット、<xref:System.Windows.DragEventArgs.Effects%2A>プロパティに通知する、<xref:System.Windows.DragDrop.DoDragDrop%2A>メソッドを移動またはコピー操作が実行されたかどうか。</span><span class="sxs-lookup"><span data-stu-id="6d291-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="6d291-273">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6d291-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="6d291-274">テキスト選択`green`から、<xref:System.Windows.Controls.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="6d291-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="6d291-275">円のコントロールの上のテキストをドラッグし、ドロップします。</span><span class="sxs-lookup"><span data-stu-id="6d291-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="6d291-276">右側のパネルの左側のパネルから円コントロールをドラッグし、ドロップします。</span><span class="sxs-lookup"><span data-stu-id="6d291-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="6d291-277">円はから削除、<xref:System.Windows.Controls.Panel.Children%2A>左側のパネルのコレクションと、右側のパネルの子のコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6d291-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="6d291-278">その他のパネル内にあるパネルから円コントロールをドラッグし、キーを押しながらドロップ、 **Ctrl**キー。</span><span class="sxs-lookup"><span data-stu-id="6d291-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="6d291-279">円がコピーされ、コピーに追加されます、<xref:System.Windows.Controls.Panel.Children%2A>受信側のパネルのコレクション。</span><span class="sxs-lookup"><span data-stu-id="6d291-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="6d291-280">![CTRL キーを押しながら Circle をドラッグ](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="6d291-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="6d291-281">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d291-281">See also</span></span>

- [<span data-ttu-id="6d291-282">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="6d291-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)