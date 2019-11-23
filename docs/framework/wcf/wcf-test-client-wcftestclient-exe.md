---
title: WCF のテスト用クライアント (WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: ac89b234dfafe3f87f1423a04ce8e4dd6b44b991
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321191"
---
# <a name="wcf-test-client-wcftestclientexe"></a><span data-ttu-id="2f4bf-102">WCF のテスト用クライアント (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="2f4bf-102">WCF Test Client (WcfTestClient.exe)</span></span>
<span data-ttu-id="2f4bf-103">Windows Communication Foundation (WCF) テストクライアント (Wcftestclient.exe) は、ユーザーがテストパラメーターを入力し、その入力をサービスに送信し、サービスから返される応答を表示できるようにする GUI ツールです。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-103">Windows Communication Foundation (WCF) Test Client (WcfTestClient.exe) is a GUI tool that enables users to input test parameters, submit that input to the service, and view the response that the service sends back.</span></span> <span data-ttu-id="2f4bf-104">WCF サービスホストと組み合わせると、シームレスなサービステストエクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-104">It provides a seamless service testing experience when combined with WCF Service Host.</span></span>

<span data-ttu-id="2f4bf-105">通常、WCF テストクライアント (Wcftestclient.exe) は次の場所にあります。 `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` コミュニティは、インストールされている Visual Studio のレベルに応じて、"Enterprise"、"Professional"、または "Community" のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-105">You can typically find the WCF Test Client (WcfTestClient.exe) in the following location: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` - Community may be one of "Enterprise", "Professional" or "Community" depending on which level of Visual Studio is installed.</span></span>

## <a name="scenarios-for-using-test-client"></a><span data-ttu-id="2f4bf-106">テスト用クライアントを使用するシナリオ</span><span class="sxs-lookup"><span data-stu-id="2f4bf-106">Scenarios for Using Test Client</span></span>

<span data-ttu-id="2f4bf-107">以下のセクションでは、WCF テストクライアントを使用して開発プロセスを効率化できる最も一般的なシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-107">The following sections discuss the most common scenarios in which you can use WCF Test Client to streamline your development process.</span></span>

### <a name="inside-visual-studio"></a><span data-ttu-id="2f4bf-108">Visual Studio 内</span><span class="sxs-lookup"><span data-stu-id="2f4bf-108">Inside Visual Studio</span></span>

#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a><span data-ttu-id="2f4bf-109">WCF サービス ホストが、1 つのサービスを使用する WCF のテスト用クライアントを開始する</span><span class="sxs-lookup"><span data-stu-id="2f4bf-109">WCF Service Host Starts WCF Test Client with a Single Service</span></span>

<span data-ttu-id="2f4bf-110">新しい WCF サービスプロジェクトを作成し、F5 キーを押してデバッガーを起動した後、WCF サービスホストがプロジェクト内のサービスのホストを開始します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-110">After you create a new WCF service project and press F5 to start the debugger, the WCF Service Host begins to host the service in your project.</span></span> <span data-ttu-id="2f4bf-111">次に、WCF テストクライアントが開き、構成ファイルで定義されているサービスエンドポイントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-111">Then, WCF Test Client opens and displays a list of service endpoints defined in the configuration file.</span></span> <span data-ttu-id="2f4bf-112">ユーザーは、パラメーターをテストしてサービスを呼び出すことができ、このプロセスを繰り返して、サービスのテストおよび検証を継続的に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-112">You can test the parameters and invoke the service, and repeat this process to continuously test and validate your service.</span></span>

#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a><span data-ttu-id="2f4bf-113">WCF サービス ホストが、複数のサービスを使用する WCF のテスト用クライアントを開始する</span><span class="sxs-lookup"><span data-stu-id="2f4bf-113">WCF Service Host Starts WCF Test Client with Multiple Services</span></span>

<span data-ttu-id="2f4bf-114">また、WCF テストクライアントを使用して、複数のサービスを含むサービスプロジェクトをデバッグすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-114">You can also use WCF Test Client to help debug a service project that contains multiple services.</span></span> <span data-ttu-id="2f4bf-115">WCF テストクライアントを開くと、プロジェクト内のサービスの一覧が自動的に反復処理され、テストのために開かれます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-115">When WCF Test Client opens, it automatically iterates the list of services in your project and opens them for testing.</span></span>

### <a name="outside-visual-studio"></a><span data-ttu-id="2f4bf-116">Visual Studio の外部</span><span class="sxs-lookup"><span data-stu-id="2f4bf-116">Outside Visual Studio</span></span>

<span data-ttu-id="2f4bf-117">また、Visual Studio の外部で WCF テストクライアント (Wcftestclient.exe) を呼び出して、インターネット上の任意のサービスをテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-117">You can also invoke the WCF Test Client (WcfTestClient.exe) outside Visual Studio to test an arbitrary service on the Internet.</span></span> <span data-ttu-id="2f4bf-118">このツールを見つけるには、次の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-118">To locate the tool, go to the following location:</span></span>

<span data-ttu-id="2f4bf-119">`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (どのレベルの Visual Studio がコンピューターにインストールされているかによって、community は "Enterprise"、"Professional"、"Community" のいずれかになります)</span><span class="sxs-lookup"><span data-stu-id="2f4bf-119">`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (where community can be one of "Enterprise", "Professional" or "Community" depending on which level of Visual Studio is installed on the machine)</span></span>

<span data-ttu-id="2f4bf-120">ツールを使用するには、ファイル名をダブルクリックしてこの場所からツールを開くか、コマンド ラインからツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-120">To use the tool, double-click the file name to open it from this location, or launch it from a command line.</span></span>

<span data-ttu-id="2f4bf-121">WCF テストクライアントは、コマンドライン引数として任意の数の Uri を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-121">WCF Test Client takes an arbitrary number of URIs as command line arguments.</span></span>  <span data-ttu-id="2f4bf-122">これらの引数には、テストできるサービスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-122">These are the URIs of services that can be tested.</span></span>

`wcfTestClient.exe URI1 URI2 …`

<span data-ttu-id="2f4bf-123">WCF テストクライアントウィンドウが開いたら、[->**ファイル**] をクリックし、 **[サービスの追加]** をクリックして、開くサービスのエンドポイントアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-123">After the WCF Test Client window is opened, click **File**->**Add Service**, and enter the endpoint address of the service you want to open.</span></span>

## <a name="wcf-test-client-user-interface"></a><span data-ttu-id="2f4bf-124">WCF のテスト用クライアントのユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f4bf-124">WCF Test Client User Interface</span></span>

<span data-ttu-id="2f4bf-125">WCF テストクライアントは、1つのサービスまたは複数のサービスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-125">You can use WCF Test Client with a single service or multiple services.</span></span>

### <a name="service-operations"></a><span data-ttu-id="2f4bf-126">サービス操作</span><span class="sxs-lookup"><span data-stu-id="2f4bf-126">Service Operations</span></span>

<span data-ttu-id="2f4bf-127">WCF テストクライアントのメインウィンドウの左ペインには、使用可能なすべてのサービスと、それぞれのエンドポイントと操作が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-127">The left pane of the WCF Test Client main window lists all the available services, along with their respective endpoints and operations.</span></span>

<span data-ttu-id="2f4bf-128">操作をダブルクリックすると、その操作の名前が付いた新しいタブ内の右ペインで、操作の内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-128">When you double-click an operation, you can view its content in the right pane inside a new tab with the operation's name.</span></span>

<span data-ttu-id="2f4bf-129">左ペインには、クライアントの構成ファイルも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-129">The left pane also lists client configuration files.</span></span> <span data-ttu-id="2f4bf-130">いずれかの項目をダブルクリックすると、右ペインの新しいタブ付きウィンドウにファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-130">Double-click any of the items to display the content of the file in a new tabbed window in the right pane.</span></span>

### <a name="entering-test-parameters"></a><span data-ttu-id="2f4bf-131">テスト パラメーターの入力</span><span class="sxs-lookup"><span data-stu-id="2f4bf-131">Entering Test Parameters</span></span>

<span data-ttu-id="2f4bf-132">テスト パラメーターを表示するには、右ペインで操作をダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-132">To view the test parameters, double-click an operation to open it in the right pane.</span></span> <span data-ttu-id="2f4bf-133">既定では、パラメーターは**書式付き**ビューで表示されます。また、パラメーターに任意の値を入力して、サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-133">The parameters are showed in **Formatted** view by default, and you can enter arbitrary values for the parameters to test the service.</span></span>

<span data-ttu-id="2f4bf-134">メッセージの XML を表示するには、 **[xml]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-134">To view the message's XML, click **XML**.</span></span> <span data-ttu-id="2f4bf-135">サービスに送信するには、 **[呼び出し]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-135">To send them to the service, click **Invoke**.</span></span>

<span data-ttu-id="2f4bf-136">データセットパラメーターの場合は、[. **.** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-136">For a DataSet parameter, click the **…**</span></span> <span data-ttu-id="2f4bf-137">[編集] の横にあるボタン. **.**</span><span class="sxs-lookup"><span data-stu-id="2f4bf-137">button next to **Edit…**</span></span> <span data-ttu-id="2f4bf-138">データグリッドを表示する新しいウィンドウで編集します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-138">to edit it in a new window showing the DataGrid.</span></span> <span data-ttu-id="2f4bf-139">**[データセットのコピー]** ボタンと **[データセットの貼り付け]** ボタンの外観がわかります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-139">Notice the appearance of the **Copy DataSet** and **Paste DataSet** buttons.</span></span> <span data-ttu-id="2f4bf-140">最初の編集時に DataSet オブジェクトのスキーマが不明の場合、DataGrid は空になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-140">If the schema of the DataSet object is unknown upon the first edit, the DataGrid is empty.</span></span> <span data-ttu-id="2f4bf-141">スキーマが同じ DataSet オブジェクトを DataGrid の現在のオブジェクトに貼り付ける必要があります</span><span class="sxs-lookup"><span data-stu-id="2f4bf-141">You have to paste a DataSet object with the same schema into the current object in the DataGrid.</span></span> <span data-ttu-id="2f4bf-142">(貼り付け操作の前に、他の場所からスキーマをコピーする必要があることに注意してください)。 **[データセットのコピー]** ボタンをクリックして、将来使用するためにデータセットオブジェクトをコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-142">(Notice that you need to copy the schema from somewhere else before the paste operation.) You can also copy a Dataset object for future usage by clicking the **Copy DataSet** button.</span></span>

<span data-ttu-id="2f4bf-143">サービスの応答がテスト パラメーターの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-143">The service's response appears below the test parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="2f4bf-144">想定される戻り値が文字列の場合、入力が引用符で囲まれていなくても、結果は引用符で囲まれた文字列として表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-144">If the expected return value is a string, the result will be displayed as a quoted string even though the input provided was not in quotes.</span></span>

<span data-ttu-id="2f4bf-145">サービスのコントラクトの作成時に特定の操作を一方向として指定した場合は、サービスの応答は表示されません。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-145">If you specified a particular operation as one-way when you created the contract for the service, no service response is displayed.</span></span> <span data-ttu-id="2f4bf-146">メッセージが配信のキューに置かれると、メッセージが正常に送信されたことを通知するダイアログ ボックスがすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-146">As soon as the message is queued for delivery, a dialog box pops up to notify you that the message was successfully sent.</span></span>

### <a name="session-support"></a><span data-ttu-id="2f4bf-147">セッション サポート</span><span class="sxs-lookup"><span data-stu-id="2f4bf-147">Session Support</span></span>

<span data-ttu-id="2f4bf-148">サービス操作のタブで [**新しいプロキシを開始**する] チェックボックスをオンにすると、セッションのサポートを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-148">The **Start a new proxy** check box in a service operation's tab enables you to toggle session support.</span></span> <span data-ttu-id="2f4bf-149">既定では、このチェック ボックスはオフになります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-149">This box is cleared by default.</span></span>

<span data-ttu-id="2f4bf-150">特定の操作 (または同じサービスエンドポイントの別の操作) に対してテストパラメーターを入力し、チェックボックスをオフにして **[呼び出し]** を複数回クリックすると、これらの操作は1つのプロキシを共有し、サービスの状態は複数の操作にわたって保持されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-150">When you enter test parameters for a specific operation (or another operation in the same service endpoint) and click **Invoke** multiple times with the check box cleared, these operations share one proxy and the service status is persisted across multiple operations.</span></span>

<span data-ttu-id="2f4bf-151">[**新しいプロキシを開始**する] チェックボックスがオンになっている場合は、**呼び出し**ごとに新しいプロキシが開始され、前のセッションシナリオが終了して、サービスの状態がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-151">If the **Start a new proxy** check box is checked, a new proxy is started for each **Invoke**, the previous session scenario is ended, and the service status is reset.</span></span>

### <a name="editing-client-configuration"></a><span data-ttu-id="2f4bf-152">クライアント構成の編集</span><span class="sxs-lookup"><span data-stu-id="2f4bf-152">Editing Client Configuration</span></span>

<span data-ttu-id="2f4bf-153">WCF テストクライアントのメインウィンドウの左ペインには、クライアント構成ファイルが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-153">The left pane of the WCF Test Client main window lists client configuration files.</span></span> <span data-ttu-id="2f4bf-154">いずれかの項目をダブルクリックすると、右ペインにファイルの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-154">Double-click any of the items to display the contents of the file in the right pane.</span></span>

#### <a name="edit-with-service-configuration-editor"></a><span data-ttu-id="2f4bf-155">サービス構成エディターを使用した編集</span><span class="sxs-lookup"><span data-stu-id="2f4bf-155">Edit with Service Configuration Editor</span></span>

<span data-ttu-id="2f4bf-156">左側のウィンドウで **[Config File]** を右クリックし、コンテキストメニューの **[Edit with svcconfigeditor.exe]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-156">Right-click **Config File** in the left pane and select the context menu **Edit with SvcConfigEditor**.</span></span> <span data-ttu-id="2f4bf-157">サービス構成エディターが起動し、クライアント構成の内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-157">Service Configuration Editor is launched with the client configuration content.</span></span> <span data-ttu-id="2f4bf-158">このツール内で構成を編集して保存できます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-158">You can edit the configuration and save it within the tool.</span></span>

<span data-ttu-id="2f4bf-159">サービス構成エディターでファイルを保存した後、ファイルが外部で変更されたことを知らせる警告メッセージが WCF テストクライアントに表示され、再度読み込むかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-159">After saving the file in Service Configuration Editor, WCF Test Client displays a warning message to inform you that the file has been modified outside and asks whether you would like to reload it.</span></span>

<span data-ttu-id="2f4bf-160">**はい** を選択すると、クライアントの .dll. .config タブの構成内容に、エディターで行った変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-160">If you select **Yes**, the configuration content in the "Client.dll.config" tab reflects the changes you made in the editor.</span></span>

<span data-ttu-id="2f4bf-161">**いいえ** を選択した場合、クライアントの .dll. .config タブの構成内容は変更されず、変更されたコンテンツは自動的にソースファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-161">If you select **No**, the configuration content in the "Client.dll.config" tab remains unchanged and the modified content is automatically saved to the source file.</span></span>

#### <a name="restore-to-default-configuration"></a><span data-ttu-id="2f4bf-162">既定の構成への復元</span><span class="sxs-lookup"><span data-stu-id="2f4bf-162">Restore to Default Configuration</span></span>

<span data-ttu-id="2f4bf-163">すべての変更を取り消して、既定のクライアント構成に復元する場合は、左側のウィンドウで **[Config File]** を右クリックし、コンテキストメニューの **[既定の構成に復元]** を選択します。既定の構成値が読み込まれ、"Client. .dll. .config" タブにコンテンツが復元されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-163">If you want to cancel all the changes and restore to the default client configuration, right-click **Config File** in the left pane and select the context menu **Restore to Default Config**. The default configuration value is loaded and content in "Client.dll.config" tab is restored.</span></span>

#### <a name="validate-changes"></a><span data-ttu-id="2f4bf-164">変更の検証</span><span class="sxs-lookup"><span data-stu-id="2f4bf-164">Validate Changes</span></span>

<span data-ttu-id="2f4bf-165">保存された変更が WCF テストクライアントに読み込まれるときに、WCF スキーマに対して構成が有効かどうかがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-165">When saved changes are being loaded in WCF Test Client, the configuration is checked for validity against WCF schema.</span></span> <span data-ttu-id="2f4bf-166">エラーが見つかった場合は、エラーの詳細を示すダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-166">If errors are found, a dialog box is displayed to show error details.</span></span>

<span data-ttu-id="2f4bf-167">プロキシの生成中、バイナリのコンパイル中、またはサービスの呼び出し時に、編集をサポートするメニュー項目 ("Edit..."、"Restore..." など) は無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-167">During proxy generation, binary compiling, or service invoking, menu items that support editing (that is, "Edit …", "Restore …", and so on) are disabled.</span></span> <span data-ttu-id="2f4bf-168">サービスの呼び出しは、更新された構成を WCF テストクライアントに読み込むときにも無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-168">Service invocation is also disabled when loading updated configuration to WCF Test Client.</span></span>

#### <a name="persist-client-configuration"></a><span data-ttu-id="2f4bf-169">クライアント構成の保持</span><span class="sxs-lookup"><span data-stu-id="2f4bf-169">Persist Client Configuration</span></span>

<span data-ttu-id="2f4bf-170">[**ツール**->**オプション**]-> **[クライアントの構成]** タブには、 **[サービスの起動時に常に構成を再生成]** する オプションがあります。これは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-170">The **Tools**->**Options**->**Client Configuration** tab contains an **Always Regenerate Config When Launching Services** option, which is enabled by default.</span></span> <span data-ttu-id="2f4bf-171">このオプションは、WCF テストクライアントがサービスを読み込むたびに、最新のサービスコントラクトとサービスの App.config ファイルに基づいて構成ファイルを再生成することを指定します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-171">This option specifies that every time WCF Test Client loads a service, it regenerates a configuration file based on the latest service contract and service App.config files.</span></span>

<span data-ttu-id="2f4bf-172">WCF サービスのクライアント構成を編集していて、この更新されたファイルを常に使用してサービスをデバッグする場合は、 **[再生成]** オプションをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-172">If you have edited the client configuration for your WCF service and want to always use this updated file to debug your service, you can uncheck the **Regenerate** option.</span></span> <span data-ttu-id="2f4bf-173">これにより、サービスを更新して WCF テストクライアントを再度開く場合でも、クライアントの .dll .config ファイルは、更新されたサービスに基づいて再生成されたものではなく、以前に更新したものになります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-173">By doing so, even when you update the service and reopen WCF Test Client, the Client.dll.config file is the one you updated previously instead of a regenerated one based on the updated service.</span></span>

<span data-ttu-id="2f4bf-174">ただし、再生成されたプロキシとの一貫性を保つために、構成ファイルの編集が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-174">However, you might need to edit the configuration file to make it consistent with the regenerated proxy.</span></span> <span data-ttu-id="2f4bf-175">サービスを更新したことが原因で、再生成されたプロキシと構成ファイルが一致しなくなると、サービスを呼び出したときにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-175">If the regenerated proxy and configuration file are mismatched due to an updated service, errors will occur when the service is invoked.</span></span>

> [!CAUTION]
> <span data-ttu-id="2f4bf-176">変更したクライアント構成ファイルを後で再利用することにした場合、該当するファイルは次の場所で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-176">If you have modified the client configuration file and select to reuse it in the future, you can find the file in the following location:</span></span>
>
> <span data-ttu-id="2f4bf-177">\Documents と Settings\\[User Account] \My Documents\Test Client Projects.</span><span class="sxs-lookup"><span data-stu-id="2f4bf-177">\Documents and Settings\\[User Account]\My Documents\Test Client Projects.</span></span>
>
> <span data-ttu-id="2f4bf-178">クライアント構成ファイルに格納されている更新された資格情報は、このフォルダーのアクセス制御リスト (ACL) によって保護されています。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-178">Any updated credential information stored to the client configuration file is protected by the Access Control List (ACL) of this folder.</span></span>

### <a name="adding-removing-and-refreshing-services"></a><span data-ttu-id="2f4bf-179">サービスの追加、削除、および更新</span><span class="sxs-lookup"><span data-stu-id="2f4bf-179">Adding, Removing and Refreshing Services</span></span>

#### <a name="add-service"></a><span data-ttu-id="2f4bf-180">サービスの追加</span><span class="sxs-lookup"><span data-stu-id="2f4bf-180">Add Service</span></span>

<span data-ttu-id="2f4bf-181">[**ファイル**->**追加**] をクリックして、WCF テストクライアントにサービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-181">Click **File**->**Add Service** to add a service to WCF Test Client.</span></span> <span data-ttu-id="2f4bf-182">次に、追加するサービスの URI (エンドポイント アドレス) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-182">You are then required to type the URI (endpoint address) of the service to be added.</span></span> <span data-ttu-id="2f4bf-183">サービスのアドレスには、MEX アドレスまたは WSDL アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-183">The service’s address can be a mex address or WSDL address.</span></span>

<span data-ttu-id="2f4bf-184">[**最近使用**したサービス] サブメニューには、最近追加された10個のサービスのエンドポイントの一覧も表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-184">You can also find a list of 10 recently added services' endpoints in the **Recent Services** submenu.</span></span> <span data-ttu-id="2f4bf-185">これらのいずれかを選択すると、指定したサービスが WCF テストクライアントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-185">If you select one of them, the specified service is added to WCF Test Client.</span></span>

<span data-ttu-id="2f4bf-186">また、サービスツリーの **[マイサービスプロジェクト**] のルートを右クリックし、 **[サービスの追加]** を選択すると、同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-186">You can also right-click the root of service tree **My Service Projects**, and select **Add Service** to achieve the same result.</span></span>

<span data-ttu-id="2f4bf-187">プロキシの生成中、バイナリのコンパイル中、またはサービスの呼び出し中は、サービスの追加をサポートするメニュー項目が無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-187">During proxy generation, binary compiling, or service invocation, menu items that support adding a service are disabled.</span></span> <span data-ttu-id="2f4bf-188">また、サービスの呼び出しも無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-188">Service invocation is also disabled.</span></span>

#### <a name="remove-service"></a><span data-ttu-id="2f4bf-189">サービスの削除</span><span class="sxs-lookup"><span data-stu-id="2f4bf-189">Remove Service</span></span>

<span data-ttu-id="2f4bf-190">削除するサービスのサービスルートを右クリックし、 **[サービスの削除]** を選択して、WCF テストクライアントからサービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-190">Right-click the service root of the service to be removed, and select **Remove Service** to remove a service from WCF Test Client.</span></span>

<span data-ttu-id="2f4bf-191">プロキシの生成中、バイナリのコンパイル中、またはサービスの呼び出し中は、サービスの削除をサポートするメニュー項目が無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-191">During proxy generation, binary compiling, or service invocation, menu items that support removing a service are disabled.</span></span> <span data-ttu-id="2f4bf-192">また、サービスの呼び出しも無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-192">Service invocation is also disabled.</span></span>

#### <a name="refresh-service"></a><span data-ttu-id="2f4bf-193">サービスの更新</span><span class="sxs-lookup"><span data-stu-id="2f4bf-193">Refresh Service</span></span>

<span data-ttu-id="2f4bf-194">WCF テストクライアントの実行中にサービスに変更が加えられた場合に、そのサービスの WCF テストクライアントの実装が最新であることを確認するには、サービスのサービスルートを右クリックし、 **[サービスの更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-194">If a change is made to the service while WCF Test Client is running and you want to ensure that the WCF Test Client implementation for that service is up-to-date, right-click the service root of the service, and select **Refresh Service**.</span></span> <span data-ttu-id="2f4bf-195">更新後、サービスの状態はリセットされます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-195">Note that after refreshing, the service status is reset.</span></span>

<span data-ttu-id="2f4bf-196">プロキシの生成中、バイナリのコンパイル中、またはサービスの呼び出し中は、サービスの更新をサポートするメニュー項目が無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-196">During proxy generation, binary compiling, or service invocation, menu items that support refreshing a service are disabled.</span></span> <span data-ttu-id="2f4bf-197">また、サービスの呼び出しも無効になります。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-197">Service invocation is also disabled.</span></span>

## <a name="location-of-files-generated-by-the-test-client"></a><span data-ttu-id="2f4bf-198">テスト クライアントが生成するファイルの場所</span><span class="sxs-lookup"><span data-stu-id="2f4bf-198">Location of Files Generated by the Test Client</span></span>

<span data-ttu-id="2f4bf-199">既定では、WCF テストクライアントは、生成されたクライアントコードと構成ファイルを "%Appdata%\local\temp\test client projects Client Projects" フォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-199">By default, WCF Test Client stores generated client code and configuration files in the "%appdata%\Local\temp\Test Client Projects" folder.</span></span> <span data-ttu-id="2f4bf-200">このフォルダーは、WCF テストクライアントが終了した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-200">This folder is deleted after WCF Test Client exits.</span></span> <span data-ttu-id="2f4bf-201">WCF テストクライアントで構成ファイルが変更され、[サービスの開始] オプションが無効になっているときに [**常に構成を再生成**する] が有効になっている場合、変更されたファイルは、"My Documents\Test Client Projects" の下の "CachedConfig" フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-201">If a configuration file is modified in WCF Test Client and the **Always Regenerate Config When Launching Services** option is disabled, the modified file is copied to the "CachedConfig" folder under "My Documents\Test Client Projects" with a mapping (metadata-address-to-file-name) XML file as an index.</span></span>

<span data-ttu-id="2f4bf-202">また、コマンドラインで WCF テストクライアントを起動し、`/ProjectPath` スイッチを使用して生成されたファイルを保存するための新しいパスを指定するか、`/RestoreProjectPath` スイッチを使用して既定の場所を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-202">You can also start WCF Test Client in a command line, use the `/ProjectPath` switch to specify a new desired path for storing generated files, or use the `/RestoreProjectPath` switch to restore the default location.</span></span> <span data-ttu-id="2f4bf-203">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-203">The syntax is as follows:</span></span>

`wcfTestClient.exe /ProjectPath [desired location]`

<span data-ttu-id="2f4bf-204">このコマンドを実行しても、WCF テストクライアントは開かれません。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-204">Running this command does not open WCF Test Client.</span></span> <span data-ttu-id="2f4bf-205">フォルダーの場所が変更されるだけです。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-205">Only the folder location is changed.</span></span> <span data-ttu-id="2f4bf-206">このコマンドは、WCF テストクライアントが実行されているかどうかにかかわらず実行できます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-206">You can run this command whether WCF Test Client is running or not.</span></span> <span data-ttu-id="2f4bf-207">新しい場所は、WCF テストクライアントの再起動時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-207">The new location is applied when WCF Test Client is restarted.</span></span> <span data-ttu-id="2f4bf-208">場所情報は、レジストリ、または "%Appdata%\local\temp\test client projects Client Projects" フォルダー内の Wcftestclient.exe ファイルに保存できます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-208">The location information can be saved in registry, or in the WcfTestClient.exe.option file in the "%appdata%\Local\temp\Test Client Projects" folder.</span></span>

## <a name="features-supported-by-wcf-test-client"></a><span data-ttu-id="2f4bf-209">WCF のテスト用クライアントでサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="2f4bf-209">Features supported by WCF Test Client</span></span>

<span data-ttu-id="2f4bf-210">WCF テストクライアントでサポートされている機能の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-210">The following is a list of features supported by WCF Test Client:</span></span>

- <span data-ttu-id="2f4bf-211">サービスの呼び出し : 要求/応答メッセージおよび一方向メッセージ</span><span class="sxs-lookup"><span data-stu-id="2f4bf-211">Service Invocation: Request/Response and One-way message.</span></span>

- <span data-ttu-id="2f4bf-212">バインディング : Svcutil.exe でサポートされるすべてのバインディング</span><span class="sxs-lookup"><span data-stu-id="2f4bf-212">Bindings: all bindings supported by Svcutil.exe.</span></span>

- <span data-ttu-id="2f4bf-213">セッションの制御</span><span class="sxs-lookup"><span data-stu-id="2f4bf-213">Controlling Session.</span></span>

- <span data-ttu-id="2f4bf-214">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="2f4bf-214">Message Contract.</span></span>

- <span data-ttu-id="2f4bf-215">XML シリアル化</span><span class="sxs-lookup"><span data-stu-id="2f4bf-215">XML serialization.</span></span>

<span data-ttu-id="2f4bf-216">WCF テストクライアントでサポートされていない機能の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-216">The following is a list of features not supported by WCF Test Client:</span></span>

- <span data-ttu-id="2f4bf-217">型: <xref:System.IO.Stream>、<xref:System.ServiceModel.Channels.Message>、<xref:System.Xml.XmlElement>、<xref:System.Xml.XmlAttribute>、<xref:System.Xml.XmlNode>、<xref:System.Xml.Serialization.IXmlSerializable> インターフェイスを実装する型 (関連する <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 属性を含む)、<xref:System.Xml.Linq.XDocument> 型と <xref:System.Xml.Linq.XElement> 型、および ADO.NET <xref:System.Data.DataTable> 型。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-217">Types: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, types that implement the <xref:System.Xml.Serialization.IXmlSerializable> interface, including the related <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> attribute, and the <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> types and the ADO.NET <xref:System.Data.DataTable> type.</span></span>

- <span data-ttu-id="2f4bf-218">双方向コントラクト</span><span class="sxs-lookup"><span data-stu-id="2f4bf-218">Duplex contract.</span></span>

- <span data-ttu-id="2f4bf-219">トランザクション</span><span class="sxs-lookup"><span data-stu-id="2f4bf-219">Transaction.</span></span>

- <span data-ttu-id="2f4bf-220">セキュリティ: CardSpace、証明書、およびユーザー名/パスワード。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-220">Security: CardSpace , Certificate, and Username/Password.</span></span>

- <span data-ttu-id="2f4bf-221">バインディング : WSFederationBinding、任意のコンテキスト バインディングおよび HTTPS バインディング、WebHttpBinding (JSON 応答メッセージ サポート)</span><span class="sxs-lookup"><span data-stu-id="2f4bf-221">Bindings: WSFederationbinding, any Context bindings and Https binding, WebHttpbinding (Json response message support).</span></span>

## <a name="closing-wcf-test-client"></a><span data-ttu-id="2f4bf-222">WCF のテスト用クライアントの終了</span><span class="sxs-lookup"><span data-stu-id="2f4bf-222">Closing WCF Test Client</span></span>

<span data-ttu-id="2f4bf-223">WCF テストクライアントは、次の方法で閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-223">You can close WCF Test Client in the following ways:</span></span>

- <span data-ttu-id="2f4bf-224">**[ファイル]** メニューの **[終了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-224">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="2f4bf-225">または、WCF テストクライアントのメインウィンドウで、 **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-225">Alternatively, in the WCF Test Client main window, click **Close**.</span></span> <span data-ttu-id="2f4bf-226">どちらのアクションも、wcf サービスの自動ホストをシャットダウンし、visual Studio によって WCF テストクライアントが起動された場合に Visual Studio のデバッグプロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-226">Both of these actions also shut down WCF Service Auto Host and stop the Visual Studio debugging process if WCF Test Client was launched by Visual Studio.</span></span>

- <span data-ttu-id="2f4bf-227">通知領域の **WCF サービスホスト** アイコンを右クリックし、終了 をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="2f4bf-227">Right-click the **WCF Service Host** icon in the notification area, and then click **Exit.**</span></span> <span data-ttu-id="2f4bf-228">これにより、WCF サービスの自動ホストと WCF テストクライアントの両方がシャットダウンされ、Visual Studio のデバッグプロセスが停止します。</span><span class="sxs-lookup"><span data-stu-id="2f4bf-228">This shuts down both WCF Service Auto Host and WCF Test Client and stops the Visual Studio debugging process.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f4bf-229">参照</span><span class="sxs-lookup"><span data-stu-id="2f4bf-229">See also</span></span>

- [<span data-ttu-id="2f4bf-230">WCF サービス ホスト (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="2f4bf-230">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
