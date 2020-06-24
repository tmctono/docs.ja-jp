---
title: 構成エディター ツール (SvcConfigEditor.exe)
description: Wcf サービス構成エディターを使用して、WCF のバインディング、動作、サービス、および診断の設定を管理する方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 258437ff616b969d40feabbfff364ad2cc6b25bc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247650"
---
# <a name="configuration-editor-tool-svcconfigeditorexe"></a><span data-ttu-id="68d1a-103">構成エディター ツール (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="68d1a-103">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>

<span data-ttu-id="68d1a-104">管理者と開発者は、Windows Communication Foundation (WCF) サービス構成エディター (SvcConfigEditor.exe) のグラフィカル ユーザー インターフェイスを使用して、WCF サービスの構成設定を作成および変更できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-104">The Windows Communication Foundation (WCF) Service Configuration Editor (SvcConfigEditor.exe) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="68d1a-105">このツールを使用すると、XML 構成ファイルを直接編集せずに、WCF のバインディング、動作、サービス、および診断の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-105">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without having to directly edit XML configuration files.</span></span>

<span data-ttu-id="68d1a-106">サービス構成エディターは、C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-106">Service Configuration Editor can be found in the C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin folder.</span></span>

## <a name="the-wcf-configuration-editor"></a><span data-ttu-id="68d1a-107">WCF 構成エディター</span><span class="sxs-lookup"><span data-stu-id="68d1a-107">The WCF Configuration Editor</span></span>

<span data-ttu-id="68d1a-108">サービス構成エディターには、WCF のサービスやクライアントを構成する手順をすべてガイドするウィザードが付属しています。</span><span class="sxs-lookup"><span data-stu-id="68d1a-108">Service Configuration Editor comes with a wizard that guides you through all the steps in configuring a WCF service or client.</span></span> <span data-ttu-id="68d1a-109">エディターで直接編集する代わりにウィザードを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-109">You are strongly advised to use the wizard instead of the editor directly.</span></span>

<span data-ttu-id="68d1a-110">標準の System.Configuration スキーマに準拠する構成ファイルが既にいくつかある場合は、ユーザー インターフェイスを使用してバインディング、動作、サービス、および診断の固有の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-110">If you already have some configuration files that comply with the standard System.Configuration schema, you can manage specific settings for bindings, behavior, services, and diagnostics with the user interface.</span></span> <span data-ttu-id="68d1a-111">サービス構成エディターを使用すると、既存の WCF 構成ファイルの設定だけでなく、実行可能ファイル、COM+ サービス、および Web ホスト サービスの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-111">The Service Configuration Editor enables you to manage the settings for existing WCF configuration files as well as executable files, COM+ services, and Web-hosted services.</span></span> <span data-ttu-id="68d1a-112">サービス構成エディターで Web ホスト サービスを開くと、上位レベル ノードのサービス固有の構成セクションおよび継承された構成セクションの両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-112">When opening a Web-hosted service with Service Configuration Editor, both the service’s own configuration and inherited configurations sections of upper level nodes are shown.</span></span>

<span data-ttu-id="68d1a-113">WCF 構成設定は、構成ファイルの `<system.serviceModel>` セクションにあるため、エディターはこの要素の内容だけを操作し、同じファイル内の他の要素にはアクセスしません。</span><span class="sxs-lookup"><span data-stu-id="68d1a-113">Because WCF configuration settings are located in the `<system.serviceModel>` section of the configuration file, the editor operates exclusively on the content of this element and does not access other elements in the same file.</span></span> <span data-ttu-id="68d1a-114">既存の構成ファイルに直接移動したり、サービス、仮想ディレクトリ、または COM+ サービスを含むアセンブリを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-114">You can navigate to existing configuration files directly or you can select an assembly that contains a service, virtual directory, or COM+ service.</span></span> <span data-ttu-id="68d1a-115">エディターがその特定のサービスの構成ファイルを読み込むと、ユーザーは新しい要素を追加したり、構成ファイルの `<system.serviceModel>` セクションで入れ子になっている既存の要素を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-115">The editor loads the configuration file for that particular service and allows the user to either add new elements or edit existing elements nested in the `<system.serviceModel>` section of the configuration file.</span></span>

<span data-ttu-id="68d1a-116">エディターは、IntelliSense をサポートし、スキーマ準拠を強制します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-116">The editor supports IntelliSense and enforces schema compliance.</span></span> <span data-ttu-id="68d1a-117">結果として得られる出力は、構成ファイルのスキーマに準拠し、構文的に正しいデータ値を持つことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-117">The resulting output is guaranteed to comply with the schema of the configuration file and to have syntactically correct data values.</span></span> <span data-ttu-id="68d1a-118">ただし、エディターは構成ファイルのセマンティクスが有効であることは保証しません。</span><span class="sxs-lookup"><span data-stu-id="68d1a-118">However, the editor does not guarantee that the configuration file is semantically valid.</span></span> <span data-ttu-id="68d1a-119">つまり、エディターは構成ファイルが関連するサービスで有効に機能することは保証しません。</span><span class="sxs-lookup"><span data-stu-id="68d1a-119">In other words, the editor does not guarantee that the configuration file can work with the service it configures.</span></span>

> [!CAUTION]
> <span data-ttu-id="68d1a-120">要素を変更すると、エディターは構成ファイルからその構成要素を削除できません。</span><span class="sxs-lookup"><span data-stu-id="68d1a-120">The editor cannot purge a configuration element from the configuration file once you have modified the element.</span></span> <span data-ttu-id="68d1a-121">たとえば、エディターを使用してエンドポイント名を空でない文字列に設定して保存すると、構成ファイルは次の内容になります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-121">For example, if you use the editor to set the endpoint name to a non-empty string and save it, the configuration file has the following content, as shown in the following example.</span></span>
>
> `<endpoint binding="basicHttpBinding" name="somename" />`
>
> <span data-ttu-id="68d1a-122">そのエンドポイント名を削除するために名前を空の文字列に設定して保存しようとしても、構成ファイルには、`name` 属性が残ります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-122">If you attempt to remove the name by setting it to an empty string and save the file, the configuration file still contains the `name` attribute, as shown in the following example.</span></span>
>
> `<endpoint binding="basicHttpBinding" name="" />`
>
> <span data-ttu-id="68d1a-123">属性を削除するには、別のテキスト エディターを使用して要素を手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-123">To purge the attribute, you must manually edit the element using another text editor.</span></span>
>
> <span data-ttu-id="68d1a-124">特に、`issueToken` エンドポイント動作の `clientCredential` 要素を使用する場合は、この問題に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-124">You should be especially careful with this issue when you use the `issueToken` element of the `clientCredential` Endpoint behavior.</span></span> <span data-ttu-id="68d1a-125">具体的には、`address` サブ要素の `localIssuer` 属性を空の文字列にしないようにします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-125">Specifically, the `address` attribute of its `localIssuer` sub-element must not be an empty string.</span></span> <span data-ttu-id="68d1a-126">構成エディターを使用して既に `address` 属性を変更している場合にその属性を完全に削除したい場合は、構成エディター以外のツールを使用して削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-126">If you have modified the `address` attribute using the Configuration Editor and want to remove it completely, you should do so using a tool other than the Editor.</span></span> <span data-ttu-id="68d1a-127">そうでない場合、属性は空の文字列を含むことになるため、アプリケーションは例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-127">Otherwise, the attribute contains an empty string and your application throws an exception.</span></span>

## <a name="using-the-configuration-editor"></a><span data-ttu-id="68d1a-128">構成エディターの使用</span><span class="sxs-lookup"><span data-stu-id="68d1a-128">Using the Configuration Editor</span></span>

