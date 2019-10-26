---
title: 'チュートリアル : XAML を使用したボタンの作成'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a0792beca358de52a24bd9bb0dd48a20c175f8ff
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920185"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="47e13-102">チュートリアル : XAML を使用したボタンの作成</span><span class="sxs-lookup"><span data-stu-id="47e13-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="47e13-103">このチュートリアルの目的は、Windows Presentation Foundation (WPF) アプリケーションで使用するためのアニメーションボタンを作成する方法を学習することです。</span><span class="sxs-lookup"><span data-stu-id="47e13-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="47e13-104">このチュートリアルでは、スタイルとテンプレートを使用して、コードの再利用とボタンのロジックの分離を可能にするカスタマイズされたボタンリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="47e13-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="47e13-105">このチュートリアルは完全に [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]に記述されています。</span><span class="sxs-lookup"><span data-stu-id="47e13-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47e13-106">このチュートリアルでは、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] を入力またはコピーして Visual Studio に貼り付けることによってアプリケーションを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="47e13-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="47e13-107">デザイナーを使用して同じアプリケーションを作成する方法については、「 [Microsoft Expression Blend を使用してボタンを作成](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e13-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="47e13-108">完成したボタンを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="47e13-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="47e13-109">![XAML を使用して作成されたカスタムボタン](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="47e13-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="47e13-110">基本ボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="47e13-110">Create Basic Buttons</span></span>

<span data-ttu-id="47e13-111">まず、新しいプロジェクトを作成し、いくつかのボタンをウィンドウに追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="47e13-112">新しい WPF プロジェクトを作成し、ウィンドウにボタンを追加するには</span><span class="sxs-lookup"><span data-stu-id="47e13-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="47e13-113">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="47e13-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="47e13-114">**新しい WPF プロジェクトを作成します。** **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47e13-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="47e13-115">**Windows アプリケーション (WPF)** テンプレートを探し、プロジェクトに "AnimatedButton" という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="47e13-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="47e13-116">これにより、アプリケーションのスケルトンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="47e13-117">**基本的な既定のボタンを追加します。** このチュートリアルで必要なすべてのファイルは、テンプレートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="47e13-118">ソリューションエクスプローラーでダブルクリックして、Window1.xaml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="47e13-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="47e13-119">既定では、Window1.xaml には <xref:System.Windows.Controls.Grid> 要素があります。</span><span class="sxs-lookup"><span data-stu-id="47e13-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="47e13-120"><xref:System.Windows.Controls.Grid> 要素を削除し、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ページにいくつかのボタンを追加します。そのためには、次の強調表示されているコードを Window1.xaml に入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="47e13-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="47e13-121">F5 キーを押してアプリケーションを実行します。次の図のような一連のボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="47e13-122">![3つの基本的なボタン](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="47e13-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="47e13-123">これで基本的なボタンが作成されたので、Window1.xaml ファイルの作業は終了です。</span><span class="sxs-lookup"><span data-stu-id="47e13-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="47e13-124">このチュートリアルの残りの部分では、app.xaml ファイルに焦点を当てて、ボタンのスタイルとテンプレートを定義します。</span><span class="sxs-lookup"><span data-stu-id="47e13-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="47e13-125">基本プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="47e13-125">Set Basic Properties</span></span>

<span data-ttu-id="47e13-126">次に、ボタンの外観とレイアウトを制御するために、これらのボタンのいくつかのプロパティを設定してみましょう。</span><span class="sxs-lookup"><span data-stu-id="47e13-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="47e13-127">ボタンのプロパティを個別に設定するのではなく、リソースを使用して、アプリケーション全体のボタンプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="47e13-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="47e13-128">アプリケーションリソースは、概念的には Web ページの外部カスケードスタイルシート (CSS) に似ています。ただし、このチュートリアルの最後にわかるように、リソースはカスケードスタイルシート (CSS) よりはるかに強力です。</span><span class="sxs-lookup"><span data-stu-id="47e13-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="47e13-129">リソースの詳細については、「 [XAML resources](../advanced/xaml-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e13-129">To learn more about resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="47e13-130">スタイルを使用してボタンの基本プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="47e13-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="47e13-131">**Application .resources ブロックを定義します**。App.xaml を開き、次の強調表示されているマークアップを追加します (まだ存在していない場合)。</span><span class="sxs-lookup"><span data-stu-id="47e13-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="47e13-132">リソースのスコープは、リソースを定義する場所によって決まります。</span><span class="sxs-lookup"><span data-stu-id="47e13-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="47e13-133">App.xaml ファイルの `Application.Resources` にリソースを定義すると、アプリケーション内の任意の場所からリソースを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="47e13-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="47e13-134">リソースのスコープを定義する方法の詳細については、「 [XAML resources](../advanced/xaml-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e13-134">To learn more about defining the scope of your resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

2. <span data-ttu-id="47e13-135">**スタイルを作成し、それを使用して基本的なプロパティ値を定義します。** 次のマークアップを `Application.Resources` ブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="47e13-136">このマークアップは、アプリケーションのすべてのボタンに適用される <xref:System.Windows.Style> を作成し、ボタンの <xref:System.Windows.FrameworkElement.Width%2A> を90に、<xref:System.Windows.FrameworkElement.Margin%2A> を10に設定します。</span><span class="sxs-lookup"><span data-stu-id="47e13-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="47e13-137"><xref:System.Windows.Style.TargetType%2A> プロパティは、スタイルが <xref:System.Windows.Controls.Button>型のすべてのオブジェクトに適用されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="47e13-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="47e13-138">各 <xref:System.Windows.Setter> は、<xref:System.Windows.Style>に対して異なるプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="47e13-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="47e13-139">そのため、この時点では、アプリケーションの各ボタンの幅は90、余白は10です。</span><span class="sxs-lookup"><span data-stu-id="47e13-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="47e13-140">F5 キーを押してアプリケーションを実行すると、次のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="47e13-141">![幅が90、余白が10のボタン](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="47e13-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="47e13-142">スタイルを使用すると、さまざまな方法で、対象となるオブジェクトを細かく調整したり、複雑なプロパティ値を指定したり、他のスタイルの入力としてスタイルを使用したりできます。</span><span class="sxs-lookup"><span data-stu-id="47e13-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="47e13-143">詳しくは、「 [スタイルとテンプレート](styling-and-templating.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="47e13-143">For more information, see [Styling and Templating](styling-and-templating.md).</span></span>

3. <span data-ttu-id="47e13-144">**リソースにスタイルプロパティ値を設定します。** リソースを使用すると、一般的に定義されているオブジェクトと値を簡単に再利用できます。</span><span class="sxs-lookup"><span data-stu-id="47e13-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="47e13-145">特に、コードのモジュール性を高めるために、リソースを使用して複雑な値を定義すると便利です。</span><span class="sxs-lookup"><span data-stu-id="47e13-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="47e13-146">次の強調表示されたマークアップを app.xaml に追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-146">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="47e13-147">`Application.Resources` ブロックのすぐ下には、"GrayBlueGradientBrush" という名前のリソースが作成されています。</span><span class="sxs-lookup"><span data-stu-id="47e13-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="47e13-148">このリソースは、水平方向のグラデーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="47e13-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="47e13-149">このリソースは、アプリケーション内の任意の場所からのプロパティ値として使用できます。これには、<xref:System.Windows.Controls.Control.Background%2A> プロパティのボタンスタイルセッターの内部を含みます。</span><span class="sxs-lookup"><span data-stu-id="47e13-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="47e13-150">これで、すべてのボタンにこのグラデーションの <xref:System.Windows.Controls.Control.Background%2A> プロパティ値が設定されました。</span><span class="sxs-lookup"><span data-stu-id="47e13-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="47e13-151">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="47e13-151">Press F5 to run the application.</span></span> <span data-ttu-id="47e13-152">これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="47e13-152">It should look like the following.</span></span>

     <span data-ttu-id="47e13-153">![グラデーションの背景を持つボタン](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="47e13-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="47e13-154">ボタンの外観を定義するテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="47e13-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="47e13-155">このセクションでは、ボタンの外観 (プレゼンテーション) をカスタマイズするテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="47e13-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="47e13-156">ボタンの表示は、四角形やその他のコンポーネントを含む複数のオブジェクトで構成されています。これにより、ボタンに固有の外観が提供されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="47e13-157">これまでのところ、アプリケーションでのボタンの外観の制御は、ボタンのプロパティの変更に限定されています。</span><span class="sxs-lookup"><span data-stu-id="47e13-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="47e13-158">ボタンの外観により大きな変更を加える場合はどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="47e13-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="47e13-159">テンプレートを使用すると、オブジェクトのプレゼンテーションを強力に制御できます。</span><span class="sxs-lookup"><span data-stu-id="47e13-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="47e13-160">テンプレートはスタイル内で使用できるため、スタイルが適用されるすべてのオブジェクト (このチュートリアルではボタン) にテンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="47e13-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="47e13-161">テンプレートを使用してボタンの外観を定義するには</span><span class="sxs-lookup"><span data-stu-id="47e13-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="47e13-162">**テンプレートを設定します。** <xref:System.Windows.Controls.Button> のようなコントロールには <xref:System.Windows.Controls.Control.Template%2A> のプロパティがあるため、<xref:System.Windows.Setter>を使用して <xref:System.Windows.Style> に設定した他のプロパティ値と同じように、テンプレートプロパティの値を定義できます。</span><span class="sxs-lookup"><span data-stu-id="47e13-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="47e13-163">次の強調表示されたマークアップをボタンのスタイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-163">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="47e13-164">**Alter button プレゼンテーション:** この時点で、テンプレートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47e13-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="47e13-165">次の強調表示されたマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-165">Add the following highlighted markup.</span></span> <span data-ttu-id="47e13-166">このマークアップは、角が丸い2つの <xref:System.Windows.Shapes.Rectangle> 要素と、その後に <xref:System.Windows.Controls.DockPanel>を指定します。</span><span class="sxs-lookup"><span data-stu-id="47e13-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="47e13-167"><xref:System.Windows.Controls.DockPanel> は、ボタンの <xref:System.Windows.Controls.ContentPresenter> をホストするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="47e13-168"><xref:System.Windows.Controls.ContentPresenter> には、ボタンの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="47e13-169">このチュートリアルでは、コンテンツはテキスト ("Button 1"、"Button 2"、"Button 3") です。</span><span class="sxs-lookup"><span data-stu-id="47e13-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="47e13-170">すべてのテンプレートコンポーネント (四角形と <xref:System.Windows.Controls.DockPanel>) は、<xref:System.Windows.Controls.Grid>内にレイアウトされます。</span><span class="sxs-lookup"><span data-stu-id="47e13-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="47e13-171">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="47e13-171">Press F5 to run the application.</span></span> <span data-ttu-id="47e13-172">これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="47e13-172">It should look like the following.</span></span>

     ![3個のボタンがあるウィンドウ](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="47e13-174">**テンプレートに glasseffect を追加します。** 次に、グラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="47e13-175">まず、ガラスのグラデーション効果を作成するいくつかのリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="47e13-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="47e13-176">次のグラデーションリソースを `Application.Resources` ブロック内の任意の場所に追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="47e13-177">これらのリソースは、ボタンテンプレートの <xref:System.Windows.Controls.Grid> に挿入する四角形の <xref:System.Windows.Shapes.Shape.Fill%2A> として使用されます。</span><span class="sxs-lookup"><span data-stu-id="47e13-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="47e13-178">次の強調表示されたマークアップをテンプレートに追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="47e13-179">`x:Name` プロパティが "glassCube" の四角形の <xref:System.Windows.UIElement.Opacity%2A> が0であることに注意してください。そのため、サンプルを実行すると、グラス四角形が上に重なって表示されません。</span><span class="sxs-lookup"><span data-stu-id="47e13-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="47e13-180">これは、ユーザーがボタンを操作するときに、後でテンプレートにトリガーを追加するためです。</span><span class="sxs-lookup"><span data-stu-id="47e13-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="47e13-181">ただし、<xref:System.Windows.UIElement.Opacity%2A> の値を1に変更してアプリケーションを実行すると、ボタンがどのように表示されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="47e13-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="47e13-182">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e13-182">See the following figure.</span></span> <span data-ttu-id="47e13-183">次の手順に進む前に、<xref:System.Windows.UIElement.Opacity%2A> を0に戻します。</span><span class="sxs-lookup"><span data-stu-id="47e13-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="47e13-184">![XAML を使用して作成されたカスタムボタン](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="47e13-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="47e13-185">ボタンの対話機能の作成</span><span class="sxs-lookup"><span data-stu-id="47e13-185">Create Button Interactivity</span></span>

<span data-ttu-id="47e13-186">このセクションでは、プロパティトリガーとイベントトリガーを作成して、プロパティ値を変更し、マウスポインターをボタンの上に移動したり、をクリックしたりするなど、ユーザーの操作に応じてアニメーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="47e13-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="47e13-187">対話機能を追加する簡単な方法としては、テンプレートまたはスタイル内でトリガーを定義する方法があります。</span><span class="sxs-lookup"><span data-stu-id="47e13-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="47e13-188"><xref:System.Windows.Trigger>を作成するには、プロパティ "condition" を定義します。たとえば、ボタン <xref:System.Windows.UIElement.IsMouseOver%2A> プロパティ値は `true`に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="47e13-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="47e13-189">次に、トリガー条件が true のときに実行される setter (アクション) を定義します。</span><span class="sxs-lookup"><span data-stu-id="47e13-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="47e13-190">ボタンのインタラクティビティを作成するには</span><span class="sxs-lookup"><span data-stu-id="47e13-190">To create button interactivity</span></span>

1. <span data-ttu-id="47e13-191">**テンプレートトリガーの追加:** 強調表示されたマークアップをテンプレートに追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="47e13-192">**プロパティトリガーの追加:** 強調表示されたマークアップを `ControlTemplate.Triggers` ブロックに追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="47e13-193">F5 キーを押してアプリケーションを実行し、ボタンの上にマウスポインターを置いたときの効果を確認します。</span><span class="sxs-lookup"><span data-stu-id="47e13-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="47e13-194">**フォーカストリガーを追加します。** 次に、同様の setter を追加して、ボタンにフォーカスがある場合 (ユーザーがクリックした後など) に対処します。</span><span class="sxs-lookup"><span data-stu-id="47e13-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="47e13-195">F5 キーを押してアプリケーションを実行し、ボタンのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="47e13-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="47e13-196">ボタンはフォーカスがあるため、クリックすると強調表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="47e13-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="47e13-197">別のボタンをクリックすると、最後のボタンではフォーカスが失われますが、新しいボタンはフォーカスを取得します。</span><span class="sxs-lookup"><span data-stu-id="47e13-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="47e13-198"><xref:System.Windows.UIElement.MouseEnter> と <xref:System.Windows.UIElement.MouseLeave>**のアニメーションを追加** **し** **ます。** 次に、いくつかのアニメーションをトリガーに追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="47e13-199">`ControlTemplate.Triggers` ブロック内の任意の場所に、次のマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="47e13-200">マウスポインターをボタンの上に移動するとグラス四角形が縮小され、ポインターが離れると通常のサイズに戻ります。</span><span class="sxs-lookup"><span data-stu-id="47e13-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="47e13-201">ポインターがボタンの上に移動したときにトリガーされるアニメーションが2つあります (<xref:System.Windows.UIElement.MouseEnter> イベントが発生します)。</span><span class="sxs-lookup"><span data-stu-id="47e13-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="47e13-202">これらのアニメーションは、X 軸と Y 軸に沿ってグラス四角形を縮小します。</span><span class="sxs-lookup"><span data-stu-id="47e13-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="47e13-203"><xref:System.Windows.Media.Animation.DoubleAnimation> 要素のプロパティ (<xref:System.Windows.Media.Animation.Timeline.Duration%2A> と <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>に注意してください。</span><span class="sxs-lookup"><span data-stu-id="47e13-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="47e13-204"><xref:System.Windows.Media.Animation.Timeline.Duration%2A> は、アニメーションが0.5 秒を超えて実行されることを指定し、<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> は、ガラスが10% 削減されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="47e13-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="47e13-205">2つ目のイベントトリガー (<xref:System.Windows.UIElement.MouseLeave>) は、最初のトリガーを停止するだけです。</span><span class="sxs-lookup"><span data-stu-id="47e13-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="47e13-206"><xref:System.Windows.Media.Animation.Storyboard>を停止すると、アニメーション化されたすべてのプロパティが既定値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="47e13-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="47e13-207">このため、ユーザーがポインターをボタンの外に移動すると、ボタンは、マウスポインターがボタンの上に移動する前の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="47e13-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="47e13-208">アニメーションの詳細については、「[アニメーションの概要](../graphics-multimedia/animation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47e13-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="47e13-209">**ボタンがクリックされたときのアニメーションを追加します。** 最後の手順では、ユーザーがボタンをクリックしたときのトリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="47e13-210">`ControlTemplate.Triggers` ブロック内の任意の場所に、次のマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="47e13-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="47e13-211">F5 キーを押してアプリケーションを実行し、ボタンのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="47e13-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="47e13-212">ボタンをクリックすると、グラス四角形が回転します。</span><span class="sxs-lookup"><span data-stu-id="47e13-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="47e13-213">まとめ</span><span class="sxs-lookup"><span data-stu-id="47e13-213">Summary</span></span>
 <span data-ttu-id="47e13-214">このチュートリアルでは、次の演習を実行しました。</span><span class="sxs-lookup"><span data-stu-id="47e13-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="47e13-215">オブジェクトの種類 (<xref:System.Windows.Controls.Button>) への <xref:System.Windows.Style> を対象としています。</span><span class="sxs-lookup"><span data-stu-id="47e13-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="47e13-216"><xref:System.Windows.Style>を使用して、アプリケーション全体のボタンの基本プロパティを制御します。</span><span class="sxs-lookup"><span data-stu-id="47e13-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="47e13-217"><xref:System.Windows.Style> setter のプロパティ値に使用する、グラデーションなどのリソースを作成しました。</span><span class="sxs-lookup"><span data-stu-id="47e13-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="47e13-218">ボタンにテンプレートを適用することによって、アプリケーション全体のボタンの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="47e13-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="47e13-219">アニメーション効果を含むユーザーの操作 (<xref:System.Windows.UIElement.MouseEnter>、<xref:System.Windows.UIElement.MouseLeave>、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>など) に応じたボタンのカスタマイズされた動作。</span><span class="sxs-lookup"><span data-stu-id="47e13-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="47e13-220">関連項目</span><span class="sxs-lookup"><span data-stu-id="47e13-220">See also</span></span>

- [<span data-ttu-id="47e13-221">Microsoft Expression Blend を使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="47e13-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="47e13-222">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="47e13-222">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="47e13-223">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="47e13-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="47e13-224">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="47e13-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="47e13-225">ビットマップ効果の概要</span><span class="sxs-lookup"><span data-stu-id="47e13-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
