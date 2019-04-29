---
title: 'チュートリアル: WPF コンテンツへのスタイルの適用'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 887a157494c2992c1ae5868229c442f31fafb276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781304"
---
# <a name="walkthrough-styling-wpf-content"></a><span data-ttu-id="eb87e-102">チュートリアル: WPF コンテンツへのスタイルの適用</span><span class="sxs-lookup"><span data-stu-id="eb87e-102">Walkthrough: Styling WPF Content</span></span>
<span data-ttu-id="eb87e-103">このチュートリアルでは、Windows フォームでホストされている Windows Presentation Foundation (WPF) コントロールにスタイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="eb87e-104">このチュートリアルでは次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="eb87e-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="eb87e-105">プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-105">Create the project.</span></span>

- <span data-ttu-id="eb87e-106">WPF コントロール型を作成します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-106">Create the WPF control type.</span></span>

- <span data-ttu-id="eb87e-107">WPF コントロールにスタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-107">Apply a style to the WPF control.</span></span>

> [!NOTE]
>  <span data-ttu-id="eb87e-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb87e-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="eb87e-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb87e-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="eb87e-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb87e-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb87e-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="eb87e-111">Prerequisites</span></span>  
 <span data-ttu-id="eb87e-112">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb87e-112">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="eb87e-113">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="eb87e-113">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="eb87e-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="eb87e-114">Creating the Project</span></span>  
 <span data-ttu-id="eb87e-115">まず、Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-115">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb87e-116">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-116">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="eb87e-117">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb87e-117">To create the project</span></span>  
  
- <span data-ttu-id="eb87e-118">`StylingWpfContent` という新しい Windows フォーム アプリケーション プロジェクトを Visual Basic または Visual C# で作成します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-118">Create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="eb87e-119">WPF コントロール型の作成</span><span class="sxs-lookup"><span data-stu-id="eb87e-119">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="eb87e-120">プロジェクトに追加した WPF コントロール型は、<xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストできます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-120">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="eb87e-121">WPF コントロール型を作成するには</span><span class="sxs-lookup"><span data-stu-id="eb87e-121">To create WPF control types</span></span>  
  
1. <span data-ttu-id="eb87e-122">新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-122">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="eb87e-123">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-123">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="eb87e-124">詳細については、「[チュートリアル:デザイン時に Windows フォームで新しい WPF コンテンツを作成する](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-124">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="eb87e-125">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-125">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="eb87e-126">詳細については、「[方法 :選択し、デザイン サーフェイス上の要素の移動](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-126">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="eb87e-127">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-127">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4. <span data-ttu-id="eb87e-128">追加、<xref:System.Windows.Controls.Button?displayProperty=nameWithType>への制御、<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティを**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-128">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>  
  
5. <span data-ttu-id="eb87e-129">1 秒あたりの追加<xref:System.Windows.Controls.Button?displayProperty=nameWithType>コントロールを<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティを**OK**。</span><span class="sxs-lookup"><span data-stu-id="eb87e-129">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>  
  
6. <span data-ttu-id="eb87e-130">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="eb87e-130">Build the project.</span></span>  
  
## <a name="applying-a-style-to-a-wpf-control"></a><span data-ttu-id="eb87e-131">WPF コントロールへのスタイルの適用</span><span class="sxs-lookup"><span data-stu-id="eb87e-131">Applying a Style to a WPF Control</span></span>  
 <span data-ttu-id="eb87e-132">さまざまなスタイルを WPF コントロールに適用することで、外観や動作を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-132">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a><span data-ttu-id="eb87e-133">WPF コントロールにスタイルを適用するには</span><span class="sxs-lookup"><span data-stu-id="eb87e-133">To apply a style to a WPF control</span></span>  
  
1. <span data-ttu-id="eb87e-134">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-134">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="eb87e-135">**ツールボックス**、 をダブルクリックします`UserControl1`のインスタンスを作成する`UserControl1`形式にします。</span><span class="sxs-lookup"><span data-stu-id="eb87e-135">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="eb87e-136">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-136">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3. <span data-ttu-id="eb87e-137">スマート タグ パネルで`elementHost1`、 をクリックして**ホストされているコンテンツの編集**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="eb87e-137">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>  
  
     <span data-ttu-id="eb87e-138">`UserControl1` が [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] で開きます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-138">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4. <span data-ttu-id="eb87e-139">XAML ビューで、次の XAML を `<UserControl>` の開始タグの後に挿入します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-139">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>  
  
     <span data-ttu-id="eb87e-140">この XAML は、明暗のあるグラデーション境界を持つグラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-140">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="eb87e-141">このコントロールをクリックすると、グラデーションが変わり、ボタンを押したような外観が生成されます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-141">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="eb87e-142">詳しくは、「 [スタイルとテンプレート](../../wpf/controls/styling-and-templating.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eb87e-142">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>  
  
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
  
1. <span data-ttu-id="eb87e-143">[Cancel] ボタンの `<Button>` タグに次の XAML を挿入することで、前の手順で定義した `SimpleButton` スタイルを [Cancel] ボタンに適用します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-143">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     <span data-ttu-id="eb87e-144">ボタン宣言は次の XAML のようになります。</span><span class="sxs-lookup"><span data-stu-id="eb87e-144">Your button declaration will resemble the following XAML.</span></span>  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1. <span data-ttu-id="eb87e-145">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="eb87e-145">Build the project.</span></span>  
  
2. <span data-ttu-id="eb87e-146">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-146">Open `Form1` in the Windows Forms Designer.</span></span>  
  
3. <span data-ttu-id="eb87e-147">新しいスタイルが Button コントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="eb87e-147">The new style is applied to the button control.</span></span>  
  
4. <span data-ttu-id="eb87e-148">**デバッグ**メニューの [**デバッグの開始]** アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-148">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>  
  
5. <span data-ttu-id="eb87e-149">[OK] ボタンと [Cancel] ボタンをクリックして、違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb87e-149">Click the OK and Cancel buttons and view the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb87e-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb87e-150">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="eb87e-151">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="eb87e-151">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="eb87e-152">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="eb87e-152">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="eb87e-153">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="eb87e-153">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="eb87e-154">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="eb87e-154">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="eb87e-155">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="eb87e-155">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