<span data-ttu-id="68d1a-129">サービス構成エディターは、次の Windows SDK のインストール場所にあります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-129">The Service Configuration Editor can be found at the following Windows SDK installation location:</span></span>

<span data-ttu-id="68d1a-130">C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="68d1a-130">C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span></span>

<span data-ttu-id="68d1a-131">サービス構成エディターを起動した後、[ファイル] メニューから [**開く**] メニューを使用して、管理するサービスまたはアセンブリを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-131">After you launch the Service Configuration Editor, you can use the **File/Open** menu to browse for the service or assembly you want to manage.</span></span> <span data-ttu-id="68d1a-132">構成ファイルを直接開き、WCF /COM+ サービスを参照し、Web ホスト サービスの構成ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-132">You can open configuration files directly, browse for WCF /COM+ services, and open configuration files for Web-hosted services.</span></span>

<span data-ttu-id="68d1a-133">サービス構成エディターのユーザー インターフェイスは、次の領域に分割されています。</span><span class="sxs-lookup"><span data-stu-id="68d1a-133">The Service Configuration Editor's user interface is divided into the following areas:</span></span>

- <span data-ttu-id="68d1a-134">ツリー ビュー ペイン: 左側に構成要素をツリー構造で表示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-134">Tree View Pane, which displays configuration elements in a tree structure on the left.</span></span> <span data-ttu-id="68d1a-135">ノードを右クリックと、ツリーで操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-135">You can perform operations in the tree by right-clicking the nodes.</span></span>

- <span data-ttu-id="68d1a-136">タスク ペイン: ウィンドウの左下に現在の要素の一般的なタスクを表示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-136">Task Pane, which displays common tasks for current elements on the lower-left of the window</span></span>

- <span data-ttu-id="68d1a-137">詳細ペイン: ツリー ビューで選択された構成ノードの詳細設定を右側に表示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-137">Detail Pane, which displays detailed settings of the configuration node selected in the Tree View on the right.</span></span>

### <a name="opening-a-configuration-file"></a><span data-ttu-id="68d1a-138">構成ファイルを開く</span><span class="sxs-lookup"><span data-stu-id="68d1a-138">Opening a Configuration File</span></span>

