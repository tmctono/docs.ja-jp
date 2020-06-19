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
ms.openlocfilehash: 172e49c2c255db4d24d2180f919b1305326b5e82
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991809"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="30475-102">チュートリアル: ユーザー コントロールでのドラッグ アンド ドロップの有効化</span><span class="sxs-lookup"><span data-stu-id="30475-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="30475-103">このチュートリアルでは、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] でドラッグ アンド ドロップのデータ転送 (受信) に参加できるカスタム ユーザー コントロールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30475-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="30475-104">このチュートリアルでは、円の図形を表すカスタムの WPF <xref:System.Windows.Controls.UserControl> を作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="30475-105">また、ドラッグ アンド ドロップによるデータ転送を有効にする機能をコントロールに実装します。</span><span class="sxs-lookup"><span data-stu-id="30475-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="30475-106">たとえば、ある円コントロールから別の円コントロールにドラッグすると、塗りつぶし色のデータがソースの円からターゲットの円にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="30475-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="30475-107">円コントロールから <xref:System.Windows.Controls.TextBox> にドラッグすると、塗りつぶし色の文字列表現が <xref:System.Windows.Controls.TextBox> にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="30475-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="30475-108">さらに、2 つのパネル コントロールと <xref:System.Windows.Controls.TextBox> を含む小さなアプリケーションを作成して、ドラッグ アンド ドロップ機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="30475-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="30475-109">ドロップされた円データをパネルで処理できるようにするコードを作成します。これにより、ユーザーはあるパネルの子コレクションから別のパネルに円を移動またはコピーできるようになります。</span><span class="sxs-lookup"><span data-stu-id="30475-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="30475-110">このチュートリアルでは、次の作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="30475-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="30475-111">カスタム ユーザー コントロールを作成する。</span><span class="sxs-lookup"><span data-stu-id="30475-111">Create a custom user control.</span></span>

- <span data-ttu-id="30475-112">ユーザー コントロールをドラッグ ソースとして有効にする。</span><span class="sxs-lookup"><span data-stu-id="30475-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="30475-113">ユーザー コントロールをドラッグ ターゲットとして有効にする。</span><span class="sxs-lookup"><span data-stu-id="30475-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="30475-114">ユーザー コントロールからドロップされたデータをパネルで受信できるようにする。</span><span class="sxs-lookup"><span data-stu-id="30475-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30475-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="30475-115">Prerequisites</span></span>

