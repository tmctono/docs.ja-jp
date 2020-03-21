---
title: Windows Workflow Foundation の機能仕様
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: 11bde5edea44f09ef1a5658cdf0e20ec1349c84b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182923"
---
# <a name="windows-workflow-foundation-feature-specifics"></a><span data-ttu-id="10da0-102">Windows Workflow Foundation の機能仕様</span><span class="sxs-lookup"><span data-stu-id="10da0-102">Windows Workflow Foundation Feature Specifics</span></span>

<span data-ttu-id="10da0-103">.NET Framework 4 では、Windows ワークフローファウンデーションに多数の機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="10da0-103">.NET Framework 4 adds a number of features to Windows Workflow Foundation.</span></span> <span data-ttu-id="10da0-104">このドキュメントでは、いくつかの新機能について説明し、役に立つ可能性のあるシナリオの詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="10da0-104">This document describes a number of the new features, and gives details about scenarios in which they may be useful.</span></span>

## <a name="messaging-activities"></a><span data-ttu-id="10da0-105">メッセージング アクティビティ</span><span class="sxs-lookup"><span data-stu-id="10da0-105">Messaging Activities</span></span>

<span data-ttu-id="10da0-106">メッセージング アクティビティ (<xref:System.ServiceModel.Activities.Receive> <xref:System.ServiceModel.Activities.SendReply>、 <xref:System.ServiceModel.Activities.Send> <xref:System.ServiceModel.Activities.ReceiveReply>、 、 ) は、ワークフローから WCF メッセージを送受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-106">The messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) are used to send and receive WCF messages from your workflow.</span></span> <span data-ttu-id="10da0-107"><xref:System.ServiceModel.Activities.Receive>アクティビティ<xref:System.ServiceModel.Activities.SendReply>は、標準の WCF Web サービスと同様に WSDL を介して公開される Windows 通信基盤 (WCF) サービス操作を形成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-107"><xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities are used to form a Windows Communication Foundation (WCF) service operation that is exposed via WSDL just like standard WCF web services.</span></span> <span data-ttu-id="10da0-108"><xref:System.ServiceModel.Activities.Send>WCF<xref:System.ServiceModel.Activities.ReceiveReply><xref:System.ServiceModel.ChannelFactory>に似た Web サービスを使用するために使用されます。事前に構成されたアクティビティを生成するワークフロー ファンデーションにも、**サービス参照の追加**エクスペリエンスが存在します。</span><span class="sxs-lookup"><span data-stu-id="10da0-108"><xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> are used to consume a web service similar to a WCF <xref:System.ServiceModel.ChannelFactory>; an **Add Service Reference** experience also exists for Workflow Foundation that generates pre-configured activities.</span></span>

### <a name="getting-started-with-messaging-activities"></a><span data-ttu-id="10da0-109">メッセージング アクティビティの概要</span><span class="sxs-lookup"><span data-stu-id="10da0-109">Getting Started with Messaging Activities</span></span>

- <span data-ttu-id="10da0-110">Visual Studio 2012 で、WCF ワークフロー サービス アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-110">In Visual Studio 2012, create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="10da0-111"><xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> のペアがキャンバスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-111">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas.</span></span>

