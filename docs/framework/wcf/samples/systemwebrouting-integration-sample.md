---
title: SystemWebRouting 統合サンプル
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: a9f9dc871b92b8cd689234c79b09c98e38a2848d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650998"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="9d6b9-102">SystemWebRouting 統合サンプル</span><span class="sxs-lookup"><span data-stu-id="9d6b9-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="9d6b9-103">このサンプルでは、<xref:System.Web.Routing> 名前空間のクラスとのホスト層の統合を示します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="9d6b9-104"><xref:System.Web.Routing> 名前空間のクラスを使用すると、物理リソースに直接対応しない URL をアプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="9d6b9-105">Web のルーティングを使用すると、開発者は実際の WCF サービスにバックアップし、マップされている HTTP 仮想アドレスの作成ができます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="9d6b9-106">これは、物理ファイルやリソースを配置せずに WCF サービスをホストする必要がある場合、または .html や .aspx などのファイルがない URL を使用してサービスにアクセスする必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="9d6b9-107">このサンプルでは、<xref:System.Web.Routing.RouteTable> クラスを使用して、global.asax で定義された実行中のサービスにマップされる仮想 URI を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
>  <span data-ttu-id="9d6b9-108"><xref:System.Web.Routing> 名前空間のクラスは、HTTP でホストされるサービスに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="9d6b9-109">この例では、WCF を使用して、2 つの RSS フィードを作成します。、`movies`フィードと`channels`フィード。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="9d6b9-110">サービスをアクティブ化する Url は、拡張機能が含まれていないに登録されている、`Application_Start`のメソッド、`Global`から派生したクラス、<xref:System.Web.HttpApplication>クラス。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d6b9-111">このサンプルでは、インターネット インフォメーション サービス (IIS) 7.0 のみは機能し、後で、IIS 6.0 とメソッドを使用して、さまざまな拡張機能のない Url をサポートするため。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="9d6b9-112">このサンプルをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="9d6b9-112">To download this sample</span></span>
  
<span data-ttu-id="9d6b9-113">このサンプルは、コンピューターに既にインストールされてことがあります。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="9d6b9-114">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="9d6b9-115">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9d6b9-116">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="9d6b9-117">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="9d6b9-117">To use this sample</span></span>  
  
1. <span data-ttu-id="9d6b9-118">Visual Studio を使用して、WebRoutingIntegration.sln ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="9d6b9-119">ソリューションを実行して Web 開発サーバーを起動するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="9d6b9-120">サンプルのディレクトリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="9d6b9-121">ファイル拡張子が .svc のファイルがないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="9d6b9-122">アドレス バーに追加`movies`、URL にのでその it 読み取り`http://localhost:[port]/movies`ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="9d6b9-123">movies フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="9d6b9-124">アドレス バーに追加`channels`、URL にこれが読み取り`http://localhost:[port]/channels`ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="9d6b9-125">channels フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="9d6b9-126">Alt キーを押しながら F4 キーを押して Web ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="9d6b9-127">開発サーバーが終了しない場合、通知領域アイコンを右クリックし **停止**します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="9d6b9-128">このサンプルを使用するには (IIS でホストする場合)</span><span class="sxs-lookup"><span data-stu-id="9d6b9-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="9d6b9-129">Visual Studio を使用して、WebRoutingIntegration.sln ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="9d6b9-130">Ctrl キーと Shift キーを押しながら B キーを押して、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="9d6b9-131">インターネット インフォメーション サービス (IIS) マネージャーで Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="9d6b9-132">IIS マネージャーで、右クリックして、**既定の Web サイト**選択**アプリケーションを追加**します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="9d6b9-133">**エイリアス**、入力`WebRoutingIntegration`します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="9d6b9-134">**物理パス**プロジェクト内の Service フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="9d6b9-135">**[OK]** を押します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="9d6b9-136">Web アプリケーションを右クリックしてアプリケーションを起動**アプリケーションの管理**し**参照**します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="9d6b9-137">アドレス バーに追加`movies`、URL にこれが読み取り`http://localhost:[port]/movies`ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="9d6b9-138">movies フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="9d6b9-139">アドレス バーに追加`channels`、URL にこれが読み取り`http://localhost:[port]/channels`ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="9d6b9-140">channels フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="9d6b9-141">Alt キーを押しながら F4 キーを押して Web ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="9d6b9-142">このサンプルは、HTTP でホストされたサービスの要求をルーティングするために、<xref:System.Web.Routing> 名前空間のクラスを使用してホスト層を構成できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d6b9-143">既定のアプリケーション プール バージョンを更新する必要があります[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]バージョン 2 に設定されている場合。</span><span class="sxs-lookup"><span data-stu-id="9d6b9-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6b9-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d6b9-144">See also</span></span>

- [<span data-ttu-id="9d6b9-145">AppFabric のホストおよび永続化のサンプル</span><span class="sxs-lookup"><span data-stu-id="9d6b9-145">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
