---
title: Entity SQL 言語
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: ecbf9bc555594d205281237559037ac2a0e1cdb0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631706"
---
# <a name="entity-sql-language"></a><span data-ttu-id="3574f-102">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="3574f-102">Entity SQL Language</span></span>
<span data-ttu-id="3574f-103">Entity SQL は、ストレージに依存しない SQL と似たクエリ言語です。</span><span class="sxs-lookup"><span data-stu-id="3574f-103">Entity SQL is a storage-independent query language that is similar to SQL.</span></span> <span data-ttu-id="3574f-104">Entity SQL を使用すると、オブジェクトとして、または表形式でエンティティ データに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3574f-104">Entity SQL allows you to query entity data, either as objects or in a tabular form.</span></span> <span data-ttu-id="3574f-105">次の場合には Entity SQL の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="3574f-105">You should consider using Entity SQL in the following cases:</span></span>  
  
- <span data-ttu-id="3574f-106">クエリを実行時に動的に作成する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="3574f-106">When a query must be dynamically constructed at runtime.</span></span> <span data-ttu-id="3574f-107">その場合、実行時に Entity SQL クエリ文字列を作成する代わりに、<xref:System.Data.Objects.ObjectQuery%601> のクエリ ビルダー メソッドを使用することも検討してください。</span><span class="sxs-lookup"><span data-stu-id="3574f-107">In this case, you should also consider using the query builder methods of <xref:System.Data.Objects.ObjectQuery%601> instead of constructing an Entity SQL query string at runtime.</span></span>  
  
- <span data-ttu-id="3574f-108">モデル定義の一部としてクエリを定義する場合。</span><span class="sxs-lookup"><span data-stu-id="3574f-108">When you want to define a query as part of the model definition.</span></span> <span data-ttu-id="3574f-109">データ モデルでは Entity SQL のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3574f-109">Only Entity SQL is supported in a data model.</span></span> <span data-ttu-id="3574f-110">詳細については、次を参照してください[QueryView 要素 (MSL)。](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span><span class="sxs-lookup"><span data-stu-id="3574f-110">For more information, see [QueryView Element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)</span></span>  
  
- <span data-ttu-id="3574f-111">EntityClient で <xref:System.Data.EntityClient.EntityDataReader> を使用して行セットとして読み取り専用エンティティ データを返す場合。</span><span class="sxs-lookup"><span data-stu-id="3574f-111">When using EntityClient to return read-only entity data as rowsets using a <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="3574f-112">詳細については、次を参照してください。 [Entity Framework 用の EntityClient プロバイダー](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)します。</span><span class="sxs-lookup"><span data-stu-id="3574f-112">For more information, see [EntityClient Provider for the Entity Framework](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).</span></span>  
  
- <span data-ttu-id="3574f-113">SQL ベースのクエリ言語に詳しい場合、Entity SQL の使用が最も適切に思われるでしょう。</span><span class="sxs-lookup"><span data-stu-id="3574f-113">If you are already an expert in SQL-based query languages, Entity SQL may seem the most natural to you.</span></span>  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a><span data-ttu-id="3574f-114">Entity SQL と EntityClient プロバイダーの使用</span><span class="sxs-lookup"><span data-stu-id="3574f-114">Using Entity SQL with the EntityClient provider</span></span>  
 <span data-ttu-id="3574f-115">Entity SQL を EntityClient プロバイダーと一緒に使用する際の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3574f-115">If you want to use Entity SQL with the EntityClient provider, see the following topics for more information:</span></span>  
  
 [<span data-ttu-id="3574f-116">Entity Framework 用の EntityClient プロバイダー</span><span class="sxs-lookup"><span data-stu-id="3574f-116">EntityClient Provider for the Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 [<span data-ttu-id="3574f-117">方法: EntityConnection の接続文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="3574f-117">How to: Build an EntityConnection Connection String</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)  
  
 [<span data-ttu-id="3574f-118">方法: PrimitiveType 結果を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-118">How to: Execute a Query that Returns PrimitiveType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [<span data-ttu-id="3574f-119">方法: StructuralType 結果を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-119">How to: Execute a Query that Returns StructuralType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [<span data-ttu-id="3574f-120">方法: RefType 結果を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-120">How to: Execute a Query that Returns RefType Results</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [<span data-ttu-id="3574f-121">方法: 複合型を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-121">How to: Execute a Query that Returns Complex Types</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-complex-types.md)  
  
 [<span data-ttu-id="3574f-122">方法: 入れ子になったコレクションを返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-122">How to: Execute a Query that Returns Nested Collections</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [<span data-ttu-id="3574f-123">方法: EntityCommand を使用してパラメーター化 Entity SQL クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-123">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [<span data-ttu-id="3574f-124">方法: EntityCommand を使用してパラメーター化されたストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-124">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [<span data-ttu-id="3574f-125">方法: ポリモーフィック クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="3574f-125">How to: Execute a Polymorphic Query</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-polymorphic-query.md)  
  
 [<span data-ttu-id="3574f-126">方法: リレーションシップをナビゲート、Navigate 演算子</span><span class="sxs-lookup"><span data-stu-id="3574f-126">How to: Navigate Relationships with the Navigate Operator</span></span>](../../../../../../docs/framework/data/adonet/ef/how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a><span data-ttu-id="3574f-127">Entity SQL とオブジェクト クエリの使用</span><span class="sxs-lookup"><span data-stu-id="3574f-127">Using Entity SQL with object queries</span></span>  
 <span data-ttu-id="3574f-128">Entity SQL をオブジェクト クエリと一緒に使用する際の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3574f-128">If you want to use Entity SQL with object queries, see the following topics for more information:</span></span>  
  
 <span data-ttu-id="3574f-129">[方法: エンティティ型のオブジェクトを返すクエリを実行します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-129">[How to: Execute a Query that Returns Entity Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-130">[方法: パラメーター化クエリを実行します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-130">[How to: Execute a Parameterized Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-131">[方法: ナビゲーション プロパティを使用してリレーションシップを移動します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-131">[How to: Navigate Relationships Using Navigation Properties](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-132">[方法: ユーザー定義関数を呼び出す](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-132">[How to: Call a User-Defined Function](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-133">[方法: データをフィルター処理します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-133">[How to: Filter Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-134">[方法: データの並べ替え](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-134">[How to: Sort Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-135">[方法: データをグループ化](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-135">[How to: Group Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-136">[方法: 集計データ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-136">[How to: Aggregate Data](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-137">[方法: 匿名型オブジェクトを返すクエリを実行します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-137">[How to: Execute a Query that Returns Anonymous Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-138">[方法: プリミティブ型のコレクションを返すクエリを実行します。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-138">[How to: Execute a Query that Returns a Collection of Primitive Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-139">[方法: EntityCollection 内の関連オブジェクトをクエリします。](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-139">[How to: Query Related Objects in an EntityCollection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-140">[方法: 2 つのクエリの結合を並べ替える](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-140">[How to: Order the Union of Two Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))</span></span>  
  
 <span data-ttu-id="3574f-141">[方法: クエリ結果 ページ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3574f-141">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3574f-142">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3574f-142">In This Section</span></span>  
 [<span data-ttu-id="3574f-143">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="3574f-143">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
  
 [<span data-ttu-id="3574f-144">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="3574f-144">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
  
## <a name="see-also"></a><span data-ttu-id="3574f-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="3574f-145">See also</span></span>

- [<span data-ttu-id="3574f-146">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="3574f-146">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
- [<span data-ttu-id="3574f-147">言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="3574f-147">Language Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
