---
title: 'チュートリアル : Microsoft Expression Blend を使用してボタンを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: 10d049288cf560dadedf7bc5e624deb7c42aae81
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636173"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a><span data-ttu-id="669d1-102">チュートリアル : Microsoft Expression Blend を使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="669d1-102">Walkthrough: Create a Button by Using Microsoft Expression Blend</span></span>

<span data-ttu-id="669d1-103">このチュートリアルでは、Microsoft Expression Blend を使用して、WPF のカスタマイズされたボタンを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="669d1-103">This walkthrough steps you through the process of creating a WPF customized button using Microsoft Expression Blend.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="669d1-104">Microsoft Expression Blend は、実行可能プログラムを作成するためにコンパイルされた [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を生成することによって機能します。</span><span class="sxs-lookup"><span data-stu-id="669d1-104">Microsoft Expression Blend works by generating [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is then compiled to make the executable program.</span></span> <span data-ttu-id="669d1-105">XAML を直接操作する場合は、Blend ではなく Visual Studio で XAML を使用して、同じアプリケーションを作成するもう1つのチュートリアルがあります。</span><span class="sxs-lookup"><span data-stu-id="669d1-105">If you would rather work with XAML directly, there is another walkthrough that creates the same application as this one using XAML with Visual Studio rather than Blend.</span></span> <span data-ttu-id="669d1-106">詳細について[は、「XAML を使用したボタンの作成](walkthrough-create-a-button-by-using-xaml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="669d1-106">See [Create a Button by Using XAML](walkthrough-create-a-button-by-using-xaml.md) for more information.</span></span>

<span data-ttu-id="669d1-107">次の図は、作成するカスタマイズされたボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="669d1-107">The following illustration shows the customized button that you will create.</span></span>

![ユーザーが作成するカスタマイズされたボタン](./media/custom-button-blend-intro.jpg)

## <a name="convert-a-shape-to-a-button"></a><span data-ttu-id="669d1-109">図形をボタンに変換する</span><span class="sxs-lookup"><span data-stu-id="669d1-109">Convert a Shape to a Button</span></span>

<span data-ttu-id="669d1-110">このチュートリアルの最初の部分では、カスタムボタンの外観を独自に作成します。</span><span class="sxs-lookup"><span data-stu-id="669d1-110">In the first part of this walkthrough you create the custom look of the custom button.</span></span> <span data-ttu-id="669d1-111">これを行うには、最初に四角形をボタンに変換します。</span><span class="sxs-lookup"><span data-stu-id="669d1-111">To do this, you first convert a rectangle to a button.</span></span> <span data-ttu-id="669d1-112">次に、ボタンのテンプレートに図形を追加して、より複雑な外観のボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="669d1-112">You then add additional shapes to the template of the button, creating a more complex looking button.</span></span> <span data-ttu-id="669d1-113">通常のボタンで開始してカスタマイズするのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="669d1-113">Why not start with a regular button and customize it?</span></span> <span data-ttu-id="669d1-114">ボタンには必要のない組み込みの機能があるため、カスタムボタンの場合は、四角形から始める方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="669d1-114">Because a button has built-in functionality that you do not need; for custom buttons, it is easier to start with a rectangle.</span></span>

### <a name="to-create-a-new-project-in-expression-blend"></a><span data-ttu-id="669d1-115">Expression Blend で新しいプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="669d1-115">To create a new project in Expression Blend</span></span>

1. <span data-ttu-id="669d1-116">Expression Blend を開始します。</span><span class="sxs-lookup"><span data-stu-id="669d1-116">Start Expression Blend.</span></span> <span data-ttu-id="669d1-117">( **[スタート]** をクリックし、 **[すべてのプログラム]** 、 **[microsoft expression]** の順にポイントし、 **[microsoft expression Blend]** をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="669d1-117">(Click **Start**, point to **All Programs**, point to **Microsoft Expression**, and then click **Microsoft Expression Blend**.)</span></span>

2. <span data-ttu-id="669d1-118">必要に応じて、アプリケーションを最大化します。</span><span class="sxs-lookup"><span data-stu-id="669d1-118">Maximize the application if needed.</span></span>

3. <span data-ttu-id="669d1-119">**[ファイル]** メニューの **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="669d1-119">On the **File** menu, click **New Project**.</span></span>

4. <span data-ttu-id="669d1-120">**[標準アプリケーション (.exe)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="669d1-120">Select **Standard Application (.exe)**.</span></span>

5. <span data-ttu-id="669d1-121">プロジェクトに `CustomButton` という名前を指定し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="669d1-121">Name the project `CustomButton` and press **OK**.</span></span>

<span data-ttu-id="669d1-122">この時点で、空の WPF プロジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="669d1-122">At this point you have a blank WPF project.</span></span> <span data-ttu-id="669d1-123">F5 キーを押してアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="669d1-123">You can press F5 to run the application.</span></span> <span data-ttu-id="669d1-124">ご想像のとおり、アプリケーションは空のウィンドウだけで構成されています。</span><span class="sxs-lookup"><span data-stu-id="669d1-124">As you might expect, the application consists of only a blank window.</span></span> <span data-ttu-id="669d1-125">次に、角丸四角形を作成し、ボタンに変換します。</span><span class="sxs-lookup"><span data-stu-id="669d1-125">Next, you create a rounded rectangle and convert it into a button.</span></span>

### <a name="to-convert-a-rectangle-to-a-button"></a><span data-ttu-id="669d1-126">四角形をボタンに変換するには</span><span class="sxs-lookup"><span data-stu-id="669d1-126">To convert a Rectangle to a Button</span></span>

1. <span data-ttu-id="669d1-127">**Window Background プロパティを black に設定します。** ウィンドウを選択し、**プロパティ タブ**をクリックして、<xref:System.Windows.Controls.Control.Background%2A> プロパティを `Black`に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-127">**Set the Window Background property to black:** Select the Window, click the **Properties Tab**, and set the <xref:System.Windows.Controls.Control.Background%2A> property to `Black`.</span></span>

    ![ボタンの背景を黒に設定する方法](./media/custom-button-blend-changebackground.png)

2. <span data-ttu-id="669d1-129">**ウィンドウのボタンのサイズとほぼ同じ四角形を描画します。** 左側のツールパネルで [四角形] ツールを選択し、四角形をウィンドウにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="669d1-129">**Draw a rectangle approximately the size of a button on the Window:** Select the rectangle tool on the left-hand tool panel and drag the rectangle onto the Window.</span></span>

    ![四角形を描画する方法](./media/custom-button-blend-drawrect.png)

3. <span data-ttu-id="669d1-131">**四角形の角を丸めます。** 四角形のコントロールポイントをドラッグするか、<xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> のプロパティを直接設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-131">**Round out the corners of the rectangle:** Either drag the control points of the rectangle or directly set the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="669d1-132"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> の値を20に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-132">Set the values of <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> to 20.</span></span>

    ![四角形の角を丸くする方法](./media/custom-button-blend-roundcorners.png)

4. <span data-ttu-id="669d1-134">**四角形をボタンに変更します。** 四角形を選択します。</span><span class="sxs-lookup"><span data-stu-id="669d1-134">**Change the rectangle into a button:** Select the rectangle.</span></span> <span data-ttu-id="669d1-135">**[ツール]** メニューの [**作成] ボタン**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="669d1-135">On the **Tools** menu, click **Make Button**.</span></span>

    ![図形をボタンにする方法](./media/custom-button-blend-makebutton.png)

5. <span data-ttu-id="669d1-137">**スタイル/テンプレートのスコープを指定します。** 次のようなダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-137">**Specify the scope of the style/template:** A dialog box like the following appears.</span></span>

    ![[Style リソースの作成] ダイアログ ボックス](./media/custom-button-blend-makebutton2.gif)

    <span data-ttu-id="669d1-139">**[リソース名 (キー)]** で、 **[すべてに適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="669d1-139">For **Resource name (Key)**, select **Apply to all**.</span></span>  <span data-ttu-id="669d1-140">これにより、結果のスタイルとボタンテンプレートが、ボタンであるすべてのオブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-140">This will make the resulting style and button template apply to all objects that are buttons.</span></span> <span data-ttu-id="669d1-141">[**定義] で**、 **[アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="669d1-141">For **Define in**, select **Application**.</span></span> <span data-ttu-id="669d1-142">これにより、結果のスタイルとボタンテンプレートにアプリケーション全体のスコープが設定されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-142">This will make the resulting style and button template have scope over the entire application.</span></span> <span data-ttu-id="669d1-143">これらの2つのボックスの値を設定すると、ボタンのスタイルとテンプレートはアプリケーション全体のすべてのボタンに適用され、アプリケーションで作成したボタンは既定でこのテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="669d1-143">When you set the values in these two boxes, the button style and template apply to all buttons within the entire application and any button you create in the application will, by default, use this template.</span></span>

## <a name="edit-the-button-template"></a><span data-ttu-id="669d1-144">ボタンテンプレートを編集する</span><span class="sxs-lookup"><span data-stu-id="669d1-144">Edit the Button Template</span></span>

<span data-ttu-id="669d1-145">これで、四角形がボタンに変更されました。</span><span class="sxs-lookup"><span data-stu-id="669d1-145">You now have a rectangle that has been changed to a button.</span></span> <span data-ttu-id="669d1-146">このセクションでは、ボタンのテンプレートを変更し、その外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="669d1-146">In this section, you'll modify the template of the button and further customize how it looks.</span></span>

### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a><span data-ttu-id="669d1-147">ボタンテンプレートを編集してボタンの外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="669d1-147">To edit the button template to change the button appearance</span></span>

1. <span data-ttu-id="669d1-148">**テンプレートビューの編集に進む:** ボタンの外観をさらにカスタマイズするには、ボタンテンプレートを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="669d1-148">**Go into edit template view:** To further customize the look of our button, we need to edit the button template.</span></span> <span data-ttu-id="669d1-149">このテンプレートは、四角形をボタンに変換したときに作成されたものです。</span><span class="sxs-lookup"><span data-stu-id="669d1-149">This template was created when we converted the rectangle into a button.</span></span> <span data-ttu-id="669d1-150">ボタンテンプレートを編集するには、ボタンを右クリックし、[**コントロールパーツの編集] (テンプレート)** 、 **[テンプレートの編集]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="669d1-150">To edit the button template, right-click the button and select **Edit Control Parts (Template)** and then **Edit Template**.</span></span>

    ![テンプレートを編集する方法](./media/custom-button-blend-edittemplate.jpg)

    <span data-ttu-id="669d1-152">テンプレートエディターで、ボタンが <xref:System.Windows.Shapes.Rectangle> と <xref:System.Windows.Controls.ContentPresenter>に分割されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="669d1-152">In the template editor, notice that the button is now separated into a <xref:System.Windows.Shapes.Rectangle> and the <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="669d1-153"><xref:System.Windows.Controls.ContentPresenter> は、ボタン内にコンテンツを表示するために使用されます (たとえば、文字列 "Button")。</span><span class="sxs-lookup"><span data-stu-id="669d1-153">The <xref:System.Windows.Controls.ContentPresenter> is used to present content within the button (for example, the string "Button").</span></span> <span data-ttu-id="669d1-154">四角形と <xref:System.Windows.Controls.ContentPresenter> の両方が <xref:System.Windows.Controls.Grid>内にレイアウトされます。</span><span class="sxs-lookup"><span data-stu-id="669d1-154">Both the rectangle and <xref:System.Windows.Controls.ContentPresenter> are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ![四角形で表したコンポーネント](./media/custom-button-blend-templatepanel.png)

2. <span data-ttu-id="669d1-156">**テンプレートコンポーネントの名前を変更します。** テンプレートインベントリ内の四角形を右クリックし、<xref:System.Windows.Shapes.Rectangle> 名を "[四角形]" から "outerRectangle" に変更し、"[ContentPresenter]" を "myContentPresenter" に変更します。</span><span class="sxs-lookup"><span data-stu-id="669d1-156">**Change the names of the template components:** Right-click the rectangle in the template inventory, change the <xref:System.Windows.Shapes.Rectangle> name from "[Rectangle]" to "outerRectangle", and change "[ContentPresenter]" to "myContentPresenter".</span></span>

    ![テンプレートのコンポーネント名を変更する方法](./media/custom-button-blend-renamecomponents.png)

3. <span data-ttu-id="669d1-158">**(ドーナツのように) 内側に空になるように四角形を変更します。** **OuterRectangle**を選択し、<xref:System.Windows.Shapes.Shape.Fill%2A> を "Transparent" に、<xref:System.Windows.Shapes.Shape.StrokeThickness%2A> を5に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-158">**Alter the rectangle so that it is empty inside (like a donut):** Select **outerRectangle** and set <xref:System.Windows.Shapes.Shape.Fill%2A> to "Transparent" and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> to 5.</span></span>

    ![四角形を空にする方法](./media/custom-button-blend-changerectproperties.png)

    <span data-ttu-id="669d1-160">次に、<xref:System.Windows.Shapes.Shape.Stroke%2A> を、テンプレートのすべての色に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-160">Then set the <xref:System.Windows.Shapes.Shape.Stroke%2A> to the color of whatever the template will be.</span></span> <span data-ttu-id="669d1-161">これを行うには、 **[ストローク]** の横にある小さな白いボックスをクリックし、 **[customexpression]** を選択して、ダイアログボックスに「{TemplateBinding Background}」と入力します。</span><span class="sxs-lookup"><span data-stu-id="669d1-161">To do this, click the small white box next to **Stroke**, select **CustomExpression**, and type "{TemplateBinding Background}" in the dialog box.</span></span>

    ![テンプレートの色の使用を設定する方法](./media/custom-button-blend-templatestroke.png)

4. <span data-ttu-id="669d1-163">**内部の四角形を作成します。** 次に、別の四角形を作成し ("innerRectangle" という名前を指定)、 **outerRectangle**の内部に対称的に配置します。</span><span class="sxs-lookup"><span data-stu-id="669d1-163">**Create an inner rectangle:** Now, create another rectangle (name it "innerRectangle") and position it symmetrically on the inside of **outerRectangle** .</span></span> <span data-ttu-id="669d1-164">このような作業では、ズームして、編集領域のボタンのサイズを大きくすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="669d1-164">For this kind of work, you will probably want to zoom to make the button larger in the editing area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="669d1-165">四角形は、図の場合とは異なる場合があります (たとえば、角が丸くなる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="669d1-165">Your rectangle might look different than the one in the figure (for example, it might have rounded corners).</span></span>

    ![別の四角形の中に四角形を作成する方法](./media/custom-button-blend-innerrectangleproperties.png)

5. <span data-ttu-id="669d1-167">**ContentPresenter を一番上に移動します。** この時点で、テキスト "Button" が表示されなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="669d1-167">**Move ContentPresenter to the top:** At this point, it is possible that the text "Button" will not be visible any longer.</span></span> <span data-ttu-id="669d1-168">これが原因である場合、これは、 **Innerrectangle**が**myContentPresenter**の上にあるためです。</span><span class="sxs-lookup"><span data-stu-id="669d1-168">If this is so, this is because **innerRectangle** is on top of the **myContentPresenter**.</span></span> <span data-ttu-id="669d1-169">これを修正するには、 **myContentPresenter**を**innerrectangle**の下にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="669d1-169">To fix this, drag **myContentPresenter** below **innerRectangle**.</span></span> <span data-ttu-id="669d1-170">四角形と**myContentPresenter**の位置を変更して、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="669d1-170">Reposition rectangles and **myContentPresenter** to look similar to below.</span></span>

    > [!NOTE]
    > <span data-ttu-id="669d1-171">または、 **myContentPresenter**を右クリックして **[Send Forward]** をクリックして、上に配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="669d1-171">Alternatively, you can also position **myContentPresenter** on top by right-clicking it and pressing **Send Forward**.</span></span>

    ![別のボタンの上にボタンを移動する方法](./media/custom-button-blend-innerrectangle2.png)

6. <span data-ttu-id="669d1-173">**InnerRectangle の外観を変更します。** <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>、<xref:System.Windows.Shapes.Rectangle.RadiusY%2A>、および <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> の値を20に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-173">**Change the look of innerRectangle:** Set the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>, <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> values to 20.</span></span> <span data-ttu-id="669d1-174">さらに、カスタム式 "{TemplateBinding Background}" を使用して、テンプレートの背景に <xref:System.Windows.Shapes.Shape.Fill%2A> を設定し、<xref:System.Windows.Shapes.Shape.Stroke%2A> を "transparent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-174">In addition, set the <xref:System.Windows.Shapes.Shape.Fill%2A> to the background of the template using the custom expression "{TemplateBinding Background}" ) and set <xref:System.Windows.Shapes.Shape.Stroke%2A> to "transparent".</span></span> <span data-ttu-id="669d1-175">**Innerrectangle**の <xref:System.Windows.Shapes.Shape.Fill%2A> と <xref:System.Windows.Shapes.Shape.Stroke%2A> の設定は、 **outerRectangle**の設定とは逆になっていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="669d1-175">Notice that the settings for the <xref:System.Windows.Shapes.Shape.Fill%2A> and <xref:System.Windows.Shapes.Shape.Stroke%2A> of **innerRectangle** are the opposite of those for **outerRectangle**.</span></span>

    ![四角形の外観を変更する方法](./media/custom-button-blend-glassrectangleproperties1.png)

7. <span data-ttu-id="669d1-177">**グラスレイヤーを上に追加します。** ボタンの外観をカスタマイズする最後の部分は、ガラスレイヤーを上部に追加することです。</span><span class="sxs-lookup"><span data-stu-id="669d1-177">**Add a glass layer on top:** The final piece of customizing the look of the button is to add a glass layer on top.</span></span> <span data-ttu-id="669d1-178">このグラスレイヤーは、3番目の四角形で構成されています。</span><span class="sxs-lookup"><span data-stu-id="669d1-178">This glass layer consists of a third rectangle.</span></span> <span data-ttu-id="669d1-179">グラスではボタン全体が表示されるので、ガラスの四角形は**outerRectangle**のような大きさに似ています。</span><span class="sxs-lookup"><span data-stu-id="669d1-179">Because the glass will cover the entire button, the glass rectangle is similar in dimensions to the **outerRectangle**.</span></span> <span data-ttu-id="669d1-180">そのため、 **outerRectangle**のコピーを作成するだけで、四角形を作成できます。</span><span class="sxs-lookup"><span data-stu-id="669d1-180">Therefore, create the rectangle by simply making a copy of the **outerRectangle**.</span></span> <span data-ttu-id="669d1-181">**OuterRectangle**を強調表示し、Ctrl + C キーと Ctrl + V キーを使用してコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="669d1-181">Highlight **outerRectangle** and use CTRL+C and CTRL+V to make a copy.</span></span> <span data-ttu-id="669d1-182">この新しい四角形に "glassCube" という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-182">Name this new rectangle "glassCube".</span></span>

8. <span data-ttu-id="669d1-183">**必要に応じて glassCube の位置を変更します。** **GlassCube**がボタン全体をカバーするように配置されていない場合は、その位置にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="669d1-183">**Reposition glassCube if necessary:** If **glassCube** is not already positioned so that it covers the entire button, drag it into position.</span></span>

9. <span data-ttu-id="669d1-184">**GlassCube は、outerRectangle とは少し異なる形で指定します。** **GlassCube**のプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="669d1-184">**Give glassCube a slightly different shape than outerRectangle:** Change the properties of **glassCube**.</span></span> <span data-ttu-id="669d1-185">まず、<xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> のプロパティを10に変更し、<xref:System.Windows.Shapes.Shape.StrokeThickness%2A> を2に変更します。</span><span class="sxs-lookup"><span data-stu-id="669d1-185">Start off by changing the <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties to 10 and the <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> to 2.</span></span>

    ![glassCube の外観設定](./media/custom-button-blend-glasscubeappearance.gif)

10. <span data-ttu-id="669d1-187">**GlassCube をガラスのように表示します。** 透明度が75% である線状グラデーションを使用して、<xref:System.Windows.Shapes.Shape.Fill%2A> を glassy に設定します。線形グラデーションの色は白で、透明度は約均等に6分間隔で透明です。</span><span class="sxs-lookup"><span data-stu-id="669d1-187">**Make glassCube look like glass:** Set the <xref:System.Windows.Shapes.Shape.Fill%2A> to a glassy look by  using a linear gradient that is 75% opaque and alternates between the color White and Transparent over 6 approximately evenly spaced intervals.</span></span> <span data-ttu-id="669d1-188">次に、グラデーションの分岐点を設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="669d1-188">This is what to set the gradient stops to:</span></span>

    - <span data-ttu-id="669d1-189">グラデーションの分岐点 1: アルファ値が75% の白</span><span class="sxs-lookup"><span data-stu-id="669d1-189">Gradient Stop 1: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="669d1-190">グラデーションの分岐点 2: 透明</span><span class="sxs-lookup"><span data-stu-id="669d1-190">Gradient Stop 2: Transparent</span></span>

    - <span data-ttu-id="669d1-191">グラデーションの分岐点 3: アルファ値が75% の白</span><span class="sxs-lookup"><span data-stu-id="669d1-191">Gradient Stop 3: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="669d1-192">グラデーションの分岐点 4: 透明</span><span class="sxs-lookup"><span data-stu-id="669d1-192">Gradient Stop 4: Transparent</span></span>

    - <span data-ttu-id="669d1-193">グラデーションの分岐点 5: アルファ値が75% の白</span><span class="sxs-lookup"><span data-stu-id="669d1-193">Gradient Stop 5: White with Alpha value of 75%</span></span>

    - <span data-ttu-id="669d1-194">グラデーションの分岐点 6: 透明</span><span class="sxs-lookup"><span data-stu-id="669d1-194">Gradient Stop 6: Transparent</span></span>

    <span data-ttu-id="669d1-195">これにより、"波" グラスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-195">This creates a "wavy" glass look.</span></span>

    ![グラスのような四角形](./media/custom-button-blend-glassrectangleproperties2.png)

11. <span data-ttu-id="669d1-197">**グラスレイヤーを非表示にします。** Glassy レイヤーがどのように見えるかを確認したので、[**プロパティ] パネル**の [**外観] ウィンドウ**に戻り、不透明度を0% に設定して非表示にします。</span><span class="sxs-lookup"><span data-stu-id="669d1-197">**Hide the glass layer:** Now that you see what the glassy layer looks like, go into the **Appearance pane** of the **Properties panel** and set the Opacity to 0% to hide it.</span></span> <span data-ttu-id="669d1-198">前のセクションでは、プロパティトリガーとイベントを使用して、グラスレイヤーを表示および操作します。</span><span class="sxs-lookup"><span data-stu-id="669d1-198">In the sections ahead, we'll use property triggers and events to show and manipulate the glass layer.</span></span>

    ![グラス四角形を非表示にする方法](./media/custom-button-glassrectangleproperties3.gif)

## <a name="customize-the-button-behavior"></a><span data-ttu-id="669d1-200">ボタンの動作をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="669d1-200">Customize the Button Behavior</span></span>

<span data-ttu-id="669d1-201">この時点では、テンプレートを編集してボタンの表示をカスタマイズしていますが、ボタンは通常のボタンとは異なります (たとえば、マウスオーバーでの外観の変更、フォーカスの受け取り、クリックなど)。次の2つの手順では、これらのような動作をカスタムボタンにビルドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="669d1-201">At this point, you have customized the presentation of the button by editing its template, but the button does not react to user actions as typical buttons do (for example, changing appearance upon mouse-over, receiving focus, and clicking.) The next two procedures show how to build behaviors like these into the custom button.</span></span> <span data-ttu-id="669d1-202">単純なプロパティトリガーから始めて、イベントトリガーとアニメーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="669d1-202">We'll start with simple property triggers, and then add event triggers and animations.</span></span>

### <a name="to-set-property-triggers"></a><span data-ttu-id="669d1-203">プロパティトリガーを設定するには</span><span class="sxs-lookup"><span data-stu-id="669d1-203">To set property triggers</span></span>

1. <span data-ttu-id="669d1-204">**新しいプロパティトリガーを作成します。** **GlassCube**を選択した状態で、 **[トリガー]** パネルの **[+ プロパティ]** をクリックします (次の手順に続く図を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="669d1-204">**Create a new property trigger:** With **glassCube** selected, click **+ Property** in the **Triggers** panel (see the figure that follows the next step).</span></span> <span data-ttu-id="669d1-205">これにより、既定のプロパティトリガーを持つプロパティトリガーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-205">This creates a property trigger with a default property trigger.</span></span>

2. <span data-ttu-id="669d1-206">**トリガーによって使用されるプロパティを次のように設定します。** プロパティを <xref:System.Windows.UIElement.IsMouseOver%2A>に変更します。</span><span class="sxs-lookup"><span data-stu-id="669d1-206">**Make IsMouseOver the property used by the trigger:** Change the property to <xref:System.Windows.UIElement.IsMouseOver%2A>.</span></span> <span data-ttu-id="669d1-207">これにより、<xref:System.Windows.UIElement.IsMouseOver%2A> プロパティが `true` 場合 (ユーザーがマウスでボタンをポイントしたとき) に、プロパティトリガーがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="669d1-207">This makes the property trigger activate when the <xref:System.Windows.UIElement.IsMouseOver%2A> property is `true` (when the user points to the button with the mouse).</span></span>

    ![プロパティでトリガーを設定する方法](./media/custom-button-blend-ismousedoverpropertytrigger.png)

3. <span data-ttu-id="669d1-209">**GlassCube の ismouseover トリガーの100% の不透明度。** **トリガーの記録がオンになっ**ていることに注意してください (前の図を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="669d1-209">**IsMouseOver triggers opacity of 100% for glassCube:** Notice that the **Trigger recording is on** (see the preceding figure).</span></span> <span data-ttu-id="669d1-210">つまり、記録中に**glassCube**のプロパティ値に加えた変更は、<xref:System.Windows.UIElement.IsMouseOver%2A> が `true`たときに実行されるアクションになります。</span><span class="sxs-lookup"><span data-stu-id="669d1-210">This means that any changes you make to the property values of **glassCube** while recording is on will become an action that takes place when <xref:System.Windows.UIElement.IsMouseOver%2A> is `true`.</span></span> <span data-ttu-id="669d1-211">記録中に、 **glassCube**の <xref:System.Windows.UIElement.Opacity%2A> を100% に変更します。</span><span class="sxs-lookup"><span data-stu-id="669d1-211">While recording, change the <xref:System.Windows.UIElement.Opacity%2A> of **glassCube** to 100%.</span></span>

    ![ボタンの不透明度を設定する方法](./media/custom-button-blend-ismousedoverpropertytrigger2.gif)

    <span data-ttu-id="669d1-213">これで、最初のプロパティトリガーが作成されました。</span><span class="sxs-lookup"><span data-stu-id="669d1-213">You have now created your first property trigger.</span></span> <span data-ttu-id="669d1-214">エディターの [**トリガー] パネル**に、100% に変更された <xref:System.Windows.UIElement.Opacity%2A> が記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="669d1-214">Notice that the **Triggers panel** of the editor has recorded the <xref:System.Windows.UIElement.Opacity%2A> being changed to 100%.</span></span>

    ![[トリガー] パネル](./media/custom-button-blend-propertytriggerinfo.png)

    <span data-ttu-id="669d1-216">F5 キーを押してアプリケーションを実行し、マウスポインターをボタンの上または下に移動します。</span><span class="sxs-lookup"><span data-stu-id="669d1-216">Press F5 to run the application, and move the mouse pointer over and off the button.</span></span> <span data-ttu-id="669d1-217">ボタンをマウスでポイントするとグラスレイヤーが表示され、ポインターが離れると消えます。</span><span class="sxs-lookup"><span data-stu-id="669d1-217">You should see the glass layer appear when you mouse-over the button and disappear when the pointer leaves.</span></span>

4. <span data-ttu-id="669d1-218">**Ismouseover トリガーのストローク値の変更:** その他のアクションを <xref:System.Windows.UIElement.IsMouseOver%2A> トリガーに関連付けてみましょう。</span><span class="sxs-lookup"><span data-stu-id="669d1-218">**IsMouseOver triggers stroke value change:** Let's associate some other actions with the <xref:System.Windows.UIElement.IsMouseOver%2A> trigger.</span></span> <span data-ttu-id="669d1-219">記録が続行されたら、選択内容を**glassCube**から**outerRectangle**に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="669d1-219">While recording continues, switch your selection from **glassCube** to **outerRectangle**.</span></span> <span data-ttu-id="669d1-220">次に、 **outerRectangle**の <xref:System.Windows.Shapes.Shape.Stroke%2A> を "{dynamicresource {HighlightBrushKey}}" のカスタム式に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-220">Then set the <xref:System.Windows.Shapes.Shape.Stroke%2A> of **outerRectangle** to the custom expression of "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}".</span></span> <span data-ttu-id="669d1-221">これにより、<xref:System.Windows.Shapes.Shape.Stroke%2A> がボタンによって使用される一般的な強調表示色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-221">This sets the <xref:System.Windows.Shapes.Shape.Stroke%2A> to the typical highlight color used by buttons.</span></span> <span data-ttu-id="669d1-222">F5 キーを押して、ボタンの上にマウスを置いたときの効果を確認します。</span><span class="sxs-lookup"><span data-stu-id="669d1-222">Press F5 to see the effect when you mouse over the button.</span></span>

    ![ストロークを強調表示色に設定する方法](./media/custom-button-blend-ismousedoverpropertytrigger3.png)

5. <span data-ttu-id="669d1-224">**Ismouseover トリガーがぼやけたテキスト:** 1つ以上のアクションを <xref:System.Windows.UIElement.IsMouseOver%2A> プロパティトリガーに関連付けてみましょう。</span><span class="sxs-lookup"><span data-stu-id="669d1-224">**IsMouseOver triggers blurry text:** Let's associate one more action to the <xref:System.Windows.UIElement.IsMouseOver%2A> property trigger.</span></span> <span data-ttu-id="669d1-225">ボタンの上にグラスが表示されているときに、ボタンの内容が少しぼやけて表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="669d1-225">Make the content of the button appear a little blurry when the glass appears over it.</span></span> <span data-ttu-id="669d1-226">これを行うには、<xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**) にぼかし <xref:System.Windows.Media.Effects.BitmapEffect> を適用します。</span><span class="sxs-lookup"><span data-stu-id="669d1-226">To do this, we can apply a blur <xref:System.Windows.Media.Effects.BitmapEffect> to the <xref:System.Windows.Controls.ContentPresenter> (**myContentPresenter**).</span></span>

    ![ボタンの内容をぼかす方法](./media/custom-button-blend-propertytriggerwithbitmapeffect.png)

    > [!NOTE]
    > <span data-ttu-id="669d1-228">[**プロパティ] パネル**を <xref:System.Windows.Media.Effects.BitmapEffect>検索を実行する前の値に戻すには、**検索ボックス**のテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="669d1-228">To return the **Properties panel** back to what it was before you did the search for <xref:System.Windows.Media.Effects.BitmapEffect>, clear the text from the **Search box**.</span></span>

    <span data-ttu-id="669d1-229">この時点で、いくつかの関連するアクションを含むプロパティトリガーを使用して、マウスポインターがボタン領域に出入りするときの強調表示動作を作成しました。</span><span class="sxs-lookup"><span data-stu-id="669d1-229">At this point, we have used a property trigger with several associated actions to create highlighting behavior for when the mouse pointer enters and leaves the button area.</span></span> <span data-ttu-id="669d1-230">ボタンのもう1つの一般的な動作は、フォーカスがあるときに強調表示されます (クリックされた後)。</span><span class="sxs-lookup"><span data-stu-id="669d1-230">Another typical behavior for a button is to highlight when it has focus (as after it is clicked).</span></span> <span data-ttu-id="669d1-231">このような動作を追加するには、<xref:System.Windows.UIElement.IsFocused%2A> プロパティに別のプロパティトリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="669d1-231">We can add such behavior by adding another property trigger for the <xref:System.Windows.UIElement.IsFocused%2A> property.</span></span>

6. <span data-ttu-id="669d1-232">**IsFocused のプロパティトリガーを作成します。** <xref:System.Windows.UIElement.IsMouseOver%2A> の場合と同じ手順 (このセクションの最初の手順を参照) を使用して、<xref:System.Windows.UIElement.IsFocused%2A> プロパティのプロパティトリガーをもう1つ作成します。</span><span class="sxs-lookup"><span data-stu-id="669d1-232">**Create property trigger for IsFocused:** Using the same procedure as for <xref:System.Windows.UIElement.IsMouseOver%2A> (see the first step of this section), create another property trigger for the <xref:System.Windows.UIElement.IsFocused%2A> property.</span></span> <span data-ttu-id="669d1-233">**トリガーの記録がオンになって**いる間に、次のアクションをトリガーに追加します。</span><span class="sxs-lookup"><span data-stu-id="669d1-233">While **Trigger recording is on**, add the following actions to the trigger:</span></span>

    - <span data-ttu-id="669d1-234">**glassCube**は100% の <xref:System.Windows.UIElement.Opacity%2A> を取得します。</span><span class="sxs-lookup"><span data-stu-id="669d1-234">**glassCube** gets an <xref:System.Windows.UIElement.Opacity%2A> of 100%.</span></span>

    - <span data-ttu-id="669d1-235">**outerRectangle**は、"{dynamicresource {HighlightBrushKey}}" という <xref:System.Windows.Shapes.Shape.Stroke%2A> カスタム式の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="669d1-235">**outerRectangle** gets a <xref:System.Windows.Shapes.Shape.Stroke%2A> custom expression value of "{DynamicResource {x:Static SystemColors.HighlightBrushKey}}".</span></span>

<span data-ttu-id="669d1-236">このチュートリアルの最後の手順として、アニメーションをボタンに追加します。</span><span class="sxs-lookup"><span data-stu-id="669d1-236">As the final step in this walkthrough, we will add animations to the button.</span></span> <span data-ttu-id="669d1-237">これらのアニメーションは、イベント (具体的には、<xref:System.Windows.UIElement.MouseEnter> イベントと <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントによってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="669d1-237">These animations will be triggered by events—specifically, the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events.</span></span>

### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a><span data-ttu-id="669d1-238">イベントトリガーとアニメーションを使用して対話機能を追加するには</span><span class="sxs-lookup"><span data-stu-id="669d1-238">To use event triggers and animations to add interactivity</span></span>

1. <span data-ttu-id="669d1-239">**MouseEnter イベントトリガーを作成します。** 新しいイベントトリガーを追加し、トリガーで使用するイベントとして [<xref:System.Windows.UIElement.MouseEnter>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="669d1-239">**Create a MouseEnter Event Trigger:** Add a new event trigger and select <xref:System.Windows.UIElement.MouseEnter> as the event to use in the trigger.</span></span>

     ![MouseEnter イベント トリガーを作成する方法](./media/custom-button-blend-mouseovereventtrigger.png)

2. <span data-ttu-id="669d1-241">**アニメーションタイムラインを作成します。** 次に、アニメーションタイムラインを <xref:System.Windows.UIElement.MouseEnter> イベントに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="669d1-241">**Create an animation timeline:** Next, associate an animation timeline to the <xref:System.Windows.UIElement.MouseEnter> event.</span></span>

    ![アニメーション タイムラインをイベントに追加する方法](./media/custom-button-blend-mouseovereventtrigger2.png)

    <span data-ttu-id="669d1-243">**[OK]** をクリックして新しいタイムラインを作成すると、[タイムライン **] パネル**が表示され、[タイムラインの記録がオンになっています] がデザインパネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-243">After you press **OK** to create a new timeline, a **Timeline Panel** appears and "Timeline recording is on" is visible in the design panel.</span></span> <span data-ttu-id="669d1-244">これは、タイムラインでプロパティの変更の記録を開始できることを意味します (プロパティの変更をアニメーション化します)。</span><span class="sxs-lookup"><span data-stu-id="669d1-244">This means we can start recording property changes in the timeline (animate property changes).</span></span>

    > [!NOTE]
    > <span data-ttu-id="669d1-245">画面を表示するには、ウィンドウやパネルのサイズを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="669d1-245">You may need to resize your window and/or panels to see the display.</span></span>

    ![タイムライン パネル](./media/custom-button-blend-mouseovereventtrigger3.png)

3. <span data-ttu-id="669d1-247">**キーフレームを作成します。** アニメーションを作成するには、アニメーション化するオブジェクトを選択し、タイムライン上に複数のキーフレームを作成します。これらのキーフレームについては、アニメーションで補間するプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-247">**Create a keyframe:** To create an animation, select the object you want to animate, create two or more keyframes on the timeline, and for those keyframes, set the property values you want the animation to interpolate between.</span></span> <span data-ttu-id="669d1-248">次の図は、キーフレームを作成する手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="669d1-248">The following figure guides you through the creation of a keyframe.</span></span>

    ![キーフレームを作成する方法](./media/custom-button-blend-mouseovereventtrigger4.png)

4. <span data-ttu-id="669d1-250">**このキーフレームで glassCube を圧縮します。** 2番目のキーフレームを選択した状態で、**サイズ変換**を使用して、 **glassCube**のサイズを完全なサイズの90% に縮小します。</span><span class="sxs-lookup"><span data-stu-id="669d1-250">**Shrink glassCube at this keyframe:** With the second keyframe selected, shrink the size of the **glassCube** to 90% of its full size using the **Size Transform**.</span></span>

    ![ボタンのサイズを縮小する方法](./media/custom-button-blend-sizetransform.png)

    <span data-ttu-id="669d1-252">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="669d1-252">Press F5 to run the application.</span></span> <span data-ttu-id="669d1-253">マウスポインターをボタンの上に移動します。</span><span class="sxs-lookup"><span data-stu-id="669d1-253">Move the mouse pointer over the button.</span></span> <span data-ttu-id="669d1-254">グラスレイヤーがボタンの上に縮小されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="669d1-254">Notice that the glass layer shrinks on top of the button.</span></span>

5. <span data-ttu-id="669d1-255">**別のイベントトリガーを作成し、別のアニメーションを関連付けます。** もう1つアニメーションを追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="669d1-255">**Create another Event Trigger and associate a different animation with it:** Let's add one more animation.</span></span> <span data-ttu-id="669d1-256">前のイベントトリガーアニメーションの作成に使用したものと同様の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="669d1-256">Use a similar procedure to what you used to create the previous event trigger animation:</span></span>

    1. <span data-ttu-id="669d1-257"><xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントを使用して、新しいイベントトリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="669d1-257">Create a new event trigger using the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>

    2. <span data-ttu-id="669d1-258">新しいタイムラインを <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="669d1-258">Associate a new timeline with the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>

        ![新しいタイムラインを作成する方法](./media/custom-button-blend-clickeventtrigger1.png)

    3. <span data-ttu-id="669d1-260">このタイムラインでは、2つのキーフレームを作成します。1つは0.0 秒、2番目は0.3 秒です。</span><span class="sxs-lookup"><span data-stu-id="669d1-260">For this timeline, create two keyframes, one at 0.0 seconds and the second one at 0.3 seconds.</span></span>

    4. <span data-ttu-id="669d1-261">キーフレームが0.3 秒で強調表示されている状態で、**回転変換の角度**を360度に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-261">With the keyframe at 0.3 seconds highlighted, set the **Rotate Transform Angle** to 360 degrees.</span></span>

        ![回転変換を作成する方法](./media/custom-button-blend-rotatetransform.gif)

    5. <span data-ttu-id="669d1-263">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="669d1-263">Press F5 to run the application.</span></span> <span data-ttu-id="669d1-264">ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="669d1-264">Click the button.</span></span> <span data-ttu-id="669d1-265">グラスレイヤーが回転していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="669d1-265">Notice that the glass layer spins around.</span></span>

## <a name="conclusion"></a><span data-ttu-id="669d1-266">結論</span><span class="sxs-lookup"><span data-stu-id="669d1-266">Conclusion</span></span>

<span data-ttu-id="669d1-267">カスタマイズしたボタンを完了しました。</span><span class="sxs-lookup"><span data-stu-id="669d1-267">You have completed a customized button.</span></span> <span data-ttu-id="669d1-268">これを行うには、アプリケーションのすべてのボタンに適用されたボタンテンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="669d1-268">You did this using a button template that was applied to all buttons in the application.</span></span> <span data-ttu-id="669d1-269">テンプレート編集モードをそのままにした場合 (次の図を参照してください)、さらにボタンを作成すると、既定のボタンのようにではなく、カスタムボタンのような外観と動作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-269">If you leave the template editing mode (see the following figure) and create more buttons, you will see that they look and behave like your custom button rather than like the default button.</span></span>

![カスタムボタンテンプレート](./media/custom-button-blend-scopeup.gif)

![同じテンプレートを使用する複数のボタン](./media/custom-button-blend-createmultiplebuttons.png)

<span data-ttu-id="669d1-272">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="669d1-272">Press F5 to run the application.</span></span> <span data-ttu-id="669d1-273">ボタンをクリックして、すべての動作が同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="669d1-273">Click the buttons and notice how they all behave the same.</span></span>

<span data-ttu-id="669d1-274">テンプレートをカスタマイズしている間は、 **Innerrectangle**の <xref:System.Windows.Shapes.Shape.Fill%2A> プロパティと <xref:System.Windows.Shapes.Shape.Stroke%2A> プロパティ**outerRectangle**をテンプレートの背景 ({TemplateBinding background}) に設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-274">Remember that while you were customizing the template, you set the <xref:System.Windows.Shapes.Shape.Fill%2A> property of **innerRectangle** and the <xref:System.Windows.Shapes.Shape.Stroke%2A> property **outerRectangle** to the template background ({TemplateBinding Background}).</span></span> <span data-ttu-id="669d1-275">このため、個々のボタンの背景色を設定すると、設定した背景がそれぞれのプロパティに使用されます。</span><span class="sxs-lookup"><span data-stu-id="669d1-275">Because of this, when you set the background color of the individual buttons, the background you set will be used for those respective properties.</span></span> <span data-ttu-id="669d1-276">今すぐ背景を変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="669d1-276">Try changing the backgrounds now.</span></span> <span data-ttu-id="669d1-277">次の図では、さまざまなグラデーションが使用されています。</span><span class="sxs-lookup"><span data-stu-id="669d1-277">In the following figure, different gradients are used.</span></span> <span data-ttu-id="669d1-278">したがって、テンプレートはボタンのようなコントロールを全体的にカスタマイズするのに役立ちますが、テンプレートを持つコントロールは、互いに異なる外観に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="669d1-278">Therefore, although a template is useful for overall customization of controls like button, controls with templates can still be modified to look different from each other.</span></span>

<span data-ttu-id="669d1-279">![外観のような同じテンプレートを持つボタン](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")</span><span class="sxs-lookup"><span data-stu-id="669d1-279">![Buttons with the same template that look diferent](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")</span></span>

<span data-ttu-id="669d1-280">結論として、ボタンテンプレートをカスタマイズするプロセスでは、Microsoft Expression Blend で次の操作を行う方法を学習しました。</span><span class="sxs-lookup"><span data-stu-id="669d1-280">In conclusion, in the process of customizing a button template you have learned how to do the following in Microsoft Expression Blend:</span></span>

- <span data-ttu-id="669d1-281">コントロールの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="669d1-281">Customize the look of a control.</span></span>

- <span data-ttu-id="669d1-282">プロパティトリガーを設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-282">Set property triggers.</span></span> <span data-ttu-id="669d1-283">プロパティトリガーは、コントロールだけでなく、ほとんどのオブジェクトで使用できるため、非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="669d1-283">Property triggers are very useful because they can be used on most objects, not just controls.</span></span>

- <span data-ttu-id="669d1-284">イベントトリガーを設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-284">Set event triggers.</span></span> <span data-ttu-id="669d1-285">イベントトリガーは、コントロールだけでなく、ほとんどのオブジェクトで使用できるため、非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="669d1-285">Event triggers are very useful because they can be used on most objects, not just controls.</span></span>

- <span data-ttu-id="669d1-286">アニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="669d1-286">Create animations.</span></span>

- <span data-ttu-id="669d1-287">その他: グラデーションを作成し、BitmapEffects を追加し、変換を使用して、オブジェクトの基本プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="669d1-287">Miscellaneous: create gradients, add BitmapEffects, use transforms, and set basic properties of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="669d1-288">関連項目</span><span class="sxs-lookup"><span data-stu-id="669d1-288">See also</span></span>

- [<span data-ttu-id="669d1-289">XAML を使用したボタンの作成</span><span class="sxs-lookup"><span data-stu-id="669d1-289">Create a Button by Using XAML</span></span>](walkthrough-create-a-button-by-using-xaml.md)
- [<span data-ttu-id="669d1-290">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="669d1-290">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="669d1-291">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="669d1-291">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="669d1-292">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="669d1-292">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="669d1-293">ビットマップ効果の概要</span><span class="sxs-lookup"><span data-stu-id="669d1-293">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
