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
ms.openlocfilehash: ccc918a9e8ca5e09cfebf1724519e8e6f9d1d32e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627351"
---
# <a name="how-to-create-an-add-in-that-returns-a-ui"></a><span data-ttu-id="27e79-102">方法: UI を返すアドインを作成する</span><span class="sxs-lookup"><span data-stu-id="27e79-102">How to: Create an Add-In That Returns a UI</span></span>
<span data-ttu-id="27e79-103">この例では、スタンドアロンの WPF アプリケーションのホストに Windows Presentation Foundation (WPF) を返すアドインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="27e79-103">This example shows how to create an add-in that returns a Windows Presentation Foundation (WPF) to a host WPF standalone application.</span></span>  
  
 <span data-ttu-id="27e79-104">アドインには、WPF ユーザー コントロールの UI を返します。</span><span class="sxs-lookup"><span data-stu-id="27e79-104">The add-in returns a UI that is a WPF user control.</span></span> <span data-ttu-id="27e79-105">ユーザー コントロールの中身は 1 つのボタンであり、クリックすると、メッセージ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="27e79-105">The content of the user control is a single button that, when clicked, displays a message box.</span></span> <span data-ttu-id="27e79-106">スタンドアロンの WPF アプリケーションでは、アドインをホストし、アプリケーションのメイン ウィンドウの内容として (アドインによって返される) ユーザー コントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="27e79-106">The WPF standalone application hosts the add-in and displays the user control (returned by the add-in) as the content of the main application window.</span></span>  
  
 <span data-ttu-id="27e79-107">**必須コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="27e79-107">**Prerequisites**</span></span>  
  
 <span data-ttu-id="27e79-108">この例では、このシナリオを有効にする、.NET Framework アドイン モデルを WPF 拡張を強調表示し、前提条件は次。</span><span class="sxs-lookup"><span data-stu-id="27e79-108">This example highlights the WPF extensions to the .NET Framework add-in model that enable this scenario, and assumes the following:</span></span>  
  
- <span data-ttu-id="27e79-109">.NET Framework アドイン モデルのパイプライン、アドイン、およびホストの開発を含むナレッジです。</span><span class="sxs-lookup"><span data-stu-id="27e79-109">Knowledge of the .NET Framework add-in model, including pipeline, add-in, and host development.</span></span> <span data-ttu-id="27e79-110">これらの概念に慣れていない場合は、次を参照してください。[アドインおよび拡張](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))します。</span><span class="sxs-lookup"><span data-stu-id="27e79-110">If you are unfamiliar with these concepts, see [Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).</span></span> <span data-ttu-id="27e79-111">パイプライン、アドイン、およびホスト アプリケーションの実装を示すチュートリアルについては、次を参照してください。[チュートリアル。拡張可能なアプリケーションを作成する](../../add-ins/walkthrough-create-extensible-app.md)します。</span><span class="sxs-lookup"><span data-stu-id="27e79-111">For a tutorial that demonstrates the implementation of a pipeline, an add-in, and a host application, see [Walkthrough: Creating an Extensible Application](../../add-ins/walkthrough-create-extensible-app.md).</span></span>  
  
