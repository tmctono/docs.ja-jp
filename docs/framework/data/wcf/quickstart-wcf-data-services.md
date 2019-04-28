---
title: クイック スタート (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f20ffcf356aa0493b1e2356746d9ad7b27d9a1aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876201"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="73cee-102">クイック スタート (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="73cee-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="73cee-103">このクイック スタートでは、WCF Data Services に精通することが、[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]一連のトピックをサポートするタスクを[Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="73cee-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="73cee-104">学習内容</span><span class="sxs-lookup"><span data-stu-id="73cee-104">What you'll learn</span></span>

<span data-ttu-id="73cee-105">このクイック スタートでは、最初のタスクでは、Northwind サンプル データベースから OData フィードを公開するデータ サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="73cee-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="73cee-106">後半のトピックでは、OData アクセスは Web ブラウザーを使用してフィードし、も、変更する Windows Presentation Foundation (WPF) クライアント ライブラリを使用して、OData を使用するクライアント アプリケーションがフィードを作成します。</span><span class="sxs-lookup"><span data-stu-id="73cee-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73cee-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="73cee-107">Prerequisites</span></span>

<span data-ttu-id="73cee-108">このクイック スタートを最後まで行うには、次のコンポーネントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73cee-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="73cee-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73cee-109">Visual Studio</span></span>

- <span data-ttu-id="73cee-110">SQL Server のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="73cee-110">An instance of SQL Server.</span></span> <span data-ttu-id="73cee-111">これは、Visual Studio 2015、またはの一部として既定のインストールに含まれている SQL Server Express が含まれています。、**データ ストレージと処理**Visual Studio 2017 のワークロード。</span><span class="sxs-lookup"><span data-stu-id="73cee-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="73cee-112">Northwind サンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="73cee-112">The Northwind sample database.</span></span> <span data-ttu-id="73cee-113">このサンプル データベースをダウンロードするには、ダウンロード ページ「 [SQL Server 用サンプル データベース](https://go.microsoft.com/fwlink/?linkid=24758)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73cee-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="73cee-114">WCF data services クイック スタートのタスク</span><span class="sxs-lookup"><span data-stu-id="73cee-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="73cee-115">データ サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="73cee-115">Create the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 <span data-ttu-id="73cee-116">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] アプリケーションの定義、データ モデルの定義、データ サービスの作成、およびリソースへのアクセスの有効化を行います。</span><span class="sxs-lookup"><span data-stu-id="73cee-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="73cee-117">Web ブラウザーからサービスへのアクセスします。</span><span class="sxs-lookup"><span data-stu-id="73cee-117">Access the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="73cee-118">Visual Studio からサービスを開始し、公開されているフィードに対して Web ブラウザーから HTTP GET 要求を送信してサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="73cee-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="73cee-119">.NET Framework クライアント アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="73cee-119">Create the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="73cee-120">OData フィードの使用、Windows のコントロールにデータをバインド、バインドされたコントロールでデータを変更する WPF アプリを作成し、データ サービスにバックアップを作成、変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="73cee-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="73cee-121">クイック スタートを完了したプロジェクト ファイルは、「 [WCF Data Services ドキュメントのサンプル](https://go.microsoft.com/fwlink/?LinkId=179994) 」ページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="73cee-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="73cee-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="73cee-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="73cee-123">クイック スタートを開始します。</span><span class="sxs-lookup"><span data-stu-id="73cee-123">Start the quickstart</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="73cee-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="73cee-124">See also</span></span>

- [<span data-ttu-id="73cee-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="73cee-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)
