---
title: Web ブラウザーからサービスへのアクセス (WCF Data Services クイックスタート)
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: d89f84cd3ea4f56bbae34cbefe0c3891df96fa8b
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894338"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="19ed5-102">Web ブラウザーからサービスへのアクセス (WCF Data Services クイックスタート)</span><span class="sxs-lookup"><span data-stu-id="19ed5-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="19ed5-103">これは、WCF Data Services のクイックスタートの2番目のタスクです。</span><span class="sxs-lookup"><span data-stu-id="19ed5-103">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="19ed5-104">このタスクでは、Visual Studio から WCF Data Services を開始し、必要に応じて Web ブラウザーでのフィードの読み取りを無効にします。</span><span class="sxs-lookup"><span data-stu-id="19ed5-104">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="19ed5-105">次に、公開されたリソースに対して Web ブラウザーから HTTP GET 要求を送信することで、サービス定義ドキュメントを取得し、データサービスリソースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="19ed5-105">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="19ed5-106">既定では、Visual Studio によって、コンピューター上の `localhost` URI にポート番号が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-106">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="19ed5-107">このタスクでは、URI の例でポート番号 `12345` を使用しています。</span><span class="sxs-lookup"><span data-stu-id="19ed5-107">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="19ed5-108">Visual Studio プロジェクトで特定のポート番号を設定する方法の詳細について[は、「データサービスの作成](creating-the-data-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19ed5-108">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="19ed5-109">Internet Explorer を使用して既定のサービス ドキュメントを要求するには</span><span class="sxs-lookup"><span data-stu-id="19ed5-109">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="19ed5-110">Internet Explorer で、 **[ツール]** メニューの **[インターネットオプション]** を選択し、 **[コンテンツ]** タブをクリックし、 **[設定]** をクリックして、 **[フィードの表示を有効にする]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="19ed5-110">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="19ed5-111">フィードの読み取りが無効になります。</span><span class="sxs-lookup"><span data-stu-id="19ed5-111">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="19ed5-112">この機能が無効でなければ、Web ブラウザーは、AtomPub エンコードのドキュメントが返されると生の XML データを表示せずに XML フィードとして処理します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-112">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19ed5-113">ブラウザーでフィードを生の XML データとして表示できない場合は、そのままでフィードをページのソース コードとして表示できます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-113">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="19ed5-114">Visual Studio で、 **F5**キーを押してアプリケーションのデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-114">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="19ed5-115">ローカル コンピューターで Web ブラウザーを開きます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-115">Open a Web browser on the local computer.</span></span> <span data-ttu-id="19ed5-116">アドレス バーに次の URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-116">In the address bar, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="19ed5-117">既定のサービス ドキュメントが返されます。このドキュメントには、このデータ サービスによって公開されているエンティティ セットの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19ed5-117">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="19ed5-118">Web ブラウザーからエンティティ セット リソースにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="19ed5-118">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="19ed5-119">Web ブラウザーのアドレス バーに次の URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-119">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="19ed5-120">Northwind サンプル データベース内のすべての顧客のセットが返されます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-120">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="19ed5-121">Web ブラウザーのアドレス バーに次の URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="19ed5-122">特定の顧客 `ALFKI` のエンティティ インスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-122">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="19ed5-123">Web ブラウザーのアドレス バーに次の URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="19ed5-124">顧客と注文の間のリレーションシップがスキャンされ、特定の顧客 `ALFKI` のすべての注文のセットが返されます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-124">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="19ed5-125">Web ブラウザーのアドレス バーに次の URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="19ed5-126">特定の顧客 `ALFKI` に属する注文がフィルターされ、指定した `OrderID` 値に基づいた特定の注文だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-126">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19ed5-127">次の手順</span><span class="sxs-lookup"><span data-stu-id="19ed5-127">Next Steps</span></span>

<span data-ttu-id="19ed5-128">ブラウザーが指定されたリソースに対して HTTP GET 要求を発行して、Web ブラウザーから WCF Data Services に正常にアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="19ed5-128">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="19ed5-129">Web ブラウザーを使用すると、リクエストのアドレス構文を試したり、結果を表示したりすることが簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="19ed5-129">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="19ed5-130">しかし、一般的に、この方法では運用データ サービスにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="19ed5-130">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="19ed5-131">通常、アプリケーションでは、アプリケーション コードまたはスクリプト言語を使用してデータ サービスと対話します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-131">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="19ed5-132">次に、クライアント ライブラリを使用して共通言語ランタイム (CLR) オブジェクトと同様にデータ サービス リソースにアクセスするクライアント アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="19ed5-132">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="19ed5-133">.NET Framework クライアント アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="19ed5-133">Creating the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="19ed5-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="19ed5-134">See also</span></span>

- [<span data-ttu-id="19ed5-135">データ サービス リソースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="19ed5-135">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
