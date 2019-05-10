---
title: 'チュートリアル: ストアド プロシージャのみを使用する (C#)'
ms.date: 03/30/2017
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
ms.openlocfilehash: f4c34252f7d92985dac94663c85d3cca0dc58ab3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655123"
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="7db3c-102">チュートリアル: ストアド プロシージャのみを使用する (C#)</span><span class="sxs-lookup"><span data-stu-id="7db3c-102">Walkthrough: Using Only Stored Procedures (C#)</span></span>
<span data-ttu-id="7db3c-103">このチュートリアルでは、ストアド プロシージャを実行することでのみデータにアクセスする、基本的な [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] シナリオ全体を示します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="7db3c-104">この方法は、データ ストアへのアクセス方法を制限する目的で、データベース管理者によってよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7db3c-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションでストアド プロシージャを使用して、既定の動作をオーバーライドすることもできます。これは、`Create`、`Update`、および `Delete` の各プロセスで特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="7db3c-106">詳細については、次を参照してください。[のカスタマイズを挿入、更新、および削除を行う](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="7db3c-107">このチュートリアルの目的は、Northwind サンプル データベース内のストアド プロシージャにマップされている 2 つのメソッドを使用します。CustOrdersDetail および CustOrderHist します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="7db3c-108">このマップは、SqlMetal コマンド ライン ツールを実行して C# ファイルを生成したときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-108">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="7db3c-109">詳細については、このチュートリアルの「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db3c-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="7db3c-110">このチュートリアルは、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]には依存しません。</span><span class="sxs-lookup"><span data-stu-id="7db3c-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="7db3c-111">Visual Studio を使用している開発者が使用することも、[!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]ストアド プロシージャの機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="7db3c-112">参照してください[LINQ to Visual Studio での SQL ツール](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="7db3c-113">このチュートリアルは、Visual C# 開発設定を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="7db3c-113">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7db3c-114">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7db3c-114">Prerequisites</span></span>  
 <span data-ttu-id="7db3c-115">このチュートリアルの前提条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7db3c-115">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="7db3c-116">このチュートリアルでは、専用フォルダー ("c:\linqtest7") を使用してファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-116">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="7db3c-117">チュートリアルを開始する前に、このフォルダーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="7db3c-117">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="7db3c-118">Northwind サンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="7db3c-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="7db3c-119">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード サイトからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="7db3c-120">手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="7db3c-121">データベースをダウンロードしたら、northwnd.mdf ファイルを c:\linqtest7 フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>  
  
- <span data-ttu-id="7db3c-122">Northwind データベースから生成された C# コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="7db3c-122">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="7db3c-123">このチュートリアルは、SqlMetal ツールを使用して次のコマンド ラインで作成されています。</span><span class="sxs-lookup"><span data-stu-id="7db3c-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="7db3c-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="7db3c-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="7db3c-125">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7db3c-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="7db3c-126">概要</span><span class="sxs-lookup"><span data-stu-id="7db3c-126">Overview</span></span>  
 <span data-ttu-id="7db3c-127">このチュートリアルは、主に次の 6 つのタスクで構成されています。</span><span class="sxs-lookup"><span data-stu-id="7db3c-127">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="7db3c-128">設定する、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Visual Studio でソリューション。</span><span class="sxs-lookup"><span data-stu-id="7db3c-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="7db3c-129">プロジェクトに System.Data.Linq アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
- <span data-ttu-id="7db3c-130">プロジェクトにデータベース コード ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-130">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="7db3c-131">データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-131">Creating a connection with the database.</span></span>  
  
- <span data-ttu-id="7db3c-132">ユーザー インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-132">Setting up the user interface.</span></span>  
  
- <span data-ttu-id="7db3c-133">アプリケーションを実行およびテストします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="7db3c-134">LINQ to SQL ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="7db3c-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="7db3c-135">この最初のタスクでは、ビルドおよび実行するために必要な参照を含む Visual Studio ソリューションを作成、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="7db3c-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="7db3c-136">LINQ to SQL ソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="7db3c-136">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="7db3c-137">Visual Studio で**ファイル**メニューで、**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-137">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="7db3c-138">**プロジェクトの種類**ペインで、**新しいプロジェクト**ダイアログ ボックスで、をクリックして**Visual C#** します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-138">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3. <span data-ttu-id="7db3c-139">**[テンプレート]** ペインの **[Windows フォーム アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4. <span data-ttu-id="7db3c-140">**名前**ボックスに「 **SprocOnlyApp**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5. <span data-ttu-id="7db3c-141">**場所**ボックスで、プロジェクト ファイルを格納することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-141">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6. <span data-ttu-id="7db3c-142">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="7db3c-143">Windows フォーム デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-143">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="7db3c-144">LINQ to SQL アセンブリ参照を追加する</span><span class="sxs-lookup"><span data-stu-id="7db3c-144">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="7db3c-145">標準の Windows フォーム アプリケーション テンプレートには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アセンブリは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="7db3c-145">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="7db3c-146">次の手順に従って、アセンブリを自分で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7db3c-146">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="7db3c-147">System.Data.Linq.dll を追加するには</span><span class="sxs-lookup"><span data-stu-id="7db3c-147">To add System.Data.Linq.dll</span></span>  
  
1. <span data-ttu-id="7db3c-148">**ソリューション エクスプ ローラー**を右クリックして**参照**、 をクリックし、**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2. <span data-ttu-id="7db3c-149">**参照の追加**ダイアログ ボックスで、をクリックして **.NET**、System.Data.Linq アセンブリをクリックし、順にクリックして、 **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7db3c-150">アセンブリがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="7db3c-151">プロジェクトに Northwind コード ファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="7db3c-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="7db3c-152">この手順では、事前に SqlMetal ツールを使用して、Northwind サンプル データベースからコード ファイルを生成していることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="7db3c-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="7db3c-153">詳細については、このチュートリアルの「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7db3c-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="7db3c-154">プロジェクトに Northwind コード ファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="7db3c-154">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="7db3c-155">**[プロジェクト]** メニューの **[既存項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="7db3c-156">**既存項目の追加**ダイアログ ボックスが c:\linqtest7\northwind.cs に移動し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-156">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="7db3c-157">northwind.cs ファイルがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-157">The northwind.cs file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="7db3c-158">データベース接続を作成する</span><span class="sxs-lookup"><span data-stu-id="7db3c-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="7db3c-159">この手順では、Northwind サンプル データベースへの接続を定義します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="7db3c-160">このチュートリアルでは、パスとして "c:\linqtest7\northwnd.mdf" を使用します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-160">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="7db3c-161">データベース接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="7db3c-161">To create the database connection</span></span>  
  
1. <span data-ttu-id="7db3c-162">**ソリューション エクスプ ローラー**、右クリック**Form1.cs**、 をクリックし、**コードの表示**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-162">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>  
  
2. <span data-ttu-id="7db3c-163">`Form1` クラスに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-163">Type the following code into the `Form1` class:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="7db3c-164">ユーザー インターフェイスを設定する</span><span class="sxs-lookup"><span data-stu-id="7db3c-164">Setting up the User Interface</span></span>  
 <span data-ttu-id="7db3c-165">この手順では、ユーザーがストアド プロシージャを実行してデータベース内のデータにアクセスできるように、インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-165">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="7db3c-166">このチュートリアルで作成するアプリケーションでは、ユーザーがデータベース内のデータにアクセスできる手段は、アプリケーションに埋め込まれたストアド プロシージャを使用することだけです。</span><span class="sxs-lookup"><span data-stu-id="7db3c-166">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="7db3c-167">ユーザー インターフェイスを設定するには</span><span class="sxs-lookup"><span data-stu-id="7db3c-167">To set up the user interface</span></span>  
  
1. <span data-ttu-id="7db3c-168">戻り値を Windows フォーム デザイナー (**form1.cs [デザイン]**)。</span><span class="sxs-lookup"><span data-stu-id="7db3c-168">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>  
  
2. <span data-ttu-id="7db3c-169">**[表示]** メニューの **[ツールボックス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-169">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="7db3c-170">ツールボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-170">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7db3c-171">をクリックして、**自動的に隠す**このセクションの手順を残りの実行中に、ツールボックスを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-171">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3. <span data-ttu-id="7db3c-172">2 つのボタン、2 つのテキスト ボックス、および 2 つのラベルをツールボックスからドラッグ**Form1**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-172">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="7db3c-173">図のようにコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-173">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="7db3c-174">展開**Form1**コントロールを簡単に適合するようにします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-174">Expand **Form1** so that the controls fit easily.</span></span>  
  
4. <span data-ttu-id="7db3c-175">右クリックして**label1**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-175">Right-click **label1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="7db3c-176">変更、**テキスト**プロパティから**label1**に**Enter OrderID:** します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-176">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>  
  
6. <span data-ttu-id="7db3c-177">に対して同じ方法で**label2**、変更、**テキスト**プロパティから**label2**に**Enter CustomerID:** します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-177">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>  
  
7. <span data-ttu-id="7db3c-178">同様に、変更、**テキスト**プロパティを**button1**に**Order Details**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-178">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>  
  
8. <span data-ttu-id="7db3c-179">変更、**テキスト**プロパティ**button2**に**注文履歴**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-179">Change the **Text** property for **button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="7db3c-180">すべてのテキストが表示されるように、ボタン コントロールの幅を広げます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-180">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="7db3c-181">ボタン クリックを処理するには</span><span class="sxs-lookup"><span data-stu-id="7db3c-181">To handle button clicks</span></span>  
  
1. <span data-ttu-id="7db3c-182">ダブルクリック**Order Details**で**Form1**をコード エディターに button1 のイベント ハンドラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-182">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>  
  
2. <span data-ttu-id="7db3c-183">`button1` のハンドラーに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-183">Type the following code into the `button1` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3. <span data-ttu-id="7db3c-184">ダブルクリック**button2**で**Form1**を開く、`button2`ハンドラー</span><span class="sxs-lookup"><span data-stu-id="7db3c-184">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>  
  
4. <span data-ttu-id="7db3c-185">`button2` のハンドラーに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-185">Type the following code into the `button2` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="7db3c-186">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="7db3c-186">Testing the Application</span></span>  
 <span data-ttu-id="7db3c-187">次に、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="7db3c-187">Now it is time to test your application.</span></span> <span data-ttu-id="7db3c-188">データ ストアに対する操作は、2 つのストアド プロシージャで実行できる処理に制限されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7db3c-188">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="7db3c-189">つまり、入力した orderID に含まれている製品を返す処理と、入力した CustomerID の注文製品の履歴を返す処理のみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-189">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="7db3c-190">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="7db3c-190">To test the application</span></span>  
  
1. <span data-ttu-id="7db3c-191">F5 キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-191">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="7db3c-192">Form1 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-192">Form1 appears.</span></span>  
  
2. <span data-ttu-id="7db3c-193">**Enter OrderID**ボックスに「 `10249`、 をクリックし、 **Order Details**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-193">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="7db3c-194">注文 10249 に含まれている製品がメッセージ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-194">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="7db3c-195">クリックして**OK**メッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-195">Click **OK** to close the message box.</span></span>  
  
3. <span data-ttu-id="7db3c-196">**Enter CustomerID**ボックスに「 `ALFKI`、 をクリックし、**注文履歴**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-196">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="7db3c-197">顧客 ALFKI の注文履歴がメッセージ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-197">A message box appears that lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="7db3c-198">クリックして**OK**メッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-198">Click **OK** to close the message box.</span></span>  
  
4. <span data-ttu-id="7db3c-199">**Enter OrderID**ボックスに「 `123`、 をクリックし、 **Order Details**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-199">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="7db3c-200">"No results" というメッセージ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-200">A message box appears that displays "No results."</span></span>  
  
     <span data-ttu-id="7db3c-201">クリックして**OK**メッセージ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-201">Click **OK** to close the message box.</span></span>  
  
5. <span data-ttu-id="7db3c-202">**デバッグ** メニューのをクリックして**デバッグを停止**します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-202">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="7db3c-203">デバッグ セッションが終了します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-203">The debug session closes.</span></span>  
  
6. <span data-ttu-id="7db3c-204">クリックすることができる場合、実験が完了したら、**プロジェクトを閉じる**で、**ファイル**] メニューの [されたら、プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="7db3c-204">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7db3c-205">次の手順</span><span class="sxs-lookup"><span data-stu-id="7db3c-205">Next Steps</span></span>  
 <span data-ttu-id="7db3c-206">いくつかの変更を加えることによって、このプロジェクトを強化できます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-206">You can enhance this project by making some changes.</span></span> <span data-ttu-id="7db3c-207">たとえば、使用できるストアド プロシージャの一覧をリスト ボックスに表示し、実行するプロシージャをユーザーに選択させることができます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-207">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="7db3c-208">レポートの出力をテキスト ファイルに送ることもできます。</span><span class="sxs-lookup"><span data-stu-id="7db3c-208">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db3c-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="7db3c-209">See also</span></span>

- [<span data-ttu-id="7db3c-210">チュートリアルによる学習</span><span class="sxs-lookup"><span data-stu-id="7db3c-210">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="7db3c-211">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="7db3c-211">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