- <span data-ttu-id="27e79-112">WPF の拡張機能を .NET Framework アドイン モデルはこちらのサポート技術情報:[WPF アドインの概要](wpf-add-ins-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="27e79-112">Knowledge of the WPF extensions to the .NET Framework add-in model, which can be found here: [WPF Add-Ins Overview](wpf-add-ins-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27e79-113">例</span><span class="sxs-lookup"><span data-stu-id="27e79-113">Example</span></span>  
 <span data-ttu-id="27e79-114">WPF UI を返すアドインを作成するには、各パイプライン セグメント、アドイン、およびホスト アプリケーションの特定のコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="27e79-114">To create an add-in that returns a WPF UI requires specific code for each pipeline segment, the add-in, and the host application.</span></span>  

<a name="Contract"></a>   
## <a name="implementing-the-contract-pipeline-segment"></a><span data-ttu-id="27e79-115">コントラクト パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="27e79-115">Implementing the Contract Pipeline Segment</span></span>  
 <span data-ttu-id="27e79-116">メソッドは、UI を返すためのコントラクトを定義する必要があり、その戻り値型でなければなりません<xref:System.AddIn.Contract.INativeHandleContract>します。</span><span class="sxs-lookup"><span data-stu-id="27e79-116">A method must be defined by the contract for returning a UI, and its return value must be of type <xref:System.AddIn.Contract.INativeHandleContract>.</span></span> <span data-ttu-id="27e79-117">これを示します、`GetAddInUI`のメソッド、`IWPFAddInContract`次のコード コントラクトします。</span><span class="sxs-lookup"><span data-stu-id="27e79-117">This is demonstrated by the `GetAddInUI` method of the `IWPFAddInContract` contract in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Contracts/IWPFAddInContract.cs#contractcode)]
 [!code-vb[SimpleAddInReturnsAUISample#ContractCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Contracts/IWPFAddInContract.vb#contractcode)]  
  
<a name="AddInView"></a>   
## <a name="implementing-the-add-in-view-pipeline-segment"></a><span data-ttu-id="27e79-118">アドイン ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="27e79-118">Implementing the Add-In View Pipeline Segment</span></span>  
 <span data-ttu-id="27e79-119">アドインを実装しているため、[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]のサブクラスとして提供<xref:System.Windows.FrameworkElement>、メソッドは、アドイン ビューに関連付けられた`IWPFAddInView.GetAddInUI`型の値を返す必要があります<xref:System.Windows.FrameworkElement>します。</span><span class="sxs-lookup"><span data-stu-id="27e79-119">Because the add-in implements the [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] it provides as subclasses of <xref:System.Windows.FrameworkElement>, the method on the add-in view that correlates to `IWPFAddInView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="27e79-120">次のコードは、コントラクトのアドイン ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="27e79-120">The following code shows the add-in view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInViews/IWPFAddInView.cs#addinviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInViews/IWPFAddInView.vb#addinviewcode)]  
  
<a name="AddInSideAdapter"></a>   
## <a name="implementing-the-add-in-side-adapter-pipeline-segment"></a><span data-ttu-id="27e79-121">アドイン側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="27e79-121">Implementing the Add-In-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="27e79-122">コントラクト メソッドを返します、 <xref:System.AddIn.Contract.INativeHandleContract>、アドインを返しますが、 <xref:System.Windows.FrameworkElement> (アドイン ビューによって、指定した)。</span><span class="sxs-lookup"><span data-stu-id="27e79-122">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the add-in returns a <xref:System.Windows.FrameworkElement> (as specified by the add-in view).</span></span> <span data-ttu-id="27e79-123">その結果、<xref:System.Windows.FrameworkElement>に変換する必要があります、<xref:System.AddIn.Contract.INativeHandleContract>分離境界を越える前にします。</span><span class="sxs-lookup"><span data-stu-id="27e79-123">Consequently, the <xref:System.Windows.FrameworkElement> must be converted to an <xref:System.AddIn.Contract.INativeHandleContract> before crossing the isolation boundary.</span></span> <span data-ttu-id="27e79-124">呼び出して追加アドイン側アダプターによってこの作業が実行される<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="27e79-124">This work is performed by the add-in-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.cs#addinsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/AddInSideAdapters/WPFAddIn_ViewToContractAddInSideAdapter.vb#addinsideadaptercode)]  
  
<a name="HostView"></a>   
## <a name="implementing-the-host-view-pipeline-segment"></a><span data-ttu-id="27e79-125">ホスト ビュー パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="27e79-125">Implementing the Host View Pipeline Segment</span></span>  
 <span data-ttu-id="27e79-126">ホスト アプリケーションが表示されるため、 <xref:System.Windows.FrameworkElement>、メソッドは、ホスト ビューに関連付けられた`IWPFAddInHostView.GetAddInUI`型の値を返す必要があります<xref:System.Windows.FrameworkElement>します。</span><span class="sxs-lookup"><span data-stu-id="27e79-126">Because the host application will display a <xref:System.Windows.FrameworkElement>, the method on the host view that correlates to `IWPFAddInHostView.GetAddInUI` must return a value of type <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="27e79-127">次のコードは、コントラクトのホスト ビューがインターフェイスとして実装されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="27e79-127">The following code shows the host view of the contract, implemented as an interface.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostViews/IWPFAddInHostView.cs#hostviewcode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostViewCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostViews/IWPFAddInHostView.vb#hostviewcode)]  
  
<a name="HostSideAdapter"></a>   
## <a name="implementing-the-host-side-adapter-pipeline-segment"></a><span data-ttu-id="27e79-128">ホスト側アダプター パイプライン セグメントの実装</span><span class="sxs-lookup"><span data-stu-id="27e79-128">Implementing the Host-Side Adapter Pipeline Segment</span></span>  
 <span data-ttu-id="27e79-129">コントラクト メソッドを返します、 <xref:System.AddIn.Contract.INativeHandleContract>、ホスト アプリケーションが必要ですが、 <xref:System.Windows.FrameworkElement> (ホスト ビューによって、指定した)。</span><span class="sxs-lookup"><span data-stu-id="27e79-129">The contract method returns an <xref:System.AddIn.Contract.INativeHandleContract>, but the host application expects a <xref:System.Windows.FrameworkElement> (as specified by the host view).</span></span> <span data-ttu-id="27e79-130">その結果、<xref:System.AddIn.Contract.INativeHandleContract>に変換する必要があります、<xref:System.Windows.FrameworkElement>分離境界を越えた後。</span><span class="sxs-lookup"><span data-stu-id="27e79-130">Consequently, the <xref:System.AddIn.Contract.INativeHandleContract> must be converted to a <xref:System.Windows.FrameworkElement> after crossing the isolation boundary.</span></span> <span data-ttu-id="27e79-131">呼び出して、ホスト側アダプターによってこの作業が実行される<xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="27e79-131">This work is performed by the host-side adapter by calling <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, as shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.cs#hostsideadaptercode)]
 [!code-vb[SimpleAddInReturnsAUISample#HostSideAdapterCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/HostSideAdapters/WPFAddIn_ContractToViewHostSideAdapter.vb#hostsideadaptercode)]  
  
<a name="AddIn"></a>   
## <a name="implementing-the-add-in"></a><span data-ttu-id="27e79-132">アドインの実装</span><span class="sxs-lookup"><span data-stu-id="27e79-132">Implementing the Add-In</span></span>  
 <span data-ttu-id="27e79-133">追加アドイン側アダプターとアドイン ビューが作成されると、アドイン (`WPFAddIn1.AddIn`) を実装する必要があります、`IWPFAddInView.GetAddInUI`を返すメソッドを<xref:System.Windows.FrameworkElement>オブジェクト (、<xref:System.Windows.Controls.UserControl>この例では)。</span><span class="sxs-lookup"><span data-stu-id="27e79-133">With the add-in-side adapter and add-in view created, the add-in (`WPFAddIn1.AddIn`) must implement the `IWPFAddInView.GetAddInUI` method to return a <xref:System.Windows.FrameworkElement> object (a <xref:System.Windows.Controls.UserControl> in this example).</span></span> <span data-ttu-id="27e79-134">実装、 <xref:System.Windows.Controls.UserControl>、 `AddInUI`、次のコードで示されています。</span><span class="sxs-lookup"><span data-stu-id="27e79-134">The implementation of the <xref:System.Windows.Controls.UserControl>, `AddInUI`, is shown by the following code.</span></span>  
  
 [!code-xaml[SimpleAddInReturnsAUISample#AddInUIMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml#addinuimarkup)]  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddInUI.xaml.cs#addinuicodebehind)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInUICodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddInUI.xaml.vb#addinuicodebehind)]  
  
 <span data-ttu-id="27e79-135">実装、 `IWPFAddInView.GetAddInUI` 、アドインによって単純にする必要がありますの新しいインスタンスを返す`AddInUI`を次のコードに示すように、します。</span><span class="sxs-lookup"><span data-stu-id="27e79-135">The implementation of the `IWPFAddInView.GetAddInUI` by the add-in simply needs to return a new instance of `AddInUI`, as shown by the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/WPFAddIn1/AddIn.cs#addincode)]
 [!code-vb[SimpleAddInReturnsAUISample#AddInCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/WPFAddIn1/AddIn.vb#addincode)]  
  
<a name="App"></a>   
## <a name="implementing-the-host-application"></a><span data-ttu-id="27e79-136">ホスト アプリケーションの実装</span><span class="sxs-lookup"><span data-stu-id="27e79-136">Implementing the Host Application</span></span>  
 <span data-ttu-id="27e79-137">ホスト側アダプターとホスト ビューの作成、ホスト アプリケーションは、パイプラインを開き、アドイン、および呼び出しのホスト ビューを取得する .NET Framework アドイン モデルを使用できます、`IWPFAddInHostView.GetAddInUI`メソッド。</span><span class="sxs-lookup"><span data-stu-id="27e79-137">With the host-side adapter and host view created, the host application can use the .NET Framework add-in model to open the pipeline, acquire a host view of the add-in, and call the `IWPFAddInHostView.GetAddInUI` method.</span></span> <span data-ttu-id="27e79-138">これらの手順を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="27e79-138">These steps are shown in the following code.</span></span>  
  
 [!code-csharp[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/CSharp/Host/MainWindow.xaml.cs#getuicode)]
 [!code-vb[SimpleAddInReturnsAUISample#GetUICode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleAddInReturnsAUISample/VisualBasic/Host/MainWindow.xaml.vb#getuicode)]  
  
## <a name="see-also"></a><span data-ttu-id="27e79-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="27e79-139">See also</span></span>

- <span data-ttu-id="27e79-140">[アドインおよび拡張機能](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="27e79-140">[Add-ins and Extensibility](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))</span></span>
- [<span data-ttu-id="27e79-141">WPF のアドインの概要</span><span class="sxs-lookup"><span data-stu-id="27e79-141">WPF Add-Ins Overview</span></span>](wpf-add-ins-overview.md)
