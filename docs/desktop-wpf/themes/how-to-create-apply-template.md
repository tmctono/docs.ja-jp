---
title: WPF でテンプレートを作成する - .NET デスクトップ
description: Windows プレゼンテーション ファンデーションおよび .NET Core でコントロール テンプレートを作成して参照する方法について説明します。
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432540"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="0f268-103">コントロールのテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="0f268-103">Create a template for a control</span></span>

<span data-ttu-id="0f268-104">Windows プレゼンテーションファンデーション (WPF) を使用すると、独自の再利用可能なテンプレートを使用して、既存のコントロールの視覚的な構造と動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0f268-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="0f268-105">テンプレートは、アプリケーション、ウィンドウ、ページにグローバルに適用することも、コントロールに直接適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f268-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="0f268-106">新しいコントロールを作成する必要があるほとんどのシナリオは、既存のコントロールの新しいテンプレートを作成する代わりに対応できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="0f268-107">この記事では、コントロールの新しい<xref:System.Windows.Controls.ControlTemplate>作成について説明します。 <xref:System.Windows.Controls.Button></span><span class="sxs-lookup"><span data-stu-id="0f268-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="0f268-108">コントロール テンプレートを作成する場合</span><span class="sxs-lookup"><span data-stu-id="0f268-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="0f268-109">コントロールには、 、 <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.Control.Foreground%2A>、および<xref:System.Windows.Controls.Control.FontFamily%2A>などの多くのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="0f268-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="0f268-110">これらのプロパティは、コントロールの外観のさまざまな側面を制御しますが、これらのプロパティを設定することによって行うことができる変更は制限されます。</span><span class="sxs-lookup"><span data-stu-id="0f268-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="0f268-111">たとえば、プロパティを<xref:System.Windows.Controls.Control.Foreground%2A>青に設定し、<xref:System.Windows.Controls.Control.FontStyle%2A>プロパティに斜体を<xref:System.Windows.Controls.CheckBox>設定できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="0f268-112">コントロールの他のプロパティを設定する以外に、コントロールの外観をカスタマイズする場合は、 を作成します<xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="0f268-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="0f268-113">ほとんどのユーザー インターフェイスでは、ボタンは同じ一般的な外観を持ちます: いくつかのテキストを持つ四角形。</span><span class="sxs-lookup"><span data-stu-id="0f268-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="0f268-114">丸みを帯びたボタンを作成する場合は、ボタンから継承する新しいコントロールを作成するか、ボタンの機能を再作成します。</span><span class="sxs-lookup"><span data-stu-id="0f268-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="0f268-115">さらに、新しいユーザー コントロールは、円形のビジュアルを提供します。</span><span class="sxs-lookup"><span data-stu-id="0f268-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="0f268-116">既存のコントロールの視覚的なレイアウトをカスタマイズすることで、新しいコントロールを作成しないようにできます。</span><span class="sxs-lookup"><span data-stu-id="0f268-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="0f268-117">丸みを帯びたボタンを使用して<xref:System.Windows.Controls.ControlTemplate>、目的のビジュアルレイアウトを持つ を作成します。</span><span class="sxs-lookup"><span data-stu-id="0f268-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="0f268-118">一方、新しい機能、異なるプロパティ、および新しい設定を持つコントロールが必要な場合は、新<xref:System.Windows.Controls.UserControl>しい を作成します。</span><span class="sxs-lookup"><span data-stu-id="0f268-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f268-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="0f268-119">Prerequisites</span></span>

<span data-ttu-id="0f268-120">新しい WPF アプリケーションを作成し *、MainWindow.xaml* (または選択した別のウィンドウ) で**\<、Window>** 要素に次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="0f268-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="0f268-121">**\<ウィンドウ>** 要素の内容を次の XAML に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f268-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="0f268-122">最終的には *、MainWindow.xaml*ファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0f268-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="0f268-123">アプリケーションを実行すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0f268-123">If you run the application, it looks like the following:</span></span>

