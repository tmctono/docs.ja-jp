---
title: CQRS マイクロサービスに読み取り/クエリを実装する
description: コンテナー化された .NET アプリケーション用の .NET マイクロサービス アーキテクチャ | Dapper を使用した eShopOnContainers でのオーダリング マイクロサービスの CQRS のクエリ側の実装を理解する。
ms.date: 10/08/2018
ms.openlocfilehash: 49f42a5035bab38f800f3ec5ea24b01fde0d2964
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988753"
---
# <a name="implement-readsqueries-in-a-cqrs-microservice"></a><span data-ttu-id="3ca63-103">CQRS マイクロサービスに読み取り/クエリを実装する</span><span class="sxs-lookup"><span data-stu-id="3ca63-103">Implement reads/queries in a CQRS microservice</span></span>

<span data-ttu-id="3ca63-104">読み取り/クエリの場合、eShopOnContainers 参照アプリケーションのオーダリング マイクロサービスでは、DDD モデルおよびトランザクション領域とは別にクエリを実装します。</span><span class="sxs-lookup"><span data-stu-id="3ca63-104">For reads/queries, the ordering microservice from the eShopOnContainers reference application implements the queries independently from the DDD model and transactional area.</span></span> <span data-ttu-id="3ca63-105">この主な理由は、クエリとトランザクションの要求が大幅に異なるためです。</span><span class="sxs-lookup"><span data-stu-id="3ca63-105">This was done primarily because the demands for queries and for transactions are drastically different.</span></span> <span data-ttu-id="3ca63-106">書き込みでは、ドメイン ロジックに準拠する必要があるトランザクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-106">Writes execute transactions that must be compliant with the domain logic.</span></span> <span data-ttu-id="3ca63-107">一方、クエリはべき等であり、ドメイン ルールから分離することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-107">Queries, on the other hand, are idempotent and can be segregated from the domain rules.</span></span>

<span data-ttu-id="3ca63-108">図 7-3 に示すように、方法は単純です。</span><span class="sxs-lookup"><span data-stu-id="3ca63-108">The approach is simple, as shown in Figure 7-3.</span></span> <span data-ttu-id="3ca63-109">API インターフェイスは、Dapper のようなマイクロ オブジェクト リレーショナル マッパー (ORM) などの任意のインフラストラクチャを使用して、UI アプリケーションのニーズに応じて動的な ViewModel を返すことで Web API コントローラーによって実装されます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-109">The API interface is implemented by the Web API controllers using any infrastructure, such as a micro Object Relational Mapper (ORM) like Dapper, and returning dynamic ViewModels depending on the needs of the UI applications.</span></span>

![簡略化された CQRS における上位レベルのクエリ側を示す図。](./media/cqrs-microservice-reads/simple-approach-cqrs-queries.png)

<span data-ttu-id="3ca63-111">**図 7-3**。</span><span class="sxs-lookup"><span data-stu-id="3ca63-111">**Figure 7-3**.</span></span> <span data-ttu-id="3ca63-112">CQRS マイクロサービスでのクエリの最も単純な方法</span><span class="sxs-lookup"><span data-stu-id="3ca63-112">The simplest approach for queries in a CQRS microservice</span></span>

