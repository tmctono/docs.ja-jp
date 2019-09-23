---
title: '方法: UI であるアドインを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that is a UI [WPF]
- add-ins [WPF], UI
- creating UI add-ins [WPF]
- UI add-ins [WPF], creating
- implementing UI add-ins [WPF]
- pipeline segments [WPF], creating add-ins
ms.assetid: 86375525-282b-4039-8352-8680051a10ea
ms.openlocfilehash: b0e847061a30e93d36997ab603c52715e2730765
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182637"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a><span data-ttu-id="eb3fd-102">方法: UI であるアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="eb3fd-102">How to: Create an Add-In That Is a UI</span></span>
<span data-ttu-id="eb3fd-103">この例では、WPF スタンドアロンアプリケーションによってホストされる Windows Presentation Foundation (WPF) であるアドインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-103">This example shows how to create an add-in that is a Windows Presentation Foundation (WPF) which is hosted by a WPF standalone application.</span></span>  
  
 <span data-ttu-id="eb3fd-104">アドインは、WPF ユーザーコントロールである UI です。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-104">The add-in is a UI that is a WPF user control.</span></span> <span data-ttu-id="eb3fd-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="eb3fd-106">WPF スタンドアロンアプリケーションは、アドイン UI をメインアプリケーションウィンドウのコンテンツとしてホストします。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-106">The WPF standalone application hosts the add-in UI as the content of the main application window.</span></span>  
  
 <span data-ttu-id="eb3fd-107">**必須コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="eb3fd-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="eb3fd-108">この例では、このシナリオを有効にする .NET Framework アドインモデルの WPF 拡張機能に焦点を当て、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="eb3fd-109">パイプライン、アドイン、およびホスト開発を含む .NET Framework アドインモデルに関する知識。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="eb3fd-110">これらの概念についてよく知らない場合は、「[アドインと拡張機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="eb3fd-111">パイプライン、アドイン、およびホストアプリケーションの実装方法を示すチュートリアルについては、「 [チュートリアル:拡張可能なアプリケーション](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))を作成する。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="eb3fd-112">.NET Framework アドインモデルに対する WPF 拡張機能に関する知識。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-112">Knowledge of the WPF extensions to the .NET Framework add-in model.</span></span> <span data-ttu-id="eb3fd-113">「 [WPF アドインの概要](wpf-add-ins-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-113">See [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb3fd-114">例</span><span class="sxs-lookup"><span data-stu-id="eb3fd-114">Example</span></span>  
 <span data-ttu-id="eb3fd-115">WPF UI であるアドインを作成するには、各パイプラインセグメント、アドイン、およびホストアプリケーションに特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-115">To create an add-in that is a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="eb3fd-116">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="eb3fd-116">Implementing the Contract Pipeline Segment</span></span>

<span data-ttu-id="eb3fd-117">アドインが UI の場合、アドインのコントラクトはを実装<xref:System.AddIn.Contract.INativeHandleContract>する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-117">When an add-in is a UI, the contract for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="eb3fd-118">この例`IWPFAddInContract`では、 <xref:System.AddIn.Contract.INativeHandleContract>次のコードに示すように、がを実装しています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-118">In the example, `IWPFAddInContract` implements <xref:System.AddIn.Contract.INativeHandleContract>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="eb3fd-119">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="eb3fd-119">Implementing the Add-In View Pipeline Segment</span></span>

<span data-ttu-id="eb3fd-120">アドインは<xref:System.Windows.FrameworkElement>型のサブクラスとして実装されるため、アドインビューでもサブクラス<xref:System.Windows.FrameworkElement>を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-120">Because the add-in is implemented as a subclass of the <xref:System.Windows.FrameworkElement> type, the add-in view must also subclass <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="eb3fd-121">次のコードは、 `WPFAddInView`クラスとして実装されているコントラクトのアドインビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-121">The following code shows the add-in view of the contract, implemented as the `WPFAddInView` class.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
<span data-ttu-id="eb3fd-122">ここでは、アドインビューはから<xref:System.Windows.Controls.UserControl>派生しています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-122">Here, the add-in view is derived from <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="eb3fd-123">そのため、アドインの UI もから<xref:System.Windows.Controls.UserControl>派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-123">Consequently, the add-in UI should also derive from <xref:System.Windows.Controls.UserControl>.</span></span>  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="eb3fd-124">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="eb3fd-124">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="eb3fd-125">コントラクトが<xref:System.AddIn.Contract.INativeHandleContract>の場合、アドイン<xref:System.Windows.FrameworkElement>は (アドインビューのパイプラインセグメントで指定されている) です。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-125">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the add-in is a <xref:System.Windows.FrameworkElement> (as specified by the add-in view pipeline segment).</span></span> <span data-ttu-id="eb3fd-126">したがって、 <xref:System.Windows.FrameworkElement>分離境界を越える<xref:System.AddIn.Contract.INativeHandleContract>前に、をに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-126">Therefore, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="eb3fd-127">この作業は、次のコードに示すように、を呼び<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>出すことによってアドイン側のアダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-127">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

<span data-ttu-id="eb3fd-128">アドインが ui を返すアドインモデル (「 [ui を返すアドインを作成](how-to-create-an-add-in-that-returns-a-ui.md)する」を参照) では、アドインアダプターはを<xref:System.Windows.FrameworkElement>呼び出し<xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>て、をに変換します。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-128">In the add-in model where an add-in returns a UI (see [Create an Add-In That Returns a UI](how-to-create-an-add-in-that-returns-a-ui.md)), the add-in adapter converted the <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="eb3fd-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>このモデルでも呼び出される必要がありますが、呼び出すコードを記述するメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> must also be called in this model, although you need to implement a method from which to write the code to call it.</span></span> <span data-ttu-id="eb3fd-130">これを行うには<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> 、を呼び出すコードがを<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>必要<xref:System.AddIn.Contract.INativeHandleContract>とする場合<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>に、を呼び出すコードをオーバーライドして実装します。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-130">You do this by overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> and implementing the code that calls <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> if the code that is calling <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is expecting an <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="eb3fd-131">この場合、呼び出し元はホスト側のアダプターであり、これについては、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-131">In this case, the caller will be the host-side adapter, which is covered in a subsequent subsection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb3fd-132">また、このモデルで<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>をオーバーライドして、ホストアプリケーション ui とアドイン ui 間のタブ移動を有効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-132">You also need to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in this model to enable tabbing between host application UI and add-in UI.</span></span> <span data-ttu-id="eb3fd-133">詳細については、「Wpf アドインの[概要](wpf-add-ins-overview.md)」の「wpf アドインの制限事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-133">For more information, see "WPF Add-In Limitations" in [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
<span data-ttu-id="eb3fd-134">アドイン側アダプターはから<xref:System.AddIn.Contract.INativeHandleContract>派生するインターフェイスを実装するため、を実装<xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>する必要もあります。ただし、をオーバーライドし<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>た場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-134">Because the add-in-side adapter implements an interface that derives from <xref:System.AddIn.Contract.INativeHandleContract>, you also need to implement <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, although this is ignored when <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is overridden.</span></span>  
  
<a name="HostViewPipeline"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="eb3fd-135">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="eb3fd-135">Implementing the Host View Pipeline Segment</span></span>

<span data-ttu-id="eb3fd-136">このモデルでは、ホストアプリケーションは通常、ホストビューが<xref:System.Windows.FrameworkElement>サブクラスであることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-136">In this model, the host application typically expects the host view to be a <xref:System.Windows.FrameworkElement> subclass.</span></span> <span data-ttu-id="eb3fd-137">が分離境界を<xref:System.AddIn.Contract.INativeHandleContract> <xref:System.AddIn.Contract.INativeHandleContract>越え<xref:System.Windows.FrameworkElement>た後、ホスト側アダプターはをに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-137">The host-side adapter must convert the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary.</span></span> <span data-ttu-id="eb3fd-138">メソッドは、 <xref:System.Windows.FrameworkElement>を取得するためにホストアプリケーションによって呼び出されないため、ホストビューはそれ<xref:System.Windows.FrameworkElement>を含むを "返す" 必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-138">Because a method isn't being called by the host application to get the <xref:System.Windows.FrameworkElement>, the host view must "return" the <xref:System.Windows.FrameworkElement> by containing it.</span></span> <span data-ttu-id="eb3fd-139">そのため、ホストビューは、などの他の<xref:System.Windows.FrameworkElement> ui を<xref:System.Windows.Controls.UserControl>含むことができるのサブクラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-139">Consequently, the host view must derive from a subclass of <xref:System.Windows.FrameworkElement> that can contain other UIs, such as <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="eb3fd-140">次のコードは、 `WPFAddInHostView`クラスとして実装されているコントラクトのホストビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-140">The following code shows the host view of the contract, implemented as the `WPFAddInHostView` class.</span></span>  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="eb3fd-141">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="eb3fd-141">Implementing the Host-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="eb3fd-142">コントラクトが<xref:System.AddIn.Contract.INativeHandleContract>の場合、ホストアプリケーションは (ホストビュー <xref:System.Windows.Controls.UserControl>で指定されているように) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-142">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the host application expects a <xref:System.Windows.Controls.UserControl> (as specified by the host view).</span></span> <span data-ttu-id="eb3fd-143">そのため、分離境界を越え<xref:System.Windows.FrameworkElement>た後にをに変換してから、ホストビュー (から<xref:System.Windows.Controls.UserControl>派生) のコンテンツとして設定する必要があります。<xref:System.AddIn.Contract.INativeHandleContract></span><span class="sxs-lookup"><span data-stu-id="eb3fd-143">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary, before being set as content of the host view (which derives from <xref:System.Windows.Controls.UserControl>).</span></span>  
  
<span data-ttu-id="eb3fd-144">この作業は、次のコードに示されているように、ホスト側アダプターによって行われます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-144">This work is performed by the host-side adapter, as shown in the following code.</span></span>  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

<span data-ttu-id="eb3fd-145">ご覧のように、ホスト側アダプターは、アドイン側<xref:System.AddIn.Contract.INativeHandleContract>アダプターの<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>メソッドを呼び出すことによってを取得します (これ<xref:System.AddIn.Contract.INativeHandleContract>はが分離境界を越える点です)。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-145">As you can see, the host-side adapter acquires the <xref:System.AddIn.Contract.INativeHandleContract> by calling the add-in-side adapter's <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> method (this is the point where the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary).</span></span>  
  
<span data-ttu-id="eb3fd-146">次に、を呼び出し<xref:System.AddIn.Contract.INativeHandleContract> <xref:System.Windows.FrameworkElement> <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>て、をに変換します。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-146">The host-side adapter then converts the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="eb3fd-147">最後に<xref:System.Windows.FrameworkElement> 、はホストビューのコンテンツとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-147">Finally, the <xref:System.Windows.FrameworkElement> is set as the content of the host view.</span></span>  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="eb3fd-148">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="eb3fd-148">Implementing the Add-In</span></span>

<span data-ttu-id="eb3fd-149">アドイン側アダプターとアドイン ビューが用意できると、次のコードに示されているように、アドイン ビューから派生することでアドインを実装できます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-149">With the add-in-side adapter and add-in view in place, the add-in can be implemented by deriving from the add-in view, as shown in the following code.</span></span>  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

<span data-ttu-id="eb3fd-150">この例では、このモデルの1つの興味深い利点を確認できます。アドインの開発者は、アドインとアドインの UI の両方ではなく、アドインのみを実装する必要があります (UI でもあるため)。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-150">From this example, you can see one interesting benefit of this model: add-in developers only need to implement the add-in (since it is the UI as well), rather than both an add-in class and an add-in UI.</span></span>  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a><span data-ttu-id="eb3fd-151">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="eb3fd-151">Implementing the Host Application</span></span>

<span data-ttu-id="eb3fd-152">ホスト側アダプターとホストビューを作成すると、ホストアプリケーションは .NET Framework アドインモデルを使用して、パイプラインを開き、アドインのホストビューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-152">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline and acquire a host view of the add-in.</span></span> <span data-ttu-id="eb3fd-153">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-153">These steps are shown in the following code.</span></span>  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

<span data-ttu-id="eb3fd-154">ホストアプリケーションは、一般的な .NET Framework アドインモデルコードを使用してアドインをアクティブ化します。これにより、ホストビューが暗黙的にホストアプリケーションに返されます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-154">The host application uses typical .NET Framework add-in model code to activate the add-in, which implicitly returns the host view to the host application.</span></span> <span data-ttu-id="eb3fd-155">その後、ホストアプリケーションでは、 <xref:System.Windows.Controls.UserControl> <xref:System.Windows.Controls.Grid>からのホストビュー () が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-155">The host application subsequently displays the host view (which is a <xref:System.Windows.Controls.UserControl>) from a <xref:System.Windows.Controls.Grid>.</span></span>  
  
 <span data-ttu-id="eb3fd-156">アドインの UI との対話処理のコードは、アドインのアプリケーションドメインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-156">The code for processing interactions with the add-in UI runs in the add-in's application domain.</span></span> <span data-ttu-id="eb3fd-157">このような対話には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-157">These interactions include the following:</span></span>  
  
- <span data-ttu-id="eb3fd-158">イベントの<xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click>処理。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-158">Handling the <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
- <span data-ttu-id="eb3fd-159">を表示<xref:System.Windows.MessageBox>しています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-159">Showing the <xref:System.Windows.MessageBox>.</span></span>  
  
 <span data-ttu-id="eb3fd-160">このアクティビティは、ホスト アプリケーションから完全に分離されています。</span><span class="sxs-lookup"><span data-stu-id="eb3fd-160">This activity is completely isolated from the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3fd-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb3fd-161">See also</span></span>

- <span data-ttu-id="eb3fd-162">[アドインおよび拡張機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="eb3fd-162">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="eb3fd-163">WPF のアドインの概要</span><span class="sxs-lookup"><span data-stu-id="eb3fd-163">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
