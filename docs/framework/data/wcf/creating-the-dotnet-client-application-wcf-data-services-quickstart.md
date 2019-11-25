---
title: .NET Framework クライアント アプリケーションの作成 (WCF Data Services クイック スタート)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 4beaba24e42b15ebc45ece6e5319a2b14df54ab6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975381"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a><span data-ttu-id="cd2ad-102">.NET Framework クライアント アプリケーションの作成 (WCF Data Services クイック スタート)</span><span class="sxs-lookup"><span data-stu-id="cd2ad-102">Creating the .NET Framework Client Application (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="cd2ad-103">これは、WCF Data Services のクイックスタートの最後のタスクです。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-103">This is the final task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="cd2ad-104">このタスクでは、コンソールアプリケーションをソリューションに追加し、この新しいクライアントアプリケーションに Open Data Protocol (OData) フィードへの参照を追加します。生成されたクライアントデータサービスクラスとクライアントを使用して、クライアントアプリケーションから OData フィードにアクセスします。ライブラリ.</span><span class="sxs-lookup"><span data-stu-id="cd2ad-104">In this task, you will add a console application to the solution, add a reference to the Open Data Protocol (OData) feed into this new client application, and access the OData feed from the client application by using the generated client data service classes and client libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="cd2ad-105">データ フィードへのアクセスには .NET Framework ベースのクライアント アプリケーションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-105">A .NET Framework-based client application is not required to access a data feed.</span></span> <span data-ttu-id="cd2ad-106">データサービスには、OData フィードを使用する任意のアプリケーションコンポーネントからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-106">The data service can be accessed by any application component that consumes an OData feed.</span></span> <span data-ttu-id="cd2ad-107">詳細については、「[クライアントアプリケーションでのデータサービスの使用](using-a-data-service-in-a-client-application-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-107">For more information, see [Using a Data Service in a Client Application](using-a-data-service-in-a-client-application-wcf-data-services.md).</span></span>

## <a name="to-create-the-client-application-by-using-visual-studio"></a><span data-ttu-id="cd2ad-108">Visual Studio を使用してクライアント アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="cd2ad-108">To create the client application by using Visual Studio</span></span>

1. <span data-ttu-id="cd2ad-109">**ソリューションエクスプローラー**で、ソリューションを右クリックし、 **[追加]** をクリックして、 **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-109">In **Solution Explorer**, right-click the solution, click **Add**, and then click **New Project**.</span></span>

2. <span data-ttu-id="cd2ad-110">左側のウィンドウで、**インストールされ**た > [ **C#ビジュアル**または**Visual Basic**] > **[Windows デスクトップ]** の順に選択し、 **[WPF アプリケーション]** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-110">In the left pane, select **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, and then select the **WPF App** template.</span></span>

3. <span data-ttu-id="cd2ad-111">プロジェクト名として `NorthwindClient` を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-111">Enter `NorthwindClient` for the project name, and then click **OK**.</span></span>

4. <span data-ttu-id="cd2ad-112">ファイル MainWindow.xaml を開き、XAML コードを次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-112">Open the file MainWindow.xaml and replace the XAML code with the following code:</span></span>

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a><span data-ttu-id="cd2ad-113">データ サービス参照をプロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="cd2ad-113">To add a data service reference to the project</span></span>

1. <span data-ttu-id="cd2ad-114">**ソリューションエクスプローラー**で、NorthwindClient プロジェクトを右クリックし、[ > **サービス参照**の**追加**] をクリックして、 **[探索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-114">In **Solution Explorer**, right-click the NorthwindClient project, click **Add** > **Service Reference**, and then click **Discover**.</span></span>

     <span data-ttu-id="cd2ad-115">最初のタスクで作成した Northwind データ サービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-115">This displays the Northwind data service that you created in the first task.</span></span>

2. <span data-ttu-id="cd2ad-116">**[名前空間]** テキストボックスに「`Northwind`」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-116">In the **Namespace** text box, type `Northwind`, and then click **OK**.</span></span>

     <span data-ttu-id="cd2ad-117">プロジェクトに新しいコード ファイルが追加されます。このコード ファイルには、データ サービス リソースにアクセスし、オブジェクトとしてデータ サービス リソースと対話するデータ クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-117">This adds a new code file to the project, which contains the data classes that are used to access and interact with data service resources as objects.</span></span> <span data-ttu-id="cd2ad-118">データ クラスは、名前空間 `NorthwindClient.Northwind` で作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-118">The data classes are created in the namespace `NorthwindClient.Northwind`.</span></span>

## <a name="to-access-data-service-data-in-the-wpf-application"></a><span data-ttu-id="cd2ad-119">WPF アプリケーションのデータ サービスにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="cd2ad-119">To access data service data in the WPF application</span></span>

1. <span data-ttu-id="cd2ad-120">**[NorthwindClient]** の下の**ソリューションエクスプローラー**で、プロジェクトを右クリックし、 **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-120">In **Solution Explorer** under **NorthwindClient**, right-click the project and click **Add Reference**.</span></span>

2. <span data-ttu-id="cd2ad-121">**参照の追加** ダイアログボックスで、 **.net** タブをクリックし、system.servicemodel アセンブリを選択して、 **OK** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-121">In the **Add Reference** dialog box, click the **.NET** tab, select the System.Data.Services.Client.dll assembly, and then click **OK**.</span></span>

3. <span data-ttu-id="cd2ad-122">**NorthwindClient**の下の**ソリューションエクスプローラー**で、mainwindow.xaml ファイルのコードページを開き、次の `using` ステートメント (Visual Basic で`Imports`) を追加します。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-122">In **Solution Explorer** under **NorthwindClient**, open the code page for the MainWindow.xaml file, and add the following `using` statement (`Imports` in Visual Basic).</span></span>

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. <span data-ttu-id="cd2ad-123">次のコードを挿入します。このコードは、データ サービスをクエリし、<xref:System.Data.Services.Client.DataServiceCollection%601> に対する結果を `MainWindow` クラスにバインドします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-123">Insert the following code that queries that data service and binds the result to a <xref:System.Data.Services.Client.DataServiceCollection%601> into the `MainWindow` class:</span></span>

    > [!NOTE]
    > <span data-ttu-id="cd2ad-124">ホスト名 `localhost:12345` を Northwind データ サービスのインスタンスをホストするサーバーとポートで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-124">You must replace the host name `localhost:12345` with the server and port that is hosting your instance of the Northwind data service.</span></span>

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. <span data-ttu-id="cd2ad-125">次のコードを挿入します。このコードは、変更内容を `MainWindow` クラスに保存します。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-125">Insert the following code that saves changes into the `MainWindow` class:</span></span>

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a><span data-ttu-id="cd2ad-126">NorthwindClient アプリケーションをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="cd2ad-126">To build and run the NorthwindClient application</span></span>

1. <span data-ttu-id="cd2ad-127">**ソリューションエクスプローラー**で、NorthwindClient プロジェクトを右クリックし、 **[スタートアッププロジェクトに設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-127">In **Solution Explorer**, right-click the NorthwindClient project and select **Set as startup project**.</span></span>

2. <span data-ttu-id="cd2ad-128">**F5**キーを押してアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-128">Press **F5** to start the application.</span></span>

     <span data-ttu-id="cd2ad-129">ソリューションがビルドされ、クライアント アプリケーションが起動します。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-129">This builds the solution and starts the client application.</span></span> <span data-ttu-id="cd2ad-130">データがサービスから要求され、コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-130">Data is requested from the service and displayed in the console.</span></span>

3. <span data-ttu-id="cd2ad-131">データグリッドの**Quantity**列の値を編集し、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-131">Edit a value in the **Quantity** column of the data grid, and then click **Save**.</span></span>

     <span data-ttu-id="cd2ad-132">変更内容はデータ サービスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-132">Changes are saved to the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cd2ad-133">このバージョンの NorthwindClient アプリケーションでは、エンティティの追加と削除はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-133">This version of the NorthwindClient application does not support adding and deleting of entities.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cd2ad-134">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cd2ad-134">Next Steps</span></span>

<span data-ttu-id="cd2ad-135">これで、サンプルの Northwind OData フィードにアクセスするクライアントアプリケーションが正常に作成されました。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-135">You have successfully created the client application that accesses the sample Northwind OData feed.</span></span> <span data-ttu-id="cd2ad-136">WCF Data Services クイックスタートも完了しました。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-136">You've also completed the WCF Data Services quickstart!</span></span>

<span data-ttu-id="cd2ad-137">.NET Framework アプリケーションから OData フィードにアクセスする方法の詳細については、「 [WCF Data Services クライアントライブラリ](wcf-data-services-client-library.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd2ad-137">For more information about accessing an OData feed from a .NET Framework application, see [WCF Data Services Client Library](wcf-data-services-client-library.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cd2ad-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd2ad-138">See also</span></span>

- [<span data-ttu-id="cd2ad-139">はじめに</span><span class="sxs-lookup"><span data-stu-id="cd2ad-139">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="cd2ad-140">リソース</span><span class="sxs-lookup"><span data-stu-id="cd2ad-140">Resources</span></span>](wcf-data-services-resources.md)