<span data-ttu-id="30475-116">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="30475-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="30475-117">アプリケーション プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="30475-117">Create the Application Project</span></span>
 <span data-ttu-id="30475-118">このセクションでは、2 つのパネルと <xref:System.Windows.Controls.TextBox> で構成されるメイン ページを含むアプリケーション インフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="30475-119">Visual Basic または Visual C# で、`DragDropExample` という名前の WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="30475-120">詳細については、「[チュートリアル:初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30475-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="30475-121">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="30475-122"><xref:System.Windows.Controls.Grid> の開始タグと終了タグの間に次のマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="30475-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="30475-123">このマークアップは、テスト アプリケーションのユーザー インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="30475-124">新しいユーザー コントロールをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="30475-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="30475-125">このセクションでは、新しいユーザー コントロールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="30475-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="30475-126">[プロジェクト] メニューで、 **[ユーザー コントロールの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30475-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="30475-127">**[新しい項目の追加]** ダイアログ ボックスで、名前を `Circle.xaml` に変更し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30475-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="30475-128">Circle.xaml とその分離コードがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="30475-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="30475-129">Circle.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="30475-130">このファイルには、ユーザー コントロールのユーザー インターフェイス要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="30475-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="30475-131">次のマークアップをルート <xref:System.Windows.Controls.Grid> に追加し、UI として青色の円を含む単純なユーザー コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="30475-132">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="30475-133">C# で、パラメーターなしのコンストラクターの後に次のコードを追加して、コピー コンストラクターを作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-133">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="30475-134">Visual Basic で、次のコードを追加して、パラメーターなしのコンストラクターとコピー コンストラクターの両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-134">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="30475-135">ユーザー コントロールをコピーできるようにするために、分離コード ファイルにコピー コンストラクター メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="30475-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="30475-136">単純な円形のユーザー コントロールの場合、ユーザー コントロールの塗りつぶしとサイズのみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="30475-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="30475-137">ユーザー コントロールをメイン ウィンドウに追加する</span><span class="sxs-lookup"><span data-stu-id="30475-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="30475-138">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="30475-139"><xref:System.Windows.Window> の開始タグで、次の XAML を追加して、現在のアプリケーションへの XML 名前空間参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="30475-140">最初の <xref:System.Windows.Controls.StackPanel>で、次の XAML を追加して、最初のパネルの円ユーザー コントロールの 2 つのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="30475-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="30475-141">パネルの完全な XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="30475-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="30475-142">ユーザー コントロールでドラッグ ソース イベントを実装する</span><span class="sxs-lookup"><span data-stu-id="30475-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="30475-143">このセクションでは、<xref:System.Windows.UIElement.OnMouseMove%2A> メソッドをオーバーライドして、ドラッグ アンド ドロップ操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="30475-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="30475-144">ドラッグが開始されたら (マウス ボタンが押されて、マウスが移動されたら)、<xref:System.Windows.DataObject>に転送されるデータをパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="30475-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="30475-145">この場合、円コントロールは、3 つのデータ項目 (塗りつぶし色の文字列表現、高さの double 表現、それ自体のコピー) をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="30475-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="30475-146">ドラッグ アンド ドロップ操作を開始する手順</span><span class="sxs-lookup"><span data-stu-id="30475-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="30475-147">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="30475-148">次の <xref:System.Windows.UIElement.OnMouseMove%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.MouseMove> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="30475-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="30475-149">この <xref:System.Windows.UIElement.OnMouseMove%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="30475-150">マウスの移動中にマウスの左ボタンが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30475-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="30475-151">円データを <xref:System.Windows.DataObject> にパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="30475-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="30475-152">この場合、円コントロールは、3 つのデータ項目 (塗りつぶし色の文字列表現、高さの double 表現、それ自体のコピー) をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="30475-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="30475-153">静的 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> メソッドを呼び出して、ドラッグ アンド ドロップ操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="30475-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="30475-154">次の 3 つのパラメーターを <xref:System.Windows.DragDrop.DoDragDrop%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="30475-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="30475-155">`dragSource` - このコントロールへの参照。</span><span class="sxs-lookup"><span data-stu-id="30475-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="30475-156">`data` - 前のコードで作成された <xref:System.Windows.DataObject>。</span><span class="sxs-lookup"><span data-stu-id="30475-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="30475-157">`allowedEffects` - 許可されたドラッグ アンド ドロップ操作。これは、<xref:System.Windows.DragDropEffects.Copy> または <xref:System.Windows.DragDropEffects.Move> です。</span><span class="sxs-lookup"><span data-stu-id="30475-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="30475-158">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="30475-159">いずれかの円コントロールをクリックしてパネル、もう一方の円、<xref:System.Windows.Controls.TextBox> にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="30475-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="30475-160"><xref:System.Windows.Controls.TextBox>にドラッグすると、カーソルが変化して移動を示すようになります。</span><span class="sxs-lookup"><span data-stu-id="30475-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="30475-161">円を <xref:System.Windows.Controls.TextBox>にドラッグしながら、**Ctrl** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="30475-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="30475-162">カーソルが変化してコピーを示すようになる方法にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="30475-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="30475-163">円を <xref:System.Windows.Controls.TextBox> にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="30475-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="30475-164">円の塗りつぶし色の文字列表現が <xref:System.Windows.Controls.TextBox> に追加されます。</span><span class="sxs-lookup"><span data-stu-id="30475-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="30475-165">![円の塗りつぶし色の文字列表現](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="30475-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="30475-166">既定では、カーソルは、ドラッグ アンド ドロップ操作中に変化して、データのドロップによる効果を示します。</span><span class="sxs-lookup"><span data-stu-id="30475-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="30475-167"><xref:System.Windows.UIElement.GiveFeedback> イベントを処理して、別のカーソルを設定することによって、ユーザーに表示するフィードバックをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="30475-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="30475-168">ユーザーにフィードバックを表示する</span><span class="sxs-lookup"><span data-stu-id="30475-168">Give feedback to the user</span></span>

