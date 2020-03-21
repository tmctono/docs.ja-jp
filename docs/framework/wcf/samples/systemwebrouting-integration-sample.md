---
title: SystemWebRouting 統合サンプル
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 2f12d80085e3ac27dac8ce80b6bb09f69337bfd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143955"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="c7b40-102">SystemWebRouting 統合サンプル</span><span class="sxs-lookup"><span data-stu-id="c7b40-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="c7b40-103">このサンプルでは、<xref:System.Web.Routing> 名前空間のクラスとのホスト層の統合を示します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="c7b40-104"><xref:System.Web.Routing> 名前空間のクラスを使用すると、物理リソースに直接対応しない URL をアプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="c7b40-105">Web ルーティングを使用すると、開発者は HTTP の仮想アドレスを作成し、実際の WCF サービスにマップし直すことができます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="c7b40-106">これは、物理ファイルやリソースを配置せずに WCF サービスをホストする必要がある場合、または .html や .aspx などのファイルがない URL を使用してサービスにアクセスする必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="c7b40-107">このサンプルでは、<xref:System.Web.Routing.RouteTable> クラスを使用して、global.asax で定義された実行中のサービスにマップされる仮想 URI を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span>

> [!NOTE]
> <span data-ttu-id="c7b40-108"><xref:System.Web.Routing> 名前空間のクラスは、HTTP でホストされるサービスに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="c7b40-109">この例では、WCF を使用して、フィードとフィード`movies`の 2`channels`つの RSS フィードを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="c7b40-110">サービスをアクティブ化する URL には、拡張が含まれておらず、`Application_Start`クラスから派生`Global`したクラスのメソッド<xref:System.Web.HttpApplication>に登録されます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7b40-111">このサンプルは、IIS 6.0 が拡張なしの URL をサポートするために別の方法を使用するため、インターネット インフォメーション サービス (IIS) 7.0 以降でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="c7b40-112">このサンプルをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="c7b40-112">To download this sample</span></span>
  
<span data-ttu-id="c7b40-113">このサンプルは、既にコンピュータにインストールされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7b40-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="c7b40-114">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7b40-114">Check for the following (default) directory before continuing.</span></span>  

`<InstallDrive>:\WF_WCF_Samples`  

 <span data-ttu-id="c7b40-115">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c7b40-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c7b40-116">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-116">This sample is located in the following directory.</span></span>  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c7b40-117">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="c7b40-117">To use this sample</span></span>  
  
1. <span data-ttu-id="c7b40-118">を使用して、Web ルーティング統合.sln ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="c7b40-119">ソリューションを実行して Web 開発サーバーを起動するには、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="c7b40-120">サンプルのディレクトリの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="c7b40-121">ファイル拡張子が .svc のファイルがないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7b40-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="c7b40-122">アドレス バーで URL`movies`に追加し、URL を`http://localhost:[port]/movies`読み取って Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="c7b40-123">movies フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="c7b40-124">アドレス バーで URL`channels`に追加し、読み取`http://localhost:[port]/channels`りと Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="c7b40-125">channels フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="c7b40-126">Alt キーを押しながら F4 キーを押して Web ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="c7b40-127">開発サーバーが終了していない場合は、通知領域アイコンを右クリックし、[**停止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="c7b40-128">このサンプルを使用するには (IIS でホストする場合)</span><span class="sxs-lookup"><span data-stu-id="c7b40-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="c7b40-129">を使用して、Web ルーティング統合.sln ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="c7b40-130">Ctrl キーと Shift キーを押しながら B キーを押して、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="c7b40-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="c7b40-131">インターネット インフォメーション サービス (IIS) マネージャーで Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="c7b40-132">IIS マネージャで、[既定の**Web サイト**] を右クリックし、[**アプリケーションの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7b40-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="c7b40-133">**エイリアス**に、 を入力`WebRoutingIntegration`します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="c7b40-134">[**物理パス**] で、プロジェクト内の [サービス] フォルダを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="c7b40-135">[**OK**] を押します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="c7b40-136">Web アプリケーションを右クリックし、[アプリケーションの**管理**] を選択して **[参照]** を選択し、アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="c7b40-137">アドレス バーで URL`movies`に追加し、読み取`http://localhost:[port]/movies`りと Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="c7b40-138">movies フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="c7b40-139">アドレス バーで URL`channels`に追加し、読み取`http://localhost:[port]/channels`りと Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c7b40-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="c7b40-140">channels フィードがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="c7b40-141">Alt キーを押しながら F4 キーを押して Web ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c7b40-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="c7b40-142">このサンプルは、HTTP でホストされたサービスの要求をルーティングするために、<xref:System.Web.Routing> 名前空間のクラスを使用してホスト層を構成できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c7b40-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7b40-143">バージョン 2 に設定されている場合は、既定のアプリケーション プール バージョンを .NET Framework 4 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7b40-143">You must update the default application pool version to .NET Framework 4 if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b40-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7b40-144">See also</span></span>

- <span data-ttu-id="c7b40-145">[AppFabric のホストおよび永続化のサンプル](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c7b40-145">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
