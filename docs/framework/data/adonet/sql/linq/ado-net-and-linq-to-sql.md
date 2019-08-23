---
title: ADO.NET および LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: b47a46f9fd9ef3ef1935fa7a88c2e60fe80db09d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964138"
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="37e20-102">ADO.NET および LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="37e20-102">ADO.NET and LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="37e20-103">は、ADO.NET のテクノロジファミリの一部です。</span><span class="sxs-lookup"><span data-stu-id="37e20-103">is part of the ADO.NET family of technologies.</span></span> <span data-ttu-id="37e20-104">これは、ADO.NET プロバイダーモデルによって提供されるサービスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="37e20-104">It is based on services provided by the ADO.NET provider model.</span></span> <span data-ttu-id="37e20-105">これにより、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]既存の ADO.NET アプリケーションとコードを組み合わせて、現在[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]の ADO.NET ソリューションをに移行できます。</span><span class="sxs-lookup"><span data-stu-id="37e20-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing ADO.NET applications and migrate current ADO.NET solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="37e20-106">次の図は、この関係を高いレベルから見たものです。</span><span class="sxs-lookup"><span data-stu-id="37e20-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="37e20-107">![LINQ to SQL と ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="37e20-107">![LINQ to SQL and ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="37e20-108">接続</span><span class="sxs-lookup"><span data-stu-id="37e20-108">Connections</span></span>  
 <span data-ttu-id="37e20-109">を作成するときに、既存の[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>ADO.NET 接続を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="37e20-109">You can supply an existing ADO.NET connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="37e20-110">に対するすべての<xref:System.Data.Linq.DataContext>操作 (クエリを含む) は、この指定された接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="37e20-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="37e20-111">接続が既に開いている[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]場合は、終了時にそのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="37e20-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="37e20-112">次のコードに示すとおり、<xref:System.Data.Linq.DataContext.Connection%2A> プロパティを使用して、いつでも接続にアクセスしたり、任意に閉じたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="37e20-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="37e20-113">トランザクション</span><span class="sxs-lookup"><span data-stu-id="37e20-113">Transactions</span></span>  
 <span data-ttu-id="37e20-114">既に独自のデータベース トランザクションを初期化していて、<xref:System.Data.Linq.DataContext> をトランザクションに使用する必要がある場合は、<xref:System.Data.Linq.DataContext> をトランザクションに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="37e20-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="37e20-115">.NET Framework でトランザクションを実行する場合は、 <xref:System.Transactions.TransactionScope>オブジェクトを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37e20-115">The preferred method of doing transactions with the .NET Framework is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="37e20-116">この方法を使うと、データベースと他のメモリ常駐リソース マネージャー間で動作する分散トランザクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="37e20-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="37e20-117">トランザクション スコープは、わずかなリソースで開始されます。</span><span class="sxs-lookup"><span data-stu-id="37e20-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="37e20-118">トランザクションのスコープ内に複数の接続がある場合のみ、このトランザクションは分散トランザクションに昇格します。</span><span class="sxs-lookup"><span data-stu-id="37e20-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="37e20-119">この方法は、すべてのデータベースに使用できるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="37e20-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="37e20-120">たとえば、SqlClient 接続では、SQL Server 2000 サーバーに対して動作する場合、システムトランザクションを昇格させることはできません。</span><span class="sxs-lookup"><span data-stu-id="37e20-120">For example, the SqlClient connection cannot promote system transactions when it works against a SQL Server 2000 server.</span></span> <span data-ttu-id="37e20-121">代わりに、トランザクション スコープが使用されているときは、完全な分散トランザクションに自動的に参加します。</span><span class="sxs-lookup"><span data-stu-id="37e20-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="37e20-122">直接 SQL コマンド</span><span class="sxs-lookup"><span data-stu-id="37e20-122">Direct SQL Commands</span></span>  
 <span data-ttu-id="37e20-123">ときには、クエリを実行したり変更内容を送信したりする <xref:System.Data.Linq.DataContext> 機能に不足があり、実行する必要がある特別なタスクを完了できないこともあります。</span><span class="sxs-lookup"><span data-stu-id="37e20-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="37e20-124">このような場合は、<xref:System.Data.Linq.DataContext.ExecuteQuery%2A> メソッドを使用して、SQL コマンドをデータベースに発行し、クエリ結果をオブジェクトに変換することができます。</span><span class="sxs-lookup"><span data-stu-id="37e20-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="37e20-125">たとえば、`Customer` クラスのデータが 2 つのテーブル (customer1 および customer2) に含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="37e20-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="37e20-126">次のクエリは `Customer` オブジェクトのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="37e20-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="37e20-127">表形式の結果の列名がエンティティクラスの列のプロパティと一致する限り[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 、は SQL クエリからオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="37e20-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="37e20-128">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37e20-128">Parameters</span></span>  
 <span data-ttu-id="37e20-129"><xref:System.Data.Linq.DataContext.ExecuteQuery%2A> メソッドは、パラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="37e20-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="37e20-130">次のコードでは、パラメーター化されたクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="37e20-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="37e20-131">パラメーターは、`Console.WriteLine()` および `String.Format()` で使用されるものと同じ中かっこ表記でクエリ テキストに表現されます。</span><span class="sxs-lookup"><span data-stu-id="37e20-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="37e20-132">`String.Format()` は、指定されたクエリ文字列を受け取り、中かっこで囲まれたパラメーターを、`@p0`、`@p1` …、`@p(n)` などの、生成されたパラメーター名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="37e20-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37e20-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="37e20-133">See also</span></span>

- [<span data-ttu-id="37e20-134">背景情報</span><span class="sxs-lookup"><span data-stu-id="37e20-134">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="37e20-135">方法: ADO.NET コマンドと DataContext の間の接続を再利用する</span><span class="sxs-lookup"><span data-stu-id="37e20-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
