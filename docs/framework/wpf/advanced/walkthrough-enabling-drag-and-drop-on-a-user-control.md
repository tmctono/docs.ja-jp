---
title: 'チュートリアル: ユーザー コントロールでのドラッグ アンド ドロップの有効化'
description: Windows Presentation Foundation でドラッグ アンド ドロップのデータ転送 (受信) に参加できるカスタム ユーザー コントロールを作成する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 12ad47035a09995094014841b083062743fc2574
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168279"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="936ad-103">チュートリアル: ユーザー コントロールでのドラッグ アンド ドロップの有効化</span><span class="sxs-lookup"><span data-stu-id="936ad-103">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="936ad-104">このチュートリアルでは、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] でドラッグ アンド ドロップのデータ転送 (受信) に参加できるカスタム ユーザー コントロールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="936ad-104">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="936ad-105">このチュートリアルでは、円の図形を表すカスタムの WPF <xref:System.Windows.Controls.UserControl> を作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-105">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="936ad-106">また、ドラッグ アンド ドロップによるデータ転送を有効にする機能をコントロールに実装します。</span><span class="sxs-lookup"><span data-stu-id="936ad-106">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="936ad-107">たとえば、ある円コントロールから別の円コントロールにドラッグすると、塗りつぶし色のデータがソースの円からターゲットの円にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="936ad-107">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="936ad-108">円コントロールから <xref:System.Windows.Controls.TextBox> にドラッグすると、塗りつぶし色の文字列表現が <xref:System.Windows.Controls.TextBox> にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="936ad-108">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="936ad-109">さらに、2 つのパネル コントロールと <xref:System.Windows.Controls.TextBox> を含む小さなアプリケーションを作成して、ドラッグ アンド ドロップ機能をテストします。</span><span class="sxs-lookup"><span data-stu-id="936ad-109">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="936ad-110">ドロップされた円データをパネルで処理できるようにするコードを作成します。これにより、ユーザーはあるパネルの子コレクションから別のパネルに円を移動またはコピーできるようになります。</span><span class="sxs-lookup"><span data-stu-id="936ad-110">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="936ad-111">このチュートリアルでは、次の作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="936ad-111">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="936ad-112">カスタム ユーザー コントロールを作成する。</span><span class="sxs-lookup"><span data-stu-id="936ad-112">Create a custom user control.</span></span>

- <span data-ttu-id="936ad-113">ユーザー コントロールをドラッグ ソースとして有効にする。</span><span class="sxs-lookup"><span data-stu-id="936ad-113">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="936ad-114">ユーザー コントロールをドラッグ ターゲットとして有効にする。</span><span class="sxs-lookup"><span data-stu-id="936ad-114">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="936ad-115">ユーザー コントロールからドロップされたデータをパネルで受信できるようにする。</span><span class="sxs-lookup"><span data-stu-id="936ad-115">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="936ad-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="936ad-116">Prerequisites</span></span>

<span data-ttu-id="936ad-117">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="936ad-117">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="936ad-118">アプリケーション プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="936ad-118">Create the Application Project</span></span>
 <span data-ttu-id="936ad-119">このセクションでは、2 つのパネルと <xref:System.Windows.Controls.TextBox> で構成されるメイン ページを含むアプリケーション インフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="936ad-120">Visual Basic または Visual C# で、`DragDropExample` という名前の WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-120">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="936ad-121">詳細については、「[チュートリアル:初めての WPF デスクトップ アプリケーション](../getting-started/walkthrough-my-first-wpf-desktop-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="936ad-121">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="936ad-122">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-122">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="936ad-123"><xref:System.Windows.Controls.Grid> の開始タグと終了タグの間に次のマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-123">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="936ad-124">このマークアップは、テスト アプリケーションのユーザー インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-124">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="936ad-125">新しいユーザー コントロールをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="936ad-125">Add a New User Control to the Project</span></span>
 <span data-ttu-id="936ad-126">このセクションでは、新しいユーザー コントロールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-126">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="936ad-127">[プロジェクト] メニューで、 **[ユーザー コントロールの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="936ad-127">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="936ad-128">**[新しい項目の追加]** ダイアログ ボックスで、名前を `Circle.xaml` に変更し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="936ad-128">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="936ad-129">Circle.xaml とその分離コードがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-129">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="936ad-130">Circle.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-130">Open Circle.xaml.</span></span>

     <span data-ttu-id="936ad-131">このファイルには、ユーザー コントロールのユーザー インターフェイス要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="936ad-131">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="936ad-132">次のマークアップをルート <xref:System.Windows.Controls.Grid> に追加し、UI として青色の円を含む単純なユーザー コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-132">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="936ad-133">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-133">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="936ad-134">C# で、パラメーターなしのコンストラクターの後に次のコードを追加して、コピー コンストラクターを作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-134">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="936ad-135">Visual Basic で、次のコードを追加して、パラメーターなしのコンストラクターとコピー コンストラクターの両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-135">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="936ad-136">ユーザー コントロールをコピーできるようにするために、分離コード ファイルにコピー コンストラクター メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-136">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="936ad-137">単純な円形のユーザー コントロールの場合、ユーザー コントロールの塗りつぶしとサイズのみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="936ad-137">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="936ad-138">ユーザー コントロールをメイン ウィンドウに追加する</span><span class="sxs-lookup"><span data-stu-id="936ad-138">Add the user control to the main window</span></span>