<span data-ttu-id="3ca63-113">単純化された CQRS アプローチのクエリ側の最も単純なアプローチは、動的な ViewModels を返す Micro-ORM のような Dapper を使用して、データベースをクエリすることによって実装できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-113">The simplest approach for the queries-side in a simplified CQRS approach can be implemented by just querying the database with a Micro-ORM like Dapper, returning dynamic ViewModels.</span></span> <span data-ttu-id="3ca63-114">クエリ定義ではデータベースをクエリし、各クエリに対してオンザフライでビルドされた動的な ViewModel を返します。</span><span class="sxs-lookup"><span data-stu-id="3ca63-114">The query definitions query the database and return a dynamic ViewModel built on the fly for each query.</span></span> <span data-ttu-id="3ca63-115">クエリはべき等であるため、クエリの実行回数に関係なく、データが変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3ca63-115">Since the queries are idempotent, they won't change the data no matter how many times you run a query.</span></span> <span data-ttu-id="3ca63-116">したがって、トランザクション側で使用される DDD パターン (集計などのパターン) によって制限される必要はありません。これが、クエリがトランザクション領域から分離される理由です。</span><span class="sxs-lookup"><span data-stu-id="3ca63-116">Therefore, you don't need to be restricted by any DDD pattern used in the transactional side, like aggregates and other patterns, and that is why queries are separated from the transactional area.</span></span> <span data-ttu-id="3ca63-117">UI に必要なデータについてデータベースをクエリし、SQL ステートメント自体を除く、任意の場所 (ViewModel のクラスがない) で静的に定義する必要のない動的な ViewModel を返すだけです。</span><span class="sxs-lookup"><span data-stu-id="3ca63-117">You simply query the database for the data that the UI needs and return a dynamic ViewModel that does not need to be statically defined anywhere (no classes for the ViewModels) except in the SQL statements themselves.</span></span>

