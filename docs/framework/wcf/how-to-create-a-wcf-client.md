---
title: 'チュートリアル: Windows Communication Foundation クライアントを作成する'
description: Wcf アプリケーションの作成を開始する際に役立つ一連の記事の一部として、WCF サービスからメタデータを取得することによって、クライアントを作成する方法について説明します。
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d5a2a2b5175c9e34eaf1dbaff20ac57f34117c4e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246325"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="e795b-103">チュートリアル: Windows Communication Foundation クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="e795b-103">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="e795b-104">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクのうち、4番目のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e795b-104">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="e795b-105">チュートリアルの概要については、「[チュートリアル: Windows Communication Foundation アプリケーションの](getting-started-tutorial.md)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e795b-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="e795b-106">WCF アプリケーションを作成するための次のタスクでは、WCF サービスからメタデータを取得してクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-106">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="e795b-107">サービスの MEX エンドポイントからメタデータを取得するサービス参照を追加するには、Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="e795b-107">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="e795b-108">その後、Visual Studio によって、選択した言語でクライアントプロキシのマネージソースコードファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e795b-108">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="e795b-109">また、クライアント構成ファイル (*App.config*) も作成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-109">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="e795b-110">このファイルにより、クライアントアプリケーションはエンドポイントでサービスに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e795b-110">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="e795b-111">Visual Studio のクラスライブラリプロジェクトから WCF サービスを呼び出す場合は、**サービス参照の追加**機能を使用して、プロキシおよび関連する構成ファイルを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-111">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="e795b-112">ただし、クラスライブラリプロジェクトではこの構成ファイルを使用しないため、クラスライブラリを呼び出す実行可能ファイルの*App.config*ファイルに、生成された構成ファイルの設定を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e795b-112">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="e795b-113">別の方法として、Visual Studio ではなく[ServiceModel メタデータユーティリティツール](#servicemodel-metadata-utility-tool)を使用して、プロキシクラスと構成ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e795b-113">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="e795b-114">クライアント アプリケーションは、生成されたプロキシ クラスを使用してサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="e795b-114">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="e795b-115">この手順については[、「チュートリアル: クライアントを使用](how-to-use-a-wcf-client.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e795b-115">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="e795b-116">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e795b-116">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="e795b-117">WCF クライアントのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-117">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="e795b-118">WCF サービスへのサービス参照を追加して、プロキシクラスと構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-118">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="e795b-119">Windows Communication Foundation クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="e795b-119">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="e795b-120">Visual Studio でコンソールアプリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-120">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="e795b-121">[**ファイル**] メニューの [プロジェクト/ソリューションを**開く**] を選択し、前の作業で作成し  >  **Project/Solution**た**gettingstarted** (*gettingstarted. .sln*) を参照します。</span><span class="sxs-lookup"><span data-stu-id="e795b-121">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="e795b-122">**[Open (開く)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-122">Select **Open**.</span></span>

    2. <span data-ttu-id="e795b-123">[**表示**] メニューの [**ソリューションエクスプローラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e795b-123">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="e795b-124">[**ソリューションエクスプローラー** ] ウィンドウで、[ **gettingstarted** ] ソリューション (最上位ノード) を選択**Add**し、  >  ショートカットメニューの [**新しいプロジェクト**の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e795b-124">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="e795b-125">[**新しいプロジェクトの追加**] ウィンドウの左側にある [ **Visual C#** ] または [ **Visual Basic**] の下にある [ **Windows デスクトップ**] カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-125">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="e795b-126">[**コンソールアプリ (.NET Framework)** ] テンプレートを選択し、**名前**として「 *gettingclient* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e795b-126">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="e795b-127">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-127">Select **OK**.</span></span>

2. <span data-ttu-id="e795b-128">**Gettingのクライアント**プロジェクトで、アセンブリに参照を追加し <xref:System.ServiceModel> ます。</span><span class="sxs-lookup"><span data-stu-id="e795b-128">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="e795b-129">[**ソリューションエクスプローラー** ] ウィンドウで、 **gettingclient**プロジェクトの [**参照**] フォルダーを選択し、ショートカットメニューの [**参照の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e795b-129">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="e795b-130">[**参照の追加**] ウィンドウの左側にある [**アセンブリ**] で、[**フレームワーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-130">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="e795b-131">[ **System.servicemodel**] を見つけて選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-131">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="e795b-132">[**ファイル**] [  >  **すべて保存**] の順に選択して、ソリューションを保存します。</span><span class="sxs-lookup"><span data-stu-id="e795b-132">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="e795b-133">電卓サービスへのサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="e795b-133">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="e795b-134">[**ソリューションエクスプローラー** ] ウィンドウで、 **gettingclient**プロジェクトの [**参照**] フォルダーを選択し、ショートカットメニューの [**サービス参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-134">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="e795b-135">[**サービス参照の追加**] ウィンドウで、[**探索**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-135">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="e795b-136">電卓サービスが開始され、Visual Studio に [**サービス**] ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e795b-136">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="e795b-137">[**計算] を選択して**展開し、サービスによって実装されているサービスコントラクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="e795b-137">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="e795b-138">既定の**名前空間**をそのまま使用し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e795b-138">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="e795b-139">Visual Studio によって、 **Gettingclient**プロジェクトの**接続済みサービス**フォルダーの下に新しい項目が追加されます。</span><span class="sxs-lookup"><span data-stu-id="e795b-139">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="e795b-140">ServiceModel メタデータユーティリティツール</span><span class="sxs-lookup"><span data-stu-id="e795b-140">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="e795b-141">次の例は、必要に応じて[ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)を使用してプロキシクラスファイルを生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e795b-141">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="e795b-142">このツールでは、プロキシクラスファイルと*App.config*ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e795b-142">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="e795b-143">次の例では、C# でプロキシを生成する方法と Visual Basic について説明します。</span><span class="sxs-lookup"><span data-stu-id="e795b-143">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="e795b-144">クライアント構成ファイル</span><span class="sxs-lookup"><span data-stu-id="e795b-144">Client configuration file</span></span>

<span data-ttu-id="e795b-145">クライアントを作成すると、Visual Studio によって**Gettingのクライアント**プロジェクトに**App.config**構成ファイルが作成されます。これは、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="e795b-145">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="e795b-146">セクションの下で、 [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) 要素を確認し [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="e795b-146">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="e795b-147">\*\* &lt; Endpoint &gt; \*\*要素は、次のように、クライアントがサービスにアクセスするために使用するエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="e795b-147">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="e795b-148">アドレス: `http://localhost:8000/GettingStarted/CalculatorService` 。</span><span class="sxs-lookup"><span data-stu-id="e795b-148">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="e795b-149">エンドポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="e795b-149">The address of the endpoint.</span></span>
- <span data-ttu-id="e795b-150">サービスコントラクト: `ServiceReference1.ICalculator` 。</span><span class="sxs-lookup"><span data-stu-id="e795b-150">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="e795b-151">サービスコントラクトは、WCF クライアントとサービス間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="e795b-151">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="e795b-152">**サービス参照の追加**関数を使用したときに、Visual Studio によってこのコントラクトが生成されました。</span><span class="sxs-lookup"><span data-stu-id="e795b-152">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="e795b-153">これは基本的に、Gettingの Lib プロジェクトで定義したコントラクトのコピーです。</span><span class="sxs-lookup"><span data-stu-id="e795b-153">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="e795b-154">バインド: <xref:System.ServiceModel.WSHttpBinding> 。</span><span class="sxs-lookup"><span data-stu-id="e795b-154">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="e795b-155">バインドでは、HTTP をトランスポート、相互運用可能なセキュリティ、およびその他の構成の詳細として指定します。</span><span class="sxs-lookup"><span data-stu-id="e795b-155">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e795b-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="e795b-156">Next steps</span></span>

<span data-ttu-id="e795b-157">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="e795b-157">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="e795b-158">WCF クライアントのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-158">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="e795b-159">WCF サービスへのサービス参照を追加して、プロキシクラスとクライアントアプリケーションの構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e795b-159">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="e795b-160">次のチュートリアルに進み、生成されたクライアントの使用方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="e795b-160">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e795b-161">チュートリアル: WCF クライアントの使用</span><span class="sxs-lookup"><span data-stu-id="e795b-161">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