1. <span data-ttu-id="936ad-139">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-139">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="936ad-140"><xref:System.Windows.Window> の開始タグで、次の XAML を追加して、現在のアプリケーションへの XML 名前空間参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-140">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="936ad-141">最初の <xref:System.Windows.Controls.StackPanel>で、次の XAML を追加して、最初のパネルの円ユーザー コントロールの 2 つのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="936ad-141">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="936ad-142">パネルの完全な XAML は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="936ad-142">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="936ad-143">ユーザー コントロールでドラッグ ソース イベントを実装する</span><span class="sxs-lookup"><span data-stu-id="936ad-143">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="936ad-144">このセクションでは、<xref:System.Windows.UIElement.OnMouseMove%2A> メソッドをオーバーライドして、ドラッグ アンド ドロップ操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="936ad-144">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="936ad-145">ドラッグが開始されたら (マウス ボタンが押されて、マウスが移動されたら)、<xref:System.Windows.DataObject>に転送されるデータをパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-145">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="936ad-146">この場合、円コントロールは、3 つのデータ項目 (塗りつぶし色の文字列表現、高さの double 表現、それ自体のコピー) をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-146">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="936ad-147">ドラッグ アンド ドロップ操作を開始する手順</span><span class="sxs-lookup"><span data-stu-id="936ad-147">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="936ad-148">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-148">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="936ad-149">次の <xref:System.Windows.UIElement.OnMouseMove%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.MouseMove> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="936ad-149">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="936ad-150">この <xref:System.Windows.UIElement.OnMouseMove%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-150">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-151">マウスの移動中にマウスの左ボタンが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="936ad-151">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="936ad-152">円データを <xref:System.Windows.DataObject> にパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-152">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="936ad-153">この場合、円コントロールは、3 つのデータ項目 (塗りつぶし色の文字列表現、高さの double 表現、それ自体のコピー) をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-153">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="936ad-154">静的 <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> メソッドを呼び出して、ドラッグ アンド ドロップ操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="936ad-154">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="936ad-155">次の 3 つのパラメーターを <xref:System.Windows.DragDrop.DoDragDrop%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="936ad-155">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="936ad-156">`dragSource` - このコントロールへの参照。</span><span class="sxs-lookup"><span data-stu-id="936ad-156">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="936ad-157">`data` - 前のコードで作成された <xref:System.Windows.DataObject>。</span><span class="sxs-lookup"><span data-stu-id="936ad-157">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="936ad-158">`allowedEffects` - 許可されたドラッグ アンド ドロップ操作。これは、<xref:System.Windows.DragDropEffects.Copy> または <xref:System.Windows.DragDropEffects.Move> です。</span><span class="sxs-lookup"><span data-stu-id="936ad-158">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="936ad-159">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-159">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="936ad-160">いずれかの円コントロールをクリックしてパネル、もう一方の円、<xref:System.Windows.Controls.TextBox> にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="936ad-160">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="936ad-161"><xref:System.Windows.Controls.TextBox>にドラッグすると、カーソルが変化して移動を示すようになります。</span><span class="sxs-lookup"><span data-stu-id="936ad-161">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="936ad-162">円を <xref:System.Windows.Controls.TextBox>にドラッグしながら、**Ctrl** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="936ad-162">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="936ad-163">カーソルが変化してコピーを示すようになる方法にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="936ad-163">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="936ad-164">円を <xref:System.Windows.Controls.TextBox> にドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="936ad-164">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="936ad-165">円の塗りつぶし色の文字列表現が <xref:System.Windows.Controls.TextBox> に追加されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-165">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="936ad-166">![円の塗りつぶしの色の文字列表現](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="936ad-166">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="936ad-167">既定では、カーソルは、ドラッグ アンド ドロップ操作中に変化して、データのドロップによる効果を示します。</span><span class="sxs-lookup"><span data-stu-id="936ad-167">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="936ad-168"><xref:System.Windows.UIElement.GiveFeedback> イベントを処理して、別のカーソルを設定することによって、ユーザーに表示するフィードバックをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="936ad-168">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="936ad-169">ユーザーにフィードバックを表示する</span><span class="sxs-lookup"><span data-stu-id="936ad-169">Give feedback to the user</span></span>

