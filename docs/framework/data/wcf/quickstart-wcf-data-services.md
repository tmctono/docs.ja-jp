---
title: クイック スタート (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121224"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="6052a-102">クイック スタート (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="6052a-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="6052a-103">このクイック スタートを使用すると、「[はじめに](getting-started-with-wcf-data-services.md)」のトピックをサポートする一連のタスクを通じて、 WCF データ サービスとオープン データ プロトコル (OData) について理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6052a-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="6052a-104">学習内容</span><span class="sxs-lookup"><span data-stu-id="6052a-104">What you'll learn</span></span>

<span data-ttu-id="6052a-105">このクイック スタートの最初のタスクでは、データ サービスを作成して、Northwind サンプル データベースから OData フィードを公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6052a-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="6052a-106">後のトピックでは、Web ブラウザーを使用して OData フィードにアクセスし、クライアント ライブラリを使用して OData フィードを使用する Windows プレゼンテーション 基盤 (WPF) クライアント アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6052a-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6052a-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="6052a-107">Prerequisites</span></span>

<span data-ttu-id="6052a-108">このクイック スタートを完了するには、次のコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6052a-108">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="6052a-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6052a-109">Visual Studio</span></span>

- <span data-ttu-id="6052a-110">SQL サーバーのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6052a-110">An instance of SQL Server.</span></span> <span data-ttu-id="6052a-111">これには、Visual Studio 2015 の既定のインストールに含まれている SQL Server Express、または Visual Studio 2017 以降の**データストレージと処理**ワークロードの一部として含まれます。</span><span class="sxs-lookup"><span data-stu-id="6052a-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="6052a-112">Northwind サンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="6052a-112">The Northwind sample database.</span></span> <span data-ttu-id="6052a-113">データベースをインストールするには、ノースウィンドから Transact-SQL スクリプト[を実行し、Microsoft SQL Server のサンプル データベースを pubs](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)します。</span><span class="sxs-lookup"><span data-stu-id="6052a-113">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="6052a-114">WCF データ サービスのクイック スタート タスク</span><span class="sxs-lookup"><span data-stu-id="6052a-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="6052a-115">データ サービスの作成</span><span class="sxs-lookup"><span data-stu-id="6052a-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="6052a-116">ASP.NET アプリケーションの定義、データ モデルの定義、データ サービスの作成、およびリソースへのアクセスの有効化を行います。</span><span class="sxs-lookup"><span data-stu-id="6052a-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="6052a-117">Web ブラウザからサービスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="6052a-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="6052a-118">Visual Studio からサービスを開始し、公開されているフィードに対して Web ブラウザーから HTTP GET 要求を送信してサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6052a-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="6052a-119">NET Framework クライアント アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="6052a-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="6052a-120">OData フィードを使用する WPF アプリを作成し、Windows コントロールにデータをバインドし、バインドされたコントロールのデータを変更して、変更をデータ サービスに返送します。</span><span class="sxs-lookup"><span data-stu-id="6052a-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="6052a-121">完成したバージョンのクイック スタートのプロジェクト ファイルは[、GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6052a-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6052a-122">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6052a-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6052a-123">クイック スタートを開始する</span><span class="sxs-lookup"><span data-stu-id="6052a-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="6052a-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="6052a-124">See also</span></span>

- [<span data-ttu-id="6052a-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="6052a-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
