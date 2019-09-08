---
title: ADO.NET コードサンプルのサンプル SQL Server データベースを取得する
description: ADO.NET のドキュメントのコードサンプルに使用されているサンプル SQL Server データベースと、SQL Server および管理ツールをダウンロードします。
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 60566041ff4f99e96c9aee052dbcc17b5e5da9e5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794032"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="bae84-103">ADO.NET コードサンプルのサンプルデータベースを入手する</span><span class="sxs-lookup"><span data-stu-id="bae84-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="bae84-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]ドキュメントに記載されているいくつかの例とチュートリアルでは、サンプル SQL Server データベースと SQL Server Express を使用します。</span><span class="sxs-lookup"><span data-stu-id="bae84-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="bae84-105">これらの製品は、Microsoft から無料でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bae84-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="bae84-106">SQL Server の Northwind サンプルデータベースを取得する</span><span class="sxs-lookup"><span data-stu-id="bae84-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="bae84-107">次の GitHub `instnwnd.sql`リポジトリからスクリプトをダウンロードして、SQL Server 用の Northwind サンプルデータベースを作成して読み込みます。</span><span class="sxs-lookup"><span data-stu-id="bae84-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="bae84-108">Microsoft SQL Server 用の Northwind および pubs サンプルデータベース</span><span class="sxs-lookup"><span data-stu-id="bae84-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="bae84-109">Northwind データベースを使用するには、ダウンロード`instnwnd.sql`したスクリプトファイルを実行して、 [SQL Server Management Studio](#get_ssms)または同様のツールを使用して SQL Server のインスタンスにデータベースを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bae84-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="bae84-110">リポジトリの Readme ファイルに記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bae84-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="bae84-111">Microsoft Access 用の Northwind データベースをお探しの場合は、「 [Microsoft access 用の northwind サンプルデータベースのインストール](#northwind_access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bae84-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="northwind_access"></a><span data-ttu-id="bae84-112">Microsoft Access 用の Northwind サンプルデータベースを入手する</span><span class="sxs-lookup"><span data-stu-id="bae84-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="bae84-113">Microsoft Access 用の Northwind サンプルデータベースは、Microsoft ダウンロードセンターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="bae84-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="bae84-114">Access 内から直接 Northwind をインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bae84-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="bae84-115">[アクセス] を開きます。</span><span class="sxs-lookup"><span data-stu-id="bae84-115">Open Access.</span></span>

1. <span data-ttu-id="bae84-116">**[オンラインテンプレートの検索]** ボックスに「 **Northwind** 」と入力し、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bae84-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="bae84-117">結果 画面で  **Northwind** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bae84-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="bae84-118">新しいウィンドウが開き、Northwind データベースの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bae84-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="bae84-119">新しいウィンドウで、 **[ファイル名]** テキストボックスに Northwind データベースのコピーのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bae84-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="bae84-120">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bae84-120">Select **Create**.</span></span> <span data-ttu-id="bae84-121">Access は Northwind データベースをダウンロードし、ファイルを準備します。</span><span class="sxs-lookup"><span data-stu-id="bae84-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="bae84-122">この処理が完了すると、データベースが [ようこそ] 画面で開きます。</span><span class="sxs-lookup"><span data-stu-id="bae84-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="bae84-123">SQL Server の AdventureWorks サンプルデータベースを取得する</span><span class="sxs-lookup"><span data-stu-id="bae84-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="bae84-124">次の GitHub リポジトリから SQL Server 用の AdventureWorks サンプルデータベースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bae84-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="bae84-125">AdventureWorks サンプルデータベース</span><span class="sxs-lookup"><span data-stu-id="bae84-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="bae84-126">データベースバックアップ (\*.bak) ファイルの1つをダウンロードした後、SQL Server Management Studio (SSMS) を使用して SQL Server のインスタンスにバックアップを復元します。</span><span class="sxs-lookup"><span data-stu-id="bae84-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="bae84-127">「 [Get SQL Server Management Studio](#get_ssms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bae84-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get_ssms"></a><span data-ttu-id="bae84-128">SQL Server Management Studio の取得</span><span class="sxs-lookup"><span data-stu-id="bae84-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="bae84-129">ダウンロードしたデータベースを表示または変更する場合は、SQL Server Management Studio (SSMS) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bae84-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="bae84-130">次のページから SSMS をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bae84-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="bae84-131">SQL Server Management Studio (SSMS) のダウンロード</span><span class="sxs-lookup"><span data-stu-id="bae84-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms) 

<span data-ttu-id="bae84-132">また、Visual Studio 統合開発環境 (IDE) でデータベースを表示および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="bae84-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="bae84-133">[Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)で、 **SQL Server オブジェクトエクスプローラー**からデータベースに接続するか、**サーバーエクスプローラー**でデータベースへのデータ接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="bae84-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="bae84-134">これらのエクスプローラーウィンドウは、 **[表示]** メニューから開きます。</span><span class="sxs-lookup"><span data-stu-id="bae84-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get_sql"></a><span data-ttu-id="bae84-135">SQL Server Express の取得</span><span class="sxs-lookup"><span data-stu-id="bae84-135">Get SQL Server Express</span></span>

<span data-ttu-id="bae84-136">SQL Server Express は、アプリケーションと共に再頒布できる SQL Server の無料のエントリレベルエディションです。</span><span class="sxs-lookup"><span data-stu-id="bae84-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="bae84-137">次のページから SQL Server Express をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bae84-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="bae84-138">SQL Server Express エディション</span><span class="sxs-lookup"><span data-stu-id="bae84-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="bae84-139">[Visual studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)を使用している場合、SQL Server Express LocalDB は、visual studio の無料の Community edition、および Professional 以上のエディションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bae84-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="bae84-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="bae84-140">See also</span></span>

- [<span data-ttu-id="bae84-141">はじめに</span><span class="sxs-lookup"><span data-stu-id="bae84-141">Getting Started</span></span>](getting-started.md)
