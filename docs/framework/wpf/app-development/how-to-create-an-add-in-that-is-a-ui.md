---
title: '方法 : UI であるアドインを作成する'
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
ms.openlocfilehash: 339231031b9e57b9f00a2aeb6fbbde8ad66c1ad9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141030"
---
# <a name="how-to-create-an-add-in-that-is-a-ui"></a><span data-ttu-id="cebcb-102">方法 : UI であるアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="cebcb-102">How to: Create an Add-In That Is a UI</span></span>
<span data-ttu-id="cebcb-103">この例では、WPF スタンドアロン アプリケーションによってホストされる Windows プレゼンテーション ファンデーション (WPF) であるアドインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-103">This example shows how to create an add-in that is a Windows Presentation Foundation (WPF) which is hosted by a WPF standalone application.</span></span>  
  
 <span data-ttu-id="cebcb-104">アドインは、WPF ユーザー コントロールである UI です。</span><span class="sxs-lookup"><span data-stu-id="cebcb-104">The add-in is a UI that is a WPF user control.</span></span> <span data-ttu-id="cebcb-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="cebcb-106">WPF スタンドアロン アプリケーションは、メイン アプリケーション ウィンドウのコンテンツとしてアドイン UI をホストします。</span><span class="sxs-lookup"><span data-stu-id="cebcb-106">The WPF standalone application hosts the add-in UI as the content of the main application window.</span></span>  
  
 <span data-ttu-id="cebcb-107">**前提条件**</span><span class="sxs-lookup"><span data-stu-id="cebcb-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="cebcb-108">この例では、このシナリオを有効にする .NET Framework アドイン モデルの WPF 拡張機能を強調表示し、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="cebcb-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="cebcb-109">パイプライン、アドイン、ホスト開発など、.NET Framework アドイン モデルに関する知識。</span><span class="sxs-lookup"><span data-stu-id="cebcb-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="cebcb-110">これらの概念に詳しくない場合は、「[アドインと機能拡張](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cebcb-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="cebcb-111">パイプライン、アドイン、およびホスト アプリケーションの実装を示すチュートリアルについては、「[チュートリアル : 拡張アプリケーションの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cebcb-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="cebcb-112">.NET Framework アドイン モデルに対する WPF 拡張機能に関する知識。</span><span class="sxs-lookup"><span data-stu-id="cebcb-112">Knowledge of the WPF extensions to the .NET Framework add-in model.</span></span> <span data-ttu-id="cebcb-113">[WPF アドインの概要 を](wpf-add-ins-overview.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cebcb-113">See [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cebcb-114">例</span><span class="sxs-lookup"><span data-stu-id="cebcb-114">Example</span></span>  
 <span data-ttu-id="cebcb-115">WPF UI であるアドインを作成するには、パイプライン セグメント、アドイン、およびホスト アプリケーションごとに特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="cebcb-115">To create an add-in that is a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="cebcb-116">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="cebcb-116">Implementing the Contract Pipeline Segment</span></span>

<span data-ttu-id="cebcb-117">アドインが UI の場合、アドインのコントラクトは を実装<xref:System.AddIn.Contract.INativeHandleContract>する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-117">When an add-in is a UI, the contract for the add-in must implement <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="cebcb-118">この例では、`IWPFAddInContract`次の<xref:System.AddIn.Contract.INativeHandleContract>コードに示すように を実装します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-118">In the example, `IWPFAddInContract` implements <xref:System.AddIn.Contract.INativeHandleContract>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
[!code-vb[SimpleAddInIsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]

<a name="AddInViewPipeline"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="cebcb-119">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="cebcb-119">Implementing the Add-In View Pipeline Segment</span></span>

<span data-ttu-id="cebcb-120">アドインは<xref:System.Windows.FrameworkElement>型のサブクラスとして実装されているため、アドイン ビューもサブクラス<xref:System.Windows.FrameworkElement>を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-120">Because the add-in is implemented as a subclass of the <xref:System.Windows.FrameworkElement> type, the add-in view must also subclass <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="cebcb-121">次のコードは、クラスとして実装されたコントラクトのアドイン ビューを`WPFAddInView`示しています。</span><span class="sxs-lookup"><span data-stu-id="cebcb-121">The following code shows the add-in view of the contract, implemented as the `WPFAddInView` class.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInViews/WPFAddInView.cs#addinviewcode)]  
[!code-vb[SimpleAddInIsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInViews/WPFAddInView.vb#AddInViewCode)]  
  
<span data-ttu-id="cebcb-122">ここでは、アドイン ビューは<xref:System.Windows.Controls.UserControl>から派生します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-122">Here, the add-in view is derived from <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="cebcb-123">したがって、アドイン UI も<xref:System.Windows.Controls.UserControl>から派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-123">Consequently, the add-in UI should also derive from <xref:System.Windows.Controls.UserControl>.</span></span>  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="cebcb-124">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="cebcb-124">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="cebcb-125">コントラクトが<xref:System.AddIn.Contract.INativeHandleContract>である間、アドインは<xref:System.Windows.FrameworkElement>(アドイン ビュー パイプライン セグメントで指定された) です。</span><span class="sxs-lookup"><span data-stu-id="cebcb-125">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the add-in is a <xref:System.Windows.FrameworkElement> (as specified by the add-in view pipeline segment).</span></span> <span data-ttu-id="cebcb-126">したがって、分離<xref:System.Windows.FrameworkElement>境界を越える前<xref:System.AddIn.Contract.INativeHandleContract>に に 変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-126">Therefore, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="cebcb-127">この作業は、次のコードに示すように、 を呼<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>び出すことによってアドイン側アダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="cebcb-127">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
[!code-csharp[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]  
[!code-vb[SimpleAddInIsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]

<span data-ttu-id="cebcb-128">アドインが UI を返すアドイン モデル (「UI を[返すアドインを作成](how-to-create-an-add-in-that-returns-a-ui.md)する」を参照) では、アドイン アダプタは<xref:System.Windows.FrameworkElement>を<xref:System.AddIn.Contract.INativeHandleContract>呼び<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>出して に変換します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-128">In the add-in model where an add-in returns a UI (see [Create an Add-In That Returns a UI](how-to-create-an-add-in-that-returns-a-ui.md)), the add-in adapter converted the <xref:System.Windows.FrameworkElement> to an <xref:System.AddIn.Contract.INativeHandleContract> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.</span></span> <span data-ttu-id="cebcb-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>このモデルでも呼び出す必要がありますが、呼び出すコードを記述するメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-129"><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> must also be called in this model, although you need to implement a method from which to write the code to call it.</span></span> <span data-ttu-id="cebcb-130">これを行うには、呼び<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>出すコードがを必要<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>としている場合に呼び<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>出すコード<xref:System.AddIn.Contract.INativeHandleContract>をオーバーライドして実装します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-130">You do this by overriding <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> and implementing the code that calls <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> if the code that is calling <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is expecting an <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="cebcb-131">この場合、呼び出し元はホスト側のアダプターであり、これについては、後で説明します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-131">In this case, the caller will be the host-side adapter, which is covered in a subsequent subsection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cebcb-132">ホスト アプリケーション UI<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>とアドイン UI 間のタブ移動を有効にするには、このモデルでオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-132">You also need to override <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> in this model to enable tabbing between host application UI and add-in UI.</span></span> <span data-ttu-id="cebcb-133">詳細については、「WPF アドインの概要」の[「WPF アドインの](wpf-add-ins-overview.md)制限」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cebcb-133">For more information, see "WPF Add-In Limitations" in [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
<span data-ttu-id="cebcb-134">アドイン側アダプタは から<xref:System.AddIn.Contract.INativeHandleContract>派生するインターフェイスを実装しているため、 をオーバーライドすると<xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A><xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>、このメソッドは無視されますが、 も実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-134">Because the add-in-side adapter implements an interface that derives from <xref:System.AddIn.Contract.INativeHandleContract>, you also need to implement <xref:System.AddIn.Contract.INativeHandleContract.GetHandle%2A>, although this is ignored when <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> is overridden.</span></span>  
  
<a name="HostViewPipeline"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="cebcb-135">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="cebcb-135">Implementing the Host View Pipeline Segment</span></span>

<span data-ttu-id="cebcb-136">このモデルでは、ホスト アプリケーションは通常、ホスト ビューをサブ<xref:System.Windows.FrameworkElement>クラスと想定します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-136">In this model, the host application typically expects the host view to be a <xref:System.Windows.FrameworkElement> subclass.</span></span> <span data-ttu-id="cebcb-137">ホスト側アダプターは、分離境界<xref:System.AddIn.Contract.INativeHandleContract>を越えた<xref:System.Windows.FrameworkElement>後に<xref:System.AddIn.Contract.INativeHandleContract>を に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-137">The host-side adapter must convert the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> after the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary.</span></span> <span data-ttu-id="cebcb-138">メソッドは、ホスト アプリケーションからを取得するために呼び出されていないの<xref:System.Windows.FrameworkElement>で、ホスト ビューは、 を<xref:System.Windows.FrameworkElement>格納することによって" 返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-138">Because a method isn't being called by the host application to get the <xref:System.Windows.FrameworkElement>, the host view must "return" the <xref:System.Windows.FrameworkElement> by containing it.</span></span> <span data-ttu-id="cebcb-139">したがって、ホスト ビューは、 などの<xref:System.Windows.FrameworkElement><xref:System.Windows.Controls.UserControl>他の UI を含むことができる サブクラスから派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-139">Consequently, the host view must derive from a subclass of <xref:System.Windows.FrameworkElement> that can contain other UIs, such as <xref:System.Windows.Controls.UserControl>.</span></span> <span data-ttu-id="cebcb-140">次のコードは、クラスとして実装されたコントラクトのホスト ビューを`WPFAddInHostView`示しています。</span><span class="sxs-lookup"><span data-stu-id="cebcb-140">The following code shows the host view of the contract, implemented as the `WPFAddInHostView` class.</span></span>  

[!code-csharp[WPFAddInHostView class](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostViews/WPFAddInHostView.cs#HostViewCode)]
[!code-vb[WPFAddInHostView class](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostViews/WPFAddInHostView.vb#HostViewCode)]

<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="cebcb-141">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="cebcb-141">Implementing the Host-Side Adapter Pipeline Segment</span></span>

<span data-ttu-id="cebcb-142">コントラクトが<xref:System.AddIn.Contract.INativeHandleContract>である間、ホスト アプリケーションは<xref:System.Windows.Controls.UserControl>ホスト ビューで指定された を要求します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-142">While the contract is an <xref:System.AddIn.Contract.INativeHandleContract>, the host application expects a <xref:System.Windows.Controls.UserControl> (as specified by the host view).</span></span> <span data-ttu-id="cebcb-143">したがって、分離境界<xref:System.AddIn.Contract.INativeHandleContract>を越えた<xref:System.Windows.FrameworkElement>後に、ホスト ビューのコンテンツとして設定される前に 、 に変換する必要があります<xref:System.Windows.Controls.UserControl>( から派生します)。</span><span class="sxs-lookup"><span data-stu-id="cebcb-143">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary, before being set as content of the host view (which derives from <xref:System.Windows.Controls.UserControl>).</span></span>  
  
<span data-ttu-id="cebcb-144">この作業は、次のコードに示されているように、ホスト側アダプターによって行われます。</span><span class="sxs-lookup"><span data-stu-id="cebcb-144">This work is performed by the host-side adapter, as shown in the following code.</span></span>  

[!code-csharp[Host-side adapter](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#HostSideAdapterCode)]
[!code-vb[Host-side adapter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#HostSideAdapterCode)]

<span data-ttu-id="cebcb-145">ご覧のとおり、ホスト側アダプターは、アドイン側アダプター<xref:System.AddIn.Contract.INativeHandleContract>の<xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>メソッドを呼び出すことによってを取得します (これは分離境界を<xref:System.AddIn.Contract.INativeHandleContract>越えるポイントです)。</span><span class="sxs-lookup"><span data-stu-id="cebcb-145">As you can see, the host-side adapter acquires the <xref:System.AddIn.Contract.INativeHandleContract> by calling the add-in-side adapter's <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> method (this is the point where the <xref:System.AddIn.Contract.INativeHandleContract> crosses the isolation boundary).</span></span>  
  
<span data-ttu-id="cebcb-146">ホスト側アダプタは、 を<xref:System.AddIn.Contract.INativeHandleContract>呼び出<xref:System.Windows.FrameworkElement><xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>して に変換します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-146">The host-side adapter then converts the <xref:System.AddIn.Contract.INativeHandleContract> to a <xref:System.Windows.FrameworkElement> by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.</span></span> <span data-ttu-id="cebcb-147">最後に<xref:System.Windows.FrameworkElement>、ホスト ビューの内容として 設定されます。</span><span class="sxs-lookup"><span data-stu-id="cebcb-147">Finally, the <xref:System.Windows.FrameworkElement> is set as the content of the host view.</span></span>  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a><span data-ttu-id="cebcb-148">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="cebcb-148">Implementing the Add-In</span></span>

<span data-ttu-id="cebcb-149">アドイン側アダプターとアドイン ビューが用意できると、次のコードに示されているように、アドイン ビューから派生することでアドインを実装できます。</span><span class="sxs-lookup"><span data-stu-id="cebcb-149">With the add-in-side adapter and add-in view in place, the add-in can be implemented by deriving from the add-in view, as shown in the following code.</span></span>  

[!code-csharp[Add-in implementation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#AddInCodeBehind)]
[!code-vb[Add-in implementation](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#AddInCodeBehind)]

<span data-ttu-id="cebcb-150">この例では、アドイン の開発者はアドイン クラスとアドイン UI の両方ではなく、アドインを実装するだけで済むという、このモデルの興味深い利点を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="cebcb-150">From this example, you can see one interesting benefit of this model: add-in developers only need to implement the add-in (since it is the UI as well), rather than both an add-in class and an add-in UI.</span></span>  
  
<a name="HostApp"></a>
## <a name="implementing-the-host-application"></a><span data-ttu-id="cebcb-151">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="cebcb-151">Implementing the Host Application</span></span>

<span data-ttu-id="cebcb-152">ホスト側のアダプターとホスト ビューを作成すると、ホスト アプリケーションは .NET Framework アドイン モデルを使用してパイプラインを開き、アドインのホスト ビューを取得できます。</span><span class="sxs-lookup"><span data-stu-id="cebcb-152">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline and acquire a host view of the add-in.</span></span> <span data-ttu-id="cebcb-153">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-153">These steps are shown in the following code.</span></span>  

[!code-csharp[Acquiring a host view of the add-in](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInIsAUISample/CSharp/Host/MainWindow.xaml.cs#GetUICode)]
[!code-vb[Acquiring a host view of the add-in](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInIsAUISample/VisualBasic/Host/MainWindow.xaml.vb#GetUICode)]

<span data-ttu-id="cebcb-154">ホスト アプリケーションは、一般的な .NET Framework アドイン モデル コードを使用してアドインをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-154">The host application uses typical .NET Framework add-in model code to activate the add-in, which implicitly returns the host view to the host application.</span></span> <span data-ttu-id="cebcb-155">ホスト アプリケーションは、その後、 からホスト<xref:System.Windows.Controls.UserControl>ビュー ( <xref:System.Windows.Controls.Grid>) を表示します。</span><span class="sxs-lookup"><span data-stu-id="cebcb-155">The host application subsequently displays the host view (which is a <xref:System.Windows.Controls.UserControl>) from a <xref:System.Windows.Controls.Grid>.</span></span>  
  
 <span data-ttu-id="cebcb-156">アドイン UI との対話を処理するためのコードは、アドインのアプリケーション ドメインで実行されます。</span><span class="sxs-lookup"><span data-stu-id="cebcb-156">The code for processing interactions with the add-in UI runs in the add-in's application domain.</span></span> <span data-ttu-id="cebcb-157">このような対話には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="cebcb-157">These interactions include the following:</span></span>  
  
- <span data-ttu-id="cebcb-158">イベントの<xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click>処理。</span><span class="sxs-lookup"><span data-stu-id="cebcb-158">Handling the <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
- <span data-ttu-id="cebcb-159">を表示<xref:System.Windows.MessageBox>する。</span><span class="sxs-lookup"><span data-stu-id="cebcb-159">Showing the <xref:System.Windows.MessageBox>.</span></span>  
  
 <span data-ttu-id="cebcb-160">このアクティビティは、ホスト アプリケーションから完全に分離されています。</span><span class="sxs-lookup"><span data-stu-id="cebcb-160">This activity is completely isolated from the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cebcb-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="cebcb-161">See also</span></span>

- <span data-ttu-id="cebcb-162">[アドインと拡張性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="cebcb-162">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="cebcb-163">WPF アドインの概要</span><span class="sxs-lookup"><span data-stu-id="cebcb-163">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