<span data-ttu-id="3ca63-118">これは単純な方法であるため、クエリ側で必要なコード ([Dapper](https://github.com/StackExchange/Dapper) のようなマイクロ ORM を使用するコードなど) を[同じ Web API プロジェクト内で](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs)実装することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-118">Since this is a simple approach, the code required for the queries side (such as code using a micro ORM like [Dapper](https://github.com/StackExchange/Dapper)) can be implemented [within the same Web API project](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.API/Application/Queries/OrderQueries.cs).</span></span> <span data-ttu-id="3ca63-119">これは図 7-4 に示されています。</span><span class="sxs-lookup"><span data-stu-id="3ca63-119">Figure 7-4 shows this.</span></span> <span data-ttu-id="3ca63-120">クエリは eShopOnContainers 内の **Ordering.API** マイクロサービス プロジェクトで定義されています。</span><span class="sxs-lookup"><span data-stu-id="3ca63-120">The queries are defined in the **Ordering.API** microservice project within the eShopOnContainers solution.</span></span>

![Ordering.API プロジェクトの Queries フォルダーのスクリーンショット。](./media/cqrs-microservice-reads/ordering-api-queries-folder.png)

<span data-ttu-id="3ca63-122">**図 7-4**。</span><span class="sxs-lookup"><span data-stu-id="3ca63-122">**Figure 7-4**.</span></span> <span data-ttu-id="3ca63-123">eShopOnContainers でのオーダリング マイクロサービスのクエリ</span><span class="sxs-lookup"><span data-stu-id="3ca63-123">Queries in the Ordering microservice in eShopOnContainers</span></span>

## <a name="use-viewmodels-specifically-made-for-client-apps-independent-from-domain-model-constraints"></a><span data-ttu-id="3ca63-124">ドメイン モデル制約とは別の、クライアント アプリ専用の ViewModel の使用</span><span class="sxs-lookup"><span data-stu-id="3ca63-124">Use ViewModels specifically made for client apps, independent from domain model constraints</span></span>

<span data-ttu-id="3ca63-125">クエリはクライアント アプリケーションで必要なデータを取得するために実行されるため、戻り値の型は、クエリによって返されるデータに基づいて、クライアント専用に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-125">Since the queries are performed to obtain the data needed by the client applications, the returned type can be specifically made for the clients, based on the data returned by the queries.</span></span> <span data-ttu-id="3ca63-126">これらのモデル、またはデータ転送オブジェクト (DTO)、は ViewModel と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-126">These models, or Data Transfer Objects (DTOs), are called ViewModels.</span></span>

<span data-ttu-id="3ca63-127">返されるデータ (ViewModel) は、データベースの複数のエンティティまたはテーブルからの、あるいはトランザクション領域のドメイン モデルで定義されている複数の集計全体のデータの結合結果である場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ca63-127">The returned data (ViewModel) can be the result of joining data from multiple entities or tables in the database, or even across multiple aggregates defined in the domain model for the transactional area.</span></span> <span data-ttu-id="3ca63-128">ここでは、ドメイン モデルには依存しないクエリを作成するため、集計の境界と制約は完全に無視され、必要になる可能性のあるテーブルと列をクエリするのは自由です。</span><span class="sxs-lookup"><span data-stu-id="3ca63-128">In this case, because you are creating queries independent of the domain model, the aggregates boundaries and constraints are completely ignored and you're free to query any table and column you might need.</span></span> <span data-ttu-id="3ca63-129">この方法では、開発者がクエリの作成または更新を行う場合に優れた柔軟性と生産性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-129">This approach provides great flexibility and productivity for the developers creating or updating the queries.</span></span>

<span data-ttu-id="3ca63-130">ViewModel として、クラスで定義されている静的な型を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-130">The ViewModels can be static types defined in classes.</span></span> <span data-ttu-id="3ca63-131">または、実行 (オーダリング マイクロサービスで実装) されたクエリに基づいて動的に作成することもできます。これは、開発者にとって非常にアジャイルな方法です。</span><span class="sxs-lookup"><span data-stu-id="3ca63-131">Or they can be created dynamically based on the queries performed (as is implemented in the ordering microservice), which is very agile for developers.</span></span>

## <a name="use-dapper-as-a-micro-orm-to-perform-queries"></a><span data-ttu-id="3ca63-132">クエリを実行するためのマイクロ ORM としての Dapper の使用</span><span class="sxs-lookup"><span data-stu-id="3ca63-132">Use Dapper as a micro ORM to perform queries</span></span>

<span data-ttu-id="3ca63-133">クエリでは、任意のマイクロ ORM、Entity Framework Core、またはプレーン ADO.NET を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-133">You can use any micro ORM, Entity Framework Core, or even plain ADO.NET for querying.</span></span> <span data-ttu-id="3ca63-134">サンプル アプリケーションでは、一般的なマイクロ ORM の良い例として、eShopOnContainers でのオーダリング マイクロサービスに対して Dapper が選択されました。</span><span class="sxs-lookup"><span data-stu-id="3ca63-134">In the sample application, Dapper was selected for the ordering microservice in eShopOnContainers as a good example of a popular micro ORM.</span></span> <span data-ttu-id="3ca63-135">これは非常に軽量なフレームワークであるため、パフォーマンスの優れたプレーン SQL クエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-135">It can run plain SQL queries with great performance, because it's a very light framework.</span></span> <span data-ttu-id="3ca63-136">Dapper を使用することで、複数のテーブルのアクセスと結合が可能な SQL クエリを記述できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-136">Using Dapper, you can write a SQL query that can access and join multiple tables.</span></span>

<span data-ttu-id="3ca63-137">Dapper はオープンソースのプロジェクト (Sam Saffron によって最初に作成された) であり、[スタック オーバーフロー](https://stackoverflow.com/)で使用される構成要素の一部です。</span><span class="sxs-lookup"><span data-stu-id="3ca63-137">Dapper is an open-source project (original created by Sam Saffron), and is part of the building blocks used in [Stack Overflow](https://stackoverflow.com/).</span></span> <span data-ttu-id="3ca63-138">Dapper を使用するために必要になるのは、次の図に示すように、[Dapper NuGet パッケージ](https://www.nuget.org/packages/Dapper)を使用してインストールすることだけです。</span><span class="sxs-lookup"><span data-stu-id="3ca63-138">To use Dapper, you just need to install it through the [Dapper NuGet package](https://www.nuget.org/packages/Dapper), as shown in the following figure:</span></span>

![[NuGet パッケージ] ビューの Dapper パッケージのスクリーンショット。](./media/cqrs-microservice-reads/drapper-package-nuget.png)

<span data-ttu-id="3ca63-140">コードで Dapper 拡張メソッドにアクセスできるようにするために、ステートメントを追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="3ca63-140">You also need to add a using statement so your code has access to the Dapper extension methods.</span></span>

<span data-ttu-id="3ca63-141">コードで Dapper を使用する場合は、<xref:System.Data.SqlClient> 名前空間で使用可能な <xref:System.Data.SqlClient.SqlConnection> クラスを直接使用します。</span><span class="sxs-lookup"><span data-stu-id="3ca63-141">When you use Dapper in your code, you directly use the <xref:System.Data.SqlClient.SqlConnection> class available in the <xref:System.Data.SqlClient> namespace.</span></span> <span data-ttu-id="3ca63-142">QueryAsync メソッドと、<xref:System.Data.SqlClient.SqlConnection> クラスを拡張するその他の拡張メソッドを使用して、簡単でパフォーマンスの高い方法でクエリを実行するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-142">Through the QueryAsync method and other extension methods that extend the <xref:System.Data.SqlClient.SqlConnection> class, you can simply run queries in a straightforward and performant way.</span></span>

## <a name="dynamic-versus-static-viewmodels"></a><span data-ttu-id="3ca63-143">動的な ViewModel と静的な ViewModel</span><span class="sxs-lookup"><span data-stu-id="3ca63-143">Dynamic versus static ViewModels</span></span>

<span data-ttu-id="3ca63-144">ViewModel をサーバー側からクライアント アプリに返す場合、エンティティ モデルの内部ドメイン エンティティとは異なる可能性のある DTO (Data Transfer Object) として ViewModel を考えることができます。これは、ViewModel がクライアント アプリで必要な方法でデータを保持するためです。</span><span class="sxs-lookup"><span data-stu-id="3ca63-144">When returning ViewModels from the server-side to client apps, you can think about those ViewModels as DTOs (Data Transfer Objects) that can be different to the internal domain entities of your entity model because the ViewModels hold the data the way the client app needs.</span></span> <span data-ttu-id="3ca63-145">したがって、多くの場合、複数のドメイン エンティティからのデータを集計し、クライアント アプリでそのデータがいかに必要であるかに従って ViewModel を正確に構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-145">Therefore, in many cases, you can aggregate data coming from multiple domain entities and compose the ViewModels precisely according to how the client app needs that data.</span></span>

<span data-ttu-id="3ca63-146">これらの ViewModel または DTO は、後述のコード スニペットで示す `OrderSummary` クラスと同様に (データ ホルダー クラスとして) 明示的に定義できます。あるいは、動的な型として、クエリによって返される属性に基づいて、単に動的な ViewModel または動的な DTO を返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-146">Those ViewModels or DTOs can be defined explicitly (as data holder classes) like the `OrderSummary` class shown in a later code snippet, or you could just return dynamic ViewModels or dynamic DTOs simply based on the attributes returned by your queries, as a dynamic type.</span></span>

### <a name="viewmodel-as-dynamic-type"></a><span data-ttu-id="3ca63-147">動的な型としての ViewModel</span><span class="sxs-lookup"><span data-stu-id="3ca63-147">ViewModel as dynamic type</span></span>

<span data-ttu-id="3ca63-148">次のコードに示すように、`ViewModel` は、内部的にクエリによって返される属性に基づく*動的な*型を単に返すことで、クエリで直接返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-148">As shown in the following code, a `ViewModel` can be directly returned by the queries by just returning a *dynamic* type that internally is based on the attributes returned by a query.</span></span> <span data-ttu-id="3ca63-149">これは、返される属性のサブセットがクエリ自体に基づいていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3ca63-149">That means that the subset of attributes to be returned is based on the query itself.</span></span> <span data-ttu-id="3ca63-150">そのため、クエリまたは結合に新しい列を追加する場合、そのデータは返される `ViewModel` に動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-150">Therefore, if you add a new column to the query or join, that data is dynamically added to the returned `ViewModel`.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
    public async Task<IEnumerable<dynamic>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<dynamic>(
                @"SELECT o.[Id] as ordernumber,
                o.[OrderDate] as [date],os.[Name] as [status],
                SUM(oi.units*oi.unitprice) as total
                FROM [ordering].[Orders] o
                LEFT JOIN[ordering].[orderitems] oi ON o.Id = oi.orderid
                LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                GROUP BY o.[Id], o.[OrderDate], os.[Name]");
        }
    }
}
```

<span data-ttu-id="3ca63-151">重要な点は、動的な型を使用することで、返されるデータ コレクションが ViewModel として動的にアセンブルされることです。</span><span class="sxs-lookup"><span data-stu-id="3ca63-151">The important point is that by using a dynamic type, the returned collection of data is dynamically assembled as the ViewModel.</span></span>

<span data-ttu-id="3ca63-152">**長所 :** この方法では、クエリの SQL 文を更新するたびに静的な ViewModel クラスを変更する必要性が低くなります。したがって、この設計方法は非常にアジャイルなコーディング方法であり、簡単で、将来の変更に合わせてすばやく進化します。</span><span class="sxs-lookup"><span data-stu-id="3ca63-152">**Pros:** This approach reduces the need to modify static ViewModel classes whenever you update the SQL sentence of a query, making this design approach pretty agile when coding, straightforward, and quick to evolve in regard to future changes.</span></span>

<span data-ttu-id="3ca63-153">**短所 :** 長期的に見ると、動的な型はクライアント アプリのサービスの明確性と互換性に悪影響を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ca63-153">**Cons:** In the long term, dynamic types can negatively impact the clarity and the compatibility of a service with client apps.</span></span> <span data-ttu-id="3ca63-154">さらに、Swashbuckle のようなミドルウェア ソフトウェアでは、動的な型を使用する場合に戻り値の型で同じレベルのドキュメントを提供できません。</span><span class="sxs-lookup"><span data-stu-id="3ca63-154">In addition, middleware software like Swashbuckle cannot provide the same level of documentation on returned types if using dynamic types.</span></span>

### <a name="viewmodel-as-predefined-dto-classes"></a><span data-ttu-id="3ca63-155">定義済み DTO クラスとしての ViewModel</span><span class="sxs-lookup"><span data-stu-id="3ca63-155">ViewModel as predefined DTO classes</span></span>

<span data-ttu-id="3ca63-156">**長所** :明示的な DTO クラスに基づく "コントラクト" のように、静的な定義済み ViewModel クラスを使用することは、パブリック API だけでなく、長期的なマイクロサービスにも確実に適しています。同じアプリケーションでのみ使用される場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="3ca63-156">**Pros**: Having static predefined ViewModel classes, like "contracts" based on explicit DTO classes, is definitely better for public APIs but also for long term microservices, even if they are only used by the same application.</span></span>

<span data-ttu-id="3ca63-157">Swagger の応答型を指定する場合は、戻り値の型として明示的な DTO クラスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca63-157">If you want to specify response types for Swagger, you need to use explicit DTO classes as the return type.</span></span> <span data-ttu-id="3ca63-158">したがって、定義済み DTO クラスを使用すれば、Swagger からより豊富な情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-158">Therefore, predefined DTO classes allow you to offer richer information from Swagger.</span></span> <span data-ttu-id="3ca63-159">これにより、API 利用時の API のドキュメントと互換性が改善されます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-159">That improves the API documentation and compatibility when consuming an API.</span></span>

<span data-ttu-id="3ca63-160">**短所** :前述のとおり、コードを更新する場合、DTO クラスを更新するためにさらにいくつかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ca63-160">**Cons**: As mentioned earlier, when updating the code, it takes some more steps to update the DTO classes.</span></span>

<span data-ttu-id="3ca63-161">*経験に基づくヒント:* 開発段階の初期には非常に簡単でアジャイルであるため、eShopOnContainers のオーダリング マイクロサービスに実装したクエリには、動的な ViewModel を使用して開発を開始しました。</span><span class="sxs-lookup"><span data-stu-id="3ca63-161">*Tip based on our experience*: In the queries implemented at the Ordering microservice in eShopOnContainers, we started developing by using dynamic ViewModels as it was very straightforward and agile on the early development stages.</span></span> <span data-ttu-id="3ca63-162">しかし、開発が安定した後で、API をリファクタリングし、ViewModel に静的な、または定義済みの DTO を使用することにしました。これは、マイクロサービスのコンシューマーが、"コントラクト" として使用される、明示的な DTO 型を認識しやすいためです。</span><span class="sxs-lookup"><span data-stu-id="3ca63-162">But, once the development was stabilized, we chose to refactor the APIs and use static or pre-defined DTOs for the ViewModels, because it is clearer for the microservice's consumers to know explicit DTO types, used as "contracts".</span></span>

<span data-ttu-id="3ca63-163">次の例では、明示的な ViewModel DTO クラスである OrderSummary クラスを使用して、クエリでどのようにデータが返されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-163">In the following example, you can see how the query is returning data by using an explicit ViewModel DTO class: the OrderSummary class.</span></span>

```csharp
using Dapper;
using Microsoft.Extensions.Configuration;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Dynamic;
using System.Collections.Generic;

public class OrderQueries : IOrderQueries
{
  public async Task<IEnumerable<OrderSummary>> GetOrdersAsync()
    {
        using (var connection = new SqlConnection(_connectionString))
        {
            connection.Open();
            return await connection.QueryAsync<OrderSummary>(
                  @"SELECT o.[Id] as ordernumber,
                  o.[OrderDate] as [date],os.[Name] as [status],
                  SUM(oi.units*oi.unitprice) as total
                  FROM [ordering].[Orders] o
                  LEFT JOIN[ordering].[orderitems] oi ON  o.Id = oi.orderid
                  LEFT JOIN[ordering].[orderstatus] os on o.OrderStatusId = os.Id
                  GROUP BY o.[Id], o.[OrderDate], os.[Name]
                  ORDER BY o.[Id]");
        }
    }
}
```

#### <a name="describe-response-types-of-web-apis"></a><span data-ttu-id="3ca63-164">Web API の応答型の説明</span><span class="sxs-lookup"><span data-stu-id="3ca63-164">Describe response types of Web APIs</span></span>

<span data-ttu-id="3ca63-165">Web API とマイクロサービスを利用する開発者は、何が返されるか (具体的には、応答型とエラー コード (標準以外の場合)) を最も考慮します。</span><span class="sxs-lookup"><span data-stu-id="3ca63-165">Developers consuming web APIs and microservices are most concerned with what is returned — specifically response types and error codes (if not standard).</span></span> <span data-ttu-id="3ca63-166">これらは、XML のコメントおよびデータ注釈で処理されます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-166">These are handled in the XML comments and data annotations.</span></span>

<span data-ttu-id="3ca63-167">Swagger UI に適切なドキュメントがないと、コンシューマーは返される型や返される可能性のある HTTP コードを認識できません。</span><span class="sxs-lookup"><span data-stu-id="3ca63-167">Without proper documentation in the Swagger UI, the consumer lacks knowledge of what types are being returned or what HTTP codes can be returned.</span></span> <span data-ttu-id="3ca63-168">この問題は <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType> を追加することで解決できるため、次のコードに示すように、Swashbuckle は API の戻りモデルと値に関する情報をより多く生成できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-168">That problem is fixed by adding the <xref:Microsoft.AspNetCore.Mvc.ProducesResponseTypeAttribute?displayProperty=nameWithType>, so Swashbuckle can generate richer information about the API return model and values, as shown in the following code:</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class OrdersController : Controller
    {
        //Additional code...
        [Route("")]
        [HttpGet]
        [ProducesResponseType(typeof(IEnumerable<OrderSummary>),
            (int)HttpStatusCode.OK)]
        public async Task<IActionResult> GetOrders()
        {
            var userid = _identityService.GetUserIdentity();
            var orders = await _orderQueries
                .GetOrdersFromUserAsync(Guid.Parse(userid));
            return Ok(orders);
        }
    }
}
```

<span data-ttu-id="3ca63-169">ただし、`ProducesResponseType` 属性では型として動的な型を使用できず、次の例に示すように、`OrderSummary` ViewModel DTO などの明示的な型を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ca63-169">However, the `ProducesResponseType` attribute cannot use dynamic as a type but requires to use explicit types, like the `OrderSummary` ViewModel DTO, shown in the following example:</span></span>

```csharp
public class OrderSummary
{
    public int ordernumber { get; set; }
    public DateTime date { get; set; }
    public string status { get; set; }
    public double total { get; set; }
}
```

<span data-ttu-id="3ca63-170">これが、長期的に見ると、明示的な戻り値の型が動的な型より適しているもう 1 つの理由です。</span><span class="sxs-lookup"><span data-stu-id="3ca63-170">This is another reason why explicit returned types are better than dynamic types, in the long term.</span></span> <span data-ttu-id="3ca63-171">`ProducesResponseType` 属性を使用する場合、200、400 などの考えられる HTTP エラー/コードで予期できる結果を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-171">When using the `ProducesResponseType` attribute, you can also specify what is the expected outcome in regards possible HTTP errors/codes, like 200, 400, etc.</span></span>

<span data-ttu-id="3ca63-172">次のイメージで、Swagger UI にどのように ResponseType 情報が表示されるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-172">In the following image, you can see how Swagger UI shows the ResponseType information.</span></span>

![Ordering API 用の Swagger UI ページのスクリーンショット。](./media/cqrs-microservice-reads/swagger-ordering-http-api.png)

<span data-ttu-id="3ca63-174">**図 7-5**。</span><span class="sxs-lookup"><span data-stu-id="3ca63-174">**Figure 7-5**.</span></span> <span data-ttu-id="3ca63-175">Web API からの応答型と考えられる HTTP ステータス コードを示す Swagger UI</span><span class="sxs-lookup"><span data-stu-id="3ca63-175">Swagger UI showing response types and possible HTTP status codes from a Web API</span></span>

<span data-ttu-id="3ca63-176">上のイメージでは、ViewModel 型に基づくいくつかの値の例と、返される可能性のある HTTP ステータス コードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3ca63-176">You can see in the image above some example values based on the ViewModel types plus the possible HTTP status codes that can be returned.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3ca63-177">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="3ca63-177">Additional resources</span></span>

- <span data-ttu-id="3ca63-178">**Dapper**</span><span class="sxs-lookup"><span data-stu-id="3ca63-178">**Dapper**</span></span>  
 <https://github.com/StackExchange/dapper-dot-net>

- <span data-ttu-id="3ca63-179">**Julie Lerman。データ ポイント - Dapper、Entity Framework、およびハイブリッド アプリ (MSDN マガジンの記事)**</span><span class="sxs-lookup"><span data-stu-id="3ca63-179">**Julie Lerman. Data Points - Dapper, Entity Framework and Hybrid Apps (MSDN magazine article)**</span></span>  
  <https://docs.microsoft.com/archive/msdn-magazine/2016/may/data-points-dapper-entity-framework-and-hybrid-apps>

- <span data-ttu-id="3ca63-180">**Swagger を使用する ASP.NET Core Web API のヘルプ ページ**</span><span class="sxs-lookup"><span data-stu-id="3ca63-180">**ASP.NET Core Web API Help Pages using Swagger**</span></span>  
  <https://docs.microsoft.com/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio>

>[!div class="step-by-step"]
><span data-ttu-id="3ca63-181">[前へ](eshoponcontainers-cqrs-ddd-microservice.md)
>[次へ](ddd-oriented-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="3ca63-181">[Previous](eshoponcontainers-cqrs-ddd-microservice.md)
[Next](ddd-oriented-microservice.md)</span></span>
