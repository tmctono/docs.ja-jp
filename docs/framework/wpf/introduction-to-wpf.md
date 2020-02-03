---
title: WPF の概要
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
dev_langs:
- csharp
- vb
ms.openlocfilehash: ecdd3b3c24b71917efb0d982d1f23737673622f9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744708"
---
# <a name="wpf-overview"></a><span data-ttu-id="1db77-102">WPF の概要</span><span class="sxs-lookup"><span data-stu-id="1db77-102">WPF overview</span></span>

<span data-ttu-id="1db77-103">Windows Presentation Foundation (WPF) を使用して、視覚的に美しいユーザー エクスペリエンスを持つ Windows 用のデスクトップ クライアント アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-103">Windows Presentation Foundation (WPF) lets you create desktop client applications for Windows with visually stunning user experiences.</span></span>

![Contoso Healthcare UI のサンプル](media/introduction-to-wpf/wpfintrofigure24.png)

<span data-ttu-id="1db77-105">WPF の中核を成すのは、解像度に依存しない、ベクター ベースのレンダリング エンジンであり、これは最新のグラフィックス ハードウェアを活用できるように構築されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-105">The core of WPF is a resolution-independent and vector-based rendering engine that is built to take advantage of modern graphics hardware.</span></span> <span data-ttu-id="1db77-106">この中核を拡張するため、WPF では、Extensible Application Markup Language (XAML)、コントロール、データ バインディング、レイアウト、2D および 3D グラフィックス、アニメーション、スタイル、テンプレート、ドキュメント、メディア、テキスト、タイポグラフィなどの、アプリケーション開発機能の包括的なセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1db77-106">WPF extends the core with a comprehensive set of application-development features that include Extensible Application Markup Language (XAML), controls, data binding, layout, 2D and 3D graphics, animation, styles, templates, documents, media, text, and typography.</span></span> <span data-ttu-id="1db77-107">WPF は .NET の一部です。そのため、.NET API の他の要素を組み込むアプリケーションを構築できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-107">WPF is part of .NET, so you can build applications that incorporate other elements of the .NET API.</span></span>

<span data-ttu-id="1db77-108">この概要は初めての方を対象としており、WPF の主要な機能と概念を説明します。</span><span class="sxs-lookup"><span data-stu-id="1db77-108">This overview is intended for newcomers and covers the key capabilities and concepts of WPF.</span></span>

## <a name="program-with-wpf"></a><span data-ttu-id="1db77-109">WPF でのプログラミング</span><span class="sxs-lookup"><span data-stu-id="1db77-109">Program with WPF</span></span>

<span data-ttu-id="1db77-110">WPF は、ほとんどの部分が <xref:System.Windows> 名前空間に格納されている .NET 型のサブセットとして存在します。</span><span class="sxs-lookup"><span data-stu-id="1db77-110">WPF exists as a subset of .NET types that are (for the most part) located in the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="1db77-111">ASP.NET や Windows フォームのようなマネージド テクノロジを使用して .NET で以前にアプリケーションを構築したことがあるユーザーは、基本的な WPF のプログラミングの経験には慣れているはずです。クラスのインスタンス化、プロパティの設定、メソッドの呼び出し、イベントの処理は C# または Visual Basic などの使い慣れた .NET プログラミング言語を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1db77-111">If you have previously built applications with .NET using managed technologies like ASP.NET and Windows Forms, the fundamental WPF programming experience should be familiar; you instantiate classes, set properties, call methods, and handle events, using your favorite .NET programming language, such as C# or Visual Basic.</span></span>

<span data-ttu-id="1db77-112">WPF には、プロパティとイベントを拡張する追加のプログラミング構成要素である、 [依存関係プロパティ](advanced/dependency-properties-overview.md) と [ルーティング イベント](advanced/routed-events-overview.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1db77-112">WPF includes additional programming constructs that enhance properties and events: [dependency properties](advanced/dependency-properties-overview.md) and [routed events](advanced/routed-events-overview.md).</span></span>

## <a name="markup-and-code-behind"></a><span data-ttu-id="1db77-113">マークアップおよび分離コード</span><span class="sxs-lookup"><span data-stu-id="1db77-113">Markup and code-behind</span></span>

<span data-ttu-id="1db77-114">WPF では "*マークアップ*" と "*分離コード*" の両方を使用したアプリケーションを開発できます。これは ASP.NET 開発者にとってなじみ深いエクスペリエンスに違いありません。</span><span class="sxs-lookup"><span data-stu-id="1db77-114">WPF lets you develop an application using both *markup* and *code-behind*, an experience with which ASP.NET developers should be familiar.</span></span> <span data-ttu-id="1db77-115">一般に、アプリケーションの外観を実装するには XAML マークアップを使用し、一方、その動作を実装するには、マネージド プログラミング言語 (分離コード) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1db77-115">You generally use XAML markup to implement the appearance of an application while using managed programming languages (code-behind) to implement its behavior.</span></span> <span data-ttu-id="1db77-116">外観と動作の実装を別々に行うことには、次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-116">This separation of appearance and behavior has the following benefits:</span></span>

- <span data-ttu-id="1db77-117">外観固有のマークアップが動作固有のコードと密接に結び付いていないので、開発と保守のコストが削減されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-117">Development and maintenance costs are reduced because appearance-specific markup is not tightly coupled with behavior-specific code.</span></span>

- <span data-ttu-id="1db77-118">デザイナーがアプリケーションの外観を実装しているとき同時に、開発者はアプリケーションの動作を実装できるため、開発がより効率的に進みます。</span><span class="sxs-lookup"><span data-stu-id="1db77-118">Development is more efficient because designers can implement an application's appearance simultaneously with developers who are implementing the application's behavior.</span></span>

- <span data-ttu-id="1db77-119">WPF アプリケーションの[グローバリゼーションとローカリゼーション](advanced/wpf-globalization-and-localization-overview.md) が簡略化します。</span><span class="sxs-lookup"><span data-stu-id="1db77-119">[Globalization and localization](advanced/wpf-globalization-and-localization-overview.md) for WPF applications is simplified.</span></span>

### <a name="markup"></a><span data-ttu-id="1db77-120">マークアップ</span><span class="sxs-lookup"><span data-stu-id="1db77-120">Markup</span></span>

<span data-ttu-id="1db77-121">XAML は、アプリケーションの外観を宣言的に実装する XML ベースのマークアップ言語です。</span><span class="sxs-lookup"><span data-stu-id="1db77-121">XAML is an XML-based markup language that implements an application's appearance declaratively.</span></span> <span data-ttu-id="1db77-122">一般的に、ウィンドウ、ダイアログ ボックス、ページ、ユーザー コントロールの作成と、これらにコントロール、図形、グラフィックスを入れるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-122">You typically use it to create windows, dialog boxes, pages, and user controls, and to fill them with controls, shapes, and graphics.</span></span>

<span data-ttu-id="1db77-123">次の例では、XAML を使用して、1つのボタンを含むウィンドウの外観を実装しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-123">The following example uses XAML to implement the appearance of a window that contains a single button:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

<span data-ttu-id="1db77-124">具体的には、この XAML は `Window` エレメントと `Button` エレメントを使用して、ウィンドウとボタンをそれぞれ定義しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-124">Specifically, this XAML defines a window and a button by using the `Window` and `Button` elements, respectively.</span></span> <span data-ttu-id="1db77-125">各エレメントは属性で構成されます。たとえば `Window` エレメントの `Title` 属性はウィンドウのタイトルバーのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="1db77-125">Each element is configured with attributes, such as the `Window` element's `Title` attribute to specify the window's title-bar text.</span></span> <span data-ttu-id="1db77-126">マークアップで定義されている要素と属性は、実行時に WPF により、WPF クラスのインスタンスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-126">At run time, WPF converts the elements and attributes that are defined in markup to instances of WPF classes.</span></span> <span data-ttu-id="1db77-127">たとえば、 `Window` エレメントは、 <xref:System.Windows.Window> プロパティが <xref:System.Windows.Window.Title%2A> 属性の値である `Title` クラスのインスタンスに変換されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-127">For example, the `Window` element is converted to an instance of the <xref:System.Windows.Window> class whose <xref:System.Windows.Window.Title%2A> property is the value of the `Title` attribute.</span></span>

<span data-ttu-id="1db77-128">次の図は、前の例の XAML で定義されているユーザーインターフェイス (UI) を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-128">The following figure shows the user interface (UI) that is defined by the XAML in the previous example:</span></span>

![ボタンを含むウィンドウ](media/introduction-to-wpf/wpfintrofigure10.png)

<span data-ttu-id="1db77-130">XAML は XML ベースなので、XAML を使用して作成する UI は [要素ツリー](advanced/trees-in-wpf.md)と呼ばれるネストされた要素の階層で組み立てられます。</span><span class="sxs-lookup"><span data-stu-id="1db77-130">Since XAML is XML-based, the UI that you compose with it is assembled in a hierarchy of nested elements known as an [element tree](advanced/trees-in-wpf.md).</span></span> <span data-ttu-id="1db77-131">要素ツリーは UI を作成し、管理するための論理的かつ直感的な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="1db77-131">The element tree provides a logical and intuitive way to create and manage UIs.</span></span>

### <a name="code-behind"></a><span data-ttu-id="1db77-132">コードビハインド</span><span class="sxs-lookup"><span data-stu-id="1db77-132">Code-behind</span></span>

<span data-ttu-id="1db77-133">アプリケーションの主な動作は、ユーザー インタラクションに対して応答する機能を実装することです。これにはイベントの処理 (メニュー、ツールバー、またはボタンをクリックする、など) および応答のビジネス ロジックやデータ アクセス ロジックの呼び出しなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1db77-133">The main behavior of an application is to implement the functionality that responds to user interactions, including handling events (for example, clicking a menu, tool bar, or button) and calling business logic and data access logic in response.</span></span> <span data-ttu-id="1db77-134">WPF では、この動作が、マークアップと関連付けられたコードで実装されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-134">In WPF, this behavior is implemented in code that is associated with markup.</span></span> <span data-ttu-id="1db77-135">このタイプのコードは分離コードと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="1db77-135">This type of code is known as code-behind.</span></span> <span data-ttu-id="1db77-136">次の例は、前の例の更新されたマークアップと分離コードを示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-136">The following example shows the updated markup from the previous example and the code-behind:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.AWindow"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button" Click="button_Click">Click Me!</Button>

</Window>
```

```csharp
using System.Windows; // Window, RoutedEventArgs, MessageBox 

namespace SDKSample
{
    public partial class AWindow : Window
    {
        public AWindow()
        {
            // InitializeComponent call is required to merge the UI 
            // that is defined in markup with this class, including  
            // setting properties and registering event handlers
            InitializeComponent();
        }

        void button_Click(object sender, RoutedEventArgs e)
        {
            // Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!");
        }
    }
}
```

```vb
Namespace SDKSample

    Partial Public Class AWindow
        Inherits System.Windows.Window

        Public Sub New()

            ' InitializeComponent call is required to merge the UI 
            ' that is defined in markup with this class, including  
            ' setting properties and registering event handlers
            InitializeComponent()

        End Sub 

        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)

            ' Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!")

        End Sub 

    End Class 

