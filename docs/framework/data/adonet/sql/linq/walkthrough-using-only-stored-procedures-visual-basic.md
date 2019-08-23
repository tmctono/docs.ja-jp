---
title: 'チュートリアル: ストアド プロシージャのみの使用 (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 159b65b4b58b9142a168401ea2a881af2714df5f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946640"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a><span data-ttu-id="d38fc-102">チュートリアル: ストアド プロシージャのみの使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d38fc-102">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>
<span data-ttu-id="d38fc-103">このチュートリアルでは、ストアド プロシージャのみを使用してデータにアクセスする、基本の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] シナリオ全体を示します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by using stored procedures only.</span></span> <span data-ttu-id="d38fc-104">この方法は、データ ストアへのアクセス方法を制限する目的で、データベース管理者によってよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d38fc-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションでストアド プロシージャを使用して、既定の動作をオーバーライドすることもできます。これは、`Create`、`Update`、および `Delete` の各プロセスで特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="d38fc-106">詳細については、「[挿入、更新、および削除の操作をカスタマイズ](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="d38fc-107">このチュートリアルでは、Northwind サンプルデータベースのストアドプロシージャにマップされている2つのメソッドを使用します。CustOrdersDetail と CustOrderHist。</span><span class="sxs-lookup"><span data-stu-id="d38fc-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="d38fc-108">このマッピングは、SqlMetal コマンドラインツールを実行して Visual Basic ファイルを生成するときに行われます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-108">The mapping occurs when you run the SqlMetal command-line tool to generate a Visual Basic file.</span></span> <span data-ttu-id="d38fc-109">詳細については、このチュートリアルの「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="d38fc-110">このチュートリアルは、オブジェクトリレーショナルデザイナーに依存しません。</span><span class="sxs-lookup"><span data-stu-id="d38fc-110">This walkthrough does not rely on the Object Relational Designer.</span></span> <span data-ttu-id="d38fc-111">Visual Studio を使用する開発者は、O/R デザイナーを使用してストアドプロシージャ機能を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-111">Developers using Visual Studio can also use the O/R Designer to implement stored procedure functionality.</span></span> <span data-ttu-id="d38fc-112">「 [Visual Studio の LINQ to SQL ツール」を](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="d38fc-113">このチュートリアルは、Visual Basic 開発設定を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="d38fc-113">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d38fc-114">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d38fc-114">Prerequisites</span></span>  
 <span data-ttu-id="d38fc-115">このチュートリアルの前提条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d38fc-115">This walkthrough requires the following:</span></span>  
  
- <span data-ttu-id="d38fc-116">このチュートリアルでは、専用フォルダー ("c:\linqtest3") を使用してファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-116">This walkthrough uses a dedicated folder ("c:\linqtest3") to hold files.</span></span> <span data-ttu-id="d38fc-117">チュートリアルを開始する前に、このフォルダーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-117">Create this folder before you begin the walkthrough.</span></span>  
  
- <span data-ttu-id="d38fc-118">Northwind サンプル データベース。</span><span class="sxs-lookup"><span data-stu-id="d38fc-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="d38fc-119">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード サイトからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="d38fc-120">手順については、「[サンプルデータベースのダウンロード](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="d38fc-121">データベースをダウンロードしたら、northwnd.mdf ファイルを c:\linqtest3 フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest3 folder.</span></span>  
  
- <span data-ttu-id="d38fc-122">Northwind データベースから生成された Visual Basic コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="d38fc-122">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="d38fc-123">このチュートリアルは、SqlMetal ツールを使用して次のコマンド ラインで作成されています。</span><span class="sxs-lookup"><span data-stu-id="d38fc-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="d38fc-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="d38fc-124">**sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="d38fc-125">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d38fc-126">概要</span><span class="sxs-lookup"><span data-stu-id="d38fc-126">Overview</span></span>  
 <span data-ttu-id="d38fc-127">このチュートリアルは、主に次の 6 つのタスクで構成されています。</span><span class="sxs-lookup"><span data-stu-id="d38fc-127">This walkthrough consists of six main tasks:</span></span>  
  
- <span data-ttu-id="d38fc-128">Visual Studio でソリューションを設定します。 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d38fc-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
- <span data-ttu-id="d38fc-129">プロジェクトに System.Data.Linq アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
- <span data-ttu-id="d38fc-130">プロジェクトにデータベース コード ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-130">Adding the database code file to the project.</span></span>  
  
- <span data-ttu-id="d38fc-131">データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-131">Creating a connection to the database.</span></span>  
  
- <span data-ttu-id="d38fc-132">ユーザー インターフェイスを設定します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-132">Setting up the user interface.</span></span>  
  
- <span data-ttu-id="d38fc-133">アプリケーションを実行およびテストします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="d38fc-134">LINQ to SQL ソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="d38fc-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="d38fc-135">この最初のタスクでは、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]プロジェクトをビルドして実行するために必要な参照を含む Visual Studio ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="d38fc-136">LINQ to SQL ソリューションを作成するには</span><span class="sxs-lookup"><span data-stu-id="d38fc-136">To create a LINQ to SQL solution</span></span>  
  
1. <span data-ttu-id="d38fc-137">Visual Studio で **[ファイル]** メニューの **[新しいプロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-137">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2. <span data-ttu-id="d38fc-138">**[新しいプロジェクト]** ダイアログ ボックスの **[プロジェクトの種類]** ペインで、 **[Visual Basic]** を展開し、 **[Windows]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-138">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3. <span data-ttu-id="d38fc-139">**[テンプレート]** ペインの **[Windows フォーム アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4. <span data-ttu-id="d38fc-140">**[名前]** ボックスに「 **Sprocon氏アプリ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5. <span data-ttu-id="d38fc-141">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="d38fc-142">Windows フォーム デザイナーが開きます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-142">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="d38fc-143">LINQ to SQL アセンブリ参照を追加する</span><span class="sxs-lookup"><span data-stu-id="d38fc-143">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="d38fc-144">標準の Windows フォーム アプリケーション テンプレートには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アセンブリは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="d38fc-144">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="d38fc-145">次の手順に従って、アセンブリを自分で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d38fc-145">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="d38fc-146">System.Data.Linq.dll を追加するには</span><span class="sxs-lookup"><span data-stu-id="d38fc-146">To add System.Data.Linq.dll</span></span>  
  
1. <span data-ttu-id="d38fc-147">**ソリューションエクスプローラー**で、 **[すべてのファイルを表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-147">In **Solution Explorer**, click **Show All Files**.</span></span>  
  
2. <span data-ttu-id="d38fc-148">**ソリューションエクスプローラー**で、 **[参照]** を右クリックし、 **[参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
3. <span data-ttu-id="d38fc-149">**[参照の追加]** ダイアログボックスで **[.net]** をクリックし、system.string アセンブリをクリックして、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d38fc-150">アセンブリがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="d38fc-151">プロジェクトに Northwind コード ファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="d38fc-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="d38fc-152">この手順では、事前に SqlMetal ツールを使用して、Northwind サンプル データベースからコード ファイルを生成していることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="d38fc-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="d38fc-153">詳細については、このチュートリアルの「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="d38fc-154">プロジェクトに Northwind コード ファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="d38fc-154">To add the northwind code file to the project</span></span>  
  
1. <span data-ttu-id="d38fc-155">**[プロジェクト]** メニューの **[既存項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2. <span data-ttu-id="d38fc-156">**[既存項目の追加]** ダイアログボックスで、c:\linqtest3\northwind.vb に移動し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-156">In the **Add Existing Item** dialog box, move to c:\linqtest3\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="d38fc-157">プロジェクトに northwind.vb ファイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-157">The northwind.vb file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="d38fc-158">データベース接続を作成する</span><span class="sxs-lookup"><span data-stu-id="d38fc-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="d38fc-159">この手順では、Northwind サンプル データベースへの接続を定義します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="d38fc-160">このチュートリアルでは、パスとして "c:\linqtest3\northwnd.mdf" を使用します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-160">This walkthrough uses "c:\linqtest3\northwnd.mdf" as the path.</span></span>  
  
### <a name="to-create-the-database-connection"></a><span data-ttu-id="d38fc-161">データベース接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="d38fc-161">To create the database connection</span></span>  
  
1. <span data-ttu-id="d38fc-162">**ソリューションエクスプローラー**で、 **[form1.vb]** を右クリックし、 **[コードの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-162">In **Solution Explorer**, right-click **Form1.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="d38fc-163">コード エディターに `Class Form1` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-163">`Class Form1` appears in the code editor.</span></span>  
  
2. <span data-ttu-id="d38fc-164">`Form1` コード ブロックに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-164">Type the following code into the `Form1` code block:</span></span>  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="d38fc-165">ユーザー インターフェイスを設定する</span><span class="sxs-lookup"><span data-stu-id="d38fc-165">Setting up the User Interface</span></span>  
 <span data-ttu-id="d38fc-166">この手順では、ユーザーがストアド プロシージャを実行してデータベース内のデータにアクセスできるように、インターフェイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-166">In this task you create an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="d38fc-167">このチュートリアルで作成するアプリケーションでは、ユーザーはアプリケーションに埋め込まれているストアド プロシージャを使用してのみ、データベース内のデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-167">In the application that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="d38fc-168">ユーザー インターフェイスを設定するには</span><span class="sxs-lookup"><span data-stu-id="d38fc-168">To set up the user interface</span></span>  
  
1. <span data-ttu-id="d38fc-169">戻り値を Windows フォーム デザイナー (**form1.vb [デザイン]** )。</span><span class="sxs-lookup"><span data-stu-id="d38fc-169">Return to the Windows Forms Designer (**Form1.vb[Design]**).</span></span>  
  
2. <span data-ttu-id="d38fc-170">**[表示]** メニューの **[ツールボックス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-170">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="d38fc-171">ツールボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-171">The toolbox opens.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d38fc-172">**[自動的に隠す]** をクリックして、このセクションの残りの手順を実行しながら、ツールボックスを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-172">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3. <span data-ttu-id="d38fc-173">ツールボックスから**Form1**に2つのボタン、2つのテキストボックス、2つのラベルをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-173">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="d38fc-174">図のようにコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-174">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="d38fc-175">**[Form1]** を展開して、コントロールが簡単に見えるようにします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-175">Expand **Form1** so that the controls fit easily.</span></span>  
  
4. <span data-ttu-id="d38fc-176">**[Label1]** を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-176">Right-click **Label1**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="d38fc-177">**[Text]** プロパティを 「Label1 **」から「Enter OrderID:」** に変更します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-177">Change the **Text** property from **Label1** to **Enter OrderID:**.</span></span>  
  
6. <span data-ttu-id="d38fc-178">**Label2**の場合と同じように、 **Text**プロパティを**label2**から**CustomerID:** に変更します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-178">In the same way for **Label2**, change the **Text** property from **Label2** to **Enter CustomerID:**.</span></span>  
  
7. <span data-ttu-id="d38fc-179">同様に、 **Button1**の**Text**プロパティを**Order Details**に変更します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-179">In the same way, change the **Text** property for **Button1** to **Order Details**.</span></span>  
  
8. <span data-ttu-id="d38fc-180">**Button2**の**Text**プロパティを「 **Order History**」に変更します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-180">Change the **Text** property for **Button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="d38fc-181">すべてのテキストが表示されるように、ボタン コントロールの幅を広げます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-181">Widen the button controls so that all the text is visible.</span></span>  
  
### <a name="to-handle-button-clicks"></a><span data-ttu-id="d38fc-182">ボタン クリックを処理するには</span><span class="sxs-lookup"><span data-stu-id="d38fc-182">To handle button clicks</span></span>  
  
1. <span data-ttu-id="d38fc-183">**Form1**の`Button1` **[Order Details]** をダブルクリックしてイベントハンドラーを作成し、コードエディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-183">Double-click **Order Details** on **Form1** to create the `Button1` event handler and open the code editor.</span></span>  
  
2. <span data-ttu-id="d38fc-184">`Button1` のハンドラーに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-184">Type the following code into the `Button1` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. <span data-ttu-id="d38fc-185">ここで、Form1 の**Button2**をダブルクリックし`Button2`てイベントハンドラーを作成し、コードエディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-185">Now double-click **Button2** on Form1 to create the `Button2` event handler and open the code editor.</span></span>  
  
4. <span data-ttu-id="d38fc-186">`Button2` のハンドラーに次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-186">Type the following code into the `Button2` handler:</span></span>  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="d38fc-187">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="d38fc-187">Testing the Application</span></span>  
 <span data-ttu-id="d38fc-188">次に、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-188">Now it is time to test your application.</span></span> <span data-ttu-id="d38fc-189">データ ストアに対する操作は、2 つのストアド プロシージャで実行できる処理に制限されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d38fc-189">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="d38fc-190">つまり、入力した orderID に含まれている製品を返す処理と、入力した CustomerID の注文製品の履歴を返す処理のみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-190">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="d38fc-191">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="d38fc-191">To test the application</span></span>  
  
1. <span data-ttu-id="d38fc-192">F5 キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-192">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="d38fc-193">Form1 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-193">Form1 appears.</span></span>  
  
2. <span data-ttu-id="d38fc-194">**[OrderID の入力]** ボックスに「 **10249** 」と入力し、 **[Order Details]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-194">In the **Enter OrderID** box, type **10249** and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="d38fc-195">注文 10249 に含まれている製品がメッセージ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-195">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="d38fc-196">[ **OK]** をクリックして、メッセージボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-196">Click **OK** to close the message box.</span></span>  
  
3. <span data-ttu-id="d38fc-197">**[CustomerID の入力]** ボックスに`ALFKI`「」と入力し、 **[注文履歴]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-197">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="d38fc-198">メッセージ ボックスに、顧客 ALFKI の注文履歴が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-198">A message box lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="d38fc-199">[ **OK]** をクリックして、メッセージボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-199">Click **OK** to close the message box.</span></span>  
  
4. <span data-ttu-id="d38fc-200">**[OrderID の入力]** ボックスに`123`「」と入力し、 **[Order Details]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-200">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="d38fc-201">メッセージ ボックスに "No results" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-201">A message box displays "No results."</span></span>  
  
     <span data-ttu-id="d38fc-202">[ **OK]** をクリックして、メッセージボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-202">Click **OK** to close the message box.</span></span>  
  
5. <span data-ttu-id="d38fc-203">**[デバッグ]** メニューの **[デバッグの停止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d38fc-203">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="d38fc-204">デバッグ セッションが終了します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-204">The debug session closes.</span></span>  
  
6. <span data-ttu-id="d38fc-205">実験が終了したら、 **[ファイル]** メニューの **[プロジェクトを閉じる]** をクリックし、メッセージが表示されたらプロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="d38fc-205">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d38fc-206">次の手順</span><span class="sxs-lookup"><span data-stu-id="d38fc-206">Next Steps</span></span>  
 <span data-ttu-id="d38fc-207">いくつかの変更を加えることによって、このプロジェクトを強化できます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-207">You can enhance this project by making some changes.</span></span> <span data-ttu-id="d38fc-208">たとえば、使用できるストアド プロシージャの一覧をリスト ボックスに表示し、実行するプロシージャをユーザーに選択させることができます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-208">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="d38fc-209">レポートの出力をテキスト ファイルに送ることもできます。</span><span class="sxs-lookup"><span data-stu-id="d38fc-209">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38fc-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="d38fc-210">See also</span></span>

- [<span data-ttu-id="d38fc-211">チュートリアルによる学習</span><span class="sxs-lookup"><span data-stu-id="d38fc-211">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [<span data-ttu-id="d38fc-212">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="d38fc-212">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
