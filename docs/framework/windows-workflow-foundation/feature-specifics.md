---
title: Windows Workflow Foundation の機能仕様
description: この記事では、.NET Framework 4 が Windows Workflow Foundation に追加される新機能と、機能が役立つ可能性があるシナリオについて説明します。
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: fb490b3dd368710bf2ed98f7c53b7b184fa15b0b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419955"
---
# <a name="windows-workflow-foundation-feature-specifics"></a><span data-ttu-id="91a67-103">Windows Workflow Foundation の機能仕様</span><span class="sxs-lookup"><span data-stu-id="91a67-103">Windows Workflow Foundation Feature Specifics</span></span>

<span data-ttu-id="91a67-104">.NET Framework 4 は、Windows Workflow Foundation にいくつかの機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-104">.NET Framework 4 adds a number of features to Windows Workflow Foundation.</span></span> <span data-ttu-id="91a67-105">このドキュメントでは、いくつかの新機能について説明し、役に立つ可能性のあるシナリオの詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="91a67-105">This document describes a number of the new features, and gives details about scenarios in which they may be useful.</span></span>

## <a name="messaging-activities"></a><span data-ttu-id="91a67-106">メッセージング アクティビティ</span><span class="sxs-lookup"><span data-stu-id="91a67-106">Messaging Activities</span></span>

<span data-ttu-id="91a67-107">メッセージングアクティビティ ( <xref:System.ServiceModel.Activities.Receive> 、、 <xref:System.ServiceModel.Activities.SendReply> <xref:System.ServiceModel.Activities.Send> 、 <xref:System.ServiceModel.Activities.ReceiveReply> ) は、ワークフローから WCF メッセージを送受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-107">The messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) are used to send and receive WCF messages from your workflow.</span></span> <span data-ttu-id="91a67-108"><xref:System.ServiceModel.Activities.Receive>および <xref:System.ServiceModel.Activities.SendReply> アクティビティは、標準の wcf web サービスと同様に、WSDL 経由で公開される Windows Communication Foundation (wcf) サービス操作を形成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-108"><xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities are used to form a Windows Communication Foundation (WCF) service operation that is exposed via WSDL just like standard WCF web services.</span></span> <span data-ttu-id="91a67-109"><xref:System.ServiceModel.Activities.Send>と <xref:System.ServiceModel.Activities.ReceiveReply> は、WCF と同様に web サービスを使用するために使用されます。 <xref:System.ServiceModel.ChannelFactory> 事前に構成されたアクティビティを生成する Workflow Foundation の**サービス参照の追加**エクスペリエンスもあります。</span><span class="sxs-lookup"><span data-stu-id="91a67-109"><xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> are used to consume a web service similar to a WCF <xref:System.ServiceModel.ChannelFactory>; an **Add Service Reference** experience also exists for Workflow Foundation that generates pre-configured activities.</span></span>

### <a name="getting-started-with-messaging-activities"></a><span data-ttu-id="91a67-110">メッセージング アクティビティの概要</span><span class="sxs-lookup"><span data-stu-id="91a67-110">Getting Started with Messaging Activities</span></span>

- <span data-ttu-id="91a67-111">Visual Studio 2012 で、WCF ワークフローサービスアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-111">In Visual Studio 2012, create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="91a67-112"><xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> のペアがキャンバスに配置されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-112">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas.</span></span>

