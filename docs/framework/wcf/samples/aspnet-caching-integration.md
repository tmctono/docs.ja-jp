---
title: ASP.NET キャッシュ統合
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 23c10e56dba7daec2d1027de92e8252c8fe69055
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716179"
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="f5b80-102">ASP.NET キャッシュ統合</span><span class="sxs-lookup"><span data-stu-id="f5b80-102">ASP.NET Caching Integration</span></span>

<span data-ttu-id="f5b80-103">このサンプルでは、WCF WEB HTTP プログラミング モデルで ASP.NET 出力キャッシュを利用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="f5b80-104">ここでは、ASP.NET 出力キャッシュ統合機能について集中的に説明します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-104">This topic focuses on the ASP.NET output cache integration feature.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="f5b80-105">例</span><span class="sxs-lookup"><span data-stu-id="f5b80-105">Demonstrates</span></span>

<span data-ttu-id="f5b80-106">ASP.NET 出力キャッシュとの統合</span><span class="sxs-lookup"><span data-stu-id="f5b80-106">Integration with the ASP.NET Output Cache</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5b80-107">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5b80-107">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f5b80-108">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5b80-108">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f5b80-109">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459)にアクセスして、すべての WINDOWS COMMUNICATION FOUNDATION (wcf) と [!INCLUDE[wf1](../../../../includes/wf1-md.md)] サンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f5b80-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f5b80-110">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-110">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a><span data-ttu-id="f5b80-111">ディスカッション</span><span class="sxs-lookup"><span data-stu-id="f5b80-111">Discussion</span></span>

<span data-ttu-id="f5b80-112">このサンプルでは、<xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> を使用して、Windows Communication Foundation (WCF) サービスで ASP.NET 出力キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-112">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="f5b80-113"><xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> は、サービス操作に適用される属性で、特定の操作からの応答に適用する構成ファイル内のキャッシュ プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-113">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>

<span data-ttu-id="f5b80-114">サンプルサービスプロジェクトの Service.cs ファイルでは、`GetCustomer` と `GetCustomers` の両方の操作が <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>でマークされます。この場合、キャッシュプロファイル名は "CacheFor60Seconds" になります。</span><span class="sxs-lookup"><span data-stu-id="f5b80-114">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="f5b80-115">サービスプロジェクトの web.config ファイルでは、<`system.web`> の <`caching`> 要素の下にキャッシュプロファイル "CacheFor60Seconds" が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f5b80-115">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="f5b80-116">このキャッシュプロファイルの場合、`duration` 属性の値は "60" であるため、このプロファイルに関連付けられている応答は ASP.NET 出力キャッシュに60秒間キャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-116">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="f5b80-117">また、このキャッシュプロファイルでは、`varmByParam` 属性が "format" に設定されているため、`format` クエリ文字列パラメーターの値が異なる要求の応答が個別にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-117">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="f5b80-118">最後に、キャッシュプロファイルの `varyByHeader` 属性が "Accept" に設定されているため、Accept ヘッダー値が異なる要求の応答は個別にキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-118">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>

<span data-ttu-id="f5b80-119">Client プロジェクトの Program.cs では、<xref:System.Net.HttpWebRequest> を使用してこのようなクライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-119">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="f5b80-120">これは、WCF サービスにアクセスする 1 つの方法にすぎません。</span><span class="sxs-lookup"><span data-stu-id="f5b80-120">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="f5b80-121">また、WCF チャネルファクトリや <xref:System.Net.WebClient>などの他の .NET Framework クラスを使用してサービスにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-121">It is also possible to access the service using other .NET Framework classes like the WCF channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="f5b80-122">SDK のその他のサンプル ([基本的な HTTP サービス](../../../../docs/framework/wcf/samples/basic-http-service.md)サンプルなど) は、これらのクラスを使用して WCF サービスと通信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5b80-122">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample) illustrate how to use these classes to communicate with a WCF service.</span></span>

## <a name="to-run-the-sample"></a><span data-ttu-id="f5b80-123">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="f5b80-123">To run the sample</span></span>

<span data-ttu-id="f5b80-124">このサンプルは、3 つのプロジェクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-124">The sample consists of three projects:</span></span>

- <span data-ttu-id="f5b80-125">**Service**: ASP.NET でホストされる WCF HTTP サービスを含む Web アプリケーションプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="f5b80-125">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>

- <span data-ttu-id="f5b80-126">**Client**: サービスの呼び出しを行うコンソールアプリケーションプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="f5b80-126">**Client**: A console application project that makes calls to the service.</span></span>

- <span data-ttu-id="f5b80-127">**共通**: クライアントおよびサービスによって使用される顧客の種類を含む共有ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="f5b80-127">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>

<span data-ttu-id="f5b80-128">クライアント コンソール アプリケーションが実行されると、クライアントはサービスに要求を発行し、応答からの適切な情報をコンソール ウィンドウに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-128">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>

#### <a name="to-run-the-sample"></a><span data-ttu-id="f5b80-129">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="f5b80-129">To run the sample</span></span>

1. <span data-ttu-id="f5b80-130">ASP.NET キャッシュ統合サンプルのソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-130">Open the solution for the ASP.NET Caching Integration Sample.</span></span>

2. <span data-ttu-id="f5b80-131">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f5b80-131">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="f5b80-132">**ソリューションエクスプローラー**ウィンドウがまだ開いていない場合は、Ctrl + W + S キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-132">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>

4. <span data-ttu-id="f5b80-133">**[ソリューションエクスプローラー]** ウィンドウで、**サービス**プロジェクトを右クリックし、 **[新しいインスタンスを開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-133">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="f5b80-134">これで、サービスをホストする ASP.NET 開発サーバーが起動します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-134">This launches the ASP.NET development server, which hosts the service.</span></span>

5. <span data-ttu-id="f5b80-135">**[ソリューションエクスプローラー]** ウィンドウで、**クライアント**プロジェクトを右クリックし、 **[新しいインスタンスを開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-135">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>

6. <span data-ttu-id="f5b80-136">クライアント コンソール ウィンドウが表示されて、実行中のサービスの URI および実行中のサービスの HTML ヘルプ ページの URI が示されます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-136">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="f5b80-137">ブラウザーでヘルプ ページの URI を入力することで、いつでも HTML ヘルプ ページを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-137">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>

7. <span data-ttu-id="f5b80-138">サンプルが実行されると、クライアントは現在のアクティビティのステータスを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="f5b80-138">As the sample runs, the client writes the status of the current activity.</span></span>

8. <span data-ttu-id="f5b80-139">クライアント コンソール アプリケーションを終了するには、任意のキーを押します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-139">Press any key to terminate the client console application.</span></span>

9. <span data-ttu-id="f5b80-140">サービスのデバッグを停止するには、Shift キーを押しながら F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-140">Press SHIFT+F5 to stop debugging the service.</span></span>

10. <span data-ttu-id="f5b80-141">Windows 通知領域で、ASP.NET development server アイコンを右クリックし、 **[停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f5b80-141">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
