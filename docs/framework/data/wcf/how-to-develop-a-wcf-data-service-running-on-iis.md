---
title: '方法: IIS 上で実行する WCF Data Service を開発する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: 8a1a0c2c55267940463e2c9ab82bb52345269260
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121610"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="22194-102">方法: IIS で実行されている WCF データ サービスを開発する</span><span class="sxs-lookup"><span data-stu-id="22194-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="22194-103">この記事では、WCF データ サービスを使用して、インターネット インフォメーション サービス (IIS) で実行されている ASP.NET Web アプリによってホストされる Northwind サンプル データベースに基づくデータ サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="22194-103">This article shows how to use WCF Data Services to create a data service that's based on the Northwind sample database that's hosted by an ASP.NET Web app running on Internet Information Services (IIS).</span></span> <span data-ttu-id="22194-104">ASP.NET開発サーバーで実行される ASP.NET Web アプリと同じ Northwind データ サービスを作成する方法の例については[、WCF データ サービスのクイック スタート](quickstart-wcf-data-services.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22194-104">For an example of how to create the same Northwind data service as an ASP.NET Web app that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="22194-105">Northwind データ サービスを作成するには、まずローカル コンピューターに Northwind サンプル データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="22194-105">To create the Northwind data service, first install the Northwind sample database on the local computer.</span></span> <span data-ttu-id="22194-106">データベースをインストールするには、ノースウィンドから Transact-SQL スクリプト[を実行し、Microsoft SQL Server のサンプル データベースを pubs](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)します。</span><span class="sxs-lookup"><span data-stu-id="22194-106">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

<span data-ttu-id="22194-107">この記事では、Entity Framework プロバイダーを使用してデータ サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="22194-107">This article shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="22194-108">その他のデータ サービス プロバイダーを利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="22194-108">Other data services providers are available.</span></span> <span data-ttu-id="22194-109">詳細については、「[データ サービス プロバイダ](data-services-providers-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22194-109">For more information, see [Data Services Providers](data-services-providers-wcf-data-services.md).</span></span>

<span data-ttu-id="22194-110">サービスを作成した後に、データ サービス リソースへのアクセスを明示的に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22194-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="22194-111">詳細については、「[方法 : データ サービスへのアクセスを有効にする](how-to-enable-access-to-the-data-service-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22194-111">For more information, see [How to: Enable Access to the Data Service](how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="22194-112">IIS で実行するASP.NET Web アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="22194-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="22194-113">Visual Studio の **[ファイル]** メニューで､ **[新規作成]**  >  **[プロジェクト]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="22194-114">[**新しいプロジェクト**] ダイアログ ボックスで、[**インストール済み**> [**Visual C#** または**Visual Basic**] を選択> **Web**カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="22194-115">**[ASP.NET Web アプリケーション]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-115">Select the **ASP.NET Web Application** template.</span></span>

4. <span data-ttu-id="22194-116">プロジェクト`NorthwindService`の名前として入力します。</span><span class="sxs-lookup"><span data-stu-id="22194-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="22194-117">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-117">Click **OK**.</span></span>

6. <span data-ttu-id="22194-118">[**プロジェクト**] メニューの [**ノースウィンド サービスのプロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="22194-119">**[Web]** タブを選択し、[**ローカル IIS Web サーバーを使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="22194-120">[**仮想ディレクトリの作成**] をクリックし **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="22194-121">管理特権を持つコマンド プロンプトから、次のコマンドを実行します (オペレーティング システムによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="22194-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="22194-122">32 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="22194-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    - <span data-ttu-id="22194-123">64 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="22194-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="22194-124">これにより、コンピューターに Windows Communication Foundation (WCF) が登録されます。</span><span class="sxs-lookup"><span data-stu-id="22194-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="22194-125">管理特権を持つコマンド プロンプトから、次のコマンドを実行します (オペレーティング システムによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="22194-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    - <span data-ttu-id="22194-126">32 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="22194-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    - <span data-ttu-id="22194-127">64 ビット システム: </span><span class="sxs-lookup"><span data-stu-id="22194-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="22194-128">これにより、WCF がコンピューターにインストールされた後、IIS は正常に実行されます。</span><span class="sxs-lookup"><span data-stu-id="22194-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="22194-129">IIS の再起動が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="22194-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="22194-130">ASP.NET アプリケーションが IIS7 で実行されると、次の手順も実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22194-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="22194-131">IIS マネージャーを開き、既定の**Web サイト**の下の PhotoService アプリケーションに移動します。</span><span class="sxs-lookup"><span data-stu-id="22194-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="22194-132">[**機能ビュー**] で、[**認証**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="22194-133">**[認証]** ページで、**[匿名認証]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="22194-134">[**操作**] ウィンドウで [**編集**] をクリックして、匿名ユーザーがサイトに接続するセキュリティ プリンシパルを設定します。</span><span class="sxs-lookup"><span data-stu-id="22194-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="22194-135">[**匿名認証資格情報の編集**] ダイアログ ボックスで、[**アプリケーション プール ID]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="22194-136">ネットワーク サービス アカウントを使用する際、そのアカウントに関連するすべての内部ネットワーク アクセス権を匿名ユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="22194-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="22194-137">SQL Server Management Studio、sqlcmd.exe ユーティリティ、または Visual Studio の Transact-SQL エディターを使用して、Northwind データベースがアタッチされた SQL Server のインスタンスに対して次の Transact-SQL コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="22194-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="22194-138">これにより、IIS の実行に使用される Windows アカウントに対して、SQL Server インスタンスのログインが作成されます。</span><span class="sxs-lookup"><span data-stu-id="22194-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="22194-139">IIS は、これを使用して SQL Server インスタンスに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="22194-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="22194-140">Northwind データベースをアタッチして、次の Transact-SQL コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="22194-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

    ```sql
    USE Northwind
    GO
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];
    GO
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]
    WITH DEFAULT_DATABASE=[Northwind];
    GO
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'
    GO
    ```

    <span data-ttu-id="22194-141">これにより、新しいログインに権限が付与され、IIS は Northwind データベースに対してデータの読み取りおよび書き込みを行うことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="22194-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="22194-142">データ モデルを定義する</span><span class="sxs-lookup"><span data-stu-id="22194-142">Define the data model</span></span>

1. <span data-ttu-id="22194-143">**ソリューション エクスプローラ**で、ASP.NET プロジェクトの名前を右クリックし、[**新しい項目**の**追加** > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="22194-144">[**新しい項目の追加**] ダイアログ ボックス**で、[エンティティ データ モデルADO.NET]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="22194-145">データ モデルの名前として、「 」`Northwind.edmx`と入力します。</span><span class="sxs-lookup"><span data-stu-id="22194-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="22194-146">エンティティ データ モデル ウィザードで、[**データベースから生成**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="22194-147">次のいずれかの手順を実行してデータ モデルをデータベースに接続し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    - <span data-ttu-id="22194-148">データベース接続が構成されていない場合は、[**新しい接続**] をクリックして新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="22194-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="22194-149">詳細については、「 [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22194-149">For more information, see [How to: Create Connections to SQL Server Databases](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)).</span></span> <span data-ttu-id="22194-150">この SQL Server インスタンスには、Northwind サンプル データベースがアタッチされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="22194-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="22194-151">\- または</span><span class="sxs-lookup"><span data-stu-id="22194-151">\- or -</span></span>

    - <span data-ttu-id="22194-152">Northwind データベースに接続するようにデータベース接続が既に構成されている場合は、一覧からその接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="22194-153">ウィザードの最終ページで、データベース内のすべてのテーブルのチェック ボックスをオンにし、ビューおよびストアド プロシージャのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="22194-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="22194-154">**[完了]** をクリックして、ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="22194-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="22194-155">データ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="22194-155">Create the data service</span></span>

1. <span data-ttu-id="22194-156">**ソリューション エクスプローラ**で、ASP.NET プロジェクトの名前を右クリックし、[**新しい項目**の**追加** > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22194-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="22194-157">[**新しい項目の追加**] ダイアログ ボックスで **、[WCF データ サービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22194-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![WCF データ サービス項目テンプレートの Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="22194-159">**WCF データ サービス**テンプレートは、Visual Studio 2015 で使用できますが、Visual Studio 2017 以降では使用できません。</span><span class="sxs-lookup"><span data-stu-id="22194-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

3. <span data-ttu-id="22194-160">サービスの名前として、 を入力`Northwind`します。</span><span class="sxs-lookup"><span data-stu-id="22194-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="22194-161">Visual Studio で新しいサービスの XML マークアップおよびコード ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="22194-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="22194-162">既定では、コード エディターのウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="22194-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="22194-163">**ソリューション エクスプローラー**では、サービスの名前 、Northwind、拡張子 .svc.cs または .svc.vb が含まれています。</span><span class="sxs-lookup"><span data-stu-id="22194-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="22194-164">データ サービスのコードで、データ サービスを定義するクラスの定義にあるコメント `/* TODO: put your data source class name here */` をデータ モデルのエンティティ コンテナーである型 (この場合は `NorthwindEntities`) で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="22194-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="22194-165">クラス定義は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="22194-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="22194-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="22194-166">See also</span></span>

- [<span data-ttu-id="22194-167">サービスとしてのデータの公開</span><span class="sxs-lookup"><span data-stu-id="22194-167">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
