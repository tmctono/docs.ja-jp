---
title: '方法: マネージド アプリケーションで WCF サービスをホストする'
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 131d99457427e0818f78076d987f550a99ad7cf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929312"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="67576-102">方法: 管理対象アプリでの WCF サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="67576-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="67576-103">マネージド アプリケーションでサービスをホストするには、マネージド アプリケーション コード内にサービスのコードを埋め込み、サービスのエンドポイントをコードで強制的に定義するか、構成を使用して宣言により定義してから、または既定のエンドポイントを使用して、<xref:System.ServiceModel.ServiceHost> のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="67576-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="67576-104">メッセージの受信を開始するには、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67576-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="67576-105">これにより、サービスのリスナーが作成されて開きます。</span><span class="sxs-lookup"><span data-stu-id="67576-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="67576-106">この方法によるサービスのホストは、マネージド アプリケーション自体がホスト作業を行うため、"自己ホスト" と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="67576-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="67576-107">サービスを閉じるには、<xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> で <xref:System.ServiceModel.ServiceHost> を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="67576-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="67576-108">サービスは、マネージド Windows サービス、インターネット インフォメーション サービス (IIS)、または Windows プロセス アクティブ化サービス (WAS) でホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="67576-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="67576-109">ホスティング サービスのオプションの詳細については、次を参照してください。[ホスティング サービス](../../../docs/framework/wcf/hosting-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="67576-109">For more information about hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>

<span data-ttu-id="67576-110">マネージド アプリケーションでのサービスのホスティングは、展開するインフラストラクチャが最小限で済むため、最も柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="67576-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="67576-111">マネージ アプリケーションでサービスをホストする方法の詳細については、次を参照してください。[マネージ アプリケーションでのホスティング](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="67576-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="67576-112">次の手順では、自己ホスト型サービスをコンソール アプリケーションに実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="67576-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="67576-113">自己ホスト型サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="67576-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="67576-114">新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="67576-114">Create a new console application:</span></span>

   1. <span data-ttu-id="67576-115">Visual Studio を開き、選択**新規** > **プロジェクト**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="67576-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="67576-116">**インストールされたテンプレート**一覧で、 **Visual c#** または**Visual Basic**、し、 **Windows デスクトップ**します。</span><span class="sxs-lookup"><span data-stu-id="67576-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="67576-117">選択、**コンソール アプリ**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="67576-117">Select the **Console App** template.</span></span> <span data-ttu-id="67576-118">型`SelfHost`で、**名前**ボックス選び、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="67576-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="67576-119">右クリック**SelfHost**で**ソリューション エクスプ ローラー**選択**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="67576-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="67576-120">選択**System.ServiceModel**から、 **.NET**タブをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="67576-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="67576-121">場合、**ソリューション エクスプ ローラー**ウィンドウが表示される、選択**ソリューション エクスプ ローラー**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="67576-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="67576-122">ダブルクリック**Program.cs**または**Module1.vb**で**ソリューション エクスプ ローラー**がまだ開いていない場合、コード ウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="67576-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="67576-123">ファイルの上部にある次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="67576-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="67576-124">サービス コントラクトを定義して実装します。</span><span class="sxs-lookup"><span data-stu-id="67576-124">Define and implement a service contract.</span></span> <span data-ttu-id="67576-125">この例では、サービスへの入力に基づいてメッセージを返す `HelloWorldService` を定義します。</span><span class="sxs-lookup"><span data-stu-id="67576-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="67576-126">定義して、サービス インターフェイスを実装する方法の詳細については、次を参照してください。[方法。サービス コントラクトを定義する](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)と[方法。サービス コントラクトを実装する](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="67576-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="67576-127">`Main` メソッドの上部で、サービスのベース アドレスで <xref:System.Uri> クラスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="67576-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="67576-128"><xref:System.ServiceModel.ServiceHost> クラスのインスタンスを作成して、サービス型を表す <xref:System.Type> とベース アドレス URI (Uniform Resource Identifier) を <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29> に渡します。</span><span class="sxs-lookup"><span data-stu-id="67576-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="67576-129">メタデータ公開を有効にして、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> メソッドを呼び出し、サービスを初期化してメッセージを受信する準備をします。</span><span class="sxs-lookup"><span data-stu-id="67576-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="67576-130">この例では、既定のエンドポイントを使用するので、このサービスには構成ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="67576-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="67576-131">エンドポイントが構成されていない場合、ランタイムは、サービスによって実装されたサービス コントラクトごとに 1 つのエンドポイントを各ベース アドレスに作成します。</span><span class="sxs-lookup"><span data-stu-id="67576-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="67576-132">既定のエンドポイントの詳細については、次を参照してください。 [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md)と[Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="67576-132">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="67576-133">キーを押して**Ctrl**+**Shift**+**B**ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="67576-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="67576-134">サービスをテストする</span><span class="sxs-lookup"><span data-stu-id="67576-134">Test the service</span></span>

1. <span data-ttu-id="67576-135">キーを押して**Ctrl**+**F5**サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="67576-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="67576-136">開いている**WCF テスト クライアント**します。</span><span class="sxs-lookup"><span data-stu-id="67576-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="67576-137">開くには**WCF テスト クライアント**for Visual Studio 開発者コマンド プロンプトを開くし、実行、 **WcfTestClient.exe**します。</span><span class="sxs-lookup"><span data-stu-id="67576-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="67576-138">選択**サービスの追加**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="67576-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="67576-139">型`http://localhost:8080/hello`アドレス ボックスに**OK**します。</span><span class="sxs-lookup"><span data-stu-id="67576-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="67576-140">サービスが実行していることを確認してください。サービスが実行していない場合、この手順は失敗します。</span><span class="sxs-lookup"><span data-stu-id="67576-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="67576-141">コードでベース アドレスを変更した場合は、この手順で、変更したアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="67576-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="67576-142">ダブルクリック**SayHello**下、**マイ サービス プロジェクト**ノード。</span><span class="sxs-lookup"><span data-stu-id="67576-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="67576-143">型名を指定して、**値**内の列、**要求**ボックスの一覧し、をクリックして**Invoke**します。</span><span class="sxs-lookup"><span data-stu-id="67576-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="67576-144">応答メッセージが表示されます、**応答**一覧。</span><span class="sxs-lookup"><span data-stu-id="67576-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="67576-145">例</span><span class="sxs-lookup"><span data-stu-id="67576-145">Example</span></span>

<span data-ttu-id="67576-146"><xref:System.ServiceModel.ServiceHost> 型のサービスをホストする `HelloWorldService` オブジェクトを作成し、<xref:System.ServiceModel.ICommunicationObject.Open%2A> で <xref:System.ServiceModel.ServiceHost> メソッドを呼び出す例を、次に示します。</span><span class="sxs-lookup"><span data-stu-id="67576-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="67576-147">ベース アドレスがコードで指定され、メタデータ公開が有効化されていて、既定のエンドポイントが使用されています。</span><span class="sxs-lookup"><span data-stu-id="67576-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="67576-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="67576-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="67576-149">方法: IIS で WCF サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="67576-149">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="67576-150">自己ホスト</span><span class="sxs-lookup"><span data-stu-id="67576-150">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="67576-151">ホスティング サービス</span><span class="sxs-lookup"><span data-stu-id="67576-151">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="67576-152">方法: サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="67576-152">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="67576-153">方法: サービス コントラクトを実装します。</span><span class="sxs-lookup"><span data-stu-id="67576-153">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="67576-154">ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="67576-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="67576-155">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="67576-155">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="67576-156">システム標準のバインディング</span><span class="sxs-lookup"><span data-stu-id="67576-156">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)