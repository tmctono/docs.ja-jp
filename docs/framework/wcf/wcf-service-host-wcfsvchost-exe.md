---
title: WCF サービス ホスト (WcfSvcHost.exe)
description: WCF サービスホストを使用して、実装したサービスをホストし、テストします。 WCF テストクライアントまたは独自のクライアントを使用して、サービスをテストできます。
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: 2ac1d6318d8a82a82c08f38305ee6f92ad3f52a2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544597"
---
# <a name="wcf-service-host-wcfsvchostexe"></a><span data-ttu-id="4b6f4-104">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="4b6f4-104">WCF Service Host (WcfSvcHost.exe)</span></span>

<span data-ttu-id="4b6f4-105">Windows Communication Foundation (WCF) サービスホスト (WcfSvcHost.exe) を使用すると、Visual Studio デバッガー (F5) を起動して、実装したサービスを自動的にホストおよびテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-105">Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="4b6f4-106">その後、WCF テストクライアント (WcfTestClient.exe) または独自のクライアントを使用してサービスをテストし、潜在的なエラーを見つけて修正することができます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-106">You can then test the service using WCF Test Client (WcfTestClient.exe), or your own client, to find and fix any potential errors.</span></span>

## <a name="wcf-service-host"></a><span data-ttu-id="4b6f4-107">WCF サービス ホスト</span><span class="sxs-lookup"><span data-stu-id="4b6f4-107">WCF Service Host</span></span>

<span data-ttu-id="4b6f4-108">Wcf サービスホストは、WCF サービスプロジェクト内のサービスを列挙し、プロジェクトの構成を読み込み、検出された各サービスのホストをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-108">WCF Service Host enumerates the services in a WCF service project, loads the project’s configuration, and instantiates a host for each service that it finds.</span></span> <span data-ttu-id="4b6f4-109">このツールは、WCF サービステンプレートを使用して Visual Studio に統合され、プロジェクトのデバッグを開始すると呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-109">The tool is integrated into Visual Studio through the WCF Service template and is invoked when you start to debug your project.</span></span>

<span data-ttu-id="4b6f4-110">Wcf サービスホストを使用すると、追加のコードを記述したり、開発中に特定のホストにコミットしたりすることなく、wcf サービスを (WCF サービスライブラリプロジェクト内で) ホストできます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-110">By using WCF Service Host, you can host a WCF service (in a WCF service library project) without writing extra code or committing to a specific host during development.</span></span>

> [!NOTE]
> <span data-ttu-id="4b6f4-111">WCF サービスホストは部分信頼をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-111">WCF Service Host does not support Partial Trust.</span></span> <span data-ttu-id="4b6f4-112">部分信頼で WCF サービスを使用する場合は、サービスをビルドするために Visual Studio で WCF サービスライブラリプロジェクトテンプレートを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-112">If you want to use a WCF Service in Partial Trust, do not use the WCF Service Library Project template in Visual Studio to build your service.</span></span> <span data-ttu-id="4b6f4-113">代わりに、wcf 部分信頼がサポートされている web サーバーでサービスをホストできる WCF サービス Web サイトテンプレートを選択して、Visual Studio で新しい Web サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-113">Instead, create a New WebSite in Visual Studio by choosing the WCF Service WebSite template, which can host the service in a WebServer on which WCF Partial Trust is supported.</span></span>

## <a name="project-types-hosted-by-wcf-service-host"></a><span data-ttu-id="4b6f4-114">WCF サービス ホストでホストされるプロジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="4b6f4-114">Project Types hosted by WCF Service Host</span></span>