- <span data-ttu-id="91a67-113">プロジェクトを右クリックし、[**サービス参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="91a67-113">Right-click on the project and select **Add Service Reference**.</span></span> <span data-ttu-id="91a67-114">既存の web サービス WSDL をポイントし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91a67-114">Point to an existing web service WSDL and click **OK**.</span></span> <span data-ttu-id="91a67-115">プロジェクトをビルドして、生成されたアクティビティ (およびを使用して実装 <xref:System.ServiceModel.Activities.Send> <xref:System.ServiceModel.Activities.ReceiveReply> ) をツールボックスに表示します。</span><span class="sxs-lookup"><span data-stu-id="91a67-115">Build your project to show the generated activities (implemented using <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply>) in your toolbox.</span></span>

- [<span data-ttu-id="91a67-116">ワークフローサービスのドキュメント</span><span class="sxs-lookup"><span data-stu-id="91a67-116">Workflow services documentation</span></span>](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a><span data-ttu-id="91a67-117">メッセージング アクティビティのシナリオ例</span><span class="sxs-lookup"><span data-stu-id="91a67-117">Messaging Activities Example Scenario</span></span>

<span data-ttu-id="91a67-118">サービスは、 `BestPriceFinder` 複数の航空会社サービスを呼び出して、特定のルートに最適なチケット価格を検索します。</span><span class="sxs-lookup"><span data-stu-id="91a67-118">A `BestPriceFinder` service calls out to multiple airline services to find the best ticket price for a particular route.</span></span> <span data-ttu-id="91a67-119">このシナリオを実装するには、メッセージアクティビティを使用して価格要求を受信し、バックエンドサービスから価格を取得し、価格要求に最高価格で返信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-119">Implementing this scenario would require you to use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span> <span data-ttu-id="91a67-120">また、その他の既定のアクティビティを使用して、最適な価格を計算するためのビジネスロジックを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-120">It would also require you to use other out-of-box activities to create the business logic for calculating the best price.</span></span>

## <a name="workflowservicehost"></a><span data-ttu-id="91a67-121">WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="91a67-121">WorkflowServiceHost</span></span>

<span data-ttu-id="91a67-122"><xref:System.ServiceModel.WorkflowServiceHost>は、複数のインスタンス、構成、および WCF メッセージングをサポートする、標準のワークフローホストです (ただし、ワークフローは、ホストするためにメッセージングを使用する必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="91a67-122">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren't required to use messaging in order to be hosted).</span></span> <span data-ttu-id="91a67-123">また、一連のサービス動作を介して永続性、追跡、およびインスタンス コントロールを統合します。</span><span class="sxs-lookup"><span data-stu-id="91a67-123">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span> <span data-ttu-id="91a67-124">WCF の場合と同様に <xref:System.ServiceModel.ServiceHost> 、は、 <xref:System.ServiceModel.WorkflowServiceHost> コンソール、WINFORMS、WPF アプリケーション、Windows サービス、または IIS または WAS の web ホスト (.xamlx ファイル) で自己ホストされます。</span><span class="sxs-lookup"><span data-stu-id="91a67-124">Just like WCF's <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in a console/WinForms/WPF application or Windows service, or web-hosted (as a .xamlx file) in IIS or WAS.</span></span>

### <a name="getting-started-with-workflow-service-host"></a><span data-ttu-id="91a67-125">ワークフロー サービス ホストの概要</span><span class="sxs-lookup"><span data-stu-id="91a67-125">Getting Started with Workflow Service Host</span></span>

- <span data-ttu-id="91a67-126">Visual Studio 2010 で、WCF ワークフローサービスアプリケーションプロジェクトを作成します。このプロジェクトは、 <xref:System.ServiceModel.WorkflowServiceHost> web ホスト環境で使用するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-126">In Visual Studio 2010, create a WCF Workflow Service Application project: this project will be set up to use <xref:System.ServiceModel.WorkflowServiceHost> in a web-host environment.</span></span>

- <span data-ttu-id="91a67-127">非メッセージング ワークフローをホストするには、メッセージに基づいてインスタンスを作成するカスタム <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> を追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-127">In order to host a non-messaging workflow, add a custom <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> that will create the instance based on a message.</span></span>

- <span data-ttu-id="91a67-128">ワークフロー インスタンスは、<xref:System.ServiceModel.Activities.WorkflowControlEndpoint> を <xref:System.ServiceModel.WorkflowServiceHost> に追加し、<xref:System.ServiceModel.Activities.WorkflowControlClient> を使用することで制御 (中断や終了など) できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-128">Workflow instances can be controlled (e.g. suspended or terminated) by adding a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> to the <xref:System.ServiceModel.WorkflowServiceHost> and then using a <xref:System.ServiceModel.Activities.WorkflowControlClient>.</span></span>

- <span data-ttu-id="91a67-129"><xref:System.ServiceModel.WorkflowServiceHost> のサンプルは次のセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="91a67-129">Samples for the <xref:System.ServiceModel.WorkflowServiceHost> can be found in the following sections:</span></span>

  - [<span data-ttu-id="91a67-130">実行</span><span class="sxs-lookup"><span data-stu-id="91a67-130">Execution</span></span>](./samples/execution.md)

  - <span data-ttu-id="91a67-131">アプリケーション:[中断](./samples/suspended-instance-management.md)されたインスタンスの管理</span><span class="sxs-lookup"><span data-stu-id="91a67-131">Application: [Suspended Instance Management](./samples/suspended-instance-management.md)</span></span>

- [<span data-ttu-id="91a67-132">ワークフローサービスのホスティングの概要</span><span class="sxs-lookup"><span data-stu-id="91a67-132">Hosting Workflow services overview</span></span>](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a><span data-ttu-id="91a67-133">WorkflowServiceHost のシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-133">WorkflowServiceHost Scenario</span></span>

<span data-ttu-id="91a67-134">BestPriceFinder サービスは、複数の航空会社サービスを呼び出して、特定のルートに最適なチケット価格を探します。</span><span class="sxs-lookup"><span data-stu-id="91a67-134">A BestPriceFinder service calls out to multiple airline services to find the best ticket price for a particular route.</span></span> <span data-ttu-id="91a67-135">このシナリオを実装するには、でワークフローをホストする必要があり <xref:System.ServiceModel.WorkflowServiceHost> ます。</span><span class="sxs-lookup"><span data-stu-id="91a67-135">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="91a67-136">また、メッセージアクティビティを使用して、価格要求を受信し、バックエンドサービスから価格を取得し、価格要求に最高価格で応答します。</span><span class="sxs-lookup"><span data-stu-id="91a67-136">It would also use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span>

## <a name="correlation"></a><span data-ttu-id="91a67-137">Correlation</span><span class="sxs-lookup"><span data-stu-id="91a67-137">Correlation</span></span>

<span data-ttu-id="91a67-138">相関関係は次の 2 つのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="91a67-138">A correlation is one of two things:</span></span>

- <span data-ttu-id="91a67-139">メッセージをグループ化する方法。つまり、要求メッセージとその応答の関係。</span><span class="sxs-lookup"><span data-stu-id="91a67-139">A way of grouping messages together; that is, the relationship between a request message and its reply.</span></span>

- <span data-ttu-id="91a67-140">サービス インスタンスにデータの一部をマッピングする方法。</span><span class="sxs-lookup"><span data-stu-id="91a67-140">A way of mapping a piece of data to a service instance</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-141">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-141">Getting Started</span></span>

- <span data-ttu-id="91a67-142">相関を開始するには、Visual Studio で新規プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-142">To get started with correlation, create a new project in Visual Studio.</span></span> <span data-ttu-id="91a67-143"><xref:System.ServiceModel.Activities.CorrelationHandle> 型の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-143">Create a variable of type <xref:System.ServiceModel.Activities.CorrelationHandle>.</span></span>

- <span data-ttu-id="91a67-144">メッセージのグループ化に使用する相関関係の例は、メッセージをグループ化する要求/応答の相関関係です。</span><span class="sxs-lookup"><span data-stu-id="91a67-144">An example of correlation used to group messages together is a Request-Reply correlation that groups messages together.</span></span>

  - <span data-ttu-id="91a67-145">アクティビティで、プロパティをクリックし、 <xref:System.ServiceModel.Activities.Receive> 上の <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 最初の <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> 手順で作成した CorrelationHandle を使用してを追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-145">On a <xref:System.ServiceModel.Activities.Receive> activity, click on the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> property and add a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> using the CorrelationHandle created in the first step above.</span></span>

  - <span data-ttu-id="91a67-146">アクティビティを作成するに <xref:System.ServiceModel.Activities.SendReply> は、を右クリックし、[ <xref:System.ServiceModel.Activities.Receive> SendReply の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91a67-146">Create a <xref:System.ServiceModel.Activities.SendReply> activity by right-clicking on the <xref:System.ServiceModel.Activities.Receive> and clicking "Create SendReply".</span></span> <span data-ttu-id="91a67-147">これをワークフローの <xref:System.ServiceModel.Activities.Receive> アクティビティの後に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="91a67-147">Paste it into your workflow after the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

- <span data-ttu-id="91a67-148">データの一部をサービス インスタンスにマッピングする例は、データの一部 (オーダー ID など) を特定のワークフロー インスタンスにマップするコンテンツ ベースの相関関係です。</span><span class="sxs-lookup"><span data-stu-id="91a67-148">An example of mapping a piece of data to a service instance is content-based correlation which maps a piece of data (for example, an order ID) to a particular workflow instance.</span></span>

  - <span data-ttu-id="91a67-149">任意のメッセージング アクティビティで、`CorrelationInitializers` プロパティをクリックし、上記で作成した <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 変数を使用して <xref:System.ServiceModel.Activities.CorrelationHandle> を追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-149">On any messaging activity, click on the `CorrelationInitializers` property and add a <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> using the <xref:System.ServiceModel.Activities.CorrelationHandle> variable created above.</span></span> <span data-ttu-id="91a67-150">ドロップダウン メニューで、メッセージ上の目的のプロパティ (OrderID など) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="91a67-150">Double-click on the desired property on the message (e.g. OrderID) from the drop-down menu.</span></span> <span data-ttu-id="91a67-151">`CorrelatesWith` プロパティを上記で使用した <xref:System.ServiceModel.Activities.CorrelationHandle> 変数に設定します。</span><span class="sxs-lookup"><span data-stu-id="91a67-151">Set the `CorrelatesWith` property to the <xref:System.ServiceModel.Activities.CorrelationHandle> variable used above.</span></span>

- [<span data-ttu-id="91a67-152">相関関係の概念説明ドキュメント</span><span class="sxs-lookup"><span data-stu-id="91a67-152">Correlation Conceptual Documentation</span></span>](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a><span data-ttu-id="91a67-153">相関関係のシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-153">Correlation Scenario</span></span>

<span data-ttu-id="91a67-154">注文処理ワークフローは、新しい注文の作成や、処理中の既存の注文の更新を処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-154">An order-processing workflow is used to handle new order creation and updating existing orders that are in process.</span></span> <span data-ttu-id="91a67-155">このシナリオを実装するには、でワークフローをホストし、メッセージングアクティビティを使用する必要があり <xref:System.ServiceModel.WorkflowServiceHost> ます。</span><span class="sxs-lookup"><span data-stu-id="91a67-155">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost> and use the messaging activities.</span></span> <span data-ttu-id="91a67-156">また、 `orderId` 適切なワークフローに更新が行われるように、に基づく相関関係も必要です。</span><span class="sxs-lookup"><span data-stu-id="91a67-156">It would also require correlation based on the `orderId` to ensure that updates are made to the correct workflow.</span></span>

## <a name="simplified-configuration"></a><span data-ttu-id="91a67-157">簡略化された構成</span><span class="sxs-lookup"><span data-stu-id="91a67-157">Simplified Configuration</span></span>

<span data-ttu-id="91a67-158">WCF 構成スキーマは複雑であり、ユーザーはさまざまな機能を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="91a67-158">The WCF configuration schema is complex and provides users with many hard to find features.</span></span> <span data-ttu-id="91a67-159">では [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 、WCF ユーザーが次の機能を使用してサービスを構成する方法について重点的に説明しました。</span><span class="sxs-lookup"><span data-stu-id="91a67-159">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], we have focused on helping WCF users configure their services with the following features:</span></span>

- <span data-ttu-id="91a67-160">サービスごとの明示的な構成の必要性をなくします。</span><span class="sxs-lookup"><span data-stu-id="91a67-160">Removing the need for explicit per-service configuration.</span></span> <span data-ttu-id="91a67-161">サービスに対してサービス> 要素を構成せず、サービスがプログラムを使用して \< エンドポイントを定義していない場合、エンドポイントのセットがサービスに自動的に追加されます。サービスによって実装されるサービスベースアドレスとコントラクトごとに、一連のエンドポイントが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-161">If you do not configure any \<service> elements for your service, and your service does not define programmatically any endpoint, then a set of endpoints will be automatically added to your service, one per service base address and per contract implemented by your service.</span></span>

- <span data-ttu-id="91a67-162">明示的な構成のないサービスに適用される WCF バインディングおよび動作の既定値をユーザーが定義できるようにします。</span><span class="sxs-lookup"><span data-stu-id="91a67-162">Enables the user to define default values for WCF bindings and behaviors, which will be applied to services with no explicit configuration.</span></span>

- <span data-ttu-id="91a67-163">標準のエンドポイントは、事前に構成された再利用可能なエンドポイントを定義します。このエンドポイントは、1 つ以上のエンドポイント プロパティ (アドレス、バインド、およびコントラクト) に対して固定値を持ち、カスタム プロパティを定義できるようにします。</span><span class="sxs-lookup"><span data-stu-id="91a67-163">Standard endpoints define reusable preconfigured endpoints, which have fixed values for one or more of the endpoint properties (address, binding and contract), and allow defining custom properties.</span></span>

- <span data-ttu-id="91a67-164">最後に、を <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 使用すると、アプリケーションドメインの読み込み時間の後に構成が選択または変更された場合に役立つ、WCF クライアント構成の中央管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="91a67-164">Finally, the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows you to do central management of WCF client configuration, useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-165">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-165">Getting Started</span></span>

- <span data-ttu-id="91a67-166">[WCF 4.0 開発者ガイド](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="91a67-166">[A Developer's Guide to WCF 4.0](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))</span></span>

- [<span data-ttu-id="91a67-167">構成チャネル ファクトリ</span><span class="sxs-lookup"><span data-stu-id="91a67-167">Configuration Channel Factory</span></span>](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [<span data-ttu-id="91a67-168">標準エンドポイント要素</span><span class="sxs-lookup"><span data-stu-id="91a67-168">Standard Endpoint Element</span></span>](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [<span data-ttu-id="91a67-169">.NET Framework 4 のサービス構成の機能強化</span><span class="sxs-lookup"><span data-stu-id="91a67-169">Service configuration improvements in .NET Framework 4</span></span>](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [<span data-ttu-id="91a67-170">.NET 4 でよくあるユーザーの誤り: WF/WCF サービス構成名の入力ミス</span><span class="sxs-lookup"><span data-stu-id="91a67-170">Common User Mistake in .NET 4: Mistyping the WF/WCF Service Configuration Name</span></span>](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a><span data-ttu-id="91a67-171">簡略化された構成のシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-171">Simplified Configuration Scenarios</span></span>

- <span data-ttu-id="91a67-172">経験豊富な ASMX 開発者は、WCF の使用を開始したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="91a67-172">An experienced ASMX developer wants to start using WCF.</span></span> <span data-ttu-id="91a67-173">しかし、WCF はあまり複雑ではないように思えます。</span><span class="sxs-lookup"><span data-stu-id="91a67-173">However, WCF seems way too complicated!</span></span> <span data-ttu-id="91a67-174">構成ファイルに書き込む必要のある情報は何ですか。</span><span class="sxs-lookup"><span data-stu-id="91a67-174">What is all that information that I need to write in a configuration file?</span></span> <span data-ttu-id="91a67-175">.NET 4 では、構成ファイルをまったく使用しないこともできます。</span><span class="sxs-lookup"><span data-stu-id="91a67-175">In .NET 4, you can even decide to not have a configuration file at all.</span></span>

- <span data-ttu-id="91a67-176">既存の WCF サービスのセットは構成とメンテナンスが非常に困難です。</span><span class="sxs-lookup"><span data-stu-id="91a67-176">An existing set of WCF services are very difficult to configure and maintain.</span></span> <span data-ttu-id="91a67-177">構成ファイルには、変更するのが非常に危険な XML コードが何千行もあります。</span><span class="sxs-lookup"><span data-stu-id="91a67-177">The configuration file has thousands of lines of XML code that are extremely dangerous to touch.</span></span> <span data-ttu-id="91a67-178">コード量を管理しやすい量に減らすための支援が必要です。</span><span class="sxs-lookup"><span data-stu-id="91a67-178">Help is needed to reduce that amount of code to something more manageable.</span></span>

## <a name="data-contract-resolver"></a><span data-ttu-id="91a67-179">データ コントラクト リゾルバー</span><span class="sxs-lookup"><span data-stu-id="91a67-179">Data Contract Resolver</span></span>

<span data-ttu-id="91a67-180">.NET 3.5 では、既知の型の設計にはいくつかの制限がありました。</span><span class="sxs-lookup"><span data-stu-id="91a67-180">In .NET 3.5, there were a few limitations in the design of known types:</span></span>

- <span data-ttu-id="91a67-181">シリアル化または逆シリアル化中に既知の型を動的に追加することはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="91a67-181">Adding known types dynamically, during serialization or deserialization, was not possible.</span></span>

- <span data-ttu-id="91a67-182">シリアライザーは不明な xsi:type の情報を処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="91a67-182">Serializers could not deal with unknown xsi:type information.</span></span>

- <span data-ttu-id="91a67-183">ユーザーは、ネットワーク上のシリアル化インスタンスのサイズを小さくするなど、ネットワーク上に出現する xsi:type を指定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="91a67-183">It was not possible for users to specify what xsi:type they would like to have appear on the wire to, for instance, make the size of a serialization instance on the wire smaller.</span></span>

<span data-ttu-id="91a67-184">[DataContractResolver](../wcf/samples/datacontractresolver.md)は、これらの問題を .net 4.5 で解決します。</span><span class="sxs-lookup"><span data-stu-id="91a67-184">The [DataContractResolver](../wcf/samples/datacontractresolver.md) solves these issues in .NET 4.5.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-185">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-185">Getting Started</span></span>

- [<span data-ttu-id="91a67-186">データ コントラクト リゾルバー API のドキュメント</span><span class="sxs-lookup"><span data-stu-id="91a67-186">Data Contract Resolver API documentation</span></span>](xref:System.Runtime.Serialization.DataContractResolver)

- [<span data-ttu-id="91a67-187">データ コントラクト リゾルバーの概要</span><span class="sxs-lookup"><span data-stu-id="91a67-187">Introducing the Data Contract Resolver</span></span>](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- <span data-ttu-id="91a67-188">サンプル:</span><span class="sxs-lookup"><span data-stu-id="91a67-188">Samples:</span></span>

  - [<span data-ttu-id="91a67-189">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="91a67-189">DataContractResolver</span></span>](../wcf/samples/datacontractresolver.md)

  - [<span data-ttu-id="91a67-190">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="91a67-190">KnownAssemblyAttribute</span></span>](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a><span data-ttu-id="91a67-191">データ コントラクト リゾルバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-191">Data Contract Resolver Scenarios</span></span>

- <span data-ttu-id="91a67-192">数十の <xref:System.Runtime.Serialization.KnownTypeAttribute> オブジェクトをサービスで宣言する必要性の回避。</span><span class="sxs-lookup"><span data-stu-id="91a67-192">Avoiding having to declare tens of <xref:System.Runtime.Serialization.KnownTypeAttribute> objects in a service.</span></span>

- <span data-ttu-id="91a67-193">XML BLOB のサイズの削減。</span><span class="sxs-lookup"><span data-stu-id="91a67-193">Reducing the size of the XML blob.</span></span>

## <a name="flowchart"></a><span data-ttu-id="91a67-194">フローチャート</span><span class="sxs-lookup"><span data-stu-id="91a67-194">Flowchart</span></span>

<span data-ttu-id="91a67-195">フローチャートは、ドメインの問題を視覚的に表すための既知のパラダイムです。</span><span class="sxs-lookup"><span data-stu-id="91a67-195">Flowchart is a well-known paradigm to visually represent domain problems.</span></span> <span data-ttu-id="91a67-196">これは、.NET 4 で導入されている新しい制御フロースタイルです。</span><span class="sxs-lookup"><span data-stu-id="91a67-196">It is a new control flow style we're introducing in .NET 4.</span></span> <span data-ttu-id="91a67-197">フローチャートの主な特性は、一度に 1 つのアクティビティのみ実行されることです。</span><span class="sxs-lookup"><span data-stu-id="91a67-197">A core characteristic of Flowchart is that only one activity is executed at any given time.</span></span> <span data-ttu-id="91a67-198">フローチャートはループと代替結果を表すことができますが、その性質上、複数ノードの同時実行を表すことはできません。</span><span class="sxs-lookup"><span data-stu-id="91a67-198">Flowcharts can express loops and alternative outcomes, but cannot natively express concurrent execution of multiple nodes.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-199">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-199">Getting Started</span></span>

- <span data-ttu-id="91a67-200">Visual Studio 2012 で、ワークフローコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-200">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="91a67-201">ワークフロー デザイナーにフローチャートを追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-201">Add a Flowchart in the workflow designer.</span></span>

- <span data-ttu-id="91a67-202">フローチャート機能では、次のクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="91a67-202">The flowchart feature uses the following classes:</span></span>

  - <xref:System.Activities.Statements.Flowchart>

  - <xref:System.Activities.Statements.FlowNode>

  - <xref:System.Activities.Statements.FlowDecision>

  - <xref:System.Activities.Statements.FlowStep>

  - <xref:System.Activities.Statements.FlowSwitch%601>

- <span data-ttu-id="91a67-203">サンプル:</span><span class="sxs-lookup"><span data-stu-id="91a67-203">Samples:</span></span>

  - [<span data-ttu-id="91a67-204">TryCatch を使用した Flowchart アクティビティでのエラー処理</span><span class="sxs-lookup"><span data-stu-id="91a67-204">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

  - [<span data-ttu-id="91a67-205">雇用プロセス</span><span class="sxs-lookup"><span data-stu-id="91a67-205">Hiring Process</span></span>](./samples/hiring-process.md)

- <span data-ttu-id="91a67-206">デザイナー ドキュメント:</span><span class="sxs-lookup"><span data-stu-id="91a67-206">Designer Documentation:</span></span>

  - [<span data-ttu-id="91a67-207">フローチャートアクティビティデザイナー</span><span class="sxs-lookup"><span data-stu-id="91a67-207">Flowchart Activity Designers</span></span>](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a><span data-ttu-id="91a67-208">フローチャートのシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-208">Flowchart Scenarios</span></span>

<span data-ttu-id="91a67-209">フローチャート アクティビティを使用して推測ゲームを実装できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-209">A flowchart activity can be used to implement a guessing game.</span></span> <span data-ttu-id="91a67-210">推測ゲームは非常に単純です。コンピューターによってランダムな数値が選択され、プレーヤーはその数値を推測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-210">The guessing game is very simple: the computer selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="91a67-211">プレーヤーが各推測を送信すると、コンピューターにヒントが表示されます ("小さい数値を試す" など)。</span><span class="sxs-lookup"><span data-stu-id="91a67-211">When the player submits each guess, the computer shows them a hint (i.e. "try a lower number").</span></span> <span data-ttu-id="91a67-212">プレーヤーが7回未満で数値を検出した場合、コンピューターから特別な祝福を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="91a67-212">If the player finds the number in less than 7 attempts, they receive a special congratulation from the computer.</span></span> <span data-ttu-id="91a67-213">このゲームは、次の手続き型アクティビティの組み合わせで実装できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-213">This game can be implemented with a combination of the following procedural activities:</span></span>

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a><span data-ttu-id="91a67-214">手続き型アクティビティ (Sequence、If、ForEach、Switch、Assign、DoWhile、While)</span><span class="sxs-lookup"><span data-stu-id="91a67-214">Procedural activities (Sequence, If, ForEach, Switch, Assign, DoWhile, While)</span></span>

<span data-ttu-id="91a67-215">手続き型アクティビティは、プログラマになじみのある概念を使用してシーケンシャル制御フローをモデル化するメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="91a67-215">Procedural activities provide a mechanism to model sequential control flow using concepts that are familiar to programmers.</span></span> <span data-ttu-id="91a67-216">これらのアクティビティは、従来の構造化プログラミング言語構成要素を有効にします。また、必要に応じて、C# や Visual Basic などの一般的な手続き型言語と言語の同等性を提供します。</span><span class="sxs-lookup"><span data-stu-id="91a67-216">These activities enable traditionally structured programming language constructs and, when appropriate, provide language parity with common procedural languages such as C# and Visual Basic.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-217">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-217">Getting Started</span></span>

- <span data-ttu-id="91a67-218">Visual Studio 2012 で、ワークフローコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-218">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="91a67-219">ワークフロー デザイナーで、手続き型アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-219">Add procedural activities in the workflow designer.</span></span>

- <span data-ttu-id="91a67-220">サンプル:</span><span class="sxs-lookup"><span data-stu-id="91a67-220">Samples:</span></span>

  - [<span data-ttu-id="91a67-221">雇用プロセス</span><span class="sxs-lookup"><span data-stu-id="91a67-221">Hiring Process</span></span>](./samples/hiring-process.md)

  - [<span data-ttu-id="91a67-222">企業の購買プロセス</span><span class="sxs-lookup"><span data-stu-id="91a67-222">Corporate Purchase Process</span></span>](./samples/corporate-purchase-process.md)

- <span data-ttu-id="91a67-223">デザイナー ドキュメント:</span><span class="sxs-lookup"><span data-stu-id="91a67-223">Designer Documentation:</span></span>

  - [<span data-ttu-id="91a67-224">Parallel アクティビティ デザイナー</span><span class="sxs-lookup"><span data-stu-id="91a67-224">Parallel Activity Designer</span></span>](/visualstudio/workflow-designer/parallel-activity-designer)

  - [<span data-ttu-id="91a67-225">ParallelForEach \< T> アクティビティデザイナー</span><span class="sxs-lookup"><span data-stu-id="91a67-225">ParallelForEach\<T> Activity Designer</span></span>](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a><span data-ttu-id="91a67-226">手続き型アクティビティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-226">Procedural Activity Scenarios</span></span>

- <span data-ttu-id="91a67-227"><xref:System.Activities.Statements.Parallel>: イントラネットドキュメント管理システムには、ドキュメント承認ワークフローがあります。</span><span class="sxs-lookup"><span data-stu-id="91a67-227"><xref:System.Activities.Statements.Parallel>: An intranet document management system has a document approval workflow.</span></span> <span data-ttu-id="91a67-228">ドキュメントは、イントラネットに公開する前に、複数の部門の担当者によって承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-228">Documents need to be approved by people in several departments before they can be published to the intranet.</span></span> <span data-ttu-id="91a67-229">承認の順序が確立されていません。ドキュメントが "承認の保留中" フェーズにある間はいつでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-229">There isn't an established order for the approvals; they can occur at any time while the document is in the "approval pending" phase.</span></span> <span data-ttu-id="91a67-230">ユーザーがドキュメントをレビュー用に送信する場合、そのドキュメントは、直属の上司、イントラネット管理者、および内部通信マネージャーによって承認されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-230">When a user submits a document for review, it must be approved by their direct manager, the intranet administrator, and the internal communications manager.</span></span>

- <span data-ttu-id="91a67-231"><xref:System.Activities.Statements.ParallelForEach%601>: WF アプリケーションは、大規模企業内での企業購買を管理します。</span><span class="sxs-lookup"><span data-stu-id="91a67-231"><xref:System.Activities.Statements.ParallelForEach%601>: A WF application manages corporate buys within a large company.</span></span> <span data-ttu-id="91a67-232">企業の規則では、購買作業を計画する前に 3 社の異なるベンダーを評価する必要があると規定されています。</span><span class="sxs-lookup"><span data-stu-id="91a67-232">The corporate rules dictate that before planning any purchase operation, the valuations of three different vendors is required.</span></span> <span data-ttu-id="91a67-233">購入部署の従業員は、会社の仕入先リストから3つの仕入先を選択します。</span><span class="sxs-lookup"><span data-stu-id="91a67-233">An employee from the buying department selects three vendors from the company's vendor list.</span></span> <span data-ttu-id="91a67-234">これらのベンダーを選択し、通知した後で、企業は経済提案書を待ちます。</span><span class="sxs-lookup"><span data-stu-id="91a67-234">After these vendors have been selected and notified, the company will wait for their economic proposals.</span></span> <span data-ttu-id="91a67-235">提案書は任意の順序で到着します。</span><span class="sxs-lookup"><span data-stu-id="91a67-235">The proposals can come in any order.</span></span> <span data-ttu-id="91a67-236">WF でこのシナリオを実装するには、ベンダーのコレクションを反復処理して経済提案書を求める <xref:System.Activities.Statements.ParallelForEach%601> を使用します。</span><span class="sxs-lookup"><span data-stu-id="91a67-236">To implement this scenario in WF, we use a <xref:System.Activities.Statements.ParallelForEach%601> that will iterate through our collection of vendors and ask for their economic proposals.</span></span> <span data-ttu-id="91a67-237">すべての提案が収集された後で、最良の提案が選択されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-237">After all offers are gathered, the best one is selected and displayed.</span></span>

## <a name="invokemethod"></a><span data-ttu-id="91a67-238">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="91a67-238">InvokeMethod</span></span>

<span data-ttu-id="91a67-239"><xref:System.Activities.Statements.InvokeMethod> アクティビティでは、オブジェクト内のパブリック メソッドまたはスコープ内の型を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="91a67-239">The <xref:System.Activities.Statements.InvokeMethod> activity allows invoking public methods in objects or types in scope.</span></span> <span data-ttu-id="91a67-240">パラメーター付きまたはパラメーターなし (パラメーター配列を含む) でのインスタンス メソッドおよび静的メソッドの呼び出し、および汎用メソッドの呼び出しがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="91a67-240">It supports invoking instance and static methods with or without parameters (including parameter arrays), and generic methods.</span></span> <span data-ttu-id="91a67-241">メソッドを同期および非同期で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="91a67-241">It also allows executing method synchronously and asynchronously.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-242">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-242">Getting Started</span></span>

- <span data-ttu-id="91a67-243">Visual Studio 2012 で、ワークフローコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-243">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="91a67-244">ワークフロー デザイナーに <xref:System.Activities.Statements.InvokeMethod> アクティビティを追加し、そこに静的メソッドとインスタンス メソッドを構成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-244">Add an <xref:System.Activities.Statements.InvokeMethod> activity in the workflow designer, and configure static and instance methods on it.</span></span>

- <span data-ttu-id="91a67-245">デザイナードキュメント: [InvokeMethod アクティビティデザイナー](/visualstudio/workflow-designer/invokemethod-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="91a67-245">Designer Documentation: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)</span></span>

### <a name="invokemethod-scenarios"></a><span data-ttu-id="91a67-246">InvokeMethod のシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-246">InvokeMethod Scenarios</span></span>

- <span data-ttu-id="91a67-247">スコープ内のオブジェクトのメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-247">A method in an object in scope needs to be invoked.</span></span> <span data-ttu-id="91a67-248">たとえば、辞書に値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-248">For example, a value needs to be added to a dictionary.</span></span> <span data-ttu-id="91a67-249">辞書のインスタンスの Add メソッドが呼び出され、キーと値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-249">The Add method of the instance of the dictionary is invoked, and the key and value are provided.</span></span>

- <span data-ttu-id="91a67-250">レガシー CLR オブジェクトに対してメソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-250">A method needs to be invoked on a legacy CLR object.</span></span> <span data-ttu-id="91a67-251">カスタム アクティビティを作成してそのレガシー クラスの呼び出しをラップする代わりに、ワークフロー実行中にそのクラスがスコープ内にある場合には <xref:System.Activities.Statements.InvokeMethod> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-251">Instead of creating a custom activity to wrap the call to that legacy class, if it is in scope during the workflow execution, <xref:System.Activities.Statements.InvokeMethod> can be used.</span></span>

## <a name="error-handling-activities"></a><span data-ttu-id="91a67-252">エラー処理アクティビティ</span><span class="sxs-lookup"><span data-stu-id="91a67-252">Error handling activities</span></span>

<span data-ttu-id="91a67-253">アクティビティは、 <xref:System.Activities.Statements.TryCatch> 含まれているアクティビティのセットの実行中に発生した例外をキャッチするためのメカニズムを提供します (C# の Try/Catch コンストラクトや Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="91a67-253">The <xref:System.Activities.Statements.TryCatch> activity provides a mechanism for catching exceptions that occur during the execution of a set of contained activities (similar to the Try/Catch construct in C# and Visual Basic).</span></span> <span data-ttu-id="91a67-254"><xref:System.Activities.Statements.TryCatch> はワークフロー レベルの例外処理を提供します。</span><span class="sxs-lookup"><span data-stu-id="91a67-254"><xref:System.Activities.Statements.TryCatch> provides exception handling at the workflow level.</span></span> <span data-ttu-id="91a67-255">未処理の例外がスローされると、ワークフローは中止され、Finally ブロックは実行されません。</span><span class="sxs-lookup"><span data-stu-id="91a67-255">When an unhandled exception is thrown, the workflow is aborted and the Finally block won't be executed.</span></span> <span data-ttu-id="91a67-256">この動作は C# と一貫性があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-256">This behavior is consistent with C#.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-257">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-257">Getting Started</span></span>

- <span data-ttu-id="91a67-258">Visual Studio 2012 で、ワークフローコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-258">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="91a67-259">ワークフロー デザイナーで <xref:System.Activities.Statements.TryCatch> アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-259">Add a <xref:System.Activities.Statements.TryCatch> activity in the workflow designer.</span></span>

- <span data-ttu-id="91a67-260">サンプル: [TryCatch を使用した Flowchart アクティビティでのエラー処理](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-260">Sample: [Fault Handling in a Flowchart Activity Using TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)</span></span>

- <span data-ttu-id="91a67-261">デザイナードキュメント:[エラー処理アクティビティデザイナー](/visualstudio/workflow-designer/error-handling-activity-designers)</span><span class="sxs-lookup"><span data-stu-id="91a67-261">Designer Documentation: [Error Handling Activity Designers](/visualstudio/workflow-designer/error-handling-activity-designers)</span></span>

### <a name="error-handling-scenarios"></a><span data-ttu-id="91a67-262">エラー処理のシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-262">Error handling scenarios</span></span>

<span data-ttu-id="91a67-263">アクティビティのセットを実行する必要があり、エラーの発生時に特定のロジックを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-263">A set of activities needs to be executed, and specific logic needs to be executed when an error occurs.</span></span> <span data-ttu-id="91a67-264">そのエラー処理ロジック中にエラーが回復不能であることがわかった場合は、例外が再スローされ、親アクティビティ (またはホスト) によって問題が処理されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-264">If during that error handling logic it is found that the error is not recoverable, the exception will be rethrown, and the parent activity (or the host) will deal with the problem.</span></span>

## <a name="pick-activity"></a><span data-ttu-id="91a67-265">Pick アクティビティ</span><span class="sxs-lookup"><span data-stu-id="91a67-265">Pick activity</span></span>

<span data-ttu-id="91a67-266"><xref:System.Activities.Statements.Pick> アクティビティは、WF でイベント ベースの制御フロー モデリングを提供します。</span><span class="sxs-lookup"><span data-stu-id="91a67-266">The <xref:System.Activities.Statements.Pick> Activity provides event-based control flow modeling in WF.</span></span> <span data-ttu-id="91a67-267"><xref:System.Activities.Statements.Pick> には、多数の分岐が含まれています。各分岐は、特定のイベントが発生すると実行されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-267"><xref:System.Activities.Statements.Pick> contains many branches where each branch waits for a particular event to occur before running.</span></span> <span data-ttu-id="91a67-268">この設定では、<xref:System.Activities.Statements.Pick> は、アクティビティがリッスンしているイベント セットの 1 つのみを実行する <xref:System.Activities.Statements.Switch%601> と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="91a67-268">In this setup, a <xref:System.Activities.Statements.Pick> behaves similar to a <xref:System.Activities.Statements.Switch%601> to which the Activity will execute only one of the set of events it is listening.</span></span> <span data-ttu-id="91a67-269">各分岐はイベント ドリブンなので、発生したイベントが対応する分岐を実行します。</span><span class="sxs-lookup"><span data-stu-id="91a67-269">Each branch is event driven and the event that occurs runs the corresponding branch first.</span></span> <span data-ttu-id="91a67-270">他のすべての分岐は、イベントのリッスンをキャンセルし、停止します。</span><span class="sxs-lookup"><span data-stu-id="91a67-270">All other branches cancel and stop listening for events.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-271">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-271">Getting Started</span></span>

- <span data-ttu-id="91a67-272">Visual Studio 2012 で、ワークフローコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-272">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="91a67-273">ワークフロー デザイナーで <xref:System.Activities.Statements.Pick> アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-273">Add a <xref:System.Activities.Statements.Pick> activity in the workflow designer.</span></span>

- <span data-ttu-id="91a67-274">サンプル: [Pick アクティビティの使用](./samples/using-the-pick-activity.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-274">Sample: [Using the Pick Activity](./samples/using-the-pick-activity.md)</span></span>

- <span data-ttu-id="91a67-275">デザイナードキュメント: [Pick アクティビティデザイナー](/visualstudio/workflow-designer/pick-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="91a67-275">Designer documentation: [Pick Activity Designer](/visualstudio/workflow-designer/pick-activity-designer)</span></span>

### <a name="pick-scenario"></a><span data-ttu-id="91a67-276">Pick のシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-276">Pick Scenario</span></span>

<span data-ttu-id="91a67-277">ユーザーに入力を求めるプロンプトを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-277">A user needs to be prompted for input.</span></span> <span data-ttu-id="91a67-278">通常の状況では、開発者はのようなメソッド呼び出しを使用し <xref:System.Console.ReadLine%2A> て、ユーザーの入力を要求します。</span><span class="sxs-lookup"><span data-stu-id="91a67-278">Under normal circumstances, the developer would use a method call like <xref:System.Console.ReadLine%2A> to prompt for a user's input.</span></span> <span data-ttu-id="91a67-279">この設定の問題は、ユーザーが何か入力するまでプログラムが待機することです。</span><span class="sxs-lookup"><span data-stu-id="91a67-279">The problem with this setup is that the program waits until the user enters something.</span></span> <span data-ttu-id="91a67-280">このシナリオでは、ブロッキング アクティビティのブロックを解除するためにタイムアウトが必要です。</span><span class="sxs-lookup"><span data-stu-id="91a67-280">In this scenario, a time-out is needed to unblock a blocking activity.</span></span> <span data-ttu-id="91a67-281">一般的なシナリオでは、特定の期間内にタスクが完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-281">A common scenario is one that requires a task to be completed within a given time duration.</span></span> <span data-ttu-id="91a67-282">ブロッキング アクティビティのタイムアウトは、Pick が大量の値を追加するシナリオです。</span><span class="sxs-lookup"><span data-stu-id="91a67-282">Timing out a blocking activity is a scenario where Pick adds a lot of value.</span></span>

## <a name="wcf-routing-service"></a><span data-ttu-id="91a67-283">WCF ルーティング サービス</span><span class="sxs-lookup"><span data-stu-id="91a67-283">WCF Routing Service</span></span>

<span data-ttu-id="91a67-284">ルーティングサービスは、WCF メッセージがクライアントとサービスの間でどのように流れるかを制御できる汎用的なソフトウェアルーターとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="91a67-284">The Routing Service is designed to be a generic software Router that allows you to control how WCF messages flow in between your clients and services.</span></span> <span data-ttu-id="91a67-285">ルーティングサービスを使用すると、サービスからクライアントを切り離すことができます。これにより、サポート可能な構成と、サービスをホストする方法を検討する際の柔軟性が大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="91a67-285">The Routing Service allows you to decouple your clients from your services, which gives you much more freedom in terms of the configurations that you can support and the flexibility you have when considering how to host your services.</span></span> <span data-ttu-id="91a67-286">.NET 3.5 では、クライアントとサービスが緊密に結合されていました。クライアントは、通信に必要なすべてのサービスとその場所を把握している必要がありました。</span><span class="sxs-lookup"><span data-stu-id="91a67-286">In .NET 3.5, clients and services were tightly coupled; a client had to know about all of the services it needed to talk to and where they were located.</span></span> <span data-ttu-id="91a67-287">さらに、.NET Framework 3.5 の WCF には次の制限がありました。</span><span class="sxs-lookup"><span data-stu-id="91a67-287">In addition, WCF in .NET Framework 3.5 had the following limitations:</span></span>

- <span data-ttu-id="91a67-288">ロジックをクライアントにハードコーディングする必要があったため、エラー処理が複雑でした。</span><span class="sxs-lookup"><span data-stu-id="91a67-288">Error handling was complex, as this logic had to be hard-coded into the client.</span></span>

- <span data-ttu-id="91a67-289">クライアントとサービスは常に同じバインディングを使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="91a67-289">Clients and services had to always use the same bindings.</span></span>

- <span data-ttu-id="91a67-290">サービスが適切に分類されていることはほとんどありませんでした。複数のサービス間で選択するよりも、クライアントがすべてを実装する 1 つのサービスと対話する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="91a67-290">Services were rarely well factored: it is easier to have the client talk to one service which implements everything, rather than needing to choose between multiple services.</span></span>

<span data-ttu-id="91a67-291">.NET 4 のルーティングサービスは、これらの問題を解決しやすくするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="91a67-291">The routing service in .NET 4 is designed to make these problems easier to solve.</span></span> <span data-ttu-id="91a67-292">新しいルーティング サービスには次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-292">The new routing service has the following features:</span></span>

1. <span data-ttu-id="91a67-293">コンテント ベースのルーティング (<xref:System.ServiceModel.Dispatcher.MessageFilter> オブジェクトがメッセージを調べて送信先を判断します。)</span><span class="sxs-lookup"><span data-stu-id="91a67-293">Content based routing (<xref:System.ServiceModel.Dispatcher.MessageFilter> objects examine a message to determine where it should be sent.)</span></span>

2. <span data-ttu-id="91a67-294">プロトコルブリッジング (トランスポート & メッセージ)</span><span class="sxs-lookup"><span data-stu-id="91a67-294">Protocol bridging (transport & message)</span></span>

3. <span data-ttu-id="91a67-295">エラー処理 (ルーターは、通信例外をキャッチし、バックアップ エンドポイントにフェールオーバーします)</span><span class="sxs-lookup"><span data-stu-id="91a67-295">Error handling (the router catches communication exceptions and fails over to backup endpoints)</span></span>

4. <span data-ttu-id="91a67-296"><xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> およびルーティング構成の動的 (メモリ内) 更新。</span><span class="sxs-lookup"><span data-stu-id="91a67-296">Dynamic (in memory) update of <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> and Routing Configuration.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-297">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-297">Getting Started</span></span>

1. <span data-ttu-id="91a67-298">ドキュメント:[ルーティング](../wcf/feature-details/routing.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-298">Documentation: [Routing](../wcf/feature-details/routing.md)</span></span>

2. <span data-ttu-id="91a67-299">サンプル:[ルーティングサービス &#91;WCF サンプル&#93;](../wcf/samples/routing-services.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-299">Samples: [Routing Services &#91;WCF Samples&#93;](../wcf/samples/routing-services.md)</span></span>

3. <span data-ttu-id="91a67-300">ブログ:[ルーティングルール](https://docs.microsoft.com/archive/blogs/RoutingRules/)</span><span class="sxs-lookup"><span data-stu-id="91a67-300">Blog: [Routing Rules!](https://docs.microsoft.com/archive/blogs/RoutingRules/)</span></span>

### <a name="routing-scenarios"></a><span data-ttu-id="91a67-301">ルーティング シナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-301">Routing Scenarios</span></span>

<span data-ttu-id="91a67-302">ルーティング サービスは、次のシナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="91a67-302">The routing service is useful in the following scenarios:</span></span>

- <span data-ttu-id="91a67-303">クライアントは、複数のサービスを直接アドレス指定することなく、これらのサービスと対話できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-303">Clients can talk to multiple services without having to address them all directly.</span></span>

- <span data-ttu-id="91a67-304">クライアントは、ルーティング先を判断するためにクライアント要求で追加のロジックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-304">Clients can perform additional logic on a client request to determine where to route it</span></span>

- <span data-ttu-id="91a67-305">クライアントをリファクタリングすることなく、クライアントが実行する操作を複数のサービス実装に分解します。</span><span class="sxs-lookup"><span data-stu-id="91a67-305">Decompose the operations a client performs into multiple service implementations without refactoring the client.</span></span>

- <span data-ttu-id="91a67-306">クライアントとサービスは、異なるセキュリティ設定の異なるバインディングで会話できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-306">Clients and services can speak different bindings with different security settings.</span></span>

- <span data-ttu-id="91a67-307">クライアントは、障害またはサービスの使用不能に対してより堅牢になることができます。</span><span class="sxs-lookup"><span data-stu-id="91a67-307">Clients can be enabled to be more robust against failure or the unavailability of services.</span></span>

## <a name="wcf-discovery"></a><span data-ttu-id="91a67-308">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="91a67-308">WCF Discovery</span></span>

<span data-ttu-id="91a67-309">WCF Discovery は、アプリケーションインフラストラクチャに検出メカニズムを組み込むことができるフレームワークテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="91a67-309">WCF Discovery is a framework technology that allows you to incorporate a discovery mechanism to your application infrastructure.</span></span> <span data-ttu-id="91a67-310">これを使用して、サービスを探索可能にし、サービスを検索するようにクライアントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-310">You can use this to make your service discoverable, and configure your clients to search for services.</span></span> <span data-ttu-id="91a67-311">クライアントはエンドポイントでハードコーディングする必要がなくなるため、アプリケーションはより堅牢になりフォールト トレランスが向上します。</span><span class="sxs-lookup"><span data-stu-id="91a67-311">Clients no longer need to be hard coded with endpoint, making your application more robust and fault tolerant.</span></span> <span data-ttu-id="91a67-312">探索は、アプリケーションに自動構成機能をビルドするための最適なプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="91a67-312">Discovery is the perfect platform to build auto-configuration capabilities into your application.</span></span>

<span data-ttu-id="91a67-313">製品は、WS-Discovery 標準の上に構築されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-313">The product is built on top of the WS-Discovery standard.</span></span> <span data-ttu-id="91a67-314">これは、相互運用、拡張、および汎用になるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="91a67-314">It's designed to be interoperable, extensible, and generic.</span></span> <span data-ttu-id="91a67-315">製品では 2 つの操作モードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="91a67-315">The product supports two modes of operation:</span></span>

1. <span data-ttu-id="91a67-316">マネージド: 既存のサービスに関する知識を持つエンティティがネットワーク上にあり、クライアントは情報を直接クエリします。</span><span class="sxs-lookup"><span data-stu-id="91a67-316">Managed: where there is an entity on the network knowledgeable about existing services, clients query it directly for information.</span></span> <span data-ttu-id="91a67-317">これは Active Directory に類似しています。</span><span class="sxs-lookup"><span data-stu-id="91a67-317">This is analogous to Active Directory.</span></span>

2. <span data-ttu-id="91a67-318">アドホック: クライアントはマルチキャスト メッセージを使用してサービスを特定します。</span><span class="sxs-lookup"><span data-stu-id="91a67-318">Ad-hoc: where clients use multicast messages to locate services.</span></span>

<span data-ttu-id="91a67-319">さらに、探索メッセージはネットワーク プロトコルに依存しません。モード要件をサポートする任意のプロトコル上でこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-319">Furthermore, discovery messages are network protocol agnostic; you can use them on top any protocol that supports the mode requirements.</span></span> <span data-ttu-id="91a67-320">たとえば、検出マルチキャストメッセージは、UDP チャネルまたはマルチキャストメッセージングをサポートするその他のネットワーク経由で送信できます。</span><span class="sxs-lookup"><span data-stu-id="91a67-320">For example, discovery multicast messages can be sent over the UDP channel or any other network that supports multicast messaging.</span></span> <span data-ttu-id="91a67-321">これらの設計ポイントと機能の柔軟性を組み合わせることにより、ソリューションに対する検出を具体的に適合させることができます。</span><span class="sxs-lookup"><span data-stu-id="91a67-321">These design points, combined with feature flexibility, allow you to adapt the discovery specifically to your solution.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-322">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-322">Getting Started</span></span>

- <span data-ttu-id="91a67-323">ドキュメント: [WCF 検出](../wcf/feature-details/wcf-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-323">Documentation: [WCF Discovery](../wcf/feature-details/wcf-discovery.md)</span></span>

- <span data-ttu-id="91a67-324">サンプル:[検出 (サンプル)](../wcf/samples/discovery-samples.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-324">Samples: [Discovery (Samples)](../wcf/samples/discovery-samples.md)</span></span>

### <a name="discovery-scenarios"></a><span data-ttu-id="91a67-325">探索のシナリオ</span><span class="sxs-lookup"><span data-stu-id="91a67-325">Discovery Scenarios</span></span>

<span data-ttu-id="91a67-326">サービスがいつ使用可能になるかが不明なため、開発者はエンドポイントのハードコーディングを望みません。</span><span class="sxs-lookup"><span data-stu-id="91a67-326">A developer doesn't want to hard code endpoints, since it is unknown when my service will be available.</span></span> <span data-ttu-id="91a67-327">代わりに、開発者は実行時にサービスを選択することを望んでいます。</span><span class="sxs-lookup"><span data-stu-id="91a67-327">Instead, the developer wants to choose a service at runtime.</span></span> <span data-ttu-id="91a67-328">アプリケーションのコンポーネント間に、切り離し、堅牢性、および自動構成がさらに必要です。</span><span class="sxs-lookup"><span data-stu-id="91a67-328">More decoupling, robustness, and auto-configuration is needed between the components in the application.</span></span>

## <a name="tracking"></a><span data-ttu-id="91a67-329">追跡</span><span class="sxs-lookup"><span data-stu-id="91a67-329">Tracking</span></span>

<span data-ttu-id="91a67-330">ワークフロー追跡は、ワークフローインスタンスの実行に関する洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="91a67-330">Workflow tracking provides insight into the execution of a workflow instance.</span></span> <span data-ttu-id="91a67-331">追跡イベントは、ワークフローインスタンスレベルでワークフローから生成され、ワークフロー内のアクティビティが実行されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-331">The tracking events are emitted from a workflow at the workflow instance level and when activities within the workflow execute.</span></span> <span data-ttu-id="91a67-332">追跡レコードを定期受信するにはワークフロー追跡参加要素をワークフロー ホストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a67-332">A workflow tracking participant needs to be added to the workflow host to subscribe to tracking records.</span></span> <span data-ttu-id="91a67-333">追跡レコードは、追跡プロファイルを使用してフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-333">The tracking records are filtered using a tracking profile.</span></span> <span data-ttu-id="91a67-334">.NET Framework には ETW (Windows イベントトレーシング) 追跡参加要素が用意されており、基本プロファイルは machine.config ファイルにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="91a67-334">The .NET Framework provides an ETW (Event Tracing for Windows) tracking participant, and a basic profile is installed in the machine.config file.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-335">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-335">Getting Started</span></span>

1. <span data-ttu-id="91a67-336">Visual Studio 2010 で、WCF ワークフロー サービス アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a67-336">In Visual Studio 2010, create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="91a67-337">開始するキャンバスに <xref:System.ServiceModel.Activities.Receive> と <xref:System.ServiceModel.Activities.SendReply> のペアが配置されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-337">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas to start.</span></span>

2. <span data-ttu-id="91a67-338">web.config を開き、プロファイルなしで ETW 追跡動作を追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-338">Open the web.config and add an ETW tracking behavior with no profile.</span></span>

    1. <span data-ttu-id="91a67-339">既定のプロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="91a67-339">The default profile is used.</span></span>

    2. <span data-ttu-id="91a67-340">イベントビューアーを開き、[**イベントビューアー**]、[**アプリケーションとサービスログ**]、[ **Microsoft**]、[ **Windows**]、[**アプリケーションサーバー-アプリケーション**] の各ノードで分析チャネルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="91a67-340">Open event viewer and enable the analytic channel in the following node: **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="91a67-341">[**分析**] を右クリックし、[**ログを有効にする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="91a67-341">Right-click **Analytic** and select **Enable Log**.</span></span>

    3. <span data-ttu-id="91a67-342">ワークフロー サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="91a67-342">Run the workflow service.</span></span>

    4. <span data-ttu-id="91a67-343">イベント ビューアーでワークフロー追跡イベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="91a67-343">Observe the workflow tracking events in event viewer.</span></span>

3. <span data-ttu-id="91a67-344">サンプル:[追跡](./samples/tracking.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-344">Samples: [Tracking](./samples/tracking.md)</span></span>

4. <span data-ttu-id="91a67-345">概念説明のドキュメント:[ワークフローの追跡とトレース](workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="91a67-345">Conceptual documentation: [Workflow Tracking and Tracing](workflow-tracking-and-tracing.md)</span></span>

## <a name="sql-workflow-instance-store"></a><span data-ttu-id="91a67-346">SQL Workflow Instance Store</span><span class="sxs-lookup"><span data-stu-id="91a67-346">SQL Workflow Instance Store</span></span>

<span data-ttu-id="91a67-347"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> は、SQL Server ベースのインスタンス ストアの実装です。</span><span class="sxs-lookup"><span data-stu-id="91a67-347">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is a SQL Server-based implementation of an instance store.</span></span> <span data-ttu-id="91a67-348">インスタンス ストアは、実行中のインスタンスの状態を、そのインスタンスの読み込みと再開に必要なすべてのデータと共に格納します。</span><span class="sxs-lookup"><span data-stu-id="91a67-348">An instance store stores the state of a running instance together with all data necessary to load and resume that instance.</span></span> <span data-ttu-id="91a67-349">サービス ホストは、ワークフローが永続的な場合にインスタンス状態を保存するようインスタンス ストアに指示し、そのインスタンスのメッセージが到着するか遅延アクティビティが期限切れになったときにインスタンス状態を読み込むようインスタンス ストアに指示します。</span><span class="sxs-lookup"><span data-stu-id="91a67-349">The service host instructs the instance store to save the instance state if the workflow persists, and it instructs the instance store to load the instance state when a message arrives for that instance or a delay activity expires.</span></span>

### <a name="getting-started"></a><span data-ttu-id="91a67-350">はじめに</span><span class="sxs-lookup"><span data-stu-id="91a67-350">Getting Started</span></span>

1. <span data-ttu-id="91a67-351">Visual Studio 2012 で、暗黙的または明示的なアクティビティを含むワークフローを作成し <xref:System.Activities.Statements.Persist> ます。</span><span class="sxs-lookup"><span data-stu-id="91a67-351">In Visual Studio 2012, create a Workflow that contains an implicit or explicit <xref:System.Activities.Statements.Persist> activity.</span></span> <span data-ttu-id="91a67-352"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 動作をワークフロー サービス ホストに追加します。</span><span class="sxs-lookup"><span data-stu-id="91a67-352">Add the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> behavior to your workflow service host.</span></span> <span data-ttu-id="91a67-353">これはコードまたはアプリケーション構成ファイルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="91a67-353">This can be done in code or in the application configuration file.</span></span>

2. <span data-ttu-id="91a67-354">サンプル:[永続](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))化</span><span class="sxs-lookup"><span data-stu-id="91a67-354">Samples: [Persistence](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))</span></span>

3. <span data-ttu-id="91a67-355">概念説明のドキュメント: [SQL Workflow Instance Store](sql-workflow-instance-store.md)。</span><span class="sxs-lookup"><span data-stu-id="91a67-355">Conceptual documentation: [SQL Workflow Instance Store](sql-workflow-instance-store.md).</span></span>
