---
title: Visual Studio での WCF data service を作成します。
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: e8d82ff8958af12842366911b6633ea6b2e0efbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765865"
---
# <a name="create-the-data-service"></a><span data-ttu-id="a7a9c-102">データ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="a7a9c-102">Create the data service</span></span>

<span data-ttu-id="a7a9c-103">このトピックでは、公開する WCF Data Services を使用するサンプル データ サービスを作成する、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]フィード、Northwind サンプル データベースに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-103">In this topic, you create a sample data service that uses WCF Data Services to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="a7a9c-104">この作業に必要な基本手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="a7a9c-105">ASP.NET Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="a7a9c-106">Entity Data Model ツールを使用して、データ モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="a7a9c-107">データ サービスを Web アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="a7a9c-108">データ サービスへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="a7a9c-109">ASP.NET web アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="a7a9c-110">Visual Studio での**ファイル**メニューの **新規** > **プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="a7a9c-111">**新しいプロジェクト** ダイアログ ボックスで、Visual Basic または Visual C# のいずれかの選択 で、 **Web**カテゴリ、および選択**ASP.NET Web アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="a7a9c-112">入力`NorthwindService`選択し、プロジェクトの名前として**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="a7a9c-113">**新しい ASP.NET Web アプリケーション**ダイアログ ボックスで、**空**選び**OK**。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="a7a9c-114">(省略可能) Web アプリケーションに対して特定のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="a7a9c-115">注: ポート番号`12345`のクイック スタート トピックには、このシリーズで使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="a7a9c-116">**ソリューション エクスプ ローラー**、先ほど作成した ASP.NET プロジェクトを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="a7a9c-117">選択、 **Web**タブをクリックし、値の設定、**特定のポート**テキスト ボックスに`12345`します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="a7a9c-118">データ モデルを定義する</span><span class="sxs-lookup"><span data-stu-id="a7a9c-118">Define the data model</span></span>

1. <span data-ttu-id="a7a9c-119">**ソリューション エクスプ ローラー**ASP.NET プロジェクトの名前を右クリックし、クリックして**追加** > **新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="a7a9c-120">**新しい項目の追加**ダイアログ ボックスで、**データ**カテゴリ、および選択**ADO.NET Entity Data Model**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="a7a9c-121">データ モデルの名前を入力`Northwind.edmx`します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="a7a9c-122">**Entity Data Model ウィザード**を選択します**データベースの EF デザイナー**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="a7a9c-123">次の手順のいずれかの手順を実行して、データ モデルをデータベースに接続し、**次**:</span><span class="sxs-lookup"><span data-stu-id="a7a9c-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="a7a9c-124">既に構成されているデータベース接続を持っていない場合はクリックして**新しい接続**し、新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="a7a9c-125">詳細については、「[方法 :SQL Server データベースへの接続を作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="a7a9c-126">この SQL Server インスタンスには、Northwind サンプル データベースがアタッチされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="a7a9c-127">\- または -</span><span class="sxs-lookup"><span data-stu-id="a7a9c-127">\- or -</span></span>

    - <span data-ttu-id="a7a9c-128">Northwind データベースに接続するようにデータベース接続が既に構成されている場合は、一覧からその接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="a7a9c-129">ウィザードの最終ページで、データベース内のすべてのテーブルのチェック ボックスをオンにし、ビューおよびストアド プロシージャのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="a7a9c-130">クリックして**完了**ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="a7a9c-131">WCF データ サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-131">Create the WCF data service</span></span>

1. <span data-ttu-id="a7a9c-132">**ソリューション エクスプ ローラー**、ASP.NET プロジェクトを右クリックし、選択し、**追加** > **新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="a7a9c-133">**新しい項目の追加**ダイアログ ボックスで、 **WCF Data Service**から項目テンプレート、 **Web**カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Visual Studio 2015 での WCF データ サービス項目テンプレート](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="a7a9c-135">**WCF Data Service**テンプレートは、Visual Studio 2015 ではなく Visual Studio 2017 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="a7a9c-136">サービスの名前を入力`Northwind`します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="a7a9c-137">Visual Studio で新しいサービスの XML マークアップおよびコード ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="a7a9c-138">既定では、コード エディターのウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="a7a9c-139">**ソリューション エクスプ ローラー**、サービスが、拡張子を持つ名前 Northwind *. は.svc.cs*または *..svc.vb になります*します。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="a7a9c-140">データ サービスのコードで、データ サービスを定義するクラスの定義にあるコメント `/* TODO: put your data source class name here */` をデータ モデルのエンティティ コンテナーである型 (この場合は `NorthwindEntities`) で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="a7a9c-141">クラス定義は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="a7a9c-142">データ サービス リソースへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="a7a9c-143">データ サービスのコードで、`InitializeService` 関数のプレースホルダーのコードを次の内容で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="a7a9c-144">これにより、承認されたクライアントは、指定したエンティティ セットのリソースに読み取りおよび書き込みアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a7a9c-145">ASP.NET アプリケーションにアクセスできるクライアントは、データ サービスによって公開されるリソースにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="a7a9c-146">運用データ サービスで、リソースへの承認されていないアクセスを防止するために、アプリケーション自身もセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="a7a9c-147">詳細については、「 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-147">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a7a9c-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="a7a9c-148">Next steps</span></span>

<span data-ttu-id="a7a9c-149">Northwind サンプル データベースに基づいている OData フィードを公開する新しいデータ サービスが正常に作成しを ASP.NET Web アプリケーションへのアクセス許可を持つクライアントからフィードへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="a7a9c-150">次に、Visual Studio からデータ サービスを開始し、Web ブラウザーから HTTP GET 要求を送信してフィードの OData へのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a7a9c-151">Web ブラウザーからサービスへのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a7a9c-151">Access the service from a web browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="a7a9c-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7a9c-152">See also</span></span>

- <span data-ttu-id="a7a9c-153">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a7a9c-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>