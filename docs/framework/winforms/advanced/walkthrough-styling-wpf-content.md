---
title: 'チュートリアル: WPF コンテンツへのスタイルの適用'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: d815311a89ba09ade7e3092ca4eeab67cbe20bd0
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211260"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="bc790-102">チュートリアル: WPF コンテンツのスタイル</span><span class="sxs-lookup"><span data-stu-id="bc790-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="bc790-103">このチュートリアルでは、Windows フォームでホストされている Windows Presentation Foundation (WPF) コントロールにスタイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc790-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="bc790-104">このチュートリアルでは次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="bc790-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="bc790-105">プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc790-105">Create the project.</span></span>

- <span data-ttu-id="bc790-106">WPF コントロール型を作成します。</span><span class="sxs-lookup"><span data-stu-id="bc790-106">Create the WPF control type.</span></span>

- <span data-ttu-id="bc790-107">WPF control.a にスタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="bc790-107">Apply a style to the WPF control.a</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc790-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc790-108">Prerequisites</span></span>

<span data-ttu-id="bc790-109">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="bc790-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="bc790-110">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="bc790-110">Create the project</span></span>

<span data-ttu-id="bc790-111">Visual Studio を開き、Visual Basic または Visual で新しい Windows フォーム アプリケーション プロジェクトを作成C#という`StylingWpfContent`します。</span><span class="sxs-lookup"><span data-stu-id="bc790-111">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="bc790-112">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="bc790-112">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="bc790-113">WPF コントロール型を作成します。</span><span class="sxs-lookup"><span data-stu-id="bc790-113">Create the WPF control types</span></span>

<span data-ttu-id="bc790-114">プロジェクトに追加した WPF コントロール型は、<xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストできます。</span><span class="sxs-lookup"><span data-stu-id="bc790-114">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="bc790-115">新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="bc790-115">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="bc790-116">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc790-116">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="bc790-117">詳細については、「[チュートリアル:デザイン時に Windows フォームで新しい WPF コンテンツを作成する](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc790-117">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="bc790-118">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc790-118">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="bc790-119">詳細については、「[方法 :選択し、デザイン サーフェイス上の要素の移動](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="bc790-119">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="bc790-120">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`します。</span><span class="sxs-lookup"><span data-stu-id="bc790-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="bc790-121">追加、<xref:System.Windows.Controls.Button?displayProperty=nameWithType>への制御、<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティを**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="bc790-121">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="bc790-122">1 秒あたりの追加<xref:System.Windows.Controls.Button?displayProperty=nameWithType>コントロールを<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティを**OK**。</span><span class="sxs-lookup"><span data-stu-id="bc790-122">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="bc790-123">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="bc790-123">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="bc790-124">WPF コントロールにスタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="bc790-124">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="bc790-125">さまざまなスタイルを WPF コントロールに適用することで、外観や動作を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="bc790-125">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="bc790-126">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="bc790-126">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="bc790-127">**ツールボックス**、 をダブルクリックします`UserControl1`のインスタンスを作成する`UserControl1`形式にします。</span><span class="sxs-lookup"><span data-stu-id="bc790-127">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="bc790-128">
  `UserControl1\` のインスタンスは、`elementHost1\` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="bc790-128">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="bc790-129">スマート タグ パネルで`elementHost1`、 をクリックして**ホストされているコンテンツの編集**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="bc790-129">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

     <span data-ttu-id="bc790-130">`UserControl1` が [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] で開きます。</span><span class="sxs-lookup"><span data-stu-id="bc790-130">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

4. <span data-ttu-id="bc790-131">XAML ビューで、次の XAML を `<UserControl>` の開始タグの後に挿入します。</span><span class="sxs-lookup"><span data-stu-id="bc790-131">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>

     <span data-ttu-id="bc790-132">この XAML は、明暗のあるグラデーション境界を持つグラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc790-132">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="bc790-133">このコントロールをクリックすると、グラデーションが変わり、ボタンを押したような外観が生成されます。</span><span class="sxs-lookup"><span data-stu-id="bc790-133">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="bc790-134">詳しくは、「 [スタイルとテンプレート](../../wpf/controls/styling-and-templating.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bc790-134">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

4. <span data-ttu-id="bc790-135">[Cancel] ボタンの `<Button>` タグに次の XAML を挿入することで、前の手順で定義した `SimpleButton` スタイルを [Cancel] ボタンに適用します。</span><span class="sxs-lookup"><span data-stu-id="bc790-135">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="bc790-136">ボタン宣言は次の XAML のようになります。</span><span class="sxs-lookup"><span data-stu-id="bc790-136">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

5. <span data-ttu-id="bc790-137">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="bc790-137">Build the project.</span></span>

6. <span data-ttu-id="bc790-138">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="bc790-138">Open `Form1` in the Windows Forms Designer.</span></span>

7. <span data-ttu-id="bc790-139">新しいスタイルが Button コントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc790-139">The new style is applied to the button control.</span></span>

8. <span data-ttu-id="bc790-140">**デバッグ**メニューの [**デバッグの開始]** アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc790-140">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

9. <span data-ttu-id="bc790-141">[OK] ボタンと [Cancel] ボタンをクリックして、違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc790-141">Click the OK and Cancel buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc790-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc790-142">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="bc790-143">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="bc790-143">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="bc790-144">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="bc790-144">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="bc790-145">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="bc790-145">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="bc790-146">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="bc790-146">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="bc790-147">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="bc790-147">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