End Namespace
```

<span data-ttu-id="1db77-137">この例では、 <xref:System.Windows.Window> クラスから派生したクラスを分離コードが実装しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-137">In this example, the code-behind implements a class that derives from the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="1db77-138">マークアップを分離コード クラスと関連付けるために `x:Class` 属性が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-138">The `x:Class` attribute is used to associate the markup with the code-behind class.</span></span> <span data-ttu-id="1db77-139">分離コード クラスのコンストラクターから`InitializeComponent` が呼び出されて、マークアップで定義された UI を分離コード クラスとマージします。</span><span class="sxs-lookup"><span data-stu-id="1db77-139">`InitializeComponent` is called from the code-behind class's constructor to merge the UI that is defined in markup with the code-behind class.</span></span> <span data-ttu-id="1db77-140">(`InitializeComponent` は、アプリケーションがビルドされるときに生成されるため、手動で実装する必要はありません)。`x:Class` と `InitializeComponent` を組み合わせることにより、実装が作成されるたびに正しく初期化されるようになります。</span><span class="sxs-lookup"><span data-stu-id="1db77-140">(`InitializeComponent` is generated for you when your application is built, which is why you don't need to implement it manually.) The combination of `x:Class` and `InitializeComponent` ensure that your implementation is correctly initialized whenever it is created.</span></span> <span data-ttu-id="1db77-141">分離コード クラスはボタンの <xref:System.Windows.Controls.Primitives.ButtonBase.Click> イベントのイベント ハンドラーも実装します。</span><span class="sxs-lookup"><span data-stu-id="1db77-141">The code-behind class also implements an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span> <span data-ttu-id="1db77-142">ボタンがクリックされると、イベント ハンドラーは <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> メソッドを呼び出して、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-142">When the button is clicked, the event handler shows a message box by calling the <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> method.</span></span>

<span data-ttu-id="1db77-143">次の図は、ボタンがクリックされたときの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-143">The following figure shows the result when the button is clicked:</span></span>

![MessageBox](media/introduction-to-wpf/wpfintrofigure25.png)

## <a name="controls"></a><span data-ttu-id="1db77-145">コントロール</span><span class="sxs-lookup"><span data-stu-id="1db77-145">Controls</span></span>

<span data-ttu-id="1db77-146">アプリケーション モデルにより提供されるユーザー エクスペリエンスは、構築済みのコントロールです。</span><span class="sxs-lookup"><span data-stu-id="1db77-146">The user experiences that are delivered by the application model are constructed controls.</span></span> <span data-ttu-id="1db77-147">WPF において、"*コントロール*" とはウィンドウまたはページによりホストされ、ユーザー インターフェイスを持ち、何らかの動作を実装する WPF クラスのカテゴリに適用される総称です。</span><span class="sxs-lookup"><span data-stu-id="1db77-147">In WPF, *control* is an umbrella term that applies to a category of WPF classes that are hosted in either a window or a page, have a user interface, and implement some behavior.</span></span>

<span data-ttu-id="1db77-148">詳しくは、「 [コントロール](controls/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-148">For more information, see [Controls](controls/index.md).</span></span>

### <a name="wpf-controls-by-function"></a><span data-ttu-id="1db77-149">WPF コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="1db77-149">WPF controls by function</span></span>

<span data-ttu-id="1db77-150">組み込みの WPF コントロールを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-150">The built-in WPF controls are listed here:</span></span>

- <span data-ttu-id="1db77-151">**ボタン類**: <xref:System.Windows.Controls.Button> および <xref:System.Windows.Controls.Primitives.RepeatButton>。</span><span class="sxs-lookup"><span data-stu-id="1db77-151">**Buttons**: <xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.Primitives.RepeatButton>.</span></span>

- <span data-ttu-id="1db77-152">**データ表示**: <xref:System.Windows.Controls.DataGrid>、<xref:System.Windows.Controls.ListView>、および <xref:System.Windows.Controls.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="1db77-152">**Data Display**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, and <xref:System.Windows.Controls.TreeView>.</span></span>

- <span data-ttu-id="1db77-153">**日付表示と選択**: <xref:System.Windows.Controls.Calendar> および <xref:System.Windows.Controls.DatePicker>。</span><span class="sxs-lookup"><span data-stu-id="1db77-153">**Date Display and Selection**: <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>.</span></span>

- <span data-ttu-id="1db77-154">**ダイアログ ボックス**: <xref:Microsoft.Win32.OpenFileDialog>、 <xref:System.Windows.Controls.PrintDialog>、 <xref:Microsoft.Win32.SaveFileDialog>。</span><span class="sxs-lookup"><span data-stu-id="1db77-154">**Dialog Boxes**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, and <xref:Microsoft.Win32.SaveFileDialog>.</span></span>

- <span data-ttu-id="1db77-155">**デジタル インク**: <xref:System.Windows.Controls.InkCanvas> および <xref:System.Windows.Controls.InkPresenter>。</span><span class="sxs-lookup"><span data-stu-id="1db77-155">**Digital Ink**: <xref:System.Windows.Controls.InkCanvas> and <xref:System.Windows.Controls.InkPresenter>.</span></span>

- <span data-ttu-id="1db77-156">**ドキュメント**: <xref:System.Windows.Controls.DocumentViewer>、 <xref:System.Windows.Controls.FlowDocumentPageViewer>、 <xref:System.Windows.Controls.FlowDocumentReader>、 <xref:System.Windows.Controls.FlowDocumentScrollViewer>、 <xref:System.Windows.Controls.StickyNoteControl>。</span><span class="sxs-lookup"><span data-stu-id="1db77-156">**Documents**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, and <xref:System.Windows.Controls.StickyNoteControl>.</span></span>

- <span data-ttu-id="1db77-157">**入力**: <xref:System.Windows.Controls.TextBox>、 <xref:System.Windows.Controls.RichTextBox>、 <xref:System.Windows.Controls.PasswordBox>。</span><span class="sxs-lookup"><span data-stu-id="1db77-157">**Input**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Controls.PasswordBox>.</span></span>

- <span data-ttu-id="1db77-158">**レイアウト**: <xref:System.Windows.Controls.Border>、 <xref:System.Windows.Controls.Primitives.BulletDecorator>、 <xref:System.Windows.Controls.Canvas>、 <xref:System.Windows.Controls.DockPanel>、 <xref:System.Windows.Controls.Expander>、 <xref:System.Windows.Controls.Grid>、 <xref:System.Windows.Controls.GridView>、 <xref:System.Windows.Controls.GridSplitter>、 <xref:System.Windows.Controls.GroupBox>、 <xref:System.Windows.Controls.Panel>、 <xref:System.Windows.Controls.Primitives.ResizeGrip>、 <xref:System.Windows.Controls.Separator>、 <xref:System.Windows.Controls.Primitives.ScrollBar>、 <xref:System.Windows.Controls.ScrollViewer>、 <xref:System.Windows.Controls.StackPanel>、 <xref:System.Windows.Controls.Primitives.Thumb>、 <xref:System.Windows.Controls.Viewbox>、 <xref:System.Windows.Controls.VirtualizingStackPanel>、 <xref:System.Windows.Window>、 <xref:System.Windows.Controls.WrapPanel>。</span><span class="sxs-lookup"><span data-stu-id="1db77-158">**Layout**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, and <xref:System.Windows.Controls.WrapPanel>.</span></span>

- <span data-ttu-id="1db77-159">**メディア**: <xref:System.Windows.Controls.Image>、 <xref:System.Windows.Controls.MediaElement>、 <xref:System.Windows.Controls.SoundPlayerAction>。</span><span class="sxs-lookup"><span data-stu-id="1db77-159">**Media**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, and <xref:System.Windows.Controls.SoundPlayerAction>.</span></span>

- <span data-ttu-id="1db77-160">**メニュー類**: <xref:System.Windows.Controls.ContextMenu>、 <xref:System.Windows.Controls.Menu>、 <xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="1db77-160">**Menus**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, and <xref:System.Windows.Controls.ToolBar>.</span></span>

- <span data-ttu-id="1db77-161">**ナビゲーション**: <xref:System.Windows.Controls.Frame>、 <xref:System.Windows.Documents.Hyperlink>、 <xref:System.Windows.Controls.Page>、 <xref:System.Windows.Navigation.NavigationWindow>、 <xref:System.Windows.Controls.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="1db77-161">**Navigation**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, and <xref:System.Windows.Controls.TabControl>.</span></span>

- <span data-ttu-id="1db77-162">**選択**: <xref:System.Windows.Controls.CheckBox>、 <xref:System.Windows.Controls.ComboBox>、 <xref:System.Windows.Controls.ListBox>、 <xref:System.Windows.Controls.RadioButton>、 <xref:System.Windows.Controls.Slider>。</span><span class="sxs-lookup"><span data-stu-id="1db77-162">**Selection**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, and <xref:System.Windows.Controls.Slider>.</span></span>

- <span data-ttu-id="1db77-163">**ユーザー情報**: <xref:System.Windows.Controls.AccessText>、 <xref:System.Windows.Controls.Label>、 <xref:System.Windows.Controls.Primitives.Popup>、 <xref:System.Windows.Controls.ProgressBar>、 <xref:System.Windows.Controls.Primitives.StatusBar>、 <xref:System.Windows.Controls.TextBlock>、 <xref:System.Windows.Controls.ToolTip>。</span><span class="sxs-lookup"><span data-stu-id="1db77-163">**User Information**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.ToolTip>.</span></span>

## <a name="input-and-commands"></a><span data-ttu-id="1db77-164">入力とコマンド</span><span class="sxs-lookup"><span data-stu-id="1db77-164">Input and commands</span></span>

<span data-ttu-id="1db77-165">コントロールはほとんどの場合、ユーザー入力の検出と応答に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-165">Controls most often detect and respond to user input.</span></span> <span data-ttu-id="1db77-166">[WPF 入力システム](advanced/input-overview.md) では直接イベントとルーティング イベントの両方を使用して、テキスト入力、フォーカス管理、マウス位置指定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1db77-166">The [WPF input system](advanced/input-overview.md) uses both direct and routed events to support text input, focus management, and mouse positioning.</span></span>

<span data-ttu-id="1db77-167">アプリケーションにはたいてい、複雑な入力要件があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-167">Applications often have complex input requirements.</span></span> <span data-ttu-id="1db77-168">WPF には、ユーザー入力動作と、それらの動作に応答するコードを分離する [コマンド システム](advanced/commanding-overview.md) があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-168">WPF provides a [command system](advanced/commanding-overview.md) that separates user-input actions from the code that responds to those actions.</span></span>

## <a name="layout"></a><span data-ttu-id="1db77-169">[レイアウト]</span><span class="sxs-lookup"><span data-stu-id="1db77-169">Layout</span></span>

<span data-ttu-id="1db77-170">ユーザー インターフェイスを作成すると、場所とサイズによりコントロール類を配置して、レイアウトを決めます。</span><span class="sxs-lookup"><span data-stu-id="1db77-170">When you create a user interface, you arrange your controls by location and size to form a layout.</span></span> <span data-ttu-id="1db77-171">すべてのレイアウトの重要な要件は、ウィンドウ サイズと表示設定の変更に適応させることです。</span><span class="sxs-lookup"><span data-stu-id="1db77-171">A key requirement of any layout is to adapt to changes in window size and display settings.</span></span> <span data-ttu-id="1db77-172">こうした状況でレイアウトを適応させるために開発者にコードを作成させるのではなく、WPF では最上級の拡張可能なレイアウト システムを提供します。</span><span class="sxs-lookup"><span data-stu-id="1db77-172">Rather than forcing you to write the code to adapt a layout in these circumstances, WPF provides a first-class, extensible layout system for you.</span></span>

<span data-ttu-id="1db77-173">レイアウト システムの要となるのは、相対的な位置指定です。これにより、ウィンドウや表示条件の変化への適応性が高まります。</span><span class="sxs-lookup"><span data-stu-id="1db77-173">The cornerstone of the layout system is relative positioning, which increases the ability to adapt to changing window and display conditions.</span></span> <span data-ttu-id="1db77-174">さらに、レイアウト システムは各コントロール間のネゴシエーションを管理して、レイアウトを決定します。</span><span class="sxs-lookup"><span data-stu-id="1db77-174">In addition, the layout system manages the negotiation between controls to determine the layout.</span></span> <span data-ttu-id="1db77-175">このネゴシエーションは 2 段階のプロセスで行われます。まず、コントロールがその親に対して、必要な場所とサイズを伝えます。次に、親コントロールはどれぐらいの空間を持てるかを子コントロールに伝えます。</span><span class="sxs-lookup"><span data-stu-id="1db77-175">The negotiation is a two-step process: first, a control tells its parent what location and size it requires; second, the parent tells the control what space it can have.</span></span>

<span data-ttu-id="1db77-176">レイアウト システムは基本の WPF クラスを介して子コントロールに公開されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-176">The layout system is exposed to child controls through base WPF classes.</span></span> <span data-ttu-id="1db77-177">グリッド、スタック、ドックなどの一般的なレイアウトについて、WPF には複数のレイアウト コントロールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="1db77-177">For common layouts such as grids, stacking, and docking, WPF includes several layout controls:</span></span>

- <span data-ttu-id="1db77-178"><xref:System.Windows.Controls.Canvas>: 子コントロールは独自のレイアウトを提供します。</span><span class="sxs-lookup"><span data-stu-id="1db77-178"><xref:System.Windows.Controls.Canvas>: Child controls provide their own layout.</span></span>

- <span data-ttu-id="1db77-179"><xref:System.Windows.Controls.DockPanel>: 子コントロールはパネルの縁に並べられます。</span><span class="sxs-lookup"><span data-stu-id="1db77-179"><xref:System.Windows.Controls.DockPanel>: Child controls are aligned to the edges of the panel.</span></span>

- <span data-ttu-id="1db77-180"><xref:System.Windows.Controls.Grid>: 子コントロールは行ごと、列ごとに位置指定されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-180"><xref:System.Windows.Controls.Grid>: Child controls are positioned by rows and columns.</span></span>

- <span data-ttu-id="1db77-181"><xref:System.Windows.Controls.StackPanel>: 子コントロールは垂直方向または水平方向に積み上げられます。</span><span class="sxs-lookup"><span data-stu-id="1db77-181"><xref:System.Windows.Controls.StackPanel>: Child controls are stacked either vertically or horizontally.</span></span>

- <span data-ttu-id="1db77-182"><xref:System.Windows.Controls.VirtualizingStackPanel>: 子コントロールは仮想化され、水平方向または垂直方向の 1 本の線上に配置されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-182"><xref:System.Windows.Controls.VirtualizingStackPanel>: Child controls are virtualized and arranged on a single line that is either horizontally or vertically oriented.</span></span>

- <span data-ttu-id="1db77-183"><xref:System.Windows.Controls.WrapPanel>: 子コントロールは左から右への順序に配置され、現在の行に納まらない場合は、次の行に折り返されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-183"><xref:System.Windows.Controls.WrapPanel>: Child controls are positioned in left-to-right order and wrapped to the next line when there are more controls on the current line than space allows.</span></span>

<span data-ttu-id="1db77-184">次の例では、<xref:System.Windows.Controls.DockPanel> を使用して、複数の <xref:System.Windows.Controls.TextBox> コントロールをレイアウトします。</span><span class="sxs-lookup"><span data-stu-id="1db77-184">The following example uses a <xref:System.Windows.Controls.DockPanel> to lay out several <xref:System.Windows.Controls.TextBox> controls:</span></span>

[!code-xaml[IntroToWPFSnippets#LayoutMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_1.xaml)]

<span data-ttu-id="1db77-185"><xref:System.Windows.Controls.DockPanel> により、子 <xref:System.Windows.Controls.TextBox> コントロールはどのように配置するかを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="1db77-185">The <xref:System.Windows.Controls.DockPanel> allows the child <xref:System.Windows.Controls.TextBox> controls to tell it how to arrange them.</span></span> <span data-ttu-id="1db77-186">このために、<xref:System.Windows.Controls.DockPanel> は `Dock` 添付プロパティを実装しています。このプロパティが子コントロールに公開されて、それぞれのコントロールがドック スタイルを指定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1db77-186">To do this, the <xref:System.Windows.Controls.DockPanel> implements a `Dock` attached property that is exposed to the child controls to allow each of them to specify a dock style.</span></span>

> [!NOTE]
> <span data-ttu-id="1db77-187">子コントロールで使用するために親コントロールにより実装されるプロパティは、[添付プロパティ](advanced/attached-properties-overview.md)と呼ばれる WPF 構成要素です。</span><span class="sxs-lookup"><span data-stu-id="1db77-187">A property that's implemented by a parent control for use by child controls is a WPF construct called an [attached property](advanced/attached-properties-overview.md).</span></span>

<span data-ttu-id="1db77-188">次の図は、前の例の XAML マークアップの結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-188">The following figure shows the result of the XAML markup in the preceding example:</span></span>

![DockPanel ページ](media/introduction-to-wpf/wpfintrofigure11.png)

## <a name="data-binding"></a><span data-ttu-id="1db77-190">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="1db77-190">Data binding</span></span>

<span data-ttu-id="1db77-191">ほとんどのアプリケーションは、データの表示と編集の手段をユーザーに提供するために作成されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-191">Most applications are created to provide users with the means to view and edit data.</span></span> <span data-ttu-id="1db77-192">WPF アプリケーションの場合、データ格納とアクセスの機能は、SQL Server や ADO .NET などのテクノロジにより、すでに提供されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-192">For WPF applications, the work of storing and accessing data is already provided for by technologies such as SQL Server and ADO .NET.</span></span> <span data-ttu-id="1db77-193">データがアクセスされ、アプリケーションの管理対象オブジェクトに読み込まれると、WPF アプリケーションの処理が開始します。</span><span class="sxs-lookup"><span data-stu-id="1db77-193">After the data is accessed and loaded into an application's managed objects, the hard work for WPF applications begins.</span></span> <span data-ttu-id="1db77-194">基本的に、これには 2 つの処理が伴います。</span><span class="sxs-lookup"><span data-stu-id="1db77-194">Essentially, this involves two things:</span></span>

1. <span data-ttu-id="1db77-195">管理対象のオブジェクトからコントロールにデータをコピーします。これらのコントロールで、データを表示および編集できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-195">Copying the data from the managed objects into controls, where the data can be displayed and edited.</span></span>

2. <span data-ttu-id="1db77-196">コントロールを使用してデータに対して行う変更が、必ず管理対象オブジェクトにもう一度コピーされるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1db77-196">Ensuring that changes made to data by using controls are copied back to the managed objects.</span></span>

<span data-ttu-id="1db77-197">アプリケーションの開発を簡素化するために、WPF にはこれらの手順を自動的に実行する、データ バインディング エンジンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-197">To simplify application development, WPF provides a data binding engine to automatically perform these steps.</span></span> <span data-ttu-id="1db77-198">データ バインディング エンジンの中核となる単位は <xref:System.Windows.Data.Binding> クラスであり、その仕事はコントロール (バインディング ターゲット) をデータ オブジェクト (バインディング ソース) にバインドすることです。</span><span class="sxs-lookup"><span data-stu-id="1db77-198">The core unit of the data binding engine is the <xref:System.Windows.Data.Binding> class, whose job is to bind a control (the binding target) to a data object (the binding source).</span></span> <span data-ttu-id="1db77-199">この関係を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-199">This relationship is illustrated by the following figure:</span></span>

![基本的なデータ バインディング ダイアグラム](media/introduction-to-wpf/databindingmostbasic.png)

<span data-ttu-id="1db77-201">次の例は、<xref:System.Windows.Controls.TextBox> をカスタム `Person` オブジェクトのインスタンスにバインドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-201">The next example demonstrates how to bind a <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object.</span></span> <span data-ttu-id="1db77-202">`Person` の実装を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-202">The `Person` implementation is shown in the following code:</span></span>

[!code-vb[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_2.vb)]
[!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_2.cs)]

<span data-ttu-id="1db77-203">次のマークアップは、<xref:System.Windows.Controls.TextBox> をカスタム `Person` オブジェクトのインスタンスにバインドします。</span><span class="sxs-lookup"><span data-stu-id="1db77-203">The following markup binds the <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object:</span></span>

```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
```

[!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_6.vb)]
[!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_6.cs)]

<span data-ttu-id="1db77-204">この例で、 `Person` クラスは、分離コードでインスタンス化され、 `DataBindingWindow`のデータ コンテキストとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-204">In this example, the `Person` class is instantiated in code-behind and is set as the data context for the `DataBindingWindow`.</span></span> <span data-ttu-id="1db77-205">マークアップでは、 <xref:System.Windows.Controls.TextBox.Text%2A> の <xref:System.Windows.Controls.TextBox> プロパティが、 `Person.Name` プロパティにバインドされます ("`{Binding ... }`" XAML 構文を使用)。</span><span class="sxs-lookup"><span data-stu-id="1db77-205">In markup, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> is bound to the `Person.Name` property (using the "`{Binding ... }`" XAML syntax).</span></span> <span data-ttu-id="1db77-206">この XAML は WPF に対して、ウィンドウの <xref:System.Windows.Controls.TextBox> プロパティに格納されている `Person` オブジェクトに、 <xref:System.Windows.FrameworkElement.DataContext%2A> コントロールをバインドするよう、指示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-206">This XAML tells WPF to bind the <xref:System.Windows.Controls.TextBox> control to the `Person` object that is stored in the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the window.</span></span>

<span data-ttu-id="1db77-207">WPF データ バインディング エンジンは、検証、並べ替え、フィルター処理、グループ化などのその他のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="1db77-207">The WPF data binding engine provides additional support that includes validation, sorting, filtering, and grouping.</span></span> <span data-ttu-id="1db77-208">さらにデータ バインディングでは、標準の WPF コントロールによって表示されたユーザー インターフェイスが適切ではない場合に、バインドされたデータを操作するためのカスタム ユーザー インターフェイスをデータ テンプレートで作成することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1db77-208">Furthermore, data binding supports the use of data templates to create custom user interface for bound data when the user interface displayed by the standard WPF controls is not appropriate.</span></span>

<span data-ttu-id="1db77-209">詳しくは、「[データ バインディングの概要](../../desktop-wpf/data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-209">For more information, see [Data binding overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="graphics"></a><span data-ttu-id="1db77-210">グラフィックス</span><span class="sxs-lookup"><span data-stu-id="1db77-210">Graphics</span></span>

<span data-ttu-id="1db77-211">WPF では次の利点を備えた、広範囲にわたるスケーラブルで柔軟なグラフィックス機能セットが導入されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-211">WPF introduces an extensive, scalable, and flexible set of graphics features that have the following benefits:</span></span>

- <span data-ttu-id="1db77-212">**解像度にもデバイスにも依存しないグラフィックス**。</span><span class="sxs-lookup"><span data-stu-id="1db77-212">**Resolution-independent and device-independent graphics**.</span></span> <span data-ttu-id="1db77-213">WPF グラフィックス システムでの測定値の基本単位は、デバイスに依存しないピクセル、すなわち 1 インチの 1/96 であり、実際の画面解像度には関係ありません。このため、解像度にもデバイスにも依存しないレンダリングの基盤が提供されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-213">The basic unit of measurement in the WPF graphics system is the device-independent pixel, which is 1/96th of an inch, regardless of actual screen resolution, and provides the foundation for resolution-independent and device-independent rendering.</span></span> <span data-ttu-id="1db77-214">デバイスに依存しない各ピクセルは、レンダリングを行うシステムのドット/インチ (dpi) 設定に合うように、自動的にスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="1db77-214">Each device-independent pixel automatically scales to match the dots-per-inch (dpi) setting of the system it renders on.</span></span>

- <span data-ttu-id="1db77-215">**精度の向上**。</span><span class="sxs-lookup"><span data-stu-id="1db77-215">**Improved precision**.</span></span> <span data-ttu-id="1db77-216">WPF の座標系は、単精度ではなく、倍精度浮動小数点数で測定されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-216">The WPF coordinate system is measured with double-precision floating-point numbers rather than single-precision.</span></span> <span data-ttu-id="1db77-217">変換および不透明度の値も倍精度で表現されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-217">Transformations and opacity values are also expressed as double-precision.</span></span> <span data-ttu-id="1db77-218">また、WPF は、広色域 (scRGB) に対応しており、異なる色空間からの入力を管理する統合サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="1db77-218">WPF also supports a wide color gamut (scRGB) and provides integrated support for managing inputs from different color spaces.</span></span>

- <span data-ttu-id="1db77-219">**高度なグラフィックスおよびアニメーションのサポート**。</span><span class="sxs-lookup"><span data-stu-id="1db77-219">**Advanced graphics and animation support**.</span></span> <span data-ttu-id="1db77-220">WPF はアニメーションのシーンを管理してグラフィックスのプログラミングを簡略化します。シーンの処理、レンダリング ループ、バイリニア補間について心配する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1db77-220">WPF simplifies graphics programming by managing animation scenes for you; there is no need to worry about scene processing, rendering loops, and bilinear interpolation.</span></span> <span data-ttu-id="1db77-221">WPF はさらに、ヒット テストのサポートとアルファ合成の完全なサポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-221">Additionally, WPF provides hit-testing support and full alpha-compositing support.</span></span>

- <span data-ttu-id="1db77-222">**ハードウェアの高速化**</span><span class="sxs-lookup"><span data-stu-id="1db77-222">**Hardware acceleration**.</span></span> <span data-ttu-id="1db77-223">WPF グラフィックス システムでは、CPU 使用率を最小限に抑えるためにグラフィックス ハードウェアを利用します。</span><span class="sxs-lookup"><span data-stu-id="1db77-223">The WPF graphics system takes advantage of graphics hardware to minimize CPU usage.</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="1db77-224">2D 図形</span><span class="sxs-lookup"><span data-stu-id="1db77-224">2D shapes</span></span>

<span data-ttu-id="1db77-225">WPF には、次の図に示す四角形や楕円のような、一般的なベクター描画による 2D 図形のライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-225">WPF provides a library of common vector-drawn 2D shapes, such as the rectangles and ellipses that are shown in the following illustration:</span></span>

![楕円と四角形](media/introduction-to-wpf/wpfintrofigure4.PNG)

<span data-ttu-id="1db77-227">図形の興味深い機能は、単に表示するだけのものではないところです。図形はコントロールに期待される多くの機能 (キーボード入力とマウス入力を含む) を実装します。</span><span class="sxs-lookup"><span data-stu-id="1db77-227">An interesting capability of shapes is that they are not just for display; shapes implement many of the features that you expect from controls, including keyboard and mouse input.</span></span> <span data-ttu-id="1db77-228">次の例は、処理される <xref:System.Windows.Shapes.Ellipse> の <xref:System.Windows.UIElement.MouseUp> イベントを示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-228">The following example shows the <xref:System.Windows.UIElement.MouseUp> event of an <xref:System.Windows.Shapes.Ellipse> being handled:</span></span>

[!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_7.xaml)]

[!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_8.vb)]
[!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_8.cs)]

<span data-ttu-id="1db77-229">次の図は、上記のコードによって生成される内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-229">The following figure shows what is produced by the preceding code:</span></span>

!["you clicked the ellipse&#33;" というテキストを含むウィンドウ](media/introduction-to-wpf/wpfintrofigure12.png)

<span data-ttu-id="1db77-231">詳しくは、「[WPF での図形と基本描画の概要](../../desktop-wpf/data/data-binding-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-231">For more information, see [Shapes and basic drawing in WPF overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="1db77-232">2D ジオメトリ</span><span class="sxs-lookup"><span data-stu-id="1db77-232">2D geometries</span></span>

<span data-ttu-id="1db77-233">WPF で提供される 2D 図形では、基本的な図形の標準セットが網羅されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-233">The 2D shapes provided by WPF cover the standard set of basic shapes.</span></span> <span data-ttu-id="1db77-234">ただし、カスタマイズされたユーザー インターフェイスを容易に設計するには、カスタム図形を作成しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-234">However, you may need to create custom shapes to facilitate the design of a customized user interface.</span></span> <span data-ttu-id="1db77-235">このため、WPF ではジオメトリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-235">For this purpose, WPF provides geometries.</span></span> <span data-ttu-id="1db77-236">次の図では、直接描画、ブラシとして使用、または他の図形やコントロールをクリップするために使用できるカスタム図形を作成するジオメトリの使用法を示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-236">The following figure demonstrates the use of geometries to create a custom shape that can be drawn directly, used as a brush, or used to clip other shapes and controls.</span></span>

<span data-ttu-id="1db77-237"><xref:System.Windows.Shapes.Path> オブジェクトは、閉じているまたは開いている図形、複数の図形、さらに曲線図形の描画に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-237"><xref:System.Windows.Shapes.Path> objects can be used to draw closed or open shapes, multiple shapes, and even curved shapes.</span></span>

<span data-ttu-id="1db77-238"><xref:System.Windows.Media.Geometry> オブジェクトは、クリップ、ヒット テスト、2D グラフィック データのレンダリングに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-238"><xref:System.Windows.Media.Geometry> objects can be used for clipping, hit-testing, and rendering 2D graphic data.</span></span>

![パスのさまざまな使用](media/introduction-to-wpf/wpfintrofigure5.png)

<span data-ttu-id="1db77-240">詳しくは、「[ジオメトリの概要](graphics-multimedia/geometry-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-240">For more information, see [Geometry overview](graphics-multimedia/geometry-overview.md).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="1db77-241">2D 効果</span><span class="sxs-lookup"><span data-stu-id="1db77-241">2D effects</span></span>

<span data-ttu-id="1db77-242">WPF の 2D 機能のサブセットには、グラデーション、ビットマップ、描画、ビデオによる塗りつぶし、回転、スケーリング、傾斜などの視覚効果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1db77-242">A subset of WPF 2D capabilities includes visual effects, such as gradients, bitmaps, drawings, painting with videos, rotation, scaling, and skewing.</span></span> <span data-ttu-id="1db77-243">これらはすべて、ブラシを使用して実現されます。次の図は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-243">These are all achieved with brushes; the following figure shows some examples:</span></span>

![さまざまなブラシの図](media/introduction-to-wpf/wpfintrofigure6.png)

<span data-ttu-id="1db77-245">詳しくは、「[WPF のブラシの概要](graphics-multimedia/wpf-brushes-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-245">For more information, see [WPF brushes overview](graphics-multimedia/wpf-brushes-overview.md).</span></span>

### <a name="3d-rendering"></a><span data-ttu-id="1db77-246">3D レンダリング</span><span class="sxs-lookup"><span data-stu-id="1db77-246">3D rendering</span></span>

<span data-ttu-id="1db77-247">WPF には 2D グラフィックスと統合し、より魅力的で興味深いユーザー インターフェイスを作成できる 3D レンダリング機能も含まれています。</span><span class="sxs-lookup"><span data-stu-id="1db77-247">WPF also includes 3D rendering capabilities that integrate with 2-d graphics to allow the creation of more exciting and interesting user interfaces.</span></span> <span data-ttu-id="1db77-248">たとえば、次の図は、3D 図形にレンダリングされる2D イメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-248">For example, the following figure shows 2D images rendered onto 3D shapes:</span></span>

![Visual3D サンプルのスクリーンショット](media/introduction-to-wpf/wpfintrofigure13.png)

<span data-ttu-id="1db77-250">詳細については、「[3D グラフィックスの概要](graphics-multimedia/3-d-graphics-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1db77-250">For more information, see [3D graphics overview](graphics-multimedia/3-d-graphics-overview.md).</span></span>

## <a name="animation"></a><span data-ttu-id="1db77-251">アニメーション</span><span class="sxs-lookup"><span data-stu-id="1db77-251">Animation</span></span>

<span data-ttu-id="1db77-252">WPF のアニメーション サポートを使用すると、コントロールを拡大、振動、スピン、フェードさせることができ、魅力的なページ遷移などを作成できです。</span><span class="sxs-lookup"><span data-stu-id="1db77-252">WPF animation support lets you make controls grow, shake, spin, and fade, to create interesting page transitions, and more.</span></span> <span data-ttu-id="1db77-253">カスタム クラスも含めて、ほとんどの WPF クラスをアニメーション表示できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-253">You can animate most WPF classes, even custom classes.</span></span> <span data-ttu-id="1db77-254">次の図は、動作中の単純なアニメーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-254">The following figure shows a simple animation in action:</span></span>

![アニメーション キューブのイメージ](media/introduction-to-wpf/wpfintrofigure7.png)

<span data-ttu-id="1db77-256">詳しくは、「[アニメーションの概要](graphics-multimedia/animation-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-256">For more information, see [Animation overview](graphics-multimedia/animation-overview.md).</span></span>

## <a name="media"></a><span data-ttu-id="1db77-257">メディア</span><span class="sxs-lookup"><span data-stu-id="1db77-257">Media</span></span>

<span data-ttu-id="1db77-258">リッチ コンテンツを伝達するための 1 つの方法は、オーディオビジュアル メディアを使用することです。</span><span class="sxs-lookup"><span data-stu-id="1db77-258">One way to convey rich content is through the use of audiovisual media.</span></span> <span data-ttu-id="1db77-259">WPF では、イメージ、ビデオ、オーディオに対して特別なサポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-259">WPF provides special support for images, video, and audio.</span></span>

### <a name="images"></a><span data-ttu-id="1db77-260">イメージ</span><span class="sxs-lookup"><span data-stu-id="1db77-260">Images</span></span>

<span data-ttu-id="1db77-261">イメージは、ほとんどのアプリケーションに共通していますが、WPF にはイメージを使用するための、いくつかの方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-261">Images are common to most applications, and WPF provides several ways to use them.</span></span> <span data-ttu-id="1db77-262">次の図に、サムネイル イメージが含まれているリスト ボックスがある、ユーザー インターフェイスを示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-262">The following figure shows a user interface with a list box that contains thumbnail images.</span></span> <span data-ttu-id="1db77-263">サムネイルを選ぶと、そのイメージがフル サイズで表示されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-263">When a thumbnail is selected, the image is shown full-size.</span></span>

![サムネイル イメージとフルサイズのイメージ](media/introduction-to-wpf/wpfintrofigure8.png)

<span data-ttu-id="1db77-265">詳しくは、「[イメージングの概要](graphics-multimedia/imaging-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-265">For more information, see [Imaging overview](graphics-multimedia/imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="1db77-266">ビデオとオーディオ</span><span class="sxs-lookup"><span data-stu-id="1db77-266">Video and audio</span></span>

<span data-ttu-id="1db77-267"><xref:System.Windows.Controls.MediaElement> コントロールは、オーディオとビデオの両方を再生でき、カスタム メディア プレーヤーの土台となれる柔軟性を備えています。</span><span class="sxs-lookup"><span data-stu-id="1db77-267">The <xref:System.Windows.Controls.MediaElement> control is capable of playing both video and audio, and it is flexible enough to be the basis for a custom media player.</span></span> <span data-ttu-id="1db77-268">次の XAML マークアップは、メディアプレーヤーを実装します。</span><span class="sxs-lookup"><span data-stu-id="1db77-268">The following XAML markup implements a media player:</span></span>

[!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_9.xaml)]

<span data-ttu-id="1db77-269">次の図のウィンドウは、動作中の <xref:System.Windows.Controls.MediaElement> コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-269">The window in the following figure shows the <xref:System.Windows.Controls.MediaElement> control in action:</span></span>

![オーディオおよびビデオを含む MediaElement コントロール](media/introduction-to-wpf/wpfintrofigure1.png)

<span data-ttu-id="1db77-271">詳細については、「[グラフィックスとマルチメディア](graphics-multimedia/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1db77-271">For more information, see [Graphics and multimedia](graphics-multimedia/index.md).</span></span>

## <a name="text-and-typography"></a><span data-ttu-id="1db77-272">テキストとタイポグラフィ</span><span class="sxs-lookup"><span data-stu-id="1db77-272">Text and typography</span></span>

<span data-ttu-id="1db77-273">高品質のテキスト レンダリングを容易に行うために、WPF では次の機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-273">To facilitate high-quality text rendering, WPF offers the following features:</span></span>

- <span data-ttu-id="1db77-274">OpenType フォントのサポート。</span><span class="sxs-lookup"><span data-stu-id="1db77-274">OpenType font support.</span></span>

- <span data-ttu-id="1db77-275">ClearType 機能拡張。</span><span class="sxs-lookup"><span data-stu-id="1db77-275">ClearType enhancements.</span></span>

- <span data-ttu-id="1db77-276">ハードウェアの高速化を利用する高パフォーマンス。</span><span class="sxs-lookup"><span data-stu-id="1db77-276">High performance that takes advantage of hardware acceleration.</span></span>

- <span data-ttu-id="1db77-277">テキストと、メディア、グラフィックス、アニメーションとの統合。</span><span class="sxs-lookup"><span data-stu-id="1db77-277">Integration of text with media, graphics, and animation.</span></span>

- <span data-ttu-id="1db77-278">国際対応フォントのサポートとフォールバック メカニズム。</span><span class="sxs-lookup"><span data-stu-id="1db77-278">International font support and fallback mechanisms.</span></span>

<span data-ttu-id="1db77-279">グラフィックスとのテキストの統合のデモとして、次の図は、文字装飾の適用を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-279">As a demonstration of text integration with graphics, the following figure shows the application of text decorations:</span></span>

![さまざまなテキスト装飾を含むテキスト](media/introduction-to-wpf/wpfintrofigure23.png)

<span data-ttu-id="1db77-281">詳しくは、「 [Windows Presentation Foundation のタイポグラフィ](advanced/typography-in-wpf.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-281">For more information, see [Typography in Windows Presentation Foundation](advanced/typography-in-wpf.md).</span></span>

## <a name="customize-wpf-apps"></a><span data-ttu-id="1db77-282">WPF アプリをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="1db77-282">Customize WPF apps</span></span>

<span data-ttu-id="1db77-283">ここまで、アプリケーションを開発するための中核となる WPF 構成要素を説明してきました。</span><span class="sxs-lookup"><span data-stu-id="1db77-283">Up to this point, you've seen the core WPF building blocks for developing applications.</span></span> <span data-ttu-id="1db77-284">主にコントロールから成るアプリケーション コンテンツをホストして提供するには、アプリケーション モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1db77-284">You use the application model to host and deliver application content, which consists mainly of controls.</span></span> <span data-ttu-id="1db77-285">ユーザー インターフェイスでのコントロールの配置を簡素化して、ウィンドウ サイズや表示設定に変更が発生した場合にも配置を維持するには、WPF レイアウト システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="1db77-285">To simplify the arrangement of controls in a user interface, and to ensure the arrangement is maintained in the face of changes to window size and display settings, you use the WPF layout system.</span></span> <span data-ttu-id="1db77-286">ほとんどのアプリケーションでは、ユーザーがデータと対話できるようになっているため、データ バインディングを使用すればユーザー インターフェイスとデータの統合作業を削減できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-286">Because most applications let users interact with data, you use data binding to reduce the work of integrating your user interface with data.</span></span> <span data-ttu-id="1db77-287">アプリケーションの外観を向上させるには、WPF が提供する幅広いグラフィックス、アニメーション、メディアのサポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="1db77-287">To enhance the visual appearance of your application, you use the comprehensive range of graphics, animation, and media support provided by WPF.</span></span>

<span data-ttu-id="1db77-288">ただし多くの場合、基本要素だけでは、真に個性的で視覚的に美しいユーザー エクスペリエンスを作成し、管理するには不十分です。</span><span class="sxs-lookup"><span data-stu-id="1db77-288">Often, though, the basics are not enough for creating and managing a truly distinct and visually stunning user experience.</span></span> <span data-ttu-id="1db77-289">標準の WPF コントロールでは、アプリケーションの目的の外観にはそぐわない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-289">The standard WPF controls might not integrate with the desired appearance of your application.</span></span> <span data-ttu-id="1db77-290">最も効果的な方法でデータを表示できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-290">Data might not be displayed in the most effective way.</span></span> <span data-ttu-id="1db77-291">アプリケーションの全体的なユーザー エクスペリエンスが、Windows のテーマの既定のルック アンド フィールに適合しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-291">Your application's overall user experience may not be suited to the default look and feel of Windows themes.</span></span> <span data-ttu-id="1db77-292">多くの点で、プレゼンテーション技術には他の種類の機能拡張と同様、視覚的な機能拡張性が必要です。</span><span class="sxs-lookup"><span data-stu-id="1db77-292">In many ways, a presentation technology needs visual extensibility as much as any other type of extensibility.</span></span>

<span data-ttu-id="1db77-293">このため、WPF には独自のユーザー エクスペリエンスを作成するためのさまざまなメカニズムが用意されています。コントロール、トリガー、コントロールとデータのテンプレート、スタイル、ユーザー インターフェイスのリソース、テーマとスキン用の豊富なコンテンツ モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="1db77-293">For this reason, WPF provides a variety of mechanisms for creating unique user experiences, including a rich content model for controls, triggers, control and data templates, styles, user interface resources, and themes and skins.</span></span>

### <a name="content-model"></a><span data-ttu-id="1db77-294">コンテンツ モデル</span><span class="sxs-lookup"><span data-stu-id="1db77-294">Content model</span></span>

<span data-ttu-id="1db77-295">大半の WPF コントロールの主な目的はコンテンツを表示することです。</span><span class="sxs-lookup"><span data-stu-id="1db77-295">The main purpose of a majority of the WPF controls is to display content.</span></span> <span data-ttu-id="1db77-296">WPF では、コントロールのコンテンツを構成するアイテムの種類と数を、コントロールの *コンテンツ モデル*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="1db77-296">In WPF, the type and number of items that can constitute the content of a control is referred to as the control's *content model*.</span></span> <span data-ttu-id="1db77-297">一部のコントロールには、1 つのアイテムと種類のコンテンツを含めることができます。たとえば、 <xref:System.Windows.Controls.TextBox> のコンテンツは <xref:System.Windows.Controls.TextBox.Text%2A> プロパティに割り当てられている文字列値です。</span><span class="sxs-lookup"><span data-stu-id="1db77-297">Some controls can contain a single item and type of content; for example, the content of a <xref:System.Windows.Controls.TextBox> is a string value that is assigned to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="1db77-298">次の例では、<xref:System.Windows.Controls.TextBox>の内容を設定します。</span><span class="sxs-lookup"><span data-stu-id="1db77-298">The following example sets the content of a <xref:System.Windows.Controls.TextBox>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">

    <TextBox Text="This is the content of a TextBox." />
</Window>
```