1. <span data-ttu-id="936ad-170">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-170">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="936ad-171">次の <xref:System.Windows.UIElement.OnGiveFeedback%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.GiveFeedback> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="936ad-171">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="936ad-172">この <xref:System.Windows.UIElement.OnGiveFeedback%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-172">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-173">ドロップ ターゲットの <xref:System.Windows.UIElement.DragOver> イベント ハンドラーで設定されている <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 値を確認します。</span><span class="sxs-lookup"><span data-stu-id="936ad-173">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="936ad-174"><xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> 値に基づいてカスタム カーソルを設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-174">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="936ad-175">カーソルは、データのドロップによる効果について視覚的フィードバックをユーザーに表示することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="936ad-175">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="936ad-176">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-176">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="936ad-177">いずれかの円コントロールをパネル、もう一方の円、<xref:System.Windows.Controls.TextBox> にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="936ad-177">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="936ad-178">今度は、カーソルが、<xref:System.Windows.UIElement.OnGiveFeedback%2A> で指定したカスタム カーソルになることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="936ad-178">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="936ad-179">![カスタム カーソルによるドラッグ アンド ドロップ](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="936ad-179">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="936ad-180"><xref:System.Windows.Controls.TextBox> からテキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="936ad-180">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="936ad-181">テキスト `green` を円コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="936ad-181">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="936ad-182">既定のカーソルは、ドラッグ アンド ドロップ操作の効果を示すために表示されていることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="936ad-182">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="936ad-183">フィードバック カーソルは、常にドラッグ ソースによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-183">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="936ad-184">ユーザー コントロールにドロップ ターゲット イベントを実装する</span><span class="sxs-lookup"><span data-stu-id="936ad-184">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="936ad-185">このセクションでは、ユーザー コントロールがドロップ ターゲットであり、ユーザー コントロールをドロップ ターゲットとして有効にするメソッドをオーバーライドし、ドロップされたデータを処理することを指定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-185">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="936ad-186">ユーザー コントロールをドロップ ターゲットとして有効にする手順</span><span class="sxs-lookup"><span data-stu-id="936ad-186">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="936ad-187">Circle.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-187">Open Circle.xaml.</span></span>

2. <span data-ttu-id="936ad-188"><xref:System.Windows.Controls.UserControl> の開始タグで、<xref:System.Windows.UIElement.AllowDrop%2A> プロパティを追加し、それを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-188">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="936ad-189"><xref:System.Windows.UIElement.AllowDrop%2A> が `true` に設定され、ドラッグ ソースのデータが円ユーザー コントロールにドロップされると、<xref:System.Windows.UIElement.OnDrop%2A> メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-189">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="936ad-190">このメソッドでは、ドロップされたデータを処理し、データを円に適用します。</span><span class="sxs-lookup"><span data-stu-id="936ad-190">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="936ad-191">ドロップされたデータを処理する手順</span><span class="sxs-lookup"><span data-stu-id="936ad-191">To process the dropped data</span></span>