1. <span data-ttu-id="68d1a-139">コマンドウィンドウを使用してサービス構成エディターを起動し、WCF のインストール場所に移動して、「」と入力し `SvcConfigEditor.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-139">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>

2. <span data-ttu-id="68d1a-140">[**ファイル**] メニューの [**開く**] を選択し、管理するファイルの種類をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-140">From the **File** menu, select **Open** and click the type of file you want to manage.</span></span>

3. <span data-ttu-id="68d1a-141">[**開く**] ダイアログボックスで、管理する特定のファイルに移動し、ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-141">In the **Open** dialog box, navigate to the specific file you want to manage and double-click it.</span></span>

<span data-ttu-id="68d1a-142">ビューアーは、構成のマージ パスを自動的にたどり、マージされた構成のビューを生成します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-142">The viewer automatically follows the configuration merge path and creates a view of the merged configuration.</span></span> <span data-ttu-id="68d1a-143">たとえば、ホストされていないサービスの実際の構成は、Machine.config と App.config を組み合わせたものです。変更は、Svcconfigeditor.exe 内のアクティブファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-143">For example, the actual configuration of a non-hosted service is a combination of Machine.config and App.config. Any changes are applied to the active file in the SvcConfigEditor.</span></span> <span data-ttu-id="68d1a-144">構成マージ パスの特定ファイルを編集する場合は、直接開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-144">If you want to edit a specific file in the configuration merge path, you should open it directly.</span></span>

> [!NOTE]
> <span data-ttu-id="68d1a-145">構成ファイルが構成エディター以外で変更されている場合、構成エディターは、現在開いている構成ファイルを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-145">Configuration Editor reloads the currently opened configuration file when the latter has been modified outside the Editor.</span></span> <span data-ttu-id="68d1a-146">再読み込みが発生すると、エディター内で永続的に保存されていないすべての変更が失われます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-146">When this happens, all the changes that are not durably saved inside the Editor are lost.</span></span> <span data-ttu-id="68d1a-147">再読み込みが連続して発生する場合は、構成ファイルに定期的にアクセスするサービス (バックグラウンドで実行するウイルス対策ソフトウェアなど) が原因と考えられます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-147">If reloading happens consistently, the most likely cause is a service that constantly accesses the configuration file, for example, an antivirus software running in the background.</span></span> <span data-ttu-id="68d1a-148">この問題を解決するには、ファイルが開いているときに、構成エディターがそのファイルにアクセスできる唯一のプロセスであることを保証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-148">To resolve this, ensure that Configuration Editor is the only process that can access the file when it is opened.</span></span>

### <a name="services"></a><span data-ttu-id="68d1a-149">サービス</span><span class="sxs-lookup"><span data-stu-id="68d1a-149">Services</span></span>

<span data-ttu-id="68d1a-150">[**サービス**ノードには、構成ファイルで現在割り当てられているすべてのサービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-150">The **Services** node displays all of the services currently assigned in the configuration file.</span></span> <span data-ttu-id="68d1a-151">ツリー内の各サブノードは、構成ファイル内の <> 要素のサブ要素に対応し `services` ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-151">Each sub-node in the tree corresponds to a sub-element of the <`services`> element in the configuration file.</span></span>

<span data-ttu-id="68d1a-152">[**サービス**] ノードをクリックすると、**詳細**ペインの [サービスの概要] ページでタスクを表示または実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-152">When you click the **Services** node, you can view or perform tasks on the service Summary Page in the **Detail** Pane.</span></span>

#### <a name="creating-a-new-service-configuration"></a><span data-ttu-id="68d1a-153">新しいサービス構成の作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-153">Creating a new Service Configuration</span></span>

<span data-ttu-id="68d1a-154">新しいサービス構成は次の方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-154">You can create a new service configuration in the following ways:</span></span>

- <span data-ttu-id="68d1a-155">ウィザードの使用: リンクをクリックして**新しいサービスを作成...**</span><span class="sxs-lookup"><span data-stu-id="68d1a-155">Using a Wizard: Click the link **Create a New Service…**</span></span> <span data-ttu-id="68d1a-156">[タスク] ウィンドウまたは [概要] ページで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-156">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="68d1a-157">また、[**ファイル**] メニューの [**新しい項目の追加**] を > ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-157">You can also do so in the **File** menu -> **Add New Item**.</span></span>

- <span data-ttu-id="68d1a-158">手動で作成する: [**サービス**] ノードを右クリックし、[**新しいサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-158">Create manually: You can right-click the **Services** node and choose **New Service**.</span></span>

#### <a name="creating-a-new-service-endpoint-configuration"></a><span data-ttu-id="68d1a-159">新しいサービス エンドポイント構成の作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-159">Creating a new Service Endpoint Configuration</span></span>

<span data-ttu-id="68d1a-160">新しいサービス エンドポイント構成は次の方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-160">You can create a new service endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="68d1a-161">ウィザードを使用して作成する: [**新しいサービスエンドポイントの作成...** ] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-161">Create using a Wizard: click the link **Create a New Service Endpoint…**</span></span> <span data-ttu-id="68d1a-162">[タスク] ウィンドウまたは [概要] ページで、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-162">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="68d1a-163">また、[**ファイル**] メニューの [**新しい項目の追加**] を > ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-163">You can also do so in the **File** menu -> **Add New Item**.</span></span>

- <span data-ttu-id="68d1a-164">手動で作成: サービスを作成したら、[**エンドポイント**] ノードを右クリックし、[**新しいサービスエンドポイント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-164">Create manually: Once you created a Service, you can right-click the **Endpoints** node and choose "**New Service Endpoint**".</span></span>

#### <a name="editing-a-service-configuration"></a><span data-ttu-id="68d1a-165">サービス構成の編集</span><span class="sxs-lookup"><span data-stu-id="68d1a-165">Editing a Service Configuration</span></span>

1. <span data-ttu-id="68d1a-166">**サービス**ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-166">Click a **Service** node.</span></span>

2. <span data-ttu-id="68d1a-167">プロパティ グリッドで設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-167">Edit the settings in the property grids.</span></span>

#### <a name="editing-a-service-endpoint-configuration"></a><span data-ttu-id="68d1a-168">サービス エンドポイント構成の編集</span><span class="sxs-lookup"><span data-stu-id="68d1a-168">Editing a Service Endpoint Configuration</span></span>

1. <span data-ttu-id="68d1a-169">[**サービスエンドポイント**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-169">Click a **Service Endpoint** node.</span></span>

2. <span data-ttu-id="68d1a-170">プロパティ グリッドで設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-170">Edit the settings in the property grids.</span></span>

#### <a name="adding-a-base-address"></a><span data-ttu-id="68d1a-171">ベース アドレスの追加</span><span class="sxs-lookup"><span data-stu-id="68d1a-171">Adding a Base Address</span></span>

1. <span data-ttu-id="68d1a-172">[**ホスト**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-172">Click the **Host** node.</span></span>

2. <span data-ttu-id="68d1a-173">**[OData ソース エディター]**</span><span class="sxs-lookup"><span data-stu-id="68d1a-173">Click the **New…**</span></span> <span data-ttu-id="68d1a-174">[**ベースアドレス**] セクションのボタン</span><span class="sxs-lookup"><span data-stu-id="68d1a-174">button in the **Base Addresses** section.</span></span>

3. <span data-ttu-id="68d1a-175">ダイアログ ボックスにベース アドレスの URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-175">Type in the base address URI in the dialog box.</span></span>

4. <span data-ttu-id="68d1a-176">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-176">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="68d1a-177">このツール内での値を編集することはできません [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) 。</span><span class="sxs-lookup"><span data-stu-id="68d1a-177">You cannot edit the value of [\<baseAddressPrefixFilters>](../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) inside this tool.</span></span> <span data-ttu-id="68d1a-178">この要素を追加または変更するには、テキスト エディターまたは Visual Studio を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-178">To add or modify this element, you should use a text editor or Visual Studio.</span></span>

### <a name="client"></a><span data-ttu-id="68d1a-179">クライアント</span><span class="sxs-lookup"><span data-stu-id="68d1a-179">Client</span></span>

<span data-ttu-id="68d1a-180">**クライアント**ノードには、構成ファイル内のすべてのクライアントエンドポイントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-180">The **Client** node displays all of the client endpoints in the configuration file.</span></span> <span data-ttu-id="68d1a-181">ツリー内のすべてのサブノードは、構成ファイル内の <> 要素のサブ要素に対応し `client` ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-181">Every sub-node in the tree corresponds to a sub-element of the <`client`> element in the configuration file.</span></span>

<span data-ttu-id="68d1a-182">[**クライアント**] ノードをクリックすると、**詳細ウィンドウ**の [クライアントの**概要] ページ**でタスクを表示または実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-182">When you click the **Client** node, you can view or perform tasks on the client **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-client-endpoint-configuration"></a><span data-ttu-id="68d1a-183">新しいクライアント エンドポイント構成の作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-183">Creating a new Client Endpoint Configuration</span></span>

<span data-ttu-id="68d1a-184">新しいクライアント エンドポイント構成は次の方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-184">You can create a new client endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="68d1a-185">ウィザードによる作成: [**新しいクライアントの作成**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-185">Create by Wizard: Click the link **Create a New Client…**</span></span> <span data-ttu-id="68d1a-186">ウィンドウの左下の**作業ウィンドウ**または [**概要] ページ**で、ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-186">on the **Task Pane** on the lower-left of the window, or **Summary Page** to launch the wizard.</span></span> <span data-ttu-id="68d1a-187">また、[**ファイル**] メニューの [**新しい項目の追加**] を > ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-187">You can also do so in the **File** menu -> **Add New Item**.</span></span> <span data-ttu-id="68d1a-188">クライアント構成を生成するサービス構成の場所の指定を求めるプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-188">The wizard prompts you to point to the location of the service configuration, from which the client configuration is generated.</span></span> <span data-ttu-id="68d1a-189">接続するサービス エンドポイントを選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-189">You can then choose the service endpoint to connect to.</span></span>

- <span data-ttu-id="68d1a-190">手動で作成する: [**クライアント**] の下の [**エンドポイント**] ノードを右クリックし、[**新しいクライアントエンドポイント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-190">Create manually: Right-click the **Endpoints** node under **Client**, and choose **New Client Endpoint**.</span></span>

#### <a name="editing-a-client-endpoint-configuration"></a><span data-ttu-id="68d1a-191">クライアント エンドポイント構成の編集</span><span class="sxs-lookup"><span data-stu-id="68d1a-191">Editing a Client Endpoint Configuration</span></span>

1. <span data-ttu-id="68d1a-192">[**クライアントエンドポイント**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-192">Click a **Client Endpoint** node.</span></span>

2. <span data-ttu-id="68d1a-193">プロパティ グリッドで設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-193">Edit the settings in the property grids.</span></span>

### <a name="standard-endpoint"></a><span data-ttu-id="68d1a-194">標準エンドポイント</span><span class="sxs-lookup"><span data-stu-id="68d1a-194">Standard Endpoint</span></span>

<span data-ttu-id="68d1a-195">標準エンドポイントは、既定値に設定されたアドレス、コントラクト、およびバインディングの 1 つ以上の特性を持つ特殊なエンドポイントです。</span><span class="sxs-lookup"><span data-stu-id="68d1a-195">Standard endpoints are specialized endpoints that have one or more aspects of the address, contract and binding set to default values.</span></span>

<span data-ttu-id="68d1a-196">このような構成設定は、**標準エンドポイント**ノードに格納されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-196">Such configuration settings are stored in the **Standard Endpoint** node.</span></span> <span data-ttu-id="68d1a-197">[**標準エンドポイント**] ノードには、構成ファイル内のすべての標準エンドポイント設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-197">The **Standard Endpoint** node displays all of the standard endpoint settings in the configuration file.</span></span> <span data-ttu-id="68d1a-198">ツリー内のすべてのサブノードは、構成ファイル内の要素のサブ要素に対応して `<standardEndpoints>` います。</span><span class="sxs-lookup"><span data-stu-id="68d1a-198">Every sub-node in the tree corresponds to a sub-element in the `<standardEndpoints>` element in the configuration file.</span></span>

<span data-ttu-id="68d1a-199">[**標準エンドポイント**] ノードをクリックすると、**詳細ペイン**の標準エンドポイントの**概要ページ**でタスクを表示または実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-199">When you click the **Standard Endpoint** node, you can view or perform tasks on the standard endpoint **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-standard-endpoint-configuration"></a><span data-ttu-id="68d1a-200">新しい標準エンドポイント構成の作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-200">Creating a New Standard Endpoint Configuration</span></span>

<span data-ttu-id="68d1a-201">新しい標準エンドポイント構成は、次の方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-201">You can create a new standard endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="68d1a-202">[**標準エンドポイント**] ノードを右クリックし、[**新しい標準エンドポイント構成...** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-202">Right-click the **Standard Endpoint** node and select **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="68d1a-203">ダイアログボックスでバインドの種類を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-203">Select the binding type in the dialog box and click **OK**.</span></span>

- <span data-ttu-id="68d1a-204">[**標準エンドポイント**] ノードを選択し、[**新しい標準エンドポイント構成...** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-204">Select the **Standard Endpoint** node and click **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="68d1a-205">ウィンドウの左下にある**作業ウィンドウ**を表示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-205">in the **Task Pane** on the lower-left of the window.</span></span>

<span data-ttu-id="68d1a-206">[**新しい標準エンドポイントの作成**] ダイアログボックスが表示され、登録されているすべての標準エンドポイントの種類が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-206">The **Creating a New Standard Endpoint** dialog box displays and lists all registered standard endpoint types.</span></span>

#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a><span data-ttu-id="68d1a-207">標準エンドポイント構成の表示および編集</span><span class="sxs-lookup"><span data-stu-id="68d1a-207">Viewing and Editing a Standard Endpoint Configuration</span></span>

<span data-ttu-id="68d1a-208">表示および編集する標準エンドポイント構成は、次の方法で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-208">You can open a standard endpoint configuration for viewing and editing in the following ways:</span></span>

- <span data-ttu-id="68d1a-209">[**標準エンドポイント**] ノードをクリックして展開し、それぞれのエンドポイントサブノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-209">Click to expand the **Standard Endpoint** node and click the respective endpoint sub-node.</span></span>

- <span data-ttu-id="68d1a-210">[**標準エンドポイント**] ノードをクリックし、詳細ペインでそれぞれのエンドポイントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-210">Click the **Standard Endpoint** node and click the respective endpoint on the Detail pane.</span></span>

<span data-ttu-id="68d1a-211">エンドポイントの属性を右ペインに表示して、編集できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-211">Attributes for the endpoint are shown in the right pane for editing.</span></span>

#### <a name="deleting-a-standard-endpoint-configuration"></a><span data-ttu-id="68d1a-212">標準エンドポイント構成の削除</span><span class="sxs-lookup"><span data-stu-id="68d1a-212">Deleting a Standard Endpoint Configuration</span></span>

<span data-ttu-id="68d1a-213">標準エンドポイント構成は次の方法で削除できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-213">You can delete a standard endpoint configuration in the following ways:</span></span>

- <span data-ttu-id="68d1a-214">[**標準エンドポイント**] ノードをクリックして展開し、それぞれのエンドポイントサブノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-214">Click to expand the **Standard Endpoint** node and right-click the respective endpoint sub-node.</span></span> <span data-ttu-id="68d1a-215">エンドポイントを削除するには、コンテキストコマンドの [**標準エンドポイント構成の削除**] を使用します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-215">Use the context command **Delete Standard Endpoint Configuration** to delete the endpoint.</span></span>

- <span data-ttu-id="68d1a-216">[**標準エンドポイント**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-216">Click the **Standard Endpoint** node.</span></span> <span data-ttu-id="68d1a-217">**作業**ウィンドウで、[**標準エンドポイント構成の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-217">In the **Task** pane, click **Delete Standard Endpoint Configuration**.</span></span>

<span data-ttu-id="68d1a-218">標準エンドポイントが使用されている場合、削除しようとすると警告メッセージが表示されます。**標準エンドポイントは使用中です。ここで削除する場合は、構成の他の部分 (サービスエンドポイントやクライアントエンドポイントなど) ですべての参照を必ず削除してください。それ以外の場合、構成は無効になり、次回は開くことができません。標準エンドポイントを削除しますか? "**</span><span class="sxs-lookup"><span data-stu-id="68d1a-218">If the standard endpoint is in used, a warning message is displayed when you attempt to delete it: **The standard endpoint is in use. If you delete it now, please be sure to delete all of its references in other parts of the configuration (for example, in the service endpoint or client endpoint). Otherwise, the configuration will be invalid and cannot be opened next time. Are you sure you want to delete the standard endpoint?"**</span></span>

### <a name="binding"></a><span data-ttu-id="68d1a-219">バインド</span><span class="sxs-lookup"><span data-stu-id="68d1a-219">Binding</span></span>

<span data-ttu-id="68d1a-220">バインディング構成は、エンドポイントでバインディングを構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-220">Binding configurations are used to configure bindings on endpoints.</span></span> <span data-ttu-id="68d1a-221">このような構成設定は、**バインド**ノードに格納されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-221">Such configuration settings are stored in the **Binding** node.</span></span> <span data-ttu-id="68d1a-222">エンドポイントはバインド構成を名前で参照し、複数のエンドポイントは単一のバインド構成を参照できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-222">Endpoints reference binding configurations by name and multiple endpoints can reference a single binding configuration.</span></span>

<span data-ttu-id="68d1a-223">[**バインド**] ノードには、構成ファイル内のすべてのバインド設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-223">The **Bindings** node displays all of the binding settings in the configuration file.</span></span> <span data-ttu-id="68d1a-224">ツリー内のすべてのサブノードは、 `bindings` 構成ファイル内の <> 要素のサブ要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-224">Every sub-node in the tree corresponds to a sub-element in the <`bindings`> element in the configuration file.</span></span>

<span data-ttu-id="68d1a-225">[**バインド**] ノードをクリックすると、**詳細ペイン**の [バインドの**概要] ページ**でタスクを表示または実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-225">When you click the **Bindings** node, you can view or perform tasks on the binding **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="creating-a-new-binding-configuration"></a><span data-ttu-id="68d1a-226">新しいバインド構成の作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-226">Creating a New Binding Configuration</span></span>

<span data-ttu-id="68d1a-227">新しいバインド構成は次の方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-227">You can create a new binding configuration in the following ways.</span></span>

- <span data-ttu-id="68d1a-228">[**バインド**] ノードを右クリックし、[**新しいバインド構成**...] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-228">Right-click the **Bindings** node and select **New Binding Configuration**…</span></span> <span data-ttu-id="68d1a-229">ダイアログボックスでバインドの種類を選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-229">Select the binding type in the dialog box and click **OK**.</span></span>

- <span data-ttu-id="68d1a-230">[**バインド**] ノードを選択し、[**新しいバインド構成**...] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-230">Select the **Bindings** node and click **New Binding Configuration**…</span></span> <span data-ttu-id="68d1a-231">ウィンドウの左下にある**作業ウィンドウ**を表示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-231">in the **Task Pane** on the lower-left of the window.</span></span>

- <span data-ttu-id="68d1a-232">サービスまたはクライアントの概要ページで、[**バインドの構成**] フィールドの **[クリックして作成**] をクリックし、対応するエンドポイントのバインド構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-232">In the service or client summary page, click **Click to Create** in the **Binding Configuration** field to create a binding configuration for the corresponding endpoint.</span></span>

#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a><span data-ttu-id="68d1a-233">カスタム バインディングへのバインディング要素拡張の追加</span><span class="sxs-lookup"><span data-stu-id="68d1a-233">Adding Binding Element Extensions to a Custom Binding</span></span>

1. <span data-ttu-id="68d1a-234">拡張要素を追加するバインディングを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-234">Select the binding you want to add an extension element to.</span></span>

2. <span data-ttu-id="68d1a-235">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-235">Click **Add**.</span></span>

3. <span data-ttu-id="68d1a-236">使用できる拡張一覧から、追加するバインド要素拡張を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-236">From the list of available extensions, select the binding element extension you want to add.</span></span> <span data-ttu-id="68d1a-237">複数の項目を選択するには、Ctrl キーを同時に押します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-237">To select multiple items, press the CTRL key simultaneously.</span></span>

4. <span data-ttu-id="68d1a-238">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-238">Click **Add**.</span></span>

#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a><span data-ttu-id="68d1a-239">カスタム バインドの拡張位置の調整</span><span class="sxs-lookup"><span data-stu-id="68d1a-239">Adjusting the Extension Position in a Custom Binding</span></span>

<span data-ttu-id="68d1a-240">カスタム バインドは、スタックを形成するバインド要素のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="68d1a-240">A custom binding is a collection of binding elements that form a stack.</span></span> <span data-ttu-id="68d1a-241">スタックの各バインド要素には、独自の構成設定があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-241">Each binding element on the stack has its own configuration settings.</span></span> <span data-ttu-id="68d1a-242">カスタム バインド内のバインド要素拡張の順序は、スタック内のそれらの位置を示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-242">The order of the binding element extensions in a custom binding indicates their positions in the stack.</span></span> <span data-ttu-id="68d1a-243">スタック最上位の要素が最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-243">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="68d1a-244">順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="68d1a-244">To change the ordering:</span></span>

1. <span data-ttu-id="68d1a-245">カスタム バインディング ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-245">Select the custom binding node.</span></span>

2. <span data-ttu-id="68d1a-246">[**バインド要素拡張の位置**] セクションで、1つのバインド拡張要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-246">Select one binding extension element in the **Binding Element Extension Position** section.</span></span>

3. <span data-ttu-id="68d1a-247">一覧の左側に**ある上矢印または\*\*\*\*下**矢印ボタンを使用して、選択した要素の位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-247">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>

#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a><span data-ttu-id="68d1a-248">カスタム バインドのバインド要素拡張の構成の編集</span><span class="sxs-lookup"><span data-stu-id="68d1a-248">Editing the Configuration of Binding Element Extensions in a Custom Binding</span></span>

1. <span data-ttu-id="68d1a-249">ツリー内のバインディング ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-249">Select the binding node in the tree.</span></span>

2. <span data-ttu-id="68d1a-250">編集する要素を含むカスタム バインディングを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-250">Select the custom binding that contains the element you want to edit.</span></span>

3. <span data-ttu-id="68d1a-251">編集するバインド要素拡張を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-251">Select the binding element extension you want to edit.</span></span> <span data-ttu-id="68d1a-252">要素の設定が、編集場所の右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-252">The settings of the element appear in the right pane, where they can be edited.</span></span>

### <a name="diagnostics"></a><span data-ttu-id="68d1a-253">診断</span><span class="sxs-lookup"><span data-stu-id="68d1a-253">Diagnostics</span></span>

<span data-ttu-id="68d1a-254">[**診断**] ノードには、構成ファイル内のすべての診断設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-254">The **Diagnostics** node displays all of the diagnostic settings in the configuration file.</span></span> <span data-ttu-id="68d1a-255">パフォーマンスカウンターを有効または無効にしたり、Windows Management Instrumentation (WMI) を有効または無効にしたり、WCF トレースを構成したり、WCF メッセージログを構成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-255">It enables you to turn performance counters on or off, enable or disable Windows Management Instrumentation (WMI), configure WCF tracing, and configure WCF message logging.</span></span> <span data-ttu-id="68d1a-256">[**診断**] ノードの設定は、構成ファイルの [<`system.diagnostics`> セクション、およびセクションに対応し `<diagnostics>` `<system.serviceModel>` ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-256">The settings in the **Diagnostics** node correspond to the <`system.diagnostics`> section, and `<diagnostics>` section in `<system.serviceModel>` in the configuration file.</span></span>

<span data-ttu-id="68d1a-257">[**診断**] ノードをクリックすると、**詳細ウィンドウ**の [診断の**概要] ページ**でタスクを表示または実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-257">When you click the **Diagnostics** node, you can view or perform tasks on the diagnostics **Summary Page** in the **Detail Pane**.</span></span>

#### <a name="configuring-performance-counters-and-wmi"></a><span data-ttu-id="68d1a-258">パフォーマンス カウンターと WMI の構成</span><span class="sxs-lookup"><span data-stu-id="68d1a-258">Configuring performance counters and WMI</span></span>

1. <span data-ttu-id="68d1a-259">[**診断**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-259">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="68d1a-260">[**パフォーマンスカウンターの切り替え**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-260">Click **Toggle Performance Counters**.</span></span> <span data-ttu-id="68d1a-261">パフォーマンス カウンターには、Off (既定)、ServiceOnly、All の 3 つの状態があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-261">The performance counter has three states: Off (default), ServiceOnly, and All.</span></span> <span data-ttu-id="68d1a-262">リンクをクリックすると、これらの 3 つの状態の間で設定が切り替わります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-262">Clicking the link toggles the setting among these three states.</span></span>

#### <a name="configuring-wmi-provider"></a><span data-ttu-id="68d1a-263">WMI プロバイダーの構成</span><span class="sxs-lookup"><span data-stu-id="68d1a-263">Configuring WMI Provider</span></span>

1. <span data-ttu-id="68d1a-264">[**診断**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-264">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="68d1a-265">WMI プロバイダーを有効にするには、[ **Wmi プロバイダーを有効**にする] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-265">To enable WMI provider, click the **Enable WMI Provider** link.</span></span>

#### <a name="enabling-wcf-tracing"></a><span data-ttu-id="68d1a-266">WCF トレースの有効化</span><span class="sxs-lookup"><span data-stu-id="68d1a-266">Enabling WCF Tracing</span></span>

<span data-ttu-id="68d1a-267">標準プロパティを持つ WCF トレース ファイルを作成したり、カスタム トレース ファイルを設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-267">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>

1. <span data-ttu-id="68d1a-268">[**診断**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-268">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="68d1a-269">[**トレースを有効にする] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-269">Click **Enable Tracing**.</span></span>

3. <span data-ttu-id="68d1a-270">トレースレベルを調整するには、[**トレースレベル**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-270">Click the **Trace Level** link to adjust the trace level.</span></span> <span data-ttu-id="68d1a-271">トレース レベルは、Off、Critical、Error、Warning、Information、Verbose の 6 つあります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-271">There are six trace levels: Off, Critical, Error, Warning, Information, and Verbose.</span></span> <span data-ttu-id="68d1a-272">[**アクティビティのトレース**] と [**アクティビティの伝達**] オプションを使用すると、WCF アクティビティトレース機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-272">The **Activity Tracing** and **Propagate Activity** option enable you to use the WCF activity tracing feature.</span></span>

4. <span data-ttu-id="68d1a-273">トレース ファイルとオプションを指定するには、トレース リスナー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-273">Click the trace listener name to specify the trace file and options.</span></span>

#### <a name="enabling-wcf-logging"></a><span data-ttu-id="68d1a-274">WCF ログの有効化</span><span class="sxs-lookup"><span data-stu-id="68d1a-274">Enabling WCF Logging</span></span>

<span data-ttu-id="68d1a-275">標準プロパティを持つ WCF トレース ファイルを作成したり、カスタム トレース ファイルを設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-275">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>

1. <span data-ttu-id="68d1a-276">[**診断**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-276">Click the **Diagnostics** node.</span></span>

2. <span data-ttu-id="68d1a-277">[**メッセージログの有効化] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-277">Click **Enable Message Logging**.</span></span>

3. <span data-ttu-id="68d1a-278">ログレベルを調整するには、[**ログレベル**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-278">Click the **Log Level** link to adjust the log level.</span></span> <span data-ttu-id="68d1a-279">ログ レベルには、無効な形式、サービス、トランスポートの 3 つがあります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-279">There are three log levels: Malformed, Service, and Transport.</span></span>

4. <span data-ttu-id="68d1a-280">ログ ファイルとオプションを指定するには、リスナー名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-280">Click the listener name to specify the log file and options.</span></span>

> [!NOTE]
> <span data-ttu-id="68d1a-281">アプリケーションを閉じたときにトレースログとメッセージログを自動的にフラッシュする場合は、[**自動フラッシュ**] オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-281">If you want the trace and message logs to be flushed automatically when your application is closed, enable the **Auto Flush** option.</span></span>

<span data-ttu-id="68d1a-282">[**診断**の**概要] ページ**では、診断の構成で最も一般的なタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-282">The **Diagnostics** **Summary Page** enables you to accomplish the most common tasks in configuring diagnostics.</span></span> <span data-ttu-id="68d1a-283">ただし、リスナーとソースの設定を手動で編集する場合は、[**診断**] ノードを展開し、[**メッセージログ**、**リスナー** 、および**ソース**] ノードで設定を編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-283">However, if you want to manually edit the Listeners and Sources settings, you must expand the **Diagnostics** node and edit settings in **Message Logging**, **Listeners** and **Sources** node.</span></span>

#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a><span data-ttu-id="68d1a-284">WCF カスタム トレースまたはメッセージ ログの有効化</span><span class="sxs-lookup"><span data-stu-id="68d1a-284">Enabling WCF Custom Tracing or Message Logging</span></span>

1. <span data-ttu-id="68d1a-285">[**診断**] ノードをクリックし、展開します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-285">Click the **Diagnostics** node, and expand it.</span></span>

2. <span data-ttu-id="68d1a-286">[**リスナー** ] ノードを右クリックし、[**新しいリスナー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-286">Right-click the **Listeners** node and select **New Listener**.</span></span>

3. <span data-ttu-id="68d1a-287">[ **InitData** ] フィールドにトレースファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-287">Type in the trace file name in the **InitData** field.</span></span> <span data-ttu-id="68d1a-288">[...] をクリックすると、をクリックしてパスを参照します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-288">You can click the "…" button to browse to a path.</span></span>

4. <span data-ttu-id="68d1a-289">[ **TypeName** ] 行をクリックすると、"..." と表示されます。;.</span><span class="sxs-lookup"><span data-stu-id="68d1a-289">Clicking the **TypeName** line displays a "…" button.</span></span> <span data-ttu-id="68d1a-290">このボタンをクリックすると、[**トレースリスナーの種類] ブラウザー**が開きます。このブラウザーを使用すると、既にインストールされている構成済みのトレースリスナーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-290">Click this button to open the **Trace Listener Type Browser**, which you can use to find pre-configured trace listeners that are already installed.</span></span>

5. <span data-ttu-id="68d1a-291">[**ソース**] セクションに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68d1a-291">Note the **Source** section.</span></span> <span data-ttu-id="68d1a-292">このセクションの [**追加**] をクリックして、使用可能なトレースソースを一覧表示するドロップダウンメニューを含むダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-292">Click **Add** in this section to open a dialog box with a drop-down menu, which lists available tracing sources.</span></span> <span data-ttu-id="68d1a-293">トレースソースを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-293">Select a tracing source and click **OK**.</span></span>

6. <span data-ttu-id="68d1a-294">メッセージログの設定を編集するには、[**メッセージログ**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-294">To edit Message Logging settings, click the **Message Logging** node.</span></span> <span data-ttu-id="68d1a-295">プロパティ グリッドで設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-295">You can edit the settings in the property grid.</span></span>

### <a name="advanced"></a><span data-ttu-id="68d1a-296">上級</span><span class="sxs-lookup"><span data-stu-id="68d1a-296">Advanced</span></span>

#### <a name="behaviors"></a><span data-ttu-id="68d1a-297">ビヘイビアー</span><span class="sxs-lookup"><span data-stu-id="68d1a-297">Behaviors</span></span>

<span data-ttu-id="68d1a-298">[**ビヘイビアー**ノードには、構成ファイルで現在定義されている動作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-298">The **Behaviors** node displays the behaviors that are currently defined in the configuration file.</span></span>

<span data-ttu-id="68d1a-299">動作構成は、エンドポイントとサービスの動作を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-299">Behavior configurations are used to configure behaviors of endpoints and services.</span></span> <span data-ttu-id="68d1a-300">このような構成設定は、[サービスの**動作**と**エンドポイントの動作**] の [**詳細設定**] ノードに格納されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-300">Such configuration settings are stored in the **Advanced** node under **Service Behaviors** and **Endpoint Behaviors**.</span></span> <span data-ttu-id="68d1a-301">サービス動作はサービスによって使用され、エンドポイント動作はエンドポイントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-301">Service behaviors are used by services; whereas endpoint behaviors by endpoints.</span></span>

<span data-ttu-id="68d1a-302">動作は、スタックを形成する拡張要素のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="68d1a-302">Behaviors are a collection of extension elements that for a stack.</span></span> <span data-ttu-id="68d1a-303">スタック最上位の要素が最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-303">The element at the top of the stack is applied first.</span></span> <span data-ttu-id="68d1a-304">各拡張要素は独自の構成を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-304">Each extension element can have its own configuration.</span></span>

##### <a name="creating-a-new-behavior-configuration"></a><span data-ttu-id="68d1a-305">新しい動作構成の作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-305">Creating a new Behavior Configuration</span></span>

<span data-ttu-id="68d1a-306">新しい動作構成は次の 2 つの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-306">You can create a new behavior configuration in two ways.</span></span>

- <span data-ttu-id="68d1a-307">動作ノードの1つを右クリックし、[**新しい動作の構成...** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-307">Right-click one of the behavior nodes and select "**New Behavior Configuration…**</span></span>

- <span data-ttu-id="68d1a-308">動作ノードの1つを選択し、[**新しい動作の構成**...] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-308">Select one of the behavior nodes and click the **New Behavior Configuration**…</span></span> <span data-ttu-id="68d1a-309">ウィンドウの左下にある**作業ウィンドウ**を表示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-309">in the **Task Pane** on the lower-left of the window.</span></span>

##### <a name="adding-behavior-element-extensions-to-a-behavior"></a><span data-ttu-id="68d1a-310">動作への動作要素拡張の追加</span><span class="sxs-lookup"><span data-stu-id="68d1a-310">Adding Behavior Element Extensions to a Behavior</span></span>

1. <span data-ttu-id="68d1a-311">動作ノードのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-311">Select one of the behavior nodes.</span></span>

2. <span data-ttu-id="68d1a-312">編集する動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-312">Select the behavior you want edit.</span></span>

3. <span data-ttu-id="68d1a-313">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-313">Click **Add**.</span></span>

4. <span data-ttu-id="68d1a-314">使用できる拡張一覧から、追加する動作要素拡張を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-314">From the list of available extensions, select the behavior element extension you want to add.</span></span>

5. <span data-ttu-id="68d1a-315">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-315">Click **Add**.</span></span>

##### <a name="adjusting-the-extension-position-in-a-behavior"></a><span data-ttu-id="68d1a-316">動作の拡張位置の調整</span><span class="sxs-lookup"><span data-stu-id="68d1a-316">Adjusting the Extension Position in a Behavior</span></span>

<span data-ttu-id="68d1a-317">動作は、スタックを形成する要素のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="68d1a-317">Behaviors are collections of elements that form a stack.</span></span> <span data-ttu-id="68d1a-318">スタックの各要素には、独自の構成があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-318">Each element on the stack has its own configuration.</span></span> <span data-ttu-id="68d1a-319">動作内の動作要素拡張の順序は、スタック内のそれらの位置を示します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-319">The order of the behavior element extensions in a behavior indicates their positions in the stack.</span></span> <span data-ttu-id="68d1a-320">スタック最上位の要素が最初に適用されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-320">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="68d1a-321">順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="68d1a-321">To change the ordering:</span></span>

1. <span data-ttu-id="68d1a-322">動作ノードのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-322">Select one of the behavior nodes.</span></span>

2. <span data-ttu-id="68d1a-323">編集する動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-323">Select the behavior you want edit.</span></span>

3. <span data-ttu-id="68d1a-324">[**動作要素拡張の位置**] セクションで、動作拡張要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-324">Select a behavior extension element in the **Behavior Element Extension Position** section.</span></span>

4. <span data-ttu-id="68d1a-325">一覧の左側に**ある上矢印または\*\*\*\*下**矢印ボタンを使用して、選択した要素の位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-325">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>

##### <a name="editing-the-configuration-of-behavior-element-extensions"></a><span data-ttu-id="68d1a-326">動作要素拡張の構成の編集</span><span class="sxs-lookup"><span data-stu-id="68d1a-326">Editing the Configuration of Behavior Element Extensions</span></span>

1. <span data-ttu-id="68d1a-327">ツリー内の動作ノードの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-327">Select one of the behavior nodes in the tree.</span></span>

2. <span data-ttu-id="68d1a-328">編集する要素を含む動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-328">Select the behavior that contains the element you want to edit.</span></span>

3. <span data-ttu-id="68d1a-329">編集する動作要素拡張を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-329">Select the behavior element extension you want to edit.</span></span> <span data-ttu-id="68d1a-330">要素の設定が、編集場所の右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-330">The settings of the element appear in the right pane where they can be edited.</span></span>

#### <a name="protocolmapping"></a><span data-ttu-id="68d1a-331">ProtocolMapping</span><span class="sxs-lookup"><span data-stu-id="68d1a-331">ProtocolMapping</span></span>

<span data-ttu-id="68d1a-332">このセクションでは、プロトコル アドレス スキームと可能なバインドの間に定義されているマッピングを介して、http、tcp、MSMQ、net.pipe などのさまざまなプロトコルに対する既定のバインドの種類を設定できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-332">This section allows you to set default binding types for different protocols such as http, tcp, MSMQ or net.pipe through defined mapping between protocol address schemes and the possible bindings.</span></span> <span data-ttu-id="68d1a-333">他のプロトコルへの新しいマッピングを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-333">You can also add new mappings to other protocols.</span></span>

#### <a name="extensions"></a><span data-ttu-id="68d1a-334">拡張機能</span><span class="sxs-lookup"><span data-stu-id="68d1a-334">Extensions</span></span>

<span data-ttu-id="68d1a-335">新しいバインディング拡張、バインディング要素拡張、標準エンドポイント拡張、および動作拡張を登録して、WCF 構成で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-335">New binding extensions, binding element extensions, standard endpoint extensions and behavior extensions can be registered for use in WCF configuration.</span></span> <span data-ttu-id="68d1a-336">拡張は、名前と種類のペアです。</span><span class="sxs-lookup"><span data-stu-id="68d1a-336">Extensions are name/type pairs.</span></span> <span data-ttu-id="68d1a-337">名前は構成の拡張の名前を定義し、種類は拡張を実装します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-337">The name defines the name of the extension in configuration, whereas the type implements the extension.</span></span> <span data-ttu-id="68d1a-338">拡張には次の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-338">There are four types of extensions:</span></span>

- <span data-ttu-id="68d1a-339">バインディング拡張は、バインディングの種類全体を定義します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-339">Binding extensions define an entire binding type.</span></span> <span data-ttu-id="68d1a-340">例: `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="68d1a-340">Example: `basicHttpBinding`.</span></span>