<span data-ttu-id="4b6f4-115">Wcf サービスホストは、wcf サービスライブラリ、シーケンシャルワークフローサービスライブラリ、ステートマシンワークフローサービスライブラリ、および配信サービスライブラリという WCF サービスライブラリプロジェクトの種類をホストできます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-115">WCF Service Host can host the following WCF service library project types: WCF Service Library, Sequential Workflow Service Library, State Machine Workflow Service Library and Syndication Service Library.</span></span> <span data-ttu-id="4b6f4-116">WCF サービスホストは、[ **項目の追加** ] 機能を使用してサービスライブラリプロジェクトに追加できるサービスをホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-116">WCF Service Host can also host those services that can be added to a service library project using the **Add Item** functionality.</span></span> <span data-ttu-id="4b6f4-117">これには、WCF サービス、WF ステートマシンサービス、WF シーケンシャルサービス、XAML WF ステートマシンサービス、および XAML WF シーケンシャルサービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-117">This includes WCF Service, WF State Machine Service, WF Sequential Service, XAML WF State Machine Service and XAML WF Sequential Service.</span></span>

<span data-ttu-id="4b6f4-118">ただし、このツールでホストを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-118">You should note, however, that the tool will not help you to configure a host.</span></span> <span data-ttu-id="4b6f4-119">このタスクでは、App.config ファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-119">For this task, you must manually edit the App.config file.</span></span> <span data-ttu-id="4b6f4-120">また、このツールでユーザー定義の構成ファイルを検証することはできません。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-120">The tool also does not validate user-defined configuration files.</span></span>

> [!CAUTION]
> <span data-ttu-id="4b6f4-121">WCF サービスホストは、この目的のために設計されていないため、運用環境でサービスをホストするためには使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-121">You should not use WCF Service Host to host services in a production environment, as it was not engineered for this purpose.</span></span>  <span data-ttu-id="4b6f4-122">WCF サービスホストは、このような環境の信頼性、セキュリティ、および管理容易性の要件をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-122">WCF Service Host does not support the reliability, security, and manageability requirements of such an environment.</span></span> <span data-ttu-id="4b6f4-123">代わりに IIS を使用してください。IIS は、より高度な信頼性機能や監視機能を備えており、サービスをホストするのに適しています。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-123">Instead, use IIS since it provides superior reliability and monitoring features, and is the preferred solution for hosting services.</span></span> <span data-ttu-id="4b6f4-124">サービスの開発が完了したら、WCF サービスホストから IIS にサービスを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-124">Once development of your services is complete, you should migrate the services from WCF Service Host to IIS.</span></span>

## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a><span data-ttu-id="4b6f4-125">Visual Studio 内で WCF サービス ホストを使用するシナリオ</span><span class="sxs-lookup"><span data-stu-id="4b6f4-125">Scenarios for Using WCF Service Host inside Visual Studio</span></span>

<span data-ttu-id="4b6f4-126">次の表に、[ **コマンドライン引数** ] ダイアログボックスのすべてのパラメーターを示します。このダイアログボックスは、Visual Studio の **ソリューションエクスプローラー** でプロジェクトを右クリックし、[ **プロパティ**] を選択し、[ **デバッグ** ] タブを選択して [ **プロジェクトの開始**] をクリックすると表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-126">The following table lists all the parameters in the **Command line arguments** dialog box, which can be found by right-clicking your project in **Solutions Explorer** in Visual Studio, selecting **Properties**, then selecting the **Debug** tab and clicking **Start Project**.</span></span> <span data-ttu-id="4b6f4-127">これらのパラメーターは、WCF サービスホストを構成するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-127">These parameters are useful in configuring WCF Service Host.</span></span>

|<span data-ttu-id="4b6f4-128">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b6f4-128">Parameter</span></span>|<span data-ttu-id="4b6f4-129">意味</span><span class="sxs-lookup"><span data-stu-id="4b6f4-129">Meaning</span></span>|
|---------------|-------------|
|`/client`|<span data-ttu-id="4b6f4-130">サービスのホストが開始された後に実行する実行可能ファイルへのパスを指定するオプション パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-130">An optional parameter that specifies the path to an executable to run after the services are hosted.</span></span> <span data-ttu-id="4b6f4-131">これにより、ホストの後に WCF テストクライアントが起動します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-131">This launches WCF Test Client following hosting.</span></span>|
|`/clientArg`|<span data-ttu-id="4b6f4-132">カスタム クライアント アプリケーションに渡す引数として文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-132">Specify a string as an argument that is passed to the custom client application.</span></span>|
|`/?`|<span data-ttu-id="4b6f4-133">ヘルプ テキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-133">Displays the help text.</span></span>|

