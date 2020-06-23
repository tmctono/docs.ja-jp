---
title: '方法: マネージド アプリケーションで WCF サービスをホストする'
description: 自己ホスト型サービスを作成してテストすることによって、マネージアプリケーション内で WCF サービスをホストする方法について説明します。
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246169"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="8f8ad-103">方法: マネージアプリで WCF サービスをホストする</span><span class="sxs-lookup"><span data-stu-id="8f8ad-103">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="8f8ad-104">マネージド アプリケーションでサービスをホストするには、マネージド アプリケーション コード内にサービスのコードを埋め込み、サービスのエンドポイントをコードで強制的に定義するか、構成を使用して宣言により定義してから、または既定のエンドポイントを使用して、<xref:System.ServiceModel.ServiceHost> のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-104">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="8f8ad-105">メッセージの受信を開始するには、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-105">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="8f8ad-106">これにより、サービスのリスナーが作成されて開きます。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-106">This creates and opens the listener for the service.</span></span> <span data-ttu-id="8f8ad-107">この方法によるサービスのホストは、マネージド アプリケーション自体がホスト作業を行うため、"自己ホスト" と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-107">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="8f8ad-108">サービスを閉じるには、<xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> で <xref:System.ServiceModel.ServiceHost> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-108">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="8f8ad-109">サービスは、マネージド Windows サービス、インターネット インフォメーション サービス (IIS)、または Windows プロセス アクティブ化サービス (WAS) でホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-109">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="8f8ad-110">サービスのホスティングオプションの詳細については、「[ホスティングサービス](hosting-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-110">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="8f8ad-111">マネージド アプリケーションでのサービスのホスティングは、展開するインフラストラクチャが最小限で済むため、最も柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-111">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="8f8ad-112">マネージアプリケーションでのホスティングサービスの詳細については、「[マネージアプリケーションでのホスティング](./feature-details/hosting-in-a-managed-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-112">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="8f8ad-113">次の手順では、自己ホスト型サービスをコンソール アプリケーションに実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-113">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="8f8ad-114">自己ホスト型サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="8f8ad-114">Create a self-hosted service</span></span>

1. <span data-ttu-id="8f8ad-115">新しいコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-115">Create a new console application:</span></span>

   1. <span data-ttu-id="8f8ad-116">Visual Studio を開き**New**  >  、[**ファイル**] メニューの [新しい**プロジェクト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-116">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="8f8ad-117">[**インストールされたテンプレート**] の一覧で [ **Visual C#** ] または [ **Visual Basic**] を選択し、[ **Windows デスクトップ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-117">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="8f8ad-118">[**コンソールアプリケーション**] テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-118">Select the **Console App** template.</span></span> <span data-ttu-id="8f8ad-119">[ `SelfHost` **名前**] ボックスに「」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-119">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="8f8ad-120">**ソリューションエクスプローラー**で [ **selfhost** ] を右クリックし、[**参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-120">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="8f8ad-121">[ **.Net** ] タブで [ **system.servicemodel** ] を選択し、[ **OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-121">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8f8ad-122">**ソリューションエクスプローラー**ウィンドウが表示されていない場合は、[**表示**] メニューの [**ソリューションエクスプローラー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-122">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="8f8ad-123">**ソリューションエクスプローラー**で**Program.cs**または module1.vb をダブルクリックして、まだ開いていない**場合はコード**ウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="8f8ad-124">ファイルの先頭に次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-124">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="8f8ad-125">サービス コントラクトを定義して実装します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-125">Define and implement a service contract.</span></span> <span data-ttu-id="8f8ad-126">この例では、サービスへの入力に基づいてメッセージを返す `HelloWorldService` を定義します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-126">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="8f8ad-127">サービスインターフェイスを定義および実装する方法の詳細については、「[方法: サービスコントラクトを定義](how-to-define-a-wcf-service-contract.md)する」および「[方法: サービスコントラクトを実装](how-to-implement-a-wcf-contract.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-127">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="8f8ad-128">`Main` メソッドの上部で、サービスのベース アドレスで <xref:System.Uri> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-128">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="8f8ad-129"><xref:System.ServiceModel.ServiceHost> クラスのインスタンスを作成して、サービス型を表す <xref:System.Type> とベース アドレス URI (Uniform Resource Identifier) を <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> に渡します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-129">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="8f8ad-130">メタデータ公開を有効にして、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> メソッドを呼び出し、サービスを初期化してメッセージを受信する準備をします。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-130">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="8f8ad-131">この例では、既定のエンドポイントを使用するので、このサービスには構成ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-131">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="8f8ad-132">エンドポイントが構成されていない場合、ランタイムは、サービスによって実装されたサービス コントラクトごとに 1 つのエンドポイントを各ベース アドレスに作成します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-132">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="8f8ad-133">既定のエンドポイントの詳細については、「 [WCF サービスの](./samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-133">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="8f8ad-134">**Ctrl** + **Shift** + **B**キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-134">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="8f8ad-135">サービスをテストする</span><span class="sxs-lookup"><span data-stu-id="8f8ad-135">Test the service</span></span>

1. <span data-ttu-id="8f8ad-136">**Ctrl**F5 キーを押して + **F5**サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-136">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="8f8ad-137">**WCF テストクライアント**を開きます。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-137">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8f8ad-138">**WCF テストクライアント**を開くには、Visual Studio の開発者コマンドプロンプトを開き、 **WcfTestClient.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-138">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="8f8ad-139">[**ファイル**] メニューの [**サービスの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-139">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="8f8ad-140">`http://localhost:8080/hello`[アドレス] ボックスに「」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-140">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8f8ad-141">サービスが実行していることを確認してください。サービスが実行していない場合、この手順は失敗します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-141">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="8f8ad-142">コードでベース アドレスを変更した場合は、この手順で、変更したアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-142">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="8f8ad-143">[**マイサービスプロジェクト**] ノードの下にある [ **SayHello** ] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-143">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="8f8ad-144">**要求**一覧の [**値**] 列に名前を入力し、[**呼び出し**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-144">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="8f8ad-145">**応答**の一覧に応答メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-145">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="8f8ad-146">例</span><span class="sxs-lookup"><span data-stu-id="8f8ad-146">Example</span></span>

<span data-ttu-id="8f8ad-147"><xref:System.ServiceModel.ServiceHost> 型のサービスをホストする `HelloWorldService` オブジェクトを作成し、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> メソッドを呼び出す例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-147">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="8f8ad-148">ベース アドレスがコードで指定され、メタデータ公開が有効化されていて、既定のエンドポイントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="8f8ad-148">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="8f8ad-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f8ad-149">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="8f8ad-150">方法: IIS で WCF サービスをホストする</span><span class="sxs-lookup"><span data-stu-id="8f8ad-150">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="8f8ad-151">自己ホスト</span><span class="sxs-lookup"><span data-stu-id="8f8ad-151">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="8f8ad-152">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="8f8ad-152">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="8f8ad-153">方法: サービス コントラクトを定義する</span><span class="sxs-lookup"><span data-stu-id="8f8ad-153">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="8f8ad-154">方法: サービス コントラクトを実装する</span><span class="sxs-lookup"><span data-stu-id="8f8ad-154">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="8f8ad-155">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="8f8ad-155">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="8f8ad-156">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="8f8ad-156">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8f8ad-157">システム標準のバインディング</span><span class="sxs-lookup"><span data-stu-id="8f8ad-157">System-Provided Bindings</span></span>](system-provided-bindings.md)
