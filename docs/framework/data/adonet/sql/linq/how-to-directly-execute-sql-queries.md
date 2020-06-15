---
title: '方法: SQL クエリを直接実行する'
description: ExecuteQuery を使用してクエリを実行し、LINQ to SQL クエリでは不十分な場合は、その結果を直接オブジェクトに変換する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 59bd404e41f6be1181d6a625c31ee23358db0df3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286366"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="b2179-103">方法: SQL クエリを直接実行する</span><span class="sxs-lookup"><span data-stu-id="b2179-103">How to: Directly Execute SQL Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b2179-104">は、作成したクエリをパラメーター化された SQL クエリ (テキスト形式) に変換し、それを SQL Server に送って処理します。</span><span class="sxs-lookup"><span data-stu-id="b2179-104">translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="b2179-105">アプリケーションでローカルに使用できるさまざまなメソッドの中には、SQL では実行できないものもあります。</span><span class="sxs-lookup"><span data-stu-id="b2179-105">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b2179-106">は、このようなローカル メソッドを、SQL 環境内で使用できる同等の操作や関数に変換しようとします。</span><span class="sxs-lookup"><span data-stu-id="b2179-106">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="b2179-107">.NET Framework の組み込み型に対するほとんどのメソッドと演算子には、SQL コマンドに直接対応する変換が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b2179-107">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="b2179-108">使用可能な関数から生成できるものもあります。</span><span class="sxs-lookup"><span data-stu-id="b2179-108">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="b2179-109">生成できないものについては、ランタイム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="b2179-109">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="b2179-110">詳しくは、「[SQL と CLR の型マッピング](sql-clr-type-mapping.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2179-110">For more information, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="b2179-111">特殊なタスクに対して [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリでは不十分な場合は、<xref:System.Data.Linq.DataContext.ExecuteQuery%2A> メソッドを使用して SQL クエリを実行し、そのクエリの結果をオブジェクトに直接変換できます。</span><span class="sxs-lookup"><span data-stu-id="b2179-111">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2179-112">例</span><span class="sxs-lookup"><span data-stu-id="b2179-112">Example</span></span>  
 <span data-ttu-id="b2179-113">次の例では、`Customer` クラスのデータが 2 つのテーブル (customer1 および customer2) にわたって格納されているものとします。</span><span class="sxs-lookup"><span data-stu-id="b2179-113">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="b2179-114">クエリは `Customer` オブジェクトのシーケンスを返します。</span><span class="sxs-lookup"><span data-stu-id="b2179-114">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="b2179-115">表形式の結果の列名がエンティティ クラスの列のプロパティと一致する限り、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] によって SQL クエリからオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b2179-115">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2179-116">例</span><span class="sxs-lookup"><span data-stu-id="b2179-116">Example</span></span>  
 <span data-ttu-id="b2179-117"><xref:System.Data.Linq.DataContext.ExecuteQuery%2A> メソッドは、パラメーターの使用にも対応しています。</span><span class="sxs-lookup"><span data-stu-id="b2179-117">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="b2179-118">パラメーター化されたクエリを実行するには、次のようなコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2179-118">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="b2179-119">クエリ テキスト内では、`Console.WriteLine()` および `String.Format()` で使用するのと同じ中かっこ表記を使用して、パラメーターを表現します。</span><span class="sxs-lookup"><span data-stu-id="b2179-119">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="b2179-120">実際には、指定したクエリ文字列について `String.Format()` が呼び出され、中かっこで囲まれたパラメーターは、生成された @p0、@p1、...、@p(n) のようなパラメーター名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="b2179-120">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2179-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2179-121">See also</span></span>

- [<span data-ttu-id="b2179-122">背景情報</span><span class="sxs-lookup"><span data-stu-id="b2179-122">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="b2179-123">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="b2179-123">Querying the Database</span></span>](querying-the-database.md)