<span data-ttu-id="1db77-299">結果を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-299">The following figure shows the result:</span></span>

![テキストを含む TextBox コントロール](media/introduction-to-wpf/wpfintrofigure21.png)

<span data-ttu-id="1db77-301">しかし、さまざまな種類の複数のアイテムのコンテンツを含めることができるコントロールもあります。 <xref:System.Windows.Controls.Button>プロパティで指定された <xref:System.Windows.Controls.ContentControl.Content%2A> のコンテンツには、レイアウト コントロール、テキスト、画像、図形などのさまざまなアイテムを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1db77-301">Other controls, however, can contain multiple items of different types of content; the content of a <xref:System.Windows.Controls.Button>, specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property, can contain a variety of items including layout controls, text, images, and shapes.</span></span> <span data-ttu-id="1db77-302">次の例は、<xref:System.Windows.Controls.DockPanel>、<xref:System.Windows.Controls.Label>、<xref:System.Windows.Controls.Border>、および <xref:System.Windows.Controls.MediaElement>を含むコンテンツを含む <xref:System.Windows.Controls.Button> を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-302">The following example shows a <xref:System.Windows.Controls.Button> with content that includes a <xref:System.Windows.Controls.DockPanel>, a <xref:System.Windows.Controls.Label>, a <xref:System.Windows.Controls.Border>, and a <xref:System.Windows.Controls.MediaElement>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ButtonContentWindow"
    Title="Button Content">

  <Button Margin="20">
    <!-- Button Content -->
    <DockPanel Width="200" Height="180">
      <Label DockPanel.Dock="Top" HorizontalAlignment="Center">Click Me!</Label>
      <Border Background="Black" BorderBrush="Yellow" BorderThickness="2"
        CornerRadius="2" Margin="5">
        <MediaElement Source="media/wpf.wmv" Stretch="Fill" />
      </Border>
    </DockPanel>
  </Button>
