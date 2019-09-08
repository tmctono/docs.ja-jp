---
title: サンプル データベースのダウンロード (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: c67ee699cf594f476a728c7345b47b0c32dea7ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795178"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="75e10-102">サンプル データベースのダウンロード (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="75e10-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="75e10-103">LINQ to DataSet ドキュメントのサンプルとチュートリアルでは、AdventureWorks サンプルデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="75e10-103">The samples and walkthroughs in the LINQ to DataSet documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="75e10-104">この製品は、Microsoft のダウンロード サイトから無償でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="75e10-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="75e10-105">LINQ to DataSet ドキュメントのサンプルとチュートリアルでは、データストアとして SQL Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="75e10-105">The samples and walkthroughs in the LINQ to DataSet documentation use SQL Server as the data store.</span></span> <span data-ttu-id="75e10-106">SQL Server の代わりに、無償で提供されている SQL Server Express Edition をデータ ストアとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="75e10-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="75e10-107">AdventureWorks データベースのダウンロードとインストール</span><span class="sxs-lookup"><span data-stu-id="75e10-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="75e10-108">SQL Server の AdventureWorks サンプル データベースをダウンロードおよびインストールするには</span><span class="sxs-lookup"><span data-stu-id="75e10-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1. <span data-ttu-id="75e10-109">Internet Explorer を開きます。</span><span class="sxs-lookup"><span data-stu-id="75e10-109">Open Internet Explorer.</span></span>  
  
2. <span data-ttu-id="75e10-110">[SQL Server 2005 のサンプルとサンプルデータベース](https://go.microsoft.com/fwlink/?linkid=31046)の Web サイトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75e10-110">Go to the [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3. <span data-ttu-id="75e10-111">記載されている手順に従ってプロセッサの種類に応じた AdventureWorks サンプル データベース (AdventureWorksDB.msi など) をダウンロードし、.MSI ファイルをローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="75e10-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4. <span data-ttu-id="75e10-112">以前のバージョンの AdventureWorks は、単体でダウンロードしたか SQL Server のセットアップ時にインストールしたかに関係なく、AdventureWorks.msi の実行前に削除しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="75e10-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="75e10-113">単体でダウンロードした以前のバージョンの AdventureWorks サンプル データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="75e10-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1. <span data-ttu-id="75e10-114">AdventureWorks データベースまたは AdventureWorksDW データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="75e10-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="75e10-115">**[プログラムの追加と削除]** から**Adventureworksdb.msi**または**adventureworksbi.msi**を選択し、 **[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75e10-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="75e10-116">過去にセットアップ プログラムを使用してインストールした AdventureWorks サンプル データベースを削除するには</span><span class="sxs-lookup"><span data-stu-id="75e10-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1. <span data-ttu-id="75e10-117">AdventureWorks データベースまたは AdventureWorksDW データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="75e10-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2. <span data-ttu-id="75e10-118">**[プログラムの追加と削除]** で**Microsoft SQL Server 2005**を選択し、 **[変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75e10-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3. <span data-ttu-id="75e10-119">**[コンポーネントの選択]** で、 **[ワークステーションコンポーネント]** を選択し、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75e10-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4. <span data-ttu-id="75e10-120">ようこそ の  **SQL Server インストールウィザード** で、**次へ** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75e10-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5. <span data-ttu-id="75e10-121">**[システム構成チェック]** で、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75e10-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6. <span data-ttu-id="75e10-122">**[インスタンスの変更または削除]** で、 **[インストールされたコンポーネントの変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75e10-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7. <span data-ttu-id="75e10-123">**[機能の選択]** で、[**ドキュメント]、[サンプル]、[サンプルデータベース**] ノードの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="75e10-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8. <span data-ttu-id="75e10-124">**[サンプルコードとアプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="75e10-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="75e10-125">**サンプルデータベース** を展開し、削除するサンプルデータベースを選択します。 機能全体を選択する**は使用**できません。</span><span class="sxs-lookup"><span data-stu-id="75e10-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="75e10-126">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75e10-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="75e10-127">**[インストール]** をクリックし、インストールウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="75e10-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="75e10-128">AdventureWorks サンプル データベース ファイルを SQL Server のインスタンスにアタッチするには</span><span class="sxs-lookup"><span data-stu-id="75e10-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1. <span data-ttu-id="75e10-129">ファイルサンプルデータベースインストーラーファイルがダウンロードされたら、 **adventureworksdb.msi**ファイル (またはダウンロードしたファイル) をダブルクリックして、データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="75e10-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="75e10-130">既定では、データベースは c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="75e10-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2. <span data-ttu-id="75e10-131">SQLCMD または SQL Server Management Studio で次のスクリプトを実行し、AdventureWorks データベース ファイルを SQL Server のインスタンスにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="75e10-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="75e10-132">これらのファイルが異なるドライブまたはディレクトリにインストールされている場合は、パスを適宜修正してから、`sp_attach_db` ストアド プロシージャを実行してください。</span><span class="sxs-lookup"><span data-stu-id="75e10-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="75e10-133">SQL Server Express Edition のダウンロード</span><span class="sxs-lookup"><span data-stu-id="75e10-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="75e10-134">LINQ to DataSet セクションのサンプルとチュートリアルでは、データストアとして 2005 SQL Server を使用しますが、代わりに SQL Server Express エディションを使用するように変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="75e10-134">The samples and walkthroughs in the LINQ to DataSet section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="75e10-135">SQL Server Express Edition は無料で入手でき、アプリケーションと共に再配布できます。</span><span class="sxs-lookup"><span data-stu-id="75e10-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="75e10-136">Visual Studio を使用している場合、SQL Server Express Edition は Pro 以降のエディションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="75e10-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="75e10-137">SQL Server Express Edition をダウンロードおよびインストールするには</span><span class="sxs-lookup"><span data-stu-id="75e10-137">To download and install SQL Server Express Edition</span></span>  
  
1. <span data-ttu-id="75e10-138">Internet Explorer を開始します。</span><span class="sxs-lookup"><span data-stu-id="75e10-138">Start Internet Explorer.</span></span>  
  
2. <span data-ttu-id="75e10-139">[Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070)のダウンロードページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="75e10-139">Go to the  [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3. <span data-ttu-id="75e10-140">Web サイトに記載されているインストールの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="75e10-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e10-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="75e10-141">See also</span></span>

- [<span data-ttu-id="75e10-142">はじめに</span><span class="sxs-lookup"><span data-stu-id="75e10-142">Getting Started</span></span>](getting-started-linq-to-dataset.md)