1. <span data-ttu-id="30475-169">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="30475-170">次の <xref:System.Windows.UIElement.OnGiveFeedback%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.GiveFeedback> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="30475-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="30475-171">この <xref:System.Windows.UIElement.OnGiveFeedback%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="30475-172">ドロップ ターゲットの <xref:System.Windows.UIElement.DragOver> イベント ハンドラーで設定されている <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 値を確認します。</span><span class="sxs-lookup"><span data-stu-id="30475-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="30475-173"><xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 値に基づいてカスタム カーソルを設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="30475-174">カーソルは、データのドロップによる効果について視覚的フィードバックをユーザーに表示することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="30475-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="30475-175">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="30475-176">いずれかの円コントロールをパネル、もう一方の円、<xref:System.Windows.Controls.TextBox> にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="30475-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="30475-177">今度は、カーソルが、<xref:System.Windows.UIElement.OnGiveFeedback%2A> で指定したカスタム カーソルになることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="30475-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="30475-178">![カスタム カーソルによるドラッグ アンド ドロップ](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="30475-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="30475-179"><xref:System.Windows.Controls.TextBox> からテキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="30475-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="30475-180">テキスト `green` を円コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="30475-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="30475-181">既定のカーソルは、ドラッグ アンド ドロップ操作の効果を示すために表示されていることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="30475-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="30475-182">フィードバック カーソルは、常にドラッグ ソースによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="30475-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="30475-183">ユーザー コントロールにドロップ ターゲット イベントを実装する</span><span class="sxs-lookup"><span data-stu-id="30475-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="30475-184">このセクションでは、ユーザー コントロールがドロップ ターゲットであり、ユーザー コントロールをドロップ ターゲットとして有効にするメソッドをオーバーライドし、ドロップされたデータを処理することを指定します。</span><span class="sxs-lookup"><span data-stu-id="30475-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="30475-185">ユーザー コントロールをドロップ ターゲットとして有効にする手順</span><span class="sxs-lookup"><span data-stu-id="30475-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="30475-186">Circle.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="30475-187"><xref:System.Windows.Controls.UserControl> の開始タグで、<xref:System.Windows.UIElement.AllowDrop%2A> プロパティを追加し、それを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="30475-188"><xref:System.Windows.UIElement.AllowDrop%2A> が `true` に設定され、ドラッグ ソースのデータが円ユーザー コントロールにドロップされると、<xref:System.Windows.UIElement.OnDrop%2A> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="30475-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="30475-189">このメソッドでは、ドロップされたデータを処理し、データを円に適用します。</span><span class="sxs-lookup"><span data-stu-id="30475-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="30475-190">ドロップされたデータを処理する手順</span><span class="sxs-lookup"><span data-stu-id="30475-190">To process the dropped data</span></span>

