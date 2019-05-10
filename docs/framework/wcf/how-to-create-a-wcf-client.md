---
title: 'チュートリアル: Windows Communication Foundation クライアントを作成します。'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 39f63b22257fb67d9caa5f84c886ead161508a33
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625820"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="40245-102">チュートリアル: Windows Communication Foundation クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="40245-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="40245-103">このチュートリアルでは、4 番目の基本的な Windows Communication Foundation (WCF) アプリケーションを作成するために必要な 5 つのタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40245-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="40245-104">チュートリアルの概要については、次を参照してください。[チュートリアル。Windows Communication Foundation アプリケーションの概要](getting-started-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="40245-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="40245-105">WCF アプリケーションを作成するための次のタスクでは、WCF サービスからメタデータを取得することによって、クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="40245-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="40245-106">Visual Studio を使用して、サービスの MEX エンドポイントからメタデータを取得します。 サービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="40245-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="40245-107">Visual Studio は、選択した言語でクライアント プロキシのマネージ ソース コード ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="40245-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="40245-108">クライアント構成ファイルが作成されます (*App.config*)。</span><span class="sxs-lookup"><span data-stu-id="40245-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="40245-109">このファイルは、エンドポイントのサービスに接続するクライアント アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="40245-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="40245-110">Visual Studio でクラス ライブラリ プロジェクトから WCF サービスを呼び出す場合は、使用、**サービス参照の追加**プロキシと関連付けられている構成ファイルを自動的に生成する機能。</span><span class="sxs-lookup"><span data-stu-id="40245-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="40245-111">ただし、クラス ライブラリ プロジェクトでは、この構成ファイルを使用しないため、必要がありますに生成された構成ファイルで設定を追加する、 *App.config*クラス ライブラリを呼び出す実行可能ファイルのファイル。</span><span class="sxs-lookup"><span data-stu-id="40245-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="40245-112">代わりに、使用、 [ServiceModel メタデータ ユーティリティ ツール](#servicemodel-metadata-utility-tool)Visual Studio で、プロキシ クラスおよび構成ファイルを生成する代わりにします。</span><span class="sxs-lookup"><span data-stu-id="40245-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="40245-113">クライアント アプリケーションは、生成されたプロキシ クラスを使用してサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="40245-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="40245-114">この手順で説明されて[チュートリアル。クライアントを使用して](how-to-use-a-wcf-client.md)します。</span><span class="sxs-lookup"><span data-stu-id="40245-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="40245-115">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="40245-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="40245-116">作成し、WCF クライアントのコンソール アプリ プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="40245-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="40245-117">プロキシ クラスと構成ファイルを生成する WCF サービスにサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="40245-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="40245-118">Windows Communication Foundation クライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="40245-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="40245-119">Visual Studio でコンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="40245-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="40245-120">**ファイル**メニューの **オープン** > **プロジェクト/ソリューション**を見つけて、 **GettingStarted**ソリューションを以前に作成した (*GettingStarted.sln*)。</span><span class="sxs-lookup"><span data-stu-id="40245-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="40245-121">**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40245-121">Select **Open**.</span></span>

    2. <span data-ttu-id="40245-122">**ビュー**メニューの **ソリューション エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="40245-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="40245-123">**ソリューション エクスプ ローラー**ウィンドウで、 **GettingStarted**ソリューション (最上位ノード) し、選択**追加** > **の新しいプロジェクト**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="40245-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="40245-124">**新しいプロジェクトの追加**ウィンドウで、左側にある、選択、 **Windows デスクトップ**カテゴリ  **Visual C#** または**Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="40245-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="40245-125">選択、**コンソール アプリ (.NET Framework)** テンプレート、入力と*GettingStartedClient*の**名前**します。</span><span class="sxs-lookup"><span data-stu-id="40245-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="40245-126">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="40245-126">Select **OK**.</span></span>

2. <span data-ttu-id="40245-127">参照を追加、 **GettingStartedClient**プロジェクトを<xref:System.ServiceModel>アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="40245-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="40245-128">**ソリューション エクスプ ローラー**ウィンドウで、**参照**の下のフォルダー、 **GettingStartedClient**プロジェクトを選び**参照の追加**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="40245-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="40245-129">**参照の追加**ウィンドウで、**アセンブリ**ウィンドウの左側にある、次のように選択します。 **Framework**します。</span><span class="sxs-lookup"><span data-stu-id="40245-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="40245-130">検索して選択**System.ServiceModel**を選び、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="40245-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="40245-131">ソリューションを選択して保存**ファイル** > **すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="40245-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="40245-132">電卓サービスにサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="40245-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="40245-133">**ソリューション エクスプ ローラー**ウィンドウで、**参照**の下のフォルダー、 **GettingStartedClient**プロジェクトを選び**サービス参照の追加**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="40245-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="40245-134">**サービス参照の追加**ウィンドウで、 **Discover**します。</span><span class="sxs-lookup"><span data-stu-id="40245-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="40245-135">CalculatorService サービスが開始されると Visual Studio でそれを表示、**サービス**ボックス。</span><span class="sxs-lookup"><span data-stu-id="40245-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="40245-136">選択**CalculatorService**展開すると、サービスによって実装されるサービス コントラクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="40245-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="40245-137">既定値のままに**Namespace**選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="40245-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="40245-138">Visual Studio は、新しい項目を追加、**接続済みサービス**フォルダーで、 **GettingStartedClient**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="40245-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="40245-139">ServiceModel メタデータ ユーティリティ ツール</span><span class="sxs-lookup"><span data-stu-id="40245-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="40245-140">次の例では、必要に応じて使用する方法、 [ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)プロキシ クラス ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="40245-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="40245-141">このツールは、プロキシ クラス ファイルを生成し、 *App.config*ファイル。</span><span class="sxs-lookup"><span data-stu-id="40245-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="40245-142">次の例でプロキシを生成する方法を示してC#および Visual Basic の場合は、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="40245-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="40245-143">クライアント構成ファイル</span><span class="sxs-lookup"><span data-stu-id="40245-143">Client configuration file</span></span>

<span data-ttu-id="40245-144">クライアントを作成したら、Visual Studio で作成、 **App.config**構成ファイルで、 **GettingStartedClient**プロジェクトで、次の例のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40245-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="40245-145">で、 [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md)セクションに注意してください、 [\<エンドポイント >](../configure-apps/file-schema/wcf/endpoint-element.md)要素。</span><span class="sxs-lookup"><span data-stu-id="40245-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="40245-146">**&lt;エンドポイント&gt;** 要素は、クライアントが次のように、サービスへのアクセスに使用するエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="40245-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>
- <span data-ttu-id="40245-147">アドレス:`http://localhost:8000/GettingStarted/CalculatorService`します。</span><span class="sxs-lookup"><span data-stu-id="40245-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="40245-148">エンドポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="40245-148">The address of the endpoint.</span></span>
- <span data-ttu-id="40245-149">サービス コントラクト:`ServiceReference1.ICalculator`します。</span><span class="sxs-lookup"><span data-stu-id="40245-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="40245-150">サービス コントラクトは、WCF クライアントとサービス間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="40245-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="40245-151">Visual Studio が使用したときに、このコントラクトを生成、**サービス参照の追加**関数。</span><span class="sxs-lookup"><span data-stu-id="40245-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="40245-152">基本的に、GettingStartedLib プロジェクトで定義されているコントラクトのコピーになります。</span><span class="sxs-lookup"><span data-stu-id="40245-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="40245-153">バインディング:<xref:System.ServiceModel.WSHttpBinding>します。</span><span class="sxs-lookup"><span data-stu-id="40245-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="40245-154">バインディングでは、トランスポート、相互運用可能なセキュリティ、およびその他の構成の詳細として HTTP を指定します。</span><span class="sxs-lookup"><span data-stu-id="40245-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="40245-155">次の手順</span><span class="sxs-lookup"><span data-stu-id="40245-155">Next steps</span></span>

<span data-ttu-id="40245-156">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="40245-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="40245-157">作成し、WCF クライアントのコンソール アプリ プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="40245-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="40245-158">クライアント アプリケーションのプロキシ クラスと構成ファイルを生成する WCF サービスにサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="40245-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="40245-159">生成されたクライアントを使用する方法については、次のチュートリアルに進んでください。</span><span class="sxs-lookup"><span data-stu-id="40245-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="40245-160">チュートリアル: WCF クライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="40245-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
