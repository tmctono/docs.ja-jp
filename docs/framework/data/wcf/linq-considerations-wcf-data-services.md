---
title: LINQ に関する留意点 (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ
- querying the data service [WCF Data Services]
- WCF Data Services, querying
ms.assetid: cc4ec9e9-348f-42a6-a78e-1cd40e370656
ms.openlocfilehash: f8ec53323abec7077c69f50fe522338228ceddbb
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116637"
---
# <a name="linq-considerations-wcf-data-services"></a><span data-ttu-id="ea333-102">LINQ に関する留意点 (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="ea333-102">LINQ Considerations (WCF Data Services)</span></span>
<span data-ttu-id="ea333-103">このトピックでは、WCF Data Services クライアントを使用しているときに LINQ クエリを作成および実行する方法について説明します。また、LINQ を使用して Open Data Protocol (OData) を実装するデータサービスを照会する場合の制限事項についても説明します。</span><span class="sxs-lookup"><span data-stu-id="ea333-103">This topic provides information about the way in which LINQ queries are composed and executed when you are using the WCF Data Services client and limitations of using LINQ to query a data service that implements the Open Data Protocol (OData).</span></span> <span data-ttu-id="ea333-104">OData ベースのデータサービスに対するクエリの作成と実行の詳細については、「[データサービスのクエリ](querying-the-data-service-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea333-104">For more information about composing and executing queries against an OData-based data service, see [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
## <a name="composing-linq-queries"></a><span data-ttu-id="ea333-105">LINQ クエリの作成</span><span class="sxs-lookup"><span data-stu-id="ea333-105">Composing LINQ Queries</span></span>  
 <span data-ttu-id="ea333-106">LINQ を使用すると、<xref:System.Collections.Generic.IEnumerable%601> を実装するオブジェクトのコレクションに対するクエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ea333-106">LINQ enables you to compose queries against a collection of objects that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="ea333-107">Visual Studio の **[サービス参照の追加]** ダイアログボックスと datasvcutil.exe ツールを使用して、OData サービスの表現を、<xref:System.Data.Services.Client.DataServiceContext>から継承するエンティティコンテナークラスとして、およびフィードで返されるエンティティを表すオブジェクトとして生成します。</span><span class="sxs-lookup"><span data-stu-id="ea333-107">Both the **Add Service Reference** dialog box in Visual Studio and the DataSvcUtil.exe tool are used to generate a representation of an OData service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>, as well as objects that represent the entities returned in feeds.</span></span> <span data-ttu-id="ea333-108">これらのツールでは、サービスによってフィードとして公開されるコレクションに対応するエンティティ コンテナー クラスのプロパティも生成されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-108">These tools also generate properties on the entity container class for the collections that are exposed as feeds by the service.</span></span> <span data-ttu-id="ea333-109">データ サービスをカプセル化するクラスのこれらのプロパティは、それぞれ <xref:System.Data.Services.Client.DataServiceQuery%601> を返します。</span><span class="sxs-lookup"><span data-stu-id="ea333-109">Each of these properties of the class that encapsulates the data service return a <xref:System.Data.Services.Client.DataServiceQuery%601>.</span></span> <span data-ttu-id="ea333-110"><xref:System.Data.Services.Client.DataServiceQuery%601> クラスは LINQ で定義された <xref:System.Linq.IQueryable%601> インターフェイスを実装するので、データ サービスによって公開されるフィードに対する LINQ クエリを作成できます。作成した LINQ クエリは、クライアント ライブラリにより、実行時にデータ サービスに送信されるクエリ要求 URI に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-110">Because the <xref:System.Data.Services.Client.DataServiceQuery%601> class implements the <xref:System.Linq.IQueryable%601> interface defined by LINQ, you can compose a LINQ query against feeds exposed by the data service, which are translated by the client library into a query request URI that is sent to the data service on execution.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ea333-111">LINQ 構文で表現できるクエリのセットは、OData データサービスで使用される URI 構文で有効になっているものよりも大きくなります。</span><span class="sxs-lookup"><span data-stu-id="ea333-111">The set of queries expressible in the LINQ syntax is broader than those enabled in the URI syntax that is used by OData data services.</span></span> <span data-ttu-id="ea333-112">クエリを対象データ サービスの URI にマップできない場合、<xref:System.NotSupportedException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="ea333-112">A <xref:System.NotSupportedException> is raised when the query cannot be mapped to a URI in the target data service.</span></span> <span data-ttu-id="ea333-113">詳細については、このトピックの「サポートされて[いない LINQ メソッド](linq-considerations-wcf-data-services.md#unsupportedMethods)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea333-113">For more information, see the [Unsupported LINQ Methods](linq-considerations-wcf-data-services.md#unsupportedMethods) in this topic.</span></span>  
  
 <span data-ttu-id="ea333-114">次の例の LINQ クエリは、輸送費が 30 ドルを超える `Orders` を取得し、結果を出荷日の新しい順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="ea333-114">The following example is a LINQ query that returns `Orders` that have a freight cost of more than $30 and sorts the results by the shipping date, starting with the latest ship date:</span></span>  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqspecific)]    
  
 <span data-ttu-id="ea333-115">この LINQ クエリは、Northwind ベースの[クイックスタート](quickstart-wcf-data-services.md)データサービスに対して実行される次のクエリ URI に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-115">This LINQ query is translated into the following query URI that is executed against the Northwind-based [quickstart](quickstart-wcf-data-services.md) data service:</span></span>  
  
```http
http://localhost:12345/Northwind.svc/Orders?Orderby=ShippedDate&?filter=Freight gt 30  
```  
  
 <span data-ttu-id="ea333-116">Linq の一般的な情報については、「[統合言語クエリ (linq C# )](../../../csharp/programming-guide/concepts/linq/index.md) 」または「[統合言語クエリ (LINQ) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea333-116">For more general information about LINQ, see [Language-Integrated Query (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>  
  
 <span data-ttu-id="ea333-117">LINQ を使用してクエリを作成する際には、前の例のような言語固有の宣言型のクエリ構文と、標準クエリ演算子と呼ばれる一連のクエリ メソッドの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea333-117">LINQ enables you to compose queries by using both the language-specific declarative query syntax, shown in the previous example, as well as a set of query methods known as standard query operators.</span></span> <span data-ttu-id="ea333-118">したがって、次の例のように、前の例と同等のクエリをメソッド ベースの構文のみを使用して作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea333-118">An equivalent query to the previous example can be composed by using only the method-based syntax, as shown the following example:</span></span>  
  
[!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpressionspecific)]      
[!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpressionSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpressionspecific)]    
  
 <span data-ttu-id="ea333-119">WCF Data Services クライアントは、両方の種類のクエリをクエリ URI に変換できます。また、クエリ式にクエリメソッドを追加して LINQ クエリを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea333-119">The WCF Data Services client is able to translate both kinds of composed queries into a query URI, and you can extend a LINQ query by appending query methods to a query expression.</span></span> <span data-ttu-id="ea333-120">クエリ式または <xref:System.Data.Services.Client.DataServiceQuery%601> にメソッド構文を追加して LINQ クエリを作成した場合は、メソッドが呼び出される順序で操作がクエリ URI に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-120">When you compose LINQ queries by appending method syntax to a query expression or a <xref:System.Data.Services.Client.DataServiceQuery%601>, the operations are added to the query URI in the order in which methods are called.</span></span> <span data-ttu-id="ea333-121">これは、<xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> メソッドを呼び出して各クエリ オプションをクエリ URI に追加するのと同じです。</span><span class="sxs-lookup"><span data-stu-id="ea333-121">This is equivalent to calling the <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> method to add each query option to the query URI.</span></span>  
  
## <a name="executing-linq-queries"></a><span data-ttu-id="ea333-122">LINQ クエリの実行</span><span class="sxs-lookup"><span data-stu-id="ea333-122">Executing LINQ Queries</span></span>  
 <span data-ttu-id="ea333-123">クエリに特定の LINQ クエリ メソッド (<xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>、<xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> など) を追加するとクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-123">Certain LINQ query methods, such as <xref:System.Linq.Enumerable.First%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29> or <xref:System.Linq.Enumerable.Single%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29>, when appended to the query, cause the query to be executed.</span></span> <span data-ttu-id="ea333-124">クエリは、結果が暗黙的に列挙される場合 (`foreach` ループの間など) や、クエリが `List` コレクションに割り当てられている場合にも実行されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-124">A query is also executed when results are enumerated implicitly, such as during a `foreach` loop or when the query is assigned to a `List` collection.</span></span> <span data-ttu-id="ea333-125">詳細については、「[データサービスのクエリ](querying-the-data-service-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea333-125">For more information, see [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ea333-126">クライアントによる LINQ クエリの実行は 2 つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="ea333-126">The client executes a LINQ query in two parts.</span></span> <span data-ttu-id="ea333-127">可能な限り、クエリ内の LINQ 式は最初にクライアントで評価されます。その後、URI ベースのクエリが生成され、データ サービスに送信されて、サービス内のデータに対して評価されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-127">Whenever possible, LINQ expressions in a query are first evaluated on the client, and then a URI-based query is generated and sent to the data service for evaluation against data in the service.</span></span> <span data-ttu-id="ea333-128">詳細については、「[データサービスのクエリ](querying-the-data-service-wcf-data-services.md)」の「[クライアントとサーバーの実行](querying-the-data-service-wcf-data-services.md#executingQueries)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea333-128">For more information, see the section [Client versus Server Execution](querying-the-data-service-wcf-data-services.md#executingQueries) in [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ea333-129">OData 準拠のクエリ URI で LINQ クエリを変換できない場合、実行が試行されると例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="ea333-129">When a LINQ query cannot be translated in an OData-compliant query URI, an exception is raised when execution is attempted.</span></span> <span data-ttu-id="ea333-130">詳細については、「[データサービスのクエリ](querying-the-data-service-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea333-130">For more information, see [Querying the Data Service](querying-the-data-service-wcf-data-services.md).</span></span>  
  
## <a name="linq-query-examples"></a><span data-ttu-id="ea333-131">LINQ クエリの例</span><span class="sxs-lookup"><span data-stu-id="ea333-131">LINQ Query Examples</span></span>  
 <span data-ttu-id="ea333-132">次のセクションの例では、OData サービスに対して実行できる LINQ クエリの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea333-132">The examples in the following sections demonstrate the kinds of LINQ queries that can be executed against an OData service.</span></span>  
  
<a name="filtering"></a>   
### <a name="filtering"></a><span data-ttu-id="ea333-133">フィルター処理</span><span class="sxs-lookup"><span data-stu-id="ea333-133">Filtering</span></span>  
 <span data-ttu-id="ea333-134">このセクションの LINQ クエリは、サービスによって返されるフィード内のデータをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="ea333-134">The LINQ query examples in this section filter data in the feed returned by the service.</span></span>  
  
 <span data-ttu-id="ea333-135">以下の各例は、返された `Orders` エンティティをフィルター処理して、輸送費が 30 ドルを超える注文のみが返されるようにする同等のクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ea333-135">The following examples are equivalent queries that filter the returned `Orders` entities so that only orders with a freight cost greater than $30 are returned:</span></span>  
  
- <span data-ttu-id="ea333-136">LINQ クエリ構文を使用する場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-136">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwhereclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwhereclausespecific)]     
  
- <span data-ttu-id="ea333-137">LINQ クエリ メソッドを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-137">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqwheremethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqwheremethodspecific)]       
  
- <span data-ttu-id="ea333-138">URI クエリ文字列オプション `$filter`:</span><span class="sxs-lookup"><span data-stu-id="ea333-138">The URI query string `$filter` option:</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitquerywheremethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryWhereMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitquerywheremethodspecific)]       
  
 <span data-ttu-id="ea333-139">上の例はすべて、`http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M` というクエリ URI に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-139">All of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$filter=Freight gt 30M`.</span></span>  
  
<a name="sorting"></a>   
### <a name="sorting"></a><span data-ttu-id="ea333-140">並べ替え</span><span class="sxs-lookup"><span data-stu-id="ea333-140">Sorting</span></span>  
 <span data-ttu-id="ea333-141">以下の各例は、返されたデータを会社名と郵便番号の降順で並べ替える同等のクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ea333-141">The following examples show equivalent queries that sort returned data both by the company name and by postal code, descending:</span></span>  
  
- <span data-ttu-id="ea333-142">LINQ クエリ構文を使用する場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-142">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbyclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbyclausespecific)]        
  
- <span data-ttu-id="ea333-143">LINQ クエリ メソッドを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-143">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqorderbymethodspecific)]        
  
- <span data-ttu-id="ea333-144">URI クエリ文字列オプション `$orderby`:</span><span class="sxs-lookup"><span data-stu-id="ea333-144">URI query string `$orderby` option):</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryorderbymethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQueryOrderByMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryorderbymethodspecific)]         
  
 <span data-ttu-id="ea333-145">上の例はすべて、`http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc` というクエリ URI に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-145">All of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Customers()?$orderby=CompanyName,PostalCode desc`.</span></span>  
  