- <span data-ttu-id="68d1a-341">バインド要素拡張は、バインディングの要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-341">Binding element extensions define an element of a binding.</span></span> <span data-ttu-id="68d1a-342">例: `textMessageEncoding`.</span><span class="sxs-lookup"><span data-stu-id="68d1a-342">Example: `textMessageEncoding`.</span></span>

- <span data-ttu-id="68d1a-343">標準エンドポイント拡張は、標準エンドポイント全体を定義します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-343">Standard endpoint extensions define an entire standard endpoint.</span></span> <span data-ttu-id="68d1a-344">例: `discoveryEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="68d1a-344">Example: `discoveryEndpoint`.</span></span>

- <span data-ttu-id="68d1a-345">動作要素拡張は、動作の要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-345">Behavior element extensions define an element of a behavior.</span></span> <span data-ttu-id="68d1a-346">例: `clientVia`.</span><span class="sxs-lookup"><span data-stu-id="68d1a-346">Example: `clientVia`.</span></span>

 <span data-ttu-id="68d1a-347">構成に登録されている拡張は、同じ種類の他のすべての WCF コンポーネントと同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-347">Extensions that have been registered in configuration can be used like any other WCF component of the same type.</span></span>

##### <a name="adding-a-new-extension"></a><span data-ttu-id="68d1a-348">新しい機能の追加</span><span class="sxs-lookup"><span data-stu-id="68d1a-348">Adding a new extension</span></span>

