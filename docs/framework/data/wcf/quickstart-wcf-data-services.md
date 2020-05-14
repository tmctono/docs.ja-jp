---
title: クイック スタート (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121224"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="7bb67-102">クイック スタート (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="7bb67-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="7bb67-103">このクイックスタートでは、「[はじめに](getting-started-with-wcf-data-services.md)」のトピックをサポートする一連のタスクを通して WCF Data Services と Open Data Protocol (OData) を学習することができます。</span><span class="sxs-lookup"><span data-stu-id="7bb67-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="7bb67-104">学習内容</span><span class="sxs-lookup"><span data-stu-id="7bb67-104">What you'll learn</span></span>

<span data-ttu-id="7bb67-105">このクイックスタートの最初のタスクでは、データ サービスを作成し、Northwind サンプル データベースの OData フィードを公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7bb67-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="7bb67-106">後半のトピックでは、Web ブラウザーを使用して OData フィードにアクセスします。また、クライアント ライブラリを使用して OData フィードを使用する Windows Presentation Foundation (WPF) クライアント アプリケーションも作成します。</span><span class="sxs-lookup"><span data-stu-id="7bb67-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7bb67-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7bb67-107">Prerequisites</span></span>

<span data-ttu-id="7bb67-108">このクイックスタートを最後まで行うには、次のコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7bb67-108">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="7bb67-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7bb67-109">Visual Studio</span></span>

- <span data-ttu-id="7bb67-110">SQL Server のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="7bb67-110">An instance of SQL Server.</span></span> <span data-ttu-id="7bb67-111">これには SQL Server Express が含まれます。これは、Visual Studio 2015 の既定のインストールに含まれているか、または Visual Studio 2017 以降の**データ ストレージおよび処理**ワークロードの一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="7bb67-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="7bb67-112">Northwind サンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="7bb67-112">The Northwind sample database.</span></span> <span data-ttu-id="7bb67-113">データベースをインストールするには、[Microsoft SQL Serverの Northwind および pubs サンプル データベース](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)から Transact-SQL スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="7bb67-113">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="7bb67-114">WCF Data Services クイックスタートのタスク</span><span class="sxs-lookup"><span data-stu-id="7bb67-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="7bb67-115">データ サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="7bb67-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="7bb67-116">ASP.NET アプリケーションの定義、データ モデルの定義、データ サービスの作成、およびリソースへのアクセスの有効化を行います。</span><span class="sxs-lookup"><span data-stu-id="7bb67-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="7bb67-117">Web ブラウザーからサービスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="7bb67-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="7bb67-118">Visual Studio からサービスを開始し、公開されているフィードに対して Web ブラウザーから HTTP GET 要求を送信してサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7bb67-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="7bb67-119">.NET Framework クライアント アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="7bb67-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="7bb67-120">WPF アプリを作成して、OData フィードの使用、Windows コントロールへのデータのバインド、バインドされたコントロールのデータの変更、およびデータ サービスへの変更内容の送信を行います。</span><span class="sxs-lookup"><span data-stu-id="7bb67-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="7bb67-121">クイックスタートの完了バージョンからのプロジェクト ファイルは、[GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)) からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="7bb67-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7bb67-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="7bb67-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7bb67-123">クイックスタートの開始</span><span class="sxs-lookup"><span data-stu-id="7bb67-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="7bb67-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bb67-124">See also</span></span>

- [<span data-ttu-id="7bb67-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7bb67-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