<a name="projection"></a>   
### <a name="projection"></a><span data-ttu-id="ea333-146">射影</span><span class="sxs-lookup"><span data-stu-id="ea333-146">Projection</span></span>  
 <span data-ttu-id="ea333-147">以下の各例は、返されたデータをより範囲の狭い `CustomerAddress` 型に射影する同等のクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ea333-147">The following examples show equivalent queries that project returned data into the narrower `CustomerAddress` type:</span></span>  
  
- <span data-ttu-id="ea333-148">LINQ クエリ構文を使用する場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-148">Using LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectclausespecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectClauseSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectclausespecific)]         
  
- <span data-ttu-id="ea333-149">LINQ クエリ メソッドを使用する場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-149">Using LINQ query methods:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqselectmethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSelectMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqselectmethodspecific)]         

> [!NOTE]
> <span data-ttu-id="ea333-150">`$select` メソッドを使用してクエリ URI に <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> クエリ オプションを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="ea333-150">The `$select` query option cannot be added to a query URI by using the <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> method.</span></span> <span data-ttu-id="ea333-151">LINQ の <xref:System.Linq.Enumerable.Select%2A> メソッドを使用して、クライアントによって要求 URI に `$select` クエリ オプションが生成されるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea333-151">We recommend that you use the LINQ <xref:System.Linq.Enumerable.Select%2A> method to have the client generate the `$select` query option in the request URI.</span></span>  
  
 <span data-ttu-id="ea333-152">上の例はいずれも、`"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"` というクエリ URI に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-152">Both of the previous examples are translated to the query URI: `"http://localhost:12345/northwind.svc/Customers()?$filter=Country eq 'GerGerm'&$select=CustomerID,Address,City,Region,PostalCode,Country"`.</span></span>  
  
