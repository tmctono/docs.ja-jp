---
title: WPF ウィンドウの概要
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
ms.openlocfilehash: 5acebf0f88f3147bf274818f11697b480146701a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296122"
---
# <a name="wpf-windows-overview"></a><span data-ttu-id="f519d-102">WPF ウィンドウの概要</span><span class="sxs-lookup"><span data-stu-id="f519d-102">WPF Windows Overview</span></span>
<span data-ttu-id="f519d-103">ユーザーは、windows で Windows Presentation Foundation (WPF) スタンドアロン アプリケーションと対話します。</span><span class="sxs-lookup"><span data-stu-id="f519d-103">Users interact with Windows Presentation Foundation (WPF) standalone applications through windows.</span></span> <span data-ttu-id="f519d-104">ウィンドウの主な目的は、データを視覚化してユーザーがデータと対話できるコンテンツをホストすることです。</span><span class="sxs-lookup"><span data-stu-id="f519d-104">The primary purpose of a window is to host content that visualizes data and enables users to interact with data.</span></span> <span data-ttu-id="f519d-105">スタンドアロン[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]アプリケーションを使用して独自のウィンドウの提供、<xref:System.Windows.Window>クラス。</span><span class="sxs-lookup"><span data-stu-id="f519d-105">Standalone [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications provide their own windows by using the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="f519d-106">このトピックでは<xref:System.Windows.Window>を作成して、スタンドアロン アプリケーションで windows の管理の基礎を紹介します。</span><span class="sxs-lookup"><span data-stu-id="f519d-106">This topic introduces <xref:System.Windows.Window> before covering the fundamentals of creating and managing windows in standalone applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-107">ブラウザーによってホストされる[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]など、アプリケーション[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]や loose[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ページは、独自のウィンドウを指定しません。</span><span class="sxs-lookup"><span data-stu-id="f519d-107">Browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pages, don't provide their own windows.</span></span> <span data-ttu-id="f519d-108">代わりに、によって提供されるウィンドウにホストされている[!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f519d-108">Instead, they are hosted in windows provided by [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)].</span></span> <span data-ttu-id="f519d-109">参照してください[WPF XAML ブラウザー アプリケーションの概要](wpf-xaml-browser-applications-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="f519d-109">See [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  

<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a><span data-ttu-id="f519d-110">ウィンドウ クラス</span><span class="sxs-lookup"><span data-stu-id="f519d-110">The Window Class</span></span>  
 <span data-ttu-id="f519d-111">次の図は、ウィンドウの構成要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="f519d-111">The following figure illustrates the constituent parts of a window:</span></span>  
  
 ![ウィンドウ要素を示すスクリーン ショット。](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 <span data-ttu-id="f519d-113">ウィンドウは、非クライアント領域とクライアント領域の 2 つに分かれます。</span><span class="sxs-lookup"><span data-stu-id="f519d-113">A window is divided into two areas: the non-client area and client area.</span></span>  
  
 <span data-ttu-id="f519d-114">*非クライアント領域*によって実装されるウィンドウの[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]次を含む、ほとんどの windows に共通のウィンドウの部分が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f519d-114">The *non-client area* of a window is implemented by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and includes the parts of a window that are common to most windows, including the following:</span></span>  
  
-   <span data-ttu-id="f519d-115">境界線。</span><span class="sxs-lookup"><span data-stu-id="f519d-115">A border.</span></span>  
  
-   <span data-ttu-id="f519d-116">タイトル バー。</span><span class="sxs-lookup"><span data-stu-id="f519d-116">A title bar.</span></span>  
  
-   <span data-ttu-id="f519d-117">アイコン。</span><span class="sxs-lookup"><span data-stu-id="f519d-117">An icon.</span></span>  
  
-   <span data-ttu-id="f519d-118">最小化ボタン、最大化ボタン、および元に戻すボタン。</span><span class="sxs-lookup"><span data-stu-id="f519d-118">Minimize, Maximize, and Restore buttons.</span></span>  
  
-   <span data-ttu-id="f519d-119">閉じるボタン。</span><span class="sxs-lookup"><span data-stu-id="f519d-119">A Close button.</span></span>  
  
-   <span data-ttu-id="f519d-120">ウィンドウを最小化、最大化、元のサイズに戻す、移動、サイズ変更、および閉じるためのメニュー項目を含むシステム メニュー。</span><span class="sxs-lookup"><span data-stu-id="f519d-120">A System menu with menu items that allow users to minimize, maximize, restore, move, resize, and close a window.</span></span>  
  
 <span data-ttu-id="f519d-121">*クライアント領域*ウィンドウがウィンドウの非クライアント領域内の領域と、メニュー バー、ツールバー、およびコントロールなどのアプリケーション固有のコンテンツを追加する開発者によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-121">The *client area* of a window is the area within a window's non-client area and is used by developers to add application-specific content, such as menu bars, tool bars, and controls.</span></span>  
  
 <span data-ttu-id="f519d-122">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]、ウィンドウがカプセル化、<xref:System.Windows.Window>次の操作に使用するクラスです。</span><span class="sxs-lookup"><span data-stu-id="f519d-122">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], a window is encapsulated by the <xref:System.Windows.Window> class that you use to do the following:</span></span>  
  
-   <span data-ttu-id="f519d-123">ウィンドウを表示する。</span><span class="sxs-lookup"><span data-stu-id="f519d-123">Display a window.</span></span>  
  
-   <span data-ttu-id="f519d-124">ウィンドウのサイズ、位置、および外観を構成する。</span><span class="sxs-lookup"><span data-stu-id="f519d-124">Configure the size, position, and appearance of a window.</span></span>  
  
-   <span data-ttu-id="f519d-125">アプリケーション固有のコンテンツをホストする。</span><span class="sxs-lookup"><span data-stu-id="f519d-125">Host application-specific content.</span></span>  
  
-   <span data-ttu-id="f519d-126">ウィンドウの有効期間を管理する。</span><span class="sxs-lookup"><span data-stu-id="f519d-126">Manage the lifetime of a window.</span></span>  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a><span data-ttu-id="f519d-127">ウィンドウの実装</span><span class="sxs-lookup"><span data-stu-id="f519d-127">Implementing a Window</span></span>  
 <span data-ttu-id="f519d-128">一般的なウィンドウの実装は、外観と動作を構成、*外観*ユーザーに、ウィンドウの外観を定義および*動作*ユーザーが操作ウィンドウの機能方法を定義しますられています。</span><span class="sxs-lookup"><span data-stu-id="f519d-128">The implementation of a typical window comprises both appearance and behavior, where *appearance* defines how a window looks to users and *behavior* defines the way a window functions as users interact with it.</span></span> <span data-ttu-id="f519d-129">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]外観を実装して、コーディングするかを使用してウィンドウの動作、または[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ。</span><span class="sxs-lookup"><span data-stu-id="f519d-129">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], you can implement the appearance and behavior of a window using either code or [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 <span data-ttu-id="f519d-130">一般に、ただし、ウィンドウの外観を使用して実装[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ、およびその動作の実装コード ビハインドを使用して次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="f519d-130">In general, however, the appearance of a window is implemented using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and its behavior is implemented using code-behind, as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 <span data-ttu-id="f519d-131">有効にする、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ ファイルと分離コード ファイルを連携では、次が必要です。</span><span class="sxs-lookup"><span data-stu-id="f519d-131">To enable a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup file and code-behind file to work together, the following are required:</span></span>  
  
-   <span data-ttu-id="f519d-132">マークアップでは、`Window`要素を含める必要があります、`x:Class`属性。</span><span class="sxs-lookup"><span data-stu-id="f519d-132">In markup, the `Window` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="f519d-133">ときに、アプリケーションがビルドが存在する`x:Class`ファイルにより、マークアップで[!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)]を作成する、`partial`クラスから派生した<xref:System.Windows.Window>によって指定された名前を持つ、`x:Class`属性。</span><span class="sxs-lookup"><span data-stu-id="f519d-133">When the application is built, the existence of `x:Class` in the markup file causes [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] to create a `partial` class that derives from <xref:System.Windows.Window> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="f519d-134">追加する必要があります、[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]名前空間宣言、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]スキーマ ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` )。</span><span class="sxs-lookup"><span data-stu-id="f519d-134">This requires the addition of an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace declaration for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span></span> <span data-ttu-id="f519d-135">生成された`partial`クラスが実装する、`InitializeComponent`メソッドが呼び出され、イベントを登録し、マークアップで実装されているプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f519d-135">The generated `partial` class implements the `InitializeComponent` method, which is called to register the events and set the properties that are implemented in markup.</span></span>  
  
-   <span data-ttu-id="f519d-136">分離コード クラスがある必要があります、`partial`によって指定される同じ名前のクラス、`x:Class`のマークアップ、およびその属性がから派生する必要があります<xref:System.Windows.Window>します。</span><span class="sxs-lookup"><span data-stu-id="f519d-136">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Window>.</span></span> <span data-ttu-id="f519d-137">これにより、分離コード ファイルに関連付けられる、`partial`アプリケーションのビルド時にマークアップ ファイル用に生成されたクラス (を参照してください[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md))。</span><span class="sxs-lookup"><span data-stu-id="f519d-137">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>  
  
-   <span data-ttu-id="f519d-138">分離コードで、<xref:System.Windows.Window>クラスを呼び出すコンス トラクターを実装する必要があります、`InitializeComponent`メソッド。</span><span class="sxs-lookup"><span data-stu-id="f519d-138">In code-behind, the <xref:System.Windows.Window> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="f519d-139">`InitializeComponent` 実装ファイルの生成されたマークアップによって`partial`イベントを登録し、マークアップで定義されているプロパティを設定するクラス。</span><span class="sxs-lookup"><span data-stu-id="f519d-139">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-140">新しいを追加すると<xref:System.Windows.Window>を使用して、プロジェクトに[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]、<xref:System.Windows.Window>マークアップと分離コードの両方を使用して実装され、としてマークアップと分離コード ファイル間の関連付けを作成するために必要な構成が含まれていますここで説明します。</span><span class="sxs-lookup"><span data-stu-id="f519d-140">When you add a new <xref:System.Windows.Window> to your project by using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], the <xref:System.Windows.Window> is implemented using both markup and code-behind, and includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>  
  
 <span data-ttu-id="f519d-141">この構成で、ウィンドウの外観を定義に集中できます[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップと分離コードでその動作を実装します。</span><span class="sxs-lookup"><span data-stu-id="f519d-141">With this configuration in place, you can focus on defining the appearance of the window in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and implementing its behavior in code-behind.</span></span> <span data-ttu-id="f519d-142">次の例では、実装で、ボタンを使用してウィンドウを[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ、およびボタンのイベント ハンドラー<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント、分離コードで実装します。</span><span class="sxs-lookup"><span data-stu-id="f519d-142">The following example shows a window with a button, implemented in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, implemented in code-behind.</span></span>  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a><span data-ttu-id="f519d-143">MSBuild 用のウィンドウ定義の構成</span><span class="sxs-lookup"><span data-stu-id="f519d-143">Configuring a Window Definition for MSBuild</span></span>  
 <span data-ttu-id="f519d-144">ウィンドウを実装する方法の構成方法を決定[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f519d-144">How you implement your window determines how it is configured for [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)].</span></span> <span data-ttu-id="f519d-145">両方を使用して定義されているウィンドウの[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップと分離コード。</span><span class="sxs-lookup"><span data-stu-id="f519d-145">For a window that is defined using both [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind:</span></span>  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <span data-ttu-id="f519d-146">マークアップ ファイルとして構成されている[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page`項目。</span><span class="sxs-lookup"><span data-stu-id="f519d-146">markup files are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Page` items.</span></span>  
  
-   <span data-ttu-id="f519d-147">分離コード ファイルとして構成されている[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Compile`項目。</span><span class="sxs-lookup"><span data-stu-id="f519d-147">Code-behind files are configured as [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]`Compile` items.</span></span>  
  
 <span data-ttu-id="f519d-148">これは、次に示すように、[!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]プロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="f519d-148">This is shown in the following [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] project file.</span></span>  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 <span data-ttu-id="f519d-149">ビルドについて[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]アプリケーションを参照してください[WPF アプリケーションのビルド](building-a-wpf-application-wpf.md)します。</span><span class="sxs-lookup"><span data-stu-id="f519d-149">For information about building [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a><span data-ttu-id="f519d-150">ウィンドウの有効期間</span><span class="sxs-lookup"><span data-stu-id="f519d-150">Window Lifetime</span></span>  
 <span data-ttu-id="f519d-151">クラスと同様に、ウィンドウにも有効期間があります。有効期間は、ウィンドウが開いて最初にインスタンス化されたときに開始し、アクティブ化と非アクティブ化を経て、最後に閉じられるまで継続します。</span><span class="sxs-lookup"><span data-stu-id="f519d-151">As with any class, a window has a lifetime that begins when it is first instantiated, after which it is opened, activated and deactivated, and eventually closed.</span></span>  

<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a><span data-ttu-id="f519d-152">ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="f519d-152">Opening a Window</span></span>  
 <span data-ttu-id="f519d-153">ウィンドウを開くには、次の例に示すように最初にインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f519d-153">To open a window, you first create an instance of it, which is demonstrated in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 <span data-ttu-id="f519d-154">この例で、 `MarkupAndCodeBehindWindow` 、アプリケーションの起動時に発生するときにインスタンス化されるときに、<xref:System.Windows.Application.Startup>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-154">In this example, the `MarkupAndCodeBehindWindow` is instantiated when the application starts, which occurs when the <xref:System.Windows.Application.Startup> event is raised.</span></span>  
  
 <span data-ttu-id="f519d-155">参照が自動的に追加で管理されている windows の一覧に、ウィンドウがインスタンス化されるとき、<xref:System.Windows.Application>オブジェクト (を参照してください<xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="f519d-155">When a window is instantiated, a reference to it is automatically added to a list of windows that is managed by the <xref:System.Windows.Application> object (see <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="f519d-156">さらに、インスタンス化する最初のウィンドウは、既定では、設定<xref:System.Windows.Application>メイン アプリケーション ウィンドウとして (を参照してください<xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="f519d-156">Additionally, the first window to be instantiated is, by default, set by <xref:System.Windows.Application> as the main application window (see <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="f519d-157">呼び出すことによって、ウィンドウが開かれた最後に、<xref:System.Windows.Window.Show%2A>メソッドは、結果は次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="f519d-157">The window is finally opened by calling the <xref:System.Windows.Window.Show%2A> method; the result is shown in the following figure.</span></span>  
  
 ![Window.Show の呼び出しによって開いたウィンドウ](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 <span data-ttu-id="f519d-159">呼び出すことによって開かれたウィンドウ<xref:System.Windows.Window.Show%2A>はモードレス ウィンドウは、アプリケーションは、同じアプリケーションの他のウィンドウをアクティブ化できるモードで動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="f519d-159">A window that is opened by calling <xref:System.Windows.Window.Show%2A> is a modeless window, which means that the application operates in a mode that allows users to activate other windows in the same application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-160"><xref:System.Windows.Window.ShowDialog%2A> ダイアログ ボックスなどの windows をモーダルとして開くには呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-160"><xref:System.Windows.Window.ShowDialog%2A> is called to open windows such as dialog boxes modally.</span></span> <span data-ttu-id="f519d-161">参照してください[ダイアログ ボックスの概要](dialog-boxes-overview.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="f519d-161">See [Dialog Boxes Overview](dialog-boxes-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="f519d-162">ときに<xref:System.Windows.Window.Show%2A>が呼び出されると、ウィンドウの初期化作業をする前に実行をユーザー入力を受け取ることのできるインフラストラクチャを確立するために表示されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-162">When <xref:System.Windows.Window.Show%2A> is called, a window performs initialization work before it is shown to establish infrastructure that allows it to receive user input.</span></span> <span data-ttu-id="f519d-163">ウィンドウが初期化されるときに、<xref:System.Windows.Window.SourceInitialized>イベントが発生し、ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-163">When the window is initialized, the <xref:System.Windows.Window.SourceInitialized> event is raised and the window is shown.</span></span>  
  
 <span data-ttu-id="f519d-164">簡単な方法として<xref:System.Windows.Application.StartupUri%2A>アプリケーションの起動時に自動的に開かれている最初のウィンドウの指定に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="f519d-164">As a shortcut, <xref:System.Windows.Application.StartupUri%2A> can be set to specify the first window that is opened automatically when an application starts.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 <span data-ttu-id="f519d-165">アプリケーションの起動時の値で指定されたウィンドウ<xref:System.Windows.Application.StartupUri%2A>が開かれるウィンドウを呼び出すことによって開くモードレスでは内部的には、その<xref:System.Windows.Window.Show%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f519d-165">When the application starts, the window specified by the value of <xref:System.Windows.Application.StartupUri%2A> is opened modelessly; internally, the window is opened by calling its <xref:System.Windows.Window.Show%2A> method.</span></span>  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a><span data-ttu-id="f519d-166">ウィンドウの所有権</span><span class="sxs-lookup"><span data-stu-id="f519d-166">Window Ownership</span></span>  
 <span data-ttu-id="f519d-167">使用して開かれるウィンドウ、<xref:System.Windows.Window.Show%2A>メソッドには、暗黙的なリレーションシップを作成したウィンドウではありません。 ユーザーのいずれかのウィンドウが、次を実行できますが、いずれかのウィンドウとは無関係に、その他の対話。</span><span class="sxs-lookup"><span data-stu-id="f519d-167">A window that is opened by using the <xref:System.Windows.Window.Show%2A> method does not have an implicit relationship with the window that created it; users can interact with either window independently of the other, which means that either window can do the following:</span></span>  
  
-   <span data-ttu-id="f519d-168">一方 (、windows のいずれかの場合を除いて、その<xref:System.Windows.Window.Topmost%2A>プロパティに設定`true`)。</span><span class="sxs-lookup"><span data-stu-id="f519d-168">Cover the other (unless one of the windows has its <xref:System.Windows.Window.Topmost%2A> property set to `true`).</span></span>  
  
-   <span data-ttu-id="f519d-169">もう一方のウィンドウに影響を与えずに、最小化/最大化し、元のサイズに戻す。</span><span class="sxs-lookup"><span data-stu-id="f519d-169">Be minimized, maximized, and restored without affecting the other.</span></span>  
  
 <span data-ttu-id="f519d-170">一部のウィンドウには、そのウィンドウを開いたウィンドウとの関係が必要です。</span><span class="sxs-lookup"><span data-stu-id="f519d-170">Some windows require a relationship with the window that opens them.</span></span> <span data-ttu-id="f519d-171">たとえば、[!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)]アプリケーションは、プロパティ ウィンドウやツール ウィンドウが一般的な動作では、作成ウィンドウを開く場合があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-171">For example, an [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] application may open property windows and tool windows whose typical behavior is to cover the window that creates them.</span></span> <span data-ttu-id="f519d-172">また、そのようなウィンドウは、必ず作成元のウィンドウと一緒に閉じ、最小化/最大化し、元のサイズに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-172">Furthermore, such windows should always close, minimize, maximize, and restore in concert with the window that created them.</span></span> <span data-ttu-id="f519d-173">このようなリレーションシップは 1 つのウィンドウを確立することができます*独自*別、設定に達すると、<xref:System.Windows.Window.Owner%2A>のプロパティ、*所有されているウィンドウ*への参照、*所有者ウィンドウ*します。</span><span class="sxs-lookup"><span data-stu-id="f519d-173">Such a relationship can be established by making one window *own* another, and is achieved by setting the <xref:System.Windows.Window.Owner%2A> property of the *owned window* with a reference to the *owner window*.</span></span> <span data-ttu-id="f519d-174">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="f519d-174">This is shown in the following example.</span></span>  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 <span data-ttu-id="f519d-175">所有権が確立されると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f519d-175">After ownership is established:</span></span>  
  
-   <span data-ttu-id="f519d-176">所有されているウィンドウの値を調べることによって、オーナー ウィンドウを参照できる、<xref:System.Windows.Window.Owner%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f519d-176">The owned window can reference its owner window by inspecting the value of its <xref:System.Windows.Window.Owner%2A> property.</span></span>  
  
-   <span data-ttu-id="f519d-177">オーナー ウィンドウの値を調べることによって、所有するすべての windows を検出できるその<xref:System.Windows.Window.OwnedWindows%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f519d-177">The owner window can discover all the windows it owns by inspecting the value of its <xref:System.Windows.Window.OwnedWindows%2A> property.</span></span>  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a><span data-ttu-id="f519d-178">ウィンドウのアクティブ化の防止</span><span class="sxs-lookup"><span data-stu-id="f519d-178">Preventing Window Activation</span></span>  
 <span data-ttu-id="f519d-179">Windows アクティブにしないインターネット メッセンジャー スタイルのアプリケーションの対話ウィンドウや、電子メール アプリケーションの通知ウィンドウなど、表示するときにシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="f519d-179">There are scenarios where windows should not be activated when shown, such as conversation windows of an Internet messenger-style application or notification windows of an email application.</span></span>  
  
 <span data-ttu-id="f519d-180">設定することがウィンドウに表示するときにアクティブにすることはできませんが、アプリケーションの場合は、その<xref:System.Windows.Window.ShowActivated%2A>プロパティを`false`呼び出す前に、<xref:System.Windows.Window.Show%2A>初めてメソッド。</span><span class="sxs-lookup"><span data-stu-id="f519d-180">If your application has a window that shouldn't be activated when shown, you can set its <xref:System.Windows.Window.ShowActivated%2A> property to `false` before calling the <xref:System.Windows.Window.Show%2A> method for the first time.</span></span> <span data-ttu-id="f519d-181">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f519d-181">As a consequence:</span></span>  
  
-   <span data-ttu-id="f519d-182">ウィンドウはアクティブになりません。</span><span class="sxs-lookup"><span data-stu-id="f519d-182">The window is not activated.</span></span>  
  
-   <span data-ttu-id="f519d-183">ウィンドウの<xref:System.Windows.Window.Activated>イベントは発生しません。</span><span class="sxs-lookup"><span data-stu-id="f519d-183">The window's <xref:System.Windows.Window.Activated> event is not raised.</span></span>  
  
-   <span data-ttu-id="f519d-184">現在アクティブなウィンドウは、アクティブのままです。</span><span class="sxs-lookup"><span data-stu-id="f519d-184">The currently activated window remains activated.</span></span>  
  
 <span data-ttu-id="f519d-185">ただし、ユーザーがクライアント領域または非クライアント領域をクリックすると、ウィンドウは直ちにアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="f519d-185">The window will become activated, however, as soon as the user activates it by clicking either the client or non-client area.</span></span> <span data-ttu-id="f519d-186">この場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f519d-186">In this case:</span></span>  
  
-   <span data-ttu-id="f519d-187">ウィンドウはアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="f519d-187">The window is activated.</span></span>  
  
-   <span data-ttu-id="f519d-188">ウィンドウの<xref:System.Windows.Window.Activated>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-188">The window's <xref:System.Windows.Window.Activated> event is raised.</span></span>  
  
-   <span data-ttu-id="f519d-189">直前にアクティブだったウィンドウは非アクティブになります。</span><span class="sxs-lookup"><span data-stu-id="f519d-189">The previously activated window is deactivated.</span></span>  
  
-   <span data-ttu-id="f519d-190">ウィンドウの<xref:System.Windows.Window.Deactivated>と<xref:System.Windows.Window.Activated>ユーザー アクションに対する応答として、その後イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-190">The window's <xref:System.Windows.Window.Deactivated> and <xref:System.Windows.Window.Activated> events are subsequently raised as expected in response to user actions.</span></span>  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a><span data-ttu-id="f519d-191">ウィンドウのアクティブ化</span><span class="sxs-lookup"><span data-stu-id="f519d-191">Window Activation</span></span>  
 <span data-ttu-id="f519d-192">アクティブなウィンドウがウィンドウを最初に開いたとき (表示される場合を除き、<xref:System.Windows.Window.ShowActivated%2A>設定`false`)。</span><span class="sxs-lookup"><span data-stu-id="f519d-192">When a window is first opened, it becomes the active window (unless it is shown with <xref:System.Windows.Window.ShowActivated%2A> set to `false`).</span></span> <span data-ttu-id="f519d-193">*アクティブなウィンドウ*は現在キー ストロークやマウス クリックなどのユーザー入力をキャプチャしているウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="f519d-193">The *active window* is the window that is currently capturing user input, such as key strokes and mouse clicks.</span></span> <span data-ttu-id="f519d-194">ウィンドウがアクティブになったときに発生、<xref:System.Windows.Window.Activated>イベント。</span><span class="sxs-lookup"><span data-stu-id="f519d-194">When a window becomes active, it raises the <xref:System.Windows.Window.Activated> event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-195">最初に、ウィンドウを開いたとき、<xref:System.Windows.FrameworkElement.Loaded>と<xref:System.Windows.Window.ContentRendered>イベントが発生した後のみ、<xref:System.Windows.Window.Activated>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-195">When a window is first opened, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.Window.ContentRendered> events are raised only after the <xref:System.Windows.Window.Activated> event is raised.</span></span> <span data-ttu-id="f519d-196">これを踏まえて、ウィンドウを見なすことができる効果的にとき開く<xref:System.Windows.Window.ContentRendered>が発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-196">With this in mind, a window can effectively be considered opened when <xref:System.Windows.Window.ContentRendered> is raised.</span></span>  
  
 <span data-ttu-id="f519d-197">ウィンドウがアクティブになった後で、ユーザーは同じアプリケーションの別のウィンドウをアクティブ化したり、別のアプリケーションをアクティブ化したりできます。</span><span class="sxs-lookup"><span data-stu-id="f519d-197">After a window becomes active, a user can activate another window in the same application, or activate another application.</span></span> <span data-ttu-id="f519d-198">そのような場合は、現在アクティブなウィンドウが非アクティブ化させ、<xref:System.Windows.Window.Deactivated>イベント。</span><span class="sxs-lookup"><span data-stu-id="f519d-198">When that happens, the currently active window becomes deactivated and raises the <xref:System.Windows.Window.Deactivated> event.</span></span> <span data-ttu-id="f519d-199">同様に、ユーザーは、現在非アクティブ化されたウィンドウを選択するときに、ウィンドウが再びアクティブと<xref:System.Windows.Window.Activated>が発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-199">Likewise, when the user selects a currently deactivated window, the window becomes active again and <xref:System.Windows.Window.Activated> is raised.</span></span>  
  
 <span data-ttu-id="f519d-200">処理するために一般的な理由の 1 つ<xref:System.Windows.Window.Activated>と<xref:System.Windows.Window.Deactivated>を有効にし、ウィンドウがアクティブなときにのみ実行できる機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f519d-200">One common reason to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> is to enable and disable functionality that can only run when a window is active.</span></span> <span data-ttu-id="f519d-201">たとえば、ゲームやビデオ プレーヤーなど、ユーザーの一定の入力や介入が必要な対話型コンテンツが表示されるウィンドウがあります。</span><span class="sxs-lookup"><span data-stu-id="f519d-201">For example, some windows display interactive content that requires constant user input or attention, including games and video players.</span></span> <span data-ttu-id="f519d-202">次の例は、処理する方法を示す簡単なビデオ プレーヤー<xref:System.Windows.Window.Activated>と<xref:System.Windows.Window.Deactivated>この動作を実装します。</span><span class="sxs-lookup"><span data-stu-id="f519d-202">The following example is a simplified video player that demonstrates how to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> to implement this behavior.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 <span data-ttu-id="f519d-203">ウィンドウが非アクティブでも、バックグラウンドでコードを実行できる種類のアプリケーションもあります。</span><span class="sxs-lookup"><span data-stu-id="f519d-203">Other types of applications may still run code in the background when a window is deactivated.</span></span> <span data-ttu-id="f519d-204">たとえば、メール クライアントは、ユーザーが他のアプリケーションを使用している間もメール サーバーへのポーリングを続けています。</span><span class="sxs-lookup"><span data-stu-id="f519d-204">For example, a mail client may continue polling the mail server while the user is using other applications.</span></span> <span data-ttu-id="f519d-205">このようなアプリケーションは、メイン ウィンドウが非アクティブのときにも、別の動作や追加の動作を頻繁に実行します。</span><span class="sxs-lookup"><span data-stu-id="f519d-205">Applications like these often provide different or additional behavior while the main window is deactivated.</span></span> <span data-ttu-id="f519d-206">メール プログラムでは、新しいメール アイテムを受信トレイに追加し、通知アイコンをシステム トレイに追加することがあります。</span><span class="sxs-lookup"><span data-stu-id="f519d-206">With respect to the mail program, this may mean both adding the new mail item to the inbox and adding a notification icon to the system tray.</span></span> <span data-ttu-id="f519d-207">通知アイコンは、メール ウィンドウがアクティブで、調べることで確認できる場合にのみ表示必要があります、<xref:System.Windows.Window.IsActive%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f519d-207">A notification icon need only be displayed when the mail window isn't active, which can be determined by inspecting the <xref:System.Windows.Window.IsActive%2A> property.</span></span>  
  
 <span data-ttu-id="f519d-208">バック グラウンド タスクが完了したら場合、ウィンドウをすることが呼び出すことによってユーザーに通知する緊急<xref:System.Windows.Window.Activate%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f519d-208">If a background task completes, a window may want to notify the user more urgently by calling <xref:System.Windows.Window.Activate%2A> method.</span></span> <span data-ttu-id="f519d-209">別のアプリケーションが、ときにアクティブ化される場合は、ユーザーが対話<xref:System.Windows.Window.Activate%2A>が呼び出されると、ウィンドウのタスク バー ボタンが点滅します。</span><span class="sxs-lookup"><span data-stu-id="f519d-209">If the user is interacting with another application activated when <xref:System.Windows.Window.Activate%2A> is called, the window's taskbar button flashes.</span></span> <span data-ttu-id="f519d-210">呼び出して、ユーザーは、現在のアプリケーションと対話して場合、<xref:System.Windows.Window.Activate%2A>フォア グラウンドにウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-210">If a user is interacting with the current application, calling <xref:System.Windows.Window.Activate%2A> will bring the window to the foreground.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-211">アプリケーション スコープのアクティブ化を使用して処理することができます、<xref:System.Windows.Application.Activated?displayProperty=nameWithType>と<xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>イベント。</span><span class="sxs-lookup"><span data-stu-id="f519d-211">You can handle application-scope activation using the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> and <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> events.</span></span>  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a><span data-ttu-id="f519d-212">ウィンドウを閉じる</span><span class="sxs-lookup"><span data-stu-id="f519d-212">Closing a Window</span></span>  
 <span data-ttu-id="f519d-213">ウィンドウの有効期間は、表示されたときに開始し、ユーザーが閉じたときに終了します。</span><span class="sxs-lookup"><span data-stu-id="f519d-213">The life of a window starts coming to an end when a user closes it.</span></span> <span data-ttu-id="f519d-214">ウィンドウを閉じるには、非クライアント領域の要素を使用します。これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f519d-214">A window can be closed by using elements in the non-client area, including the following:</span></span>  
  
-   <span data-ttu-id="f519d-215">**閉じる**の項目、**システム**メニュー。</span><span class="sxs-lookup"><span data-stu-id="f519d-215">The **Close** item of the **System** menu.</span></span>  
  
-   <span data-ttu-id="f519d-216">Alt キーを押しながら F4 キーを押す。</span><span class="sxs-lookup"><span data-stu-id="f519d-216">Pressing ALT+F4.</span></span>  
  
-   <span data-ttu-id="f519d-217">キーを押して、**閉じる**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f519d-217">Pressing the **Close** button.</span></span>  
  
 <span data-ttu-id="f519d-218">クライアント領域にさらに機構を追加してウィンドウを閉じることもできます。その一般的な例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="f519d-218">You can provide additional mechanisms to the client area to close a window, the more common of which include the following:</span></span>  
  
-   <span data-ttu-id="f519d-219">**終了**内の項目、**ファイル**メイン アプリケーション ウィンドウの通常のメニュー。</span><span class="sxs-lookup"><span data-stu-id="f519d-219">An **Exit** item in the **File** menu, typically for main application windows.</span></span>  
  
-   <span data-ttu-id="f519d-220">A**閉じる**内の項目、**ファイル**一般に、セカンダリ アプリケーション ウィンドウのメニュー。</span><span class="sxs-lookup"><span data-stu-id="f519d-220">A **Close** item in the **File** menu, typically on a secondary application window.</span></span>  
  
-   <span data-ttu-id="f519d-221">A**キャンセル**一般にモーダル ダイアログ ボックス、ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f519d-221">A **Cancel** button, typically on a modal dialog box.</span></span>  
  
-   <span data-ttu-id="f519d-222">A**閉じる**一般にモードレス ダイアログ ボックス、ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f519d-222">A **Close** button, typically on a modeless dialog box.</span></span>  
  
 <span data-ttu-id="f519d-223">これらのカスタム機構のいずれかに対応したウィンドウを閉じるを呼び出す必要があります、<xref:System.Windows.Window.Close%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f519d-223">To close a window in response to one of these custom mechanisms, you need to call the <xref:System.Windows.Window.Close%2A> method.</span></span> <span data-ttu-id="f519d-224">次の例を選択してウィンドウを閉じる機能を実装する、**終了**上、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="f519d-224">The following example implements the ability to close a window by choosing the **Exit** on the **File** menu.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 <span data-ttu-id="f519d-225">ウィンドウを閉じるときに、2 つのイベントを発生させます。:<xref:System.Windows.Window.Closing>と<xref:System.Windows.Window.Closed>します。</span><span class="sxs-lookup"><span data-stu-id="f519d-225">When a window closes, it raises two events: <xref:System.Windows.Window.Closing> and <xref:System.Windows.Window.Closed>.</span></span>  
  
 <span data-ttu-id="f519d-226"><xref:System.Windows.Window.Closing> ウィンドウが閉じ、およびどのウィンドウによってクロージャを回避できるメカニズムを提供する前に発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-226"><xref:System.Windows.Window.Closing> is raised before the window closes, and it provides a mechanism by which window closure can be prevented.</span></span> <span data-ttu-id="f519d-227">ウィンドウが閉じるのを防ぐのは、一般的に、ウィンドウ コンテンツに変更したデータが含まれている場合です。</span><span class="sxs-lookup"><span data-stu-id="f519d-227">One common reason to prevent window closure is if window content contains modified data.</span></span> <span data-ttu-id="f519d-228">このような状況で、<xref:System.Windows.Window.Closing>イベントを処理する場合は、ユーザーに、ウィンドウを閉じると、データを保存せずに続行するか、またはウィンドウを閉じるをキャンセルするかどうかを確認するため、およびデータがダーティかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f519d-228">In this situation, the <xref:System.Windows.Window.Closing> event can be handled to determine whether data is dirty and, if so, to ask the user whether to either continue closing the window without saving the data or to cancel window closure.</span></span> <span data-ttu-id="f519d-229">次の例は、処理の重要な側面を示しています。<xref:System.Windows.Window.Closing>します。</span><span class="sxs-lookup"><span data-stu-id="f519d-229">The following example shows the key aspects of handling <xref:System.Windows.Window.Closing>.</span></span>  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 <span data-ttu-id="f519d-230"><xref:System.Windows.Window.Closing>イベント ハンドラーに渡される、 <xref:System.ComponentModel.CancelEventArgs>、実装、 `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>プロパティを設定した`true`が閉じないようにするのにします。</span><span class="sxs-lookup"><span data-stu-id="f519d-230">The <xref:System.Windows.Window.Closing> event handler is passed a <xref:System.ComponentModel.CancelEventArgs>, which implements the `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property that you set to `true` to prevent a window from closing.</span></span>  
  
 <span data-ttu-id="f519d-231">場合<xref:System.Windows.Window.Closing>が処理されないとウィンドウが閉じるか、処理しますが、取り消されないことができます。</span><span class="sxs-lookup"><span data-stu-id="f519d-231">If <xref:System.Windows.Window.Closing> is not handled, or it is handled but not canceled, the window will close.</span></span> <span data-ttu-id="f519d-232">ウィンドウが実際に閉じられる直前に<xref:System.Windows.Window.Closed>が発生します。</span><span class="sxs-lookup"><span data-stu-id="f519d-232">Just before a window actually closes, <xref:System.Windows.Window.Closed> is raised.</span></span> <span data-ttu-id="f519d-233">この時点で、ウィンドウが閉じるのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="f519d-233">At this point, a window cannot be prevented from closing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-234">アプリケーションを構成して、アプリケーションのメイン ウィンドウが閉じるときに自動的をシャット ダウン (を参照してください<xref:System.Windows.Application.MainWindow%2A>) または最後のウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f519d-234">An application can be configured to shut down automatically when either the main application window closes (see <xref:System.Windows.Application.MainWindow%2A>) or the last window closes.</span></span> <span data-ttu-id="f519d-235">詳細については、「<xref:System.Windows.Application.ShutdownMode%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f519d-235">For details, see <xref:System.Windows.Application.ShutdownMode%2A>.</span></span>  
  
 <span data-ttu-id="f519d-236">ウィンドウは、非クライアントおよびクライアント領域で提供される機構によって明示的に閉じることが、中にウィンドウを終了することも暗黙的に、アプリケーションの他の部分での動作の結果として、または[!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]次を含みます。</span><span class="sxs-lookup"><span data-stu-id="f519d-236">While a window can be explicitly closed through mechanisms provided in the non-client and client areas, a window can also be implicitly closed as a result of behavior in other parts of the application or [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], including the following:</span></span>  
  
-   <span data-ttu-id="f519d-237">ユーザーはログオフまたはシャット ダウン Windows。</span><span class="sxs-lookup"><span data-stu-id="f519d-237">A user logs off or shuts down Windows.</span></span>  
  
-   <span data-ttu-id="f519d-238">ウィンドウのオーナーが閉じた場合 (を参照してください<xref:System.Windows.Window.Owner%2A>)。</span><span class="sxs-lookup"><span data-stu-id="f519d-238">A window's owner closes (see <xref:System.Windows.Window.Owner%2A>).</span></span>  
  
-   <span data-ttu-id="f519d-239">アプリケーションのメイン ウィンドウが閉じられると<xref:System.Windows.Application.ShutdownMode%2A>は<xref:System.Windows.ShutdownMode.OnMainWindowClose>します。</span><span class="sxs-lookup"><span data-stu-id="f519d-239">The main application window is closed and <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>  
  
-   <span data-ttu-id="f519d-240"><xref:System.Windows.Application.Shutdown%2A> が呼ばれたとき。</span><span class="sxs-lookup"><span data-stu-id="f519d-240"><xref:System.Windows.Application.Shutdown%2A> is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-241">ウィンドウを閉じると、再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="f519d-241">A window cannot be reopened after it is closed.</span></span>  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a><span data-ttu-id="f519d-242">ウィンドウの有効期間イベント</span><span class="sxs-lookup"><span data-stu-id="f519d-242">Window Lifetime Events</span></span>  
 <span data-ttu-id="f519d-243">次の図は、ウィンドウの有効期間に主要なイベントのシーケンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f519d-243">The following illustration shows the sequence of the principal events in the lifetime of a window:</span></span>  
  
 ![ウィンドウの有効期間中にイベントを示す図。](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 <span data-ttu-id="f519d-245">次の図は、ライセンス認証を行わずに表示されるウィンドウの有効期間の主要なイベントのシーケンスを示します (<xref:System.Windows.Window.ShowActivated%2A>に設定されている`false`ウィンドウが表示される前に)。</span><span class="sxs-lookup"><span data-stu-id="f519d-245">The following illustration shows the sequence of the principal events in the lifetime of a window that is shown without activation (<xref:System.Windows.Window.ShowActivated%2A> is set to `false` before the window is shown):</span></span>  
  
 ![ライセンス認証なしのウィンドウの有効期間でイベントを示す図。](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a><span data-ttu-id="f519d-247">ウィンドウの位置</span><span class="sxs-lookup"><span data-stu-id="f519d-247">Window Location</span></span>  
 <span data-ttu-id="f519d-248">ウィンドウが開いているとき、ウィンドウはデスクトップに対して相対的な x ディメンションと y ディメンションの位置にあります。</span><span class="sxs-lookup"><span data-stu-id="f519d-248">While a window is open, it has a location in the x and y dimensions relative to the desktop.</span></span> <span data-ttu-id="f519d-249">この場所を調べることで確認できる、<xref:System.Windows.Window.Left%2A>と<xref:System.Windows.Window.Top%2A>プロパティ、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="f519d-249">This location can be determined by inspecting the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties, respectively.</span></span> <span data-ttu-id="f519d-250">これらのプロパティを設定して、ウィンドウの位置を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f519d-250">You can set these properties to change the location of the window.</span></span>  
  
 <span data-ttu-id="f519d-251">最初の場所を指定することもできます、<xref:System.Windows.Window>ときに最初に表示される設定によって、<xref:System.Windows.Window.WindowStartupLocation%2A>プロパティは、次のいずれかで<xref:System.Windows.WindowStartupLocation>列挙値。</span><span class="sxs-lookup"><span data-stu-id="f519d-251">You can also specify the initial location of a <xref:System.Windows.Window> when it first appears by setting the <xref:System.Windows.Window.WindowStartupLocation%2A> property with one of the following <xref:System.Windows.WindowStartupLocation> enumeration values:</span></span>  
  
-   <span data-ttu-id="f519d-252"><xref:System.Windows.WindowStartupLocation.CenterOwner> (既定値)</span><span class="sxs-lookup"><span data-stu-id="f519d-252"><xref:System.Windows.WindowStartupLocation.CenterOwner> (default)</span></span>  
  
-   <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
-   <xref:System.Windows.WindowStartupLocation.Manual>  
  
 <span data-ttu-id="f519d-253">として、初期表示位置が指定されている場合<xref:System.Windows.WindowStartupLocation.Manual>、および<xref:System.Windows.Window.Left%2A>と<xref:System.Windows.Window.Top%2A>プロパティが設定されていない、<xref:System.Windows.Window>に表示される場所の Windows を求められます。</span><span class="sxs-lookup"><span data-stu-id="f519d-253">If the startup location is specified as <xref:System.Windows.WindowStartupLocation.Manual>, and the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties have not been set, <xref:System.Windows.Window> will ask Windows for a location to appear in.</span></span>  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a><span data-ttu-id="f519d-254">最上位ウィンドウと Z オーダー</span><span class="sxs-lookup"><span data-stu-id="f519d-254">Topmost Windows and Z-Order</span></span>  
 <span data-ttu-id="f519d-255">ウィンドウには、x 位置と y 位置に加えて、他のウィンドウを基準にして垂直位置を決定する z ディメンションの位置もあります。</span><span class="sxs-lookup"><span data-stu-id="f519d-255">Besides having an x and y location, a window also has a location in the z dimension, which determines its vertical position with respect to other windows.</span></span> <span data-ttu-id="f519d-256">これはウィンドウの z オーダーともいい、標準 z オーダーと最上位 z オーダーの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-256">This is known as the window's z-order, and there are two types: normal z-order and topmost z-order.</span></span> <span data-ttu-id="f519d-257">内のウィンドウの場所、*標準 z オーダー*が現在アクティブかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f519d-257">The location of a window in the *normal z-order* is determined by whether it is currently active or not.</span></span> <span data-ttu-id="f519d-258">既定では、ウィンドウは標準 z オーダーにあります。</span><span class="sxs-lookup"><span data-stu-id="f519d-258">By default, a window is located in the normal z-order.</span></span> <span data-ttu-id="f519d-259">内のウィンドウの場所、*最上位 z オーダー*が現在アクティブかどうかによっても決定されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-259">The location of a window in the *topmost z-order* is also determined by whether it is currently active or not.</span></span> <span data-ttu-id="f519d-260">また、最上位 z オーダーにあるウィンドウは、常に、標準 z オーダーにあるウィンドウの上に位置します。</span><span class="sxs-lookup"><span data-stu-id="f519d-260">Furthermore, windows in the topmost z-order are always located above windows in the normal z-order.</span></span> <span data-ttu-id="f519d-261">ウィンドウにある最上位 z オーダーを設定してその<xref:System.Windows.Window.Topmost%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="f519d-261">A window is located in the topmost z-order by setting its <xref:System.Windows.Window.Topmost%2A> property to `true`.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 <span data-ttu-id="f519d-262">各 z オーダー内では、現在アクティブなウィンドウは、同じ z オーダーにある他のすべてのウィンドウの上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-262">Within each z-order, the currently active window appears above all other windows in the same z-order.</span></span>  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a><span data-ttu-id="f519d-263">ウィンドウ サイズ</span><span class="sxs-lookup"><span data-stu-id="f519d-263">Window Size</span></span>  
 <span data-ttu-id="f519d-264">デスクトップか所だけでなく、ウィンドウにはさまざまな幅と高さのプロパティを含む、いくつかのプロパティによって決定されるサイズと<xref:System.Windows.Window.SizeToContent%2A>します。</span><span class="sxs-lookup"><span data-stu-id="f519d-264">Besides having a desktop location, a window has a size that is determined by several properties, including the various width and height properties and <xref:System.Windows.Window.SizeToContent%2A>.</span></span>  
  
 <span data-ttu-id="f519d-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>、 <xref:System.Windows.FrameworkElement.Width%2A>、および<xref:System.Windows.FrameworkElement.MaxWidth%2A>、ウィンドウの有効期間を持つことができ、、次の例に示すように構成される幅の範囲の管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.MaxWidth%2A> are used to manage the range of widths that a window can have during its lifetime, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 <span data-ttu-id="f519d-266">ウィンドウの高さは、によって管理される<xref:System.Windows.FrameworkElement.MinHeight%2A>、 <xref:System.Windows.FrameworkElement.Height%2A>、および<xref:System.Windows.FrameworkElement.MaxHeight%2A>の次の例に示すように構成します。</span><span class="sxs-lookup"><span data-stu-id="f519d-266">Window height is managed by <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 <span data-ttu-id="f519d-267">さまざまな幅の値と高さの値はそれぞれ範囲を指定しているため、サイズを変更できるウィンドウの幅と高さは、それぞれの寸法に指定された範囲内のいずれかの値を取ります。</span><span class="sxs-lookup"><span data-stu-id="f519d-267">Because the various width values and height values each specify a range, it is possible for the width and height of a resizable window to be anywhere within the specified range for the respective dimension.</span></span> <span data-ttu-id="f519d-268">現在の幅と高さを検出、<xref:System.Windows.FrameworkElement.ActualWidth%2A>と<xref:System.Windows.FrameworkElement.ActualHeight%2A>、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="f519d-268">To detect its current width and height, inspect <xref:System.Windows.FrameworkElement.ActualWidth%2A> and <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectively.</span></span>  
  
 <span data-ttu-id="f519d-269">ウィンドウのサイズに合わせたサイズのコンテンツ、ウィンドウの高さと幅が希望される場合は、使用することができます、<xref:System.Windows.Window.SizeToContent%2A>プロパティで、次の値があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-269">If you'd like the width and height of your window to have a size that fits to the size of the window's content, you can use the <xref:System.Windows.Window.SizeToContent%2A> property, which has the following values:</span></span>  
  
-   <span data-ttu-id="f519d-270"><xref:System.Windows.SizeToContent.Manual>.</span><span class="sxs-lookup"><span data-stu-id="f519d-270"><xref:System.Windows.SizeToContent.Manual>.</span></span> <span data-ttu-id="f519d-271">効果 (既定値)。</span><span class="sxs-lookup"><span data-stu-id="f519d-271">No effect (default).</span></span>  
  
-   <span data-ttu-id="f519d-272"><xref:System.Windows.SizeToContent.Width>.</span><span class="sxs-lookup"><span data-stu-id="f519d-272"><xref:System.Windows.SizeToContent.Width>.</span></span> <span data-ttu-id="f519d-273">両方の設定と同じ効果がありますが、コンテンツの幅に合わせる<xref:System.Windows.FrameworkElement.MinWidth%2A>と<xref:System.Windows.FrameworkElement.MaxWidth%2A>コンテンツの幅にします。</span><span class="sxs-lookup"><span data-stu-id="f519d-273">Fit to content width, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
-   <span data-ttu-id="f519d-274"><xref:System.Windows.SizeToContent.Height>.</span><span class="sxs-lookup"><span data-stu-id="f519d-274"><xref:System.Windows.SizeToContent.Height>.</span></span> <span data-ttu-id="f519d-275">コンテンツの高さは、両方の設定と同じ効果に合わせる<xref:System.Windows.FrameworkElement.MinHeight%2A>と<xref:System.Windows.FrameworkElement.MaxHeight%2A>コンテンツの高さにします。</span><span class="sxs-lookup"><span data-stu-id="f519d-275">Fit to content height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content.</span></span>  
  
-   <span data-ttu-id="f519d-276"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span><span class="sxs-lookup"><span data-stu-id="f519d-276"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span></span> <span data-ttu-id="f519d-277">コンテンツの幅と高さで、両方の設定と同じ効果<xref:System.Windows.FrameworkElement.MinHeight%2A>と<xref:System.Windows.FrameworkElement.MaxHeight%2A>、コンテンツと設定の両方の高さに<xref:System.Windows.FrameworkElement.MinWidth%2A>と<xref:System.Windows.FrameworkElement.MaxWidth%2A>コンテンツの幅にします。</span><span class="sxs-lookup"><span data-stu-id="f519d-277">Fit to content width and height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content, and setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
 <span data-ttu-id="f519d-278">次の例では、ウィンドウを最初に表示するときに、そのコンテンツに合わせて垂直方向と水平方向の両方のサイズを自動的に変更するウィンドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="f519d-278">The following example shows a window that automatically sizes to fit its content, both vertically and horizontally, when first shown.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 <span data-ttu-id="f519d-279">次の例は、設定する方法を示します、<xref:System.Windows.Window.SizeToContent%2A>コード ウィンドウのコンテンツに合わせてサイズ変更する方法を指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f519d-279">The following example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property in code to specify how a window resizes to fit its content    .</span></span>
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a><span data-ttu-id="f519d-280">サイズ変更プロパティの優先順位</span><span class="sxs-lookup"><span data-stu-id="f519d-280">Order of Precedence for Sizing Properties</span></span>  
 <span data-ttu-id="f519d-281">基本的に、ウィンドウのさまざまなサイズのプロパティを組み合わせて、サイズを変更できるウィンドウの幅と高さの範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="f519d-281">Essentially, the various sizes properties of a window combine to define the range of width and height for a resizable window.</span></span> <span data-ttu-id="f519d-282">有効な範囲を維持すること<xref:System.Windows.Window>優先順位の次の注文を使用して、サイズ プロパティの値を評価します。</span><span class="sxs-lookup"><span data-stu-id="f519d-282">To ensure a valid range is maintained, <xref:System.Windows.Window> evaluates the values of the size properties using the following orders of precedence.</span></span>  
  
 <span data-ttu-id="f519d-283">**高さのプロパティ:**</span><span class="sxs-lookup"><span data-stu-id="f519d-283">**For Height Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="f519d-284">**幅のプロパティ:**</span><span class="sxs-lookup"><span data-stu-id="f519d-284">**For Width Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="f519d-285">最大化されたで管理されているときに、優先順位の順序はウィンドウのサイズを決定もことができます、<xref:System.Windows.Window.WindowState%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f519d-285">The order of precedence can also determine the size of a window when it is maximized, which is managed with the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="WindowState"></a>   
## <a name="window-state"></a><span data-ttu-id="f519d-286">ウィンドウの状態</span><span class="sxs-lookup"><span data-stu-id="f519d-286">Window State</span></span>  
 <span data-ttu-id="f519d-287">サイズを変更できるウィンドウには、有効期間中、通常、最小化、最大化の 3 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-287">During the lifetime of a resizable window, it can have three states: normal, minimized, and maximized.</span></span> <span data-ttu-id="f519d-288">使用してウィンドウを*通常*状態は、ウィンドウの既定の状態。</span><span class="sxs-lookup"><span data-stu-id="f519d-288">A window with a *normal* state is the default state of a window.</span></span> <span data-ttu-id="f519d-289">この状態のウィンドウは、サイズ変更グリップ、またはサイズ変更可能な場合は境界線を使用して、ユーザーが移動したりサイズ変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="f519d-289">A window with this state allows a user to move and resize it by using a resize grip or the border, if it is resizable.</span></span>  
  
 <span data-ttu-id="f519d-290">使用してウィンドウを*を最小限に抑える*場合、タスク バー ボタンに状態が折りたたまれます<xref:System.Windows.Window.ShowInTaskbar%2A>に設定されている`true`、それ以外の折りたたまれて、最小の可能なサイズ、デスクトップの左下隅に自動的に再配置します。</span><span class="sxs-lookup"><span data-stu-id="f519d-290">A window with a *minimized* state collapses to its task bar button if <xref:System.Windows.Window.ShowInTaskbar%2A> is set to `true`; otherwise, it collapses to the smallest possible size it can be and relocates itself to the bottom-left corner of the desktop.</span></span> <span data-ttu-id="f519d-291">最小化されたウィンドウはいずれの種類も、境界線またはサイズ変更グリップを使用してサイズ変更できません。ただし、タスク バーに表示されていない最小化されたウィンドウはデスクトップの任意の場所にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="f519d-291">Neither type of minimized window can be resized using a border or resize grip, although a minimized window that isn't shown in the task bar can be dragged around the desktop.</span></span>  
  
 <span data-ttu-id="f519d-292">使用してウィンドウを*を最大化*状態が同じ大きさなることができます、最大サイズに拡大その<xref:System.Windows.FrameworkElement.MaxWidth%2A>、<xref:System.Windows.FrameworkElement.MaxHeight%2A>と<xref:System.Windows.Window.SizeToContent%2A>プロパティが指定します。</span><span class="sxs-lookup"><span data-stu-id="f519d-292">A window with a *maximized* state expands to the maximum size it can be, which will only be as large as its <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.Window.SizeToContent%2A> properties dictate.</span></span> <span data-ttu-id="f519d-293">最小化されたウィンドウと同様、最大化されたウィンドウは、サイズ変更グリップを使用したり、境界線をドラッグしたりすることによってサイズ変更できません。</span><span class="sxs-lookup"><span data-stu-id="f519d-293">Like a minimized window, a maximized window cannot be resized by using a resize grip or by dragging the border.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f519d-294">値、 <xref:System.Windows.Window.Top%2A>、 <xref:System.Windows.Window.Left%2A>、 <xref:System.Windows.FrameworkElement.Width%2A>、および<xref:System.Windows.FrameworkElement.Height%2A>ウィンドウのプロパティは、ウィンドウが現在最大化または最小限に抑える場合でも常に通常の状態の値を表します。</span><span class="sxs-lookup"><span data-stu-id="f519d-294">The values of the <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.Height%2A> properties of a window always represent the values for the normal state, even when the window is currently maximized or minimized.</span></span>  
  
 <span data-ttu-id="f519d-295">ウィンドウの状態を設定して構成できますその<xref:System.Windows.Window.WindowState%2A>プロパティで、次のいずれかの<xref:System.Windows.WindowState>列挙値。</span><span class="sxs-lookup"><span data-stu-id="f519d-295">The state of a window can be configured by setting its <xref:System.Windows.Window.WindowState%2A> property, which can have one of the following <xref:System.Windows.WindowState> enumeration values:</span></span>  
  
-   <span data-ttu-id="f519d-296"><xref:System.Windows.WindowState.Normal> (既定値)</span><span class="sxs-lookup"><span data-stu-id="f519d-296"><xref:System.Windows.WindowState.Normal> (default)</span></span>  
  
-   <xref:System.Windows.WindowState.Maximized>  
  
-   <xref:System.Windows.WindowState.Minimized>  
  
 <span data-ttu-id="f519d-297">開くときに最大化されて表示されるウィンドウを作成する方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="f519d-297">The following example shows how to create a window that is shown as maximized when it opens.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 <span data-ttu-id="f519d-298">一般に、設定する必要があります<xref:System.Windows.Window.WindowState%2A>ウィンドウの初期状態を構成します。</span><span class="sxs-lookup"><span data-stu-id="f519d-298">In general, you should set <xref:System.Windows.Window.WindowState%2A> to configure the initial state of a window.</span></span> <span data-ttu-id="f519d-299">サイズ変更可能なウィンドウが表示されると、ユーザーはウィンドウのタイトル バーにある最小化ボタン、最大化ボタン、および元に戻すボタンを使用して、ウィンドウの状態を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f519d-299">Once a resizable window is shown, users can press the minimize, maximize, and restore buttons on the window's title bar to change the window state.</span></span>  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a><span data-ttu-id="f519d-300">ウィンドウの外観</span><span class="sxs-lookup"><span data-stu-id="f519d-300">Window Appearance</span></span>  
 <span data-ttu-id="f519d-301">ウィンドウのクライアント領域の外観を変更するために、ボタン、ラベル、テキスト ボックスなど、ウィンドウ固有のコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="f519d-301">You change the appearance of the client area of a window by adding window-specific content to it, such as buttons, labels, and text boxes.</span></span> <span data-ttu-id="f519d-302">非クライアント領域を構成する<xref:System.Windows.Window>を含むいくつかのプロパティを提供します<xref:System.Windows.Window.Icon%2A>ウィンドウのアイコンを設定して<xref:System.Windows.Window.Title%2A>タイトルを設定します。</span><span class="sxs-lookup"><span data-stu-id="f519d-302">To configure the non-client area, <xref:System.Windows.Window> provides several properties, which include <xref:System.Windows.Window.Icon%2A> to set a window's icon and <xref:System.Windows.Window.Title%2A> to set its title.</span></span>  
  
 <span data-ttu-id="f519d-303">また、ウィンドウのサイズ変更モード、ウィンドウ スタイル、デスクトップのタスク バーにボタンとして表示するかどうかを構成して、非クライアント領域の境界線の外観と動作も変更できます。</span><span class="sxs-lookup"><span data-stu-id="f519d-303">You can also change the appearance and behavior of non-client area border by configuring a window's resize mode, window style, and whether it appears as a button in the desktop task bar.</span></span>  

<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a><span data-ttu-id="f519d-304">サイズ変更モード</span><span class="sxs-lookup"><span data-stu-id="f519d-304">Resize Mode</span></span>  
 <span data-ttu-id="f519d-305">に応じて、<xref:System.Windows.Window.WindowStyle%2A>プロパティを制御できますか (および場合) ユーザーがウィンドウのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="f519d-305">Depending on the <xref:System.Windows.Window.WindowStyle%2A> property, you can control how (and if) users can resize the window.</span></span> <span data-ttu-id="f519d-306">ウィンドウ スタイルの選択に影響をユーザーには、マウスで境界線をドラッグするかどうか、ウィンドウがサイズ変更するかどうか、**最小化**、**最大化**、および**サイズを変更する**ボタン非クライアント領域に表示し、有効にするかどうか、表示される場合。</span><span class="sxs-lookup"><span data-stu-id="f519d-306">The choice of window style affects whether a user can resize the window by dragging its border with the mouse, whether the **Minimize**, **Maximize**, and **Resize** buttons appear on the non-client area, and, if they do appear, whether they are enabled.</span></span>  
  
 <span data-ttu-id="f519d-307">設定してウィンドウのサイズ変更する方法を構成することができます、<xref:System.Windows.Window.ResizeMode%2A>プロパティで、次のいずれかの<xref:System.Windows.ResizeMode>列挙値。</span><span class="sxs-lookup"><span data-stu-id="f519d-307">You can configure how a window resizes by setting its <xref:System.Windows.Window.ResizeMode%2A> property, which can be one of the following <xref:System.Windows.ResizeMode> enumeration values:</span></span>  
  
-   <xref:System.Windows.ResizeMode.NoResize>  
  
-   <xref:System.Windows.ResizeMode.CanMinimize>  
  
-   <span data-ttu-id="f519d-308"><xref:System.Windows.ResizeMode.CanResize> (既定値)</span><span class="sxs-lookup"><span data-stu-id="f519d-308"><xref:System.Windows.ResizeMode.CanResize> (default)</span></span>  
  
-   <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 <span data-ttu-id="f519d-309">同様<xref:System.Windows.Window.WindowStyle%2A>、ウィンドウのサイズ変更モードを設定することがほとんどの場合から、その有効期間中に変更する可能性がない[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ。</span><span class="sxs-lookup"><span data-stu-id="f519d-309">As with <xref:System.Windows.Window.WindowStyle%2A>, the resize mode of a window is unlikely to change during its lifetime, which means that you'll most likely set it from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 <span data-ttu-id="f519d-310">ウィンドウが最大化されているかどうかを検出するので注意が最小化、および検査することによって、<xref:System.Windows.Window.WindowState%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f519d-310">Note that you can detect whether a window is maximized, minimized, or restored by inspecting the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a><span data-ttu-id="f519d-311">ウィンドウ スタイル</span><span class="sxs-lookup"><span data-stu-id="f519d-311">Window Style</span></span>  
 <span data-ttu-id="f519d-312">ウィンドウの非クライアント領域から公開される境界線は、多くのアプリケーションに適しています。</span><span class="sxs-lookup"><span data-stu-id="f519d-312">The border that is exposed from the non-client area of a window is suitable for most applications.</span></span> <span data-ttu-id="f519d-313">ただし、ウィンドウの種類によって、異なる種類の境界線が必要な状況や、境界線がまったく必要ない状況があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-313">However, there are circumstances where different types of borders are needed, or no borders are needed at all, depending on the type of window.</span></span>  
  
 <span data-ttu-id="f519d-314">ウィンドウの境界線の種類を制御するには、取得、設定したその<xref:System.Windows.Window.WindowStyle%2A>プロパティの値は次のいずれかで、<xref:System.Windows.WindowStyle>列挙体。</span><span class="sxs-lookup"><span data-stu-id="f519d-314">To control what type of border a window gets, you set its <xref:System.Windows.Window.WindowStyle%2A> property with one of the following values of the <xref:System.Windows.WindowStyle> enumeration:</span></span>  
  
-   <xref:System.Windows.WindowStyle.None>  
  
-   <span data-ttu-id="f519d-315"><xref:System.Windows.WindowStyle.SingleBorderWindow> (既定値)</span><span class="sxs-lookup"><span data-stu-id="f519d-315"><xref:System.Windows.WindowStyle.SingleBorderWindow> (default)</span></span>  
  
-   <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
-   <xref:System.Windows.WindowStyle.ToolWindow>  
  
 <span data-ttu-id="f519d-316">これらのウィンドウ スタイルの効果は、次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="f519d-316">The effect of these window styles are illustrated in the following figure:</span></span>  
  
 ![ウィンドウの境界線のスタイルの図。](./media/wpf-windows-overview/window-border-styles.png)  
  
 <span data-ttu-id="f519d-318">設定できる<xref:System.Windows.Window.WindowStyle%2A>いずれかを使用して[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップまたはコード ウィンドウの有効期間中に変更する可能性がないため、ほとんどの場合を構成を使用して[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ。</span><span class="sxs-lookup"><span data-stu-id="f519d-318">You can set <xref:System.Windows.Window.WindowStyle%2A> using either [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup or code; because it is unlikely to change during the lifetime of a window, you will most likely configure it using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a><span data-ttu-id="f519d-319">四角形以外のウィンドウ スタイル</span><span class="sxs-lookup"><span data-stu-id="f519d-319">Non-Rectangular Window Style</span></span>  
 <span data-ttu-id="f519d-320">境界線スタイルを設定、状況もあります<xref:System.Windows.Window.WindowStyle%2A>により満たされない場合。</span><span class="sxs-lookup"><span data-stu-id="f519d-320">There are also situations where the border styles that <xref:System.Windows.Window.WindowStyle%2A> allows you to have are not sufficient.</span></span> <span data-ttu-id="f519d-321">たとえばなどが四角形以外の枠線でアプリケーションを作成することがあります[!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="f519d-321">For example, you may want to create an application with a non-rectangular border, like [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] uses.</span></span>  
  
 <span data-ttu-id="f519d-322">たとえば、次の図に示す吹き出しウィンドウがあるとします。</span><span class="sxs-lookup"><span data-stu-id="f519d-322">For example, consider the speech bubble window shown in the following figure:</span></span>  
  
 ![ドラッグ me. ことを示す音声バブル ウィンドウ](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 <span data-ttu-id="f519d-324">この種類のウィンドウを設定して作成できます、<xref:System.Windows.Window.WindowStyle%2A>プロパティを<xref:System.Windows.WindowStyle.None>、および特殊なを使用してサポートを<xref:System.Windows.Window>の透明度が。</span><span class="sxs-lookup"><span data-stu-id="f519d-324">This type of window can be created by setting the <xref:System.Windows.Window.WindowStyle%2A> property to <xref:System.Windows.WindowStyle.None>, and by using special support that <xref:System.Windows.Window> has for transparency.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 <span data-ttu-id="f519d-325">値をこの組み合わせで使用し、ウィンドウが完全に透明にレンダリングされるように設定します。</span><span class="sxs-lookup"><span data-stu-id="f519d-325">This combination of values instructs the window to render completely transparent.</span></span> <span data-ttu-id="f519d-326">この状態では、ウィンドウの非クライアント領域の表示要素 (閉じるメニュー、最小化ボタン、最大化ボタン、元に戻すボタンなど) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="f519d-326">In this state, the window's non-client area adornments (the Close menu, Minimize, Maximize, and Restore buttons, and so on) cannot be used.</span></span> <span data-ttu-id="f519d-327">したがって、独自の表示要素を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-327">Consequently, you need to provide your own.</span></span>  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a><span data-ttu-id="f519d-328">タスク バーのプレゼンス</span><span class="sxs-lookup"><span data-stu-id="f519d-328">Task Bar Presence</span></span>  

<span data-ttu-id="f519d-329">ウィンドウの既定の外観には、次の図に示すように、タスク バーのボタンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f519d-329">The default appearance of a window includes a taskbar button, like the one shown in the following figure:</span></span>

 ![タスク バー ボタンを持つウィンドウを示すスクリーン ショット。](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 <span data-ttu-id="f519d-331">ウィンドウの種類によってはメッセージ ボックスやダイアログ ボックスなどのタスク バー ボタンがない (を参照してください[ダイアログ ボックスの概要](dialog-boxes-overview.md))。</span><span class="sxs-lookup"><span data-stu-id="f519d-331">Some types of windows don't have a task bar button, such as message boxes and dialog boxes (see [Dialog Boxes Overview](dialog-boxes-overview.md)).</span></span> <span data-ttu-id="f519d-332">ウィンドウのタスク バー ボタンを設定して表示するかを制御することができます、<xref:System.Windows.Window.ShowInTaskbar%2A>プロパティ (`true`既定)。</span><span class="sxs-lookup"><span data-stu-id="f519d-332">You can control whether the task bar button for a window is shown by setting the <xref:System.Windows.Window.ShowInTaskbar%2A> property (`true` by default).</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a><span data-ttu-id="f519d-333">セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="f519d-333">Security Considerations</span></span>  
 <span data-ttu-id="f519d-334"><xref:System.Windows.Window> 必要があります`UnmanagedCode`インスタンス化するためのセキュリティ アクセス許可。</span><span class="sxs-lookup"><span data-stu-id="f519d-334"><xref:System.Windows.Window> requires `UnmanagedCode` security permission to be instantiated.</span></span> <span data-ttu-id="f519d-335">ローカル コンピューターにインストールされ、ローカル コンピューターから起動されるアプリケーションの場合は、アプリケーションに付与されるアクセス許可セットの範囲内になります。</span><span class="sxs-lookup"><span data-stu-id="f519d-335">For applications installed on and launched from the local machine, this falls within the set of permissions that are granted to the application.</span></span>  
  
 <span data-ttu-id="f519d-336">ただし、これは、外からインターネットまたはローカル イントラネット ゾーンを使用して、起動されるアプリケーションに付与された権限のセット[!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f519d-336">However, this falls outside the set of permissions granted to applications that are launched from the Internet or Local intranet zone using [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)].</span></span> <span data-ttu-id="f519d-337">その結果、ユーザーが表示されます、[!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]セキュリティの警告と、アプリケーションの完全な信頼に設定するアクセス許可を昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f519d-337">Consequently, users will receive a [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] security warning and will need to elevate the permission set for the application to full trust.</span></span>  
  
 <span data-ttu-id="f519d-338">さらに、[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]既定でウィンドウまたはダイアログ ボックスを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="f519d-338">Additionally, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] cannot show windows or dialog boxes by default.</span></span> <span data-ttu-id="f519d-339">スタンドアロン アプリケーションのセキュリティに関する考慮事項については、次を参照してください。 [WPF のセキュリティ方針 - プラットフォーム セキュリティ](../wpf-security-strategy-platform-security.md)します。</span><span class="sxs-lookup"><span data-stu-id="f519d-339">For a discussion on standalone application security considerations, see [WPF Security Strategy - Platform Security](../wpf-security-strategy-platform-security.md).</span></span>  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a><span data-ttu-id="f519d-340">その他の種類のウィンドウ</span><span class="sxs-lookup"><span data-stu-id="f519d-340">Other Types of Windows</span></span>  
 <span data-ttu-id="f519d-341"><xref:System.Windows.Navigation.NavigationWindow> ナビゲート可能なコンテンツをホストするように設計されたウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="f519d-341"><xref:System.Windows.Navigation.NavigationWindow> is a window that is designed to host navigable content.</span></span> <span data-ttu-id="f519d-342">詳細については、次を参照してください。[ナビゲーションの概要](navigation-overview.md))。</span><span class="sxs-lookup"><span data-stu-id="f519d-342">For more information, see [Navigation Overview](navigation-overview.md)).</span></span>  
  
 <span data-ttu-id="f519d-343">ダイアログ ボックスは、ユーザーから情報を収集して機能を完了するためによく使用されるウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="f519d-343">Dialog boxes are windows that are often used to gather information from a user to complete a function.</span></span> <span data-ttu-id="f519d-344">ユーザーが、ファイルが場合など、**ファイルを開く** ダイアログ ボックスは通常、ユーザーからファイル名を取得するアプリケーションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="f519d-344">For example, when a user wants to open a file, the **Open File** dialog box is usually displayed by an application to get the file name from the user.</span></span> <span data-ttu-id="f519d-345">詳細については、「[ダイアログ ボックスの概要](dialog-boxes-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f519d-345">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f519d-346">関連項目</span><span class="sxs-lookup"><span data-stu-id="f519d-346">See also</span></span>

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [<span data-ttu-id="f519d-347">ダイアログ ボックスの概要</span><span class="sxs-lookup"><span data-stu-id="f519d-347">Dialog Boxes Overview</span></span>](dialog-boxes-overview.md)
- [<span data-ttu-id="f519d-348">WPF アプリケーションのビルド</span><span class="sxs-lookup"><span data-stu-id="f519d-348">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
