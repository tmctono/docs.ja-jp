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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991809"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="c18eb-102">チュートリアル: ユーザー コントロールでのドラッグ アンド ドロップの有効化</span><span class="sxs-lookup"><span data-stu-id="c18eb-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="c18eb-103">このチュートリアルでは、で[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]ドラッグアンドドロップデータ転送に参加できるカスタムユーザーコントロールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="c18eb-104">このチュートリアルでは、円図形を表すカスタム<xref:System.Windows.Controls.UserControl> WPF を作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="c18eb-105">ドラッグアンドドロップによるデータ転送を可能にするために、コントロールに機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="c18eb-106">たとえば、ある円コントロールから別のコントロールにドラッグすると、塗りつぶしの色データがソースの円からターゲットにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="c18eb-107">円コントロール<xref:System.Windows.Controls.TextBox>からにドラッグすると、塗りつぶしの色の文字列形式がにコピー <xref:System.Windows.Controls.TextBox>されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="c18eb-108">また、2つのパネルコントロールと、を<xref:System.Windows.Controls.TextBox>使用してドラッグアンドドロップ機能をテストする小さなアプリケーションも作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="c18eb-109">パネルがドロップされた円データを処理できるようにするコードを記述します。これにより、あるパネルの子コレクションから別のパネルに円を移動またはコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="c18eb-110">このチュートリアルでは、次の作業について説明します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="c18eb-111">カスタムユーザーコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-111">Create a custom user control.</span></span>

- <span data-ttu-id="c18eb-112">ユーザーコントロールがドラッグ元になるようにします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="c18eb-113">ユーザーコントロールをドロップ先として有効にします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="c18eb-114">パネルで、ユーザーコントロールから削除されたデータを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c18eb-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c18eb-115">Prerequisites</span></span>

