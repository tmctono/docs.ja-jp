---
title: 典型的な LINQ to SQL の使用手順
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: 26b88e4d45365bbaac986ce8751e1d3b5383909b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947004"
---
# <a name="typical-steps-for-using-linq-to-sql"></a><span data-ttu-id="bad9e-102">典型的な LINQ to SQL の使用手順</span><span class="sxs-lookup"><span data-stu-id="bad9e-102">Typical Steps for Using LINQ to SQL</span></span>
<span data-ttu-id="bad9e-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションを実装するには、このトピックで説明する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bad9e-103">To implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application, you follow the steps described later in this topic.</span></span> <span data-ttu-id="bad9e-104">多くの手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-104">Note that many steps are optional.</span></span> <span data-ttu-id="bad9e-105">既定の状態でオブジェクト モデルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-105">It is very possible that you can use your object model in its default state.</span></span>  
  
 <span data-ttu-id="bad9e-106">非常に高速に開始するには、オブジェクトリレーショナルデザイナーを使用してオブジェクトモデルを作成し、クエリのコーディングを開始します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-106">For a really fast start, use the Object Relational Designer to create your object model and start coding your queries.</span></span>  
  
## <a name="creating-the-object-model"></a><span data-ttu-id="bad9e-107">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="bad9e-107">Creating the Object Model</span></span>  
 <span data-ttu-id="bad9e-108">最初に、既存のリレーショナル データベースのメタデータからオブジェクト モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-108">The first step is to create an object model from the metadata of an existing relational database.</span></span> <span data-ttu-id="bad9e-109">オブジェクト モデルは、開発者のプログラミング言語に従ってデータベースを表します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-109">The object model represents the database according to the programming language of the developer.</span></span> <span data-ttu-id="bad9e-110">詳細については、「 [LINQ to SQL オブジェクトモデル](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-110">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
### <a name="1-select-a-tool-to-create-the-model"></a><span data-ttu-id="bad9e-111">1.モデルを作成するツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-111">1. Select a tool to create the model.</span></span>  
 <span data-ttu-id="bad9e-112">モデルを作成するツールとして、3 つのツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-112">Three tools are available for creating the model.</span></span>  
  
- <span data-ttu-id="bad9e-113">オブジェクトリレーショナルデザイナー</span><span class="sxs-lookup"><span data-stu-id="bad9e-113">The Object Relational Designer</span></span>  
  
     <span data-ttu-id="bad9e-114">このデザイナーは、既存のデータベースからモデルを作成する多機能なユーザー インターフェイスを備えています。</span><span class="sxs-lookup"><span data-stu-id="bad9e-114">This designer provides a rich user interface for creating an object model from an existing database.</span></span> <span data-ttu-id="bad9e-115">このツールは Visual Studio IDE の一部であり、小規模または中規模のデータベースに最適です。</span><span class="sxs-lookup"><span data-stu-id="bad9e-115">This tool is part of the Visual Studio IDE, and is best suited to small or medium databases.</span></span>  
  
- <span data-ttu-id="bad9e-116">SQLMetal コード生成ツール</span><span class="sxs-lookup"><span data-stu-id="bad9e-116">The SQLMetal code-generation tool</span></span>  
  
     <span data-ttu-id="bad9e-117">このコマンドラインユーティリティは、O/R デザイナーとは若干異なるオプションセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-117">This command-line utility provides a slightly different set of options from the O/R Designer.</span></span> <span data-ttu-id="bad9e-118">このツールは、大規模なデータベースのモデル化に適しています。</span><span class="sxs-lookup"><span data-stu-id="bad9e-118">Modeling large databases is best done by using this tool.</span></span> <span data-ttu-id="bad9e-119">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
- <span data-ttu-id="bad9e-120">コード エディター</span><span class="sxs-lookup"><span data-stu-id="bad9e-120">A code editor</span></span>  
  
     <span data-ttu-id="bad9e-121">Visual Studio コードエディターまたは別のエディターを使用して、独自のコードを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-121">You can write your own code by using either the Visual Studio code editor or another editor.</span></span> <span data-ttu-id="bad9e-122">この方法は、既存のデータベースがあり、O/R デザイナーまたは SQLMetal ツールを使用できる場合に、エラーが発生する可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bad9e-122">We do not recommend this approach, which can be prone to errors, when you have an existing database and can use either the O/R Designer or the SQLMetal tool.</span></span> <span data-ttu-id="bad9e-123">ただし、コード エディターは、他のツールを使用して既に生成されたコードを調整または変更する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-123">However, the code editor can be valuable for refining or modifying code you have already generated by using other tools.</span></span> <span data-ttu-id="bad9e-124">詳細については、「[方法 :コードエディター](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)を使用してエンティティクラスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="bad9e-124">For more information, see [How to: Customize Entity Classes by Using the Code Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md).</span></span>  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a><span data-ttu-id="bad9e-125">2.生成するコードの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-125">2. Select the kind of code you want to generate.</span></span>  
  
- <span data-ttu-id="bad9e-126">C#または Visual Basic 属性ベースのマッピング用のソースコードファイル。</span><span class="sxs-lookup"><span data-stu-id="bad9e-126">A C# or Visual Basic source code file for attribute-based mapping.</span></span>  
  
     <span data-ttu-id="bad9e-127">次に、このコードファイルを Visual Studio プロジェクトに含めます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-127">You then include this code file in your Visual Studio project.</span></span> <span data-ttu-id="bad9e-128">詳細については、「[属性ベースのマッピング](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-128">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="bad9e-129">外部マッピング用の XML ファイル。</span><span class="sxs-lookup"><span data-stu-id="bad9e-129">An XML file for external mapping.</span></span>  
  
     <span data-ttu-id="bad9e-130">この方法を使用すると、アプリケーション コードとは別にマッピング メタデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-130">By using this approach, you can keep the mapping metadata out of your application code.</span></span> <span data-ttu-id="bad9e-131">詳細については、「[外部マッピング](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-131">For more information, see [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="bad9e-132">O/R デザイナーは、外部マッピングファイルの生成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bad9e-132">The O/R Designer does not support the generation of external mapping files.</span></span> <span data-ttu-id="bad9e-133">SQLMetal ツールを使用してこの機能を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad9e-133">You must use the SQLMetal tool to implement this feature.</span></span>  
  
- <span data-ttu-id="bad9e-134">最終コード ファイルを生成する前に変更できる DBML ファイル。</span><span class="sxs-lookup"><span data-stu-id="bad9e-134">A DBML file, which you can modify before generating a final code file.</span></span>  
  
     <span data-ttu-id="bad9e-135">これは高度な機能です。</span><span class="sxs-lookup"><span data-stu-id="bad9e-135">This is an advanced feature.</span></span>  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a><span data-ttu-id="bad9e-136">3.コード ファイルを調整して、アプリケーションのニーズを反映します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-136">3. Refine the code file to reflect the needs of your application.</span></span>  
 <span data-ttu-id="bad9e-137">このためには、O/R デザイナーまたはコードエディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-137">For this purpose, you can use either the O/R Designer or the code editor.</span></span>  
  
## <a name="using-the-object-model"></a><span data-ttu-id="bad9e-138">オブジェクト モデルの使用</span><span class="sxs-lookup"><span data-stu-id="bad9e-138">Using the Object Model</span></span>  
 <span data-ttu-id="bad9e-139">2 層シナリオでの開発者とデータの関係を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-139">The following illustration shows the relationship between the developer and the data in a two-tier scenario.</span></span> <span data-ttu-id="bad9e-140">その他のシナリオについては、「 [LINQ to SQL を使用した N 層とリモートアプリケーション](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-140">For other scenarios, see [N-Tier and Remote Applications with LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).</span></span>  
  
 ![Linq オブジェクトモデルを示すスクリーンショット。](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 <span data-ttu-id="bad9e-142">オブジェクト モデルが完成したので、そのモデル内で情報要求を記述し、データを操作します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-142">Now that you have the object model, you describe information requests and manipulate data within that model.</span></span> <span data-ttu-id="bad9e-143">オブジェクト モデルのオブジェクトとプロパティを使用し、データベースの行と列は使用しません。</span><span class="sxs-lookup"><span data-stu-id="bad9e-143">You think in terms of the objects and properties in your object model and not in terms of the rows and columns of the database.</span></span> <span data-ttu-id="bad9e-144">データベースを直接操作することはありません。</span><span class="sxs-lookup"><span data-stu-id="bad9e-144">You do not deal directly with the database.</span></span>  
  
 <span data-ttu-id="bad9e-145">クエリを実行[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]するように指示した場合、または操作`SubmitChanges()`したデータに対してを[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]呼び出す場合、はデータベースの言語でデータベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-145">When you instruct [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to either execute a query that you have described or call `SubmitChanges()` on data that you have manipulated, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] communicates with the database in the language of the database.</span></span>  
  
 <span data-ttu-id="bad9e-146">作成したオブジェクト モデルの典型的な使用手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-146">The following represents typical steps for using the object model that you have created.</span></span>  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a><span data-ttu-id="bad9e-147">1.クエリを作成し、データベースから情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-147">1. Create queries to retrieve information from the database.</span></span>  
 <span data-ttu-id="bad9e-148">詳細については、「[クエリの概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)」および「[クエリの例](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-148">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) and [Query Examples](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).</span></span>  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a><span data-ttu-id="bad9e-149">2.挿入、更新、および削除の既定の動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="bad9e-149">2. Override default behaviors for Insert, Update, and Delete.</span></span>  
 <span data-ttu-id="bad9e-150">この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-150">This step is optional.</span></span> <span data-ttu-id="bad9e-151">詳細については、「[挿入、更新、および削除の操作をカスタマイズ](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-151">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a><span data-ttu-id="bad9e-152">3.適切なオプションを設定し、コンカレンシーの競合を検出およびレポートします。</span><span class="sxs-lookup"><span data-stu-id="bad9e-152">3. Set appropriate options to detect and report concurrency conflicts.</span></span>  
 <span data-ttu-id="bad9e-153">コンカレンシーの競合の処理について、モデルの既定値をそのまま使用することも、目的に合わせて変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-153">You can leave your model with its default values for handling concurrency conflicts, or you can change it to suit your purposes.</span></span> <span data-ttu-id="bad9e-154">詳細については、「[方法 :同時実行の競合](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)をテストするメンバーと、 [次の方法を指定します。同時実行例外をいつスロー](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-154">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) and [How to: Specify When Concurrency Exceptions are Thrown](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
### <a name="4-establish-an-inheritance-hierarchy"></a><span data-ttu-id="bad9e-155">4.継承階層を確立します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-155">4. Establish an inheritance hierarchy.</span></span>  
 <span data-ttu-id="bad9e-156">この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="bad9e-156">This step is optional.</span></span> <span data-ttu-id="bad9e-157">詳細については、「[継承のサポート](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-157">For more information, see [Inheritance Support](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).</span></span>  
  
### <a name="5-provide-an-appropriate-user-interface"></a><span data-ttu-id="bad9e-158">5.適切なユーザー インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bad9e-158">5. Provide an appropriate user interface.</span></span>  
 <span data-ttu-id="bad9e-159">この手順は省略でき、アプリケーションの使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="bad9e-159">This step is optional, and depends on how your application will be used.</span></span>  
  
### <a name="6-debug-and-test-your-application"></a><span data-ttu-id="bad9e-160">6.アプリケーションをデバッグおよびテストします。</span><span class="sxs-lookup"><span data-stu-id="bad9e-160">6. Debug and test your application.</span></span>  
 <span data-ttu-id="bad9e-161">詳細については、「[デバッグのサポート](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad9e-161">For more information, see [Debugging Support](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad9e-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="bad9e-162">See also</span></span>

- [<span data-ttu-id="bad9e-163">はじめに</span><span class="sxs-lookup"><span data-stu-id="bad9e-163">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
- [<span data-ttu-id="bad9e-164">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="bad9e-164">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="bad9e-165">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="bad9e-165">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
