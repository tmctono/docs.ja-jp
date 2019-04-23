---
title: 'チュートリアル: XAML を使用したボタンの作成'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 908a38485c879e3f28399bb7dbc8303afd4505da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309499"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="38a25-102">チュートリアル: XAML を使用したボタンの作成</span><span class="sxs-lookup"><span data-stu-id="38a25-102">Walkthrough: Create a Button by Using XAML</span></span>
<span data-ttu-id="38a25-103">このチュートリアルでは、Windows Presentation Foundation (WPF) アプリケーションで使用するためのアニメーションのボタンを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38a25-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="38a25-104">このチュートリアルでは、スタイルとテンプレートを使用して、コードの再利用し、ボタンの宣言からボタンのロジックの分離を許可するカスタマイズされたボタンのリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="38a25-105">このチュートリアルが完全に記述された[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="38a25-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="38a25-106">このチュートリアルで入力またはコピーして貼り付けることによって、アプリケーションを作成するための手順を説明する[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]に Microsoft Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="38a25-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Microsoft Visual Studio.</span></span> <span data-ttu-id="38a25-107">デザイン ツール (Microsoft Expression Blend) を使用して、参照してください、同じアプリケーションを作成する方法を学習したい場合[Microsoft Expression Blend を使用してボタンを作成する](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)します。</span><span class="sxs-lookup"><span data-stu-id="38a25-107">If you would prefer to learn how to use a design tool (Microsoft Expression Blend) to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>  
  
 <span data-ttu-id="38a25-108">次の図は、完成したボタンを示しています。</span><span class="sxs-lookup"><span data-stu-id="38a25-108">The following figure shows the finished buttons.</span></span>  
  
 <span data-ttu-id="38a25-109">![XAML を使用して作成されたカスタム ボタン](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="38a25-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-basic-buttons"></a><span data-ttu-id="38a25-110">基本的なボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-110">Create Basic Buttons</span></span>  
 <span data-ttu-id="38a25-111">新しいプロジェクトを作成し、ボタンをいくつかのウィンドウに追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="38a25-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="38a25-112">新しい WPF プロジェクトを作成し、ウィンドウにボタンを追加するには</span><span class="sxs-lookup"><span data-stu-id="38a25-112">To create a new WPF project and add buttons to the window</span></span>  
  
1. <span data-ttu-id="38a25-113">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="38a25-113">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="38a25-114">**新しい WPF プロジェクトを作成します。** **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a25-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="38a25-115">検索、 **Windows アプリケーション (WPF)** テンプレートとプロジェクト"AnimatedButton"の名前。</span><span class="sxs-lookup"><span data-stu-id="38a25-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="38a25-116">これにより、アプリケーションのスケルトンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-116">This will create the skeleton for the application.</span></span>  
  
3. <span data-ttu-id="38a25-117">**基本的な既定のボタンを追加します。** このチュートリアルで必要なすべてのファイルは、テンプレートによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="38a25-118">ダブルクリックして、ソリューション エクスプ ローラーで、Window1.xaml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="38a25-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="38a25-119">既定では、 <xref:System.Windows.Controls.Grid> Window1.xaml 内の要素。</span><span class="sxs-lookup"><span data-stu-id="38a25-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="38a25-120">削除、<xref:System.Windows.Controls.Grid>要素をいくつかのボタンを追加して、 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 」と入力またはコピーして貼り付けることで Window1.xaml を強調表示されている次のコード ページ。</span><span class="sxs-lookup"><span data-stu-id="38a25-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>  
  
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
  
     <span data-ttu-id="38a25-121">F5 キーを押してアプリケーションを実行次の図のようなボタンのセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>  
  
     <span data-ttu-id="38a25-122">![3 つの基本的なボタン](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="38a25-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>  
  
     <span data-ttu-id="38a25-123">基本的なボタンを作成するには、Window1.xaml ファイルの操作が完了したら。</span><span class="sxs-lookup"><span data-stu-id="38a25-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="38a25-124">このチュートリアルの残りの部分は、スタイルとボタンのテンプレートを定義する、app.xaml ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38a25-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>  
  
## <a name="set-basic-properties"></a><span data-ttu-id="38a25-125">基本的なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="38a25-125">Set Basic Properties</span></span>  
 <span data-ttu-id="38a25-126">次に、ボタンの外観とレイアウトを制御するこれらのボタンをいくつかのプロパティを設定してみましょう。</span><span class="sxs-lookup"><span data-stu-id="38a25-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="38a25-127">ボタンのプロパティを個別に設定するのではなく、アプリケーション全体のボタンのプロパティを定義するのにリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="38a25-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="38a25-128">アプリケーション リソースは外部に概念的に似ています[!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]Web ページです。 ただし、リソースはよりもはるかに強力な[!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)]、このチュートリアルの最後で表示されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-128">Application resources are conceptually similar to external [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] for Web pages; however, resources are much more powerful than [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="38a25-129">リソースの詳細については、次を参照してください。 [XAML リソース](../advanced/xaml-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="38a25-129">To learn more about resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="38a25-130">スタイルを使用して、ボタンの基本プロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="38a25-130">To use styles to set basic properties on the buttons</span></span>  
  
1. <span data-ttu-id="38a25-131">**Application.Resources ブロックを定義します。** App.xaml を開きがない場合は、次の強調表示されたマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>  
  
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
  
     <span data-ttu-id="38a25-132">リソースのスコープは、定義したリソースによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="38a25-133">内のリソースを定義する`Application.Resources`app.xaml ファイル、アプリケーションで任意の場所から使用するリソースを使用できます。</span><span class="sxs-lookup"><span data-stu-id="38a25-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="38a25-134">詳細については、リソースのスコープを定義するを参照してください。 [XAML リソース](../advanced/xaml-resources.md)します。</span><span class="sxs-lookup"><span data-stu-id="38a25-134">To learn more about defining the scope of your resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>  
  
2. <span data-ttu-id="38a25-135">**スタイルを作成し、基本的なプロパティ値を定義します。** 次のマークアップを追加、`Application.Resources`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="38a25-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="38a25-136">このマークアップを作成、<xref:System.Windows.Style>設定、アプリケーションのすべてのボタンに適用する、<xref:System.Windows.FrameworkElement.Width%2A>を 90 にボタンの<xref:System.Windows.FrameworkElement.Margin%2A>10。</span><span class="sxs-lookup"><span data-stu-id="38a25-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <span data-ttu-id="38a25-137"><xref:System.Windows.Style.TargetType%2A>プロパティは、型のすべてのオブジェクトにスタイルが適用されることを指定します<xref:System.Windows.Controls.Button>します。</span><span class="sxs-lookup"><span data-stu-id="38a25-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="38a25-138">各<xref:System.Windows.Setter>の別のプロパティ値を設定、<xref:System.Windows.Style>します。</span><span class="sxs-lookup"><span data-stu-id="38a25-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="38a25-139">そのため、この時点で、アプリケーション内のすべてのボタンが幅 90、余白は 10 です。</span><span class="sxs-lookup"><span data-stu-id="38a25-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="38a25-140">アプリケーションの実行に f5 キーを押すと、次のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-140">If you press F5 to run the application, you see the following window.</span></span>  
  
     <span data-ttu-id="38a25-141">![幅 90、余白 10 のボタン](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="38a25-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>  
  
     <span data-ttu-id="38a25-142">さらに多くのさまざまなオブジェクトが対象となるを微調整する方法を含む、複合プロパティの値を指定しても入力としてスタイルを使用して、その他のスタイルのスタイルで行えるがあります。</span><span class="sxs-lookup"><span data-stu-id="38a25-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="38a25-143">詳しくは、「 [スタイルとテンプレート](styling-and-templating.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38a25-143">For more information, see [Styling and Templating](styling-and-templating.md).</span></span>  
  
3. <span data-ttu-id="38a25-144">**リソースへのスタイル プロパティの値を設定します。** リソースには、一般的に定義されるオブジェクトと値を再利用する簡単な方法が有効にします。</span><span class="sxs-lookup"><span data-stu-id="38a25-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="38a25-145">リソースを使用して、コードをモジュール性の高い複雑な値を定義すると特に便利です。</span><span class="sxs-lookup"><span data-stu-id="38a25-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="38a25-146">App.xaml には、次の強調表示されたマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-146">Add the following highlighted markup to app.xaml.</span></span>  
  
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
  
     <span data-ttu-id="38a25-147">すぐ下、`Application.Resources`ブロック"GrayBlueGradientBrush"という名前のリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="38a25-148">このリソースは、水平方向のグラデーションを定義します。</span><span class="sxs-lookup"><span data-stu-id="38a25-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="38a25-149">このリソースをどこからでもプロパティの値として使用できますのボタン スタイル setter 内など、アプリケーションで、<xref:System.Windows.Controls.Control.Background%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="38a25-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="38a25-150">ここで、すべてのボタンがある、<xref:System.Windows.Controls.Control.Background%2A>このグラデーションのプロパティの値。</span><span class="sxs-lookup"><span data-stu-id="38a25-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>  
  
     <span data-ttu-id="38a25-151">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="38a25-151">Press F5 to run the application.</span></span> <span data-ttu-id="38a25-152">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="38a25-152">It should look like the following.</span></span>  
  
     <span data-ttu-id="38a25-153">![グラデーション背景を持つボタン](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="38a25-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="38a25-154">ボタンの外観を定義するテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-154">Create a Template That Defines the Look of the Button</span></span>  
 <span data-ttu-id="38a25-155">このセクションでは、ボタンの外観 (presentation) をカスタマイズするテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="38a25-156">ボタンのプレゼンテーションは、ボタンの外観を一意に四角形とその他のコンポーネントを含むいくつかのオブジェクトの構成されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>  
  
 <span data-ttu-id="38a25-157">ここまでは、アプリケーションのボタンの外観の制御は、ボタンのプロパティの変更に制限されていましたが。</span><span class="sxs-lookup"><span data-stu-id="38a25-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="38a25-158">ボタンの外観をより大きく変更する場合は?</span><span class="sxs-lookup"><span data-stu-id="38a25-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="38a25-159">テンプレートには、オブジェクトのプレゼンテーションに強力な制御が有効にします。</span><span class="sxs-lookup"><span data-stu-id="38a25-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="38a25-160">テンプレートは、スタイル内で使用できる、ため (このチュートリアルでは、ボタン) では、スタイルが適用されるすべてのオブジェクトにテンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="38a25-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="38a25-161">テンプレートを使用して、ボタンの外観を定義するには</span><span class="sxs-lookup"><span data-stu-id="38a25-161">To use the template to define the look of the button</span></span>  
  
1. <span data-ttu-id="38a25-162">**テンプレートを設定します。** コントロールなどのため、<xref:System.Windows.Controls.Button>が、<xref:System.Windows.Controls.Control.Template%2A>プロパティで設定している他のプロパティ値と同様、テンプレート プロパティの値を定義できますを<xref:System.Windows.Style>を使用して、<xref:System.Windows.Setter>します。</span><span class="sxs-lookup"><span data-stu-id="38a25-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="38a25-163">次の強調表示されたマークアップをボタンのスタイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-163">Add the following highlighted markup to your button style.</span></span>  
  
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
  
2. <span data-ttu-id="38a25-164">**ボタンのプレゼンテーションを変更するには。** この時点では、テンプレートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38a25-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="38a25-165">次の強調表示されたマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-165">Add the following highlighted markup.</span></span> <span data-ttu-id="38a25-166">このマークアップでは、2 つを指定します<xref:System.Windows.Shapes.Rectangle>角の丸いを持つ要素が続く、<xref:System.Windows.Controls.DockPanel>します。</span><span class="sxs-lookup"><span data-stu-id="38a25-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="38a25-167"><xref:System.Windows.Controls.DockPanel>されるホストに、<xref:System.Windows.Controls.ContentPresenter>ボタンの。</span><span class="sxs-lookup"><span data-stu-id="38a25-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="38a25-168">A<xref:System.Windows.Controls.ContentPresenter>ボタンのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="38a25-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="38a25-169">このチュートリアルでは、コンテンツは、テキスト (「ボタン 1」、「ボタン 2」、「ボタン 3」) です。</span><span class="sxs-lookup"><span data-stu-id="38a25-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="38a25-170">すべてのテンプレートのコンポーネント (四角形と<xref:System.Windows.Controls.DockPanel>) 内のレイアウトは、<xref:System.Windows.Controls.Grid>します。</span><span class="sxs-lookup"><span data-stu-id="38a25-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>  
  
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
  
     <span data-ttu-id="38a25-171">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="38a25-171">Press F5 to run the application.</span></span> <span data-ttu-id="38a25-172">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="38a25-172">It should look like the following.</span></span>  
  
     <span data-ttu-id="38a25-173">![](./media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span><span class="sxs-lookup"><span data-stu-id="38a25-173">![](./media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span></span>  
  
3. <span data-ttu-id="38a25-174">**テンプレートには、グラス効果を追加します。** 次に、ガラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="38a25-175">まずガラスのグラデーション効果を作成するいくつかのリソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="38a25-176">これらグラデーション内のリソース任意の場所を追加、`Application.Resources`ブロック。</span><span class="sxs-lookup"><span data-stu-id="38a25-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>  
  
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
  
     <span data-ttu-id="38a25-177">これらのリソースとして使用、<xref:System.Windows.Shapes.Shape.Fill%2A>に挿入する四角形の<xref:System.Windows.Controls.Grid>ボタン テンプレートの。</span><span class="sxs-lookup"><span data-stu-id="38a25-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="38a25-178">テンプレートには、次の強調表示されたマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-178">Add the following highlighted markup to the template.</span></span>  
  
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
  
     <span data-ttu-id="38a25-179">注意して、<xref:System.Windows.UIElement.Opacity%2A>四角形の`x:Name`"glassCube"のプロパティが 0 の場合、サンプルを実行するときに、一番上にオーバーレイ グラス四角形は表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="38a25-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="38a25-180">これは後でトリガーを追加のテンプレートをユーザーがボタンであるためにです。</span><span class="sxs-lookup"><span data-stu-id="38a25-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="38a25-181">ボタンの外観のように今すぐ変更することによって、ご覧、 <xref:System.Windows.UIElement.Opacity%2A> 1 およびアプリケーションを実行する値。</span><span class="sxs-lookup"><span data-stu-id="38a25-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="38a25-182">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a25-182">See the following figure.</span></span> <span data-ttu-id="38a25-183">次の手順に進む前に変更、<xref:System.Windows.UIElement.Opacity%2A>を 0 に戻します。</span><span class="sxs-lookup"><span data-stu-id="38a25-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>  
  
     <span data-ttu-id="38a25-184">![XAML を使用して作成されたカスタム ボタン](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="38a25-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-button-interactivity"></a><span data-ttu-id="38a25-185">ボタンの対話機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-185">Create Button Interactivity</span></span>  
 <span data-ttu-id="38a25-186">このセクションでは、プロパティ トリガーと、プロパティ値を変更し、ボタンの上にマウス ポインターを移動し、クリックしてなどのユーザー アクションへの応答でアニメーションを実行するイベント トリガーを作成します。</span><span class="sxs-lookup"><span data-stu-id="38a25-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>  
  
 <span data-ttu-id="38a25-187">対話機能 (マウス、マウスのままをクリックし、およびなど) を追加する簡単な方法では、テンプレートまたはスタイル内のトリガーを定義します。</span><span class="sxs-lookup"><span data-stu-id="38a25-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="38a25-188">作成する、<xref:System.Windows.Trigger>などのプロパティの"condition"を定義します。ボタン<xref:System.Windows.UIElement.IsMouseOver%2A>プロパティの値が等しく`true`します。</span><span class="sxs-lookup"><span data-stu-id="38a25-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="38a25-189">トリガー条件が true のときに行われるセッター (アクション) を定義します。</span><span class="sxs-lookup"><span data-stu-id="38a25-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>  
  
#### <a name="to-create-button-interactivity"></a><span data-ttu-id="38a25-190">ボタンの対話機能を作成するには</span><span class="sxs-lookup"><span data-stu-id="38a25-190">To create button interactivity</span></span>  
  
1. <span data-ttu-id="38a25-191">**テンプレートのトリガーを追加します。** テンプレートには、強調表示されたマークアップを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>  
  
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
  
2. <span data-ttu-id="38a25-192">**プロパティ トリガーを追加します。** 強調表示されたマークアップを追加、`ControlTemplate.Triggers`ブロック。</span><span class="sxs-lookup"><span data-stu-id="38a25-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>  
  
    ```xaml
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     <span data-ttu-id="38a25-193">F5 キーを押してアプリケーションを実行し、ボタンの上にマウス ポインターを実行すると、影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="38a25-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>  
  
3. <span data-ttu-id="38a25-194">**フォーカスのトリガーを追加します。** 次に、ボタンに (たとえば、ユーザーがクリックした後) にフォーカスがあるときに、ケースを処理するいくつかのような set アクセス操作子を追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>  
  
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
  
     <span data-ttu-id="38a25-195">F5 キーを押してアプリケーションを実行し、ボタンのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a25-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="38a25-196">フォーカスをしているために、クリックした後、ボタンが強調表示されたままことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="38a25-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="38a25-197">新しいボタンに別のボタンをクリックすると、最後の 1 つがそれを失ったときにフォーカスを取得します。</span><span class="sxs-lookup"><span data-stu-id="38a25-197">If you click another button, the new button gains focus while the last one loses it.</span></span>  
  
4. <span data-ttu-id="38a25-198">**アニメーションを追加**<xref:System.Windows.UIElement.MouseEnter> **と** <xref:System.Windows.UIElement.MouseLeave> **:** 次に、トリガーに一部のアニメーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="38a25-199">任意の場所内の次のマークアップを追加、`ControlTemplate.Triggers`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="38a25-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>  
  
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
  
     <span data-ttu-id="38a25-200">グラス四角形には、マウス ポインターがボタン上に移動し、ポインターが離れたときに通常のサイズを返しますが縮小されます。</span><span class="sxs-lookup"><span data-stu-id="38a25-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>  
  
     <span data-ttu-id="38a25-201">ポインターがボタンを超えた場合にトリガーされる 2 つのアニメーションがある (<xref:System.Windows.UIElement.MouseEnter>イベントが発生します)。</span><span class="sxs-lookup"><span data-stu-id="38a25-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="38a25-202">これらのアニメーションは、X と Y 軸に沿ったグラス四角形を縮小します。</span><span class="sxs-lookup"><span data-stu-id="38a25-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="38a25-203">プロパティに注目してください、<xref:System.Windows.Media.Animation.DoubleAnimation>要素-<xref:System.Windows.Media.Animation.Timeline.Duration%2A>と<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>します。</span><span class="sxs-lookup"><span data-stu-id="38a25-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="38a25-204"><xref:System.Windows.Media.Animation.Timeline.Duration%2A>を 0.5 秒、発生するアニメーションのことを指定します、<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>ガラスが 10% に縮小ことを指定します。</span><span class="sxs-lookup"><span data-stu-id="38a25-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>  
  
     <span data-ttu-id="38a25-205">2 番目のイベント トリガー (<xref:System.Windows.UIElement.MouseLeave>) 1 つ目を単純に停止します。</span><span class="sxs-lookup"><span data-stu-id="38a25-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="38a25-206">停止すると、 <xref:System.Windows.Media.Animation.Storyboard>、アニメーション化されたすべてのプロパティが既定値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="38a25-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="38a25-207">そのため、ユーザーがポインター ボタンから離れると、ボタンに戻りますがマウス ポインターがボタンの上に移動する前にする方法。</span><span class="sxs-lookup"><span data-stu-id="38a25-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="38a25-208">アニメーションの詳細については、次を参照してください。[アニメーションの概要](../graphics-multimedia/animation-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="38a25-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>  
  
5. <span data-ttu-id="38a25-209">**ボタンがクリックされたときのアニメーションを追加します。** 最後の手順では、ユーザーがボタンをクリックしたときにトリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="38a25-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="38a25-210">任意の場所内の次のマークアップを追加、`ControlTemplate.Triggers`ブロック。</span><span class="sxs-lookup"><span data-stu-id="38a25-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>  
  
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
  
     <span data-ttu-id="38a25-211">F5 キーを押して、アプリケーションを実行し、ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a25-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="38a25-212">ボタンをクリックすると、ガラスの四角形が回転します。</span><span class="sxs-lookup"><span data-stu-id="38a25-212">When you click a button, the glass rectangle spins around.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="38a25-213">まとめ</span><span class="sxs-lookup"><span data-stu-id="38a25-213">Summary</span></span>  
 <span data-ttu-id="38a25-214">このチュートリアルでは、次の演習を実行しました。</span><span class="sxs-lookup"><span data-stu-id="38a25-214">In this walkthrough, you performed the following exercises:</span></span>  
  
-   <span data-ttu-id="38a25-215">対象となる、<xref:System.Windows.Style>オブジェクトの種類を (<xref:System.Windows.Controls.Button>)。</span><span class="sxs-lookup"><span data-stu-id="38a25-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>  
  
-   <span data-ttu-id="38a25-216">アプリケーション全体を使用して、ボタンの基本プロパティを制御、<xref:System.Windows.Style>します。</span><span class="sxs-lookup"><span data-stu-id="38a25-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>  
  
-   <span data-ttu-id="38a25-217">プロパティ値を使用するグラデーションなどのリソースを作成、 <xref:System.Windows.Style> set アクセス操作子。</span><span class="sxs-lookup"><span data-stu-id="38a25-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>  
  
-   <span data-ttu-id="38a25-218">アプリケーション全体のボタンの外観をカスタマイズするには、ボタンにテンプレートを適用します。</span><span class="sxs-lookup"><span data-stu-id="38a25-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>  
  
-   <span data-ttu-id="38a25-219">ユーザー操作に応じてボタンの動作をカスタマイズ (など<xref:System.Windows.UIElement.MouseEnter>、<xref:System.Windows.UIElement.MouseLeave>と<xref:System.Windows.Controls.Primitives.ButtonBase.Click>) アニメーション効果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="38a25-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a25-220">関連項目</span><span class="sxs-lookup"><span data-stu-id="38a25-220">See also</span></span>

- [<span data-ttu-id="38a25-221">Microsoft Expression Blend を使用してボタンを作成する</span><span class="sxs-lookup"><span data-stu-id="38a25-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="38a25-222">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="38a25-222">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="38a25-223">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="38a25-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="38a25-224">純色およびグラデーションによる塗りつぶしの概要</span><span class="sxs-lookup"><span data-stu-id="38a25-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="38a25-225">ビットマップ効果の概要</span><span class="sxs-lookup"><span data-stu-id="38a25-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