<span data-ttu-id="c18eb-116">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="c18eb-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="c18eb-117">アプリケーションプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c18eb-117">Create the Application Project</span></span>
 <span data-ttu-id="c18eb-118">このセクションでは、2つのパネルとを<xref:System.Windows.Controls.TextBox>持つメインページを含むアプリケーションインフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="c18eb-119">Visual Basic またはという名前C# `DragDropExample`のビジュアルで新しい WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="c18eb-120">詳細については、「[チュートリアル:初めての WPF デスクトップ](../getting-started/walkthrough-my-first-wpf-desktop-application.md)アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c18eb-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="c18eb-121">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="c18eb-122">開始タグと終了<xref:System.Windows.Controls.Grid>タグの間に次のマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="c18eb-123">このマークアップは、テストアプリケーションのユーザーインターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="c18eb-124">新しいユーザーコントロールをプロジェクトに追加する</span><span class="sxs-lookup"><span data-stu-id="c18eb-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="c18eb-125">このセクションでは、新しいユーザーコントロールをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="c18eb-126">プロジェクト メニューの **ユーザーコントロールの追加** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="c18eb-127">**[新しい項目の追加]** ダイアログボックスで、名前を`Circle.xaml`に変更し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="c18eb-128">Circle .xaml とその分離コードがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="c18eb-129">[Circle .xaml] を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="c18eb-130">このファイルには、ユーザーコントロールのユーザーインターフェイス要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="c18eb-131">次のマークアップをルート<xref:System.Windows.Controls.Grid>に追加して、UI として青い円を持つ単純なユーザーコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="c18eb-132">Circle.xaml.cs または Circle .xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="c18eb-133">でC#、パラメーターなしのコンストラクターの後に次のコードを追加して、コピーコンストラクターを作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-133">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="c18eb-134">Visual Basic で、次のコードを追加して、パラメーターなしのコンストラクターとコピーコンストラクターの両方を作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-134">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="c18eb-135">ユーザーコントロールのコピーを許可するには、分離コードファイルにコピーコンストラクターメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="c18eb-136">簡略化された円ユーザーコントロールでは、ユーザーコントロールのの塗りつぶしとサイズのみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="c18eb-137">メインウィンドウにユーザーコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="c18eb-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="c18eb-138">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="c18eb-139">次の XAML を開始<xref:System.Windows.Window>タグに追加して、現在のアプリケーションへの XML 名前空間参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="c18eb-140">最初<xref:System.Windows.Controls.StackPanel>のパネルで、次の XAML を追加して、円ユーザーコントロールのインスタンスを2つ作成します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="c18eb-141">パネルの完全な XAML は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="c18eb-142">ユーザーコントロールでのドラッグソースイベントの実装</span><span class="sxs-lookup"><span data-stu-id="c18eb-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="c18eb-143">このセクションでは、 <xref:System.Windows.UIElement.OnMouseMove%2A>メソッドをオーバーライドし、ドラッグアンドドロップ操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="c18eb-144">ドラッグが開始された場合 (マウスボタンが押された状態でマウスが移動された場合)、に転送<xref:System.Windows.DataObject>されるデータをパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="c18eb-145">この場合、円コントロールは3つのデータ項目をパッケージ化します。塗りつぶしの色の文字列形式、その高さを示す double 表現、およびそれ自体のコピー。</span><span class="sxs-lookup"><span data-stu-id="c18eb-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="c18eb-146">ドラッグアンドドロップ操作を開始するには</span><span class="sxs-lookup"><span data-stu-id="c18eb-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="c18eb-147">Circle.xaml.cs または Circle .xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="c18eb-148">次<xref:System.Windows.UIElement.OnMouseMove%2A>のオーバーライドを追加して、 <xref:System.Windows.UIElement.MouseMove>イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="c18eb-149">この<xref:System.Windows.UIElement.OnMouseMove%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-150">マウスの移動中にマウスの左ボタンが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="c18eb-151">円データ<xref:System.Windows.DataObject>をにパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="c18eb-152">この場合、円コントロールは3つのデータ項目をパッケージ化します。塗りつぶしの色の文字列形式、その高さを示す double 表現、およびそれ自体のコピー。</span><span class="sxs-lookup"><span data-stu-id="c18eb-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="c18eb-153">静的<xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType>メソッドを呼び出して、ドラッグアンドドロップ操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="c18eb-154">次の3つのパラメーターを<xref:System.Windows.DragDrop.DoDragDrop%2A>メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="c18eb-155">`dragSource`–このコントロールへの参照。</span><span class="sxs-lookup"><span data-stu-id="c18eb-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="c18eb-156">`data`–前のコードで作成された。<xref:System.Windows.DataObject></span><span class="sxs-lookup"><span data-stu-id="c18eb-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="c18eb-157">`allowedEffects`–使用できるドラッグアンドドロップ操作。これ<xref:System.Windows.DragDropEffects.Copy>は、または<xref:System.Windows.DragDropEffects.Move>です。</span><span class="sxs-lookup"><span data-stu-id="c18eb-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="c18eb-158">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="c18eb-159">円コントロールのいずれかをクリックし、パネル、もう一方の円、およびに<xref:System.Windows.Controls.TextBox>ドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="c18eb-160">上<xref:System.Windows.Controls.TextBox>にドラッグすると、カーソルは移動を示すように変更されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="c18eb-161">上<xref:System.Windows.Controls.TextBox>に円をドラッグしているときに、 **ctrl**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="c18eb-162">カーソルがコピーを示すように変更されていることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="c18eb-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="c18eb-163">円をに<xref:System.Windows.Controls.TextBox>ドラッグアンドドロップします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="c18eb-164">円の塗りつぶしの色の文字列形式がに<xref:System.Windows.Controls.TextBox>追加されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="c18eb-165">![円の塗りつぶしの色の文字列表現](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="c18eb-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="c18eb-166">既定では、カーソルはドラッグアンドドロップ操作中に変更され、データの削除による影響を示します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="c18eb-167"><xref:System.Windows.UIElement.GiveFeedback>イベントを処理し、別のカーソルを設定することによって、ユーザーに与えられたフィードバックをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="c18eb-168">ユーザーへのフィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="c18eb-168">Give feedback to the user</span></span>