</Window>
```

<span data-ttu-id="1db77-303">次の図は、このボタンの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-303">The following figure shows the content of this button:</span></span>

![複数の種類の内容を含むボタン](media/introduction-to-wpf/wpfintrofigure22.png)

<span data-ttu-id="1db77-305">さまざまなコントロールでサポートされているコンテンツの種類について詳しくは、「[WPF コンテンツ モデル](controls/wpf-content-model.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-305">For more information on the kinds of content that is supported by various controls, see [WPF content model](controls/wpf-content-model.md).</span></span>

### <a name="triggers"></a><span data-ttu-id="1db77-306">トリガー</span><span class="sxs-lookup"><span data-stu-id="1db77-306">Triggers</span></span>

<span data-ttu-id="1db77-307">XAML マークアップの主な目的はアプリケーションの外観を実装することですが、XAML を使用してアプリケーションの動作の一部の機能を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="1db77-307">Although the main purpose of XAML markup is to implement an application's appearance, you can also use XAML to implement some aspects of an application's behavior.</span></span> <span data-ttu-id="1db77-308">その一例として、ユーザーの操作に基づいて、アプリケーションの外観を変更するトリガーの使用があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-308">One example is the use of triggers to change an application's appearance based on user interactions.</span></span> <span data-ttu-id="1db77-309">詳細については、[スタイルとテンプレート](../../desktop-wpf/fundamentals/styles-templates-overview.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-309">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="control-templates"></a><span data-ttu-id="1db77-310">コントロール テンプレート</span><span class="sxs-lookup"><span data-stu-id="1db77-310">Control templates</span></span>

<span data-ttu-id="1db77-311">WPF コントロールの既定のユーザー インターフェイスは、通常、他のコントロールと図形で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-311">The default user interfaces for WPF controls are typically constructed from other controls and shapes.</span></span> <span data-ttu-id="1db77-312">たとえば、 <xref:System.Windows.Controls.Button> は <xref:Microsoft.Windows.Themes.ButtonChrome> コントロールと <xref:System.Windows.Controls.ContentPresenter> コントロールの両方で構成されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-312">For example, a <xref:System.Windows.Controls.Button> is composed of both <xref:Microsoft.Windows.Themes.ButtonChrome> and <xref:System.Windows.Controls.ContentPresenter> controls.</span></span> <span data-ttu-id="1db77-313"><xref:Microsoft.Windows.Themes.ButtonChrome> は標準的なボタンの外観を提供するのに対し、 <xref:System.Windows.Controls.ContentPresenter> は <xref:System.Windows.Controls.ContentControl.Content%2A> プロパティで指定したボタンのコンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-313">The <xref:Microsoft.Windows.Themes.ButtonChrome> provides the standard button appearance, while the <xref:System.Windows.Controls.ContentPresenter> displays the button's content, as specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property.</span></span>

<span data-ttu-id="1db77-314">コントロールの既定の外観が、アプリケーションの全体的な外観と調和しない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1db77-314">Sometimes the default appearance of a control may be incongruent with the overall appearance of an application.</span></span> <span data-ttu-id="1db77-315">そのような場合は、 <xref:System.Windows.Controls.ControlTemplate> を使用すれば、コンテンツと動作を変更することなく、コントロールのユーザー インターフェイスの外観を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-315">In this case, you can use a <xref:System.Windows.Controls.ControlTemplate> to change the appearance of the control's user interface without changing its content and behavior.</span></span>

<span data-ttu-id="1db77-316">次の例は、<xref:System.Windows.Controls.ControlTemplate>を使用して <xref:System.Windows.Controls.Button> の外観を変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-316">The following example shows how to change the appearance of a <xref:System.Windows.Controls.Button> by using a <xref:System.Windows.Controls.ControlTemplate>:</span></span>

[!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_16.xaml)]

[!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_17.cs)]
[!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_17.vb)]

<span data-ttu-id="1db77-317">この例では、既定のボタン ユーザー インターフェイスが、濃い青の枠線を持ち、 <xref:System.Windows.Shapes.Ellipse> で塗りつぶされた <xref:System.Windows.Media.RadialGradientBrush>に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="1db77-317">In this example, the default button user interface has been replaced with an <xref:System.Windows.Shapes.Ellipse> that has a dark blue border and is filled using a <xref:System.Windows.Media.RadialGradientBrush>.</span></span> <span data-ttu-id="1db77-318"><xref:System.Windows.Controls.ContentPresenter> コントロールは <xref:System.Windows.Controls.Button>のコンテンツである "Click Me!" を表示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-318">The <xref:System.Windows.Controls.ContentPresenter> control displays the content of the <xref:System.Windows.Controls.Button>, "Click Me!"</span></span> <span data-ttu-id="1db77-319"><xref:System.Windows.Controls.Button> がクリックされると、 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> コントロールの既定の動作の一部として <xref:System.Windows.Controls.Button> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="1db77-319">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event is still raised as part of the <xref:System.Windows.Controls.Button> control's default behavior.</span></span> <span data-ttu-id="1db77-320">結果を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1db77-320">The result is shown in the following figure:</span></span>

![省略記号ボタンと 2 番目のウィンドウ](media/introduction-to-wpf/wpfintrofigure2.png)

### <a name="data-templates"></a><span data-ttu-id="1db77-322">データ テンプレート</span><span class="sxs-lookup"><span data-stu-id="1db77-322">Data templates</span></span>

<span data-ttu-id="1db77-323">コントロール テンプレートを使用すると、コントロールの外観を指定できますが、データ テンプレートではコントロールのコンテンツの外観を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-323">Whereas a control template lets you specify the appearance of a control, a data template lets you specify the appearance of a control's content.</span></span> <span data-ttu-id="1db77-324">データ テンプレートはたいてい、バインドされたデータの表示方法を多様化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-324">Data templates are frequently used to enhance how bound data is displayed.</span></span> <span data-ttu-id="1db77-325">次の図は、`Task` オブジェクトのコレクションにバインドされている <xref:System.Windows.Controls.ListBox> の既定の外観を示しています。各タスクには名前、説明、および優先順位があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-325">The following figure shows the default appearance for a <xref:System.Windows.Controls.ListBox> that is bound to a collection of `Task` objects, where each task has a name, description, and priority:</span></span>

![既定の外観を使用したリスト ボックス](media/introduction-to-wpf/wpfintrofigure18.png)

<span data-ttu-id="1db77-327">既定の外観は <xref:System.Windows.Controls.ListBox>に期待されるものです。</span><span class="sxs-lookup"><span data-stu-id="1db77-327">The default appearance is what you would expect from a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="1db77-328">ただし、各タスクの既定の外観にはタスク名しか含まれていません。</span><span class="sxs-lookup"><span data-stu-id="1db77-328">However, the default appearance of each task contains only the task name.</span></span> <span data-ttu-id="1db77-329">タスク名、説明、優先度の既定の外観を表示するには、 <xref:System.Windows.Controls.ListBox> コントロールのバインドされたリスト項目の既定の外観を、 <xref:System.Windows.DataTemplate>を使用して変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-329">To show the task name, description, and priority, the default appearance of the <xref:System.Windows.Controls.ListBox> control's bound list items must be changed by using a <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="1db77-330">次の XAML は、<xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 属性を使用して各タスクに適用される、このような <xref:System.Windows.DataTemplate>を定義します。</span><span class="sxs-lookup"><span data-stu-id="1db77-330">The following XAML defines such a <xref:System.Windows.DataTemplate>, which is applied to each task by using the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> attribute:</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="SDKSample.DataTemplateWindow"
  Title="With a Data Template">
  <Window.Resources>
    <!-- Data Template (applied to each bound task item in the task collection) -->
    <DataTemplate x:Key="myTaskTemplate">
      <Border Name="border" BorderBrush="DarkSlateBlue" BorderThickness="2"
        CornerRadius="2" Padding="5" Margin="5">
        <Grid>
          <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
          </Grid.RowDefinitions>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition />
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Row="0" Grid.Column="0" Padding="0,0,5,0" Text="Task Name:"/>
          <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Path=TaskName}"/>
          <TextBlock Grid.Row="1" Grid.Column="0" Padding="0,0,5,0" Text="Description:"/>
          <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Path=Description}"/>
          <TextBlock Grid.Row="2" Grid.Column="0" Padding="0,0,5,0" Text="Priority:"/>
          <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Path=Priority}"/>
        </Grid>
      </Border>
    </DataTemplate>
  </Window.Resources>

  <!-- UI -->
  <DockPanel>
    <!-- Title -->
    <Label DockPanel.Dock="Top" FontSize="18" Margin="5" Content="My Task List:"/>

    <!-- Data template is specified by the ItemTemplate attribute -->
    <ListBox
      ItemsSource="{Binding}"
      ItemTemplate="{StaticResource myTaskTemplate}"
      HorizontalContentAlignment="Stretch"
      IsSynchronizedWithCurrentItem="True"
      Margin="5,0,5,5" />

 </DockPanel>
</Window>
```