1. <span data-ttu-id="30475-191">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="30475-192">次の <xref:System.Windows.UIElement.OnDrop%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.Drop> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="30475-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="30475-193">この <xref:System.Windows.UIElement.OnDrop%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="30475-194"><xref:System.Windows.DataObject.GetDataPresent%2A> メソッドを使用して、ドラッグされたデータに文字列オブジェクトが含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30475-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="30475-195">文字列データがある場合、<xref:System.Windows.DataObject.GetData%2A> メソッドを使用して、それを抽出します。</span><span class="sxs-lookup"><span data-stu-id="30475-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="30475-196"><xref:System.Windows.Media.BrushConverter> を使用して、文字列の <xref:System.Windows.Media.Brush> への変換を試みます。</span><span class="sxs-lookup"><span data-stu-id="30475-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="30475-197">変換が成功した場合、円コントロールの UI を表示する <xref:System.Windows.Shapes.Ellipse> の <xref:System.Windows.Shapes.Shape.Fill%2A> にブラシを適用します。</span><span class="sxs-lookup"><span data-stu-id="30475-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="30475-198"><xref:System.Windows.UIElement.Drop> イベントを処理済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="30475-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="30475-199">このイベントを受信する他の要素に、イベントが円ユーザー コントロールで処理されたことを認識させるために、ドロップ イベントを処理済みとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30475-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="30475-200">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="30475-201"><xref:System.Windows.Controls.TextBox> で、テキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="30475-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="30475-202">そのテキストを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="30475-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="30475-203">円が青色から緑色に変化します。</span><span class="sxs-lookup"><span data-stu-id="30475-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="30475-204">![文字列をブラシに変換する](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="30475-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="30475-205"><xref:System.Windows.Controls.TextBox> にテキスト `green` を入力します。</span><span class="sxs-lookup"><span data-stu-id="30475-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="30475-206"><xref:System.Windows.Controls.TextBox>で、テキスト `gre` を選択します。</span><span class="sxs-lookup"><span data-stu-id="30475-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="30475-207">それを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="30475-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="30475-208">カーソルが変化して、ドロップが許可されていることを示しますが、円の色は変化していないことに注目してください。これは、`gre` が有効な色ではないためです。</span><span class="sxs-lookup"><span data-stu-id="30475-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="30475-209">緑色の円コントロールをドラッグして青色の円コントロールにドロップします。</span><span class="sxs-lookup"><span data-stu-id="30475-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="30475-210">円が青色から緑色に変化します。</span><span class="sxs-lookup"><span data-stu-id="30475-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="30475-211">表示されるカーソルが、<xref:System.Windows.Controls.TextBox> または円のどちらがドラッグ ソースであるかによって異なることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="30475-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="30475-212">要素をドロップ ターゲットとして有効にするために必要な手順は、<xref:System.Windows.UIElement.AllowDrop%2A> プロパティを `true` に設定して、ドロップされたデータを処理することだけです。</span><span class="sxs-lookup"><span data-stu-id="30475-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="30475-213">しかし、より優れたユーザー エクスペリエンスを提供するには、<xref:System.Windows.UIElement.DragEnter>、<xref:System.Windows.UIElement.DragLeave>、<xref:System.Windows.UIElement.DragOver> の各イベントも処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30475-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="30475-214">これらのイベントでは、データがドロップされる前に、チェックを実行して、ユーザーに追加のフィードバックを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="30475-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="30475-215">データが円ユーザー コントロールにドラッグされると、コントロールは、ドラッグされているデータを処理できるかどうかをドラッグ ソースに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30475-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="30475-216">コントロールがデータの処理方法を認識していない場合、ドロップを拒否する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30475-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="30475-217">このためには、<xref:System.Windows.UIElement.DragOver> イベントを処理して、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="30475-218">データのドロップが許可されていることを確認する手順</span><span class="sxs-lookup"><span data-stu-id="30475-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="30475-219">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="30475-220">次の <xref:System.Windows.UIElement.OnDragOver%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.DragOver> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="30475-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="30475-221">この <xref:System.Windows.UIElement.OnDragOver%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="30475-222"><xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.None> に設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="30475-223"><xref:System.Windows.UIElement.OnDrop%2A> メソッドで実行したチェックと同じチェックを実行して、円ユーザー コントロールがドラッグされたデータを処理できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="30475-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="30475-224">ユーザー コントロールがデータを処理できる場合、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.Copy> または <xref:System.Windows.DragDropEffects.Move> に設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="30475-225">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="30475-226"><xref:System.Windows.Controls.TextBox>で、テキスト `gre` を選択します。</span><span class="sxs-lookup"><span data-stu-id="30475-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="30475-227">テキストを円コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="30475-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="30475-228">今度は、カーソルがドロップを許可しないことを示すように変化することに注目してください。これは、`gre` が有効な色ではないためです。</span><span class="sxs-lookup"><span data-stu-id="30475-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="30475-229">さらに、ドロップ操作のプレビューを適用して、ユーザー エクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="30475-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="30475-230">この円ユーザー コントロールの場合、<xref:System.Windows.UIElement.OnDragEnter%2A> メソッドと <xref:System.Windows.UIElement.OnDragLeave%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="30475-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="30475-231">データがコントロールにドラッグされると、現在の背景 <xref:System.Windows.Shapes.Shape.Fill%2A> はプレースホルダー変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="30475-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="30475-232">次に、文字列がブラシに変換されて、円の UI を表示する <xref:System.Windows.Shapes.Ellipse> に適用されます。</span><span class="sxs-lookup"><span data-stu-id="30475-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="30475-233">データがドロップされずに円からドラッグされると、元の <xref:System.Windows.Shapes.Shape.Fill%2A> 値が円に再度適用されます。</span><span class="sxs-lookup"><span data-stu-id="30475-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="30475-234">ドラッグ アンド ドロップ操作の効果をプレビューする手順</span><span class="sxs-lookup"><span data-stu-id="30475-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="30475-235">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="30475-236">Circle クラスで、`_previousFill` という名前の <xref:System.Windows.Media.Brush> プライベート変数を宣言し、それを `null` に初期化します。</span><span class="sxs-lookup"><span data-stu-id="30475-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="30475-237">次の <xref:System.Windows.UIElement.OnDragEnter%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.DragEnter> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="30475-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="30475-238">この <xref:System.Windows.UIElement.OnDragEnter%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="30475-239"><xref:System.Windows.Shapes.Ellipse> の <xref:System.Windows.Shapes.Shape.Fill%2A> プロパティを `_previousFill` 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="30475-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="30475-240"><xref:System.Windows.UIElement.OnDrop%2A> メソッドで実行したチェックと同じチェックを実行して、データを <xref:System.Windows.Media.Brush> に変換できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="30475-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="30475-241">データが有効な <xref:System.Windows.Media.Brush>に変換されると、それを<xref:System.Windows.Shapes.Ellipse>の <xref:System.Windows.Shapes.Shape.Fill%2A> に適用します。</span><span class="sxs-lookup"><span data-stu-id="30475-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="30475-242">次の <xref:System.Windows.UIElement.OnDragLeave%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.DragLeave> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="30475-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="30475-243">この <xref:System.Windows.UIElement.OnDragLeave%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="30475-244">`_previousFill` 変数に保存された <xref:System.Windows.Media.Brush> を、円ユーザー コントロールの UI を表示する <xref:System.Windows.Shapes.Ellipse> の <xref:System.Windows.Shapes.Shape.Fill%2A> に適用します。</span><span class="sxs-lookup"><span data-stu-id="30475-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="30475-245">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="30475-246"><xref:System.Windows.Controls.TextBox> で、テキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="30475-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="30475-247">テキストを円コントロールにドラッグします。ドロップはしません。</span><span class="sxs-lookup"><span data-stu-id="30475-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="30475-248">円が青色から緑色に変化します。</span><span class="sxs-lookup"><span data-stu-id="30475-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="30475-249">![ドラッグの効果をプレビューする&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="30475-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="30475-250">テキストを円コントロールからドラッグします。</span><span class="sxs-lookup"><span data-stu-id="30475-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="30475-251">円が緑色から青色に戻ります。</span><span class="sxs-lookup"><span data-stu-id="30475-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="30475-252">ドロップされたデータをパネルで受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="30475-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="30475-253">このセクションでは、円ユーザー コントロールをホストするパネルが、ドラッグされた円データのドラッグ ターゲットとして機能できるようにします。</span><span class="sxs-lookup"><span data-stu-id="30475-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="30475-254">円を一方のパネルからもう一方のパネルに移動できるようにする、または**Ctrl** キーを押したまま円をドラッグ アンド ドロップして円コントロールのコピーを作成できるようにするコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="30475-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="30475-255">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="30475-256">次の XAML に示すように、各 <xref:System.Windows.Controls.StackPanel> で、<xref:System.Windows.UIElement.DragOver> イベントと <xref:System.Windows.UIElement.Drop> イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="30475-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="30475-257"><xref:System.Windows.UIElement.DragOver> イベント ハンドラーに `panel_DragOver` という名前を指定し、<xref:System.Windows.UIElement.Drop> イベント ハンドラーには `panel_Drop` という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="30475-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="30475-258">MainWindows.xaml.cs または MainWindow.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="30475-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="30475-259"><xref:System.Windows.UIElement.DragOver> イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="30475-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="30475-260">この <xref:System.Windows.UIElement.DragOver> イベント ハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="30475-261">ドラッグされたデータに、円ユーザー コントロールによって <xref:System.Windows.DataObject> にパッケージ化され、<xref:System.Windows.DragDrop.DoDragDrop%2A>の呼び出しで渡された "Object" データが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="30475-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="30475-262">"Object" データがある場合、**Ctrl** キーが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30475-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="30475-263">**Ctrl** キーが押されていた場合、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.Copy> に設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="30475-264">それ以外の場合は、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.Move> に設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="30475-265"><xref:System.Windows.UIElement.Drop> イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="30475-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="30475-266">この <xref:System.Windows.UIElement.Drop> イベント ハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="30475-267"><xref:System.Windows.UIElement.Drop> イベントが既に処理されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30475-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="30475-268">たとえば、円が別の円にドロップされ、その円で <xref:System.Windows.UIElement.Drop> イベントが処理される場合、円を含むパネルにそれを処理させる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="30475-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="30475-269"><xref:System.Windows.UIElement.Drop> イベントが処理されていない場合、**Ctrl** キーが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30475-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="30475-270"><xref:System.Windows.UIElement.Drop> が発生したときに **Ctrl** キーが押されていた場合、円コントロールのコピーを作成し、それを <xref:System.Windows.Controls.StackPanel> の <xref:System.Windows.Controls.Panel.Children%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="30475-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="30475-271">**Ctrl** キーが押されていない場合、円をその親パネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションから、ドロップされたパネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="30475-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="30475-272">移動操作またはコピー操作のどちらが実行されたかを <xref:System.Windows.DragDrop.DoDragDrop%2A> メソッドに通知するように <xref:System.Windows.DragEventArgs.Effects%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="30475-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="30475-273">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="30475-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="30475-274"><xref:System.Windows.Controls.TextBox> からテキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="30475-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="30475-275">そのテキストを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="30475-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="30475-276">円コントロールを左側のパネルから右側のパネルにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="30475-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="30475-277">円は、左側のパネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションから削除され、右側のパネルの Children コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="30475-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="30475-278">**Ctrl** キーを押したまま、円コントロールを、現在表示されているパネルからもう一方のパネルにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="30475-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="30475-279">円がコピーされ、そのコピーが、受け取り側のパネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="30475-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="30475-280">![CTRL キーを押したまま円をドラッグする](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="30475-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="30475-281">関連項目</span><span class="sxs-lookup"><span data-stu-id="30475-281">See also</span></span>

- [<span data-ttu-id="30475-282">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="30475-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