1. <span data-ttu-id="c18eb-169">Circle.xaml.cs または Circle .xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="c18eb-170">次<xref:System.Windows.UIElement.OnGiveFeedback%2A>のオーバーライドを追加して、 <xref:System.Windows.UIElement.GiveFeedback>イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="c18eb-171">この<xref:System.Windows.UIElement.OnGiveFeedback%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-172">ドロップ先の<xref:System.Windows.UIElement.DragOver>イベントハンドラーで設定されている値を確認します。<xref:System.Windows.GiveFeedbackEventArgs.Effects%2A></span><span class="sxs-lookup"><span data-stu-id="c18eb-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="c18eb-173"><xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>値に基づいてカスタムカーソルを設定します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="c18eb-174">カーソルは、データの削除による影響についてユーザーに視覚的フィードバックを提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="c18eb-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="c18eb-175">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="c18eb-176">円コントロールの1つを、パネル、もう一方の円、およびに<xref:System.Windows.Controls.TextBox>ドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="c18eb-177">カーソルが、 <xref:System.Windows.UIElement.OnGiveFeedback%2A>オーバーライドで指定したカスタムカーソルになっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c18eb-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="c18eb-178">![カスタムカーソルを使用したドラッグアンドドロップ](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="c18eb-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="c18eb-179">からテキスト`green`を選択します。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="c18eb-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="c18eb-180">`green`テキストを円コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="c18eb-181">ドラッグアンドドロップ操作の効果を示すために、既定のカーソルが表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c18eb-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="c18eb-182">フィードバックカーソルは、常にドラッグソースによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="c18eb-183">ユーザーコントロールにドロップ先のイベントを実装する</span><span class="sxs-lookup"><span data-stu-id="c18eb-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="c18eb-184">このセクションでは、ユーザーコントロールがドロップ先であることを指定し、ユーザーコントロールをドロップ先として使用できるようにするメソッドをオーバーライドして、削除されたデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="c18eb-185">ユーザーコントロールをドロップ先として有効にするには</span><span class="sxs-lookup"><span data-stu-id="c18eb-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="c18eb-186">[Circle .xaml] を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="c18eb-187">開始<xref:System.Windows.Controls.UserControl>タグに<xref:System.Windows.UIElement.AllowDrop%2A>プロパティを追加し、をに`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="c18eb-188">メソッドは、 <xref:System.Windows.UIElement.AllowDrop%2A>プロパティがに`true`設定され、ドラッグ元のデータが円ユーザーコントロールにドロップされたときに呼び出されます。 <xref:System.Windows.UIElement.OnDrop%2A></span><span class="sxs-lookup"><span data-stu-id="c18eb-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="c18eb-189">この方法では、削除されたデータを処理し、そのデータを円に適用します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="c18eb-190">削除されたデータを処理するには</span><span class="sxs-lookup"><span data-stu-id="c18eb-190">To process the dropped data</span></span>