<a name="paging"></a>   
### <a name="client-paging"></a><span data-ttu-id="ea333-153">クライアントのページング</span><span class="sxs-lookup"><span data-stu-id="ea333-153">Client Paging</span></span>  
 <span data-ttu-id="ea333-154">以下の各例は、25 件の注文を含む並べ替え済みの注文エンティティのページを、最初の 50 件の注文をスキップして要求する同等のクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ea333-154">The following examples show equivalent queries that request a page of sorted order entities that includes 25 orders, skipping the first 50 orders:</span></span>  
  
- <span data-ttu-id="ea333-155">LINQ クエリにクエリ メソッドを適用する場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-155">Applying query methods to a LINQ query:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#LinqSkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqskiptakemethodspecific)]     
  
- <span data-ttu-id="ea333-156">URI クエリ文字列オプション `$skip` および `$top`:</span><span class="sxs-lookup"><span data-stu-id="ea333-156">URI query string `$skip` and `$top` options):</span></span>  
  
[!code-csharp[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#explicitqueryskiptakemethodspecific)]      
[!code-vb[Astoria Northwind Client#ExplicitQuerySkipTakeMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#explicitqueryskiptakemethodspecific)]     
  
 <span data-ttu-id="ea333-157">上の例はいずれも、`http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25` というクエリ URI に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-157">Both of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$orderby=OrderDate desc&$skip=50&$top=25`.</span></span>  
  
<a name="expand"></a>   
### <a name="expand"></a><span data-ttu-id="ea333-158">Expand</span><span class="sxs-lookup"><span data-stu-id="ea333-158">Expand</span></span>  
 <span data-ttu-id="ea333-159">OData データサービスに対してクエリを実行する場合は、クエリの対象となるエンティティに関連するエンティティを、返されたフィードに含めるように要求できます。</span><span class="sxs-lookup"><span data-stu-id="ea333-159">When you query an OData data service, you can request that entities related to the entity targeted by the query be included the returned feed.</span></span> <span data-ttu-id="ea333-160">そのためには、LINQ クエリの対象のエンティティ セットの <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> で <xref:System.Data.Services.Client.DataServiceQuery%601> メソッドを呼び出して、関連するエンティティ セットの名前を `path` パラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="ea333-160">The <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method is called on the <xref:System.Data.Services.Client.DataServiceQuery%601> for the entity set targeted by the LINQ query, with the related entity set name supplied as the `path` parameter.</span></span> <span data-ttu-id="ea333-161">詳細については、「[遅延コンテンツの読み込み](loading-deferred-content-wcf-data-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea333-161">For more information, see [Loading Deferred Content](loading-deferred-content-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ea333-162">以下の各例は、クエリで <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> メソッドを使用する同等の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea333-162">The following examples show equivalent ways to use the <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method in a query:</span></span>  
  
- <span data-ttu-id="ea333-163">LINQ クエリ構文の場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-163">In LINQ query syntax:</span></span>  
  
[!code-csharp[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandspecific)]      
[!code-vb[Astoria Northwind Client#LinqQueryExpandSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandspecific)]  
  
- <span data-ttu-id="ea333-164">LINQ クエリ メソッドの場合:</span><span class="sxs-lookup"><span data-stu-id="ea333-164">With LINQ query methods:</span></span>  

[!code-csharp[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#linqqueryexpandmethodspecific)]       
[!code-vb[Astoria Northwind Client#LinqQueryExpandMethodSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#linqqueryexpandmethodspecific)]       

 <span data-ttu-id="ea333-165">上の例はいずれも、`http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details` というクエリ URI に変換されます。</span><span class="sxs-lookup"><span data-stu-id="ea333-165">Both of the previous examples are translated to the query URI: `http://localhost:12345/northwind.svc/Orders()?$filter=CustomerID eq 'ALFKI'&$expand=Order_Details`.</span></span>  
  
<a name="unsupportedMethods"></a>   
## <a name="unsupported-linq-methods"></a><span data-ttu-id="ea333-166">サポートされていない LINQ メソッド</span><span class="sxs-lookup"><span data-stu-id="ea333-166">Unsupported LINQ Methods</span></span>  
 <span data-ttu-id="ea333-167">次の表に、LINQ メソッドのクラスはサポートされていないため、OData サービスに対して実行されるクエリには含めることができません。</span><span class="sxs-lookup"><span data-stu-id="ea333-167">The following table contains the classes of LINQ methods are not supported and cannot be included in a query executed against an OData service:</span></span>  
  
|<span data-ttu-id="ea333-168">演算の種類</span><span class="sxs-lookup"><span data-stu-id="ea333-168">Operation Type</span></span>|<span data-ttu-id="ea333-169">サポートされていないメソッド</span><span class="sxs-lookup"><span data-stu-id="ea333-169">Unsupported Method</span></span>|  
|--------------------|------------------------|  
|<span data-ttu-id="ea333-170">集合演算子</span><span class="sxs-lookup"><span data-stu-id="ea333-170">Set operators</span></span>|<span data-ttu-id="ea333-171">すべての集合演算子は <xref:System.Data.Services.Client.DataServiceQuery%601> に対してサポートされていません。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ea333-171">All set operators are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, which included the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.All%2A><br />-   <xref:System.Linq.Enumerable.Any%2A><br />-   <xref:System.Linq.Enumerable.Concat%2A><br />-   <xref:System.Linq.Enumerable.DefaultIfEmpty%2A><br />-   <xref:System.Linq.Enumerable.Distinct%2A><br />-   <xref:System.Linq.Enumerable.Except%2A><br />-   <xref:System.Linq.Enumerable.Intersect%2A><br />-   <xref:System.Linq.Enumerable.Union%2A><br />-   <xref:System.Linq.Enumerable.Zip%2A>|  
|<span data-ttu-id="ea333-172">順序付け演算子</span><span class="sxs-lookup"><span data-stu-id="ea333-172">Ordering operators</span></span>|<span data-ttu-id="ea333-173"><xref:System.Collections.Generic.IComparer%601> を必要とする以下の順序付け演算子は <xref:System.Data.Services.Client.DataServiceQuery%601> に対してサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ea333-173">The following ordering operators that require <xref:System.Collections.Generic.IComparer%601> are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Collections.Generic.IComparer%7B%60%601%7D%29>|  
|<span data-ttu-id="ea333-174">プロジェクション演算子とフィルター演算子</span><span class="sxs-lookup"><span data-stu-id="ea333-174">Projection and filtering operators</span></span>|<span data-ttu-id="ea333-175">位置指定引数を受け取る以下のプロジェクション演算子とフィルター演算子は <xref:System.Data.Services.Client.DataServiceQuery%601> に対してサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ea333-175">The following projection and filtering operators that accept a positional argument are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2C%60%601%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.SelectMany%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%602%7D%29><br />-   <xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29>|  
|<span data-ttu-id="ea333-176">グループ化演算子</span><span class="sxs-lookup"><span data-stu-id="ea333-176">Grouping operators</span></span>|<span data-ttu-id="ea333-177">すべてのグループ化演算子は <xref:System.Data.Services.Client.DataServiceQuery%601> に対してサポートされていません。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ea333-177">All grouping operators are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, including the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.GroupBy%2A><br />-   <xref:System.Linq.Enumerable.GroupJoin%2A><br /><br /> <span data-ttu-id="ea333-178">グループ化の操作はクライアント側で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea333-178">Grouping operations must be performed on the client.</span></span>|  
|<span data-ttu-id="ea333-179">集計演算子</span><span class="sxs-lookup"><span data-stu-id="ea333-179">Aggregate operators</span></span>|<span data-ttu-id="ea333-180">すべての集計演算子は <xref:System.Data.Services.Client.DataServiceQuery%601> に対してサポートされていません。以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ea333-180">All aggregate operations are unsupported against a <xref:System.Data.Services.Client.DataServiceQuery%601>, including the following:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.Aggregate%2A><br />-   <xref:System.Linq.Enumerable.Average%2A><br />-   <xref:System.Linq.Enumerable.Count%2A><br />-   <xref:System.Linq.Enumerable.LongCount%2A><br />-   <xref:System.Linq.Enumerable.Max%2A><br />-   <xref:System.Linq.Enumerable.Min%2A><br />-   <xref:System.Linq.Enumerable.Sum%2A><br /><br /> <span data-ttu-id="ea333-181">集計操作は、クライアント側で実行するか、サービス操作でカプセル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea333-181">Aggregate operations must either be performed on the client or be encapsulated by a service operation.</span></span>|  
|<span data-ttu-id="ea333-182">ページング演算子</span><span class="sxs-lookup"><span data-stu-id="ea333-182">Paging operators</span></span>|<span data-ttu-id="ea333-183">以下のページング演算子は <xref:System.Data.Services.Client.DataServiceQuery%601> に対してサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ea333-183">The following paging operators are not supported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> -   <xref:System.Linq.Enumerable.ElementAt%2A><br />-   <xref:System.Linq.Enumerable.Last%2A><br />-   <xref:System.Linq.Enumerable.LastOrDefault%2A><br />-   <xref:System.Linq.Enumerable.SkipWhile%2A><br />-   <xref:System.Linq.Enumerable.TakeWhile%2A><br/><br/><span data-ttu-id="ea333-184">**注:** 空のシーケンスに対して実行されるページング演算子は、null を返します。</span><span class="sxs-lookup"><span data-stu-id="ea333-184">**Note:**  Paging operators that are executed on an empty sequence return null.</span></span>|  
|<span data-ttu-id="ea333-185">その他の演算子</span><span class="sxs-lookup"><span data-stu-id="ea333-185">Other operators</span></span>|<span data-ttu-id="ea333-186"><xref:System.Data.Services.Client.DataServiceQuery%601>に対しては、次の演算子もサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ea333-186">The following operators are also not supported against a <xref:System.Data.Services.Client.DataServiceQuery%601>:</span></span><br /><br /> - <xref:System.Linq.Enumerable.Empty%2A><br />- <xref:System.Linq.Enumerable.Range%2A><br />- <xref:System.Linq.Enumerable.Repeat%2A><br />- <xref:System.Linq.Enumerable.ToDictionary%2A><br />- <xref:System.Linq.Enumerable.ToLookup%2A>|  
  
<a name="supportedExpressions"></a>   
## <a name="supported-expression-functions"></a><span data-ttu-id="ea333-187">サポートされている式の関数</span><span class="sxs-lookup"><span data-stu-id="ea333-187">Supported Expression Functions</span></span>  
 <span data-ttu-id="ea333-188">次の共通言語ランタイム (CLR) のメソッドとプロパティは、OData サービスへの要求 URI に含めるためにクエリ式で変換できるため、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="ea333-188">The following common-language runtime (CLR) methods and properties are supported because they can be translated in a query expression for inclusion in the request URI to an OData service:</span></span>  
  
|<span data-ttu-id="ea333-189"><xref:System.String> メンバー</span><span class="sxs-lookup"><span data-stu-id="ea333-189"><xref:System.String> Member</span></span>|<span data-ttu-id="ea333-190">サポートされている OData 関数</span><span class="sxs-lookup"><span data-stu-id="ea333-190">Supported OData Function</span></span>|  
|-----------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.String.Concat%28System.String%2CSystem.String%29>|`string concat(string p0, string p1)`|  
|<xref:System.String.Contains%28System.String%29>|`bool substringof(string p0, string p1)`|  
|<xref:System.String.EndsWith%28System.String%29>|`bool endswith(string p0, string p1)`|  
|<xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>|`int indexof(string p0, string p1)`|  
|<xref:System.String.Length>|`int length(string p0)`|  
|<xref:System.String.Replace%28System.String%2CSystem.String%29>|`string replace(string p0, string find, string replace)`|  
|<xref:System.String.Substring%28System.Int32%29>|`string substring(string p0, int pos)`|  
|<xref:System.String.Substring%28System.Int32%2CSystem.Int32%29>|`string substring(string p0, int pos, int length)`|  
|<xref:System.String.ToLower>|`string tolower(string p0)`|  
|<xref:System.String.ToUpper>|`string toupper(string p0)`|  
|<xref:System.String.Trim>|`string trim(string p0)`|  
  
|<span data-ttu-id="ea333-191"><xref:System.DateTime> メンバー<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ea333-191"><xref:System.DateTime> Member<sup>1</sup></span></span>|<span data-ttu-id="ea333-192">サポートされている OData 関数</span><span class="sxs-lookup"><span data-stu-id="ea333-192">Supported OData Function</span></span>|  
|-------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Day>|`int day(DateTime p0)`|  
|<xref:System.DateTime.Hour>|`int hour(DateTime p0)`|  
|<xref:System.DateTime.Minute>|`int minute(DateTime p0)`|  
|<xref:System.DateTime.Month>|`int month(DateTime p0)`|  
|<xref:System.DateTime.Second>|`int second(DateTime p0)`|  
|<xref:System.DateTime.Year>|`int year(DateTime p0)`|  
  
 <span data-ttu-id="ea333-193"><sup>1</sup><xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType> の同じ日付と時刻のプロパティと Visual Basic の <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> メソッドもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ea333-193"><sup>1</sup>The equivalent date and time properties of <xref:Microsoft.VisualBasic.DateAndTime?displayProperty=nameWithType> and the <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> method in Visual Basic are also supported.</span></span>  
  
|<span data-ttu-id="ea333-194"><xref:System.Math> メンバー</span><span class="sxs-lookup"><span data-stu-id="ea333-194"><xref:System.Math> Member</span></span>|<span data-ttu-id="ea333-195">サポートされている OData 関数</span><span class="sxs-lookup"><span data-stu-id="ea333-195">Supported OData Function</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Math.Ceiling%28System.Decimal%29>|`decimal ceiling(decimal p0)`|  
|<xref:System.Math.Ceiling%28System.Double%29>|`double ceiling(double p0)`|  
|<xref:System.Math.Floor%28System.Decimal%29>|`decimal floor(decimal p0)`|  
|<xref:System.Math.Floor%28System.Double%29>|`double floor(double p0)`|  
|<xref:System.Math.Round%28System.Decimal%29>|`decimal round(decimal p0)`|  
|<xref:System.Math.Round%28System.Double%29>|`double round(double p0)`|  
  
|<span data-ttu-id="ea333-196"><xref:System.Linq.Expressions.Expression> メンバー</span><span class="sxs-lookup"><span data-stu-id="ea333-196"><xref:System.Linq.Expressions.Expression> Member</span></span>|<span data-ttu-id="ea333-197">サポートされている OData 関数</span><span class="sxs-lookup"><span data-stu-id="ea333-197">Supported OData Function</span></span>|  
|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|  
|<xref:System.Linq.Expressions.Expression.TypeIs%28System.Linq.Expressions.Expression%2CSystem.Type%29>|`bool isof(type p0)`|  
  
 <span data-ttu-id="ea333-198">クライアント側でその他の CLR 関数を評価できる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ea333-198">The client may also be able to evaluate additional CLR functions on the client.</span></span> <span data-ttu-id="ea333-199">クライアント側で評価することも、サーバー側で評価するために有効な要求 URI に変換することもできない式に対しては、<xref:System.NotSupportedException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="ea333-199">A <xref:System.NotSupportedException> is raised for any expression that cannot be evaluated on the client and cannot be translated into a valid request URI for evaluation on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea333-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea333-200">See also</span></span>

- [<span data-ttu-id="ea333-201">データ サービスに対するクエリ</span><span class="sxs-lookup"><span data-stu-id="ea333-201">Querying the Data Service</span></span>](querying-the-data-service-wcf-data-services.md)
- [<span data-ttu-id="ea333-202">クエリ射影</span><span class="sxs-lookup"><span data-stu-id="ea333-202">Query Projections</span></span>](query-projections-wcf-data-services.md)
- [<span data-ttu-id="ea333-203">オブジェクトの具体化</span><span class="sxs-lookup"><span data-stu-id="ea333-203">Object Materialization</span></span>](object-materialization-wcf-data-services.md)
- [<span data-ttu-id="ea333-204">OData: URI 規則</span><span class="sxs-lookup"><span data-stu-id="ea333-204">OData: URI Conventions</span></span>](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/)
