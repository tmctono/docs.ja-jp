---
title: クイック スタート (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: df6806cd77e7ff109d79f7ba61866763de4c7fc1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790367"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="c4b60-102">クイック スタート (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="c4b60-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="c4b60-103">このクイックスタートでは、 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] [はじめに](getting-started-with-wcf-data-services.md)のトピックをサポートする一連のタスクを使用して WCF Data Services とについて理解することができます。</span><span class="sxs-lookup"><span data-stu-id="c4b60-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="c4b60-104">学習する内容</span><span class="sxs-lookup"><span data-stu-id="c4b60-104">What you'll learn</span></span>

<span data-ttu-id="c4b60-105">このクイックスタートの最初のタスクでは、データサービスを作成して、Northwind サンプルデータベースから OData フィードを公開する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c4b60-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="c4b60-106">後のトピックでは、Web ブラウザーを使用して OData フィードにアクセスします。また、クライアントライブラリを使用して OData フィードを使用する Windows Presentation Foundation (WPF) クライアントアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4b60-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c4b60-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="c4b60-107">Prerequisites</span></span>

<span data-ttu-id="c4b60-108">このクイック スタートを最後まで行うには、次のコンポーネントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4b60-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="c4b60-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4b60-109">Visual Studio</span></span>

- <span data-ttu-id="c4b60-110">SQL Server のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="c4b60-110">An instance of SQL Server.</span></span> <span data-ttu-id="c4b60-111">これには、visual Studio 2015 の既定のインストールに含まれる SQL Server Express、または Visual Studio 2017 の**データストレージと処理**ワークロードの一部として含まれるが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4b60-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="c4b60-112">Northwind サンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="c4b60-112">The Northwind sample database.</span></span> <span data-ttu-id="c4b60-113">このサンプル データベースをダウンロードするには、ダウンロード ページ「 [SQL Server 用サンプル データベース](https://go.microsoft.com/fwlink/?linkid=24758)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4b60-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="c4b60-114">WCF data services クイックスタートのタスク</span><span class="sxs-lookup"><span data-stu-id="c4b60-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="c4b60-115">データサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="c4b60-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="c4b60-116">ASP.NET アプリケーションの定義、データ モデルの定義、データ サービスの作成、およびリソースへのアクセスの有効化を行います。</span><span class="sxs-lookup"><span data-stu-id="c4b60-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="c4b60-117">Web ブラウザーからサービスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="c4b60-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="c4b60-118">Visual Studio からサービスを開始し、公開されているフィードに対して Web ブラウザーから HTTP GET 要求を送信してサービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c4b60-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="c4b60-119">.NET Framework クライアントアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="c4b60-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="c4b60-120">OData フィードを使用する WPF アプリを作成し、データを Windows コントロールにバインドして、バインドされたコントロールのデータを変更した後、変更内容をデータサービスに送り返します。</span><span class="sxs-lookup"><span data-stu-id="c4b60-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b60-121">クイック スタートを完了したプロジェクト ファイルは、「 [WCF Data Services ドキュメントのサンプル](https://go.microsoft.com/fwlink/?LinkId=179994) 」ページからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c4b60-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4b60-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="c4b60-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c4b60-123">クイックスタートを開始する</span><span class="sxs-lookup"><span data-stu-id="c4b60-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="c4b60-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4b60-124">See also</span></span>

- [<span data-ttu-id="c4b60-125">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c4b60-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)
