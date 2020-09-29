---
title: 典型的な LINQ to SQL の使用手順
ms.date: 03/30/2017
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
ms.openlocfilehash: dc8c4be1e895ee5c4c7947e6311e5bf71008490f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164261"
---
# <a name="typical-steps-for-using-linq-to-sql"></a><span data-ttu-id="a1a6e-102">典型的な LINQ to SQL の使用手順</span><span class="sxs-lookup"><span data-stu-id="a1a6e-102">Typical Steps for Using LINQ to SQL</span></span>

<span data-ttu-id="a1a6e-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションを実装するには、このトピックで説明する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-103">To implement a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] application, you follow the steps described later in this topic.</span></span> <span data-ttu-id="a1a6e-104">多くの手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-104">Note that many steps are optional.</span></span> <span data-ttu-id="a1a6e-105">既定の状態でオブジェクト モデルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-105">It is very possible that you can use your object model in its default state.</span></span>  
  
 <span data-ttu-id="a1a6e-106">オブジェクト リレーショナル デザイナーを使用してオブジェクト モデルを作成し、クエリのコーディングを開始すると、非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-106">For a really fast start, use the Object Relational Designer to create your object model and start coding your queries.</span></span>  
  
## <a name="creating-the-object-model"></a><span data-ttu-id="a1a6e-107">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="a1a6e-107">Creating the Object Model</span></span>  

 <span data-ttu-id="a1a6e-108">最初に、既存のリレーショナル データベースのメタデータからオブジェクト モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-108">The first step is to create an object model from the metadata of an existing relational database.</span></span> <span data-ttu-id="a1a6e-109">オブジェクト モデルは、開発者のプログラミング言語に従ってデータベースを表します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-109">The object model represents the database according to the programming language of the developer.</span></span> <span data-ttu-id="a1a6e-110">詳しくは、「[LINQ to SQL オブジェクト モデル](the-linq-to-sql-object-model.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-110">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
### <a name="1-select-a-tool-to-create-the-model"></a><span data-ttu-id="a1a6e-111">1.モデルを作成するツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-111">1. Select a tool to create the model.</span></span>  

 <span data-ttu-id="a1a6e-112">モデルを作成するツールとして、3 つのツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-112">Three tools are available for creating the model.</span></span>  
  
- <span data-ttu-id="a1a6e-113">オブジェクト リレーショナル デザイナー</span><span class="sxs-lookup"><span data-stu-id="a1a6e-113">The Object Relational Designer</span></span>  
  
     <span data-ttu-id="a1a6e-114">このデザイナーは、既存のデータベースからモデルを作成する多機能なユーザー インターフェイスを備えています。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-114">This designer provides a rich user interface for creating an object model from an existing database.</span></span> <span data-ttu-id="a1a6e-115">このツールは Visual Studio IDE の一部であり、小規模または中規模のデータベースに最適です。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-115">This tool is part of the Visual Studio IDE, and is best suited to small or medium databases.</span></span>  
  
- <span data-ttu-id="a1a6e-116">SQLMetal コード生成ツール</span><span class="sxs-lookup"><span data-stu-id="a1a6e-116">The SQLMetal code-generation tool</span></span>  
  
     <span data-ttu-id="a1a6e-117">このコマンド ライン ユーティリティは、O/R デザイナーと多少異なるオプション セットを備えています。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-117">This command-line utility provides a slightly different set of options from the O/R Designer.</span></span> <span data-ttu-id="a1a6e-118">このツールは、大規模なデータベースのモデル化に適しています。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-118">Modeling large databases is best done by using this tool.</span></span> <span data-ttu-id="a1a6e-119">詳しくは、「[SqlMetal.exe (コード生成ツール)](../../../../tools/sqlmetal-exe-code-generation-tool.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-119">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
- <span data-ttu-id="a1a6e-120">コード エディター</span><span class="sxs-lookup"><span data-stu-id="a1a6e-120">A code editor</span></span>  
  
     <span data-ttu-id="a1a6e-121">Visual Studio のコード エディターまたは他のエディターを使用して、独自のコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-121">You can write your own code by using either the Visual Studio code editor or another editor.</span></span> <span data-ttu-id="a1a6e-122">既存のデータベースがあり、O/R デザイナーまたは SQLMetal ツールを使用できる場合は、この方法はエラーを発生する可能性が高いため、その使用はお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-122">We do not recommend this approach, which can be prone to errors, when you have an existing database and can use either the O/R Designer or the SQLMetal tool.</span></span> <span data-ttu-id="a1a6e-123">ただし、コード エディターは、他のツールを使用して既に生成されたコードを調整または変更する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-123">However, the code editor can be valuable for refining or modifying code you have already generated by using other tools.</span></span> <span data-ttu-id="a1a6e-124">詳細については、[コード エディターを使用してエンティティ クラスをカスタマイズする](how-to-customize-entity-classes-by-using-the-code-editor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-124">For more information, see [How to: Customize Entity Classes by Using the Code Editor](how-to-customize-entity-classes-by-using-the-code-editor.md).</span></span>  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a><span data-ttu-id="a1a6e-125">2.生成するコードの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-125">2. Select the kind of code you want to generate.</span></span>  
  
- <span data-ttu-id="a1a6e-126">属性ベースの対応付け用の C# または Visual Basic のソース コード ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-126">A C# or Visual Basic source code file for attribute-based mapping.</span></span>  
  
     <span data-ttu-id="a1a6e-127">このコード ファイルを、Visual Studio プロジェクトに含めます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-127">You then include this code file in your Visual Studio project.</span></span> <span data-ttu-id="a1a6e-128">詳しくは、「[属性ベースの対応付け](attribute-based-mapping.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-128">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="a1a6e-129">外部マッピング用の XML ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-129">An XML file for external mapping.</span></span>  
  
     <span data-ttu-id="a1a6e-130">この方法を使用すると、アプリケーション コードとは別にマッピング メタデータを保持できます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-130">By using this approach, you can keep the mapping metadata out of your application code.</span></span> <span data-ttu-id="a1a6e-131">詳細については、「[外部マップ](external-mapping.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-131">For more information, see [External Mapping](external-mapping.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a1a6e-132">O/R デザイナーでは、外部マッピング ファイルの生成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-132">The O/R Designer does not support the generation of external mapping files.</span></span> <span data-ttu-id="a1a6e-133">SQLMetal ツールを使用してこの機能を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-133">You must use the SQLMetal tool to implement this feature.</span></span>  
  
- <span data-ttu-id="a1a6e-134">最終コード ファイルを生成する前に変更できる DBML ファイル。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-134">A DBML file, which you can modify before generating a final code file.</span></span>  
  
     <span data-ttu-id="a1a6e-135">これは高度な機能です。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-135">This is an advanced feature.</span></span>  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a><span data-ttu-id="a1a6e-136">3.コード ファイルを調整して、アプリケーションのニーズを反映します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-136">3. Refine the code file to reflect the needs of your application.</span></span>  

 <span data-ttu-id="a1a6e-137">この目的には、O/R デザイナーまたはコード エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-137">For this purpose, you can use either the O/R Designer or the code editor.</span></span>  
  
## <a name="using-the-object-model"></a><span data-ttu-id="a1a6e-138">オブジェクト モデルの使用</span><span class="sxs-lookup"><span data-stu-id="a1a6e-138">Using the Object Model</span></span>  

 <span data-ttu-id="a1a6e-139">2 層シナリオでの開発者とデータの関係を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-139">The following illustration shows the relationship between the developer and the data in a two-tier scenario.</span></span> <span data-ttu-id="a1a6e-140">その他のシナリオについては、「[LINQ to SQL での N 層およびリモート アプリケーション](n-tier-and-remote-applications-with-linq-to-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-140">For other scenarios, see [N-Tier and Remote Applications with LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md).</span></span>  
  
 ![Linq オブジェクト モデルを示すスクリーンショット。](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 <span data-ttu-id="a1a6e-142">オブジェクト モデルが完成したので、そのモデル内で情報要求を記述し、データを操作します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-142">Now that you have the object model, you describe information requests and manipulate data within that model.</span></span> <span data-ttu-id="a1a6e-143">オブジェクト モデルのオブジェクトとプロパティを使用し、データベースの行と列は使用しません。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-143">You think in terms of the objects and properties in your object model and not in terms of the rows and columns of the database.</span></span> <span data-ttu-id="a1a6e-144">データベースを直接操作することはありません。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-144">You do not deal directly with the database.</span></span>  
  
 <span data-ttu-id="a1a6e-145">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に対して、記述したクエリの実行、または操作したデータに対する `SubmitChanges()` の呼び出しを指示すると、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、データベースの言語でデータベースとの通信が行われます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-145">When you instruct [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to either execute a query that you have described or call `SubmitChanges()` on data that you have manipulated, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] communicates with the database in the language of the database.</span></span>  
  
 <span data-ttu-id="a1a6e-146">作成したオブジェクト モデルの典型的な使用手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-146">The following represents typical steps for using the object model that you have created.</span></span>  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a><span data-ttu-id="a1a6e-147">1.クエリを作成し、データベースから情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-147">1. Create queries to retrieve information from the database.</span></span>  

 <span data-ttu-id="a1a6e-148">詳しくは、「[クエリの概念](query-concepts.md)」と「[クエリの例](query-examples.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-148">For more information, see [Query Concepts](query-concepts.md) and [Query Examples](query-examples.md).</span></span>  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a><span data-ttu-id="a1a6e-149">2.挿入、更新、および削除の既定の動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-149">2. Override default behaviors for Insert, Update, and Delete.</span></span>  

 <span data-ttu-id="a1a6e-150">この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-150">This step is optional.</span></span> <span data-ttu-id="a1a6e-151">詳細については、「[挿入、更新、および削除の各操作のカスタマイズ](customizing-insert-update-and-delete-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-151">For more information, see [Customizing Insert, Update, and Delete Operations](customizing-insert-update-and-delete-operations.md).</span></span>  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a><span data-ttu-id="a1a6e-152">3.適切なオプションを設定し、コンカレンシーの競合を検出およびレポートします。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-152">3. Set appropriate options to detect and report concurrency conflicts.</span></span>  

 <span data-ttu-id="a1a6e-153">コンカレンシーの競合の処理について、モデルの既定値をそのまま使用することも、目的に合わせて変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-153">You can leave your model with its default values for handling concurrency conflicts, or you can change it to suit your purposes.</span></span> <span data-ttu-id="a1a6e-154">詳細については、[コンカレンシーの競合を検査するメンバーを指定する](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)」および「[方法: コンカレンシー例外をいつスローするかを指定する](how-to-specify-when-concurrency-exceptions-are-thrown.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-154">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) and [How to: Specify When Concurrency Exceptions are Thrown](how-to-specify-when-concurrency-exceptions-are-thrown.md).</span></span>  
  
### <a name="4-establish-an-inheritance-hierarchy"></a><span data-ttu-id="a1a6e-155">4.継承階層を確立します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-155">4. Establish an inheritance hierarchy.</span></span>  

 <span data-ttu-id="a1a6e-156">この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-156">This step is optional.</span></span> <span data-ttu-id="a1a6e-157">詳細については、「[継承のサポート](inheritance-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-157">For more information, see [Inheritance Support](inheritance-support.md).</span></span>  
  
### <a name="5-provide-an-appropriate-user-interface"></a><span data-ttu-id="a1a6e-158">5.適切なユーザー インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-158">5. Provide an appropriate user interface.</span></span>  

 <span data-ttu-id="a1a6e-159">この手順は省略でき、アプリケーションの使用方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-159">This step is optional, and depends on how your application will be used.</span></span>  
  
### <a name="6-debug-and-test-your-application"></a><span data-ttu-id="a1a6e-160">6.アプリケーションをデバッグおよびテストします。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-160">6. Debug and test your application.</span></span>  

 <span data-ttu-id="a1a6e-161">詳しくは、「[デバッグのサポート](debugging-support.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-161">For more information, see [Debugging Support](debugging-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a6e-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1a6e-162">See also</span></span>

- [<span data-ttu-id="a1a6e-163">はじめに</span><span class="sxs-lookup"><span data-stu-id="a1a6e-163">Getting Started</span></span>](getting-started.md)
- [<span data-ttu-id="a1a6e-164">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="a1a6e-164">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="a1a6e-165">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="a1a6e-165">Stored Procedures</span></span>](stored-procedures.md)