1. <span data-ttu-id="936ad-192">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-192">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="936ad-193">次の <xref:System.Windows.UIElement.OnDrop%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.Drop> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="936ad-193">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="936ad-194">この <xref:System.Windows.UIElement.OnDrop%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-194">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-195"><xref:System.Windows.DataObject.GetDataPresent%2A> メソッドを使用して、ドラッグされたデータに文字列オブジェクトが含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="936ad-195">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="936ad-196">文字列データがある場合、<xref:System.Windows.DataObject.GetData%2A> メソッドを使用して、それを抽出します。</span><span class="sxs-lookup"><span data-stu-id="936ad-196">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="936ad-197"><xref:System.Windows.Media.BrushConverter> を使用して、文字列の <xref:System.Windows.Media.Brush> への変換を試みます。</span><span class="sxs-lookup"><span data-stu-id="936ad-197">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="936ad-198">変換が成功した場合、円コントロールの UI を表示する <xref:System.Windows.Shapes.Ellipse> の <xref:System.Windows.Shapes.Shape.Fill%2A> にブラシを適用します。</span><span class="sxs-lookup"><span data-stu-id="936ad-198">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="936ad-199"><xref:System.Windows.UIElement.Drop> イベントを処理済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="936ad-199">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="936ad-200">このイベントを受信する他の要素に、イベントが円ユーザー コントロールで処理されたことを認識させるために、ドロップ イベントを処理済みとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-200">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="936ad-201">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-201">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="936ad-202"><xref:System.Windows.Controls.TextBox> で、テキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="936ad-202">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="936ad-203">そのテキストを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="936ad-203">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="936ad-204">円が青色から緑色に変化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-204">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="936ad-205">![ブラシへの文字列の変換](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="936ad-205">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="936ad-206"><xref:System.Windows.Controls.TextBox> にテキスト `green` を入力します。</span><span class="sxs-lookup"><span data-stu-id="936ad-206">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="936ad-207"><xref:System.Windows.Controls.TextBox>で、テキスト `gre` を選択します。</span><span class="sxs-lookup"><span data-stu-id="936ad-207">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="936ad-208">それを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="936ad-208">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="936ad-209">カーソルが変化して、ドロップが許可されていることを示しますが、円の色は変化していないことに注目してください。これは、`gre` が有効な色ではないためです。</span><span class="sxs-lookup"><span data-stu-id="936ad-209">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="936ad-210">緑色の円コントロールをドラッグして青色の円コントロールにドロップします。</span><span class="sxs-lookup"><span data-stu-id="936ad-210">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="936ad-211">円が青色から緑色に変化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-211">The Circle changes from blue to green.</span></span> <span data-ttu-id="936ad-212">表示されるカーソルが、<xref:System.Windows.Controls.TextBox> または円のどちらがドラッグ ソースであるかによって異なることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="936ad-212">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="936ad-213">要素をドロップ ターゲットとして有効にするために必要な手順は、<xref:System.Windows.UIElement.AllowDrop%2A> プロパティを `true` に設定して、ドロップされたデータを処理することだけです。</span><span class="sxs-lookup"><span data-stu-id="936ad-213">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="936ad-214">しかし、より優れたユーザー エクスペリエンスを提供するには、<xref:System.Windows.UIElement.DragEnter>、<xref:System.Windows.UIElement.DragLeave>、<xref:System.Windows.UIElement.DragOver> の各イベントも処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-214">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="936ad-215">これらのイベントでは、データがドロップされる前に、チェックを実行して、ユーザーに追加のフィードバックを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="936ad-215">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="936ad-216">データが円ユーザー コントロールにドラッグされると、コントロールは、ドラッグされているデータを処理できるかどうかをドラッグ ソースに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-216">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="936ad-217">コントロールがデータの処理方法を認識していない場合、ドロップを拒否する必要があります。</span><span class="sxs-lookup"><span data-stu-id="936ad-217">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="936ad-218">このためには、<xref:System.Windows.UIElement.DragOver> イベントを処理して、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-218">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="936ad-219">データのドロップが許可されていることを確認する手順</span><span class="sxs-lookup"><span data-stu-id="936ad-219">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="936ad-220">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-220">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="936ad-221">次の <xref:System.Windows.UIElement.OnDragOver%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.DragOver> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="936ad-221">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="936ad-222">この <xref:System.Windows.UIElement.OnDragOver%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-222">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-223"><xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.None> に設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-223">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="936ad-224"><xref:System.Windows.UIElement.OnDrop%2A> メソッドで実行したチェックと同じチェックを実行して、円ユーザー コントロールがドラッグされたデータを処理できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="936ad-224">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="936ad-225">ユーザー コントロールがデータを処理できる場合、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.Copy> または <xref:System.Windows.DragDropEffects.Move> に設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-225">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="936ad-226">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-226">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="936ad-227"><xref:System.Windows.Controls.TextBox>で、テキスト `gre` を選択します。</span><span class="sxs-lookup"><span data-stu-id="936ad-227">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="936ad-228">テキストを円コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="936ad-228">Drag the text to a Circle control.</span></span> <span data-ttu-id="936ad-229">今度は、カーソルがドロップを許可しないことを示すように変化することに注目してください。これは、`gre` が有効な色ではないためです。</span><span class="sxs-lookup"><span data-stu-id="936ad-229">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="936ad-230">さらに、ドロップ操作のプレビューを適用して、ユーザー エクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="936ad-230">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="936ad-231">この円ユーザー コントロールの場合、<xref:System.Windows.UIElement.OnDragEnter%2A> メソッドと <xref:System.Windows.UIElement.OnDragLeave%2A> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="936ad-231">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="936ad-232">データがコントロールにドラッグされると、現在の背景 <xref:System.Windows.Shapes.Shape.Fill%2A> はプレースホルダー変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-232">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="936ad-233">次に、文字列がブラシに変換されて、円の UI を表示する <xref:System.Windows.Shapes.Ellipse> に適用されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-233">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="936ad-234">データがドロップされずに円からドラッグされると、元の <xref:System.Windows.Shapes.Shape.Fill%2A> 値が円に再度適用されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-234">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="936ad-235">ドラッグ アンド ドロップ操作の効果をプレビューする手順</span><span class="sxs-lookup"><span data-stu-id="936ad-235">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="936ad-236">Circle.xaml.cs または Circle.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-236">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="936ad-237">Circle クラスで、`_previousFill` という名前の <xref:System.Windows.Media.Brush> プライベート変数を宣言し、それを `null` に初期化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-237">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="936ad-238">次の <xref:System.Windows.UIElement.OnDragEnter%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.DragEnter> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="936ad-238">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="936ad-239">この <xref:System.Windows.UIElement.OnDragEnter%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-239">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-240"><xref:System.Windows.Shapes.Ellipse> の <xref:System.Windows.Shapes.Shape.Fill%2A> プロパティを `_previousFill` 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="936ad-240">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="936ad-241"><xref:System.Windows.UIElement.OnDrop%2A> メソッドで実行したチェックと同じチェックを実行して、データを <xref:System.Windows.Media.Brush> に変換できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="936ad-241">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="936ad-242">データが有効な <xref:System.Windows.Media.Brush>に変換されると、それを<xref:System.Windows.Shapes.Ellipse>の <xref:System.Windows.Shapes.Shape.Fill%2A> に適用します。</span><span class="sxs-lookup"><span data-stu-id="936ad-242">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="936ad-243">次の <xref:System.Windows.UIElement.OnDragLeave%2A> オーバーライドを追加して、<xref:System.Windows.UIElement.DragLeave> イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="936ad-243">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="936ad-244">この <xref:System.Windows.UIElement.OnDragLeave%2A> オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-244">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-245">`_previousFill` 変数に保存された <xref:System.Windows.Media.Brush> を、円ユーザー コントロールの UI を表示する <xref:System.Windows.Shapes.Ellipse> の <xref:System.Windows.Shapes.Shape.Fill%2A> に適用します。</span><span class="sxs-lookup"><span data-stu-id="936ad-245">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="936ad-246">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-246">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="936ad-247"><xref:System.Windows.Controls.TextBox> で、テキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="936ad-247">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="936ad-248">テキストを円コントロールにドラッグします。ドロップはしません。</span><span class="sxs-lookup"><span data-stu-id="936ad-248">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="936ad-249">円が青色から緑色に変化します。</span><span class="sxs-lookup"><span data-stu-id="936ad-249">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="936ad-250">![ドラッグ アンド ドロップ操作の効果のプレビュー](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="936ad-250">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="936ad-251">テキストを円コントロールからドラッグします。</span><span class="sxs-lookup"><span data-stu-id="936ad-251">Drag the text away from the Circle control.</span></span> <span data-ttu-id="936ad-252">円が緑色から青色に戻ります。</span><span class="sxs-lookup"><span data-stu-id="936ad-252">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="936ad-253">ドロップされたデータをパネルで受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="936ad-253">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="936ad-254">このセクションでは、円ユーザー コントロールをホストするパネルが、ドラッグされた円データのドラッグ ターゲットとして機能できるようにします。</span><span class="sxs-lookup"><span data-stu-id="936ad-254">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="936ad-255">円を一方のパネルからもう一方のパネルに移動できるようにする、または**Ctrl** キーを押したまま円をドラッグ アンド ドロップして円コントロールのコピーを作成できるようにするコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="936ad-255">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="936ad-256">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-256">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="936ad-257">次の XAML に示すように、各 <xref:System.Windows.Controls.StackPanel> で、<xref:System.Windows.UIElement.DragOver> イベントと <xref:System.Windows.UIElement.Drop> イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-257">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="936ad-258"><xref:System.Windows.UIElement.DragOver> イベント ハンドラーに `panel_DragOver` という名前を指定し、<xref:System.Windows.UIElement.Drop> イベント ハンドラーには `panel_Drop` という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-258">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="936ad-259">MainWindows.xaml.cs または MainWindow.xaml.vb を開きます。</span><span class="sxs-lookup"><span data-stu-id="936ad-259">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="936ad-260"><xref:System.Windows.UIElement.DragOver> イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-260">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="936ad-261">この <xref:System.Windows.UIElement.DragOver> イベント ハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-261">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-262">ドラッグされたデータに、円ユーザー コントロールによって <xref:System.Windows.DataObject> にパッケージ化され、<xref:System.Windows.DragDrop.DoDragDrop%2A>の呼び出しで渡された "Object" データが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="936ad-262">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="936ad-263">"Object" データがある場合、**Ctrl** キーが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="936ad-263">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="936ad-264">**Ctrl** キーが押されていた場合、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.Copy> に設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-264">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="936ad-265">それ以外の場合は、<xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.Move> に設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-265">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="936ad-266"><xref:System.Windows.UIElement.Drop> イベント ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-266">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="936ad-267">この <xref:System.Windows.UIElement.Drop> イベント ハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-267">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="936ad-268"><xref:System.Windows.UIElement.Drop> イベントが既に処理されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="936ad-268">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="936ad-269">たとえば、円が別の円にドロップされ、その円で <xref:System.Windows.UIElement.Drop> イベントが処理される場合、円を含むパネルにそれを処理させる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="936ad-269">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="936ad-270"><xref:System.Windows.UIElement.Drop> イベントが処理されていない場合、**Ctrl** キーが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="936ad-270">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="936ad-271"><xref:System.Windows.UIElement.Drop> が発生したときに **Ctrl** キーが押されていた場合、円コントロールのコピーを作成し、それを <xref:System.Windows.Controls.StackPanel> の <xref:System.Windows.Controls.Panel.Children%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="936ad-271">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="936ad-272">**Ctrl** キーが押されていない場合、円をその親パネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションから、ドロップされたパネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="936ad-272">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="936ad-273">移動操作またはコピー操作のどちらが実行されたかを <xref:System.Windows.DragDrop.DoDragDrop%2A> メソッドに通知するように <xref:System.Windows.DragEventArgs.Effects%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="936ad-273">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="936ad-274">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="936ad-274">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="936ad-275"><xref:System.Windows.Controls.TextBox> からテキスト `green` を選択します。</span><span class="sxs-lookup"><span data-stu-id="936ad-275">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="936ad-276">そのテキストを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="936ad-276">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="936ad-277">円コントロールを左側のパネルから右側のパネルにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="936ad-277">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="936ad-278">円は、左側のパネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションから削除され、右側のパネルの Children コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-278">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="936ad-279">**Ctrl** キーを押したまま、円コントロールを、現在表示されているパネルからもう一方のパネルにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="936ad-279">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="936ad-280">円がコピーされ、そのコピーが、受け取り側のパネルの <xref:System.Windows.Controls.Panel.Children%2A> コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="936ad-280">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="936ad-281">![Ctrl キーを押しながら円をドラッグする](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="936ad-281">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="936ad-282">関連項目</span><span class="sxs-lookup"><span data-stu-id="936ad-282">See also</span></span>

- [<span data-ttu-id="936ad-283">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="936ad-283">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
