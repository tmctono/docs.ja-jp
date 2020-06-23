---
title: '方法: WCF アクティブ化コンポーネントをインストールして設定する'
description: Windows Vista で Windows プロセスアクティブ化サービス (WAS) をセットアップして、HTTP では通信しない WCF サービスをホストする方法について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 84a0dcc4fed28ebd7a536bdabfcdc389be6072d8
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246884"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="e972c-103">方法: WCF アクティブ化コンポーネントをインストールして設定する</span><span class="sxs-lookup"><span data-stu-id="e972c-103">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="e972c-104">このトピックでは、windows Vista で Windows プロセスアクティブ化サービス (WAS) をセットアップして、HTTP ネットワークプロトコルでは通信しない Windows Communication Foundation (WCF) サービスをホストするために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e972c-104">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="e972c-105">以降の各セクションで、この構成に関する手順について概説します。</span><span class="sxs-lookup"><span data-stu-id="e972c-105">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="e972c-106">WCF アクティブ化コンポーネントをインストール (または、のインストールを確認) します。</span><span class="sxs-lookup"><span data-stu-id="e972c-106">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="e972c-107">非 HTTP プロトコルをサポートようにする WAS を構成します。</span><span class="sxs-lookup"><span data-stu-id="e972c-107">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="e972c-108">次の手順では、TCP ライセンス認証用に Windows Vista を構成します。</span><span class="sxs-lookup"><span data-stu-id="e972c-108">The following procedure configures Windows Vista for TCP activation.</span></span>

<span data-ttu-id="e972c-109">WAS をインストールして構成した後、「 [How to: Host a Wcf service IN was](how-to-host-a-wcf-service-in-was.md) 」を参照して、was を使用する非 HTTP エンドポイントを公開する wcf サービスを作成する手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e972c-109">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="e972c-110">WCF 非 HTTP アクティブ化コンポーネントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="e972c-110">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="e972c-111">**[スタート]** ボタンをクリックし、**[コントロール パネル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e972c-111">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="e972c-112">[**プログラム**] をクリックし、[**プログラムと機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e972c-112">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="e972c-113">[**タスク**] メニューの [ **Windows の機能の有効化または無効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e972c-113">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="e972c-114">WinFX ノードを見つけて、それを選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="e972c-114">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="e972c-115">[ **WCF 非 Http アクティブ化コンポーネント**] チェックボックスをオンにして、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="e972c-115">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="e972c-116">TCP アクティベーションをサポートするように WAS を構成するには</span><span class="sxs-lookup"><span data-stu-id="e972c-116">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="e972c-117">net.tcp アクティベーションをサポートするには、既定の Web サイトをあらかじめ net.tcp ポートにバインドしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e972c-117">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="e972c-118">これを行うには、IIS 7.0 管理ツールセットと共にインストールされる Appcmd.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="e972c-118">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="e972c-119">管理者レベルのコマンド プロンプト ウィンドウで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e972c-119">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="e972c-120">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="e972c-120">This command is a single line of text.</span></span> <span data-ttu-id="e972c-121">このコマンドは、net.tcp サイト バインディングを、TCP ポート 808 で任意のホスト名をリッスンする既定の Web サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e972c-121">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="e972c-122">サイト内のすべてのアプリケーションが同じ net.tcp バインディングを共有しますが、net.tcp サポートの有効化はアプリケーションごとに指定できます。</span><span class="sxs-lookup"><span data-stu-id="e972c-122">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="e972c-123">アプリケーションで net.tcp を有効にするには、管理者レベルのコマンド プロンプトから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e972c-123">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="e972c-124">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="e972c-124">This command is a single line of text.</span></span> <span data-ttu-id="e972c-125">このコマンドは、 \<*WCF Application*> との両方を使用して、/アプリケーションにアクセスできるようにし `http://localhost/<WCF Application>` `net.tcp://localhost/<WCF Application>` ます。</span><span class="sxs-lookup"><span data-stu-id="e972c-125">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="e972c-126">このサンプル用に追加した net.tcp サイト バインディングを削除します。</span><span class="sxs-lookup"><span data-stu-id="e972c-126">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="e972c-127">便宜上次の 2 つの手順が、サンプル ディレクトリにある RemoveNetTcpSiteBinding.cmd というバッチ ファイルに実装されています。</span><span class="sxs-lookup"><span data-stu-id="e972c-127">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="e972c-128">管理者レベルのコマンド プロンプト ウィンドウで次のコマンドを実行して、有効なプロトコルの一覧から net.tcp を削除します。</span><span class="sxs-lookup"><span data-stu-id="e972c-128">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="e972c-129">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="e972c-129">This command is a single line of text.</span></span>

    2. <span data-ttu-id="e972c-130">権限のレベルが高いコマンド プロンプト ウィンドウで次のコマンドを実行して、net.tcp サイト バインディングを削除します。</span><span class="sxs-lookup"><span data-stu-id="e972c-130">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="e972c-131">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="e972c-131">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="e972c-132">有効なプロトコルの一覧から net.tcp を削除するには</span><span class="sxs-lookup"><span data-stu-id="e972c-132">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="e972c-133">有効なプロトコルの一覧から net.tcp を削除するには、管理者レベルのコマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e972c-133">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="e972c-134">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="e972c-134">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="e972c-135">net.tcp サイト バインディングを削除するには</span><span class="sxs-lookup"><span data-stu-id="e972c-135">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="e972c-136">net.tcp サイト バインディングを削除するには、管理者レベルのコマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e972c-136">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="e972c-137">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="e972c-137">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="e972c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="e972c-138">See also</span></span>

- [<span data-ttu-id="e972c-139">TCP アクティベーション</span><span class="sxs-lookup"><span data-stu-id="e972c-139">TCP Activation</span></span>](../samples/tcp-activation.md)
- [<span data-ttu-id="e972c-140">MSMQ アクティベーション</span><span class="sxs-lookup"><span data-stu-id="e972c-140">MSMQ Activation</span></span>](../samples/msmq-activation.md)
- [<span data-ttu-id="e972c-141">NamedPipe アクティベーション</span><span class="sxs-lookup"><span data-stu-id="e972c-141">NamedPipe Activation</span></span>](../samples/namedpipe-activation.md)
- <span data-ttu-id="e972c-142">[AppFabric のホスティング機能](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e972c-142">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
