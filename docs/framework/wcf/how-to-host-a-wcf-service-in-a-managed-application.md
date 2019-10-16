---
title: '方法 : マネージド アプリケーションで WCF サービスをホストする'
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: e3adcad6ba70aa64b797325cd45a043301d7e680
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320979"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="1fdad-102">方法: マネージアプリで WCF サービスをホストする</span><span class="sxs-lookup"><span data-stu-id="1fdad-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="1fdad-103">マネージド アプリケーションでサービスをホストするには、マネージド アプリケーション コード内にサービスのコードを埋め込み、サービスのエンドポイントをコードで強制的に定義するか、構成を使用して宣言により定義してから、または既定のエンドポイントを使用して、<xref:System.ServiceModel.ServiceHost> のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="1fdad-104">メッセージの受信を開始するには、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="1fdad-105">これにより、サービスのリスナーが作成されて開きます。</span><span class="sxs-lookup"><span data-stu-id="1fdad-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="1fdad-106">この方法によるサービスのホストは、マネージド アプリケーション自体がホスト作業を行うため、"自己ホスト" と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="1fdad-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="1fdad-107">サービスを閉じるには、<xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> で <xref:System.ServiceModel.ServiceHost> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="1fdad-108">サービスは、マネージド Windows サービス、インターネット インフォメーション サービス (IIS)、または Windows プロセス アクティブ化サービス (WAS) でホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1fdad-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="1fdad-109">サービスのホスティングオプションの詳細については、「[ホスティングサービス](hosting-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdad-109">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="1fdad-110">マネージド アプリケーションでのサービスのホスティングは、展開するインフラストラクチャが最小限で済むため、最も柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="1fdad-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="1fdad-111">マネージアプリケーションでのホスティングサービスの詳細については、「[マネージアプリケーションでのホスティング](./feature-details/hosting-in-a-managed-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdad-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="1fdad-112">次の手順では、自己ホスト型サービスをコンソール アプリケーションに実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="1fdad-113">自己ホスト型サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="1fdad-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="1fdad-114">新しいコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-114">Create a new console application:</span></span>

   1. <span data-ttu-id="1fdad-115">Visual Studio を開き、 **[ファイル]** メニューの [**新規** > **プロジェクト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="1fdad-116">**[インストールされたテンプレート]** の一覧で **[ビジュアルC# ]** または **[Visual Basic]** を選択し、 **[Windows デスクトップ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="1fdad-117">**[コンソールアプリケーション]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-117">Select the **Console App** template.</span></span> <span data-ttu-id="1fdad-118">**[名前]** ボックスに「`SelfHost`」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdad-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="1fdad-119">**ソリューションエクスプローラー**で **[selfhost]** を右クリックし、 **[参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="1fdad-120">**[.Net]** タブで **[system.servicemodel]** を選択し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1fdad-121">**ソリューションエクスプローラー**ウィンドウが表示されていない場合は、 **[表示]** メニューの **[ソリューションエクスプローラー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="1fdad-122">**ソリューションエクスプローラー**で**Program.cs**または module1.vb をダブルクリックして、まだ開いていない**場合はコード**ウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="1fdad-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="1fdad-123">ファイルの先頭に次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="1fdad-124">サービス コントラクトを定義して実装します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-124">Define and implement a service contract.</span></span> <span data-ttu-id="1fdad-125">この例では、サービスへの入力に基づいてメッセージを返す `HelloWorldService` を定義します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="1fdad-126">サービスインターフェイスを定義および実装する方法の詳細については、「[方法: サービスコントラクトを定義](how-to-define-a-wcf-service-contract.md)する」および「[方法: サービスコントラクトを実装](how-to-implement-a-wcf-contract.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdad-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="1fdad-127">`Main` メソッドの上部で、サービスのベース アドレスで <xref:System.Uri> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="1fdad-128"><xref:System.ServiceModel.ServiceHost> クラスのインスタンスを作成して、サービス型を表す <xref:System.Type> とベース アドレス URI (Uniform Resource Identifier) を <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> に渡します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="1fdad-129">メタデータ公開を有効にして、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> メソッドを呼び出し、サービスを初期化してメッセージを受信する準備をします。</span><span class="sxs-lookup"><span data-stu-id="1fdad-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="1fdad-130">この例では、既定のエンドポイントを使用するので、このサービスには構成ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1fdad-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="1fdad-131">エンドポイントが構成されていない場合、ランタイムは、サービスによって実装されたサービス コントラクトごとに 1 つのエンドポイントを各ベース アドレスに作成します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="1fdad-132">既定のエンドポイントの詳細については、「 [WCF サービスの](./samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdad-132">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="1fdad-133">**Ctrl**+**Shift**+**B**キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="1fdad-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="1fdad-134">サービスをテストする</span><span class="sxs-lookup"><span data-stu-id="1fdad-134">Test the service</span></span>

1. <span data-ttu-id="1fdad-135">**Ctrl**+**F5**キーを押してサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="1fdad-136">**WCF テストクライアント**を開きます。</span><span class="sxs-lookup"><span data-stu-id="1fdad-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1fdad-137">**WCF テストクライアント**を開くには、Visual Studio の開発者コマンドプロンプトを開き、 **wcftestclient.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="1fdad-138">**[ファイル]** メニューの **[サービスの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="1fdad-139">[アドレス] ボックスに「`http://localhost:8080/hello`」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdad-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1fdad-140">サービスが実行していることを確認してください。サービスが実行していない場合、この手順は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="1fdad-141">コードでベース アドレスを変更した場合は、この手順で、変更したアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="1fdad-142">**[マイサービスプロジェクト]** ノードの下にある **[SayHello]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdad-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="1fdad-143">**要求**一覧の **[値]** 列に名前を入力し、 **[呼び出し]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdad-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="1fdad-144">**応答**の一覧に応答メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fdad-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="1fdad-145">例</span><span class="sxs-lookup"><span data-stu-id="1fdad-145">Example</span></span>

<span data-ttu-id="1fdad-146"><xref:System.ServiceModel.ServiceHost> 型のサービスをホストする `HelloWorldService` オブジェクトを作成し、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> メソッドを呼び出す例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fdad-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="1fdad-147">ベース アドレスがコードで指定され、メタデータ公開が有効化されていて、既定のエンドポイントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="1fdad-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="1fdad-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fdad-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="1fdad-149">方法 : IIS で WCF サービスをホストする</span><span class="sxs-lookup"><span data-stu-id="1fdad-149">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="1fdad-150">自己ホスト</span><span class="sxs-lookup"><span data-stu-id="1fdad-150">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="1fdad-151">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="1fdad-151">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="1fdad-152">方法: サービス コントラクトを定義する</span><span class="sxs-lookup"><span data-stu-id="1fdad-152">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="1fdad-153">方法: サービス コントラクトを実装する</span><span class="sxs-lookup"><span data-stu-id="1fdad-153">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="1fdad-154">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="1fdad-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="1fdad-155">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="1fdad-155">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1fdad-156">システム標準のバインディング</span><span class="sxs-lookup"><span data-stu-id="1fdad-156">System-Provided Bindings</span></span>](system-provided-bindings.md)
