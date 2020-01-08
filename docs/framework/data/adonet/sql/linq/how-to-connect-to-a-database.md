---
title: '方法 : データベースに接続する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: 837919b1cfcdf46026ccfb37cbbec951c0ae41b8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634678"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="c7388-102">方法 : データベースに接続する</span><span class="sxs-lookup"><span data-stu-id="c7388-102">How to: Connect to a Database</span></span>
<span data-ttu-id="c7388-103">データベースへの接続、データベースからのオブジェクトの取得、およびデータベースへの変更内容の反映では、<xref:System.Data.Linq.DataContext> を仲介役として使用します。</span><span class="sxs-lookup"><span data-stu-id="c7388-103">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="c7388-104">この <xref:System.Data.Linq.DataContext> は、ADO.NET <xref:System.Data.SqlClient.SqlConnection>を使用するのと同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="c7388-104">You use the <xref:System.Data.Linq.DataContext> just as you would use an ADO.NET <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="c7388-105">つまり、接続または接続文字列を指定して、<xref:System.Data.Linq.DataContext> を初期化します。</span><span class="sxs-lookup"><span data-stu-id="c7388-105">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="c7388-106">詳細については、「 [DataContext メソッド (O/R デザイナー)](/visualstudio/data-tools/datacontext-methods-o-r-designer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7388-106">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="c7388-107"><xref:System.Data.Linq.DataContext> の役割は、オブジェクトを求める要求を、データベースに対して発行する SQL クエリに変換し、その結果からオブジェクトを組み立てることです。</span><span class="sxs-lookup"><span data-stu-id="c7388-107">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="c7388-108"><xref:System.Data.Linq.DataContext> は、`Where` や `Select`などの標準クエリ演算子と同じ演算子パターンを実装することによって、統合言語クエリ (LINQ) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c7388-108">The <xref:System.Data.Linq.DataContext> enables Language-Integrated Query (LINQ) by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c7388-109">セキュリティで保護された接続を確立することは、最も重要です。</span><span class="sxs-lookup"><span data-stu-id="c7388-109">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="c7388-110">詳細については、「 [LINQ to SQL のセキュリティ](security-in-linq-to-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7388-110">For more information, see [Security in LINQ to SQL](security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7388-111">使用例</span><span class="sxs-lookup"><span data-stu-id="c7388-111">Example</span></span>  
 <span data-ttu-id="c7388-112">次の例では、<xref:System.Data.Linq.DataContext> を使用して、Northwind サンプル データベースに接続し、市が London である顧客の行を取得しています。</span><span class="sxs-lookup"><span data-stu-id="c7388-112">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="c7388-113">各データベース テーブルは `Table` コレクションとして表され、テーブルを識別するエンティティ クラスを使用して <xref:System.Data.Linq.DataContext.GetTable%2A> メソッドでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c7388-113">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7388-114">使用例</span><span class="sxs-lookup"><span data-stu-id="c7388-114">Example</span></span>  
 <span data-ttu-id="c7388-115">基本的な <xref:System.Data.Linq.DataContext> クラスおよび <xref:System.Data.Linq.DataContext> メソッドを使用するのではなく、厳密に型指定された <xref:System.Data.Linq.DataContext.GetTable%2A> を宣言するのがベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="c7388-115">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="c7388-116">厳密に型指定された <xref:System.Data.Linq.DataContext> では、次の例のように、すべての `Table` コレクションをそのコンテキストのメンバーとして宣言します。</span><span class="sxs-lookup"><span data-stu-id="c7388-116">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="c7388-117">この場合、London の顧客を取得するクエリは、次のように簡単に表せます。</span><span class="sxs-lookup"><span data-stu-id="c7388-117">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c7388-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7388-118">See also</span></span>

- [<span data-ttu-id="c7388-119">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="c7388-119">Communicating with the Database</span></span>](communicating-with-the-database.md)
