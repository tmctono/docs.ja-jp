---
title: Visual Studio で WCF data service を作成する
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: 72e3b35465968674a20aa48262d3425a2190ff74
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802268"
---
# <a name="create-the-data-service"></a><span data-ttu-id="302db-102">データ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="302db-102">Create the data service</span></span>

<span data-ttu-id="302db-103">このトピックでは、WCF Data Services を使用して、Northwind サンプルデータベースに基づく Open Data Protocol (OData) フィードを公開するサンプルデータサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="302db-103">In this topic, you create a sample data service that uses WCF Data Services to expose an Open Data Protocol (OData) feed that's based on the Northwind sample database.</span></span> <span data-ttu-id="302db-104">この作業に必要な基本手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="302db-104">The task involves the following basic steps:</span></span>

1. <span data-ttu-id="302db-105">ASP.NET Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="302db-105">Create an ASP.NET Web application.</span></span>

2. <span data-ttu-id="302db-106">Entity Data Model ツールを使用して、データ モデルを定義します。</span><span class="sxs-lookup"><span data-stu-id="302db-106">Define the data model by using the Entity Data Model tools.</span></span>

3. <span data-ttu-id="302db-107">データ サービスを Web アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="302db-107">Add the data service to the Web application.</span></span>

4. <span data-ttu-id="302db-108">データ サービスへのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="302db-108">Enable access to the data service.</span></span>

## <a name="create-the-aspnet-web-app"></a><span data-ttu-id="302db-109">ASP.NET web アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="302db-109">Create the ASP.NET web app</span></span>