1. <span data-ttu-id="c18eb-191">Circle.xaml.cs または Circle .xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="c18eb-192">次<xref:System.Windows.UIElement.OnDrop%2A>のオーバーライドを追加して、 <xref:System.Windows.UIElement.Drop>イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="c18eb-193">この<xref:System.Windows.UIElement.OnDrop%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-194"><xref:System.Windows.DataObject.GetDataPresent%2A>メソッドを使用して、ドラッグされたデータに文字列オブジェクトが含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="c18eb-195"><xref:System.Windows.DataObject.GetData%2A>メソッドを使用して、文字列データが存在する場合はそれを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="c18eb-196">を使用して、文字列<xref:System.Windows.Media.Brush>をに変換しようとします。 <xref:System.Windows.Media.BrushConverter></span><span class="sxs-lookup"><span data-stu-id="c18eb-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="c18eb-197">変換が成功した場合、は、円コントロール<xref:System.Windows.Shapes.Shape.Fill%2A>の UI <xref:System.Windows.Shapes.Ellipse>を提供するのにブラシを適用します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="c18eb-198">イベントを<xref:System.Windows.UIElement.Drop>処理済みとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="c18eb-199">このイベントを受信する他の要素が、Circle ユーザーコントロールによって処理されたことを認識するように、drop イベントを処理済みとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="c18eb-200">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="c18eb-201">でテキスト`green`を選択します。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="c18eb-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="c18eb-202">テキストを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="c18eb-203">円が青から緑に変わります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="c18eb-204">![文字列をブラシに変換する](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="c18eb-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="c18eb-205">にテキスト`green`を入力します。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="c18eb-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="c18eb-206">でテキスト`gre`を選択します。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="c18eb-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="c18eb-207">それを円コントロールにドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="c18eb-208">カーソルはドロップが許可されていることを示すために変更されますが、は有効な`gre`色ではないため、円の色は変化しません。</span><span class="sxs-lookup"><span data-stu-id="c18eb-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="c18eb-209">緑の円コントロールからドラッグし、青い円コントロールにドロップします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="c18eb-210">円が青から緑に変わります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="c18eb-211">どのカーソルが表示されるかは、 <xref:System.Windows.Controls.TextBox>または円がドラッグ元であるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="c18eb-212">要素をドロップターゲット`true`にできるようにするには、プロパティをに設定し、削除されたデータを処理する必要があります。<xref:System.Windows.UIElement.AllowDrop%2A></span><span class="sxs-lookup"><span data-stu-id="c18eb-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="c18eb-213">ただし、より優れたユーザーエクスペリエンスを提供するには、、 <xref:System.Windows.UIElement.DragEnter> <xref:System.Windows.UIElement.DragLeave>、および<xref:System.Windows.UIElement.DragOver>の各イベントも処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="c18eb-214">これらのイベントでは、データを削除する前に、チェックを実行し、ユーザーに追加のフィードバックを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="c18eb-215">データが円のユーザーコントロール上にドラッグされると、ドラッグ元に対して、ドラッグされているデータを処理できるかどうかを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="c18eb-216">コントロールがデータの処理方法を認識していない場合は、削除を拒否する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="c18eb-217">これを行うには、 <xref:System.Windows.UIElement.DragOver>イベントを処理し、 <xref:System.Windows.DragEventArgs.Effects%2A>プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="c18eb-218">データの削除が許可されていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="c18eb-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="c18eb-219">Circle.xaml.cs または Circle .xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="c18eb-220">次<xref:System.Windows.UIElement.OnDragOver%2A>のオーバーライドを追加して、 <xref:System.Windows.UIElement.DragOver>イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="c18eb-221">この<xref:System.Windows.UIElement.OnDragOver%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-222"><xref:System.Windows.DragEventArgs.Effects%2A> プロパティを <xref:System.Windows.DragDropEffects.None> に設定します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="c18eb-223">は、円ユーザーコントロールがドラッグされ<xref:System.Windows.UIElement.OnDrop%2A>たデータを処理できるかどうかを判断するために、メソッドで実行されるのと同じチェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="c18eb-224">ユーザーコントロールがデータを処理できる場合は、 <xref:System.Windows.DragEventArgs.Effects%2A>プロパティをまたは<xref:System.Windows.DragDropEffects.Move>に<xref:System.Windows.DragDropEffects.Copy>設定します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="c18eb-225">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="c18eb-226">でテキスト`gre`を選択します。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="c18eb-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="c18eb-227">テキストを円コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="c18eb-228">が有効な色ではないため`gre` 、カーソルが変更されていないことを示すようになりました。</span><span class="sxs-lookup"><span data-stu-id="c18eb-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="c18eb-229">削除操作のプレビューを適用することで、ユーザーエクスペリエンスをさらに向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="c18eb-230">Circle ユーザーコントロールでは、メソッド<xref:System.Windows.UIElement.OnDragEnter%2A>と<xref:System.Windows.UIElement.OnDragLeave%2A>メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="c18eb-231">データをコントロールの上にドラッグすると、現在の<xref:System.Windows.Shapes.Shape.Fill%2A>背景がプレースホルダー変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="c18eb-232">次に、文字列がブラシに変換され、 <xref:System.Windows.Shapes.Ellipse>円の UI を提供するに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="c18eb-233">データが削除されずに円の外にドラッグされた<xref:System.Windows.Shapes.Shape.Fill%2A>場合、元の値は円に再適用されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="c18eb-234">ドラッグアンドドロップ操作の効果をプレビューするには</span><span class="sxs-lookup"><span data-stu-id="c18eb-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="c18eb-235">Circle.xaml.cs または Circle .xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="c18eb-236">Circle クラスで、という名前<xref:System.Windows.Media.Brush> `_previousFill`のプライベート変数を宣言し、 `null`それをに初期化します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="c18eb-237">次<xref:System.Windows.UIElement.OnDragEnter%2A>のオーバーライドを追加して、 <xref:System.Windows.UIElement.DragEnter>イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="c18eb-238">この<xref:System.Windows.UIElement.OnDragEnter%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-239">のプロパティ<xref:System.Windows.Shapes.Shape.Fill%2A>を`_previousFill`変数に保存します。 <xref:System.Windows.Shapes.Ellipse></span><span class="sxs-lookup"><span data-stu-id="c18eb-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="c18eb-240"><xref:System.Windows.UIElement.OnDrop%2A> は<xref:System.Windows.Media.Brush>、データをに変換できるかどうかを判断するために、メソッドで実行されるのと同じチェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="c18eb-241">データが有効<xref:System.Windows.Media.Brush>なに変換される場合は、 <xref:System.Windows.Shapes.Shape.Fill%2A>の<xref:System.Windows.Shapes.Ellipse>に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="c18eb-242">次<xref:System.Windows.UIElement.OnDragLeave%2A>のオーバーライドを追加して、 <xref:System.Windows.UIElement.DragLeave>イベントのクラス処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="c18eb-243">この<xref:System.Windows.UIElement.OnDragLeave%2A>オーバーライドは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-244">変数`_previousFill` に保存<xref:System.Windows.Media.Brush>されているを、Circle ユーザーコントロールの UI を提供するのに適用します。<xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Shape.Fill%2A></span><span class="sxs-lookup"><span data-stu-id="c18eb-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="c18eb-245">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="c18eb-246">でテキスト`green`を選択します。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="c18eb-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="c18eb-247">テキストを削除せずに、円コントロールの上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="c18eb-248">円が青から緑に変わります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="c18eb-249">![&#45;&#45;ドラッグアンドドロップ操作の効果をプレビューする](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="c18eb-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="c18eb-250">円コントロールからテキストをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="c18eb-251">円が緑から青に変わります。</span><span class="sxs-lookup"><span data-stu-id="c18eb-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="c18eb-252">パネルでドロップされたデータを受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="c18eb-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="c18eb-253">このセクションでは、円のユーザーコントロールをホストするパネルを、ドラッグした円データのドロップターゲットとして機能するように有効にします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="c18eb-254">1つのパネルから別のパネルに円を移動したり、円をドラッグアンドドロップしながら**Ctrl**キーを押しながら円コントロールのコピーを作成したりできるようにするコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="c18eb-255">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="c18eb-256">次の XAML に示すように、各<xref:System.Windows.Controls.StackPanel>コントロールで、イベント<xref:System.Windows.UIElement.DragOver>と<xref:System.Windows.UIElement.Drop>イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="c18eb-257">イベント<xref:System.Windows.UIElement.DragOver> <xref:System.Windows.UIElement.Drop>ハンドラーにという名前を指定し、イベントハンドラー `panel_Drop`にという名前を指定します。 `panel_DragOver`</span><span class="sxs-lookup"><span data-stu-id="c18eb-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="c18eb-258">MainWindows.xaml.cs または Mainwindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="c18eb-259"><xref:System.Windows.UIElement.DragOver>イベントハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="c18eb-260">この<xref:System.Windows.UIElement.DragOver>イベントハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-261">ドラッグされたデータに、円ユーザーコントロールによってにパッケージさ<xref:System.Windows.DataObject>れ、の<xref:System.Windows.DragDrop.DoDragDrop%2A>呼び出しに渡された "オブジェクト" データが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="c18eb-262">"オブジェクト" データが存在する場合は、 **Ctrl**キーが押されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="c18eb-263">**Ctrl**キーが押されている場合は<xref:System.Windows.DragEventArgs.Effects%2A> 、プロパティ<xref:System.Windows.DragDropEffects.Copy>をに設定します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="c18eb-264">それ以外の場合<xref:System.Windows.DragEventArgs.Effects%2A>は、 <xref:System.Windows.DragDropEffects.Move>プロパティをに設定します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="c18eb-265"><xref:System.Windows.UIElement.Drop>イベントハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="c18eb-266">この<xref:System.Windows.UIElement.Drop>イベントハンドラーは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="c18eb-267"><xref:System.Windows.UIElement.Drop>イベントが既に処理されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="c18eb-268">たとえば、 <xref:System.Windows.UIElement.Drop>イベントを処理する別の円に円がドロップされた場合、その円を含むパネルにもハンドルを表示させたくありません。</span><span class="sxs-lookup"><span data-stu-id="c18eb-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="c18eb-269">イベントが処理されない場合は、Ctrl キーが押されたかどうかを確認します。 <xref:System.Windows.UIElement.Drop></span><span class="sxs-lookup"><span data-stu-id="c18eb-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="c18eb-270">が発生し<xref:System.Windows.UIElement.Drop>たときに Ctrl キーを押すと、によって円コントロールのコピーが作成さ<xref:System.Windows.Controls.Panel.Children%2A>れ、の<xref:System.Windows.Controls.StackPanel>コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="c18eb-271">**Ctrl**キーが押されていない場合、は、 <xref:System.Windows.Controls.Panel.Children%2A> <xref:System.Windows.Controls.Panel.Children%2A>親パネルのコレクションから、削除されたパネルのコレクションに円を移動します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="c18eb-272">プロパティを設定して、 <xref:System.Windows.DragDrop.DoDragDrop%2A>移動またはコピー操作が実行されたかどうかをメソッドに通知します。 <xref:System.Windows.DragEventArgs.Effects%2A></span><span class="sxs-lookup"><span data-stu-id="c18eb-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="c18eb-273">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="c18eb-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="c18eb-274">からテキスト`green`を選択します。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="c18eb-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="c18eb-275">円コントロールの上にテキストをドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="c18eb-276">左パネルから右パネルに円コントロールをドラッグしてドロップします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="c18eb-277">左側のパネルの<xref:System.Windows.Controls.Panel.Children%2A>コレクションから円が削除され、右側のパネルの子コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="c18eb-278">[円] コントロールをパネルからもう一方のパネルにドラッグし、 **Ctrl**キーを押しながらドロップします。</span><span class="sxs-lookup"><span data-stu-id="c18eb-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="c18eb-279">円がコピーされ、コピーが受信パネルの<xref:System.Windows.Controls.Panel.Children%2A>コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c18eb-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="c18eb-280">![CTRL キーを押しながら円をドラッグする](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="c18eb-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="c18eb-281">関連項目</span><span class="sxs-lookup"><span data-stu-id="c18eb-281">See also</span></span>

- [<span data-ttu-id="c18eb-282">ドラッグ アンド ドロップの概要</span><span class="sxs-lookup"><span data-stu-id="c18eb-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
