---
title: ADO.NET コード サンプルのサンプル SQL Server データベースを取得します。
description: ADO.NET のドキュメントのコード サンプルで使用されているサンプル SQL Server データベース、および SQL Server および管理ツールをダウンロードします。
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148388"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a><span data-ttu-id="fbb8e-103">ADO.NETコード サンプルのサンプル データベースを取得する</span><span class="sxs-lookup"><span data-stu-id="fbb8e-103">Get the sample databases for ADO.NET code samples</span></span>

<span data-ttu-id="fbb8e-104">ドキュメントの例とチュートリアルの例の例[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]の例では、サンプルの SQL Server データベースと SQL Server のエクスプレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-104">A number of examples and walkthroughs in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation use sample SQL Server databases and SQL Server Express.</span></span> <span data-ttu-id="fbb8e-105">これらの製品は、マイクロソフトから無料でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-105">You can download these products free of charge from Microsoft.</span></span>

## <a name="get-the-northwind-sample-database-for-sql-server"></a><span data-ttu-id="fbb8e-106">SQL Server のノースウィンド サンプル データベースを取得する</span><span class="sxs-lookup"><span data-stu-id="fbb8e-106">Get the Northwind sample database for SQL Server</span></span>

<span data-ttu-id="fbb8e-107">次の`instnwnd.sql`GitHub リポジトリからスクリプトをダウンロードして、SQL Server 用の Northwind サンプル データベースを作成して読み込みます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-107">Download the script `instnwnd.sql` from the following GitHub repository to create and load the Northwind sample database for SQL Server:</span></span>

