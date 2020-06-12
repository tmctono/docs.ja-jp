---
title: 'チュートリアル: 簡単なオブジェクト モデルとクエリ (C#)'
description: このチュートリアルに従って、サンプル データベース内のテーブルをモデル化するエンティティ クラスを作成します。 その後、シンプルなクエリを作成して、特定の場所にいる顧客を一覧表示します。
ms.date: 03/30/2017
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
ms.openlocfilehash: 4637fabecc1726d8fec12857a667073912cfbed5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286302"
---
# <a name="walkthrough-simple-object-model-and-query-c"></a><span data-ttu-id="28d9c-104">チュートリアル: 簡単なオブジェクト モデルとクエリ (C#)</span><span class="sxs-lookup"><span data-stu-id="28d9c-104">Walkthrough: Simple Object Model and Query (C#)</span></span>

<span data-ttu-id="28d9c-105">このチュートリアルでは、複雑さを抑えた、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 全体の基本的なシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-105">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="28d9c-106">サンプルの Northwind データベースにある Customers テーブルのモデル化を行うエンティティ クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-106">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="28d9c-107">次に、住所がロンドンの顧客を表示するための簡単なクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-107">You will then create a simple query to list customers who are located in London.</span></span>

<span data-ttu-id="28d9c-108">このチュートリアルでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の考え方を示すために、コード中心の方法をあえて使用しています。</span><span class="sxs-lookup"><span data-stu-id="28d9c-108">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="28d9c-109">通常は、オブジェクト リレーショナル デザイナーを使用してオブジェクト モデルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-109">Normally speaking, you would use the Object Relational Designer to create your object model.</span></span>

[!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]

<span data-ttu-id="28d9c-110">このチュートリアルは、Visual C# 開発設定を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="28d9c-110">This walkthrough was written by using Visual C# Development Settings.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28d9c-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="28d9c-111">Prerequisites</span></span>

- <span data-ttu-id="28d9c-112">このチュートリアルでは、専用フォルダー ("c:\linqtest5") を使用してファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-112">This walkthrough uses a dedicated folder ("c:\linqtest5") to hold files.</span></span> <span data-ttu-id="28d9c-113">チュートリアルを開始する前に、このフォルダーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="28d9c-113">Create this folder before you begin the walkthrough.</span></span>

- <span data-ttu-id="28d9c-114">このチュートリアルには、Northwind サンプル データベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="28d9c-114">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="28d9c-115">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード サイトからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-115">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="28d9c-116">手順については、「[サンプル データベースのダウンロード](downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d9c-116">For instructions, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span> <span data-ttu-id="28d9c-117">データベースをダウンロードしたら、ファイルを c:\linqtest5 フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-117">After you have downloaded the database, copy the file to the c:\linqtest5 folder.</span></span>

## <a name="overview"></a><span data-ttu-id="28d9c-118">概要</span><span class="sxs-lookup"><span data-stu-id="28d9c-118">Overview</span></span>

<span data-ttu-id="28d9c-119">このチュートリアルは、主に次の 6 つの手順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="28d9c-119">This walkthrough consists of six main tasks:</span></span>

- <span data-ttu-id="28d9c-120">Visual Studio で [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-120">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>

- <span data-ttu-id="28d9c-121">データベース テーブルにクラスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-121">Mapping a class to a database table.</span></span>

- <span data-ttu-id="28d9c-122">クラスに対し、データベース列を表すプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-122">Designating properties on the class to represent database columns.</span></span>

- <span data-ttu-id="28d9c-123">Northwind データベースへの接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-123">Specifying the connection to the Northwind database.</span></span>

- <span data-ttu-id="28d9c-124">データベースに対して実行する簡単なクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-124">Creating a simple query to run against the database.</span></span>

- <span data-ttu-id="28d9c-125">クエリを実行して結果を観察する。</span><span class="sxs-lookup"><span data-stu-id="28d9c-125">Executing the query and observing the results.</span></span>

## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="28d9c-126">LINQ to SQL ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="28d9c-126">Creating a LINQ to SQL Solution</span></span>

<span data-ttu-id="28d9c-127">最初のタスクに、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] プロジェクトをビルドおよび実行するために必要な参照を含む Visual Studio ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-127">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>

### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="28d9c-128">LINQ to SQL ソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="28d9c-128">To create a LINQ to SQL solution</span></span>

1. <span data-ttu-id="28d9c-129">Visual Studio の **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-129">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="28d9c-130">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、 **[Visual C#]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-130">In the **Project types** pane of the **New Project** dialog box, click **Visual C#**.</span></span>

3. <span data-ttu-id="28d9c-131">**[テンプレート]** ペインの **[コンソール アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-131">In the **Templates** pane, click **Console Application**.</span></span>

4. <span data-ttu-id="28d9c-132">**[名前]** ボックスに「**LinqConsoleApp**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-132">In the **Name** box, type **LinqConsoleApp**.</span></span>

5. <span data-ttu-id="28d9c-133">**[場所]** ボックスで、プロジェクト ファイルを格納する場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-133">In the **Location** box, verify where you want to store your project files.</span></span>

6. <span data-ttu-id="28d9c-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-134">Click **OK**.</span></span>

## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="28d9c-135">LINQ の参照とディレクティブを追加する</span><span class="sxs-lookup"><span data-stu-id="28d9c-135">Adding LINQ References and Directives</span></span>

<span data-ttu-id="28d9c-136">このチュートリアルで使用するアセンブリは、既定ではプロジェクトにインストールされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="28d9c-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="28d9c-137">System.Data.Linq がプロジェクトの参照 (**ソリューション エクスプローラー**で **[参照]** ノードを展開) に表示されていない場合は、以下の手順に従って追加します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-137">If System.Data.Linq is not listed as a reference in your project (expand the **References** node in **Solution Explorer**), add it, as explained in the following steps.</span></span>

### <a name="to-add-systemdatalinq"></a><span data-ttu-id="28d9c-138">System.Data.Linq を追加するには</span><span class="sxs-lookup"><span data-stu-id="28d9c-138">To add System.Data.Linq</span></span>

1. <span data-ttu-id="28d9c-139">**ソリューション エクスプローラー**で、 **[参照設定]** を右クリックし、 **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>

2. <span data-ttu-id="28d9c-140">**[参照の追加]** ダイアログ ボックスで、 **[.NET]** をクリックし、System.Data.Linq アセンブリをクリックします。次に、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>

     <span data-ttu-id="28d9c-141">アセンブリがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-141">The assembly is added to the project.</span></span>

3. <span data-ttu-id="28d9c-142">**Program.cs** の先頭に、次のディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-142">Add the following directives at the top of **Program.cs**:</span></span>

     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]

## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="28d9c-143">データベース テーブルにクラスを対応付ける</span><span class="sxs-lookup"><span data-stu-id="28d9c-143">Mapping a Class to a Database Table</span></span>

<span data-ttu-id="28d9c-144">この手順では、クラスを作成して、データベース テーブルに対応付けます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-144">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="28d9c-145">このようなクラスのことを "*エンティティ クラス*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-145">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="28d9c-146">対応付けは、<xref:System.Data.Linq.Mapping.TableAttribute> 属性を追加するだけで完了します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-146">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="28d9c-147"><xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> プロパティを使用して、データベースのテーブルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-147">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>

### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="28d9c-148">エンティティ クラスを作成し、データベース テーブルに対応付けるには</span><span class="sxs-lookup"><span data-stu-id="28d9c-148">To create an entity class and map it to a database table</span></span>

- <span data-ttu-id="28d9c-149">Program.cs の `Program` クラス宣言の直前に次のコードを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-149">Type or paste the following code into Program.cs immediately above the `Program` class declaration:</span></span>

     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]

## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="28d9c-150">データベース列を表すプロパティをクラスに追加する</span><span class="sxs-lookup"><span data-stu-id="28d9c-150">Designating Properties on the Class to Represent Database Columns</span></span>

<span data-ttu-id="28d9c-151">この手順では、いくつかのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-151">In this step, you accomplish several tasks.</span></span>

- <span data-ttu-id="28d9c-152"><xref:System.Data.Linq.Mapping.ColumnAttribute> 属性を使用して、エンティティ クラスの `CustomerID` プロパティおよび `City` プロパティを、データベース テーブルの列を表すものとして指定します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-152">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>

- <span data-ttu-id="28d9c-153">`CustomerID` プロパティを、データベースの主キー列を表すものとして指定します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-153">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>

- <span data-ttu-id="28d9c-154">プライベートでの格納用として `_CustomerID` フィールドおよび `_City` フィールドを指定します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-154">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="28d9c-155">これで、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、ビジネス ロジックを含む場合があるパブリック アクセサーを使用せずに、値を直接格納および取得できます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-155">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>

### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="28d9c-156">2 つのデータベース列の特性を指定するには</span><span class="sxs-lookup"><span data-stu-id="28d9c-156">To represent characteristics of two database columns</span></span>

- <span data-ttu-id="28d9c-157">Program.cs の `Customer` クラスの中かっこ内に次のコードを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-157">Type or paste the following code into Program.cs inside the curly braces for the `Customer` class.</span></span>

     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]

## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="28d9c-158">Northwind データベースへの接続を指定する</span><span class="sxs-lookup"><span data-stu-id="28d9c-158">Specifying the Connection to the Northwind Database</span></span>

<span data-ttu-id="28d9c-159">この手順では、<xref:System.Data.Linq.DataContext> オブジェクトを使用して、コードで作成したデータ構造とデータベース本体との間の接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-159">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="28d9c-160">データベースからのオブジェクトの取得や、変更内容の送信では、<xref:System.Data.Linq.DataContext> を仲介役として使用します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-160">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>

<span data-ttu-id="28d9c-161">また、データベースの Customers テーブルに対するクエリ用として、型指定された論理的なテーブルの役割を果たす `Table<Customer>` を宣言します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-161">You also declare a `Table<Customer>` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="28d9c-162">これらのクエリの作成と実行は後の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="28d9c-162">You will create and execute these queries in later steps.</span></span>

### <a name="to-specify-the-database-connection"></a><span data-ttu-id="28d9c-163">データベース接続を指定するには</span><span class="sxs-lookup"><span data-stu-id="28d9c-163">To specify the database connection</span></span>

- <span data-ttu-id="28d9c-164">`Main` メソッドに次のコードを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-164">Type or paste the following code into the `Main` method.</span></span>

     <span data-ttu-id="28d9c-165">`northwnd.mdf` ファイルは、linqtest5 フォルダーにあるものとします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-165">Note that the `northwnd.mdf` file is assumed to be in the linqtest5 folder.</span></span> <span data-ttu-id="28d9c-166">詳細については、このチュートリアルの「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d9c-166">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>

     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]

## <a name="creating-a-simple-query"></a><span data-ttu-id="28d9c-167">簡単なクエリの作成</span><span class="sxs-lookup"><span data-stu-id="28d9c-167">Creating a Simple Query</span></span>

<span data-ttu-id="28d9c-168">この手順では、データベースの Customers テーブルから、住所が London の顧客を検索するクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-168">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="28d9c-169">この手順で作成するクエリ コードは、クエリを指定するだけです。</span><span class="sxs-lookup"><span data-stu-id="28d9c-169">The query code in this step just describes the query.</span></span> <span data-ttu-id="28d9c-170">実行は行いません。</span><span class="sxs-lookup"><span data-stu-id="28d9c-170">It does not execute it.</span></span> <span data-ttu-id="28d9c-171">このような方法を "*遅延実行*" といいます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-171">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="28d9c-172">詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d9c-172">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

