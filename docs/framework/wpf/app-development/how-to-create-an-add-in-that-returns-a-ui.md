---
title: '方法: UI を返すアドインを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: 1886703e089ed538f68a7221906d815a8ae72076
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182663"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="b41c7-102">方法: UI を返すアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="b41c7-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="b41c7-103">この例では、Windows Presentation Foundation (WPF) をホスト WPF スタンドアロンアプリケーションに返すアドインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b41c7-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="b41c7-104">このアドインは、WPF ユーザーコントロールの UI を返します。</span><span class="sxs-lookup"><span data-stu-id="b41c7-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="b41c7-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="b41c7-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="b41c7-106">WPF スタンドアロンアプリケーションは、アドインをホストし、アドインによって返されたユーザーコントロールをメインアプリケーションウィンドウの内容として表示します。</span><span class="sxs-lookup"><span data-stu-id="b41c7-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="b41c7-107">**必須コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="b41c7-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="b41c7-108">この例では、このシナリオを有効にする .NET Framework アドインモデルの WPF 拡張機能に焦点を当て、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b41c7-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="b41c7-109">パイプライン、アドイン、およびホスト開発を含む .NET Framework アドインモデルに関する知識。</span><span class="sxs-lookup"><span data-stu-id="b41c7-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="b41c7-110">これらの概念についてよく知らない場合は、「[アドインと拡張機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b41c7-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="b41c7-111">パイプライン、アドイン、およびホストアプリケーションの実装方法を示すチュートリアルについては、「 [チュートリアル:拡張可能なアプリケーション](../../add-ins/walkthrough-create-extensible-app.md)を作成する。</span><span class="sxs-lookup"><span data-stu-id="b41c7-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
- <span data-ttu-id="b41c7-112">.NET Framework アドインモデルに対する WPF 拡張機能について説明します。これについては、次を参照してください。[WPF アドインの概要](wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b41c7-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b41c7-113">例</span><span class="sxs-lookup"><span data-stu-id="b41c7-113">Example</span></span>  
 <span data-ttu-id="b41c7-114">WPF UI を返すアドインを作成するには、各パイプラインセグメント、アドイン、およびホストアプリケーションに特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="b41c7-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="b41c7-115">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="b41c7-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="b41c7-116">メソッドは、UI を返すためにコントラクトによって定義される必要があり、戻り値<xref:System.AddIn.Contract.INativeHandleContract>は型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41c7-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="b41c7-117">これは、次の`GetAddInUI`コードの`IWPFAddInContract`コントラクトのメソッドによって示されます。</span><span class="sxs-lookup"><span data-stu-id="b41c7-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="b41c7-118">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="b41c7-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="b41c7-119">[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]アドインは、の<xref:System.Windows.FrameworkElement>サブクラスとして提供するを実装しているため、に関連付けら`IWPFAddInView.GetAddInUI`れているアドインビューのメソッドは<xref:System.Windows.FrameworkElement>型の値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41c7-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b41c7-120">次のコードは、コントラクトのアドイン ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b41c7-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="b41c7-121">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="b41c7-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="b41c7-122">コントラクトメソッドはを返し<xref:System.AddIn.Contract.INativeHandleContract>ますが、アドインは<xref:System.Windows.FrameworkElement> (アドインビューで指定されているように) を返します。</span><span class="sxs-lookup"><span data-stu-id="b41c7-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="b41c7-123">そのため、 <xref:System.Windows.FrameworkElement>分離境界を越える<xref:System.AddIn.Contract.INativeHandleContract>前に、をに変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41c7-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="b41c7-124">この作業は、次のコードに示すように、を呼び<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>出すことによってアドイン側のアダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="b41c7-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="b41c7-125">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="b41c7-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="b41c7-126">ホストアプリケーションはを表示<xref:System.Windows.FrameworkElement>するため、に関連付けら`IWPFAddInHostView.GetAddInUI`れているホストビューのメソッドは、型<xref:System.Windows.FrameworkElement>の値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41c7-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="b41c7-127">次のコードは、コントラクトのホスト ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b41c7-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="b41c7-128">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="b41c7-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="b41c7-129">コントラクトメソッドはを返し<xref:System.AddIn.Contract.INativeHandleContract>ますが、ホストアプリケーションは ( <xref:System.Windows.FrameworkElement>ホストビューで指定されているように) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b41c7-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="b41c7-130">そのため、分離境界を越えると<xref:System.Windows.FrameworkElement> 、はに変換される必要があります。<xref:System.AddIn.Contract.INativeHandleContract></span><span class="sxs-lookup"><span data-stu-id="b41c7-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="b41c7-131">この作業は、次のコードに示すように、 <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>を呼び出すことによってホスト側アダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="b41c7-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="b41c7-132">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="b41c7-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="b41c7-133">アドイン側のアダプターとアドインビューを作成した場合、`WPFAddIn1.AddIn`アドイン () は、 <xref:System.Windows.FrameworkElement>オブジェクト (この例では`IWPFAddInView.GetAddInUI` <xref:System.Windows.Controls.UserControl> ) を返すメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41c7-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="b41c7-134">の実装<xref:System.Windows.Controls.UserControl> `AddInUI`は、次のコードによって示されます。</span><span class="sxs-lookup"><span data-stu-id="b41c7-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="b41c7-135">アドイン`IWPFAddInView.GetAddInUI`によるの実装では、次のコードに示すように、単`AddInUI`にの新しいインスタンスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b41c7-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="b41c7-136">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="b41c7-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="b41c7-137">ホスト側アダプターとホストビューを作成すると、ホストアプリケーションは .NET Framework アドインモデルを使用してパイプラインを開き、アドインのホストビューを取得して、 `IWPFAddInHostView.GetAddInUI`メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b41c7-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="b41c7-138">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="b41c7-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="b41c7-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="b41c7-139">See also</span></span>

- <span data-ttu-id="b41c7-140">[アドインおよび拡張機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="b41c7-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="b41c7-141">WPF のアドインの概要</span><span class="sxs-lookup"><span data-stu-id="b41c7-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
