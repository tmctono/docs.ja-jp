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
ms.openlocfilehash: e32987355a6c7ad32b5e0e8522dc4daa63783fdd
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291246"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="37ba4-102">方法: UI を返すアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="37ba4-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="37ba4-103">この例では、Windows Presentation Foundation (WPF) をホスト WPF スタンドアロンアプリケーションに返すアドインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37ba4-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="37ba4-104">このアドインは、WPF ユーザーコントロールの UI を返します。</span><span class="sxs-lookup"><span data-stu-id="37ba4-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="37ba4-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="37ba4-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="37ba4-106">WPF スタンドアロンアプリケーションは、アドインをホストし、アドインによって返されたユーザーコントロールをメインアプリケーションウィンドウの内容として表示します。</span><span class="sxs-lookup"><span data-stu-id="37ba4-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="37ba4-107">**前提条件**</span><span class="sxs-lookup"><span data-stu-id="37ba4-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="37ba4-108">この例では、このシナリオを有効にする .NET Framework アドインモデルの WPF 拡張機能に焦点を当て、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="37ba4-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="37ba4-109">パイプライン、アドイン、およびホスト開発を含む .NET Framework アドインモデルに関する知識。</span><span class="sxs-lookup"><span data-stu-id="37ba4-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="37ba4-110">これらの概念についてよく知らない場合は、「[アドインと拡張機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37ba4-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="37ba4-111">パイプライン、アドイン、およびホストアプリケーションの実装方法を示すチュートリアルについては、[Walkthrough を参照してください。拡張可能なアプリケーションを作成する @ no__t-0。</span><span class="sxs-lookup"><span data-stu-id="37ba4-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
- <span data-ttu-id="37ba4-112">.NET Framework アドインモデルに対する WPF 拡張機能について説明します。これについては、次を参照してください。[WPF アドインの概要](wpf-add-ins-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="37ba4-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37ba4-113">例</span><span class="sxs-lookup"><span data-stu-id="37ba4-113">Example</span></span>  
 <span data-ttu-id="37ba4-114">WPF UI を返すアドインを作成するには、各パイプラインセグメント、アドイン、およびホストアプリケーションに特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="37ba4-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="37ba4-115">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="37ba4-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="37ba4-116">UI を返すには、コントラクトによってメソッドが定義されている必要があります。また、戻り値の型は <xref:System.AddIn.Contract.INativeHandleContract> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ba4-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="37ba4-117">これは、次のコードの `IWPFAddInContract` コントラクトの `GetAddInUI` メソッドによって示されます。</span><span class="sxs-lookup"><span data-stu-id="37ba4-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="37ba4-118">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="37ba4-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="37ba4-119">アドインは @no__t 0 のサブクラスとして提供する Ui を実装するため、`IWPFAddInView.GetAddInUI` に関連付けられているアドインビューのメソッドは、<xref:System.Windows.FrameworkElement> 型の値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ba4-119">Because the add-in implements the UIs it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="37ba4-120">次のコードは、コントラクトのアドイン ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="37ba4-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="37ba4-121">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="37ba4-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="37ba4-122">コントラクトメソッドは @no__t 0 を返しますが、アドインは、アドインビューで指定されているように <xref:System.Windows.FrameworkElement> を返します。</span><span class="sxs-lookup"><span data-stu-id="37ba4-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="37ba4-123">したがって、分離境界を越える前に、<xref:System.Windows.FrameworkElement> を <xref:System.AddIn.Contract.INativeHandleContract> に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ba4-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="37ba4-124">この作業は、次のコードに示すように <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> を呼び出すことによってアドイン側アダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="37ba4-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="37ba4-125">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="37ba4-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="37ba4-126">ホストアプリケーションには @no__t 0 が表示されるため、`IWPFAddInHostView.GetAddInUI` に関連付けられているホストビューのメソッドは <xref:System.Windows.FrameworkElement> 型の値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ba4-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="37ba4-127">次のコードは、コントラクトのホスト ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="37ba4-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="37ba4-128">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="37ba4-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="37ba4-129">コントラクトメソッドは @no__t 0 を返しますが、ホストアプリケーションでは、(ホストビューで指定されているように) <xref:System.Windows.FrameworkElement> が必要です。</span><span class="sxs-lookup"><span data-stu-id="37ba4-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="37ba4-130">したがって、分離境界を越えた後、<xref:System.AddIn.Contract.INativeHandleContract> を <xref:System.Windows.FrameworkElement> に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ba4-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="37ba4-131">この作業は、次のコードに示すように、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> を呼び出すことによってホスト側アダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="37ba4-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="37ba4-132">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="37ba4-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="37ba4-133">アドイン側のアダプターとアドインビューを作成した場合、アドイン (`WPFAddIn1.AddIn`) は、@no__t 2 のオブジェクト (この例では @no__t 3) を返すために `IWPFAddInView.GetAddInUI` メソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ba4-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="37ba4-134">@No__t-0、`AddInUI` の実装は、次のコードによって示されます。</span><span class="sxs-lookup"><span data-stu-id="37ba4-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="37ba4-135">アドインによる `IWPFAddInView.GetAddInUI` の実装では、次のコードに示すように、単に `AddInUI` の新しいインスタンスを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="37ba4-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="37ba4-136">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="37ba4-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="37ba4-137">ホスト側のアダプターとホストビューを作成すると、ホストアプリケーションは .NET Framework アドインモデルを使用してパイプラインを開き、アドインのホストビューを取得して、`IWPFAddInHostView.GetAddInUI` メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="37ba4-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="37ba4-138">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="37ba4-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="37ba4-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ba4-139">See also</span></span>

- <span data-ttu-id="37ba4-140">[アドインおよび拡張機能](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="37ba4-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="37ba4-141">WPF アドインの概要</span><span class="sxs-lookup"><span data-stu-id="37ba4-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
