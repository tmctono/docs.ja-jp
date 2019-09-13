---
title: 'チュートリアル: Windows Communication Foundation クライアントを作成する'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: ddb5167c7f71a263377fb465ec44ee21057fbf4a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928907"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="fb313-102">チュートリアル: Windows Communication Foundation クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="fb313-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="fb313-103">このチュートリアルでは、基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な5つのタスクのうち、4番目のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fb313-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="fb313-104">チュートリアルの概要については、 [「チュートリアル:Windows Communication Foundation アプリケーション](getting-started-tutorial.md)の概要」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fb313-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="fb313-105">WCF アプリケーションを作成するための次のタスクでは、WCF サービスからメタデータを取得してクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="fb313-106">サービスの MEX エンドポイントからメタデータを取得するサービス参照を追加するには、Visual Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb313-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="fb313-107">その後、Visual Studio によって、選択した言語でクライアントプロキシのマネージソースコードファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fb313-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="fb313-108">また、クライアント構成ファイル (*app.config*) も作成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="fb313-109">このファイルにより、クライアントアプリケーションはエンドポイントでサービスに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fb313-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="fb313-110">Visual Studio のクラスライブラリプロジェクトから WCF サービスを呼び出す場合は、**サービス参照の追加**機能を使用して、プロキシおよび関連する構成ファイルを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="fb313-111">ただし、クラスライブラリプロジェクトではこの構成ファイルを使用しないため、生成された構成ファイルの設定を、クラスライブラリを呼び出す実行可能ファイルの*app.config*ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb313-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="fb313-112">別の方法として、Visual Studio ではなく[ServiceModel メタデータユーティリティツール](#servicemodel-metadata-utility-tool)を使用して、プロキシクラスと構成ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb313-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="fb313-113">クライアント アプリケーションは、生成されたプロキシ クラスを使用してサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="fb313-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="fb313-114">この手順について[は、「チュートリアル:クライアント](how-to-use-a-wcf-client.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb313-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="fb313-115">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb313-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fb313-116">WCF クライアントのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="fb313-117">WCF サービスへのサービス参照を追加して、プロキシクラスと構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="fb313-118">Windows Communication Foundation クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="fb313-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="fb313-119">Visual Studio でコンソールアプリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="fb313-120">**[ファイル]** メニューの [**プロジェクト/ソリューション**を**開く** > ] を選択し、前の作業で作成した**gettingstarted** (*gettingstarted. .sln*) を参照します。</span><span class="sxs-lookup"><span data-stu-id="fb313-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="fb313-121">**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-121">Select **Open**.</span></span>

    2. <span data-ttu-id="fb313-122">**[表示]** メニューの **[ソリューションエクスプローラー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb313-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="fb313-123">**[ソリューションエクスプローラー]** ウィンドウで、 **[gettingstarted]** ソリューション (最上位ノード) を選択し、ショートカットメニューの [**新しいプロジェクト**の**追加** > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb313-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="fb313-124">**[新しいプロジェクトの追加]** ウィンドウの左側にある **[Visual C# ]** または **[Visual Basic]** の下にある **[Windows デスクトップ]** カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="fb313-125">**[コンソールアプリ (.NET Framework)]** テンプレートを選択し、**名前**として「 *gettingclient* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="fb313-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="fb313-126">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-126">Select **OK**.</span></span>

2. <span data-ttu-id="fb313-127">**Gettingのクライアント**プロジェクトで、 <xref:System.ServiceModel>アセンブリに参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="fb313-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="fb313-128">**[ソリューションエクスプローラー]** ウィンドウで、 **gettingclient**プロジェクトの **[参照]** フォルダーを選択し、ショートカットメニューの **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb313-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="fb313-129">**[参照の追加]** ウィンドウの左側にある **[アセンブリ]** で、 **[フレームワーク]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="fb313-130">**[System.servicemodel]** を見つけて選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="fb313-131">[**ファイル** > ] **[すべて保存]** の順に選択して、ソリューションを保存します。</span><span class="sxs-lookup"><span data-stu-id="fb313-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="fb313-132">電卓サービスへのサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="fb313-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="fb313-133">**[ソリューションエクスプローラー]** ウィンドウで、 **gettingclient**プロジェクトの **[参照]** フォルダーを選択し、ショートカットメニューの **[サービス参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="fb313-134">**[サービス参照の追加]** ウィンドウで、 **[探索]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="fb313-135">電卓サービスが開始され、Visual Studio に **[サービス]** ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb313-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="fb313-136">[**計算] を選択して**展開し、サービスによって実装されているサービスコントラクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="fb313-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="fb313-137">既定の**名前空間**をそのまま使用し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb313-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="fb313-138">Visual Studio によって、 **Gettingclient**プロジェクトの**接続済みサービス**フォルダーの下に新しい項目が追加されます。</span><span class="sxs-lookup"><span data-stu-id="fb313-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="fb313-139">ServiceModel メタデータユーティリティツール</span><span class="sxs-lookup"><span data-stu-id="fb313-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="fb313-140">次の例は、必要に応じて、 [ServiceModel メタデータユーティリティツール (svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)を使用してプロキシクラスファイルを生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fb313-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="fb313-141">このツールでは、プロキシクラスファイルと*app.config*ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="fb313-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="fb313-142">次の例は、 C#と Visual Basic でプロキシを生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fb313-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="fb313-143">クライアント構成ファイル</span><span class="sxs-lookup"><span data-stu-id="fb313-143">Client configuration file</span></span>

<span data-ttu-id="fb313-144">クライアントを作成すると、Visual Studio によって、次の例のように、 **Gettingclient**プロジェクトに app.config 構成ファイルが作成**されます**。</span><span class="sxs-lookup"><span data-stu-id="fb313-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="fb313-145">[System.servicemodel [ >\<](../configure-apps/file-schema/wcf/endpoint-element.md) ] セクションで、エンドポイント > 要素を確認します。 [ \<](../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fb313-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="fb313-146">Endpoint 要素は、次のように、クライアントがサービスにアクセスするために使用するエンドポイントを定義し **&lt;ます。&gt;**</span><span class="sxs-lookup"><span data-stu-id="fb313-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="fb313-147">アドレス: `http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="fb313-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="fb313-148">エンドポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="fb313-148">The address of the endpoint.</span></span>
- <span data-ttu-id="fb313-149">サービスコントラクト: `ServiceReference1.ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="fb313-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="fb313-150">サービスコントラクトは、WCF クライアントとサービス間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="fb313-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="fb313-151">**サービス参照の追加**関数を使用したときに、Visual Studio によってこのコントラクトが生成されました。</span><span class="sxs-lookup"><span data-stu-id="fb313-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="fb313-152">これは基本的に、Gettingの Lib プロジェクトで定義したコントラクトのコピーです。</span><span class="sxs-lookup"><span data-stu-id="fb313-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="fb313-153">バインド: <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="fb313-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="fb313-154">バインドでは、HTTP をトランスポート、相互運用可能なセキュリティ、およびその他の構成の詳細として指定します。</span><span class="sxs-lookup"><span data-stu-id="fb313-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb313-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="fb313-155">Next steps</span></span>

<span data-ttu-id="fb313-156">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="fb313-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fb313-157">WCF クライアントのコンソールアプリプロジェクトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="fb313-158">WCF サービスへのサービス参照を追加して、プロキシクラスとクライアントアプリケーションの構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="fb313-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="fb313-159">次のチュートリアルに進み、生成されたクライアントの使用方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="fb313-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fb313-160">チュートリアル: WCF クライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="fb313-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
