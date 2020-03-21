---
title: 'チュートリアル: Windows コミュニケーション ファウンデーション クライアントを作成する'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184111"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="c5d25-102">チュートリアル: Windows コミュニケーション ファウンデーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="c5d25-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="c5d25-103">このチュートリアルでは、基本的な Wcf (WCF) アプリケーションを作成するために必要な 5 つのタスクの 4 つ目について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c5d25-104">チュートリアルの概要については、「[チュートリアル: Windows コミュニケーションファウンデーション アプリケーションの概要](getting-started-tutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5d25-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="c5d25-105">WCF アプリケーションを作成するための次のタスクは、WCF サービスからメタデータを取得することによってクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="c5d25-106">Visual Studio を使用してサービス参照を追加すると、サービスの MEX エンドポイントからメタデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="c5d25-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="c5d25-107">次に、Visual Studio によって、選択した言語でクライアント プロキシ用のマネージ ソース コード ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c5d25-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="c5d25-108">また、クライアント構成ファイル (*App.config*) も作成されます。</span><span class="sxs-lookup"><span data-stu-id="c5d25-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="c5d25-109">このファイルを使用すると、クライアント アプリケーションはエンドポイントでサービスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="c5d25-109">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="c5d25-110">Visual Studio のクラス ライブラリ プロジェクトから WCF サービスを呼び出す場合は、**サービス参照の追加**機能を使用して、プロキシと関連付けられた構成ファイルを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="c5d25-111">ただし、クラス ライブラリ プロジェクトはこの構成ファイルを使用しないため、生成された構成ファイルの設定を、クラス ライブラリを呼び出す実行可能ファイルの*App.config*ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5d25-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="c5d25-112">代わりに、Visual Studio ではなく[サービス モデル メタデータ ユーティリティ ツール](#servicemodel-metadata-utility-tool)を使用して、プロキシ クラスと構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="c5d25-113">クライアント アプリケーションは、生成されたプロキシ クラスを使用してサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="c5d25-114">この手順については、「[チュートリアル: クライアントを使用する」を参照](how-to-use-a-wcf-client.md)してください。</span><span class="sxs-lookup"><span data-stu-id="c5d25-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="c5d25-115">このチュートリアルでは、以下の内容を学習します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c5d25-116">作成し、WCF クライアントのコンソール アプリ プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="c5d25-117">WCF サービスにサービス参照を追加して、プロキシ クラスファイルと構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="c5d25-118">Windows コミュニケーション ファウンデーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="c5d25-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="c5d25-119">Visual Studio でコンソール アプリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-119">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="c5d25-120">[**ファイル]** メニューの [**プロジェクト/ソリューション**を**開く** > ] を選択し、以前に作成した **[はじめに]** ソリューション (*GettingStarted.sln*) を参照します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="c5d25-121">**[開く]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-121">Select **Open**.</span></span>

    2. <span data-ttu-id="c5d25-122">[**表示**] メニューの [**ソリューション エクスプローラ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5d25-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="c5d25-123">[**ソリューション エクスプローラー** ] ウィンドウで **、"はじめに"** ソリューション (最上位ノード) を選択し、ショートカット メニューから **[新しいプロジェクト**の**追加** > ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="c5d25-124">[**新しいプロジェクトの追加**] ウィンドウの左側で **、[Visual C#** または Visual **Basic]** の下にある **[Windows デスクトップ**] カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="c5d25-125">コンソール**アプリケーション (.NET Framework)** テンプレートを選択し、\**名前\*\*\*に「はじめにクライアント*」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="c5d25-126">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-126">Select **OK**.</span></span>

2. <span data-ttu-id="c5d25-127">**アセンブリに、次の参照を開始クライアント**プロジェクト<xref:System.ServiceModel>に追加します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="c5d25-128">**[ソリューション エクスプローラー** ] ウィンドウで **、GettingStartedClient**プロジェクトの下にある **[参照**] フォルダーを選択し、ショートカット メニューの **[参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="c5d25-129">[**参照の追加**] ウィンドウの左側にある **[アセンブリ**] で、[**フレームワーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="c5d25-130">検索して **[System.ServiceModel]** を選択し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5d25-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="c5d25-131">[ファイルをすべて保存] を選択してソリューション**を** > **保存**します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="c5d25-132">電卓サービスにサービス参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="c5d25-133">[**ソリューション エクスプローラー** ] ウィンドウで **、GettingStartedClient**プロジェクトの下にある **[参照**] フォルダーを選択し、ショートカット メニューの **[サービス参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="c5d25-134">[**サービス参照の追加**] ウィンドウで、[**検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="c5d25-135">電卓サービス サービスが開始され、Visual Studio によって [**サービス**] ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5d25-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="c5d25-136">**電卓サービス**を展開し、サービスによって実装されるサービス コントラクトを表示するを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="c5d25-137">デフォルトの**名前空間**をそのままにして **、[OK] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="c5d25-138">新しい項目が **、GettingStartedClient**プロジェクトの **[接続済みサービス**] フォルダーに追加されます。</span><span class="sxs-lookup"><span data-stu-id="c5d25-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="c5d25-139">サービスモデル メタデータ ユーティリティ ツール</span><span class="sxs-lookup"><span data-stu-id="c5d25-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="c5d25-140">次の例は、オプションで[サービス モデル メタデータ ユーティリティ ツール (Svcutil.exe) を](servicemodel-metadata-utility-tool-svcutil-exe.md)使用してプロキシ クラス ファイルを生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c5d25-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="c5d25-141">このツールは、プロキシ クラス ファイルと*App.config*ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="c5d25-142">次の例は、C# と Visual Basic でそれぞれプロキシを生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c5d25-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="c5d25-143">クライアント構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c5d25-143">Client configuration file</span></span>

<span data-ttu-id="c5d25-144">クライアントを作成すると、次の例のようなコードが作成される必要があります、次の例に従って、**プロジェクト**に**App.config**構成ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c5d25-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="c5d25-145">system.serviceModel>セクションで、[\<エンドポイント>](../configure-apps/file-schema/wcf/endpoint-element.md)要素に注目してください。 [ \<](../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c5d25-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="c5d25-146">**&lt;エンドポイント&gt;** 要素は、クライアントがサービスへのアクセスに使用するエンドポイントを次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="c5d25-147">アドレス: `http://localhost:8000/GettingStarted/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="c5d25-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="c5d25-148">エンドポイントのアドレス。</span><span class="sxs-lookup"><span data-stu-id="c5d25-148">The address of the endpoint.</span></span>
- <span data-ttu-id="c5d25-149">サービス契約: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="c5d25-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="c5d25-150">サービス コントラクトは、WCF クライアントとサービス間の通信を処理します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="c5d25-151">Visual Studio は **、サービス参照の追加**機能を使用したときにこのコントラクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="c5d25-152">これは、基本的に、GettingStartedLib プロジェクトで定義したコントラクトのコピーです。</span><span class="sxs-lookup"><span data-stu-id="c5d25-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="c5d25-153">バインディング: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="c5d25-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="c5d25-154">バインディングは、トランスポート、相互運用可能なセキュリティ、およびその他の構成の詳細として HTTP を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c5d25-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c5d25-155">Next steps</span></span>

<span data-ttu-id="c5d25-156">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="c5d25-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c5d25-157">作成し、WCF クライアントのコンソール アプリ プロジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="c5d25-158">WCF サービスへのサービス参照を追加して、クライアント アプリケーションのプロキシ クラス ファイルと構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="c5d25-159">次のチュートリアルに進み、生成されたクライアントの使用方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="c5d25-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c5d25-160">チュートリアル: WCF クライアントを使用する</span><span class="sxs-lookup"><span data-stu-id="c5d25-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
