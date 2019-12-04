---
title: '方法: ADO.NET Entity Framework データ ソースを使用してデータ サービスを作成する (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 0aea4c21b5ea34cb0e8d944d37c879e918d6b27e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800593"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="8ca55-102">方法: ADO.NET Entity Framework データ ソースを使用してデータ サービスを作成する (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="8ca55-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="8ca55-103">WCF Data Services は、エンティティデータをデータサービスとして公開します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="8ca55-104">このエンティティデータは、データソースがリレーショナルデータベースの場合に、ADO. NETEntity Framework によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-104">This entity data is provided by the ADO.NETEntity Framework when the data source is a relational database.</span></span> <span data-ttu-id="8ca55-105">このトピックでは、既存のデータベースに基づき、このデータ モデルを使用して新しいデータ サービスを作成する Visual Studio Web アプリケーションで Entity Framework ベースのデータ モデルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-105">This topic shows you how to create an Entity Framework-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="8ca55-106">Entity Framework は、Visual Studio プロジェクトの外部に Entity Framework モデルを生成できるコマンド ライン ツールも提供します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-106">The Entity Framework also provides a command line tool that can generate an Entity Framework model outside of a Visual Studio project.</span></span> <span data-ttu-id="8ca55-107">詳細については、「[方法: edmgen.exe を使用してモデルファイルとマッピングファイルを生成する](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ca55-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="8ca55-108">既存のデータベースに基づく Entity Framework モデルを既存の Web アプリケーションに追加するには</span><span class="sxs-lookup"><span data-stu-id="8ca55-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="8ca55-109">**[プロジェクト]** メニューの [**新しい項目**の**追加** > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="8ca55-110">**[テンプレート]** ペインで **[データ]** カテゴリをクリックし、 **[ADO.NET Entity Data Model]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="8ca55-111">モデル名を入力し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="8ca55-112">Entity Data Model ウィザードの先頭ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-112">The first page of the Entity Data Model Wizard is displayed.</span></span>

4. <span data-ttu-id="8ca55-113">**[モデルのコンテンツの選択]** ダイアログボックスで、 **[データベースから生成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="8ca55-114">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-114">Then click **Next**.</span></span>

5. <span data-ttu-id="8ca55-115">**[新しい接続]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="8ca55-116">**[接続プロパティ]** ダイアログボックスで、サーバー名を入力し、認証方法を選択します。次に、データベース名を入力し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="8ca55-117">**[データ接続の選択]** ダイアログボックスが、データベース接続の設定によって更新されます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="8ca55-118">**[エンティティ接続設定に名前を付けて app.config に保存]** チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="8ca55-119">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-119">Then click **Next**.</span></span>

8. <span data-ttu-id="8ca55-120">**[データベースオブジェクトの選択]** ダイアログボックスで、データサービスに公開する予定のすべてのデータベースオブジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8ca55-121">データ モデルに含まれるオブジェクトは、データ サービスによって自動的には公開されません。</span><span class="sxs-lookup"><span data-stu-id="8ca55-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="8ca55-122">これらのオブジェクトは、サービス自身によって明示的に公開される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ca55-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="8ca55-123">詳細については、「[データサービスの構成](configuring-the-data-service-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ca55-123">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="8ca55-124">**[完了]** をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="8ca55-125">特定のデータベースに基づく既定のデータ モデルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="8ca55-126">Entity Framework では、データ モデルをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-126">The Entity Framework enables to customize the data model.</span></span> <span data-ttu-id="8ca55-127">詳細については、「 [Entity Data Model ツールのタスク](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ca55-127">For more information, see [Entity Data Model Tools Tasks](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="8ca55-128">新しいデータ モデルを使用してデータ サービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="8ca55-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="8ca55-129">データ モデルを表す .edmx ファイルを Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="8ca55-130">**モデルブラウザー**で、モデルを右クリックし、 **[プロパティ]** をクリックして、エンティティコンテナーの名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="8ca55-131">**ソリューションエクスプローラー**で、ASP.NET プロジェクトの名前を右クリックし、[ > **新しい項目**の**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-131">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="8ca55-132">**[新しい項目の追加]** ダイアログボックスで、 **[Web]** カテゴリの **[WCF Data Service]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ca55-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![Visual Studio 2015 の WCF Data Service 項目テンプレート](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="8ca55-134">**WCF Data Service**テンプレートは visual studio 2015 で使用できますが、visual studio 2017 以降では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8ca55-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

5. <span data-ttu-id="8ca55-135">サービスの名前を指定し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="8ca55-136">Visual Studio で新しいサービスの XML マークアップおよびコード ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="8ca55-137">既定では、コード エディターのウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="8ca55-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="8ca55-138">データ サービスのコードで、データ サービスを定義するクラスの定義内のコメント `/* TODO: put your data source class name here */` を <xref:System.Data.Objects.ObjectContext> クラスから継承する型で置き換えます。この型はデータ モデルのエンティティ コンテナー (手順 2 で確認したコンテナー) です。</span><span class="sxs-lookup"><span data-stu-id="8ca55-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="8ca55-139">データ サービスのコードで、承認されたクライアントがデータ サービスによって公開されているエンティティ セットにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ca55-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="8ca55-140">詳細については、「[データサービスの作成](creating-the-data-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ca55-140">For more information, see [Creating the Data Service](creating-the-data-service.md).</span></span>

8. <span data-ttu-id="8ca55-141">Web ブラウザーを使用して Northwind .svc データサービスをテストするには、「 [Web ブラウザーからサービスにアクセス](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8ca55-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ca55-142">参照</span><span class="sxs-lookup"><span data-stu-id="8ca55-142">See also</span></span>

- [<span data-ttu-id="8ca55-143">WCF Data Services の定義</span><span class="sxs-lookup"><span data-stu-id="8ca55-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="8ca55-144">Data Services プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8ca55-144">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="8ca55-145">方法: リフレクション プロバイダーを使用してデータ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="8ca55-145">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="8ca55-146">方法: LINQ to SQL データ ソースを使用してデータ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="8ca55-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