![2 つのスタイルなしボタンを持つ WPF ウィンドウ](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="0f268-125">ControlTemplate の作成</span><span class="sxs-lookup"><span data-stu-id="0f268-125">Create a ControlTemplate</span></span>

<span data-ttu-id="0f268-126">を<xref:System.Windows.Controls.ControlTemplate>宣言する最も一般的な方法は、XAML`Resources`ファイルのセクション内のリソースとしてです。</span><span class="sxs-lookup"><span data-stu-id="0f268-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="0f268-127">テンプレートはリソースであるため、すべてのリソースに適用されるのと同じスコープルールに従います。</span><span class="sxs-lookup"><span data-stu-id="0f268-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="0f268-128">簡単に言うと、テンプレートを宣言する場所は、テンプレートを適用できる場所に影響します。</span><span class="sxs-lookup"><span data-stu-id="0f268-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="0f268-129">たとえば、アプリケーション定義 XAML ファイルのルート要素でテンプレートを宣言すると、アプリケーション内の任意の場所でテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="0f268-130">テンプレートをウィンドウで定義した場合、そのウィンドウ内のコントロールだけがテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="0f268-131">まず`Window.Resources`*、MainWindow.xaml*ファイルに要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="0f268-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="0f268-132">次のプロパティを設定して、新しい**\<ControlTemplate>** を作成します。</span><span class="sxs-lookup"><span data-stu-id="0f268-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="0f268-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="0f268-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="0f268-134">このコントロール テンプレートは、次の簡単な方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-134">This control template will be simple:</span></span>

- <span data-ttu-id="0f268-135">コントロールのルート要素、<xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="0f268-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="0f268-136">ボタン<xref:System.Windows.Shapes.Ellipse>の丸みを帯びた外観を描く</span><span class="sxs-lookup"><span data-stu-id="0f268-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="0f268-137">ユーザー<xref:System.Windows.Controls.ContentPresenter>指定のボタンの内容を表示する</span><span class="sxs-lookup"><span data-stu-id="0f268-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="0f268-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="0f268-138">TemplateBinding</span></span>

<span data-ttu-id="0f268-139">新<xref:System.Windows.Controls.ControlTemplate>しい を作成する場合でも、パブリック プロパティを使用してコントロールの外観を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="0f268-140">[TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)マークアップ拡張機能は、内にある要素のプロパティ<xref:System.Windows.Controls.ControlTemplate>を、コントロールによって定義されているパブリック プロパティにバインドします。</span><span class="sxs-lookup"><span data-stu-id="0f268-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="0f268-141">[TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)を使用すると、コントロールのプロパティがテンプレートのパラメーターとして機能するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="0f268-142">つまり、コントロールのプロパティを設定すると、その値は [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) が機能している要素に渡されます。</span><span class="sxs-lookup"><span data-stu-id="0f268-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="0f268-143">楕円形</span><span class="sxs-lookup"><span data-stu-id="0f268-143">Ellipse</span></span>

<span data-ttu-id="0f268-144">Ellipse>**:::no-loc text="Fill":::** 要素**:::no-loc text="Stroke":::** の**\<** プロパティと プロパティは、コントロール<xref:System.Windows.Controls.Control.Foreground>のプロパティと<xref:System.Windows.Controls.Control.Background>プロパティにバインドされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0f268-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="0f268-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="0f268-145">ContentPresenter</span></span>

<span data-ttu-id="0f268-146">コンテンツプレゼンター>要素もテンプレートに追加されます。 [ \<](xref:System.Windows.Controls.ContentPresenter)</span><span class="sxs-lookup"><span data-stu-id="0f268-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="0f268-147">このテンプレートはボタン用に設計されているため、ボタンが から<xref:System.Windows.Controls.ContentControl>継承することを考慮する。</span><span class="sxs-lookup"><span data-stu-id="0f268-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="0f268-148">ボタンは要素の内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="0f268-148">The button presents the content of the element.</span></span> <span data-ttu-id="0f268-149">プレーン テキストや別のコントロールなど、ボタン内の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0f268-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="0f268-150">次の両方が有効なボタンです。</span><span class="sxs-lookup"><span data-stu-id="0f268-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="0f268-151">上記の両方の例では、テキストとチェックボックスが[Button.Content](xref:System.Windows.Controls.ContentControl.Content)プロパティとして設定されています。</span><span class="sxs-lookup"><span data-stu-id="0f268-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="0f268-152">コンテンツとして設定されているものは**\<、ContentPresenter>** を通じて表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="0f268-153">などの<xref:System.Windows.Controls.ControlTemplate><xref:System.Windows.Controls.ContentControl>型に a が適用されている場合`Button`<xref:System.Windows.Controls.ContentPresenter>は、要素ツリーで a が検索されます。</span><span class="sxs-lookup"><span data-stu-id="0f268-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="0f268-154">が`ContentPresenter`見つかった場合、テンプレートはコントロールの<xref:System.Windows.Controls.ContentControl.Content>プロパティを . `ContentPresenter`</span><span class="sxs-lookup"><span data-stu-id="0f268-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="0f268-155">テンプレートを使用する</span><span class="sxs-lookup"><span data-stu-id="0f268-155">Use the template</span></span>

<span data-ttu-id="0f268-156">この記事の冒頭で宣言したボタンを見つけます。</span><span class="sxs-lookup"><span data-stu-id="0f268-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="0f268-157">2 番目のボタンの<xref:System.Windows.Controls.Control.Template>プロパティをリソース`roundbutton`に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f268-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="0f268-158">プロジェクトを実行して結果を確認すると、ボタンの背景が丸くなっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="0f268-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![テンプレートの楕円形ボタンが 1 つある WPF ウィンドウ](media/create-apply-template/styled-button.png)

<span data-ttu-id="0f268-160">ボタンが円ではなく、ゆがんでいることに気づいたかもしれません。</span><span class="sxs-lookup"><span data-stu-id="0f268-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="0f268-161">**\<楕円>** 要素の動作方法により、常に使用可能なスペースを埋めるために拡張されます。</span><span class="sxs-lookup"><span data-stu-id="0f268-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="0f268-162">ボタン**:::no-loc text="width":::** と**:::no-loc text="height":::** プロパティを同じ値に変更して、円を均一にします。</span><span class="sxs-lookup"><span data-stu-id="0f268-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![1 つのテンプレートの循環ボタンを持つ WPF ウィンドウ](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="0f268-164">トリガーの追加</span><span class="sxs-lookup"><span data-stu-id="0f268-164">Add a Trigger</span></span>

<span data-ttu-id="0f268-165">テンプレートが適用されたボタンの外観は異なりますが、他のボタンと同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="0f268-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="0f268-166">ボタンを押すと、イベントが<xref:System.Windows.Controls.Primitives.ButtonBase.Click>発生します。</span><span class="sxs-lookup"><span data-stu-id="0f268-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="0f268-167">ただし、ボタンの上にマウスを移動しても、ボタンのビジュアルは変更されないことに気付いたかもしれません。</span><span class="sxs-lookup"><span data-stu-id="0f268-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="0f268-168">これらの視覚的な相互作用はすべてテンプレートによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="0f268-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="0f268-169">WPFWPF が提供する動的イベントおよびプロパティ システムでは、値の特定のプロパティを監視し、必要に応じてテンプレートのスタイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="0f268-170">この例では、ボタンの<xref:System.Windows.UIElement.IsMouseOver>プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f268-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="0f268-171">マウスをコントロールの上に置き、**\<楕円>** を新しい色でスタイル設定します。</span><span class="sxs-lookup"><span data-stu-id="0f268-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="0f268-172">この種類のトリガは、*プロパティトリガー*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="0f268-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="0f268-173">これを行うには、参照できる**\<楕円>** に名前を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f268-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="0f268-174">**背景**要素の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="0f268-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="0f268-175">次に、新<xref:System.Windows.Trigger>しいを追加[ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers)します。</span><span class="sxs-lookup"><span data-stu-id="0f268-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="0f268-176">トリガは、値`IsMouseOver``true`のイベントを監視します。</span><span class="sxs-lookup"><span data-stu-id="0f268-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="0f268-177">次に、新しい色に**\<楕円>** の**\<\*\*\*\*Fill\*\*\*\*\<** Fill プロパティを変更するトリガー>にセッター>を追加します。</span><span class="sxs-lookup"><span data-stu-id="0f268-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="0f268-178">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f268-178">Run the project.</span></span> <span data-ttu-id="0f268-179">マウスをボタンの上に移動すると、**\<楕円>** の色が変わります。</span><span class="sxs-lookup"><span data-stu-id="0f268-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![マウスを WPF ボタンの上に移動して塗りつぶしの色を変更する](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="0f268-181">ビジュアルステートを使用する</span><span class="sxs-lookup"><span data-stu-id="0f268-181">Use a VisualState</span></span>

<span data-ttu-id="0f268-182">表示状態は、コントロールによって定義およびトリガされます。</span><span class="sxs-lookup"><span data-stu-id="0f268-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="0f268-183">たとえば、マウスをコントロールの上に移動すると、`CommonStates.MouseOver`状態がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="0f268-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="0f268-184">コントロールの現在の状態に基づいて、プロパティの変更をアニメーション化できます。</span><span class="sxs-lookup"><span data-stu-id="0f268-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="0f268-185">前のセクションでは**\<、PropertyTrigger>** を使用して、`IsMouseOver`ボタンの前景を`true`プロパティ`AliceBlue`が .</span><span class="sxs-lookup"><span data-stu-id="0f268-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="0f268-186">代わりに、この色の変化をアニメーション化する表示状態を作成し、スムーズな遷移を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f268-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="0f268-187">*VisualStates*の詳細については、「 [WPF のスタイルとテンプレート](../fundamentals/styles-templates-overview.md#visual-states)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f268-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="0f268-188">**\<プロパティ トリガー>** をアニメーション表示状態に変換するには、まず、**\<テンプレートから ControlTemplate.Triggers>** 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="0f268-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="0f268-189">次に、コントロール テンプレートの**\<グリッド>** ルートに**\<、>要素を** \*\* \<>追加\*\*`CommonStates`します。</span><span class="sxs-lookup"><span data-stu-id="0f268-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="0f268-190">2 つの状態`Normal`を`MouseOver`定義し、 と を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f268-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="0f268-191">VisualState>で定義されたアニメーションは、その状態がトリガーされたときに適用されます。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="0f268-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="0f268-192">各状態のアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f268-192">Create animations for each state.</span></span> <span data-ttu-id="0f268-193">アニメーションは、**\<ストーリーボード>** 要素の内部に配置されます。</span><span class="sxs-lookup"><span data-stu-id="0f268-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="0f268-194">ストーリーボードの詳細については、「ストーリーボードの[概要](../../framework/wpf/graphics-multimedia/storyboards-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f268-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="0f268-195">Normal</span><span class="sxs-lookup"><span data-stu-id="0f268-195">Normal</span></span>

  <span data-ttu-id="0f268-196">この状態は、楕円の塗りつぶしをアニメーション化し、コントロールの`Background`色に戻します。</span><span class="sxs-lookup"><span data-stu-id="0f268-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="0f268-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0f268-197">MouseOver</span></span>

  <span data-ttu-id="0f268-198">この状態は、楕円`Background`の色を新しい色に`Yellow`アニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="0f268-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="0f268-199">コントロール テンプレート>は、次のようになります。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="0f268-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="0f268-200">プロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f268-200">Run the project.</span></span> <span data-ttu-id="0f268-201">マウスをボタンの上に移動すると、**\<楕円**の色>アニメーションに変わります。</span><span class="sxs-lookup"><span data-stu-id="0f268-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![マウスを WPF ボタンの上に移動して塗りつぶしの色を変更する](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="0f268-203">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0f268-203">Next steps</span></span>

- [<span data-ttu-id="0f268-204">WPF でコントロールのスタイルを作成する</span><span class="sxs-lookup"><span data-stu-id="0f268-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="0f268-205">WPF のスタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="0f268-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0f268-206">XAML リソースの概要</span><span class="sxs-lookup"><span data-stu-id="0f268-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
