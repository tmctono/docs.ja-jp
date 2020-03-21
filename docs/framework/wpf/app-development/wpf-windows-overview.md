---
title: ウィンドウの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: b06afb56f43a874815cf9f679f1f7fefbdfd4565
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145541"
---
# <a name="wpf-windows-overview"></a><span data-ttu-id="1078c-102">WPF ウィンドウの概要</span><span class="sxs-lookup"><span data-stu-id="1078c-102">WPF Windows Overview</span></span>
<span data-ttu-id="1078c-103">ユーザーは、ウィンドウを介して Windows プレゼンテーションファンデーション (WPF) スタンドアロン アプリケーションと対話します。</span><span class="sxs-lookup"><span data-stu-id="1078c-103">Users interact with Windows Presentation Foundation (WPF) standalone applications through windows.</span></span> <span data-ttu-id="1078c-104">ウィンドウの主な目的は、データを視覚化してユーザーがデータと対話できるコンテンツをホストすることです。</span><span class="sxs-lookup"><span data-stu-id="1078c-104">The primary purpose of a window is to host content that visualizes data and enables users to interact with data.</span></span> <span data-ttu-id="1078c-105">スタンドアロン WPF アプリケーションは、クラスを使用して<xref:System.Windows.Window>独自のウィンドウを提供します。</span><span class="sxs-lookup"><span data-stu-id="1078c-105">Standalone WPF applications provide their own windows by using the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="1078c-106">このトピックでは<xref:System.Windows.Window>、スタンドアロン アプリケーションでのウィンドウの作成と管理の基本について説明する前に説明します。</span><span class="sxs-lookup"><span data-stu-id="1078c-106">This topic introduces <xref:System.Windows.Window> before covering the fundamentals of creating and managing windows in standalone applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-107">XAML ブラウザー アプリケーション (XBaps) や緩い[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ページを含む、ブラウザーでホストされる WPF アプリケーションは、独自のウィンドウを提供しません。</span><span class="sxs-lookup"><span data-stu-id="1078c-107">Browser-hosted WPF applications, including XAML browser applications (XBAPs) and loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pages, don't provide their own windows.</span></span> <span data-ttu-id="1078c-108">代わりに、Windows インターネット エクスプローラによって提供されるウィンドウでホストされます。</span><span class="sxs-lookup"><span data-stu-id="1078c-108">Instead, they are hosted in windows provided by Windows Internet Explorer.</span></span> <span data-ttu-id="1078c-109">[WPF XAML ブラウザー アプリケーションの概要](wpf-xaml-browser-applications-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-109">See [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a><span data-ttu-id="1078c-110">ウィンドウ クラス</span><span class="sxs-lookup"><span data-stu-id="1078c-110">The Window Class</span></span>  
 <span data-ttu-id="1078c-111">次の図は、ウィンドウの構成要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-111">The following figure illustrates the constituent parts of a window:</span></span>  
  
 ![ウィンドウ要素を示すスクリーンショット。](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 <span data-ttu-id="1078c-113">ウィンドウは、非クライアント領域とクライアント領域の 2 つに分かれます。</span><span class="sxs-lookup"><span data-stu-id="1078c-113">A window is divided into two areas: the non-client area and client area.</span></span>  
  
 <span data-ttu-id="1078c-114">ウィンドウ*の非クライアント領域*は WPF によって実装され、次のようなほとんどのウィンドウに共通のウィンドウの部分が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1078c-114">The *non-client area* of a window is implemented by WPF and includes the parts of a window that are common to most windows, including the following:</span></span>  
  
- <span data-ttu-id="1078c-115">境界線。</span><span class="sxs-lookup"><span data-stu-id="1078c-115">A border.</span></span>  
  
- <span data-ttu-id="1078c-116">タイトル バー。</span><span class="sxs-lookup"><span data-stu-id="1078c-116">A title bar.</span></span>  
  
- <span data-ttu-id="1078c-117">アイコン。</span><span class="sxs-lookup"><span data-stu-id="1078c-117">An icon.</span></span>  
  
- <span data-ttu-id="1078c-118">最小化ボタン、最大化ボタン、および元に戻すボタン。</span><span class="sxs-lookup"><span data-stu-id="1078c-118">Minimize, Maximize, and Restore buttons.</span></span>  
  
- <span data-ttu-id="1078c-119">閉じるボタン。</span><span class="sxs-lookup"><span data-stu-id="1078c-119">A Close button.</span></span>  
  
- <span data-ttu-id="1078c-120">ウィンドウを最小化、最大化、元のサイズに戻す、移動、サイズ変更、および閉じるためのメニュー項目を含むシステム メニュー。</span><span class="sxs-lookup"><span data-stu-id="1078c-120">A System menu with menu items that allow users to minimize, maximize, restore, move, resize, and close a window.</span></span>  
  
 <span data-ttu-id="1078c-121">ウィンドウの*クライアント領域*は、ウィンドウの非クライアント領域内の領域であり、メニュー バー、ツール バー、コントロールなどのアプリケーション固有のコンテンツを追加するために開発者によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-121">The *client area* of a window is the area within a window's non-client area and is used by developers to add application-specific content, such as menu bars, tool bars, and controls.</span></span>  
  
 <span data-ttu-id="1078c-122">WPF では、ウィンドウは、次の操作<xref:System.Windows.Window>を行うために使用するクラスによってカプセル化されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-122">In WPF, a window is encapsulated by the <xref:System.Windows.Window> class that you use to do the following:</span></span>  
  
- <span data-ttu-id="1078c-123">ウィンドウを表示する。</span><span class="sxs-lookup"><span data-stu-id="1078c-123">Display a window.</span></span>  
  
- <span data-ttu-id="1078c-124">ウィンドウのサイズ、位置、および外観を構成する。</span><span class="sxs-lookup"><span data-stu-id="1078c-124">Configure the size, position, and appearance of a window.</span></span>  
  
- <span data-ttu-id="1078c-125">アプリケーション固有のコンテンツをホストする。</span><span class="sxs-lookup"><span data-stu-id="1078c-125">Host application-specific content.</span></span>  
  
- <span data-ttu-id="1078c-126">ウィンドウの有効期間を管理する。</span><span class="sxs-lookup"><span data-stu-id="1078c-126">Manage the lifetime of a window.</span></span>  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a><span data-ttu-id="1078c-127">ウィンドウの実装</span><span class="sxs-lookup"><span data-stu-id="1078c-127">Implementing a Window</span></span>  
 <span data-ttu-id="1078c-128">一般的なウィンドウの実装は、外観と動作の両方で構成され、*外観*は、ユーザーに対するウィンドウの外観を定義し、*ユーザー*がウィンドウを操作する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="1078c-128">The implementation of a typical window comprises both appearance and behavior, where *appearance* defines how a window looks to users and *behavior* defines the way a window functions as users interact with it.</span></span> <span data-ttu-id="1078c-129">WPF では、コードまたは[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップを使用して、ウィンドウの外観と動作を実装できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-129">In WPF, you can implement the appearance and behavior of a window using either code or [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 <span data-ttu-id="1078c-130">ただし、一般的に、ウィンドウの外観はマークアップを使用して[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]実装され、次の例に示すように、その動作は分離コードを使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-130">In general, however, the appearance of a window is implemented using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and its behavior is implemented using code-behind, as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 <span data-ttu-id="1078c-131">マークアップ ファイル[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]と分離コード ファイルを連携して動作させるには、次の項目が必要です。</span><span class="sxs-lookup"><span data-stu-id="1078c-131">To enable a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup file and code-behind file to work together, the following are required:</span></span>  
  
- <span data-ttu-id="1078c-132">マークアップでは、要素`Window`に属性を`x:Class`含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-132">In markup, the `Window` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="1078c-133">アプリケーションがビルドされると、マークアップ ファイルに`x:Class`のが存在すると、Microsoft ビルド エンジン (MSBuild) は、属性<xref:System.Windows.Window>で指定された派生した名前を持つ`x:Class``partial`クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1078c-133">When the application is built, the existence of `x:Class` in the markup file causes Microsoft build engine (MSBuild) to create a `partial` class that derives from <xref:System.Windows.Window> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="1078c-134">そのためには、スキーマ ( )[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`の XML 名前空間宣言を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-134">This requires the addition of an XML namespace declaration for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span></span> <span data-ttu-id="1078c-135">生成された`partial`クラスは、イベント`InitializeComponent`を登録し、マークアップで実装されるプロパティを設定するために呼び出されるメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="1078c-135">The generated `partial` class implements the `InitializeComponent` method, which is called to register the events and set the properties that are implemented in markup.</span></span>  
  
- <span data-ttu-id="1078c-136">分離コードでは、クラスは、マークアップの属性`partial`で指定されている名前と同じ名前の`x:Class`クラスである必要があり、派生<xref:System.Windows.Window>元である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-136">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Window>.</span></span> <span data-ttu-id="1078c-137">これにより、アプリケーションのビルド時にマークアップ ファイル用に`partial`生成されるクラスに分離コード ファイルを関連付けられます[(WPF アプリケーションのビルドを](building-a-wpf-application-wpf.md)参照)。</span><span class="sxs-lookup"><span data-stu-id="1078c-137">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>  
  
- <span data-ttu-id="1078c-138">分離コードでは、クラスは<xref:System.Windows.Window>メソッドを呼び出すコンストラクターを`InitializeComponent`実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-138">In code-behind, the <xref:System.Windows.Window> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="1078c-139">`InitializeComponent`は、イベントを登録し、マークアップで定義`partial`されているプロパティを設定するために、マークアップ ファイルの生成されたクラスによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-139">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-140">Visual Studio を<xref:System.Windows.Window>使用して新しいプロジェクトを追加すると、<xref:System.Windows.Window>マークアップと分離コードの両方を使用して が実装され、ここで説明するようにマークアップ ファイルと分離コード ファイル間の関連付けを作成するために必要な構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1078c-140">When you add a new <xref:System.Windows.Window> to your project by using Visual Studio, the <xref:System.Windows.Window> is implemented using both markup and code-behind, and includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>  
  
 <span data-ttu-id="1078c-141">この構成を適切に行えば、マークアップで[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]のウィンドウの外観を定義し、その動作を分離コードに実装することに集中できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-141">With this configuration in place, you can focus on defining the appearance of the window in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and implementing its behavior in code-behind.</span></span> <span data-ttu-id="1078c-142">次の例は、マークアップで実装されたボタンと、コード[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ビハインドで実装されたボタンの<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント ハンドラーを持つウィンドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-142">The following example shows a window with a button, implemented in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, implemented in code-behind.</span></span>  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a><span data-ttu-id="1078c-143">MSBuild 用のウィンドウ定義の構成</span><span class="sxs-lookup"><span data-stu-id="1078c-143">Configuring a Window Definition for MSBuild</span></span>  
 <span data-ttu-id="1078c-144">ウィンドウの実装方法によって、MSBuild の構成方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="1078c-144">How you implement your window determines how it is configured for MSBuild.</span></span> <span data-ttu-id="1078c-145">マークアップと分離コードの両方[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を使用して定義されるウィンドウの場合:</span><span class="sxs-lookup"><span data-stu-id="1078c-145">For a window that is defined using both [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind:</span></span>  
  
- <span data-ttu-id="1078c-146">XAML マークアップ ファイルは MSBuild`Page`項目として構成されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-146">XAML markup files are configured as MSBuild `Page` items.</span></span>  
  
- <span data-ttu-id="1078c-147">分離コード ファイルは MSBuild`Compile`項目として構成されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-147">Code-behind files are configured as MSBuild `Compile` items.</span></span>  
  
 <span data-ttu-id="1078c-148">これは、次の MSBuild プロジェクト ファイルに示されています。</span><span class="sxs-lookup"><span data-stu-id="1078c-148">This is shown in the following MSBuild project file.</span></span>  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 <span data-ttu-id="1078c-149">WPF アプリケーションのビルドについては、「 WPF アプリケーション[のビルド](building-a-wpf-application-wpf.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-149">For information about building WPF applications, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a><span data-ttu-id="1078c-150">ウィンドウの有効期間</span><span class="sxs-lookup"><span data-stu-id="1078c-150">Window Lifetime</span></span>  
 <span data-ttu-id="1078c-151">クラスと同様に、ウィンドウにも有効期間があります。有効期間は、ウィンドウが開いて最初にインスタンス化されたときに開始し、アクティブ化と非アクティブ化を経て、最後に閉じられるまで継続します。</span><span class="sxs-lookup"><span data-stu-id="1078c-151">As with any class, a window has a lifetime that begins when it is first instantiated, after which it is opened, activated and deactivated, and eventually closed.</span></span>  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a><span data-ttu-id="1078c-152">ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="1078c-152">Opening a Window</span></span>  
 <span data-ttu-id="1078c-153">ウィンドウを開くには、次の例に示すように最初にインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1078c-153">To open a window, you first create an instance of it, which is demonstrated in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 <span data-ttu-id="1078c-154">この例では、`MarkupAndCodeBehindWindow`アプリケーションの起動時に インスタンス化され、イベントが発生したときに発生<xref:System.Windows.Application.Startup>します。</span><span class="sxs-lookup"><span data-stu-id="1078c-154">In this example, the `MarkupAndCodeBehindWindow` is instantiated when the application starts, which occurs when the <xref:System.Windows.Application.Startup> event is raised.</span></span>  
  
 <span data-ttu-id="1078c-155">ウィンドウがインスタンス化されると、そのウィンドウへの参照がオブジェクトによって管理されるウィンドウのリストに自動的に<xref:System.Windows.Application>追加されます (「」を<xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>参照)。</span><span class="sxs-lookup"><span data-stu-id="1078c-155">When a window is instantiated, a reference to it is automatically added to a list of windows that is managed by the <xref:System.Windows.Application> object (see <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="1078c-156">さらに、インスタンス化される最初のウィンドウは、既定ではメイン アプリケーション ウィンドウ<xref:System.Windows.Application>として設定されます ( を<xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>参照してください )。</span><span class="sxs-lookup"><span data-stu-id="1078c-156">Additionally, the first window to be instantiated is, by default, set by <xref:System.Windows.Application> as the main application window (see <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="1078c-157">このウィンドウは、メソッドを呼び<xref:System.Windows.Window.Show%2A>出して最終的に開きます。結果を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1078c-157">The window is finally opened by calling the <xref:System.Windows.Window.Show%2A> method; the result is shown in the following figure.</span></span>  
  
 ![ウィンドウを呼び出して開いたウィンドウ。](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 <span data-ttu-id="1078c-159">呼び出し<xref:System.Windows.Window.Show%2A>によって開かれるウィンドウはモードレス ウィンドウであり、これは、ユーザーが同じアプリケーション内の他のウィンドウをアクティブにできるモードで動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="1078c-159">A window that is opened by calling <xref:System.Windows.Window.Show%2A> is a modeless window, which means that the application operates in a mode that allows users to activate other windows in the same application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-160"><xref:System.Windows.Window.ShowDialog%2A>は、ダイアログ ボックスなどのウィンドウをモーダルに開くために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-160"><xref:System.Windows.Window.ShowDialog%2A> is called to open windows such as dialog boxes modally.</span></span> <span data-ttu-id="1078c-161">詳細については、[ダイアログ ボックスの概要](dialog-boxes-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-161">See [Dialog Boxes Overview](dialog-boxes-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="1078c-162">呼<xref:System.Windows.Window.Show%2A>び出されると、ウィンドウは、ユーザー入力を受信できるインフラストラクチャを確立するために示される前に、初期化作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="1078c-162">When <xref:System.Windows.Window.Show%2A> is called, a window performs initialization work before it is shown to establish infrastructure that allows it to receive user input.</span></span> <span data-ttu-id="1078c-163">ウィンドウが初期化されると、<xref:System.Windows.Window.SourceInitialized>イベントが発生し、ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-163">When the window is initialized, the <xref:System.Windows.Window.SourceInitialized> event is raised and the window is shown.</span></span>  
  
 <span data-ttu-id="1078c-164">ショートカットとして、<xref:System.Windows.Application.StartupUri%2A>アプリケーションの起動時に自動的に開く最初のウィンドウを指定するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-164">As a shortcut, <xref:System.Windows.Application.StartupUri%2A> can be set to specify the first window that is opened automatically when an application starts.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 <span data-ttu-id="1078c-165">アプリケーションが起動すると、 の<xref:System.Windows.Application.StartupUri%2A>値で指定されたウィンドウがモードレスで開かれます。内部的には、ウィンドウはメソッドを<xref:System.Windows.Window.Show%2A>呼び出すことによって開かれます。</span><span class="sxs-lookup"><span data-stu-id="1078c-165">When the application starts, the window specified by the value of <xref:System.Windows.Application.StartupUri%2A> is opened modelessly; internally, the window is opened by calling its <xref:System.Windows.Window.Show%2A> method.</span></span>  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a><span data-ttu-id="1078c-166">ウィンドウの所有権</span><span class="sxs-lookup"><span data-stu-id="1078c-166">Window Ownership</span></span>  
 <span data-ttu-id="1078c-167"><xref:System.Windows.Window.Show%2A>メソッドを使用して開いたウィンドウは、そのウィンドウを作成したウィンドウと暗黙的に関係を持っていません。ユーザーはどちらかのウィンドウを別のウィンドウとは独立して操作できるため、どちらかのウィンドウで次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-167">A window that is opened by using the <xref:System.Windows.Window.Show%2A> method does not have an implicit relationship with the window that created it; users can interact with either window independently of the other, which means that either window can do the following:</span></span>  
  
- <span data-ttu-id="1078c-168">もう一方のウィンドウを覆います (一<xref:System.Windows.Window.Topmost%2A>方のウィンドウ`true`のプロパティが に設定されている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="1078c-168">Cover the other (unless one of the windows has its <xref:System.Windows.Window.Topmost%2A> property set to `true`).</span></span>  
  
- <span data-ttu-id="1078c-169">もう一方のウィンドウに影響を与えずに、最小化/最大化し、元のサイズに戻す。</span><span class="sxs-lookup"><span data-stu-id="1078c-169">Be minimized, maximized, and restored without affecting the other.</span></span>  
  
 <span data-ttu-id="1078c-170">一部のウィンドウには、そのウィンドウを開いたウィンドウとの関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="1078c-170">Some windows require a relationship with the window that opens them.</span></span> <span data-ttu-id="1078c-171">たとえば、統合開発環境 (IDE) アプリケーションは、プロパティ ウィンドウと、それらを作成するウィンドウをカバーする一般的な動作を持つツール ウィンドウを開く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-171">For example, an Integrated Development Environment (IDE) application may open property windows and tool windows whose typical behavior is to cover the window that creates them.</span></span> <span data-ttu-id="1078c-172">また、そのようなウィンドウは、必ず作成元のウィンドウと一緒に閉じ、最小化/最大化し、元のサイズに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-172">Furthermore, such windows should always close, minimize, maximize, and restore in concert with the window that created them.</span></span> <span data-ttu-id="1078c-173">このような関係は、あるウィンドウを別のウィンドウ*にすることで*確立でき、*所有するウィンドウ*の<xref:System.Windows.Window.Owner%2A>プロパティを*所有者ウィンドウ*への参照で設定することで実現されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-173">Such a relationship can be established by making one window *own* another, and is achieved by setting the <xref:System.Windows.Window.Owner%2A> property of the *owned window* with a reference to the *owner window*.</span></span> <span data-ttu-id="1078c-174">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-174">This is shown in the following example.</span></span>  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 <span data-ttu-id="1078c-175">所有権が確立されると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1078c-175">After ownership is established:</span></span>  
  
- <span data-ttu-id="1078c-176">所有するウィンドウは、プロパティの値を調べることによって、その所有者<xref:System.Windows.Window.Owner%2A>ウィンドウを参照できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-176">The owned window can reference its owner window by inspecting the value of its <xref:System.Windows.Window.Owner%2A> property.</span></span>  
  
- <span data-ttu-id="1078c-177">所有者ウィンドウは、プロパティの値を調べることによって、所有するすべてのウィンドウを<xref:System.Windows.Window.OwnedWindows%2A>検出できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-177">The owner window can discover all the windows it owns by inspecting the value of its <xref:System.Windows.Window.OwnedWindows%2A> property.</span></span>  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a><span data-ttu-id="1078c-178">ウィンドウのアクティブ化の防止</span><span class="sxs-lookup"><span data-stu-id="1078c-178">Preventing Window Activation</span></span>  
 <span data-ttu-id="1078c-179">インターネットメッセンジャー形式アプリケーションの会話ウィンドウや電子メールアプリケーションの通知ウィンドウなど、ウィンドウが表示されたときにアクティブにされてはいけないシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-179">There are scenarios where windows should not be activated when shown, such as conversation windows of an Internet messenger-style application or notification windows of an email application.</span></span>  
  
 <span data-ttu-id="1078c-180">アプリケーションに、表示されたときにアクティブにする必要のあるウィンドウがある場合は、その<xref:System.Windows.Window.ShowActivated%2A>プロパティを設定してから`false`、メソッドを<xref:System.Windows.Window.Show%2A>初めて呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="1078c-180">If your application has a window that shouldn't be activated when shown, you can set its <xref:System.Windows.Window.ShowActivated%2A> property to `false` before calling the <xref:System.Windows.Window.Show%2A> method for the first time.</span></span> <span data-ttu-id="1078c-181">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1078c-181">As a consequence:</span></span>  
  
- <span data-ttu-id="1078c-182">ウィンドウはアクティブになりません。</span><span class="sxs-lookup"><span data-stu-id="1078c-182">The window is not activated.</span></span>  
  
- <span data-ttu-id="1078c-183">ウィンドウの<xref:System.Windows.Window.Activated>イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="1078c-183">The window's <xref:System.Windows.Window.Activated> event is not raised.</span></span>  
  
- <span data-ttu-id="1078c-184">現在アクティブなウィンドウは、アクティブのままです。</span><span class="sxs-lookup"><span data-stu-id="1078c-184">The currently activated window remains activated.</span></span>  
  
 <span data-ttu-id="1078c-185">ただし、ユーザーがクライアント領域または非クライアント領域をクリックすると、ウィンドウは直ちにアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="1078c-185">The window will become activated, however, as soon as the user activates it by clicking either the client or non-client area.</span></span> <span data-ttu-id="1078c-186">この場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1078c-186">In this case:</span></span>  
  
- <span data-ttu-id="1078c-187">ウィンドウはアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="1078c-187">The window is activated.</span></span>  
  
- <span data-ttu-id="1078c-188">ウィンドウの<xref:System.Windows.Window.Activated>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="1078c-188">The window's <xref:System.Windows.Window.Activated> event is raised.</span></span>  
  
- <span data-ttu-id="1078c-189">直前にアクティブだったウィンドウは非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="1078c-189">The previously activated window is deactivated.</span></span>  
  
- <span data-ttu-id="1078c-190">ウィンドウと<xref:System.Windows.Window.Activated>イベントは<xref:System.Windows.Window.Deactivated>、ユーザーの操作に応じて、期待どおりに発生します。</span><span class="sxs-lookup"><span data-stu-id="1078c-190">The window's <xref:System.Windows.Window.Deactivated> and <xref:System.Windows.Window.Activated> events are subsequently raised as expected in response to user actions.</span></span>  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a><span data-ttu-id="1078c-191">ウィンドウのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="1078c-191">Window Activation</span></span>  
 <span data-ttu-id="1078c-192">ウィンドウが最初に開かれると、そのウィンドウはアクティブウィンドウになります (に設定<xref:System.Windows.Window.ShowActivated%2A>されている場合`false`を除く)。</span><span class="sxs-lookup"><span data-stu-id="1078c-192">When a window is first opened, it becomes the active window (unless it is shown with <xref:System.Windows.Window.ShowActivated%2A> set to `false`).</span></span> <span data-ttu-id="1078c-193">*アクティブ ウィンドウ*は、キー ストロークやマウス クリックなど、現在ユーザー入力をキャプチャしているウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1078c-193">The *active window* is the window that is currently capturing user input, such as key strokes and mouse clicks.</span></span> <span data-ttu-id="1078c-194">ウィンドウがアクティブになると、イベントが発生します<xref:System.Windows.Window.Activated>。</span><span class="sxs-lookup"><span data-stu-id="1078c-194">When a window becomes active, it raises the <xref:System.Windows.Window.Activated> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-195">ウィンドウが最初に開かれたときに、 <xref:System.Windows.FrameworkElement.Loaded> <xref:System.Windows.Window.ContentRendered>イベントが発生した後にのみ<xref:System.Windows.Window.Activated>、 イベントと イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="1078c-195">When a window is first opened, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.Window.ContentRendered> events are raised only after the <xref:System.Windows.Window.Activated> event is raised.</span></span> <span data-ttu-id="1078c-196">この問題を念頭に置いて、ウィンドウが上が<xref:System.Windows.Window.ContentRendered>ったときにウィンドウを開いたと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="1078c-196">With this in mind, a window can effectively be considered opened when <xref:System.Windows.Window.ContentRendered> is raised.</span></span>  
  
 <span data-ttu-id="1078c-197">ウィンドウがアクティブになった後で、ユーザーは同じアプリケーションの別のウィンドウをアクティブ化したり、別のアプリケーションをアクティブ化したりできます。</span><span class="sxs-lookup"><span data-stu-id="1078c-197">After a window becomes active, a user can activate another window in the same application, or activate another application.</span></span> <span data-ttu-id="1078c-198">この場合、現在アクティブなウィンドウは非アクティブになり、イベントが発生<xref:System.Windows.Window.Deactivated>します。</span><span class="sxs-lookup"><span data-stu-id="1078c-198">When that happens, the currently active window becomes deactivated and raises the <xref:System.Windows.Window.Deactivated> event.</span></span> <span data-ttu-id="1078c-199">同様に、ユーザーが現在非アクティブになっているウィンドウを選択すると、ウィンドウが再びアクティブになり<xref:System.Windows.Window.Activated>、発生します。</span><span class="sxs-lookup"><span data-stu-id="1078c-199">Likewise, when the user selects a currently deactivated window, the window becomes active again and <xref:System.Windows.Window.Activated> is raised.</span></span>  
  
 <span data-ttu-id="1078c-200">一<xref:System.Windows.Window.Activated>般的な処理の理由<xref:System.Windows.Window.Deactivated>の 1 つは、ウィンドウがアクティブなときにのみ実行できる機能を有効または無効にすることです。</span><span class="sxs-lookup"><span data-stu-id="1078c-200">One common reason to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> is to enable and disable functionality that can only run when a window is active.</span></span> <span data-ttu-id="1078c-201">たとえば、ゲームやビデオ プレーヤーなど、ユーザーの一定の入力や介入が必要な対話型コンテンツが表示されるウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-201">For example, some windows display interactive content that requires constant user input or attention, including games and video players.</span></span> <span data-ttu-id="1078c-202">次の例は、この動作を処理<xref:System.Windows.Window.Activated>して<xref:System.Windows.Window.Deactivated>実装する方法を示す、簡略化されたビデオ プレーヤーです。</span><span class="sxs-lookup"><span data-stu-id="1078c-202">The following example is a simplified video player that demonstrates how to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> to implement this behavior.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 <span data-ttu-id="1078c-203">ウィンドウが非アクティブでも、バックグラウンドでコードを実行できる種類のアプリケーションもあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-203">Other types of applications may still run code in the background when a window is deactivated.</span></span> <span data-ttu-id="1078c-204">たとえば、メール クライアントは、ユーザーが他のアプリケーションを使用している間もメール サーバーへのポーリングを続けています。</span><span class="sxs-lookup"><span data-stu-id="1078c-204">For example, a mail client may continue polling the mail server while the user is using other applications.</span></span> <span data-ttu-id="1078c-205">このようなアプリケーションは、メイン ウィンドウが非アクティブのときにも、別の動作や追加の動作を頻繁に実行します。</span><span class="sxs-lookup"><span data-stu-id="1078c-205">Applications like these often provide different or additional behavior while the main window is deactivated.</span></span> <span data-ttu-id="1078c-206">メール プログラムでは、新しいメール アイテムを受信トレイに追加し、通知アイコンをシステム トレイに追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-206">With respect to the mail program, this may mean both adding the new mail item to the inbox and adding a notification icon to the system tray.</span></span> <span data-ttu-id="1078c-207">通知アイコンは、メール ウィンドウがアクティブでない場合にのみ表示する必要<xref:System.Windows.Window.IsActive%2A>があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-207">A notification icon need only be displayed when the mail window isn't active, which can be determined by inspecting the <xref:System.Windows.Window.IsActive%2A> property.</span></span>  
  
 <span data-ttu-id="1078c-208">バックグラウンド タスクが完了した場合、ウィンドウはメソッドを呼び出<xref:System.Windows.Window.Activate%2A>すことによって、より緊急にユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-208">If a background task completes, a window may want to notify the user more urgently by calling <xref:System.Windows.Window.Activate%2A> method.</span></span> <span data-ttu-id="1078c-209">呼び出されたときに<xref:System.Windows.Window.Activate%2A>ユーザーがアクティブ化された別のアプリケーションと対話している場合、ウィンドウのタスク バー ボタンが点滅します。</span><span class="sxs-lookup"><span data-stu-id="1078c-209">If the user is interacting with another application activated when <xref:System.Windows.Window.Activate%2A> is called, the window's taskbar button flashes.</span></span> <span data-ttu-id="1078c-210">ユーザーが現在のアプリケーションと対話している場合、呼び<xref:System.Windows.Window.Activate%2A>出しによってウィンドウがフォアグラウンドに移動します。</span><span class="sxs-lookup"><span data-stu-id="1078c-210">If a user is interacting with the current application, calling <xref:System.Windows.Window.Activate%2A> will bring the window to the foreground.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-211">および イベントを使用して、アプリケーション<xref:System.Windows.Application.Activated?displayProperty=nameWithType>スコープ<xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>のアクティブ化を処理できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-211">You can handle application-scope activation using the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> and <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> events.</span></span>  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a><span data-ttu-id="1078c-212">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="1078c-212">Closing a Window</span></span>  
 <span data-ttu-id="1078c-213">ウィンドウの有効期間は、表示されたときに開始し、ユーザーが閉じたときに終了します。</span><span class="sxs-lookup"><span data-stu-id="1078c-213">The life of a window starts coming to an end when a user closes it.</span></span> <span data-ttu-id="1078c-214">ウィンドウを閉じるには、非クライアント領域の要素を使用します。これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1078c-214">A window can be closed by using elements in the non-client area, including the following:</span></span>  
  
- <span data-ttu-id="1078c-215">**[システム**] メニューの [**閉じる**] 項目</span><span class="sxs-lookup"><span data-stu-id="1078c-215">The **Close** item of the **System** menu.</span></span>  
  
- <span data-ttu-id="1078c-216">Alt キーを押しながら F4 キーを押す。</span><span class="sxs-lookup"><span data-stu-id="1078c-216">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="1078c-217">**閉じる**ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="1078c-217">Pressing the **Close** button.</span></span>  
  
 <span data-ttu-id="1078c-218">クライアント領域にさらに機構を追加してウィンドウを閉じることもできます。その一般的な例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="1078c-218">You can provide additional mechanisms to the client area to close a window, the more common of which include the following:</span></span>  
  
- <span data-ttu-id="1078c-219">[**ファイル]** メニューの **[終了]** 項目で、通常はメイン のアプリケーション ウィンドウ用です。</span><span class="sxs-lookup"><span data-stu-id="1078c-219">An **Exit** item in the **File** menu, typically for main application windows.</span></span>  
  
- <span data-ttu-id="1078c-220">[**ファイル]** メニューの [**閉じる**] 項目で、通常はセカンダリ アプリケーション ウィンドウで表示されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-220">A **Close** item in the **File** menu, typically on a secondary application window.</span></span>  
  
- <span data-ttu-id="1078c-221">通常モーダル ダイアログ ボックスの **[キャンセル]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="1078c-221">A **Cancel** button, typically on a modal dialog box.</span></span>  
  
- <span data-ttu-id="1078c-222">通常、モードレス ダイアログ ボックスで閉**じる**ボタン。</span><span class="sxs-lookup"><span data-stu-id="1078c-222">A **Close** button, typically on a modeless dialog box.</span></span>  
  
 <span data-ttu-id="1078c-223">これらのカスタム メカニズムのいずれかに応答してウィンドウを閉じるには、<xref:System.Windows.Window.Close%2A>メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-223">To close a window in response to one of these custom mechanisms, you need to call the <xref:System.Windows.Window.Close%2A> method.</span></span> <span data-ttu-id="1078c-224">次の例では、[**ファイル]** メニューの **[終了]** をクリックしてウィンドウを閉じる機能を実装しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-224">The following example implements the ability to close a window by choosing the **Exit** on the **File** menu.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 <span data-ttu-id="1078c-225">ウィンドウが閉じると、<xref:System.Windows.Window.Closing>と<xref:System.Windows.Window.Closed>の 2 つのイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="1078c-225">When a window closes, it raises two events: <xref:System.Windows.Window.Closing> and <xref:System.Windows.Window.Closed>.</span></span>  
  
 <span data-ttu-id="1078c-226"><xref:System.Windows.Window.Closing>ウィンドウが閉じる前に発生し、ウィンドウの閉じを防ぐことができるメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="1078c-226"><xref:System.Windows.Window.Closing> is raised before the window closes, and it provides a mechanism by which window closure can be prevented.</span></span> <span data-ttu-id="1078c-227">ウィンドウが閉じるのを防ぐのは、一般的に、ウィンドウ コンテンツに変更したデータが含まれている場合です。</span><span class="sxs-lookup"><span data-stu-id="1078c-227">One common reason to prevent window closure is if window content contains modified data.</span></span> <span data-ttu-id="1078c-228">この状況では、イベント<xref:System.Windows.Window.Closing>を処理して、データがダーティかどうかを判断し、データを保存せずにウィンドウを閉じ続けるか、またはウィンドウの閉じをキャンセルするかをユーザーに確認できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-228">In this situation, the <xref:System.Windows.Window.Closing> event can be handled to determine whether data is dirty and, if so, to ask the user whether to either continue closing the window without saving the data or to cancel window closure.</span></span> <span data-ttu-id="1078c-229">次の例は、処理の重要な側面<xref:System.Windows.Window.Closing>を示しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-229">The following example shows the key aspects of handling <xref:System.Windows.Window.Closing>.</span></span>  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 <span data-ttu-id="1078c-230">イベント<xref:System.Windows.Window.Closing>ハンドラには、<xref:System.ComponentModel.CancelEventArgs>ウィンドウを閉じないように`Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>設定`true`したプロパティを実装する が渡されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-230">The <xref:System.Windows.Window.Closing> event handler is passed a <xref:System.ComponentModel.CancelEventArgs>, which implements the `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property that you set to `true` to prevent a window from closing.</span></span>  
  
 <span data-ttu-id="1078c-231">処理<xref:System.Windows.Window.Closing>されない場合、または処理済みでキャンセルされなかった場合は、ウィンドウが閉じます。</span><span class="sxs-lookup"><span data-stu-id="1078c-231">If <xref:System.Windows.Window.Closing> is not handled, or it is handled but not canceled, the window will close.</span></span> <span data-ttu-id="1078c-232">実際にウィンドウが閉じる直前に<xref:System.Windows.Window.Closed>、上げられます。</span><span class="sxs-lookup"><span data-stu-id="1078c-232">Just before a window actually closes, <xref:System.Windows.Window.Closed> is raised.</span></span> <span data-ttu-id="1078c-233">この時点で、ウィンドウが閉じるのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="1078c-233">At this point, a window cannot be prevented from closing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-234">メイン アプリケーション ウィンドウが閉じる (<xref:System.Windows.Application.MainWindow%2A>参照) または最後のウィンドウが閉じたときに、アプリケーションを自動的にシャットダウンするようにアプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-234">An application can be configured to shut down automatically when either the main application window closes (see <xref:System.Windows.Application.MainWindow%2A>) or the last window closes.</span></span> <span data-ttu-id="1078c-235">詳細については、<xref:System.Windows.Application.ShutdownMode%2A> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-235">For details, see <xref:System.Windows.Application.ShutdownMode%2A>.</span></span>  
  
 <span data-ttu-id="1078c-236">非クライアント領域とクライアント領域で提供されるメカニズムを使用してウィンドウを明示的に閉じることができますが、アプリケーションまたは Windows の他の部分での動作の結果として、次のようなウィンドウを暗黙的に閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="1078c-236">While a window can be explicitly closed through mechanisms provided in the non-client and client areas, a window can also be implicitly closed as a result of behavior in other parts of the application or Windows, including the following:</span></span>  
  
- <span data-ttu-id="1078c-237">ユーザーがログオフするか、Windows をシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="1078c-237">A user logs off or shuts down Windows.</span></span>  
  
- <span data-ttu-id="1078c-238">ウィンドウの所有者が閉じます (を<xref:System.Windows.Window.Owner%2A>参照)。</span><span class="sxs-lookup"><span data-stu-id="1078c-238">A window's owner closes (see <xref:System.Windows.Window.Owner%2A>).</span></span>  
  
- <span data-ttu-id="1078c-239">メイン アプリケーション ウィンドウは閉<xref:System.Windows.Application.ShutdownMode%2A>じ<xref:System.Windows.ShutdownMode.OnMainWindowClose>られます。</span><span class="sxs-lookup"><span data-stu-id="1078c-239">The main application window is closed and <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>  
  
- <span data-ttu-id="1078c-240"><xref:System.Windows.Application.Shutdown%2A> が呼び出されます</span><span class="sxs-lookup"><span data-stu-id="1078c-240"><xref:System.Windows.Application.Shutdown%2A> is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-241">ウィンドウを閉じると、再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="1078c-241">A window cannot be reopened after it is closed.</span></span>  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a><span data-ttu-id="1078c-242">ウィンドウの有効期間イベント</span><span class="sxs-lookup"><span data-stu-id="1078c-242">Window Lifetime Events</span></span>  
 <span data-ttu-id="1078c-243">次の図は、ウィンドウの有効期間における主要なイベントのシーケンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-243">The following illustration shows the sequence of the principal events in the lifetime of a window:</span></span>  
  
 ![ウィンドウの有効期間内のイベントを示す図。](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 <span data-ttu-id="1078c-245">次の図は、アクティブ化なしで表示されるウィンドウの有効期間 (ウィンドウが表示される前に<xref:System.Windows.Window.ShowActivated%2A>`false`設定されている) の有効期間におけるプリンシパル イベントのシーケンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-245">The following illustration shows the sequence of the principal events in the lifetime of a window that is shown without activation (<xref:System.Windows.Window.ShowActivated%2A> is set to `false` before the window is shown):</span></span>  
  
 ![アクティブ化せずにウィンドウの有効期間内のイベントを示す図。](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a><span data-ttu-id="1078c-247">ウィンドウの位置</span><span class="sxs-lookup"><span data-stu-id="1078c-247">Window Location</span></span>  
 <span data-ttu-id="1078c-248">ウィンドウが開いているとき、ウィンドウはデスクトップに対して相対的な x ディメンションと y ディメンションの位置にあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-248">While a window is open, it has a location in the x and y dimensions relative to the desktop.</span></span> <span data-ttu-id="1078c-249">この位置は、それぞれと<xref:System.Windows.Window.Left%2A><xref:System.Windows.Window.Top%2A>プロパティを検査することによって決定できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-249">This location can be determined by inspecting the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties, respectively.</span></span> <span data-ttu-id="1078c-250">これらのプロパティを設定して、ウィンドウの位置を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-250">You can set these properties to change the location of the window.</span></span>  
  
 <span data-ttu-id="1078c-251">プロパティを次<xref:System.Windows.Window><xref:System.Windows.Window.WindowStartupLocation%2A><xref:System.Windows.WindowStartupLocation>のいずれかの列挙値で設定することで、最初に表示される a の初期位置を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1078c-251">You can also specify the initial location of a <xref:System.Windows.Window> when it first appears by setting the <xref:System.Windows.Window.WindowStartupLocation%2A> property with one of the following <xref:System.Windows.WindowStartupLocation> enumeration values:</span></span>  
  
- <span data-ttu-id="1078c-252"><xref:System.Windows.WindowStartupLocation.CenterOwner> (規定値)</span><span class="sxs-lookup"><span data-stu-id="1078c-252"><xref:System.Windows.WindowStartupLocation.CenterOwner> (default)</span></span>  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 <span data-ttu-id="1078c-253">スタートアップの<xref:System.Windows.WindowStartupLocation.Manual>場所が に指定され、<xref:System.Windows.Window.Left%2A>プロパティ<xref:System.Windows.Window.Top%2A>が設定されていない場合は、<xref:System.Windows.Window>で表示する場所を Windows に要求します。</span><span class="sxs-lookup"><span data-stu-id="1078c-253">If the startup location is specified as <xref:System.Windows.WindowStartupLocation.Manual>, and the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties have not been set, <xref:System.Windows.Window> will ask Windows for a location to appear in.</span></span>  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a><span data-ttu-id="1078c-254">最上位ウィンドウと Z オーダー</span><span class="sxs-lookup"><span data-stu-id="1078c-254">Topmost Windows and Z-Order</span></span>  
 <span data-ttu-id="1078c-255">ウィンドウには、x 位置と y 位置に加えて、他のウィンドウを基準にして垂直位置を決定する z ディメンションの位置もあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-255">Besides having an x and y location, a window also has a location in the z dimension, which determines its vertical position with respect to other windows.</span></span> <span data-ttu-id="1078c-256">これはウィンドウの z オーダーともいい、標準 z オーダーと最上位 z オーダーの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-256">This is known as the window's z-order, and there are two types: normal z-order and topmost z-order.</span></span> <span data-ttu-id="1078c-257">通常の*Z オーダー*でのウィンドウの位置は、現在アクティブかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="1078c-257">The location of a window in the *normal z-order* is determined by whether it is currently active or not.</span></span> <span data-ttu-id="1078c-258">既定では、ウィンドウは標準 z オーダーにあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-258">By default, a window is located in the normal z-order.</span></span> <span data-ttu-id="1078c-259">*一番上*の z オーダーのウィンドウの位置も、現在アクティブかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="1078c-259">The location of a window in the *topmost z-order* is also determined by whether it is currently active or not.</span></span> <span data-ttu-id="1078c-260">また、最上位 z オーダーにあるウィンドウは、常に、標準 z オーダーにあるウィンドウの上に位置します。</span><span class="sxs-lookup"><span data-stu-id="1078c-260">Furthermore, windows in the topmost z-order are always located above windows in the normal z-order.</span></span> <span data-ttu-id="1078c-261">ウィンドウは、プロパティを に設定することで、最上位の z<xref:System.Windows.Window.Topmost%2A>オーダー`true`に配置されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-261">A window is located in the topmost z-order by setting its <xref:System.Windows.Window.Topmost%2A> property to `true`.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 <span data-ttu-id="1078c-262">各 z オーダー内では、現在アクティブなウィンドウは、同じ z オーダーにある他のすべてのウィンドウの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-262">Within each z-order, the currently active window appears above all other windows in the same z-order.</span></span>  
  
<a name="WindowSize"></a>
## <a name="window-size"></a><span data-ttu-id="1078c-263">ウィンドウ サイズ</span><span class="sxs-lookup"><span data-stu-id="1078c-263">Window Size</span></span>  
 <span data-ttu-id="1078c-264">ウィンドウには、デスクトップの場所があるほかに、さまざまな幅と高さのプロパティや<xref:System.Windows.Window.SizeToContent%2A>.</span><span class="sxs-lookup"><span data-stu-id="1078c-264">Besides having a desktop location, a window has a size that is determined by several properties, including the various width and height properties and <xref:System.Windows.Window.SizeToContent%2A>.</span></span>  
  
 <span data-ttu-id="1078c-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>、、<xref:System.Windows.FrameworkElement.Width%2A>および<xref:System.Windows.FrameworkElement.MaxWidth%2A>は、ウィンドウの有効期間中に持つことができる幅の範囲を管理するために使用され、次の例に示すように構成されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.MaxWidth%2A> are used to manage the range of widths that a window can have during its lifetime, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 <span data-ttu-id="1078c-266">ウィンドウの高さは<xref:System.Windows.FrameworkElement.MinHeight%2A>、 <xref:System.Windows.FrameworkElement.Height%2A>、および<xref:System.Windows.FrameworkElement.MaxHeight%2A>によって管理され、次の例のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-266">Window height is managed by <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 <span data-ttu-id="1078c-267">さまざまな幅の値と高さの値はそれぞれ範囲を指定しているため、サイズを変更できるウィンドウの幅と高さは、それぞれの寸法に指定された範囲内のいずれかの値を取ります。</span><span class="sxs-lookup"><span data-stu-id="1078c-267">Because the various width values and height values each specify a range, it is possible for the width and height of a resizable window to be anywhere within the specified range for the respective dimension.</span></span> <span data-ttu-id="1078c-268">現在の幅と高さを検出するには、<xref:System.Windows.FrameworkElement.ActualWidth%2A>それぞれ<xref:System.Windows.FrameworkElement.ActualHeight%2A>と を検査します。</span><span class="sxs-lookup"><span data-stu-id="1078c-268">To detect its current width and height, inspect <xref:System.Windows.FrameworkElement.ActualWidth%2A> and <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectively.</span></span>  
  
 <span data-ttu-id="1078c-269">ウィンドウの幅と高さをウィンドウのコンテンツのサイズに合わせて設定する場合は、次の値を<xref:System.Windows.Window.SizeToContent%2A>持つプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-269">If you'd like the width and height of your window to have a size that fits to the size of the window's content, you can use the <xref:System.Windows.Window.SizeToContent%2A> property, which has the following values:</span></span>  
  
- <span data-ttu-id="1078c-270"><xref:System.Windows.SizeToContent.Manual>.</span><span class="sxs-lookup"><span data-stu-id="1078c-270"><xref:System.Windows.SizeToContent.Manual>.</span></span> <span data-ttu-id="1078c-271">効果 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="1078c-271">No effect (default).</span></span>  
  
- <span data-ttu-id="1078c-272"><xref:System.Windows.SizeToContent.Width>.</span><span class="sxs-lookup"><span data-stu-id="1078c-272"><xref:System.Windows.SizeToContent.Width>.</span></span> <span data-ttu-id="1078c-273">コンテンツの幅に合わせると、コンテンツの幅と設定<xref:System.Windows.FrameworkElement.MinWidth%2A>の<xref:System.Windows.FrameworkElement.MaxWidth%2A>両方と同じ効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="1078c-273">Fit to content width, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
- <span data-ttu-id="1078c-274"><xref:System.Windows.SizeToContent.Height>.</span><span class="sxs-lookup"><span data-stu-id="1078c-274"><xref:System.Windows.SizeToContent.Height>.</span></span> <span data-ttu-id="1078c-275">コンテンツの高さに合わせて、コンテンツの高さの両方<xref:System.Windows.FrameworkElement.MinHeight%2A>を設定<xref:System.Windows.FrameworkElement.MaxHeight%2A>するのと同じ効果があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-275">Fit to content height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content.</span></span>  
  
- <span data-ttu-id="1078c-276"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span><span class="sxs-lookup"><span data-stu-id="1078c-276"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span></span> <span data-ttu-id="1078c-277">コンテンツの<xref:System.Windows.FrameworkElement.MinHeight%2A>幅と高さの両方を設定し、コンテンツの高さに設定<xref:System.Windows.FrameworkElement.MaxHeight%2A>し、コンテンツの幅と両方<xref:System.Windows.FrameworkElement.MinWidth%2A>を設定するの<xref:System.Windows.FrameworkElement.MaxWidth%2A>と同じ効果を持つコンテンツの幅と高さに合わせます。</span><span class="sxs-lookup"><span data-stu-id="1078c-277">Fit to content width and height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content, and setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
 <span data-ttu-id="1078c-278">次の例では、ウィンドウを最初に表示するときに、そのコンテンツに合わせて垂直方向と水平方向の両方のサイズを自動的に変更するウィンドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-278">The following example shows a window that automatically sizes to fit its content, both vertically and horizontally, when first shown.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 <span data-ttu-id="1078c-279">次の例は、コンテンツに合<xref:System.Windows.Window.SizeToContent%2A>わせてウィンドウのサイズを変更する方法を指定するコードでプロパティを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-279">The following example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property in code to specify how a window resizes to fit its content    .</span></span>
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a><span data-ttu-id="1078c-280">サイズ変更プロパティの優先順位</span><span class="sxs-lookup"><span data-stu-id="1078c-280">Order of Precedence for Sizing Properties</span></span>  
 <span data-ttu-id="1078c-281">基本的に、ウィンドウのさまざまなサイズのプロパティを組み合わせて、サイズを変更できるウィンドウの幅と高さの範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="1078c-281">Essentially, the various sizes properties of a window combine to define the range of width and height for a resizable window.</span></span> <span data-ttu-id="1078c-282">有効な範囲を維持するために、<xref:System.Windows.Window>次の優先順位を使用してサイズ プロパティの値を評価します。</span><span class="sxs-lookup"><span data-stu-id="1078c-282">To ensure a valid range is maintained, <xref:System.Windows.Window> evaluates the values of the size properties using the following orders of precedence.</span></span>  
  
 <span data-ttu-id="1078c-283">**高さのプロパティ:**</span><span class="sxs-lookup"><span data-stu-id="1078c-283">**For Height Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="1078c-284">**幅のプロパティ:**</span><span class="sxs-lookup"><span data-stu-id="1078c-284">**For Width Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="1078c-285">優先順位は、<xref:System.Windows.Window.WindowState%2A>最大化時のウィンドウのサイズを決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1078c-285">The order of precedence can also determine the size of a window when it is maximized, which is managed with the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="WindowState"></a>
## <a name="window-state"></a><span data-ttu-id="1078c-286">ウィンドウの状態</span><span class="sxs-lookup"><span data-stu-id="1078c-286">Window State</span></span>  
 <span data-ttu-id="1078c-287">サイズを変更できるウィンドウには、有効期間中、通常、最小化、最大化の 3 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-287">During the lifetime of a resizable window, it can have three states: normal, minimized, and maximized.</span></span> <span data-ttu-id="1078c-288">*通常*の状態のウィンドウは、ウィンドウの既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="1078c-288">A window with a *normal* state is the default state of a window.</span></span> <span data-ttu-id="1078c-289">この状態のウィンドウは、サイズ変更グリップ、またはサイズ変更可能な場合は境界線を使用して、ユーザーが移動したりサイズ変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="1078c-289">A window with this state allows a user to move and resize it by using a resize grip or the border, if it is resizable.</span></span>  
  
 <span data-ttu-id="1078c-290">*最小化された*状態のウィンドウは、タスク バー ボタンに設定されている<xref:System.Windows.Window.ShowInTaskbar%2A>場合は折`true`りたたまれます。それ以外の場合は、可能な限り小さいサイズに縮小され、デスクトップの左下隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="1078c-290">A window with a *minimized* state collapses to its task bar button if <xref:System.Windows.Window.ShowInTaskbar%2A> is set to `true`; otherwise, it collapses to the smallest possible size it can be and relocates itself to the bottom-left corner of the desktop.</span></span> <span data-ttu-id="1078c-291">最小化されたウィンドウはいずれの種類も、境界線またはサイズ変更グリップを使用してサイズ変更できません。ただし、タスク バーに表示されていない最小化されたウィンドウはデスクトップの任意の場所にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="1078c-291">Neither type of minimized window can be resized using a border or resize grip, although a minimized window that isn't shown in the task bar can be dragged around the desktop.</span></span>  
  
 <span data-ttu-id="1078c-292">*最大化された*状態のウィンドウは、<xref:System.Windows.FrameworkElement.MaxWidth%2A><xref:System.Windows.FrameworkElement.MaxHeight%2A><xref:System.Windows.Window.SizeToContent%2A>最大サイズまで拡張されます。</span><span class="sxs-lookup"><span data-stu-id="1078c-292">A window with a *maximized* state expands to the maximum size it can be, which will only be as large as its <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.Window.SizeToContent%2A> properties dictate.</span></span> <span data-ttu-id="1078c-293">最小化されたウィンドウと同様、最大化されたウィンドウは、サイズ変更グリップを使用したり、境界線をドラッグしたりすることによってサイズ変更できません。</span><span class="sxs-lookup"><span data-stu-id="1078c-293">Like a minimized window, a maximized window cannot be resized by using a resize grip or by dragging the border.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1078c-294">ウィンドウの<xref:System.Windows.Window.Top%2A>プロパティ 、、、<xref:System.Windows.Window.Left%2A>および<xref:System.Windows.FrameworkElement.Height%2A><xref:System.Windows.FrameworkElement.Width%2A>プロパティの値は、ウィンドウが現在最大化または最小化されている場合でも、常に通常の状態の値を表します。</span><span class="sxs-lookup"><span data-stu-id="1078c-294">The values of the <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.Height%2A> properties of a window always represent the values for the normal state, even when the window is currently maximized or minimized.</span></span>  
  
 <span data-ttu-id="1078c-295">ウィンドウの状態は、次<xref:System.Windows.Window.WindowState%2A><xref:System.Windows.WindowState>のいずれかの列挙値を持つことができるプロパティを設定することによって構成できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-295">The state of a window can be configured by setting its <xref:System.Windows.Window.WindowState%2A> property, which can have one of the following <xref:System.Windows.WindowState> enumeration values:</span></span>  
  
- <span data-ttu-id="1078c-296"><xref:System.Windows.WindowState.Normal> (規定値)</span><span class="sxs-lookup"><span data-stu-id="1078c-296"><xref:System.Windows.WindowState.Normal> (default)</span></span>  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 <span data-ttu-id="1078c-297">開くときに最大化されて表示されるウィンドウを作成する方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1078c-297">The following example shows how to create a window that is shown as maximized when it opens.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 <span data-ttu-id="1078c-298">一般に、ウィンドウの<xref:System.Windows.Window.WindowState%2A>初期状態を設定するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-298">In general, you should set <xref:System.Windows.Window.WindowState%2A> to configure the initial state of a window.</span></span> <span data-ttu-id="1078c-299">サイズ変更可能なウィンドウが表示されると、ユーザーはウィンドウのタイトル バーにある最小化ボタン、最大化ボタン、および元に戻すボタンを使用して、ウィンドウの状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-299">Once a resizable window is shown, users can press the minimize, maximize, and restore buttons on the window's title bar to change the window state.</span></span>  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a><span data-ttu-id="1078c-300">ウィンドウの外観</span><span class="sxs-lookup"><span data-stu-id="1078c-300">Window Appearance</span></span>  
 <span data-ttu-id="1078c-301">ウィンドウのクライアント領域の外観を変更するために、ボタン、ラベル、テキスト ボックスなど、ウィンドウ固有のコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="1078c-301">You change the appearance of the client area of a window by adding window-specific content to it, such as buttons, labels, and text boxes.</span></span> <span data-ttu-id="1078c-302">非クライアント領域を構成するには、<xref:System.Windows.Window>ウィンドウのアイコンを設定したり<xref:System.Windows.Window.Icon%2A><xref:System.Windows.Window.Title%2A>、タイトルを設定したりするためのプロパティを複数提供します。</span><span class="sxs-lookup"><span data-stu-id="1078c-302">To configure the non-client area, <xref:System.Windows.Window> provides several properties, which include <xref:System.Windows.Window.Icon%2A> to set a window's icon and <xref:System.Windows.Window.Title%2A> to set its title.</span></span>  
  
 <span data-ttu-id="1078c-303">また、ウィンドウのサイズ変更モード、ウィンドウ スタイル、デスクトップのタスク バーにボタンとして表示するかどうかを構成して、非クライアント領域の境界線の外観と動作も変更できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-303">You can also change the appearance and behavior of non-client area border by configuring a window's resize mode, window style, and whether it appears as a button in the desktop task bar.</span></span>  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a><span data-ttu-id="1078c-304">サイズ変更モード</span><span class="sxs-lookup"><span data-stu-id="1078c-304">Resize Mode</span></span>  
 <span data-ttu-id="1078c-305"><xref:System.Windows.Window.WindowStyle%2A>プロパティに応じて、ユーザーがウィンドウのサイズを変更する方法 (およびかどうかを) 制御できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-305">Depending on the <xref:System.Windows.Window.WindowStyle%2A> property, you can control how (and if) users can resize the window.</span></span> <span data-ttu-id="1078c-306">ウィンドウ スタイルの選択は、ユーザーがマウスで境界線をドラッグしてウィンドウのサイズを変更できるかどうか、**クライアント**以外の領域に最小化、**最大化**、**およびサイズ変更**の各ボタンを表示するかどうか、および表示される場合は有効にするかどうかに影響します。</span><span class="sxs-lookup"><span data-stu-id="1078c-306">The choice of window style affects whether a user can resize the window by dragging its border with the mouse, whether the **Minimize**, **Maximize**, and **Resize** buttons appear on the non-client area, and, if they do appear, whether they are enabled.</span></span>  
  
 <span data-ttu-id="1078c-307">ウィンドウのサイズを変更する方法は、次<xref:System.Windows.Window.ResizeMode%2A><xref:System.Windows.ResizeMode>のいずれかの列挙値を指定できるプロパティを設定することで構成できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-307">You can configure how a window resizes by setting its <xref:System.Windows.Window.ResizeMode%2A> property, which can be one of the following <xref:System.Windows.ResizeMode> enumeration values:</span></span>  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <span data-ttu-id="1078c-308"><xref:System.Windows.ResizeMode.CanResize> (規定値)</span><span class="sxs-lookup"><span data-stu-id="1078c-308"><xref:System.Windows.ResizeMode.CanResize> (default)</span></span>  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 <span data-ttu-id="1078c-309">と同様<xref:System.Windows.Window.WindowStyle%2A>に、ウィンドウのサイズ変更モードは、その有効期間中に変更される可能性が低い、つまり、マークアップから[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]設定する可能性が高いことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1078c-309">As with <xref:System.Windows.Window.WindowStyle%2A>, the resize mode of a window is unlikely to change during its lifetime, which means that you'll most likely set it from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 <span data-ttu-id="1078c-310">ウィンドウが最大化、最小化、または復元されているかどうかを、プロパティを調べることによって検出できることに<xref:System.Windows.Window.WindowState%2A>注意してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-310">Note that you can detect whether a window is maximized, minimized, or restored by inspecting the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="Window_Style"></a>
### <a name="window-style"></a><span data-ttu-id="1078c-311">ウィンドウ スタイル</span><span class="sxs-lookup"><span data-stu-id="1078c-311">Window Style</span></span>  
 <span data-ttu-id="1078c-312">ウィンドウの非クライアント領域から公開される境界線は、多くのアプリケーションに適しています。</span><span class="sxs-lookup"><span data-stu-id="1078c-312">The border that is exposed from the non-client area of a window is suitable for most applications.</span></span> <span data-ttu-id="1078c-313">ただし、ウィンドウの種類によって、異なる種類の境界線が必要な状況や、境界線がまったく必要ない状況があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-313">However, there are circumstances where different types of borders are needed, or no borders are needed at all, depending on the type of window.</span></span>  
  
 <span data-ttu-id="1078c-314">ウィンドウが取得する境界線の種類を制御するには、列挙体<xref:System.Windows.Window.WindowStyle%2A>の次のいずれかの値を使用して、その<xref:System.Windows.WindowStyle>プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="1078c-314">To control what type of border a window gets, you set its <xref:System.Windows.Window.WindowStyle%2A> property with one of the following values of the <xref:System.Windows.WindowStyle> enumeration:</span></span>  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <span data-ttu-id="1078c-315"><xref:System.Windows.WindowStyle.SingleBorderWindow> (規定値)</span><span class="sxs-lookup"><span data-stu-id="1078c-315"><xref:System.Windows.WindowStyle.SingleBorderWindow> (default)</span></span>  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 <span data-ttu-id="1078c-316">これらのウィンドウ スタイルの効果を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1078c-316">The effect of these window styles are illustrated in the following figure:</span></span>  
  
 ![ウィンドウの境界線スタイルの図。](./media/wpf-windows-overview/window-border-styles.png)  
  
 <span data-ttu-id="1078c-318">マークアップまたはコード<xref:System.Windows.Window.WindowStyle%2A>を[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]使用して設定できます。ウィンドウの有効期間中に変更される可能性は低いため、マークアップを使用して[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]構成する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1078c-318">You can set <xref:System.Windows.Window.WindowStyle%2A> using either [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup or code; because it is unlikely to change during the lifetime of a window, you will most likely configure it using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a><span data-ttu-id="1078c-319">四角形以外のウィンドウ スタイル</span><span class="sxs-lookup"><span data-stu-id="1078c-319">Non-Rectangular Window Style</span></span>  
 <span data-ttu-id="1078c-320">また、境界線<xref:System.Windows.Window.WindowStyle%2A>スタイルが十分でない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1078c-320">There are also situations where the border styles that <xref:System.Windows.Window.WindowStyle%2A> allows you to have are not sufficient.</span></span> <span data-ttu-id="1078c-321">たとえば、Microsoft Windows メディア プレーヤーが使用するような、四角形以外の境界線を持つアプリケーションを作成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-321">For example, you may want to create an application with a non-rectangular border, like Microsoft Windows Media Player uses.</span></span>  
  
 <span data-ttu-id="1078c-322">たとえば、次の図に示す吹き出しウィンドウを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="1078c-322">For example, consider the speech bubble window shown in the following figure:</span></span>  
  
 ![「ドラッグミー」と言う吹き出しウィンドウ。](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 <span data-ttu-id="1078c-324">この種類のウィンドウは、プロパティを<xref:System.Windows.Window.WindowStyle%2A>に<xref:System.Windows.WindowStyle.None>設定し、透過性を備えた特別<xref:System.Windows.Window>なサポートを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="1078c-324">This type of window can be created by setting the <xref:System.Windows.Window.WindowStyle%2A> property to <xref:System.Windows.WindowStyle.None>, and by using special support that <xref:System.Windows.Window> has for transparency.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 <span data-ttu-id="1078c-325">値をこの組み合わせで使用し、ウィンドウが完全に透明にレンダリングされるように設定します。</span><span class="sxs-lookup"><span data-stu-id="1078c-325">This combination of values instructs the window to render completely transparent.</span></span> <span data-ttu-id="1078c-326">この状態では、ウィンドウの非クライアント領域の表示要素 (閉じるメニュー、最小化ボタン、最大化ボタン、元に戻すボタンなど) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="1078c-326">In this state, the window's non-client area adornments (the Close menu, Minimize, Maximize, and Restore buttons, and so on) cannot be used.</span></span> <span data-ttu-id="1078c-327">したがって、独自の表示要素を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-327">Consequently, you need to provide your own.</span></span>  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a><span data-ttu-id="1078c-328">タスク バーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="1078c-328">Task Bar Presence</span></span>  

<span data-ttu-id="1078c-329">ウィンドウの既定の外観には、次の図に示すようなタスク バー ボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1078c-329">The default appearance of a window includes a taskbar button, like the one shown in the following figure:</span></span>

 ![タスク バー ボタンを持つウィンドウを示すスクリーンショット。](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 <span data-ttu-id="1078c-331">ウィンドウの種類によっては、メッセージ ボックスやダイアログ ボックスなど、タスク バー ボタンが表示されない場合があります (「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="1078c-331">Some types of windows don't have a task bar button, such as message boxes and dialog boxes (see [Dialog Boxes Overview](dialog-boxes-overview.md)).</span></span> <span data-ttu-id="1078c-332">ウィンドウのタスク バー ボタンを表示するかどうかを制御するには、プロパティを<xref:System.Windows.Window.ShowInTaskbar%2A>設定します`true`(既定)。</span><span class="sxs-lookup"><span data-stu-id="1078c-332">You can control whether the task bar button for a window is shown by setting the <xref:System.Windows.Window.ShowInTaskbar%2A> property (`true` by default).</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a><span data-ttu-id="1078c-333">セキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1078c-333">Security Considerations</span></span>  
 <span data-ttu-id="1078c-334"><xref:System.Windows.Window>には`UnmanagedCode`、セキュリティアクセス許可をインスタンス化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-334"><xref:System.Windows.Window> requires `UnmanagedCode` security permission to be instantiated.</span></span> <span data-ttu-id="1078c-335">ローカル コンピューターにインストールされ、ローカル コンピューターから起動されるアプリケーションの場合は、アプリケーションに付与されるアクセス許可セットの範囲内になります。</span><span class="sxs-lookup"><span data-stu-id="1078c-335">For applications installed on and launched from the local machine, this falls within the set of permissions that are granted to the application.</span></span>  
  
 <span data-ttu-id="1078c-336">ただし、これは、ClickOnce を使用してインターネットまたはローカル イントラネット ゾーンから起動されるアプリケーションに付与されるアクセス許可のセットの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="1078c-336">However, this falls outside the set of permissions granted to applications that are launched from the Internet or Local intranet zone using ClickOnce.</span></span> <span data-ttu-id="1078c-337">したがって、ユーザーは ClickOnce セキュリティ警告を受け取り、アプリケーションのアクセス許可セットを完全信頼に昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1078c-337">Consequently, users will receive a ClickOnce security warning and will need to elevate the permission set for the application to full trust.</span></span>  
  
 <span data-ttu-id="1078c-338">また、XBaAp は既定でウィンドウやダイアログ ボックスを表示できません。</span><span class="sxs-lookup"><span data-stu-id="1078c-338">Additionally, XBAPs cannot show windows or dialog boxes by default.</span></span> <span data-ttu-id="1078c-339">スタンドアロン アプリケーションのセキュリティに関する考慮事項については、「 [WPF セキュリティ戦略 - プラットフォーム セキュリティ](../wpf-security-strategy-platform-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-339">For a discussion on standalone application security considerations, see [WPF Security Strategy - Platform Security](../wpf-security-strategy-platform-security.md).</span></span>  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a><span data-ttu-id="1078c-340">その他の種類のウィンドウ</span><span class="sxs-lookup"><span data-stu-id="1078c-340">Other Types of Windows</span></span>  
 <span data-ttu-id="1078c-341"><xref:System.Windows.Navigation.NavigationWindow>は、ナビゲート可能なコンテンツをホストするように設計されたウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1078c-341"><xref:System.Windows.Navigation.NavigationWindow> is a window that is designed to host navigable content.</span></span> <span data-ttu-id="1078c-342">詳細については、「[ナビゲーションの概要](navigation-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-342">For more information, see [Navigation Overview](navigation-overview.md)).</span></span>  
  
 <span data-ttu-id="1078c-343">ダイアログ ボックスは、ユーザーから情報を収集して機能を完了するためによく使用されるウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="1078c-343">Dialog boxes are windows that are often used to gather information from a user to complete a function.</span></span> <span data-ttu-id="1078c-344">たとえば、ユーザーがファイルを開く場合、通常はアプリケーションによって **[ファイルを開く**] ダイアログ ボックスが表示され、ユーザーからファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="1078c-344">For example, when a user wants to open a file, the **Open File** dialog box is usually displayed by an application to get the file name from the user.</span></span> <span data-ttu-id="1078c-345">詳細については、「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1078c-345">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1078c-346">関連項目</span><span class="sxs-lookup"><span data-stu-id="1078c-346">See also</span></span>

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [<span data-ttu-id="1078c-347">ダイアログ ボックスの概要</span><span class="sxs-lookup"><span data-stu-id="1078c-347">Dialog Boxes Overview</span></span>](dialog-boxes-overview.md)
- [<span data-ttu-id="1078c-348">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="1078c-348">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