#### <a name="using-wcf-test-client"></a><span data-ttu-id="4b6f4-134">WCF のテスト用クライアントの使用</span><span class="sxs-lookup"><span data-stu-id="4b6f4-134">Using WCF Test Client</span></span>

<span data-ttu-id="4b6f4-135">新しい WCF サービスプロジェクトを作成し、F5 キーを押してデバッガーを起動すると、WCF サービスホストは、プロジェクト内で検出されたすべてのサービスのホストを開始します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-135">After you create a new WCF service project and press F5 to start the debugger, WCF Service Host starts hosting all the services it finds in your project.</span></span> <span data-ttu-id="4b6f4-136">WCF テストクライアントが自動的に開き、構成ファイルで定義されているサービスエンドポイントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-136">WCF Test Client automatically opens and displays a list of service endpoints defined in the configuration file.</span></span> <span data-ttu-id="4b6f4-137">メイン ウィンドウでパラメーターをテストしたり、サービスを呼び出したりできます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-137">From the main window, you can test the parameters and invoke your service.</span></span>

<span data-ttu-id="4b6f4-138">WCF テストクライアントが使用されていることを確認するには、Visual Studio の **ソリューションエクスプローラー** でプロジェクトを右クリックし、[ **プロパティ**] をクリックして、[ **デバッグ** ] タブを選択します。[ **プロジェクトの開始** ] をクリックし、[ **コマンドライン引数** ] ダイアログボックスに次のコードが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-138">To make sure that WCF Test Client is used, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and ensure that the following appears in the **Command line arguments** dialog box.</span></span>

`/client:WcfTestClient.exe`

#### <a name="using-a-custom-client"></a><span data-ttu-id="4b6f4-139">カスタム クライアントの使用</span><span class="sxs-lookup"><span data-stu-id="4b6f4-139">Using a Custom Client</span></span>

<span data-ttu-id="4b6f4-140">カスタムクライアントを使用するには、Visual Studio の **ソリューションエクスプローラー** でプロジェクトを右クリックし、[ **プロパティ**] をクリックして、[ **デバッグ** ] タブを選択します。次の例に示すように、[ **プロジェクトの開始** ] をクリックし、[ `/client` **コマンドライン引数** ] ダイアログボックスでパラメーターを編集して、カスタムクライアントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-140">To use a custom client, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and edit the `/client` parameter in the **Command line arguments** dialog box to point to your custom client, as indicated in the following example.</span></span>

`/client:"path/CustomClient.exe"`

<span data-ttu-id="4b6f4-141">F5 キーを押してサービスを再び開始すると、デバッガーを起動すると、WCF サービスホストによって自動的にカスタムクライアントが開始されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-141">When you press F5 to start the service again, WCF Service Host automatically starts your custom client when you launch the debugger.</span></span>

<span data-ttu-id="4b6f4-142">`/clientArg:` パラメーターを使用して、カスタム クライアント アプリケーションに渡す引数として文字列を指定することもできます。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-142">You can also use the `/clientArg:` parameter to specify a string as an argument that is passed to the custom client application, as indicated in the following example.</span></span>

`/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`

<span data-ttu-id="4b6f4-143">たとえば、配信サービス ライブラリ テンプレートを使用している場合は、次のコマンド ライン引数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-143">For example, if you are using the Syndication Service Library template, you can use the following command line arguments,</span></span>

`/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`

#### <a name="specifying-no-client"></a><span data-ttu-id="4b6f4-144">クライアントを指定しない場合</span><span class="sxs-lookup"><span data-stu-id="4b6f4-144">Specifying No Client</span></span>

<span data-ttu-id="4b6f4-145">WCF サービスをホストした後にクライアントを使用しないように指定するには、Visual Studio の **ソリューションエクスプローラー** でプロジェクトを右クリックし、[ **プロパティ**] をクリックして、[ **デバッグ** ] タブを選択します。[ **プロジェクトの開始** ] をクリックし、[ **コマンドライン引数** ] ダイアログボックスを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-145">To specify that no client will be used after WCF service hosting, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and leave the **Command line arguments** dialog box blank.</span></span>

