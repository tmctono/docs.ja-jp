---
title: 'チュートリアル: WPF コンテンツへのスタイルの適用'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d0aa2c54f05cea658c95dc2c23b7ba4bb78835c9
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138930"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="0daca-102">チュートリアル: WPF コンテンツのスタイルを適用する</span><span class="sxs-lookup"><span data-stu-id="0daca-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="0daca-103">この記事では、Windows フォームでホストされている Windows Presentation Foundation (WPF) コントロールにスタイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0daca-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0daca-104">必要条件</span><span class="sxs-lookup"><span data-stu-id="0daca-104">Prerequisites</span></span>

<span data-ttu-id="0daca-105">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="0daca-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="0daca-106">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="0daca-106">Create the project</span></span>

<span data-ttu-id="0daca-107">Visual Studio を開き、Visual Basic または `StylingWpfContent`C#という名前の新しい Windows フォームアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0daca-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="0daca-108">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0daca-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="0daca-109">WPF コントロール型を作成する</span><span class="sxs-lookup"><span data-stu-id="0daca-109">Create the WPF control types</span></span>

<span data-ttu-id="0daca-110">プロジェクトに追加した WPF コントロール型は、<xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストできます。</span><span class="sxs-lookup"><span data-stu-id="0daca-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="0daca-111">新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="0daca-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="0daca-112">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="0daca-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="0daca-113">詳細については、「[チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0daca-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="0daca-114">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0daca-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="0daca-115">**[プロパティ]** ウィンドウで、<xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> のプロパティの値を**200**に設定します。</span><span class="sxs-lookup"><span data-stu-id="0daca-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="0daca-116"><xref:System.Windows.Controls.UserControl> に <xref:System.Windows.Controls.Button?displayProperty=nameWithType> コントロールを追加し、<xref:System.Windows.Controls.ContentControl.Content%2A> プロパティの値を**Cancel**に設定します。</span><span class="sxs-lookup"><span data-stu-id="0daca-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="0daca-117">2つ目の <xref:System.Windows.Controls.Button?displayProperty=nameWithType> コントロールを <xref:System.Windows.Controls.UserControl> に追加し、<xref:System.Windows.Controls.ContentControl.Content%2A> プロパティの値を**OK**に設定します。</span><span class="sxs-lookup"><span data-stu-id="0daca-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="0daca-118">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0daca-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="0daca-119">WPF コントロールへのスタイルの適用</span><span class="sxs-lookup"><span data-stu-id="0daca-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="0daca-120">さまざまなスタイルを WPF コントロールに適用することで、外観や動作を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="0daca-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="0daca-121">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="0daca-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="0daca-122">**ツールボックス**の [`UserControl1`] をダブルクリックして、フォームに `UserControl1` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0daca-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="0daca-123">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="0daca-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="0daca-124">`elementHost1`のスマートタグパネルで、ドロップダウンリストから [ホストされている**コンテンツの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0daca-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="0daca-125">WPF デザイナーで `UserControl1` が開きます。</span><span class="sxs-lookup"><span data-stu-id="0daca-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="0daca-126">XAML ビューで、次の XAML を `<UserControl>` の開始タグの後に挿入します。</span><span class="sxs-lookup"><span data-stu-id="0daca-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="0daca-127">この XAML は、明暗のあるグラデーション境界を持つグラデーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0daca-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="0daca-128">このコントロールをクリックすると、グラデーションが変わり、ボタンを押したような外観が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0daca-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="0daca-129">詳しくは、「 [スタイルとテンプレート](../../../desktop-wpf/fundamentals/styles-templates-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0daca-129">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

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

1. <span data-ttu-id="0daca-130">**[キャンセル**] ボタンの `<Button>` タグに次の XAML を挿入して、前の手順で定義した `SimpleButton` スタイルを [キャンセル] ボタンに適用します。</span><span class="sxs-lookup"><span data-stu-id="0daca-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="0daca-131">ボタン宣言は、次の XAML のようになります。</span><span class="sxs-lookup"><span data-stu-id="0daca-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="0daca-132">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0daca-132">Build the project.</span></span>

1. <span data-ttu-id="0daca-133">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="0daca-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="0daca-134">新しいスタイルが Button コントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0daca-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="0daca-135">**[デバッグ]** メニューの **[デバッグ開始]** をクリックして、アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0daca-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="0daca-136">[ **OK]** ボタンと **[キャンセル**] ボタンをクリックして、相違点を確認します。</span><span class="sxs-lookup"><span data-stu-id="0daca-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="0daca-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="0daca-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0daca-138">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="0daca-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="0daca-139">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="0daca-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="0daca-140">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="0daca-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="0daca-141">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="0daca-141">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="0daca-142">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0daca-142">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
