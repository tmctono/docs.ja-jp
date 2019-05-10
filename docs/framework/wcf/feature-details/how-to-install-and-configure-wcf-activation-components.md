---
title: '方法: WCF アクティブ化コンポーネントをインストールして設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 96607a1c744b928b340fe33c2b57a25a59f306dd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64635268"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="0164d-102">方法: WCF アクティブ化コンポーネントをインストールして設定する</span><span class="sxs-lookup"><span data-stu-id="0164d-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="0164d-103">このトピックでは、Windows プロセス アクティブ化サービス (WAS とも呼ばれます) を設定するために必要な手順を説明に[!INCLUDE[wv](../../../../includes/wv-md.md)]HTTP では通信しないサービスのネットワーク プロトコルの Windows Communication Foundation (WCF) をホストします。</span><span class="sxs-lookup"><span data-stu-id="0164d-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="0164d-104">以降の各セクションで、この構成に関する手順について概説します。</span><span class="sxs-lookup"><span data-stu-id="0164d-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="0164d-105">インストール (またはのインストールの確認)、WCF のアクティブ化コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="0164d-105">Install (or confirm the installation of) the WCF activation components.</span></span>  
  
- <span data-ttu-id="0164d-106">非 HTTP プロトコルをサポートようにする WAS を構成します。</span><span class="sxs-lookup"><span data-stu-id="0164d-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="0164d-107">次の手順では、TCP アクティベーション用に [!INCLUDE[wv](../../../../includes/wv-md.md)] を構成します。</span><span class="sxs-lookup"><span data-stu-id="0164d-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="0164d-108">インストールと構成を参照してください。 後[方法。WAS で WCF サービスをホスト](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)WAS を使用する非 HTTP エンドポイントを公開する WCF サービスを作成する手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="0164d-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="0164d-109">WCF 非 HTTP アクティブ化コンポーネントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="0164d-109">To install the WCF non-HTTP activation components</span></span>  
  
1. <span data-ttu-id="0164d-110">をクリックして、**開始**ボタンをクリックし、をクリックし、\*\*コントロール パネルの \*\*します。</span><span class="sxs-lookup"><span data-stu-id="0164d-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="0164d-111">クリックして**プログラム**、 をクリックし、**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="0164d-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3. <span data-ttu-id="0164d-112">**タスク** メニューのをクリックして**オンまたはオフにする Windows 機能**します。</span><span class="sxs-lookup"><span data-stu-id="0164d-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4. <span data-ttu-id="0164d-113">[!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] ノードを検索し、それを選択して展開します。</span><span class="sxs-lookup"><span data-stu-id="0164d-113">Find the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] node, select and then expand it.</span></span>  
  
5. <span data-ttu-id="0164d-114">選択、 **WCF 非 Http アクティブ化コンポーネント**ボックスし、設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="0164d-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="0164d-115">TCP アクティベーションをサポートするように WAS を構成するには</span><span class="sxs-lookup"><span data-stu-id="0164d-115">To configure the WAS to support TCP activation</span></span>  
  
1. <span data-ttu-id="0164d-116">net.tcp アクティベーションをサポートするには、既定の Web サイトをあらかじめ net.tcp ポートにバインドしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0164d-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="0164d-117">これは、[!INCLUDE[iisver](../../../../includes/iisver-md.md)] 管理ツール セットと共にインストールされる Appcmd.exe を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="0164d-117">You can do this by using Appcmd.exe, which is installed with the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] management toolset.</span></span> <span data-ttu-id="0164d-118">管理者レベルのコマンド プロンプト ウィンドウで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0164d-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0164d-119">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="0164d-119">This command is a single line of text.</span></span> <span data-ttu-id="0164d-120">このコマンドは、net.tcp サイト バインディングを、TCP ポート 808 で任意のホスト名をリッスンする既定の Web サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="0164d-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2. <span data-ttu-id="0164d-121">サイト内のすべてのアプリケーションが同じ net.tcp バインディングを共有しますが、net.tcp サポートの有効化はアプリケーションごとに指定できます。</span><span class="sxs-lookup"><span data-stu-id="0164d-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="0164d-122">アプリケーションで net.tcp を有効にするには、管理者レベルのコマンド プロンプトから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0164d-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0164d-123">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="0164d-123">This command is a single line of text.</span></span> <span data-ttu-id="0164d-124">このコマンドは有効、/\<*WCF アプリケーション*> アプリケーションに両方を使用してアクセスできる`http://localhost/<WCF Application>`と`net.tcp://localhost/<WCF Application>`します。</span><span class="sxs-lookup"><span data-stu-id="0164d-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>
  
     <span data-ttu-id="0164d-125">このサンプル用に追加した net.tcp サイト バインディングを削除します。</span><span class="sxs-lookup"><span data-stu-id="0164d-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="0164d-126">便宜上次の 2 つの手順が、サンプル ディレクトリにある RemoveNetTcpSiteBinding.cmd というバッチ ファイルに実装されています。</span><span class="sxs-lookup"><span data-stu-id="0164d-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1. <span data-ttu-id="0164d-127">管理者レベルのコマンド プロンプト ウィンドウで次のコマンドを実行して、有効なプロトコルの一覧から net.tcp を削除します。</span><span class="sxs-lookup"><span data-stu-id="0164d-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="0164d-128">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="0164d-128">This command is a single line of text.</span></span>  
  
    2. <span data-ttu-id="0164d-129">権限のレベルが高いコマンド プロンプト ウィンドウで次のコマンドを実行して、net.tcp サイト バインディングを削除します。</span><span class="sxs-lookup"><span data-stu-id="0164d-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="0164d-130">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="0164d-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="0164d-131">有効なプロトコルの一覧から net.tcp を削除するには</span><span class="sxs-lookup"><span data-stu-id="0164d-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1. <span data-ttu-id="0164d-132">有効なプロトコルの一覧から net.tcp を削除するには、管理者レベルのコマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0164d-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0164d-133">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="0164d-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="0164d-134">net.tcp サイト バインディングを削除するには</span><span class="sxs-lookup"><span data-stu-id="0164d-134">To remove the net.tcp site binding</span></span>  
  
1. <span data-ttu-id="0164d-135">net.tcp サイト バインディングを削除するには、管理者レベルのコマンド プロンプト ウィンドウで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0164d-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="0164d-136">このコマンドはテキスト 1 行です。</span><span class="sxs-lookup"><span data-stu-id="0164d-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0164d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="0164d-137">See also</span></span>

- [<span data-ttu-id="0164d-138">TCP アクティベーション</span><span class="sxs-lookup"><span data-stu-id="0164d-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="0164d-139">MSMQ アクティベーション</span><span class="sxs-lookup"><span data-stu-id="0164d-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="0164d-140">NamedPipe アクティベーション</span><span class="sxs-lookup"><span data-stu-id="0164d-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="0164d-141">AppFabric のホスティング機能</span><span class="sxs-lookup"><span data-stu-id="0164d-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