<span data-ttu-id="28d9c-173">また、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] が生成した SQL コマンドをログに出力します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-173">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="28d9c-174"><xref:System.Data.Linq.DataContext.Log%2A> を使用したこのログ機能は、デバッグに有効で、データベースに送信されたコマンドが目的のクエリを正確に表しているかどうかを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-174">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="28d9c-175">簡単なクエリを作成するには</span><span class="sxs-lookup"><span data-stu-id="28d9c-175">To create a simple query</span></span>

- <span data-ttu-id="28d9c-176">`Main` メソッドの `Table<Customer>` 宣言の後に次のコードを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-176">Type or paste the following code into the `Main` method after the `Table<Customer>` declaration.</span></span>

     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]

## <a name="executing-the-query"></a><span data-ttu-id="28d9c-177">クエリの実行</span><span class="sxs-lookup"><span data-stu-id="28d9c-177">Executing the Query</span></span>

<span data-ttu-id="28d9c-178">この手順では、実際にクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-178">In this step, you actually execute the query.</span></span> <span data-ttu-id="28d9c-179">ここまでの手順で作成したクエリ式は、結果が必要になるまでは評価されません。</span><span class="sxs-lookup"><span data-stu-id="28d9c-179">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="28d9c-180">`foreach` の反復処理を開始した時点で、データベースに対して SQL コマンドが実行され、オブジェクトが実体化されます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-180">When you begin the `foreach` iteration, a SQL command is executed against the database and objects are materialized.</span></span>

### <a name="to-execute-the-query"></a><span data-ttu-id="28d9c-181">クエリを実行するには</span><span class="sxs-lookup"><span data-stu-id="28d9c-181">To execute the query</span></span>

1. <span data-ttu-id="28d9c-182">`Main` メソッドの末尾 (クエリ指定の後) に次のコードを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-182">Type or paste the following code at the end of the `Main` method (after the query description).</span></span>

     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]

2. <span data-ttu-id="28d9c-183">F5 キーを押してアプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="28d9c-183">Press F5 to debug the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="28d9c-184">アプリケーションで実行時エラーが発生した場合は、「[チュートリアルによる学習](learning-by-walkthroughs.md)」のトラブルシューティングのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="28d9c-184">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

     <span data-ttu-id="28d9c-185">クエリの結果は、以下のようにコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="28d9c-185">The query results in the console window should appear as follows:</span></span>

     `ID=AROUT, City=London`

     `ID=BSBEV, City=London`

     `ID=CONSH, City=London`

     `ID=EASTC, City=London`

     `ID=NORTS, City=London`

     `ID=SEVES, City=London`

3. <span data-ttu-id="28d9c-186">コンソール ウィンドウで Enter キーを押してアプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-186">Press Enter in the console window to close the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="28d9c-187">次の手順</span><span class="sxs-lookup"><span data-stu-id="28d9c-187">Next Steps</span></span>

<span data-ttu-id="28d9c-188">「[チュートリアル: リレーションシップ間でクエリを実行する (C#)](walkthrough-querying-across-relationships-csharp.md)」トピックは、このチュートリアルの終了位置から続行します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-188">The [Walkthrough: Querying Across Relationships (C#)](walkthrough-querying-across-relationships-csharp.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="28d9c-189">「リレーションシップ間でクエリを実行する」のチュートリアルでは、リレーショナル データベースの "*結合*" と同じように、複数のテーブルにまたがったクエリを [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] で行う方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="28d9c-189">The Query Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>

<span data-ttu-id="28d9c-190">「リレーションシップ間でクエリを実行する」のチュートリアルに進む場合は、必要条件として、ここで完了したチュートリアルのソリューションを保存しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="28d9c-190">If you want to do the Query Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>

## <a name="see-also"></a><span data-ttu-id="28d9c-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="28d9c-191">See also</span></span>

- [<span data-ttu-id="28d9c-192">チュートリアルによる学習</span><span class="sxs-lookup"><span data-stu-id="28d9c-192">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
