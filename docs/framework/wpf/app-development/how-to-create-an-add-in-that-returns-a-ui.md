---
title: '方法 : UI を返すアドインを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating an add-in that returns a UI [WPF]
- implementing add-in pipeline segments [WPF]
- add-in [WPF], returns a UI
ms.assetid: 57f274b7-4c66-4b72-92eb-81939a393776
ms.openlocfilehash: f8323fe35555a56d39c1efed649c2aa3fcf17e43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174590"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="29fb2-102">方法 : UI を返すアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="29fb2-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="29fb2-103">この例では、Windows プレゼンテーション ファンデーション (WPF) をホスト WPF スタンドアロン アプリケーションに返すアドインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="29fb2-104">アドインは、WPF ユーザー コントロールである UI を返します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="29fb2-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="29fb2-106">WPF スタンドアロン アプリケーションはアドインをホストし、ユーザー コントロール (アドインによって返される) をメイン アプリケーション ウィンドウのコンテンツとして表示します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="29fb2-107">**前提条件**</span><span class="sxs-lookup"><span data-stu-id="29fb2-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="29fb2-108">この例では、このシナリオを有効にする .NET Framework アドイン モデルの WPF 拡張機能を強調表示し、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="29fb2-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="29fb2-109">パイプライン、アドイン、ホスト開発など、.NET Framework アドイン モデルに関する知識。</span><span class="sxs-lookup"><span data-stu-id="29fb2-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="29fb2-110">これらの概念に詳しくない場合は、「[アドインと機能拡張](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fb2-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="29fb2-111">パイプライン、アドイン、およびホスト アプリケーションの実装を示すチュートリアルについては、「[チュートリアル : 拡張アプリケーションの作成](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fb2-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](/previous-versions/dotnet/netframework-4.0/bb788290(v%3dvs.100)).</span></span>  
  
- <span data-ttu-id="29fb2-112">.NET Framework アドイン モデルに対する WPF 拡張機能に関する知識は次[のとおりです。](wpf-add-ins-overview.md)</span><span class="sxs-lookup"><span data-stu-id="29fb2-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29fb2-113">例</span><span class="sxs-lookup"><span data-stu-id="29fb2-113">Example</span></span>  
 <span data-ttu-id="29fb2-114">WPF UI を返すアドインを作成するには、パイプライン セグメント、アドイン、およびホスト アプリケーションごとに特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="29fb2-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="29fb2-115">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="29fb2-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="29fb2-116">メソッドは、UI を返すコントラクトによって定義され、その戻り値は型<xref:System.AddIn.Contract.INativeHandleContract>である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fb2-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="29fb2-117">これは、次のコード`GetAddInUI`でコントラクトの`IWPFAddInContract`メソッドによって示されています。</span><span class="sxs-lookup"><span data-stu-id="29fb2-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="29fb2-118">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="29fb2-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="29fb2-119">アドインは、 のサブクラスとして提供される UI<xref:System.Windows.FrameworkElement>を実装しているため、関連付`IWPFAddInView.GetAddInUI`けるアドイン ビューのメソッドは type の値を返す<xref:System.Windows.FrameworkElement>必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fb2-119">Because the add-in implements the UIs it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="29fb2-120">次のコードは、コントラクトのアドイン ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="29fb2-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="29fb2-121">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="29fb2-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="29fb2-122">コントラクト メソッドは<xref:System.AddIn.Contract.INativeHandleContract>を返しますが、アドインは<xref:System.Windows.FrameworkElement>(アドイン ビューで指定された) を返します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="29fb2-123">したがって、分離境界<xref:System.Windows.FrameworkElement>を越える前に<xref:System.AddIn.Contract.INativeHandleContract>に 変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fb2-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="29fb2-124">この作業は、次のコードに示すように、 を呼<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>び出すことによってアドイン側アダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="29fb2-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="29fb2-125">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="29fb2-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="29fb2-126">ホスト アプリケーションには<xref:System.Windows.FrameworkElement>、 を表示するため、関連付けるホスト ビューのメソッド`IWPFAddInHostView.GetAddInUI`は type の<xref:System.Windows.FrameworkElement>値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fb2-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="29fb2-127">次のコードは、コントラクトのホスト ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="29fb2-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="29fb2-128">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="29fb2-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="29fb2-129">コントラクト メソッドは<xref:System.AddIn.Contract.INativeHandleContract>を返しますが、ホスト<xref:System.Windows.FrameworkElement>アプリケーションはホスト ビューで指定された を要求します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="29fb2-130">したがって、分離境界<xref:System.AddIn.Contract.INativeHandleContract>を越えた後に<xref:System.Windows.FrameworkElement>に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fb2-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="29fb2-131">この処理は、次のコードに示すように、<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>を呼び出すことによってホスト側アダプターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="29fb2-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>
## <a name="implementing-the-add-in"></a><span data-ttu-id="29fb2-132">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="29fb2-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="29fb2-133">アドイン側`WPFAddIn1.AddIn`のアダプタとアドイン ビューが作成された場合、アドイン ( ) は`IWPFAddInView.GetAddInUI`<xref:System.Windows.FrameworkElement>オブジェクトを返すメソッドを実装する必要があります<xref:System.Windows.Controls.UserControl>(この例では a)。</span><span class="sxs-lookup"><span data-stu-id="29fb2-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="29fb2-134"><xref:System.Windows.Controls.UserControl>の`AddInUI`実装は、次のコードで示します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="29fb2-135">`IWPFAddInView.GetAddInUI`アドインによる の実装では、次のコードに示すように、 の`AddInUI`新しいインスタンスを返すだけです。</span><span class="sxs-lookup"><span data-stu-id="29fb2-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>
## <a name="implementing-the-host-application"></a><span data-ttu-id="29fb2-136">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="29fb2-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="29fb2-137">ホスト側のアダプターとホスト ビューを作成すると、ホスト アプリケーションは 、.NET Framework アドイン モデルを使用してパイプラインを開き、アドインのホスト ビューを取得し`IWPFAddInHostView.GetAddInUI`、メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="29fb2-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="29fb2-138">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="29fb2-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="29fb2-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="29fb2-139">See also</span></span>

- <span data-ttu-id="29fb2-140">[アドインと拡張性](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="29fb2-140">[Add-ins and Extensibility](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="29fb2-141">WPF アドインの概要</span><span class="sxs-lookup"><span data-stu-id="29fb2-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