1. <span data-ttu-id="302db-110">Visual Studio の **[ファイル]** メニューで､ **[新規作成]**  >  **[プロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-110">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

1. <span data-ttu-id="302db-111">**新しいプロジェクト** ダイアログ ボックスで、Visual Basic または Visual C# のいずれかの選択 で、 **Web**カテゴリ、および選択**ASP.NET Web アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="302db-111">In the **New Project** dialog box, under either Visual Basic or Visual C# select the **Web** category, and then select **ASP.NET Web Application**.</span></span>

1. <span data-ttu-id="302db-112">プロジェクトの名前として `NorthwindService` を入力し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-112">Enter `NorthwindService` as the name of the project and then select **OK**.</span></span>

1. <span data-ttu-id="302db-113">**[New ASP.NET Web Application]** ダイアログボックスで **[Empty]** を選択し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-113">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

1. <span data-ttu-id="302db-114">(省略可能) Web アプリケーションに対して特定のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="302db-114">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="302db-115">注: この一連のクイックスタートトピックでは、`12345` ポート番号が使用されています。</span><span class="sxs-lookup"><span data-stu-id="302db-115">Note: the port number `12345` is used in this series of quickstart topics.</span></span>

    1. <span data-ttu-id="302db-116">**ソリューションエクスプローラー**で、先ほど作成した ASP.NET プロジェクトを右クリックし、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-116">In **Solution Explorer**, right-click on the ASP.NET project that you just created, and then choose **Properties**.</span></span>

    2. <span data-ttu-id="302db-117">**[Web]** タブを選択し、特定の **[ポート]** ボックスの値を `12345`に設定します。</span><span class="sxs-lookup"><span data-stu-id="302db-117">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="302db-118">データ モデルを定義する</span><span class="sxs-lookup"><span data-stu-id="302db-118">Define the data model</span></span>

1. <span data-ttu-id="302db-119">**ソリューションエクスプローラー**で、ASP.NET プロジェクトの名前を右クリックし、[ > **新しい項目**の**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="302db-119">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="302db-120">**[新しい項目の追加]** ダイアログボックスで、 **[データ]** カテゴリを選択し、 **[ADO.NET Entity Data Model]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-120">In the **Add New Item** dialog box, select the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="302db-121">データモデルの名前として、「`Northwind.edmx`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="302db-121">For the name of the data model, enter `Northwind.edmx`.</span></span>

4. <span data-ttu-id="302db-122">**Entity Data Model ウィザード**で、 **[データベースから EF Designer]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="302db-122">In the **Entity Data Model Wizard**, select **EF Designer from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="302db-123">次のいずれかの手順を実行して、データモデルをデータベースに接続し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="302db-123">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="302db-124">データベース接続が既に構成されていない場合は、 **[新しい接続]** をクリックして新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="302db-124">If you don't have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="302db-125">詳細については、「 [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="302db-125">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="302db-126">この SQL Server インスタンスには、Northwind サンプル データベースがアタッチされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="302db-126">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="302db-127">\- または</span><span class="sxs-lookup"><span data-stu-id="302db-127">\- or -</span></span>

    - <span data-ttu-id="302db-128">Northwind データベースに接続するようにデータベース接続が既に構成されている場合は、一覧からその接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-128">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="302db-129">ウィザードの最終ページで、データベース内のすべてのテーブルのチェック ボックスをオンにし、ビューおよびストアド プロシージャのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="302db-129">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="302db-130">**[完了]** をクリックして、ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="302db-130">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-wcf-data-service"></a><span data-ttu-id="302db-131">WCF data service の作成</span><span class="sxs-lookup"><span data-stu-id="302db-131">Create the WCF data service</span></span>

1. <span data-ttu-id="302db-132">**ソリューションエクスプローラー**で、ASP.NET プロジェクトを右クリックし、[ > **新しい項目**の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-132">In **Solution Explorer**, right-click on the ASP.NET project, and then choose **Add** > **New Item**.</span></span>

2. <span data-ttu-id="302db-133">**[新しい項目の追加]** ダイアログボックスで、 **Web**カテゴリから**WCF Data Service**項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="302db-133">In the **Add New Item** dialog box, select the **WCF Data Service** item template from the **Web** category.</span></span>

   ![Visual Studio 2015 の WCF Data Service 項目テンプレート](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="302db-135">**WCF Data Service**テンプレートは visual studio 2015 で使用できますが、visual studio 2017 以降では使用できません。</span><span class="sxs-lookup"><span data-stu-id="302db-135">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="302db-136">サービスの名前として、「`Northwind`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="302db-136">For the name of the service, type `Northwind`.</span></span>

     <span data-ttu-id="302db-137">Visual Studio で新しいサービスの XML マークアップおよびコード ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="302db-137">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="302db-138">既定では、コード エディターのウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="302db-138">By default, the code-editor window opens.</span></span> <span data-ttu-id="302db-139">**ソリューションエクスプローラー**では、サービスの名前は、 *svc.cs*または *.svc*という名前になります。</span><span class="sxs-lookup"><span data-stu-id="302db-139">In **Solution Explorer**, the service has the name Northwind with the extension *.svc.cs* or *.svc.vb*.</span></span>

4. <span data-ttu-id="302db-140">データ サービスのコードで、データ サービスを定義するクラスの定義にあるコメント `/* TODO: put your data source class name here */` をデータ モデルのエンティティ コンテナーである型 (この場合は `NorthwindEntities`) で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="302db-140">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="302db-141">クラス定義は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="302db-141">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a><span data-ttu-id="302db-142">データサービスリソースへのアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="302db-142">Enable access to data service resources</span></span>

1. <span data-ttu-id="302db-143">データ サービスのコードで、`InitializeService` 関数のプレースホルダーのコードを次の内容で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="302db-143">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     <span data-ttu-id="302db-144">これにより、承認されたクライアントは、指定したエンティティ セットのリソースに読み取りおよび書き込みアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="302db-144">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="302db-145">ASP.NET アプリケーションにアクセスできるクライアントは、データ サービスによって公開されるリソースにもアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="302db-145">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="302db-146">運用データ サービスで、リソースへの承認されていないアクセスを防止するために、アプリケーション自身もセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="302db-146">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="302db-147">詳細については、「 [Securing WCF Data Services](securing-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="302db-147">For more information, see [Securing WCF Data Services](securing-wcf-data-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="302db-148">次のステップ:</span><span class="sxs-lookup"><span data-stu-id="302db-148">Next steps</span></span>

<span data-ttu-id="302db-149">ここでは、Northwind サンプルデータベースに基づく OData フィードを公開する新しいデータサービスを作成し、ASP.NET Web アプリケーションに対するアクセス許可を持つクライアントに対してフィードへのアクセスを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="302db-149">You have successfully created a new data service that exposes an OData feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the ASP.NET Web application.</span></span> <span data-ttu-id="302db-150">次に、Visual Studio からデータサービスを開始し、Web ブラウザーから HTTP GET 要求を送信して OData フィードにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="302db-150">Next, you'll start the data service from Visual Studio and access the OData feed by submitting HTTP GET requests through a Web browser:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="302db-151">Web ブラウザーからサービスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="302db-151">Access the service from a web browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="302db-152">参照</span><span class="sxs-lookup"><span data-stu-id="302db-152">See also</span></span>

- <span data-ttu-id="302db-153">[ADO.NET Entity Data Model ツール](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="302db-153">[ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