#### <a name="using-a-custom-host"></a><span data-ttu-id="4b6f4-146">カスタム ホストの使用</span><span class="sxs-lookup"><span data-stu-id="4b6f4-146">Using a Custom Host</span></span>

<span data-ttu-id="4b6f4-147">カスタムホストを使用するには、Visual Studio の **ソリューションエクスプローラー** でプロジェクトを右クリックし、[ **プロパティ**] をクリックして、[ **デバッグ** ] タブを選択します。[ **外部プログラムの開始** ] をクリックし、カスタムホストへの完全なパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-147">To use a custom host, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start External Program** and enter the full path to the custom host.</span></span> <span data-ttu-id="4b6f4-148">[ **コマンドライン引数** ] ダイアログボックスを使用して、ホストに渡す引数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-148">You can also use the **Command line arguments** dialog box to specify arguments to be passed to the host.</span></span>

## <a name="wcf-service-host-user-interface"></a><span data-ttu-id="4b6f4-149">WCF サービス ホストのユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b6f4-149">WCF Service Host User Interface</span></span>

<span data-ttu-id="4b6f4-150">(Visual Studio 内で F5 キーを押して) 最初に WCF サービスホストを呼び出すと、[ **Wcf サービスホスト** ] ウィンドウが自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-150">When you initially invoke WCF Service Host (by pressing F5 inside Visual Studio), the **WCF Service Host** window automatically opens.</span></span> <span data-ttu-id="4b6f4-151">WCF サービスホストが実行されている場合、プログラムのアイコンが通知領域に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-151">When WCF Service Host is running, the program's icon appears in the notification area.</span></span> <span data-ttu-id="4b6f4-152">アイコンをダブルクリックして、[ **WCF サービスホスト** ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-152">Double-click the icon to open the **WCF Service Host** window</span></span>

<span data-ttu-id="4b6f4-153">サービスホスティング中にエラーが発生すると、[WCF サービスホスト] ダイアログボックスが開き、関連する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-153">When errors occur during service hosting, WCF Service Host dialog box will open to display relevant information.</span></span>

<span data-ttu-id="4b6f4-154">**WCF サービスホスト**のメインウィンドウには、次の2つのメニューがあります。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-154">The **WCF Service Host** main window contains two menus:</span></span>

- <span data-ttu-id="4b6f4-155">**File**: **Close** および **Exit** コマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-155">**File**: Contains the **Close** and **Exit** commands.</span></span> <span data-ttu-id="4b6f4-156">[ **閉じる**] をクリックすると、[ **WCF サービスホスト** ] ダイアログボックスが閉じますが、サービスは引き続きホストされます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-156">When you click **Close**, the **WCF Service Host** dialog box closes, but the services continue to be hosted.</span></span> <span data-ttu-id="4b6f4-157">[ **終了**] をクリックすると、WCF サービスホストもシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-157">When you click **Exit**, WCF Service Host is also shut down.</span></span> <span data-ttu-id="4b6f4-158">ホストされているサービスもすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-158">This also stops all hosted services.</span></span>

- <span data-ttu-id="4b6f4-159">**Help**: バージョン情報が含まれている **About** コマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-159">**Help**: Contains the **About** command that contains version information.</span></span> <span data-ttu-id="4b6f4-160">ヘルプファイルを開くことができる **ヘルプ** コマンドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-160">It also contains the **Help** command that can open a help file.</span></span>

<span data-ttu-id="4b6f4-161">メインの [ **WCF サービスホスト** ] ウィンドウには、次の2つの領域があります。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-161">The main **WCF Service Host** window contains two areas:</span></span>