- <span data-ttu-id="10da0-112">プロジェクトを右クリックし、[**サービス参照の追加 ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="10da0-112">Right-click on the project and select **Add Service Reference**.</span></span> <span data-ttu-id="10da0-113">既存の Web サービス WSDL をポイントし **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10da0-113">Point to an existing web service WSDL and click **OK**.</span></span> <span data-ttu-id="10da0-114">生成されたアクティビティ ( を使用して実装された<xref:System.ServiceModel.Activities.Send><xref:System.ServiceModel.Activities.ReceiveReply>、 を使用して ) をツールボックスに表示するプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="10da0-114">Build your project to show the generated activities (implemented using <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply>) in your toolbox.</span></span>

- [<span data-ttu-id="10da0-115">ワークフロー サービスのドキュメント</span><span class="sxs-lookup"><span data-stu-id="10da0-115">Workflow services documentation</span></span>](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a><span data-ttu-id="10da0-116">メッセージング アクティビティのシナリオ例</span><span class="sxs-lookup"><span data-stu-id="10da0-116">Messaging Activities Example Scenario</span></span>

<span data-ttu-id="10da0-117">サービス`BestPriceFinder`は、特定のルートの最高の航空券価格を見つけるために、複数の航空会社のサービスに呼び出します。</span><span class="sxs-lookup"><span data-stu-id="10da0-117">A `BestPriceFinder` service calls out to multiple airline services to find the best ticket price for a particular route.</span></span> <span data-ttu-id="10da0-118">このシナリオを実装するには、メッセージ アクティビティを使用して価格要求を受信し、バックエンド サービスから価格を取得し、価格要求に最適な価格で返信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-118">Implementing this scenario would require you to use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span> <span data-ttu-id="10da0-119">また、最適価格を計算するためのビジネス ロジックを作成するには、他のアウトオブボックス アクティビティを使用する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="10da0-119">It would also require you to use other out-of-box activities to create the business logic for calculating the best price.</span></span>

## <a name="workflowservicehost"></a><span data-ttu-id="10da0-120">WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="10da0-120">WorkflowServiceHost</span></span>

<span data-ttu-id="10da0-121"><xref:System.ServiceModel.WorkflowServiceHost>は、複数のインスタンス、構成、および WCF メッセージングをサポートする、通常のワークフロー ホストです (ただし、ワークフローは、ホストされるためにメッセージングを使用する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="10da0-121">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren't required to use messaging in order to be hosted).</span></span> <span data-ttu-id="10da0-122">また、一連のサービス動作を介して永続性、追跡、およびインスタンス コントロールを統合します。</span><span class="sxs-lookup"><span data-stu-id="10da0-122">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span> <span data-ttu-id="10da0-123">WCF<xref:System.ServiceModel.ServiceHost>と同様に<xref:System.ServiceModel.WorkflowServiceHost>、コンソール/WinForms/WPF アプリケーションまたは Windows サービス、または IIS または WAS の Web ホスト (.xamlx ファイルとして) で自己ホストできます。</span><span class="sxs-lookup"><span data-stu-id="10da0-123">Just like WCF's <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in a console/WinForms/WPF application or Windows service, or web-hosted (as a .xamlx file) in IIS or WAS.</span></span>

### <a name="getting-started-with-workflow-service-host"></a><span data-ttu-id="10da0-124">ワークフロー サービス ホストの概要</span><span class="sxs-lookup"><span data-stu-id="10da0-124">Getting Started with Workflow Service Host</span></span>

- <span data-ttu-id="10da0-125">Visual Studio 2010 で、WCF ワークフロー サービス アプリケーション プロジェクトを作成する:<xref:System.ServiceModel.WorkflowServiceHost>このプロジェクトは、Web ホスト環境で使用するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-125">In Visual Studio 2010, create a WCF Workflow Service Application project: this project will be set up to use <xref:System.ServiceModel.WorkflowServiceHost> in a web-host environment.</span></span>

- <span data-ttu-id="10da0-126">非メッセージング ワークフローをホストするには、メッセージに基づいてインスタンスを作成するカスタム <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> を追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-126">In order to host a non-messaging workflow, add a custom <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> that will create the instance based on a message.</span></span>

- <span data-ttu-id="10da0-127">ワークフロー インスタンスは、<xref:System.ServiceModel.Activities.WorkflowControlEndpoint> を <xref:System.ServiceModel.WorkflowServiceHost> に追加し、<xref:System.ServiceModel.Activities.WorkflowControlClient> を使用することで制御 (中断や終了など) できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-127">Workflow instances can be controlled (e.g. suspended or terminated) by adding a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> to the <xref:System.ServiceModel.WorkflowServiceHost> and then using a <xref:System.ServiceModel.Activities.WorkflowControlClient>.</span></span>

- <span data-ttu-id="10da0-128"><xref:System.ServiceModel.WorkflowServiceHost> のサンプルは次のセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="10da0-128">Samples for the <xref:System.ServiceModel.WorkflowServiceHost> can be found in the following sections:</span></span>

  - [<span data-ttu-id="10da0-129">実行</span><span class="sxs-lookup"><span data-stu-id="10da0-129">Execution</span></span>](./samples/execution.md)

  - <span data-ttu-id="10da0-130">アプリケーション:[中断されたインスタンス管理](./samples/suspended-instance-management.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-130">Application: [Suspended Instance Management](./samples/suspended-instance-management.md)</span></span>

- [<span data-ttu-id="10da0-131">ワークフロー サービスのホスティングの概要</span><span class="sxs-lookup"><span data-stu-id="10da0-131">Hosting Workflow services overview</span></span>](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a><span data-ttu-id="10da0-132">WorkflowServiceHost のシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-132">WorkflowServiceHost Scenario</span></span>

<span data-ttu-id="10da0-133">BestPriceFinderサービスは、特定のルートに最適な航空券価格を見つけるために、複数の航空会社のサービスに呼び出します。</span><span class="sxs-lookup"><span data-stu-id="10da0-133">A BestPriceFinder service calls out to multiple airline services to find the best ticket price for a particular route.</span></span> <span data-ttu-id="10da0-134">このシナリオを実装するには、 で<xref:System.ServiceModel.WorkflowServiceHost>ワークフローをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-134">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="10da0-135">また、メッセージ アクティビティを使用して価格要求を受信し、バックエンド サービスから価格を取得し、価格要求に最適な価格で返信します。</span><span class="sxs-lookup"><span data-stu-id="10da0-135">It would also use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span>

## <a name="correlation"></a><span data-ttu-id="10da0-136">Correlation</span><span class="sxs-lookup"><span data-stu-id="10da0-136">Correlation</span></span>

<span data-ttu-id="10da0-137">相関関係は次の 2 つのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="10da0-137">A correlation is one of two things:</span></span>

- <span data-ttu-id="10da0-138">メッセージをグループ化する方法。つまり、要求メッセージとその応答の関係。</span><span class="sxs-lookup"><span data-stu-id="10da0-138">A way of grouping messages together; that is, the relationship between a request message and its reply.</span></span>

- <span data-ttu-id="10da0-139">サービス インスタンスにデータの一部をマッピングする方法。</span><span class="sxs-lookup"><span data-stu-id="10da0-139">A way of mapping a piece of data to a service instance</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-140">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-140">Getting Started</span></span>

- <span data-ttu-id="10da0-141">相関を開始するには、Visual Studio で新規プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-141">To get started with correlation, create a new project in Visual Studio.</span></span> <span data-ttu-id="10da0-142"><xref:System.ServiceModel.Activities.CorrelationHandle> 型の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-142">Create a variable of type <xref:System.ServiceModel.Activities.CorrelationHandle>.</span></span>

- <span data-ttu-id="10da0-143">メッセージのグループ化に使用する相関関係の例は、メッセージをグループ化する要求/応答の相関関係です。</span><span class="sxs-lookup"><span data-stu-id="10da0-143">An example of correlation used to group messages together is a Request-Reply correlation that groups messages together.</span></span>

  - <span data-ttu-id="10da0-144"><xref:System.ServiceModel.Activities.Receive>アクティビティで、プロパティを<xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>クリックし、上記の最初<xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>の手順で作成した CorrelationHandle を使用してを追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-144">On a <xref:System.ServiceModel.Activities.Receive> activity, click on the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> property and add a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> using the CorrelationHandle created in the first step above.</span></span>

  - <span data-ttu-id="10da0-145">アクティビティを<xref:System.ServiceModel.Activities.SendReply>作成するには、 を右クリック<xref:System.ServiceModel.Activities.Receive>し、[SendReply の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10da0-145">Create a <xref:System.ServiceModel.Activities.SendReply> activity by right-clicking on the <xref:System.ServiceModel.Activities.Receive> and clicking "Create SendReply".</span></span> <span data-ttu-id="10da0-146">これをワークフローの <xref:System.ServiceModel.Activities.Receive> アクティビティの後に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="10da0-146">Paste it into your workflow after the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

- <span data-ttu-id="10da0-147">データの一部をサービス インスタンスにマッピングする例は、データの一部 (オーダー ID など) を特定のワークフロー インスタンスにマップするコンテンツ ベースの相関関係です。</span><span class="sxs-lookup"><span data-stu-id="10da0-147">An example of mapping a piece of data to a service instance is content-based correlation which maps a piece of data (for example, an order ID) to a particular workflow instance.</span></span>

  - <span data-ttu-id="10da0-148">任意のメッセージング アクティビティで、`CorrelationInitializers` プロパティをクリックし、上記で作成した <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 変数を使用して <xref:System.ServiceModel.Activities.CorrelationHandle> を追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-148">On any messaging activity, click on the `CorrelationInitializers` property and add a <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> using the <xref:System.ServiceModel.Activities.CorrelationHandle> variable created above.</span></span> <span data-ttu-id="10da0-149">ドロップダウン メニューで、メッセージ上の目的のプロパティ (OrderID など) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="10da0-149">Double-click on the desired property on the message (e.g. OrderID) from the drop-down menu.</span></span> <span data-ttu-id="10da0-150">`CorrelatesWith` プロパティを上記で使用した <xref:System.ServiceModel.Activities.CorrelationHandle> 変数に設定します。</span><span class="sxs-lookup"><span data-stu-id="10da0-150">Set the `CorrelatesWith` property to the <xref:System.ServiceModel.Activities.CorrelationHandle> variable used above.</span></span>

- [<span data-ttu-id="10da0-151">相関関係の概念説明ドキュメント</span><span class="sxs-lookup"><span data-stu-id="10da0-151">Correlation Conceptual Documentation</span></span>](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a><span data-ttu-id="10da0-152">相関関係のシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-152">Correlation Scenario</span></span>

<span data-ttu-id="10da0-153">注文処理ワークフローは、新しい注文の作成を処理し、処理中の既存の注文を更新するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-153">An order-processing workflow is used to handle new order creation and updating existing orders that are in process.</span></span> <span data-ttu-id="10da0-154">このシナリオを実装するには、ワークフローをで<xref:System.ServiceModel.WorkflowServiceHost>ホストし、メッセージング アクティビティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-154">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost> and use the messaging activities.</span></span> <span data-ttu-id="10da0-155">また、正しいワークフロー`orderId`に対して確実に更新を行うために、 に基づく相関関係が必要になります。</span><span class="sxs-lookup"><span data-stu-id="10da0-155">It would also require correlation based on the `orderId` to ensure that updates are made to the correct workflow.</span></span>

## <a name="simplified-configuration"></a><span data-ttu-id="10da0-156">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="10da0-156">Simplified Configuration</span></span>

<span data-ttu-id="10da0-157">WCF 構成スキーマは複雑で、多くの機能を見つけるのが難しいユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="10da0-157">The WCF configuration schema is complex and provides users with many hard to find features.</span></span> <span data-ttu-id="10da0-158">では[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]、WCF ユーザーが次の機能を使用してサービスを構成する手助けに重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="10da0-158">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], we have focused on helping WCF users configure their services with the following features:</span></span>

- <span data-ttu-id="10da0-159">サービスごとの明示的な構成の必要性をなくします。</span><span class="sxs-lookup"><span data-stu-id="10da0-159">Removing the need for explicit per-service configuration.</span></span> <span data-ttu-id="10da0-160">サービスのサービス>要素\<を構成せず、サービスがプログラムでエンドポイントを定義しない場合、エンドポイントのセットはサービスベース アドレスごとに 1 つずつ、サービスによって実装されたコントラクトごとに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-160">If you do not configure any \<service> elements for your service, and your service does not define programmatically any endpoint, then a set of endpoints will be automatically added to your service, one per service base address and per contract implemented by your service.</span></span>

- <span data-ttu-id="10da0-161">明示的な構成のないサービスに適用される WCF バインディングおよび動作の既定値をユーザーが定義できるようにします。</span><span class="sxs-lookup"><span data-stu-id="10da0-161">Enables the user to define default values for WCF bindings and behaviors, which will be applied to services with no explicit configuration.</span></span>

- <span data-ttu-id="10da0-162">標準のエンドポイントは、事前に構成された再利用可能なエンドポイントを定義します。このエンドポイントは、1 つ以上のエンドポイント プロパティ (アドレス、バインド、およびコントラクト) に対して固定値を持ち、カスタム プロパティを定義できるようにします。</span><span class="sxs-lookup"><span data-stu-id="10da0-162">Standard endpoints define reusable preconfigured endpoints, which have fixed values for one or more of the endpoint properties (address, binding and contract), and allow defining custom properties.</span></span>

- <span data-ttu-id="10da0-163">最後に、 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> WCF クライアント構成の集中管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="10da0-163">Finally, the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows you to do central management of WCF client configuration, useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-164">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-164">Getting Started</span></span>

- <span data-ttu-id="10da0-165">[WCF 4.0 開発者ガイド](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="10da0-165">[A Developer's Guide to WCF 4.0](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))</span></span>

- [<span data-ttu-id="10da0-166">構成チャネル ファクトリ</span><span class="sxs-lookup"><span data-stu-id="10da0-166">Configuration Channel Factory</span></span>](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [<span data-ttu-id="10da0-167">標準エンドポイント要素</span><span class="sxs-lookup"><span data-stu-id="10da0-167">Standard Endpoint Element</span></span>](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [<span data-ttu-id="10da0-168">.NET Framework 4 のサービス構成の改善</span><span class="sxs-lookup"><span data-stu-id="10da0-168">Service configuration improvements in .NET Framework 4</span></span>](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [<span data-ttu-id="10da0-169">.NET 4 でよくあるユーザーの誤り: WF/WCF サービス構成名の入力ミス</span><span class="sxs-lookup"><span data-stu-id="10da0-169">Common User Mistake in .NET 4: Mistyping the WF/WCF Service Configuration Name</span></span>](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a><span data-ttu-id="10da0-170">簡略化された構成のシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-170">Simplified Configuration Scenarios</span></span>

- <span data-ttu-id="10da0-171">経験豊富な ASMX 開発者が WCF の使用を開始したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="10da0-171">An experienced ASMX developer wants to start using WCF.</span></span> <span data-ttu-id="10da0-172">しかし、WCF は複雑すぎるようです。</span><span class="sxs-lookup"><span data-stu-id="10da0-172">However, WCF seems way too complicated!</span></span> <span data-ttu-id="10da0-173">構成ファイルに書き込む必要のある情報は何ですか。</span><span class="sxs-lookup"><span data-stu-id="10da0-173">What is all that information that I need to write in a configuration file?</span></span> <span data-ttu-id="10da0-174">.NET 4 では、構成ファイルをまったく使用しないこともできます。</span><span class="sxs-lookup"><span data-stu-id="10da0-174">In .NET 4, you can even decide to not have a configuration file at all.</span></span>

- <span data-ttu-id="10da0-175">既存の WCF サービスのセットは構成とメンテナンスが非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="10da0-175">An existing set of WCF services are very difficult to configure and maintain.</span></span> <span data-ttu-id="10da0-176">構成ファイルには、変更するのが非常に危険な XML コードが何千行もあります。</span><span class="sxs-lookup"><span data-stu-id="10da0-176">The configuration file has thousands of lines of XML code that are extremely dangerous to touch.</span></span> <span data-ttu-id="10da0-177">コード量を管理しやすい量に減らすための支援が必要です。</span><span class="sxs-lookup"><span data-stu-id="10da0-177">Help is needed to reduce that amount of code to something more manageable.</span></span>

## <a name="data-contract-resolver"></a><span data-ttu-id="10da0-178">データ コントラクト リゾルバー</span><span class="sxs-lookup"><span data-stu-id="10da0-178">Data Contract Resolver</span></span>

<span data-ttu-id="10da0-179">.NET 3.5 では、既知の型の設計にはいくつかの制限がありました。</span><span class="sxs-lookup"><span data-stu-id="10da0-179">In .NET 3.5, there were a few limitations in the design of known types:</span></span>

- <span data-ttu-id="10da0-180">シリアル化または逆シリアル化中に既知の型を動的に追加することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="10da0-180">Adding known types dynamically, during serialization or deserialization, was not possible.</span></span>

- <span data-ttu-id="10da0-181">シリアライザーは不明な xsi:type の情報を処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="10da0-181">Serializers could not deal with unknown xsi:type information.</span></span>

- <span data-ttu-id="10da0-182">ユーザーは、ネットワーク上のシリアル化インスタンスのサイズを小さくするなど、ネットワーク上に出現する xsi:type を指定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="10da0-182">It was not possible for users to specify what xsi:type they would like to have appear on the wire to, for instance, make the size of a serialization instance on the wire smaller.</span></span>

<span data-ttu-id="10da0-183">[データ コントラクトリゾルバー](../wcf/samples/datacontractresolver.md)は、.NET 4.5 でこれらの問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="10da0-183">The [DataContractResolver](../wcf/samples/datacontractresolver.md) solves these issues in .NET 4.5.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-184">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-184">Getting Started</span></span>

- [<span data-ttu-id="10da0-185">データ コントラクト リゾルバー API のドキュメント</span><span class="sxs-lookup"><span data-stu-id="10da0-185">Data Contract Resolver API documentation</span></span>](xref:System.Runtime.Serialization.DataContractResolver)

- [<span data-ttu-id="10da0-186">データ コントラクト リゾルバーの概要</span><span class="sxs-lookup"><span data-stu-id="10da0-186">Introducing the Data Contract Resolver</span></span>](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- <span data-ttu-id="10da0-187">サンプル:</span><span class="sxs-lookup"><span data-stu-id="10da0-187">Samples:</span></span>

  - [<span data-ttu-id="10da0-188">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="10da0-188">DataContractResolver</span></span>](../wcf/samples/datacontractresolver.md)

  - [<span data-ttu-id="10da0-189">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="10da0-189">KnownAssemblyAttribute</span></span>](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a><span data-ttu-id="10da0-190">データ コントラクト リゾルバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-190">Data Contract Resolver Scenarios</span></span>

- <span data-ttu-id="10da0-191">数十の <xref:System.Runtime.Serialization.KnownTypeAttribute> オブジェクトをサービスで宣言する必要性の回避。</span><span class="sxs-lookup"><span data-stu-id="10da0-191">Avoiding having to declare tens of <xref:System.Runtime.Serialization.KnownTypeAttribute> objects in a service.</span></span>

- <span data-ttu-id="10da0-192">XML BLOB のサイズの削減。</span><span class="sxs-lookup"><span data-stu-id="10da0-192">Reducing the size of the XML blob.</span></span>

## <a name="flowchart"></a><span data-ttu-id="10da0-193">フローチャート</span><span class="sxs-lookup"><span data-stu-id="10da0-193">Flowchart</span></span>

<span data-ttu-id="10da0-194">フローチャートは、ドメインの問題を視覚的に表すための既知のパラダイムです。</span><span class="sxs-lookup"><span data-stu-id="10da0-194">Flowchart is a well-known paradigm to visually represent domain problems.</span></span> <span data-ttu-id="10da0-195">これは、.NET 4 で導入される新しい制御フロー スタイルです。</span><span class="sxs-lookup"><span data-stu-id="10da0-195">It is a new control flow style we're introducing in .NET 4.</span></span> <span data-ttu-id="10da0-196">フローチャートの主な特性は、一度に 1 つのアクティビティのみ実行されることです。</span><span class="sxs-lookup"><span data-stu-id="10da0-196">A core characteristic of Flowchart is that only one activity is executed at any given time.</span></span> <span data-ttu-id="10da0-197">フローチャートはループと代替結果を表すことができますが、その性質上、複数ノードの同時実行を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="10da0-197">Flowcharts can express loops and alternative outcomes, but cannot natively express concurrent execution of multiple nodes.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-198">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-198">Getting Started</span></span>

- <span data-ttu-id="10da0-199">Visual Studio 2012 で、ワークフロー コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-199">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="10da0-200">ワークフロー デザイナーにフローチャートを追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-200">Add a Flowchart in the workflow designer.</span></span>

- <span data-ttu-id="10da0-201">フローチャート機能では、次のクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="10da0-201">The flowchart feature uses the following classes:</span></span>

  - <xref:System.Activities.Statements.Flowchart>

  - <xref:System.Activities.Statements.FlowNode>

  - <xref:System.Activities.Statements.FlowDecision>

  - <xref:System.Activities.Statements.FlowStep>

  - <xref:System.Activities.Statements.FlowSwitch%601>

- <span data-ttu-id="10da0-202">サンプル:</span><span class="sxs-lookup"><span data-stu-id="10da0-202">Samples:</span></span>

  - [<span data-ttu-id="10da0-203">TryCatch を使用した Flowchart アクティビティでのエラー処理</span><span class="sxs-lookup"><span data-stu-id="10da0-203">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

  - [<span data-ttu-id="10da0-204">雇用プロセス</span><span class="sxs-lookup"><span data-stu-id="10da0-204">Hiring Process</span></span>](./samples/hiring-process.md)

- <span data-ttu-id="10da0-205">デザイナー ドキュメント:</span><span class="sxs-lookup"><span data-stu-id="10da0-205">Designer Documentation:</span></span>

  - [<span data-ttu-id="10da0-206">フローチャート アクティビティ デザイナー</span><span class="sxs-lookup"><span data-stu-id="10da0-206">Flowchart Activity Designers</span></span>](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a><span data-ttu-id="10da0-207">フローチャートのシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-207">Flowchart Scenarios</span></span>

<span data-ttu-id="10da0-208">フローチャート アクティビティを使用して推測ゲームを実装できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-208">A flowchart activity can be used to implement a guessing game.</span></span> <span data-ttu-id="10da0-209">推測ゲームは非常に単純です。コンピューターによってランダムな数値が選択され、プレーヤーはその数値を推測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-209">The guessing game is very simple: the computer selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="10da0-210">プレイヤーが各推測を送信すると、コンピュータはヒントを表示します(つまり、「より低い数値を試す」)。</span><span class="sxs-lookup"><span data-stu-id="10da0-210">When the player submits each guess, the computer shows them a hint (i.e. "try a lower number").</span></span> <span data-ttu-id="10da0-211">プレイヤーが7回未満の試行で数字を見つけた場合、彼らはコンピュータから特別な祝福を受けます。</span><span class="sxs-lookup"><span data-stu-id="10da0-211">If the player finds the number in less than 7 attempts, they receive a special congratulation from the computer.</span></span> <span data-ttu-id="10da0-212">このゲームは、次の手続き型アクティビティの組み合わせで実装できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-212">This game can be implemented with a combination of the following procedural activities:</span></span>

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a><span data-ttu-id="10da0-213">手続き型アクティビティ (Sequence、If、ForEach、Switch、Assign、DoWhile、While)</span><span class="sxs-lookup"><span data-stu-id="10da0-213">Procedural activities (Sequence, If, ForEach, Switch, Assign, DoWhile, While)</span></span>

<span data-ttu-id="10da0-214">手続き型アクティビティは、プログラマになじみのある概念を使用してシーケンシャル制御フローをモデル化するメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="10da0-214">Procedural activities provide a mechanism to model sequential control flow using concepts that are familiar to programmers.</span></span> <span data-ttu-id="10da0-215">これらのアクティビティを使用すると、従来の構造化プログラミング言語コンストラクトが可能になり、必要に応じて C# や Visual Basic などの一般的な手続き言語と言語のパリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="10da0-215">These activities enable traditionally structured programming language constructs and, when appropriate, provide language parity with common procedural languages such as C# and Visual Basic.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-216">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-216">Getting Started</span></span>

- <span data-ttu-id="10da0-217">Visual Studio 2012 で、ワークフロー コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-217">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="10da0-218">ワークフロー デザイナーで、手続き型アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-218">Add procedural activities in the workflow designer.</span></span>

- <span data-ttu-id="10da0-219">サンプル:</span><span class="sxs-lookup"><span data-stu-id="10da0-219">Samples:</span></span>

  - [<span data-ttu-id="10da0-220">雇用プロセス</span><span class="sxs-lookup"><span data-stu-id="10da0-220">Hiring Process</span></span>](./samples/hiring-process.md)

  - [<span data-ttu-id="10da0-221">企業の購買プロセス</span><span class="sxs-lookup"><span data-stu-id="10da0-221">Corporate Purchase Process</span></span>](./samples/corporate-purchase-process.md)

- <span data-ttu-id="10da0-222">デザイナー ドキュメント:</span><span class="sxs-lookup"><span data-stu-id="10da0-222">Designer Documentation:</span></span>

  - [<span data-ttu-id="10da0-223">Parallel アクティビティ デザイナー</span><span class="sxs-lookup"><span data-stu-id="10da0-223">Parallel Activity Designer</span></span>](/visualstudio/workflow-designer/parallel-activity-designer)

  - [<span data-ttu-id="10da0-224">アクティビティ デザイナー\<></span><span class="sxs-lookup"><span data-stu-id="10da0-224">ParallelForEach\<T> Activity Designer</span></span>](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a><span data-ttu-id="10da0-225">手続き型アクティビティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-225">Procedural Activity Scenarios</span></span>

- <span data-ttu-id="10da0-226"><xref:System.Activities.Statements.Parallel>: イントラネットのドキュメント管理システムには、ドキュメント承認ワークフローがあります。</span><span class="sxs-lookup"><span data-stu-id="10da0-226"><xref:System.Activities.Statements.Parallel>: An intranet document management system has a document approval workflow.</span></span> <span data-ttu-id="10da0-227">ドキュメントは、イントラネットに公開する前に、複数の部門の担当者によって承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-227">Documents need to be approved by people in several departments before they can be published to the intranet.</span></span> <span data-ttu-id="10da0-228">承認に対して確立された注文はありません。ドキュメントが「承認待ち」フェーズにある間はいつでも発生します。</span><span class="sxs-lookup"><span data-stu-id="10da0-228">There isn't an established order for the approvals; they can occur at any time while the document is in the "approval pending" phase.</span></span> <span data-ttu-id="10da0-229">ユーザーがレビュー用にドキュメントを送信する場合、そのドキュメントは、直接管理者、イントラネット管理者、および内部コミュニケーション マネージャによって承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-229">When a user submits a document for review, it must be approved by their direct manager, the intranet administrator, and the internal communications manager.</span></span>

- <span data-ttu-id="10da0-230"><xref:System.Activities.Statements.ParallelForEach%601>: WF アプリケーションは、大規模企業内での企業購買を管理します。</span><span class="sxs-lookup"><span data-stu-id="10da0-230"><xref:System.Activities.Statements.ParallelForEach%601>: A WF application manages corporate buys within a large company.</span></span> <span data-ttu-id="10da0-231">企業の規則では、購買作業を計画する前に 3 社の異なるベンダーを評価する必要があると規定されています。</span><span class="sxs-lookup"><span data-stu-id="10da0-231">The corporate rules dictate that before planning any purchase operation, the valuations of three different vendors is required.</span></span> <span data-ttu-id="10da0-232">購買部門の従業員が、会社の仕入先リストから 3 つの仕入先を選択します。</span><span class="sxs-lookup"><span data-stu-id="10da0-232">An employee from the buying department selects three vendors from the company's vendor list.</span></span> <span data-ttu-id="10da0-233">これらのベンダーを選択し、通知した後で、企業は経済提案書を待ちます。</span><span class="sxs-lookup"><span data-stu-id="10da0-233">After these vendors have been selected and notified, the company will wait for their economic proposals.</span></span> <span data-ttu-id="10da0-234">提案書は任意の順序で到着します。</span><span class="sxs-lookup"><span data-stu-id="10da0-234">The proposals can come in any order.</span></span> <span data-ttu-id="10da0-235">WF でこのシナリオを実装するには、ベンダーのコレクションを反復処理して経済提案書を求める <xref:System.Activities.Statements.ParallelForEach%601> を使用します。</span><span class="sxs-lookup"><span data-stu-id="10da0-235">To implement this scenario in WF, we use a <xref:System.Activities.Statements.ParallelForEach%601> that will iterate through our collection of vendors and ask for their economic proposals.</span></span> <span data-ttu-id="10da0-236">すべての提案が収集された後で、最良の提案が選択されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-236">After all offers are gathered, the best one is selected and displayed.</span></span>

## <a name="invokemethod"></a><span data-ttu-id="10da0-237">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="10da0-237">InvokeMethod</span></span>

<span data-ttu-id="10da0-238"><xref:System.Activities.Statements.InvokeMethod> アクティビティでは、オブジェクト内のパブリック メソッドまたはスコープ内の型を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="10da0-238">The <xref:System.Activities.Statements.InvokeMethod> activity allows invoking public methods in objects or types in scope.</span></span> <span data-ttu-id="10da0-239">パラメーター付きまたはパラメーターなし (パラメーター配列を含む) でのインスタンス メソッドおよび静的メソッドの呼び出し、および汎用メソッドの呼び出しがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="10da0-239">It supports invoking instance and static methods with or without parameters (including parameter arrays), and generic methods.</span></span> <span data-ttu-id="10da0-240">メソッドを同期および非同期で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="10da0-240">It also allows executing method synchronously and asynchronously.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-241">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-241">Getting Started</span></span>

- <span data-ttu-id="10da0-242">Visual Studio 2012 で、ワークフロー コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-242">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="10da0-243">ワークフロー デザイナーに <xref:System.Activities.Statements.InvokeMethod> アクティビティを追加し、そこに静的メソッドとインスタンス メソッドを構成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-243">Add an <xref:System.Activities.Statements.InvokeMethod> activity in the workflow designer, and configure static and instance methods on it.</span></span>

- <span data-ttu-id="10da0-244">デザイナー ドキュメント: [InvokeMethod アクティビティ デザイナー](/visualstudio/workflow-designer/invokemethod-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="10da0-244">Designer Documentation: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)</span></span>

### <a name="invokemethod-scenarios"></a><span data-ttu-id="10da0-245">InvokeMethod のシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-245">InvokeMethod Scenarios</span></span>

- <span data-ttu-id="10da0-246">スコープ内のオブジェクトのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-246">A method in an object in scope needs to be invoked.</span></span> <span data-ttu-id="10da0-247">たとえば、辞書に値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-247">For example, a value needs to be added to a dictionary.</span></span> <span data-ttu-id="10da0-248">辞書のインスタンスの Add メソッドが呼び出され、キーと値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-248">The Add method of the instance of the dictionary is invoked, and the key and value are provided.</span></span>

- <span data-ttu-id="10da0-249">レガシー CLR オブジェクトに対してメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-249">A method needs to be invoked on a legacy CLR object.</span></span> <span data-ttu-id="10da0-250">カスタム アクティビティを作成してそのレガシー クラスの呼び出しをラップする代わりに、ワークフロー実行中にそのクラスがスコープ内にある場合には <xref:System.Activities.Statements.InvokeMethod> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-250">Instead of creating a custom activity to wrap the call to that legacy class, if it is in scope during the workflow execution, <xref:System.Activities.Statements.InvokeMethod> can be used.</span></span>

## <a name="error-handling-activities"></a><span data-ttu-id="10da0-251">エラー処理アクティビティ</span><span class="sxs-lookup"><span data-stu-id="10da0-251">Error handling activities</span></span>

<span data-ttu-id="10da0-252">この<xref:System.Activities.Statements.TryCatch>アクティビティは、一連の包含アクティビティの実行中に発生する例外をキャッチするメカニズムを提供します (C# および Visual Basic の Try/Catch コンストラクトと同様)。</span><span class="sxs-lookup"><span data-stu-id="10da0-252">The <xref:System.Activities.Statements.TryCatch> activity provides a mechanism for catching exceptions that occur during the execution of a set of contained activities (similar to the Try/Catch construct in C# and Visual Basic).</span></span> <span data-ttu-id="10da0-253"><xref:System.Activities.Statements.TryCatch> はワークフロー レベルの例外処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="10da0-253"><xref:System.Activities.Statements.TryCatch> provides exception handling at the workflow level.</span></span> <span data-ttu-id="10da0-254">ハンドルされない例外がスローされると、ワークフローは中止され、Finally ブロックは実行されません。</span><span class="sxs-lookup"><span data-stu-id="10da0-254">When an unhandled exception is thrown, the workflow is aborted and the Finally block won't be executed.</span></span> <span data-ttu-id="10da0-255">この動作は C# と一貫性があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-255">This behavior is consistent with C#.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-256">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-256">Getting Started</span></span>

- <span data-ttu-id="10da0-257">Visual Studio 2012 で、ワークフロー コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-257">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="10da0-258">ワークフロー デザイナーで <xref:System.Activities.Statements.TryCatch> アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-258">Add a <xref:System.Activities.Statements.TryCatch> activity in the workflow designer.</span></span>

- <span data-ttu-id="10da0-259">サンプル: [tryCatch を使用したフローチャート アクティビティでのフォルト処理](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-259">Sample: [Fault Handling in a Flowchart Activity Using TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)</span></span>

- <span data-ttu-id="10da0-260">デザイナー ドキュメント:[エラー処理アクティビティ デザイナー](/visualstudio/workflow-designer/error-handling-activity-designers)</span><span class="sxs-lookup"><span data-stu-id="10da0-260">Designer Documentation: [Error Handling Activity Designers](/visualstudio/workflow-designer/error-handling-activity-designers)</span></span>

### <a name="error-handling-scenarios"></a><span data-ttu-id="10da0-261">エラー処理のシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-261">Error handling scenarios</span></span>

<span data-ttu-id="10da0-262">アクティビティのセットを実行する必要があり、エラーの発生時に特定のロジックを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-262">A set of activities needs to be executed, and specific logic needs to be executed when an error occurs.</span></span> <span data-ttu-id="10da0-263">そのエラー処理ロジック中にエラーが回復不能であることがわかった場合は、例外が再スローされ、親アクティビティ (またはホスト) によって問題が処理されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-263">If during that error handling logic it is found that the error is not recoverable, the exception will be rethrown, and the parent activity (or the host) will deal with the problem.</span></span>

## <a name="pick-activity"></a><span data-ttu-id="10da0-264">Pick アクティビティ</span><span class="sxs-lookup"><span data-stu-id="10da0-264">Pick activity</span></span>

<span data-ttu-id="10da0-265"><xref:System.Activities.Statements.Pick> アクティビティは、WF でイベント ベースの制御フロー モデリングを提供します。</span><span class="sxs-lookup"><span data-stu-id="10da0-265">The <xref:System.Activities.Statements.Pick> Activity provides event-based control flow modeling in WF.</span></span> <span data-ttu-id="10da0-266"><xref:System.Activities.Statements.Pick> には、多数の分岐が含まれています。各分岐は、特定のイベントが発生すると実行されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-266"><xref:System.Activities.Statements.Pick> contains many branches where each branch waits for a particular event to occur before running.</span></span> <span data-ttu-id="10da0-267">この設定では、<xref:System.Activities.Statements.Pick> は、アクティビティがリッスンしているイベント セットの 1 つのみを実行する <xref:System.Activities.Statements.Switch%601> と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="10da0-267">In this setup, a <xref:System.Activities.Statements.Pick> behaves similar to a <xref:System.Activities.Statements.Switch%601> to which the Activity will execute only one of the set of events it is listening.</span></span> <span data-ttu-id="10da0-268">各分岐はイベント ドリブンなので、発生したイベントが対応する分岐を実行します。</span><span class="sxs-lookup"><span data-stu-id="10da0-268">Each branch is event driven and the event that occurs runs the corresponding branch first.</span></span> <span data-ttu-id="10da0-269">他のすべての分岐は、イベントのリッスンをキャンセルし、停止します。</span><span class="sxs-lookup"><span data-stu-id="10da0-269">All other branches cancel and stop listening for events.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-270">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-270">Getting Started</span></span>

- <span data-ttu-id="10da0-271">Visual Studio 2012 で、ワークフロー コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-271">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="10da0-272">ワークフロー デザイナーで <xref:System.Activities.Statements.Pick> アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-272">Add a <xref:System.Activities.Statements.Pick> activity in the workflow designer.</span></span>

- <span data-ttu-id="10da0-273">サンプル:[ピッキングアクティビティの使用](./samples/using-the-pick-activity.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-273">Sample: [Using the Pick Activity](./samples/using-the-pick-activity.md)</span></span>

- <span data-ttu-id="10da0-274">デザイナーのドキュメント:[アクティビティ デザイナーの選択](/visualstudio/workflow-designer/pick-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="10da0-274">Designer documentation: [Pick Activity Designer](/visualstudio/workflow-designer/pick-activity-designer)</span></span>

### <a name="pick-scenario"></a><span data-ttu-id="10da0-275">Pick のシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-275">Pick Scenario</span></span>

<span data-ttu-id="10da0-276">ユーザーに入力を求めるプロンプトを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-276">A user needs to be prompted for input.</span></span> <span data-ttu-id="10da0-277">通常の状況では、開発者はメソッド呼び出し<xref:System.Console.ReadLine%2A>を使用して、ユーザーの入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="10da0-277">Under normal circumstances, the developer would use a method call like <xref:System.Console.ReadLine%2A> to prompt for a user's input.</span></span> <span data-ttu-id="10da0-278">この設定の問題は、ユーザーが何か入力するまでプログラムが待機することです。</span><span class="sxs-lookup"><span data-stu-id="10da0-278">The problem with this setup is that the program waits until the user enters something.</span></span> <span data-ttu-id="10da0-279">このシナリオでは、ブロッキング アクティビティのブロックを解除するためにタイムアウトが必要です。</span><span class="sxs-lookup"><span data-stu-id="10da0-279">In this scenario, a time-out is needed to unblock a blocking activity.</span></span> <span data-ttu-id="10da0-280">一般的なシナリオでは、特定の期間内にタスクが完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-280">A common scenario is one that requires a task to be completed within a given time duration.</span></span> <span data-ttu-id="10da0-281">ブロッキング アクティビティのタイムアウトは、Pick が大量の値を追加するシナリオです。</span><span class="sxs-lookup"><span data-stu-id="10da0-281">Timing out a blocking activity is a scenario where Pick adds a lot of value.</span></span>

## <a name="wcf-routing-service"></a><span data-ttu-id="10da0-282">WCF ルーティング サービス</span><span class="sxs-lookup"><span data-stu-id="10da0-282">WCF Routing Service</span></span>

<span data-ttu-id="10da0-283">ルーティング サービスは、クライアントとサービス間で WCF メッセージがどのように流れるかを制御できる汎用ソフトウェア ルーターとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="10da0-283">The Routing Service is designed to be a generic software Router that allows you to control how WCF messages flow in between your clients and services.</span></span> <span data-ttu-id="10da0-284">ルーティング サービスを使用すると、クライアントをサービスから切り離すことができます。</span><span class="sxs-lookup"><span data-stu-id="10da0-284">The Routing Service allows you to decouple your clients from your services, which gives you much more freedom in terms of the configurations that you can support and the flexibility you have when considering how to host your services.</span></span> <span data-ttu-id="10da0-285">NET 3.5 では、クライアントとサービスが緊密に結合されていました。クライアントは、話し合う必要があるすべてのサービスと、その場所について知る必要がありました。</span><span class="sxs-lookup"><span data-stu-id="10da0-285">In .NET 3.5, clients and services were tightly coupled; a client had to know about all of the services it needed to talk to and where they were located.</span></span> <span data-ttu-id="10da0-286">さらに、.NET Framework 3.5 の WCF には、次の制限がありました。</span><span class="sxs-lookup"><span data-stu-id="10da0-286">In addition, WCF in .NET Framework 3.5 had the following limitations:</span></span>

- <span data-ttu-id="10da0-287">ロジックをクライアントにハードコーディングする必要があったため、エラー処理が複雑でした。</span><span class="sxs-lookup"><span data-stu-id="10da0-287">Error handling was complex, as this logic had to be hard-coded into the client.</span></span>

- <span data-ttu-id="10da0-288">クライアントとサービスは常に同じバインディングを使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="10da0-288">Clients and services had to always use the same bindings.</span></span>

- <span data-ttu-id="10da0-289">サービスが適切に分類されていることはほとんどありませんでした。複数のサービス間で選択するよりも、クライアントがすべてを実装する 1 つのサービスと対話する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="10da0-289">Services were rarely well factored: it is easier to have the client talk to one service which implements everything, rather than needing to choose between multiple services.</span></span>

<span data-ttu-id="10da0-290">.NET 4 のルーティング サービスは、これらの問題を簡単に解決できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="10da0-290">The routing service in .NET 4 is designed to make these problems easier to solve.</span></span> <span data-ttu-id="10da0-291">新しいルーティング サービスには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-291">The new routing service has the following features:</span></span>

1. <span data-ttu-id="10da0-292">コンテント ベースのルーティング (<xref:System.ServiceModel.Dispatcher.MessageFilter> オブジェクトがメッセージを調べて送信先を判断します。)</span><span class="sxs-lookup"><span data-stu-id="10da0-292">Content based routing (<xref:System.ServiceModel.Dispatcher.MessageFilter> objects examine a message to determine where it should be sent.)</span></span>

2. <span data-ttu-id="10da0-293">プロトコル ブリッジ (トランスポート & メッセージ)</span><span class="sxs-lookup"><span data-stu-id="10da0-293">Protocol bridging (transport & message)</span></span>

3. <span data-ttu-id="10da0-294">エラー処理 (ルーターは、通信例外をキャッチし、バックアップ エンドポイントにフェールオーバーします)</span><span class="sxs-lookup"><span data-stu-id="10da0-294">Error handling (the router catches communication exceptions and fails over to backup endpoints)</span></span>

4. <span data-ttu-id="10da0-295"><xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> およびルーティング構成の動的 (メモリ内) 更新。</span><span class="sxs-lookup"><span data-stu-id="10da0-295">Dynamic (in memory) update of <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> and Routing Configuration.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-296">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-296">Getting Started</span></span>

1. <span data-ttu-id="10da0-297">ドキュメント:[ルーティング](../wcf/feature-details/routing.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-297">Documentation: [Routing](../wcf/feature-details/routing.md)</span></span>

2. <span data-ttu-id="10da0-298">サンプル: [WCF サンプル&#93;&#91;ルーティング サービス](../wcf/samples/routing-services.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-298">Samples: [Routing Services &#91;WCF Samples&#93;](../wcf/samples/routing-services.md)</span></span>

3. <span data-ttu-id="10da0-299">ブログ:[ルーティングルール!](https://docs.microsoft.com/archive/blogs/RoutingRules/)</span><span class="sxs-lookup"><span data-stu-id="10da0-299">Blog: [Routing Rules!](https://docs.microsoft.com/archive/blogs/RoutingRules/)</span></span>

### <a name="routing-scenarios"></a><span data-ttu-id="10da0-300">ルーティング シナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-300">Routing Scenarios</span></span>

<span data-ttu-id="10da0-301">ルーティング サービスは、次のシナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="10da0-301">The routing service is useful in the following scenarios:</span></span>

- <span data-ttu-id="10da0-302">クライアントは、複数のサービスを直接アドレス指定することなく、これらのサービスと対話できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-302">Clients can talk to multiple services without having to address them all directly.</span></span>

- <span data-ttu-id="10da0-303">クライアントは、ルーティング先を判断するためにクライアント要求で追加のロジックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-303">Clients can perform additional logic on a client request to determine where to route it</span></span>

- <span data-ttu-id="10da0-304">クライアントをリファクタリングすることなく、クライアントが実行する操作を複数のサービス実装に分解します。</span><span class="sxs-lookup"><span data-stu-id="10da0-304">Decompose the operations a client performs into multiple service implementations without refactoring the client.</span></span>

- <span data-ttu-id="10da0-305">クライアントとサービスは、異なるセキュリティ設定の異なるバインディングで会話できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-305">Clients and services can speak different bindings with different security settings.</span></span>

- <span data-ttu-id="10da0-306">クライアントは、障害またはサービスの使用不能に対してより堅牢になることができます。</span><span class="sxs-lookup"><span data-stu-id="10da0-306">Clients can be enabled to be more robust against failure or the unavailability of services.</span></span>

## <a name="wcf-discovery"></a><span data-ttu-id="10da0-307">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="10da0-307">WCF Discovery</span></span>

<span data-ttu-id="10da0-308">WCF Discovery は、アプリケーション インフラストラクチャに探索メカニズムを組み込むことができるフレームワーク テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="10da0-308">WCF Discovery is a framework technology that allows you to incorporate a discovery mechanism to your application infrastructure.</span></span> <span data-ttu-id="10da0-309">これを使用して、サービスを探索可能にし、サービスを検索するようにクライアントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-309">You can use this to make your service discoverable, and configure your clients to search for services.</span></span> <span data-ttu-id="10da0-310">クライアントはエンドポイントでハードコーディングする必要がなくなるため、アプリケーションはより堅牢になりフォールト トレランスが向上します。</span><span class="sxs-lookup"><span data-stu-id="10da0-310">Clients no longer need to be hard coded with endpoint, making your application more robust and fault tolerant.</span></span> <span data-ttu-id="10da0-311">探索は、アプリケーションに自動構成機能をビルドするための最適なプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="10da0-311">Discovery is the perfect platform to build auto-configuration capabilities into your application.</span></span>

<span data-ttu-id="10da0-312">製品は、WS-Discovery 標準の上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-312">The product is built on top of the WS-Discovery standard.</span></span> <span data-ttu-id="10da0-313">相互運用可能で、拡張可能で、汎用的な設計をしています。</span><span class="sxs-lookup"><span data-stu-id="10da0-313">It's designed to be interoperable, extensible, and generic.</span></span> <span data-ttu-id="10da0-314">製品では 2 つの操作モードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="10da0-314">The product supports two modes of operation:</span></span>

1. <span data-ttu-id="10da0-315">マネージド: 既存のサービスに関する知識を持つエンティティがネットワーク上にあり、クライアントは情報を直接クエリします。</span><span class="sxs-lookup"><span data-stu-id="10da0-315">Managed: where there is an entity on the network knowledgeable about existing services, clients query it directly for information.</span></span> <span data-ttu-id="10da0-316">これは Active Directory に類似しています。</span><span class="sxs-lookup"><span data-stu-id="10da0-316">This is analogous to Active Directory.</span></span>

2. <span data-ttu-id="10da0-317">アドホック: クライアントはマルチキャスト メッセージを使用してサービスを特定します。</span><span class="sxs-lookup"><span data-stu-id="10da0-317">Ad-hoc: where clients use multicast messages to locate services.</span></span>

<span data-ttu-id="10da0-318">さらに、探索メッセージはネットワーク プロトコルに依存しません。モード要件をサポートする任意のプロトコル上でこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-318">Furthermore, discovery messages are network protocol agnostic; you can use them on top any protocol that supports the mode requirements.</span></span> <span data-ttu-id="10da0-319">たとえば、探索マルチキャスト メッセージは UDP チャネルまたはマルチキャスト メッセージングをサポートする他のネットワークを介して送信できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-319">For example, discovery multicast messages can be sent over the UDP channel or any other network that supports multicast messaging.</span></span> <span data-ttu-id="10da0-320">これらの設計ポイントと機能の柔軟性を組み合わせることで、ソリューションに合わせて検出を調整できます。</span><span class="sxs-lookup"><span data-stu-id="10da0-320">These design points, combined with feature flexibility, allow you to adapt the discovery specifically to your solution.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-321">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-321">Getting Started</span></span>

- <span data-ttu-id="10da0-322">ドキュメント: [WCF ディスカバリ](../wcf/feature-details/wcf-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-322">Documentation: [WCF Discovery](../wcf/feature-details/wcf-discovery.md)</span></span>

- <span data-ttu-id="10da0-323">サンプル:[検出 (サンプル)](../wcf/samples/discovery-samples.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-323">Samples: [Discovery (Samples)](../wcf/samples/discovery-samples.md)</span></span>

### <a name="discovery-scenarios"></a><span data-ttu-id="10da0-324">探索のシナリオ</span><span class="sxs-lookup"><span data-stu-id="10da0-324">Discovery Scenarios</span></span>

<span data-ttu-id="10da0-325">サービスがいつ使用可能になるかが不明なため、開発者はエンドポイントのハードコーディングを望みません。</span><span class="sxs-lookup"><span data-stu-id="10da0-325">A developer doesn't want to hard code endpoints, since it is unknown when my service will be available.</span></span> <span data-ttu-id="10da0-326">代わりに、開発者は実行時にサービスを選択することを望んでいます。</span><span class="sxs-lookup"><span data-stu-id="10da0-326">Instead, the developer wants to choose a service at runtime.</span></span> <span data-ttu-id="10da0-327">アプリケーションのコンポーネント間に、切り離し、堅牢性、および自動構成がさらに必要です。</span><span class="sxs-lookup"><span data-stu-id="10da0-327">More decoupling, robustness, and auto-configuration is needed between the components in the application.</span></span>

## <a name="tracking"></a><span data-ttu-id="10da0-328">追跡</span><span class="sxs-lookup"><span data-stu-id="10da0-328">Tracking</span></span>

<span data-ttu-id="10da0-329">ワークフロー追跡は、ワークフロー インスタンスの実行に関する洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="10da0-329">Workflow tracking provides insight into the execution of a workflow instance.</span></span> <span data-ttu-id="10da0-330">追跡イベントは、ワークフロー インスタンス レベルでワークフローから生成され、ワークフロー内のアクティビティが実行されるときに生成されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-330">The tracking events are emitted from a workflow at the workflow instance level and when activities within the workflow execute.</span></span> <span data-ttu-id="10da0-331">追跡レコードを定期受信するにはワークフロー追跡参加要素をワークフロー ホストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10da0-331">A workflow tracking participant needs to be added to the workflow host to subscribe to tracking records.</span></span> <span data-ttu-id="10da0-332">追跡レコードは、追跡プロファイルを使用してフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-332">The tracking records are filtered using a tracking profile.</span></span> <span data-ttu-id="10da0-333">.NET Framework は ETW (Windows 用イベント トレース) 追跡参加要素を提供し、基本プロファイルが machine.config ファイルにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="10da0-333">The .NET Framework provides an ETW (Event Tracing for Windows) tracking participant, and a basic profile is installed in the machine.config file.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-334">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-334">Getting Started</span></span>

1. <span data-ttu-id="10da0-335">Visual Studio 2010 で、WCF ワークフロー サービス アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-335">In Visual Studio 2010, create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="10da0-336">開始するキャンバスに <xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> のペアが配置されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-336">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas to start.</span></span>

2. <span data-ttu-id="10da0-337">web.config を開き、プロファイルなしで ETW 追跡動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-337">Open the web.config and add an ETW tracking behavior with no profile.</span></span>

    1. <span data-ttu-id="10da0-338">既定のプロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="10da0-338">The default profile is used.</span></span>

    2. <span data-ttu-id="10da0-339">イベント ビューアを開き、次のノードで分析チャネルを有効に**します。** **Applications and Services Logs** **Microsoft** **Windows** **Application Server-Applications**</span><span class="sxs-lookup"><span data-stu-id="10da0-339">Open event viewer and enable the analytic channel in the following node: **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="10da0-340">**[分析**] を右クリックし、[**ログの有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="10da0-340">Right-click **Analytic** and select **Enable Log**.</span></span>

    3. <span data-ttu-id="10da0-341">ワークフロー サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="10da0-341">Run the workflow service.</span></span>

    4. <span data-ttu-id="10da0-342">イベント ビューアーでワークフロー追跡イベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="10da0-342">Observe the workflow tracking events in event viewer.</span></span>

3. <span data-ttu-id="10da0-343">サンプル:[トラッキング](./samples/tracking.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-343">Samples: [Tracking](./samples/tracking.md)</span></span>

4. <span data-ttu-id="10da0-344">概念ドキュメント:[ワークフローの追跡とトレース](workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-344">Conceptual documentation: [Workflow Tracking and Tracing](workflow-tracking-and-tracing.md)</span></span>

## <a name="sql-workflow-instance-store"></a><span data-ttu-id="10da0-345">SQL Workflow Instance Store</span><span class="sxs-lookup"><span data-stu-id="10da0-345">SQL Workflow Instance Store</span></span>

<span data-ttu-id="10da0-346"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> は、SQL Server ベースのインスタンス ストアの実装です。</span><span class="sxs-lookup"><span data-stu-id="10da0-346">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is a SQL Server-based implementation of an instance store.</span></span> <span data-ttu-id="10da0-347">インスタンス ストアは、実行中のインスタンスの状態を、そのインスタンスの読み込みと再開に必要なすべてのデータと共に格納します。</span><span class="sxs-lookup"><span data-stu-id="10da0-347">An instance store stores the state of a running instance together with all data necessary to load and resume that instance.</span></span> <span data-ttu-id="10da0-348">サービス ホストは、ワークフローが永続的な場合にインスタンス状態を保存するようインスタンス ストアに指示し、そのインスタンスのメッセージが到着するか遅延アクティビティが期限切れになったときにインスタンス状態を読み込むようインスタンス ストアに指示します。</span><span class="sxs-lookup"><span data-stu-id="10da0-348">The service host instructs the instance store to save the instance state if the workflow persists, and it instructs the instance store to load the instance state when a message arrives for that instance or a delay activity expires.</span></span>

### <a name="getting-started"></a><span data-ttu-id="10da0-349">作業の開始</span><span class="sxs-lookup"><span data-stu-id="10da0-349">Getting Started</span></span>

1. <span data-ttu-id="10da0-350">Visual Studio 2012 では、暗黙的または明示的<xref:System.Activities.Statements.Persist>なアクティビティを含むワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="10da0-350">In Visual Studio 2012, create a Workflow that contains an implicit or explicit <xref:System.Activities.Statements.Persist> activity.</span></span> <span data-ttu-id="10da0-351"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 動作をワークフロー サービス ホストに追加します。</span><span class="sxs-lookup"><span data-stu-id="10da0-351">Add the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> behavior to your workflow service host.</span></span> <span data-ttu-id="10da0-352">これはコードまたはアプリケーション構成ファイルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="10da0-352">This can be done in code or in the application configuration file.</span></span>

2. <span data-ttu-id="10da0-353">サンプル:[永続性](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="10da0-353">Samples: [Persistence](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))</span></span>

3. <span data-ttu-id="10da0-354">概念ドキュメント: [SQL ワークフロー インスタンス ストア](sql-workflow-instance-store.md)</span><span class="sxs-lookup"><span data-stu-id="10da0-354">Conceptual documentation: [SQL Workflow Instance Store](sql-workflow-instance-store.md).</span></span>
