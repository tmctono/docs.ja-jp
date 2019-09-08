---
title: 'チュートリアル: リレーションシップを介したクエリの実行 (C#)'
ms.date: 03/30/2017
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
ms.openlocfilehash: ebf96bc575ef68e1190c5b9be7111902c0f69fef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780990"
---
# <a name="walkthrough-querying-across-relationships-c"></a><span data-ttu-id="f9c74-102">チュートリアル: リレーションシップを介したクエリの実行 (C#)</span><span class="sxs-lookup"><span data-stu-id="f9c74-102">Walkthrough: Querying Across Relationships (C#)</span></span>
<span data-ttu-id="f9c74-103">このチュートリアルでは、データベース[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]内の外部キーリレーションシップを表すための*関連付け*の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="f9c74-104">このチュートリアルは、Visual C# 開発設定を使用して記述されています。</span><span class="sxs-lookup"><span data-stu-id="f9c74-104">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f9c74-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f9c74-105">Prerequisites</span></span>  
 <span data-ttu-id="f9c74-106">チュートリアルを完了し[ている必要があります。単純なオブジェクトモデルとクエリC#(](walkthrough-simple-object-model-and-query-csharp.md))。</span><span class="sxs-lookup"><span data-stu-id="f9c74-106">You must have completed [Walkthrough: Simple Object Model and Query (C#)](walkthrough-simple-object-model-and-query-csharp.md).</span></span> <span data-ttu-id="f9c74-107">このチュートリアルは前のチュートリアルに基づいて作成されており、c:\linqtest5 に northwnd.mdf ファイルがあることが前提です。</span><span class="sxs-lookup"><span data-stu-id="f9c74-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest5.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f9c74-108">概要</span><span class="sxs-lookup"><span data-stu-id="f9c74-108">Overview</span></span>  
 <span data-ttu-id="f9c74-109">このチュートリアルは、主に次の 3 つの手順で構成されています。</span><span class="sxs-lookup"><span data-stu-id="f9c74-109">This walkthrough consists of three main tasks:</span></span>  
  
- <span data-ttu-id="f9c74-110">エンティティ クラスを追加して、Northwind サンプル データベース内の Orders テーブルを表します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
- <span data-ttu-id="f9c74-111">`Customer` クラスに注釈を付けて、`Customer` クラスと `Order` クラス間のリレーションシップを強化します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
- <span data-ttu-id="f9c74-112">クエリを作成および実行して、`Order` クラスによる `Customer` 情報の取得をテストします。</span><span class="sxs-lookup"><span data-stu-id="f9c74-112">Creating and running a query to test obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="f9c74-113">テーブル間のリレーションシップを指定する</span><span class="sxs-lookup"><span data-stu-id="f9c74-113">Mapping Relationships Across Tables</span></span>  
 <span data-ttu-id="f9c74-114">`Customer` クラス定義の後に、次のコードから成る `Order` エンティティ クラス定義を作成します。これは、`Order.Customer` が外部キーとして `Customer.CustomerID` に関係することを示しています。</span><span class="sxs-lookup"><span data-stu-id="f9c74-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Order.Customer` relates as a foreign key to `Customer.CustomerID`.</span></span>  
  
### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="f9c74-115">Order エンティティ クラスを追加するには</span><span class="sxs-lookup"><span data-stu-id="f9c74-115">To add the Order entity class</span></span>  
  
- <span data-ttu-id="f9c74-116">`Customer` クラスの後に次のコードを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f9c74-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="f9c74-117">Customer クラスに注釈を付ける</span><span class="sxs-lookup"><span data-stu-id="f9c74-117">Annotating the Customer Class</span></span>  
 <span data-ttu-id="f9c74-118">ここでは、`Customer` クラスに注釈を付けて、`Order` クラスとのリレーションシップを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="f9c74-119">いずれかの方向のリレーションシップが定義されていればリンクを作成できるため、この注釈の追加は必ずしも必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="f9c74-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="f9c74-120">しかし、この注釈を追加することで、どちらの方向でも簡単にオブジェクトを移動できます。</span><span class="sxs-lookup"><span data-stu-id="f9c74-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="f9c74-121">Customer クラスに注釈を付けるには</span><span class="sxs-lookup"><span data-stu-id="f9c74-121">To annotate the Customer class</span></span>  
  
- <span data-ttu-id="f9c74-122">`Customer` クラスに次のコードを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f9c74-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="f9c74-123">Customer-Order リレーションシップ間のクエリを作成および実行する</span><span class="sxs-lookup"><span data-stu-id="f9c74-123">Creating and Running a Query Across the Customer-Order Relationship</span></span>  
 <span data-ttu-id="f9c74-124">`Order` オブジェクトから `Customer` オブジェクトに、またはその逆の順序で、直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f9c74-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="f9c74-125">顧客と注文の間に明示的な*結合*は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f9c74-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="f9c74-126">Customer オブジェクトを使用して Order オブジェクトにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="f9c74-126">To access Order objects by using Customer objects</span></span>  
  
1. <span data-ttu-id="f9c74-127">`Main` メソッドに次のコードを入力または貼り付けることによって、メソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-127">Modify the `Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2. <span data-ttu-id="f9c74-128">F5 キーを押して、アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="f9c74-128">Press F5 to debug your application.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f9c74-129">`db.Log = Console.Out;` をコメント アウトすることによって、コンソール ウィンドウ内の SQL コードを除去できます。</span><span class="sxs-lookup"><span data-stu-id="f9c74-129">You can eliminate the SQL code in the Console window by commenting out `db.Log = Console.Out;`.</span></span>  
  
3. <span data-ttu-id="f9c74-130">コンソール ウィンドウで Enter キーを押して、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-130">Press Enter in the Console window to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="f9c74-131">データベースの厳密に型指定されたビューを作成する</span><span class="sxs-lookup"><span data-stu-id="f9c74-131">Creating a Strongly Typed View of Your Database</span></span>  
 <span data-ttu-id="f9c74-132">データベースの厳密に型指定されたビューを使用すると、操作が非常に簡単になります。</span><span class="sxs-lookup"><span data-stu-id="f9c74-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="f9c74-133"><xref:System.Data.Linq.DataContext> オブジェクトを厳密に型指定することによって、<xref:System.Data.Linq.DataContext.GetTable%2A> を呼び出す必要がありません。</span><span class="sxs-lookup"><span data-stu-id="f9c74-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="f9c74-134">厳密に型指定された <xref:System.Data.Linq.DataContext> オブジェクトを使用する場合は、すべてのクエリで、厳密に型指定されたテーブルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9c74-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="f9c74-135">次の手順では、データベース内の Customers テーブルに対応する厳密に型指定されたテーブルとして、`Customers` を作成します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="f9c74-136">DataContext オブジェクトを厳密に型指定するには</span><span class="sxs-lookup"><span data-stu-id="f9c74-136">To strongly type the DataContext object</span></span>  
  
1. <span data-ttu-id="f9c74-137">`Customer` クラス宣言の上に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2. <span data-ttu-id="f9c74-138">`Main` メソッドを次のように変更し、厳密に型指定された <xref:System.Data.Linq.DataContext> を使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="f9c74-138">Modify the `Main` method to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3. <span data-ttu-id="f9c74-139">F5 キーを押して、アプリケーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="f9c74-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="f9c74-140">コンソール ウィンドウの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f9c74-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4. <span data-ttu-id="f9c74-141">コンソール ウィンドウで Enter キーを押して、デバッグを停止します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-141">Press Enter in the console window to stop debugging.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f9c74-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="f9c74-142">Next Steps</span></span>  
 <span data-ttu-id="f9c74-143">次のチュートリアル ([チュートリアル:データの操作C#(](walkthrough-manipulating-data-csharp.md)): データを操作する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f9c74-143">The next walkthrough ([Walkthrough: Manipulating Data (C#)](walkthrough-manipulating-data-csharp.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="f9c74-144">そのチュートリアルを実行するのに、既に終了したこのシリーズの 2 つのチュートリアルを保存する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f9c74-144">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c74-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9c74-145">See also</span></span>

- [<span data-ttu-id="f9c74-146">チュートリアルによる学習</span><span class="sxs-lookup"><span data-stu-id="f9c74-146">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