[<span data-ttu-id="fbb8e-108">ノースウィンドおよびパブのサンプル データベース</span><span class="sxs-lookup"><span data-stu-id="fbb8e-108">Northwind and pubs sample databases for Microsoft SQL Server</span></span>](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

<span data-ttu-id="fbb8e-109">Northwind データベースを使用するには、ダウンロードした`instnwnd.sql`スクリプト ファイルを実行して[、SQL Server 管理スタジオ](#get_ssms)または同様のツールを使用して SQL Server のインスタンス上にデータベースを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-109">Before you can use the Northwind database, you have to run the downloaded `instnwnd.sql` script file to recreate the database on an instance of SQL Server by using [SQL Server Management Studio](#get_ssms) or a similar tool.</span></span> <span data-ttu-id="fbb8e-110">リポジトリの Readme ファイルの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-110">Follow the instructions in the Readme file in the repository.</span></span>

> [!TIP]
> <span data-ttu-id="fbb8e-111">Access 用のノースウィンド データベースを探している場合は、「Access 用[のノースウィンド サンプル データベースのインストール](#northwind_access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-111">If you're looking for the Northwind database for Microsoft Access, see [Install the Northwind sample database for Microsoft Access](#northwind_access).</span></span>

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a><span data-ttu-id="fbb8e-112">Access 用のノースウィンド サンプル データベースを取得する</span><span class="sxs-lookup"><span data-stu-id="fbb8e-112">Get the Northwind sample database for Microsoft Access</span></span>

<span data-ttu-id="fbb8e-113">マイクロソフト のマイクロソフト ダウンロード センターでは、Access 用のノースウィンド サンプル データベースは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-113">The Northwind sample database for Microsoft Access is not available on the Microsoft Download Center.</span></span> <span data-ttu-id="fbb8e-114">Access から直接 Northwind をインストールするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-114">To install Northwind directly from within Access, do the following things:</span></span>

1. <span data-ttu-id="fbb8e-115">アクセスを開きます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-115">Open Access.</span></span>

1. <span data-ttu-id="fbb8e-116">**[オンライン テンプレートの検索**] ボックスに **「Northwind」** と入力し、[**入力**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-116">Enter **Northwind** in the **Search for Online Templates** box, and then select **Enter**.</span></span>

1. <span data-ttu-id="fbb8e-117">結果画面で、[**ノースウィンド**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-117">On the results screen, select **Northwind**.</span></span> <span data-ttu-id="fbb8e-118">Northwind データベースの説明を含む新しいウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-118">A new window opens with a description of the Northwind database.</span></span>

1. <span data-ttu-id="fbb8e-119">新しいウィンドウの **[ファイル名**] テキスト ボックスに、Northwind データベースのコピーのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-119">In the new window, in the **File Name** text box, provide a filename for your copy of the Northwind database.</span></span>

1. <span data-ttu-id="fbb8e-120">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-120">Select **Create**.</span></span> <span data-ttu-id="fbb8e-121">ノースウィンド データベースがダウンロードされ、ファイルが準備されます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-121">Access downloads the Northwind database and prepares the file.</span></span>

1. <span data-ttu-id="fbb8e-122">このプロセスが完了すると、データベースが開き、ようこそ画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-122">When this process is complete, the database opens with a Welcome screen.</span></span>

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="fbb8e-123">SQL サーバーのアドベンチャーワークス サンプル データベースを取得する</span><span class="sxs-lookup"><span data-stu-id="fbb8e-123">Get the AdventureWorks sample database for SQL Server</span></span>

<span data-ttu-id="fbb8e-124">次の GitHub リポジトリから SQL Server のアドベンチャーワークス サンプル データベースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-124">Download the AdventureWorks sample database for SQL Server from the following GitHub repository:</span></span>

[<span data-ttu-id="fbb8e-125">AdventureWorks サンプル データベース</span><span class="sxs-lookup"><span data-stu-id="fbb8e-125">AdventureWorks sample databases</span></span>](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

<span data-ttu-id="fbb8e-126">いずれかのデータベース バックアップ (.bak)\*ファイルをダウンロードした後、SQL Server 管理スタジオ (SSMS) を使用して、バックアップを SQL Server のインスタンスに復元します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-126">After you download one of the database backup (\*.bak) files, restore the backup to an instance of SQL Server by using SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="fbb8e-127">[「SQL Server 管理スタジオの取得](#get_ssms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-127">See [Get SQL Server Management Studio](#get_ssms).</span></span>

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a><span data-ttu-id="fbb8e-128">取得 SQL サーバー管理スタジオ</span><span class="sxs-lookup"><span data-stu-id="fbb8e-128">Get SQL Server Management Studio</span></span>
<span data-ttu-id="fbb8e-129">ダウンロードしたデータベースを表示または変更する場合は、SQL Server 管理スタジオ (SSMS) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-129">If you want to view or modify a database that you've downloaded, you can use SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="fbb8e-130">次のページから SSMS をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-130">Download SSMS from the following page:</span></span>

[<span data-ttu-id="fbb8e-131">SQL Server Management Studio (SSMS) のダウンロード</span><span class="sxs-lookup"><span data-stu-id="fbb8e-131">Download SQL Server Management Studio (SSMS)</span></span>](/sql/ssms/download-sql-server-management-studio-ssms)

<span data-ttu-id="fbb8e-132">また、Visual Studio 統合開発環境 (IDE) でデータベースを表示および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-132">You can also view and manage databases in the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="fbb8e-133">[Visual Studio で](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)、 SQL **Server オブジェクト エクスプローラー**からデータベースに接続するか、**またはサーバー エクスプローラー**でデータベースへのデータ接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-133">In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), connect to the database from **SQL Server Object Explorer**, or create a Data Connection to the database in **Server Explorer**.</span></span> <span data-ttu-id="fbb8e-134">[**表示**] メニューからこれらのエクスプローラ ペインを開きます。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-134">Open these explorer panes from the **View** menu.</span></span>

## <a name="get-sql-server-express"></a><a name="get_sql"></a><span data-ttu-id="fbb8e-135">SQL サーバー エクスプレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-135">Get SQL Server Express</span></span>

<span data-ttu-id="fbb8e-136">SQL Server Express は、アプリケーションと共に再配布できる、エントリ レベルの無料エディションです。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-136">SQL Server Express is a free, entry-level edition of SQL Server that you can redistribute with applications.</span></span> <span data-ttu-id="fbb8e-137">次のページから SQL Server エクスプレスをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-137">Download SQL Server Express from the following page:</span></span>
  
[<span data-ttu-id="fbb8e-138">SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="fbb8e-138">SQL Server Express Edition</span></span>](https://www.microsoft.com/sql-server/sql-server-editions-express)

<span data-ttu-id="fbb8e-139">[を](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)使用している場合は、SQL Server エクスプレス のローカル DB は、無料のコミュニティ エディションの Visual Studio に含まれています。</span><span class="sxs-lookup"><span data-stu-id="fbb8e-139">If you're using [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB is included in the free Community edition of Visual Studio, as well as the Professional and higher editions.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fbb8e-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbb8e-140">See also</span></span>

- [<span data-ttu-id="fbb8e-141">はじめに</span><span class="sxs-lookup"><span data-stu-id="fbb8e-141">Getting Started</span></span>](getting-started.md)