<span data-ttu-id="1db77-331">次の図は、このコードの効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-331">The following figure shows the effect of this code:</span></span>

![データ テンプレートを使用するリスト ボックス](media/introduction-to-wpf/wpfintrofigure19.png)

<span data-ttu-id="1db77-333"><xref:System.Windows.Controls.ListBox> の動作と全体的な外観は保持されていることにご注意ください。リスト ボックスにより表示されるコンテンツの外観のみが変更されています。</span><span class="sxs-lookup"><span data-stu-id="1db77-333">Note that the <xref:System.Windows.Controls.ListBox> has retained its behavior and overall appearance; only the appearance of the content being displayed by the list box has changed.</span></span>

<span data-ttu-id="1db77-334">詳しくは「[データ テンプレートの概要](data/data-templating-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-334">For more information, see [Data templating overview](data/data-templating-overview.md).</span></span>

### <a name="styles"></a><span data-ttu-id="1db77-335">スタイル</span><span class="sxs-lookup"><span data-stu-id="1db77-335">Styles</span></span>

<span data-ttu-id="1db77-336">スタイルを使うと、開発者とデザイナーは製品の特定の外観を標準化できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-336">Styles enable developers and designers to standardize on a particular appearance for their product.</span></span> <span data-ttu-id="1db77-337">WPF には強力なスタイル モデルが用意されており、この基盤となるのが <xref:System.Windows.Style> 要素です。</span><span class="sxs-lookup"><span data-stu-id="1db77-337">WPF provides a strong style model, the foundation of which is the <xref:System.Windows.Style> element.</span></span> <span data-ttu-id="1db77-338">次の例では、ウィンドウ上のすべての <xref:System.Windows.Controls.Button> の背景色を `Orange`に設定するスタイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1db77-338">The following example creates a style that sets the background color for every <xref:System.Windows.Controls.Button> on a window to `Orange`:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">
  <!-- Style that will be applied to all buttons -->
  <Style TargetType="{x:Type Button}">
    <Setter Property="Background" Value="Orange" />
    <Setter Property="BorderBrush" Value="Crimson" />
    <Setter Property="FontSize" Value="20" />
    <Setter Property="FontWeight" Value="Bold" />
    <Setter Property="Margin" Value="5" />
  </Style>
  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>

  <!-- This label will not have the style applied to it -->
  <Label>Don't Click Me!</Label>

  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>
</Window>
```

<span data-ttu-id="1db77-339">このスタイルでは、すべての <xref:System.Windows.Controls.Button> コントロールを対象としているため、次の図に示すように、スタイルがウィンドウのすべてのボタンに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-339">Because this style targets all <xref:System.Windows.Controls.Button> controls, the style is automatically applied to all the buttons in the window, as shown in the following figure:</span></span>

![2 つのオレンジ色のボタン](media/introduction-to-wpf/wpfintrofigure20.png)

<span data-ttu-id="1db77-341">詳細については、[スタイルとテンプレート](../../desktop-wpf/fundamentals/styles-templates-overview.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-341">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="resources"></a><span data-ttu-id="1db77-342">リソース</span><span class="sxs-lookup"><span data-stu-id="1db77-342">Resources</span></span>

<span data-ttu-id="1db77-343">アプリケーションのコントロール類は、同じ外観を持つ必要があります。こうした外観はフォントや背景色からコントロール テンプレート、データ テンプレート、スタイルまで、多岐にわたります。</span><span class="sxs-lookup"><span data-stu-id="1db77-343">Controls in an application should share the same appearance, which can include anything from fonts and background colors to control templates, data templates, and styles.</span></span> <span data-ttu-id="1db77-344">ユーザー インターフェイスのリソースに対する WPF のサポートを使用すれば、こうした各種リソースを 1 つの場所でカプセル化して、再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="1db77-344">You can use WPF's support for user interface resources to encapsulate these resources in a single location for reuse.</span></span>

<span data-ttu-id="1db77-345">次の例では、<xref:System.Windows.Controls.Button> と <xref:System.Windows.Controls.Label>によって共有される共通の背景色を定義します。</span><span class="sxs-lookup"><span data-stu-id="1db77-345">The following example defines a common background color that is shared by a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.Label>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">

  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>
</Window>
```

<span data-ttu-id="1db77-346">この例では `Window.Resources` プロパティ要素を使用して、背景色リソースを実装しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-346">This example implements a background color resource by using the `Window.Resources` property element.</span></span> <span data-ttu-id="1db77-347">このリソースは <xref:System.Windows.Window>のすべての子に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-347">This resource is available to all children of the <xref:System.Windows.Window>.</span></span> <span data-ttu-id="1db77-348">次のように、リソースのスコープは多様です。この一覧では、解決される順序で各スコープが並べられています。</span><span class="sxs-lookup"><span data-stu-id="1db77-348">There are a variety of resource scopes, including the following, listed in the order in which they are resolved:</span></span>

1. <span data-ttu-id="1db77-349">個々のコントロール (継承された <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> プロパティを使用)。</span><span class="sxs-lookup"><span data-stu-id="1db77-349">An individual control (using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

2. <span data-ttu-id="1db77-350"><xref:System.Windows.Window> または <xref:System.Windows.Controls.Page> (これも、継承された <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> プロパティを使用)。</span><span class="sxs-lookup"><span data-stu-id="1db77-350">A <xref:System.Windows.Window> or a <xref:System.Windows.Controls.Page> (also using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

3. <span data-ttu-id="1db77-351"><xref:System.Windows.Application> ( <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> プロパティを使用)。</span><span class="sxs-lookup"><span data-stu-id="1db77-351">An <xref:System.Windows.Application> (using the <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> property).</span></span>

<span data-ttu-id="1db77-352">このようなスコープの多様さのおかげで、リソースを柔軟に定義して共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1db77-352">The variety of scopes gives you flexibility with respect to the way in which you define and share your resources.</span></span>

<span data-ttu-id="1db77-353">リソースを特定のスコープに直接関連付ける代わりに、アプリケーションの他の部分で参照できる別個の <xref:System.Windows.ResourceDictionary> を使用して、1 つ以上のリソースをパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="1db77-353">As an alternative to directly associating your resources with a particular scope, you can package one or more resources by using a separate <xref:System.Windows.ResourceDictionary> that can be referenced in other parts of an application.</span></span> <span data-ttu-id="1db77-354">たとえば、次の例では、リソースディクショナリに既定の背景色を定義しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-354">For example, the following example defines a default background color in a resource dictionary:</span></span>

```xaml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```

<span data-ttu-id="1db77-355">次の例では、アプリケーション全体で共有されるように、前の例で定義されているリソースディクショナリを参照します。</span><span class="sxs-lookup"><span data-stu-id="1db77-355">The following example references the resource dictionary defined in the previous example so that it is shared across an application:</span></span>

```xaml
<Application
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.App">

  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="BackgroundColorResources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```

<span data-ttu-id="1db77-356">リソースおよびリソース ディクショナリは、テーマとスキンに対する WPF サポートの基礎です。</span><span class="sxs-lookup"><span data-stu-id="1db77-356">Resources and resource dictionaries are the foundation of WPF support for themes and skins.</span></span>

<span data-ttu-id="1db77-357">詳しくは、[リソース](../../desktop-wpf/fundamentals/xaml-resources-define.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-357">For more information, see [Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="custom-controls"></a><span data-ttu-id="1db77-358">カスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="1db77-358">Custom controls</span></span>

<span data-ttu-id="1db77-359">WPF にはカスタマイズに対する多くのサポートが用意されていますが、状況によっては既存の WPF コントロールではアプリケーションやそのユーザーのニーズを満たせない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1db77-359">Although WPF provides a host of customization support, you may encounter situations where existing WPF controls do not meet the needs of either your application or its users.</span></span> <span data-ttu-id="1db77-360">次のような状況が考えられます。</span><span class="sxs-lookup"><span data-stu-id="1db77-360">This can occur when:</span></span>

- <span data-ttu-id="1db77-361">WPF の既存の実装のルックアンドフィールをカスタマイズしても、必要とするユーザー インターフェイスを作成できない。</span><span class="sxs-lookup"><span data-stu-id="1db77-361">The user interface that you require cannot be created by customizing the look and feel of existing WPF implementations.</span></span>

- <span data-ttu-id="1db77-362">WPF の既存の実装が、必要とする動作をサポートしない (または簡単にはサポートできない)。</span><span class="sxs-lookup"><span data-stu-id="1db77-362">The behavior that you require is not supported (or not easily supported) by existing WPF implementations.</span></span>

<span data-ttu-id="1db77-363">ただし現時点では、3 つの WPF モデルのいずれかを利用して、新しいコントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-363">At this point, however, you can take advantage of one of three WPF models to create a new control.</span></span> <span data-ttu-id="1db77-364">各モデルは固有のシナリオを対象としており、カスタム コントロールは特定の WPF 基底クラスから派生するものでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1db77-364">Each model targets a specific scenario and requires your custom control to derive from a particular WPF base class.</span></span> <span data-ttu-id="1db77-365">この 3 つのモデルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1db77-365">The three models are listed here:</span></span>

- <span data-ttu-id="1db77-366">**ユーザー コントロール モデル**</span><span class="sxs-lookup"><span data-stu-id="1db77-366">**User Control Model**.</span></span> <span data-ttu-id="1db77-367">カスタム コントロールは <xref:System.Windows.Controls.UserControl> から派生し、他の 1 つ以上のコントロールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-367">A custom control derives from <xref:System.Windows.Controls.UserControl> and is composed of one or more other controls.</span></span>

- <span data-ttu-id="1db77-368">**コントロール モデル**</span><span class="sxs-lookup"><span data-stu-id="1db77-368">**Control Model**.</span></span> <span data-ttu-id="1db77-369">カスタム コントロールは <xref:System.Windows.Controls.Control> から派生し、大半の WPF コントロール同様、テンプレートを使用して、動作を外観から分離する実装を構築するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1db77-369">A custom control derives from <xref:System.Windows.Controls.Control> and is used to build implementations that separate their behavior from their appearance using templates, much like the majority of WPF controls.</span></span> <span data-ttu-id="1db77-370"><xref:System.Windows.Controls.Control> から派生することにより、ユーザー コントロールよりも自由度の高いカスタム ユーザー インターフェイスを作成できますが、これにはより多くの労力が必要です。</span><span class="sxs-lookup"><span data-stu-id="1db77-370">Deriving from <xref:System.Windows.Controls.Control> allows you more freedom for creating a custom user interface than user controls, but it may require more effort.</span></span>

- <span data-ttu-id="1db77-371">**フレームワーク要素モデル**</span><span class="sxs-lookup"><span data-stu-id="1db77-371">**Framework Element Model**.</span></span> <span data-ttu-id="1db77-372">カスタム コントロールは、カスタム レンダリング ロジック (テンプレートではなく) によって外観が定義されるときに、 <xref:System.Windows.FrameworkElement> から派生します。</span><span class="sxs-lookup"><span data-stu-id="1db77-372">A custom control derives from <xref:System.Windows.FrameworkElement> when its appearance is defined by custom rendering logic (not templates).</span></span>

<span data-ttu-id="1db77-373">次の例は、<xref:System.Windows.Controls.UserControl>から派生するカスタムの数値のアップダウンコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-373">The following example shows a custom numeric up/down control that derives from <xref:System.Windows.Controls.UserControl>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_33.xaml)]

[!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_34.cs)]
[!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_34.vb)]

<span data-ttu-id="1db77-374">次の例は、ユーザーコントロールを <xref:System.Windows.Window>に組み込むために必要な XAML を示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-374">The following example illustrates the XAML that is required to incorporate the user control into a <xref:System.Windows.Window>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_37.xaml)]

<span data-ttu-id="1db77-375">次の図は、<xref:System.Windows.Window>でホストされている `NumericUpDown` コントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="1db77-375">The following figure shows the `NumericUpDown` control hosted in a <xref:System.Windows.Window>:</span></span>

![カスタム UserControl](media/introduction-to-wpf/wpfintrofigure3.png)

<span data-ttu-id="1db77-377">カスタム コントロールについて詳しくは、「[コントロールの作成の概要](controls/control-authoring-overview.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1db77-377">For more information on custom controls, see [Control authoring overview](controls/control-authoring-overview.md).</span></span>

## <a name="wpf-best-practices"></a><span data-ttu-id="1db77-378">WPF のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="1db77-378">WPF best practices</span></span>

<span data-ttu-id="1db77-379">WPF はすべての開発プラットフォームと同様、目的の結果を得るために、さまざまな方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1db77-379">As with any development platform, WPF can be used in a variety of ways to achieve the desired result.</span></span> <span data-ttu-id="1db77-380">必要なユーザー エクスペリエンスを WPF アプリケーションが確実に提供し、オーディエンス一般の需要に応える 1 つの方法として、アクセシビリティ、グローバリゼーションとローカリゼーション、パフォーマンスに関するお勧めのベスト プラクティスがあります。</span><span class="sxs-lookup"><span data-stu-id="1db77-380">As a way of ensuring that your WPF applications provide the required user experience and meet the demands of the audience in general, there are recommended best practices for accessibility, globalization and localization, and performance.</span></span> <span data-ttu-id="1db77-381">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1db77-381">For more information, see:</span></span>

- [<span data-ttu-id="1db77-382">ユーザー補助</span><span class="sxs-lookup"><span data-stu-id="1db77-382">Accessibility</span></span>](../ui-automation/accessibility-best-practices.md)
- [<span data-ttu-id="1db77-383">WPF のグローバリゼーションとローカライズ</span><span class="sxs-lookup"><span data-stu-id="1db77-383">WPF globalization and localization</span></span>](advanced/wpf-globalization-and-localization-overview.md)
- [<span data-ttu-id="1db77-384">WPF アプリのパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="1db77-384">WPF app performance</span></span>](advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="1db77-385">WPF のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="1db77-385">WPF security</span></span>](security-wpf.md)

## <a name="next-steps"></a><span data-ttu-id="1db77-386">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1db77-386">Next steps</span></span>

<span data-ttu-id="1db77-387">WPF の主な機能を確認しました。</span><span class="sxs-lookup"><span data-stu-id="1db77-387">We've looked at the key features of WPF.</span></span> <span data-ttu-id="1db77-388">次は、初めての WPF アプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="1db77-388">Now it's time to build your first WPF app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1db77-389">チュートリアル: 初めての WPF デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1db77-389">Walkthrough: My first WPF desktop app</span></span>](getting-started/walkthrough-my-first-wpf-desktop-application.md)

## <a name="see-also"></a><span data-ttu-id="1db77-390">参照</span><span class="sxs-lookup"><span data-stu-id="1db77-390">See also</span></span>

- [<span data-ttu-id="1db77-391">WPF の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="1db77-391">Get started with WPF</span></span>](getting-started/index.md)
- [<span data-ttu-id="1db77-392">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="1db77-392">Windows Presentation Foundation</span></span>](index.md)
- [<span data-ttu-id="1db77-393">WPF コミュニティ リソース</span><span class="sxs-lookup"><span data-stu-id="1db77-393">WPF community resources</span></span>](getting-started/community-feedback.md)
