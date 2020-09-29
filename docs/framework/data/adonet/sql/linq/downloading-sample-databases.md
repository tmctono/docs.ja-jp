---
title: ADO.NET コード サンプル用のサンプル SQL Server データベースを入手する
description: ADO.NET のドキュメントのコード サンプルで使用されているサンプル SQL Server データベースと、SQL Server および管理ツールをダウンロードします。
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: f7c0d1eb0089a6bfabc92e1deecf563c3e59cc6a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156057"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="f43b3-103">ADO.NET コード サンプル用のサンプル データベースを入手する</span><span class="sxs-lookup"><span data-stu-id="f43b3-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="f43b3-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のドキュメントに含まれる多数のサンプルとチュートリアルでは、サンプル SQL Server データベースと SQL Server Express が使用されています。</span><span class="sxs-lookup"><span data-stu-id="f43b3-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="f43b3-105">これらの製品は、Microsoft から無料でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="f43b3-106">SQL Server 用の Northwind サンプル データベースを入手する</span><span class="sxs-lookup"><span data-stu-id="f43b3-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="f43b3-107">SQL Server 用の Northwind サンプル データベースを作成して読み込むには、次の GitHub リポジトリからスクリプト `instnwnd.sql` をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f43b3-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="f43b3-108">Microsoft SQL Server 用の Northwind および pubs サンプル データベース</span><span class="sxs-lookup"><span data-stu-id="f43b3-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="f43b3-109">Northwind データベースを使用するには、先に、ダウンロードした `instnwnd.sql` スクリプト ファイルを実行し、[SQL Server Management Studio](#get_ssms) または同様のツールを使用して、SQL Server のインスタンスにデータベースを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43b3-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="f43b3-110">リポジトリにある Readme ファイルの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f43b3-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="f43b3-111">Microsoft Access 用の Northwind データベースを探している場合は、「[Microsoft Access 用の Northwind サンプル データベースを入手する](#northwind_access)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f43b3-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a> <span data-ttu-id="f43b3-112">Microsoft Access 用の Northwind サンプル データベースを入手する</span><span class="sxs-lookup"><span data-stu-id="f43b3-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="f43b3-113">Microsoft Access 用の Northwind サンプル データベースは、Microsoft ダウンロード センターでは入手できません。</span><span class="sxs-lookup"><span data-stu-id="f43b3-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="f43b3-114">Access 内から直接 Northwind をインストールするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f43b3-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="f43b3-115">Access を開きます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-115">Open Access.</span></span>

1. <span data-ttu-id="f43b3-116">**[Search for Online Templates]\(オンライン テンプレートの検索\)** ボックスに「**Northwind**」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f43b3-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="f43b3-117">結果画面で、**Northwind** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f43b3-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="f43b3-118">新しいウィンドウが開き、Northwind データベースの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="f43b3-119">新しいウィンドウで、 **[ファイル名]** テキスト ボックスに、Northwind データベースの自分のコピーのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f43b3-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="f43b3-120">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f43b3-120">Select **Create**.</span></span> <span data-ttu-id="f43b3-121">Access で Northwind データベースがダウンロードされて、ファイルが準備されます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="f43b3-122">この処理が完了すると、データベースのようこそ画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="f43b3-123">SQL Server 用の AdventureWorks サンプル データベースを入手する</span><span class="sxs-lookup"><span data-stu-id="f43b3-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="f43b3-124">次の GitHub リポジトリから SQL Server 用の AdventureWorks サンプル データベースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f43b3-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="f43b3-125">AdventureWorks サンプル データベース</span><span class="sxs-lookup"><span data-stu-id="f43b3-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="f43b3-126">データベース バックアップ (\*.bak) ファイルの 1 つをダウンロードした後、SQL Server Management Studio (SSMS) を使用して、SQL Server のインスタンスにバックアップを復元します。</span><span class="sxs-lookup"><span data-stu-id="f43b3-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="f43b3-127">「[SQL Server Management Studio を入手する](#get_ssms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f43b3-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a> <span data-ttu-id="f43b3-128">SQL Server Management Studio を入手する</span><span class="sxs-lookup"><span data-stu-id="f43b3-128">Get SQL Server Management Studio</span></span>

<span data-ttu-id="f43b3-129">ダウンロードしたデータベースを表示または変更する場合は、SQL Server Management Studio (SSMS) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="f43b3-130">次のページから SSMS をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f43b3-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="f43b3-131">SQL Server Management Studio (SSMS) のダウンロード</span><span class="sxs-lookup"><span data-stu-id="f43b3-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="f43b3-132">Visual Studio 統合開発環境 (IDE) でデータベースを表示して管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="f43b3-133">[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019) で、**SQL Server オブジェクト エクスプローラー**からデータベースに接続するか、**サーバー エクスプローラー**でデータベースへのデータ接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="f43b3-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="f43b3-134">これらのエクスプローラー ペインは、 **[表示]** メニューから開きます。</span><span class="sxs-lookup"><span data-stu-id="f43b3-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a> <span data-ttu-id="f43b3-135">SQL Server Express を入手する</span><span class="sxs-lookup"><span data-stu-id="f43b3-135">Get SQL Server Express</span></span>

<span data-ttu-id="f43b3-136">SQL Server Express は、アプリケーションと共に再頒布できる SQL Server の無料のエントリ レベル エディションです。</span><span class="sxs-lookup"><span data-stu-id="f43b3-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="f43b3-137">次のページから SQL Server Express をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f43b3-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="f43b3-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="f43b3-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="f43b3-139">[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019) を使用している場合は、Visual Studio の無料の Community エディションおよび Professional 以上のエディションに、SQL Server Express LocalDB が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f43b3-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f43b3-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="f43b3-140">See also</span></span>

- [<span data-ttu-id="f43b3-141">はじめに</span><span class="sxs-lookup"><span data-stu-id="f43b3-141">Getting Started</span></span>](getting-started.md)