- <span data-ttu-id="4b6f4-162">最初の領域は **Service**です。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-162">The first area is **Service**.</span></span> <span data-ttu-id="4b6f4-163">この領域には、すべてのサービスの基本情報が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-163">It contains a list that displays basic information of all services.</span></span> <span data-ttu-id="4b6f4-164">具体的には、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-164">The information includes:</span></span>

  - <span data-ttu-id="4b6f4-165">**サービス**: すべてのサービスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-165">**Service**: Lists all the services.</span></span>

  - <span data-ttu-id="4b6f4-166">**状態**: サービスの状態を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-166">**Status**: Lists the status of the service.</span></span> <span data-ttu-id="4b6f4-167">有効な値は、"開始"、"停止"、および "エラー" です。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-167">Valid values are "Started", "Stopped," and "Error".</span></span>

  - <span data-ttu-id="4b6f4-168">[**メタデータアドレス**: サービスのメタデータアドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-168">**Metadata Address**: Displays the metadata address of the services.</span></span>

- <span data-ttu-id="4b6f4-169">2つ目の領域は **追加情報**です。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-169">The second area is **Additional Information**.</span></span> <span data-ttu-id="4b6f4-170">**サービスエリアで**特定のサービスラインが選択されている場合に、サービスの状態の詳細な説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-170">It displays a detailed explanation of the service status when the specific service line is selected in the **Service** area.</span></span> <span data-ttu-id="4b6f4-171">状態が "エラー" の場合は、完全なエラー メッセージを画面上で確認できます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-171">If the status is Error, you can view the full error message on the screen.</span></span>

## <a name="stopping-wcf-service-host"></a><span data-ttu-id="4b6f4-172">WCF サービス ホストの停止</span><span class="sxs-lookup"><span data-stu-id="4b6f4-172">Stopping WCF Service Host</span></span>

<span data-ttu-id="4b6f4-173">WCF サービスホストは、次の4つの方法でシャットダウンできます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-173">You can shut down WCF Service Host in the following four ways:</span></span>

- <span data-ttu-id="4b6f4-174">Visual Studio でデバッグセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-174">Stop the debugging session in Visual Studio.</span></span>

- <span data-ttu-id="4b6f4-175">[ **WCF サービスホスト**] ウィンドウの [**ファイル**] メニューから [**終了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-175">Select **Exit** from the **File** menu in the **WCF Service Host** window.</span></span>

- <span data-ttu-id="4b6f4-176">システム通知領域で、WCF サービスホストトレイアイコンのコンテキストメニューから [ **終了** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-176">Select **Exit** from context menu of WCF Service Host tray icon in the system notification area.</span></span>

- <span data-ttu-id="4b6f4-177">WCF テストクライアントが使用されている場合は、終了します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-177">Exit WCF Test Client if it is being used.</span></span>

## <a name="using-service-host-without-administrator-privilege"></a><span data-ttu-id="4b6f4-178">管理特権を必要としないサービス ホストの使用</span><span class="sxs-lookup"><span data-stu-id="4b6f4-178">Using Service Host without Administrator privilege</span></span>

<span data-ttu-id="4b6f4-179">管理者特権を持たないユーザーが WCF サービスを開発できるようにするには、 http://+:8731/Design_Time_Addresses Visual Studio のインストール時に、名前空間 "" の ACL (Access Control リスト) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-179">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="4b6f4-180">この ACL は (UI) に設定され、コンピューターにログオンしているすべての対話ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-180">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="4b6f4-181">管理者は、この ACL のユーザーを追加または削除したり、追加のポートを開いたりすることができます。この ACL により、ユーザーは管理者特権を付与せずに、WCF サービスの自動ホスト (wcfSvcHost.exe) を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-181">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>

<span data-ttu-id="4b6f4-182">アクセス権を変更するには、管理者特権で Windows Vista の netsh.exe ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-182">You can modify access using the netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="4b6f4-183">netsh.exe の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-183">The following is an example of using netsh.exe.</span></span>

```console
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>
```

<span data-ttu-id="4b6f4-184">netsh.exe の詳細については、「[Netsh.exe ツールとコマンドラインスイッチの使用方法](/previous-versions/tn-archive/bb490939(v=technet.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b6f4-184">For more information on netsh.exe, see "[How to Use the Netsh.exe Tool and Command-Line Switches](/previous-versions/tn-archive/bb490939(v=technet.10))".</span></span>

## <a name="see-also"></a><span data-ttu-id="4b6f4-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b6f4-185">See also</span></span>

- [<span data-ttu-id="4b6f4-186">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="4b6f4-186">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