<span data-ttu-id="68d1a-349">詳細設定ノード内の拡張ノードの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-349">Select one of the extension nodes in the advanced nodes:</span></span>

1. <span data-ttu-id="68d1a-350">**[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-350">Click **New**.</span></span>

2. <span data-ttu-id="68d1a-351">名前と種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-351">Enter a name and type.</span></span>

3. <span data-ttu-id="68d1a-352">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-352">Click **OK**.</span></span>

4. <span data-ttu-id="68d1a-353">拡張は、エディターの適切な場所に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-353">The extension now appears in the appropriate place in the Editor.</span></span> <span data-ttu-id="68d1a-354">たとえば、動作要素拡張を追加すると、使用できる拡張一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-354">For example, if you add a behavior element extension, it appears in the list of available extensions.</span></span>

#### <a name="hosting-environment"></a><span data-ttu-id="68d1a-355">ホスト環境</span><span class="sxs-lookup"><span data-stu-id="68d1a-355">Hosting Environment</span></span>

<span data-ttu-id="68d1a-356">ここでは、環境をホストするサービスのインスタンス化設定を定義できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-356">This section allows you to define instantiation settings for the service hosting environment.</span></span>

### <a name="creating-a-configuration-file-using-the-wizard"></a><span data-ttu-id="68d1a-357">ウィザードによる構成ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-357">Creating a Configuration File Using the Wizard</span></span>

<span data-ttu-id="68d1a-358">新しい構成ファイルを作成する 1 つの方法として、新しいサービス要素ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-358">One way to create a new configuration file is to use the New Service Element Wizard.</span></span> <span data-ttu-id="68d1a-359">ウィザードは、インストールされているサービスの種類と、WCF と互換性のあるその他の要素 (COM + および Web ホストの仮想ディレクトリを含む) を検索し、それらを読み込んで、構成の作成を大幅に効率化します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-359">The wizard finds the installed service types and other elements compatible with WCF on the computer, including COM+ and Web-hosted virtual directories, and loads them to make creating the configuration much more streamlined.</span></span>

#### <a name="creating-a-configuration-file"></a><span data-ttu-id="68d1a-360">構成ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-360">Creating a Configuration File</span></span>

1. <span data-ttu-id="68d1a-361">コマンドウィンドウを使用してサービス構成エディターを起動し、WCF のインストール場所に移動して、「」と入力し `SvcConfigEditor.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-361">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>

2. <span data-ttu-id="68d1a-362">[**ファイル**] メニューの [**開く**] をクリックし、作成する構成ファイルの種類に応じて [**実行可能**ファイル、 **Com + サービス**、または**web ホステッドサービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-362">From the **File** menu, select **Open** and click **Executable**, **COM+ Service**, or **WebHosted Service**, depending on the type of configuration file you want to create.</span></span>

3. <span data-ttu-id="68d1a-363">[**開く**] ダイアログボックスで、構成ファイルを作成する特定のファイルに移動し、ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-363">In the **Open** dialog box, navigate to the specific file you want to create a configuration file for and double-click it.</span></span>

4. <span data-ttu-id="68d1a-364">[**ファイル**] メニューの [**新しい項目の追加**] をポイントし、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68d1a-364">In the **File** menu, point to **Add New Item** and click **Service**.</span></span> <span data-ttu-id="68d1a-365">新しいサービス要素ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-365">The New Service Element Wizard opens.</span></span>

5. <span data-ttu-id="68d1a-366">ウィザードの手順に従って新しいサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-366">Follow the steps in the wizard to create the new service.</span></span>

> [!NOTE]
> <span data-ttu-id="68d1a-367">ウィザードによって生成される構成ファイルから NetPeerTcpBinding を使用する場合は、手動でバインディング構成要素を追加し、その `mode` 要素の `security` 属性を "None" に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68d1a-367">If you want to use the NetPeerTcpBinding from the configuration file generated by the Wizard, you have to manually add a binding configuration element and modify the `mode` attribute of its `security` element to "None".</span></span>

## <a name="configuring-com"></a><span data-ttu-id="68d1a-368">COM+ の構成</span><span class="sxs-lookup"><span data-stu-id="68d1a-368">Configuring COM+</span></span>

<span data-ttu-id="68d1a-369">サービス構成エディターによって、既存の COM+ アプリケーションに新しい構成ファイルを作成したり、既存の COM+ 構成を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-369">The Service Configuration Editor enables you to create a new configuration file for an existing COM+ application, or edit an existing COM+ configuration.</span></span> <span data-ttu-id="68d1a-370">**COM コントラクト**ノードは、構成ファイルに <> セクションが存在する場合にのみ表示され `comContract` ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-370">The **COM Contract** node is only visible when the <`comContract`> section exists in the configuration file.</span></span>

### <a name="creating-a-new-com-configuration"></a><span data-ttu-id="68d1a-371">新しい COM+ 構成の作成</span><span class="sxs-lookup"><span data-stu-id="68d1a-371">Creating a New COM+ Configuration</span></span>

<span data-ttu-id="68d1a-372">新しい COM+ 構成を作成する前に、COM+ アプリケーションがコンポーネント サービスにインストールされて、グローバル アセンブリ キャッシュ (GAC) に登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-372">Before creating a new COM+ configuration, make sure that your COM+ application is installed in Component Services, and registered in the Global Assembly Cache (GAC).</span></span>

1. <span data-ttu-id="68d1a-373">[**ファイル**] メニューの**Integrate**[  ->  **com + アプリケーション**の統合 > ます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-373">Select **File** menu -> **Integrate** -> **COM+ Application.**</span></span> <span data-ttu-id="68d1a-374">この操作は、現在開いているファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-374">This operation closes the current opened file.</span></span> <span data-ttu-id="68d1a-375">現在のファイルに保存されていないデータがあれば、[保存] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-375">If there is unsaved data in the current file, a Save dialog appears.</span></span> <span data-ttu-id="68d1a-376">次に、 **Com + 統合ウィザード**が起動します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-376">The **COM+ Integration Wizard** is then launched.</span></span>

2. <span data-ttu-id="68d1a-377">最初のページで、ツリーから COM+ アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-377">In the first page, select the COM+ application from the tree.</span></span> <span data-ttu-id="68d1a-378">ツリーで COM+ アプリケーションが見つからない場合は、COM+ アプリケーションがコンポーネント サービスにインストールされて、グローバル アセンブリ キャッシュ (GAC) に登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-378">If you cannot find your COM+ application in the tree, verify that it is installed in the Component Services and registered in the Global Assembly Cache (GAC).</span></span>

3. <span data-ttu-id="68d1a-379">次のページで、WCF サービスとして公開するメソッドを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-379">In the next page, select which method(s) you want to expose as WCF services.</span></span> <span data-ttu-id="68d1a-380">既定では、COM+ アプリケーションでサポートされるすべてのメソッドが表示され、選択されます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-380">All the supported methods in the COM+ application are displayed and selected by default.</span></span>

4. <span data-ttu-id="68d1a-381">ホスト メソッドを選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-381">Choose a hosting method.</span></span>

5. <span data-ttu-id="68d1a-382">ウィザードの手順に従って他の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-382">Configure other settings according to the guides in the wizard.</span></span>

6. <span data-ttu-id="68d1a-383">サービス構成エディターは、バックグラウンドで ComSvcConfig.exe を利用して、構成ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-383">Service Configuration Editor utilizes ComSvcConfig.exe in the background to generate configuration file.</span></span> <span data-ttu-id="68d1a-384">これが完了すると、概要を表示してウィザードを終了できます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-384">After this is completed, you can view a summary and exit the wizard.</span></span> <span data-ttu-id="68d1a-385">構成を直接編集できるように、生成された構成ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-385">The generated configuration file is opened so that you can edit it directly.</span></span>

### <a name="editing-an-existing-com-configuration"></a><span data-ttu-id="68d1a-386">既存の COM+ 構成の編集</span><span class="sxs-lookup"><span data-stu-id="68d1a-386">Editing an Existing COM+ Configuration</span></span>

1. <span data-ttu-id="68d1a-387">[**ファイル**] メニューの**Open**[  ->  **com + サービス**を開く >] を選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-387">Select **File** menu -> **Open** -> **COM+ Service**…</span></span>

2. <span data-ttu-id="68d1a-388">編集する COM+ サービスを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-388">Select the COM+ Service you want to edit from the list.</span></span>

3. <span data-ttu-id="68d1a-389">[ **COM コントラクト**] ノードで構成設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-389">Edit configuration settings in the **COM Contracts** node.</span></span>

    > [!NOTE]
    > <span data-ttu-id="68d1a-390">COM コントラクトを含む構成ファイルを直接開いて編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="68d1a-390">You can also directly open and edit a configuration file that contains COM contracts.</span></span>

## <a name="security"></a><span data-ttu-id="68d1a-391">Security</span><span class="sxs-lookup"><span data-stu-id="68d1a-391">Security</span></span>

<span data-ttu-id="68d1a-392">構成エディターによって生成されるサービス構成ファイルは、セキュリティによる保護が保証されていません。</span><span class="sxs-lookup"><span data-stu-id="68d1a-392">A service configuration file generated by the Configuration Editor is not guaranteed to be secure.</span></span> <span data-ttu-id="68d1a-393">WCF サービスをセキュリティで保護する方法については、[セキュリティ](./feature-details/security.md)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68d1a-393">Please refer to the [Security](./feature-details/security.md) documentation to find out how to secure your WCF services.</span></span>

<span data-ttu-id="68d1a-394">また、構成エディターを使用して読み書きできるのは、有効な WCF 構成要素だけです。</span><span class="sxs-lookup"><span data-stu-id="68d1a-394">In addition, the Configuration Editor can only be used to read and write valid WCF configuration elements.</span></span> <span data-ttu-id="68d1a-395">ツールは、スキーマに準拠するユーザー定義の要素を無視します。</span><span class="sxs-lookup"><span data-stu-id="68d1a-395">The tool ignores schema-compliant, user-defined elements.</span></span> <span data-ttu-id="68d1a-396">また、ツールがこれらの要素を構成ファイルから削除したり、既知の WCF 要素に対する影響を究明したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="68d1a-396">It also does not attempt remove these elements from the configuration file or determine their effects on the known WCF elements.</span></span> <span data-ttu-id="68d1a-397">これらの要素がアプリケーションやシステムに脅威を与えるかどうかを究明するのはユーザーの責任です。</span><span class="sxs-lookup"><span data-stu-id="68d1a-397">It is the user’s responsibility to determine whether these elements pose a threat to the application or the system.</span></span>
