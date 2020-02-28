---
title: Ocelot を使った API ゲートウェイの実装
description: Ocelot を使用して API ゲートウェイを実装する方法と、コンテナー ベースの環境で Ocelot を使用する方法について説明します。
ms.date: 01/30/2020
ms.openlocfilehash: 0eb834829a418cfa1ccdf13c5fc8849f6855c4ba
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502414"
---
# <a name="implement-api-gateways-with-ocelot"></a><span data-ttu-id="f5b27-103">Ocelot を使った API ゲートウェイの実装</span><span class="sxs-lookup"><span data-stu-id="f5b27-103">Implement API Gateways with Ocelot</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5b27-104">現在、参照マイクロサービス アプリケーション [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) では、[Envoy](https://www.envoyproxy.io/) が提供する機能を使用して、前に参照された [Ocelot](https://github.com/ThreeMammals/Ocelot) ではなく、API ゲートウェイを実装しています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-104">The reference microservice application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) is currently using features provided by [Envoy](https://www.envoyproxy.io/) to implement the API Gateway instead of the earlier referenced [Ocelot](https://github.com/ThreeMammals/Ocelot).</span></span>
> <span data-ttu-id="f5b27-105">この設計が選択されたのは、eShopOnContainers に実装される新しい gRPC サービス間通信で必要な WebSocket プロトコルのサポートが Envoy に組み込まれているためです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-105">We made this design choice because of Envoy's built-in support for the WebSocket protocol, required by the new gRPC inter-service communications implemented in eShopOnContainers.</span></span>
> <span data-ttu-id="f5b27-106">ただし、ガイドにこのセクションが含まれているのは、Ocelot を実稼働レベルのシナリオに適したシンプルで有能な軽量の API ゲートウェイとして 検討できるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-106">However, we've retained this section in the guide so you can consider Ocelot as a simple, capable, and lightweight API Gateway suitable for production-grade scenarios.</span></span>

## <a name="architect-and-design-your-api-gateways"></a><span data-ttu-id="f5b27-107">API ゲートウェイのアーキテクチャとデザイン</span><span class="sxs-lookup"><span data-stu-id="f5b27-107">Architect and design your API Gateways</span></span>

<span data-ttu-id="f5b27-108">次のアーキテクチャ図は、eShopOnContainers で Ocelot を使用して API ゲートウェイがどのように実装されたかを示しています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-108">The following architecture diagram shows how API Gateways were implemented with Ocelot in eShopOnContainers.</span></span>

![eShopOnContainers アーキテクチャを示す図。](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

<span data-ttu-id="f5b27-110">**図 6-28**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-110">**Figure 6-28**.</span></span> <span data-ttu-id="f5b27-111">API ゲートウェイを使用した eShopOnContainers アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f5b27-111">eShopOnContainers architecture with API Gateways</span></span>

<span data-ttu-id="f5b27-112">この図では、アプリケーション全体を 1 つの Docker ホスト、または "Docker for Windows" または "Docker for Mac" を搭載した開発 PC に配置する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-112">That diagram shows how the whole application is deployed into a single Docker host or development PC with "Docker for Windows" or "Docker for Mac".</span></span> <span data-ttu-id="f5b27-113">ただし、どのオーケストレーターでもそれに配置する方法は似ていますが、図のコンテナーはいずれも、オーケストレーターでスケールアウトする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-113">However, deploying into any orchestrator would be similar, but any container in the diagram could be scaled out in the orchestrator.</span></span>

<span data-ttu-id="f5b27-114">さらに、データベース、キャッシュ、メッセージ ブローカーなどのインフラストラクチャ資産は、オーケストレーターからオフロードして、Azure SQL Database、Azure Cosmos DB、Azure Redis、Azure Service Bus、またはオンプレミスの任意の HA クラスタリング ソリューションのような、インフラストラクチャの可用性が高いシステムに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-114">In addition, the infrastructure assets such as databases, cache, and message brokers should be offloaded from the orchestrator and deployed into high available systems for infrastructure, like Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus, or any HA clustering solution on-premises.</span></span>

<span data-ttu-id="f5b27-115">また、図からわかるように、複数の API ゲートウェイを持つことで、複数の開発チームがマイクロサービスと独自の関連する API ゲートウェイを開発して配置するときに、自律的に行うことができるようになります (この例では、マーケティング機能とショッピング機能)。</span><span class="sxs-lookup"><span data-stu-id="f5b27-115">As you can also notice in the diagram, having several API Gateways allows multiple development teams to be autonomous (in this case Marketing features vs. Shopping features) when developing and deploying their microservices plus their own related API Gateways.</span></span>

<span data-ttu-id="f5b27-116">1 つのポイントが複数の開発チームによって更新されることを意味するモノリシック API ゲートウェイがあれば、アプリケーションの 1 つの部分にすべてのマイクロサービスを組み合わせることができたかもしれません。</span><span class="sxs-lookup"><span data-stu-id="f5b27-116">If you had a single monolithic API Gateway that would mean a single point to be updated by several development teams, which could couple all the microservices with a single part of the application.</span></span>

<span data-ttu-id="f5b27-117">デザインにさらに踏み込むと、きめ細かい API ゲートウェイを、選択したアーキテクチャに応じて、1 つのビジネス マイクロサービスに制限できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-117">Going much further in the design, sometimes a fine-grained API Gateway can also be limited to a single business microservice depending on the chosen architecture.</span></span> <span data-ttu-id="f5b27-118">ビジネスまたはドメインで API ゲートウェイの境界を示すとデザインが良くなります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-118">Having the API Gateway's boundaries dictated by the business or domain will help you to get a better design.</span></span>

<span data-ttu-id="f5b27-119">たとえば、API ゲートウェイ層を細分化することは、マイクロサービスに基づくより高度な複合 UI アプリケーションで特に役立つ場合があります。これは、きめ細かい API ゲートウェイの概念が UI コンポジション サービスと似ているためです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-119">For instance, fine granularity in the API Gateway tier can be especially useful for more advanced composite UI applications that are based on microservices, because the concept of a fine-grained API Gateway is similar to a UI composition service.</span></span>

<span data-ttu-id="f5b27-120">詳細は前のセクション「[マイクロサービスを基にしている複合 UI を作成する](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md)」で取り上げています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-120">We delve into more details in the previous section [Creating composite UI based on microservices](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span></span>

<span data-ttu-id="f5b27-121">重要な点は、多くの中規模および大規模なアプリケーションの場合、カスタム ビルドの API ゲートウェイ製品の使用は、通常は有効なアプローチですが、API ゲートウェイで自立型マイクロサービスを作成している複数の開発チームに対して、複数の独立した構成領域を許可している場合を除き、単一のモノシリック アグリゲーターや一意の中央カスタム API ゲートウェイとしては適切なアプローチではないことです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-121">As key takeaway, for many medium- and large-size applications, using a custom-built API Gateway product is usually a good approach, but not as a single monolithic aggregator or unique central custom API Gateway unless that API Gateway allows multiple independent configuration areas for the several development teams creating autonomous microservices.</span></span>

### <a name="sample-microservicescontainers-to-reroute-through-the-api-gateways"></a><span data-ttu-id="f5b27-122">API ゲートウェイ経由で経路変更するマイクロサービス/コンテナーのサンプル</span><span class="sxs-lookup"><span data-stu-id="f5b27-122">Sample microservices/containers to reroute through the API Gateways</span></span>

<span data-ttu-id="f5b27-123">例として、eShopOnContainers には、次の図に示すように、API ゲートウェイ経由で公開する必要がある約 6 種類の内部のマイクロサービスがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-123">As an example, eShopOnContainers has around six internal microservice-types that have to be published through the API Gateways, as shown in the following image.</span></span>

![Services フォルダーのスクリーンショット。そのサブフォルダーを確認できます。](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

<span data-ttu-id="f5b27-125">**図 6-29**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-125">**Figure 6-29**.</span></span> <span data-ttu-id="f5b27-126">Visual Studio の eShopOnContainers ソリューション内のマイクロサービス フォルダー</span><span class="sxs-lookup"><span data-stu-id="f5b27-126">Microservice folders in eShopOnContainers solution in Visual Studio</span></span>

<span data-ttu-id="f5b27-127">ID サービスについては、システム内の唯一の横断的関心事のため、デザインでは API ゲートウェイのルーティングから除外されていますが、Ocelot を使用すると、経路変更リストの一部として含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-127">About the Identity service, in the design it's left out of the API Gateway routing because it's the only cross-cutting concern in the system, although with Ocelot it's also possible to include it as part of the rerouting lists.</span></span>

<span data-ttu-id="f5b27-128">コードからわかるように、これらのサービスはすべて、ASP.NET Core Web API サービスとして現在実装されています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-128">All those services are currently implemented as ASP.NET Core Web API services, as you can tell from the code.</span></span> <span data-ttu-id="f5b27-129">マイクロサービスの 1 つに注目してみましょう。Catalog マイクロサービス コードなどがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-129">Let's focus on one of the microservices like the Catalog microservice code.</span></span>

![Catalog.API プロジェクトのコンテンツを示すソリューション エクスプローラーのスクリーンショット。](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

<span data-ttu-id="f5b27-131">**図 6-30**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-131">**Figure 6-30**.</span></span> <span data-ttu-id="f5b27-132">サンプル Web API マイクロサービス (Catalog マイクロサービス)</span><span class="sxs-lookup"><span data-stu-id="f5b27-132">Sample Web API microservice (Catalog microservice)</span></span>

<span data-ttu-id="f5b27-133">Catalog マイクロサービスは、複数のコントローラーと次のコードにあるようなメソッドを持つ一般的な ASP.NET Core Web API プロジェクトであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-133">You can see that the Catalog microservice is a typical ASP.NET Core Web API project with several controllers and methods like in the following code.</span></span>

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

<span data-ttu-id="f5b27-134">HTTP 要求は、マイクロサービス データベースと追加の必須アクションにアクセスするような C# コードの実行で終了します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-134">The HTTP request will end up running that kind of C# code accessing the microservice database and any additional required action.</span></span>

<span data-ttu-id="f5b27-135">マイクロサービス URL については、コンテナーがローカル開発用 PC (ローカル Docker ホスト) に配置されると、各マイクロサービスのコンテナーには、次の dockerfile にあるように、その dockerfile で指定された内部ポート (通常はポート 80) が常に与えられます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-135">Regarding the microservice URL, when the containers are deployed in your local development PC (local Docker host), each microservice's container has always an internal port (usually port 80) specified in its dockerfile, as in the following dockerfile:</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
```

<span data-ttu-id="f5b27-136">コードに示されているポート 80 は、Docker ホスト内の内部ポートであるため、クライアント アプリが到達することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5b27-136">The port 80 shown in the code is internal within the Docker host, so it can't be reached by client apps.</span></span>

<span data-ttu-id="f5b27-137">クライアント アプリがアクセスできるのは、`docker-compose` を使用して配置したときに公開された外部ポートだけです (このようなポートがある場合に)。</span><span class="sxs-lookup"><span data-stu-id="f5b27-137">Client apps can access only the external ports (if any) published when deploying with `docker-compose`.</span></span>

<span data-ttu-id="f5b27-138">運用環境に配置するときに、このような外部ポートを公開しないでください。</span><span class="sxs-lookup"><span data-stu-id="f5b27-138">Those external ports shouldn't be published when deploying to a production environment.</span></span> <span data-ttu-id="f5b27-139">クライアント アプリとマイクロサービス間の直接通信を回避するために、API ゲートウェイを使用する理由がここにあります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-139">This is precisely why you want to use the API Gateway, to avoid the direct communication between the client apps and the microservices.</span></span>

<span data-ttu-id="f5b27-140">ただし、開発時には、マイクロサービス/コンテナーに直接アクセスして、Swagger を経由して実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-140">However, when developing, you want to access the microservice/container directly and run it through Swagger.</span></span> <span data-ttu-id="f5b27-141">そのため、eShopOnContainers では、API ゲートウェイまたはクライアント アプリで使われなくなっても、外部ポートは指定されたままになります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-141">That's why in eShopOnContainers, the external ports are still specified even when they won't be used by the API Gateway or the client apps.</span></span>

<span data-ttu-id="f5b27-142">Catalog マイクロサービスの `docker-compose.override.yml` ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-142">Here's an example of the `docker-compose.override.yml` file for the Catalog microservice:</span></span>

```yml
catalog-api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

<span data-ttu-id="f5b27-143">docker-compose.override.yml の構成では、Catalog コンテナーの内部ポートがポート 80 になっていますが、外部アクセスのポートは 5101 になっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-143">You can see how in the docker-compose.override.yml configuration the internal port for the Catalog container is port 80, but the port for external access is 5101.</span></span> <span data-ttu-id="f5b27-144">ただし、このポートは、API ゲートウェイを使用する場合には、アプリケーションでは使用せずに、Catalog マイクロサービスのデバッグ、実行、テストのためにだけ使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-144">But this port shouldn't be used by the application when using an API Gateway, only to debug, run, and test just the Catalog microservice.</span></span>

<span data-ttu-id="f5b27-145">マイクロサービスの適切な運用配置環境は、Kubernetes や Service Fabric などのオーケストレーターであるため、通常は docker-compose を使用して運用環境に配置することはありません。</span><span class="sxs-lookup"><span data-stu-id="f5b27-145">Normally, you won't be deploying with docker-compose into a production environment because the right production deployment environment for microservices is an orchestrator like Kubernetes or Service Fabric.</span></span> <span data-ttu-id="f5b27-146">これらの環境に配置する場合は、マイクロサービスに対してどの外部ポートも直接公開しない別の構成ファイルを使用しますが、API ゲートウェイからのリバース プロキシは常に使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-146">When deploying to those environments you use different configuration files where you won't publish directly any external port for the microservices but, you'll always use the reverse proxy from the API Gateway.</span></span>

<span data-ttu-id="f5b27-147">ローカルの Docker ホストで Catalog マイクロサービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-147">Run the catalog microservice in your local Docker host.</span></span> <span data-ttu-id="f5b27-148">Visual Studio から完全な eShopOnContainers ソリューションを実行する (docker-compose ファイル内のすべてのサービスを実行する) か、`docker-compose.yml` と `docker-compose.override.yml` が配置されているフォルダーにある CMD または PowerShell で次の docker-compose コマンドを使用して Catalog マイクロサービスを起動します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-148">Either run the full eShopOnContainers solution from Visual Studio (it runs all the services in the docker-compose files), or start the Catalog microservice with the following docker-compose command in CMD or PowerShell positioned at the folder where the `docker-compose.yml` and `docker-compose.override.yml` are placed.</span></span>

```console
docker-compose run --service-ports catalog-api
```

<span data-ttu-id="f5b27-149">このコマンドでは、catalog.api サービス コンテナーと docker-compose.yml に指定されている依存関係のみが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-149">This command only runs the catalog-api service container plus dependencies that are specified in the docker-compose.yml.</span></span> <span data-ttu-id="f5b27-150">この例では、SQL Server コンテナーと RabbitMQ コンテナーです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-150">In this case, the SQL Server container and RabbitMQ container.</span></span>

<span data-ttu-id="f5b27-151">こうすると、"外部" ポート (この例では `http://localhost:5101/swagger`) を経由して直接アクセスする Swagger UI を使用して、Catalog マイクロサービスに直接アクセスして、そのメソッドを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-151">Then, you can directly access the Catalog microservice and see its methods through the Swagger UI accessing directly through that "external" port, in this case `http://localhost:5101/swagger`:</span></span>

![Catalog.API REST API を表示している Swagger UI のスクリーンショット。](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

<span data-ttu-id="f5b27-153">**図 6-31**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-153">**Figure 6-31**.</span></span> <span data-ttu-id="f5b27-154">Swagger UI を使用した Catalog マイクロサービスのテスト</span><span class="sxs-lookup"><span data-stu-id="f5b27-154">Testing the Catalog microservice with its Swagger UI</span></span>

<span data-ttu-id="f5b27-155">この時点で、Visual Studio で C# コードにブレークポイントを設定し、Swagger UI で公開されるメソッドを使用してマイクロサービスをテストし、最後に `docker-compose down` コマンドを使用してすべてをクリーンアップすることは可能です。</span><span class="sxs-lookup"><span data-stu-id="f5b27-155">At this point, you could set a breakpoint in C# code in Visual Studio, test the microservice with the methods exposed in Swagger UI, and finally clean-up everything with the `docker-compose down` command.</span></span>

<span data-ttu-id="f5b27-156">しかしながら、マイクロサービスへの直接アクセス通信 (この例では外部ポート 5101 を経由) こそが、アプリケーションで回避したいことなのです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-156">However, direct-access communication to the microservice, in this case through the external port 5101, is precisely what you want to avoid in your application.</span></span> <span data-ttu-id="f5b27-157">また、API ゲートウェイ (この例では Ocelot ) の間接参照の追加レベルを設定することで、これを回避できます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-157">And you can avoid that by setting the additional level of indirection of the API Gateway (Ocelot, in this case).</span></span> <span data-ttu-id="f5b27-158">これにより、クライアント アプリがマイクロサービスに直接アクセスすることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-158">That way, the client app won't directly access the microservice.</span></span>

## <a name="implementing-your-api-gateways-with-ocelot"></a><span data-ttu-id="f5b27-159">Ocelot を使った API ゲートウェイの実装</span><span class="sxs-lookup"><span data-stu-id="f5b27-159">Implementing your API Gateways with Ocelot</span></span>

<span data-ttu-id="f5b27-160">Ocelot は、基本的に特定の順序で適用できるミドルウェアのセットです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-160">Ocelot is basically a set of middlewares that you can apply in a specific order.</span></span>

<span data-ttu-id="f5b27-161">Ocelot は、ASP.NET Core でのみ動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-161">Ocelot is designed to work with ASP.NET Core only.</span></span> <span data-ttu-id="f5b27-162">これは `netstandard2.0` をターゲットにしているため、.NET Standard 2.0 がサポートされていれば、どこでも使用できます。これには、.NET Core 2.0 ランタイムと .NET Framework 4.6.1 ランタイム以降が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-162">It targets `netstandard2.0` so it can be used anywhere .NET Standard 2.0 is supported, including .NET Core 2.0 runtime and .NET Framework 4.6.1 runtime and up.</span></span>

<span data-ttu-id="f5b27-163">[Ocelot の NuGet パッケージ](https://www.nuget.org/packages/Ocelot/)を使用して、Visual Studio から ASP.NET Core プロジェクトに Ocelot とその依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f5b27-163">You install Ocelot and its dependencies in your ASP.NET Core project with [Ocelot's NuGet package](https://www.nuget.org/packages/Ocelot/), from Visual Studio.</span></span>

```powershell
Install-Package Ocelot
```

<span data-ttu-id="f5b27-164">eShopOnContainers では、その API ゲートウェイの実装はシンプルな ASP.NET Core WebHost プロジェクトであり、次の図に示すように、Ocelot のミドルウェアによってすべての API ゲートウェイ機能が処理されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-164">In eShopOnContainers, its API Gateway implementation is a simple ASP.NET Core WebHost project, and Ocelot’s middleware handles all the API Gateway features, as shown in the following image:</span></span>

![Ocelot API ゲートウェイ プロジェクトを表示しているソリューション エクスプローラーのスクリーンショット。](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

<span data-ttu-id="f5b27-166">**図 6-32**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-166">**Figure 6-32**.</span></span> <span data-ttu-id="f5b27-167">eShopOnContainers の OcelotApiGw 基本プロジェクト</span><span class="sxs-lookup"><span data-stu-id="f5b27-167">The OcelotApiGw base project in eShopOnContainers</span></span>

<span data-ttu-id="f5b27-168">この ASP.NET Core WebHost プロジェクトは基本的に、`Program.cs` と `Startup.cs` の 2 つのシンプルなファイルで構築されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-168">This ASP.NET Core WebHost project is basically built with two simple files:  `Program.cs` and `Startup.cs`.</span></span>

<span data-ttu-id="f5b27-169">Program.cs では、一般的な ASP.NET Core BuildWebHost を作成して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-169">The Program.cs just needs to create and configure the typical ASP.NET Core BuildWebHost.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

<span data-ttu-id="f5b27-170">ここで Ocelot について重要な点は、`AddJsonFile()` メソッドを通じてビルダーに提供する必要がある `configuration.json` ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-170">The important point here for Ocelot is the `configuration.json` file that you must provide to the builder through the `AddJsonFile()` method.</span></span> <span data-ttu-id="f5b27-171">その `configuration.json` で、すべての API ゲートウェイの ReRoute を指定します。つまり、特定のポートを持つ外部エンドポイントと、通常は別のポートを使用する相関内部エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-171">That `configuration.json` is where you specify all the API Gateway ReRoutes, meaning the external endpoints with specific ports and the correlated internal endpoints, usually using different ports.</span></span>

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

<span data-ttu-id="f5b27-172">構成には 2 つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-172">There are two sections to the configuration.</span></span> <span data-ttu-id="f5b27-173">ReRoute の配列と GlobalConfiguration です。</span><span class="sxs-lookup"><span data-stu-id="f5b27-173">An array of ReRoutes and a GlobalConfiguration.</span></span> <span data-ttu-id="f5b27-174">ReRoute は、Ocelot にアップストリーム要求の処理方法を指示するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-174">The ReRoutes are the objects that tell Ocelot how to treat an upstream request.</span></span> <span data-ttu-id="f5b27-175">グローバル構成を使用すると、ReRoute 固有の設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-175">The Global configuration allows overrides of ReRoute specific settings.</span></span> <span data-ttu-id="f5b27-176">ReRoute 固有の設定をたくさん管理しない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f5b27-176">It's useful if you don't want to manage lots of ReRoute specific settings.</span></span>

<span data-ttu-id="f5b27-177">eShopOnContainers のうちの 1 つの API ゲートウェイから、[ReRoute 構成ファイル](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json)の単純な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-177">Here's a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.</span></span>

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

<span data-ttu-id="f5b27-178">Ocelot API ゲートウェイの主な機能は、HTTP 要求を受け取り、それらを (現在は別の HTTP 要求として) ダウンストリーム サービスに転送することです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-178">The main functionality of an Ocelot API Gateway is to take incoming HTTP requests and forward them on to a downstream service, currently as another HTTP request.</span></span> <span data-ttu-id="f5b27-179">Ocelot では、ある要求を別の場所にルーティングすることを ReRoute と説明しています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-179">Ocelot's describes the routing of one request to another as a ReRoute.</span></span>

<span data-ttu-id="f5b27-180">例として、Basket マイクロサービスの構成である、上記の configuration.json の ReRoute の 1 つに注目してみましょう。</span><span class="sxs-lookup"><span data-stu-id="f5b27-180">For instance, let's focus on one of the ReRoutes in the configuration.json from above, the configuration for the Basket microservice.</span></span>

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

<span data-ttu-id="f5b27-181">DownstreamPathTemplate、Scheme、および DownstreamHostAndPorts が、この要求の転送先となる内部マイクロサービスの URL を構成しています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-181">The DownstreamPathTemplate, Scheme, and DownstreamHostAndPorts make the internal microservice URL that this request will be forwarded to.</span></span>

<span data-ttu-id="f5b27-182">ポートは、サービスで使用される内部ポートです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-182">The port is the internal port used by the service.</span></span> <span data-ttu-id="f5b27-183">コンテナーを使用している場合、ポートはその dockerfile で指定されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-183">When using containers, the port specified at its dockerfile.</span></span>

<span data-ttu-id="f5b27-184">`Host` は、使用するサービスの名前解決に依存するサービス名です。</span><span class="sxs-lookup"><span data-stu-id="f5b27-184">The `Host` is a service name that depends on the service name resolution you are using.</span></span> <span data-ttu-id="f5b27-185">docker-compose を使用している場合、サービス名は、docker-compose ファイルで提供されるサービス名を使用する、Docker ホストにより提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-185">When using docker-compose, the services names are provided by the Docker Host, which is using the service names provided in the docker-compose files.</span></span> <span data-ttu-id="f5b27-186">Kubernetes や Service Fabric などのオーケストレーターを使用している場合、その名前は、DNS または各オーケストレーターで提供される名前解決で解決される必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-186">If using an orchestrator like Kubernetes or Service Fabric, that name should be resolved by the DNS or name resolution provided by each orchestrator.</span></span>

<span data-ttu-id="f5b27-187">DownstreamHostAndPorts は、要求の転送先となるすべてのダウンストリーム サービスのホストとポートを含む配列です。</span><span class="sxs-lookup"><span data-stu-id="f5b27-187">DownstreamHostAndPorts is an array that contains the host and port of any downstream services that you wish to forward requests to.</span></span> <span data-ttu-id="f5b27-188">通常、これには 1 つのエントリだけが含まれますが、要求をダウンストリーム サービスに負荷分散したい場合には、Ocelot を使用することで、複数のエントリを追加してロード バランサーを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-188">Usually this will just contain one entry but sometimes you might want to load balance requests to your downstream services and Ocelot lets you add more than one entry and then select a load balancer.</span></span> <span data-ttu-id="f5b27-189">ただし、Azure と任意のオーケストレーターを使用している場合は、クラウドとオーケストレーター インフラストラクチャを使用して負荷分散した方が良い場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-189">But if using Azure and any orchestrator it is probably a better idea to load balance with the cloud and orchestrator infrastructure.</span></span>

<span data-ttu-id="f5b27-190">UpstreamPathTemplate は、クライアントから特定の要求に対し、どの DownstreamPathTemplate を使用するかを識別するために Ocelot によって使用される URL です。</span><span class="sxs-lookup"><span data-stu-id="f5b27-190">The UpstreamPathTemplate is the URL that Ocelot will use to identify which DownstreamPathTemplate to use for a given request from the client.</span></span> <span data-ttu-id="f5b27-191">最後に、Ocelot が異なる要求 (GET、POST、PUT) を同じ URL に区別できるように、UpstreamHttpMethod が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-191">Finally, the UpstreamHttpMethod is used so Ocelot can distinguish between different requests (GET, POST, PUT) to the same URL.</span></span>

<span data-ttu-id="f5b27-192">この時点で、1 つまたは[複数のマージされた configuration.json ファイル](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files)を使用して 1 つの Ocelot API ゲートウェイ (ASP.NET Core WebHost) を持つことも、[Consul KV ストアに構成を格納](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul)することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-192">At this point, you could have a single Ocelot API Gateway (ASP.NET Core WebHost) using one or [multiple merged configuration.json files](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) or you can also store the [configuration in a Consul KV store](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span></span>

<span data-ttu-id="f5b27-193">ただし、アーキテクチャとデザインのセクションで紹介したように、自律型のマイクロサービスが本当に必要な場合は、その 1 つのモノリシック API ゲートウェイを複数の API ゲートウェイや Backend for Frontend (BFF) に分割した方がよい場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-193">But as introduced in the architecture and design sections, if you really want to have autonomous microservices, it might be better to split that single monolithic API Gateway into multiple API Gateways and/or BFF (Backend for Frontend).</span></span> <span data-ttu-id="f5b27-194">そのために、Docker コンテナーを使用してこのアプローチを実装する方法を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="f5b27-194">For that purpose, let's see how to implement that approach with Docker containers.</span></span>

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a><span data-ttu-id="f5b27-195">1 つの Docker コンテナー イメージを使用して、複数の異なる API ゲートウェイ/BFF コンテナーの種類を実行する</span><span class="sxs-lookup"><span data-stu-id="f5b27-195">Using a single Docker container image to run multiple different API Gateway / BFF container types</span></span>

<span data-ttu-id="f5b27-196">eShopOnContainers では、Ocelot API ゲートウェイと共に 1 つの Docker コンテナー イメージを使用していますが、その後、実行時、サービスごとに異なる PC フォルダーにアクセスする Docker ボリュームを使用し、configuration.json ファイルを提供することで、API ゲートウェイ/BFF コンテナーの種類ごとに異なるサービス/コンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-196">In eShopOnContainers, we're using a single Docker container image with the Ocelot API Gateway but then, at run time, we create different services/containers for each type of API-Gateway/BFF by providing a different configuration.json file, using a docker volume to access a different PC folder for each service.</span></span>

![すべての API ゲートウェイに対する単一 Ocelot ゲートウェイの Docker イメージの図。](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

<span data-ttu-id="f5b27-198">**図 6-33**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-198">**Figure 6-33**.</span></span> <span data-ttu-id="f5b27-199">複数の API ゲートウェイの種類で 1 つの Ocelot Docker イメージを再利用する</span><span class="sxs-lookup"><span data-stu-id="f5b27-199">Reusing a single Ocelot Docker image across multiple API Gateway types</span></span>

<span data-ttu-id="f5b27-200">eShopOnContainers では、"OcelotApiGw" という名前のプロジェクトと、docker-compose.yml ファイルで指定されたイメージ名 "eshop/ocelotapigw" を使用して、"汎用 Ocelot API ゲートウェイ Docker イメージ" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-200">In eShopOnContainers, the "Generic Ocelot API Gateway Docker Image" is created with the project named 'OcelotApiGw' and the image name "eshop/ocelotapigw" that is specified in the docker-compose.yml file.</span></span> <span data-ttu-id="f5b27-201">次に、Docker に配置すると、次の docker-compose.yml ファイルからの抜粋に示されているように、同じ Docker イメージから作成された 4 つの API ゲートウェイ コンテナーができます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-201">Then, when deploying to Docker, there will be four API-Gateway containers created from that same Docker image, as shown in the following extract from the docker-compose.yml file.</span></span>

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

<span data-ttu-id="f5b27-202">さらに、次の docker-compose.override.yml ファイルでわかるように、API ゲートウェイのこれらのコンテナーの唯一の違いは Ocelot 構成ファイルです。これはサービス コンテナーごとに異なり、Docker ボリュームにより実行時に指定されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-202">Additionally, as you can see in the following docker-compose.override.yml file, the only difference between those API Gateway containers is the Ocelot configuration file, which is different for each service container and it's specified at runtime through a Docker volume.</span></span>

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

<span data-ttu-id="f5b27-203">次の Visual Studio エクスプローラーに示されているように、前のコードにより、特定のビジネス/BFF API ゲートウェイをそれぞれ定義するために必要な唯一のファイルは、configuration.json ファイルだけです。これは、4 つの API ゲートウェイが同じ Docker イメージに基づいているためです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-203">Because of that previous code, and as shown in the Visual Studio Explorer below, the only file needed to define each specific business/BFF API Gateway is just a configuration.json file, because the four API Gateways are based on the same Docker image.</span></span>

![configuration.json ファイルを含むすべての API ゲートウェイを示すスクリーンショット。](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

<span data-ttu-id="f5b27-205">**図 6-34**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-205">**Figure 6-34**.</span></span> <span data-ttu-id="f5b27-206">Ocelot で各 API ゲートウェイ/BFF を定義するために必要な唯一のファイル</span><span class="sxs-lookup"><span data-stu-id="f5b27-206">The only file needed to define each API Gateway / BFF with Ocelot is a configuration file</span></span>

<span data-ttu-id="f5b27-207">API ゲートウェイを複数の API ゲートウェイに分割することで、マイクロサービスの異なるサブセットに重点を置いているさまざまな開発チームが、独立した Ocelot 構成ファイルを使用して、独自の API ゲートウェイを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-207">By splitting the API Gateway into multiple API Gateways, different development teams focusing on different subsets of microservices can manage their own API Gateways by using independent Ocelot configuration files.</span></span> <span data-ttu-id="f5b27-208">くわえて、同時に同じ Ocelot Docker イメージを再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-208">Plus, at the same time they can reuse the same Ocelot Docker image.</span></span>

<span data-ttu-id="f5b27-209">ここで、(eShopOnContainers ServicesAndWebApps.sln ソリューションを開くとき、または "docker-compose up" を実行している場合に、VS に既定で含まれる) API ゲートウェイを使用して eShopOnContainers を実行すると、次のサンプル ルートが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-209">Now, if you run eShopOnContainers with the API Gateways (included by default in VS when opening eShopOnContainers-ServicesAndWebApps.sln solution or if running "docker-compose up"), the following sample routes will be performed.</span></span>

<span data-ttu-id="f5b27-210">たとえば、webshoppingapigw API ゲートウェイによって提供されるアップストリーム URL `http://localhost:5202/api/v1/c/catalog/items/2/` にアクセスすると、次のブラウザーにあるように、Docker ホスト内の内部ダウンストリーム URL `http://catalog-api/api/v1/2` からの同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-210">For instance, when visiting the upstream URL `http://localhost:5202/api/v1/c/catalog/items/2/` served by the webshoppingapigw API Gateway, you get the same result from the internal Downstream URL `http://catalog-api/api/v1/2` within the Docker host, as in the following browser.</span></span>

![API ゲートウェイ経由の応答を表示しているブラウザーのスクリーンショット。](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

<span data-ttu-id="f5b27-212">**図 6-35**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-212">**Figure 6-35**.</span></span> <span data-ttu-id="f5b27-213">API ゲートウェイによって提供される URL からマイクロサービスにアクセスする</span><span class="sxs-lookup"><span data-stu-id="f5b27-213">Accessing a microservice through a URL provided by the API Gateway</span></span>

<span data-ttu-id="f5b27-214">テストまたはデバッグの理由から、API ゲートウェイを通過せずに Catalog Docker コンテナーに直接アクセスしたい場合 (開発環境でのみ)、'catalog.api' は Docker ホスト (docker-compose サービス名により処理されるサービス検索) 内部の DNS 解決であるため、コンテナーに直接アクセスする唯一の方法は、次のブラウザーにある `http://localhost:5101/api/v1/Catalog/items/1` のように、開発テスト用にのみ提供される docker-compose.override.yml で公開されている外部ポートを経由することです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-214">Because of testing or debugging reasons, if you wanted to directly access to the Catalog Docker container (only at the development environment) without passing through the API Gateway, since 'catalog-api' is a DNS resolution internal to the Docker host (service discovery handled by docker-compose service names), the only way to directly access the container is through the external port published in the docker-compose.override.yml, which is provided only for development tests, such as `http://localhost:5101/api/v1/Catalog/items/1` in the following browser.</span></span>

![Catalog.api への直接応答を表示しているブラウザーのスクリーンショット。](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

<span data-ttu-id="f5b27-216">**図 6-36**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-216">**Figure 6-36**.</span></span> <span data-ttu-id="f5b27-217">テスト目的でのマイクロサービスへの直接アクセス</span><span class="sxs-lookup"><span data-stu-id="f5b27-217">Direct access to a microservice for testing purposes</span></span>

<span data-ttu-id="f5b27-218">ただし、アプリケーションは、ダイレクト ポートの "ショートカット" を経由してではなく、API ゲートウェイを経由してすべてのマイクロサービスにアクセスするように構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-218">But the application is configured so it accesses all the microservices through the API Gateways, not though the direct port "shortcuts".</span></span>

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a><span data-ttu-id="f5b27-219">eShopOnContainers でのゲートウェイ集計パターン</span><span class="sxs-lookup"><span data-stu-id="f5b27-219">The Gateway aggregation pattern in eShopOnContainers</span></span>

<span data-ttu-id="f5b27-220">前述のとおり、要求の集計を実装する柔軟な方法は、コードでカスタム サービスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-220">As introduced previously, a flexible way to implement requests aggregation is with custom services, by code.</span></span> <span data-ttu-id="f5b27-221">[Ocelot で要求の集計機能](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation)を使用して、要求の集計を実装することもできますが、十分な柔軟性が得られない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-221">You could also implement request aggregation with the [Request Aggregation feature in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), but it might not be as flexible as you need.</span></span> <span data-ttu-id="f5b27-222">そのため、eShopOnContainers で集計を実装するために選択した方法は、各アグリゲーターに明示的な ASP.NET Core Web API サービスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-222">Therefore, the selected way to implement aggregation in eShopOnContainers is with an explicit ASP.NET Core Web API service for each aggregator.</span></span>

<span data-ttu-id="f5b27-223">このアプローチに従うと、前出の簡略化されたグローバル アーキテクチャの図に示されていないアグリゲーター サービスを考慮に入れた場合、API ゲートウェイ コンポジション図は、実際にはもう少し拡張されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-223">According to that approach, the API Gateway composition diagram is in reality a bit more extended when considering the aggregator services that are not shown in the simplified global architecture diagram shown previously.</span></span>

<span data-ttu-id="f5b27-224">次の図では、アグリゲーター サービスがその関連する API ゲートウェイとどのように連携するかも確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-224">In the following diagram, you can also see how the aggregator services work with their related API Gateways.</span></span>

![アグリゲーター サービスを示している eShopOnContainers アーキテクチャの図。](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

<span data-ttu-id="f5b27-226">**図 6-37**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-226">**Figure 6-37**.</span></span> <span data-ttu-id="f5b27-227">アグリゲーター サービスを使用した eShopOnContainers アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f5b27-227">eShopOnContainers architecture with aggregator services</span></span>

<span data-ttu-id="f5b27-228">さらに拡大してみると、次の画像の "Shopping" 事業領域では、API ゲートウェイでアグリゲーター サービスを使用するとき、クライアント アプリとマイクロサービスの間の通信が減ることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-228">Zooming in further, on the "Shopping" business area in the following image, you can see that chattiness between the client apps and the microservices is reduced when using the aggregator services in the API Gateways.</span></span>

![eShopOnContainers アーキテクチャの拡大を示す図。](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

<span data-ttu-id="f5b27-230">**図 6-38**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-230">**Figure 6-38**.</span></span> <span data-ttu-id="f5b27-231">アグリゲーター サービスのビジョンの拡大表示</span><span class="sxs-lookup"><span data-stu-id="f5b27-231">Zoom in vision of the Aggregator services</span></span>

<span data-ttu-id="f5b27-232">API ゲートウェイから送信される可能性がある要求を図に示すと、複雑になる可能性があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-232">You can notice how when the diagram shows the possible requests coming from the API Gateways it can get complex.</span></span> <span data-ttu-id="f5b27-233">しかし、クライアント アプリの視点かラ見て、青の矢印がどのように簡略化されるかがわかります。アグリゲーター パターンを使用すると、頻繁な通信と通信の待機時間を減らすことで、最終的にユーザー エクスペリエンス、とりわけリモート アプリ (モバイルおよび SPA アプリ) のユーザー エクスペリエンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-233">Although you can see how the arrows in blue would be simplified, from a client apps perspective, when using the aggregator pattern by reducing chattiness and latency in the communication, ultimately significantly improving the user experience for the remote apps (mobile and SPA apps), especially.</span></span>

<span data-ttu-id="f5b27-234">"マーケティング" ビジネス領域とマイクロサービスの場合は、シンプルなユース ケースであるため、アグリゲーターを使用する必要はありませんでしたが、必要に応じて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-234">In the case of the "Marketing" business area and microservices, it is a simple use case so there was no need to use aggregators, but it could also be possible, if needed.</span></span>

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a><span data-ttu-id="f5b27-235">Ocelot API ゲートウェイでの認証と承認</span><span class="sxs-lookup"><span data-stu-id="f5b27-235">Authentication and authorization in Ocelot API Gateways</span></span>

<span data-ttu-id="f5b27-236">Ocelot API ゲートウェイでは、認証トークンを提供する [IdentityServer](https://identityserver.io/) を使用して、ASP.NET Core Web API サービスなどの認証サービスを API ゲートウェイの内側または外側に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-236">In an Ocelot API Gateway you can sit the authentication service, such as an ASP.NET Core Web API service using [IdentityServer](https://identityserver.io/) providing the auth token, either out or inside the API Gateway.</span></span>

<span data-ttu-id="f5b27-237">eShopOnContainers では、BFF に基づく境界とビジネス領域を持つ複数の API ゲートウェイを使用しているため、ID/認証サービス (次の図に黄色で強調表示) は、API ゲートウェイから除外されています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-237">Since eShopOnContainers is using multiple API Gateways with boundaries based on BFF and business areas, the Identity/Auth service is left out of the API Gateways, as highlighted in yellow in the following diagram.</span></span>

![API ゲートウェイの下にある ID マイクロサービスを示す図。](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

<span data-ttu-id="f5b27-239">**図 6-39**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-239">**Figure 6-39**.</span></span> <span data-ttu-id="f5b27-240">eShopOnContainers 内の ID サービスの位置</span><span class="sxs-lookup"><span data-stu-id="f5b27-240">Position of the Identity service in eShopOnContainers</span></span>

<span data-ttu-id="f5b27-241">ただし、Ocelot では、この別の図に示されているように、ID/認証マイクロサービスを API ゲートウェイの境界内に配置することもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-241">However, Ocelot also supports sitting the Identity/Auth microservice within the API Gateway boundary, as in this other diagram.</span></span>

![Ocelot API ゲートウェイの認証を示す図。](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

<span data-ttu-id="f5b27-243">**図 6-40**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-243">**Figure 6-40**.</span></span> <span data-ttu-id="f5b27-244">Ocelot での認証</span><span class="sxs-lookup"><span data-stu-id="f5b27-244">Authentication in Ocelot</span></span>

<span data-ttu-id="f5b27-245">前の図に示したように、ID マイクロサービスが API ゲートウェイ (AG) の下にある場合は、次のようになります。1) AG で ID マイクロサービスに認証トークンを要求し、2) ID マイクロサービスによって AG にトークンが返され、3-4) AG で認証トークンを使用してマイクロサービスに要求します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-245">As the previous diagram shows, when the Identity microservice is beneath the API gateway (AG): 1) AG requests an auth token from identity microservice, 2) The identity microservice returns token to AG, 3-4) AG requests from microservices using the auth token.</span></span> <span data-ttu-id="f5b27-246">eShopOnContainers アプリケーションによって API ゲートウェイが複数の BFF (Backend for Frontend) とビジネス領域の API ゲートウェイに分割されているため、もう 1 つのオプションは、横断的な問題に対して追加の API ゲートウェイを作成することでした。</span><span class="sxs-lookup"><span data-stu-id="f5b27-246">Because eShopOnContainers application has split the API Gateway into multiple BFF (Backend for Frontend) and business areas API Gateways, another option would have been to create an additional API Gateway for cross-cutting concerns.</span></span> <span data-ttu-id="f5b27-247">その選択は、複数の横断的関心事のマイクロサービスを持つより複雑なマイクロサービス ベースのアーキテクチャでは適切でしょう。</span><span class="sxs-lookup"><span data-stu-id="f5b27-247">That choice would be fair in a more complex microservice based architecture with multiple cross-cutting concerns microservices.</span></span> <span data-ttu-id="f5b27-248">eShopOnContainers には横断的関心事は 1 つしかないので、簡素化するため、API ゲートウェイ領域外のセキュリティ サービスだけを処理すると判断されました。</span><span class="sxs-lookup"><span data-stu-id="f5b27-248">Since there's only one cross-cutting concern in eShopOnContainers, it was decided to just handle the security service out of the API Gateway realm, for simplicity's sake.</span></span>

<span data-ttu-id="f5b27-249">いずれの場合も、アプリが API ゲートウェイ レベルでセキュリティ保護されている場合は、任意のセキュリティで保護されたマイクロサービスを使用するときに、最初にアクセスされるのは、Ocelot API ゲートウェイの認証モジュールです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-249">In any case, if the app is secured at the API Gateway level, the authentication module of the Ocelot API Gateway is visited at first when trying to use any secured microservice.</span></span> <span data-ttu-id="f5b27-250">これは HTTP 要求をリダイレクトして、ID/認証マイクロサービスにアクセスして、access_token で保護されたサービスにアクセスできるように、アクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-250">That redirects the HTTP request to visit the Identity or auth microservice to get the access token so you can visit the protected services with the access_token.</span></span>

<span data-ttu-id="f5b27-251">認証を使用して API ゲートウェイ レベルで任意のサービスをセキュリティで保護する方法は、configuration.json で、その関連する設定に AuthenticationProviderKey を設定することで行います。</span><span class="sxs-lookup"><span data-stu-id="f5b27-251">The way you secure with authentication any service at the API Gateway level is by setting the AuthenticationProviderKey in its related settings at the configuration.json.</span></span>

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

<span data-ttu-id="f5b27-252">Ocelot により実行時に Re-Routes AuthenticationOptions.AuthenticationProviderKey が調べられ、指定したキーに登録されている認証プロバイダーがあることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-252">When Ocelot runs, it will look at the ReRoutes AuthenticationOptions.AuthenticationProviderKey and check that there is an Authentication Provider registered with the given key.</span></span> <span data-ttu-id="f5b27-253">ない場合は、Ocelot が起動しません。</span><span class="sxs-lookup"><span data-stu-id="f5b27-253">If there isn't, then Ocelot will not start up.</span></span> <span data-ttu-id="f5b27-254">ある場合、ReRoute の実行時にそのプロバイダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-254">If there is, then the ReRoute will use that provider when it executes.</span></span>

<span data-ttu-id="f5b27-255">Ocelot WebHost は `authenticationProviderKey = "IdentityApiKey"` で構成されているため、そのサービスに認証トークンがない任意の要求がある場合には常に、認証が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-255">Because the Ocelot WebHost is configured with the `authenticationProviderKey = "IdentityApiKey"`, that will require authentication whenever that service has any requests without any auth token.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

<span data-ttu-id="f5b27-256">次に、次の Basket マイクロサービス コントローラーのように、マイクロサービスのようにアクセスされる任意のリソースで、[Authorize] 属性を使用して承認を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-256">Then, you also need to set authorization with the [Authorize] attribute on any resource to be accessed like the microservices, such as in the following Basket microservice controller.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

<span data-ttu-id="f5b27-257">"basket" などの ValidAudiences は、次のコードのように、Startup クラスの ConfigureServices() で、`AddJwtBearer()` を使用して各マイクロサービスで定義されている対象ユーザーと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-257">The ValidAudiences such as "basket" are correlated with the audience defined in each microservice with `AddJwtBearer()` at the ConfigureServices() of the Startup class, such as in the code below.</span></span>

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

<span data-ttu-id="f5b27-258">`http://localhost:5202/api/v1/b/basket/1` のような API ゲートウェイに基づく ReRoute URL を使用して、セキュリティで保護された任意のマイクロサービスにアクセスしようしたときに、有効なトークンを提供しないと、401 未承認エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-258">If you try to access any secured microservice, like the Basket microservice with a ReRoute URL based on the API Gateway like `http://localhost:5202/api/v1/b/basket/1`, then you'll get a 401 Unauthorized unless you provide a valid token.</span></span> <span data-ttu-id="f5b27-259">その一方で、ReRoute URL が認証されると、(内部マイクロサービス URL に) 関連付けられているダウンストリーム スキーマが何であれ、Ocelot によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-259">On the other hand, if a ReRoute URL is authenticated, Ocelot will invoke whatever downstream scheme is associated with it (the internal microservice URL).</span></span>

<span data-ttu-id="f5b27-260">**Ocelot の ReRoute 層での承認。**</span><span class="sxs-lookup"><span data-stu-id="f5b27-260">**Authorization at Ocelot's ReRoutes tier.**</span></span>  <span data-ttu-id="f5b27-261">Ocelot では、認証後に評価されたクレーム ベースの承認をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f5b27-261">Ocelot supports claims-based authorization evaluated after the authentication.</span></span> <span data-ttu-id="f5b27-262">次の行を ReRoute 構成に追加することで、ルート レベルで承認を設定します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-262">You set the authorization at a route level by adding the following lines to the ReRoute configuration.</span></span>

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

<span data-ttu-id="f5b27-263">この例では、承認ミドルウェアが呼び出されると、ユーザーがトークンに要求の種類 'UserType' を持っているかどうか、および要求の値が 'employee' かどうかが Ocelot によって確認されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-263">In that example, when the authorization middleware is called, Ocelot will find if the user has the claim type 'UserType' in the token and if the value of that claim is 'employee'.</span></span> <span data-ttu-id="f5b27-264">そうでない場合、ユーザーは承認されず、403 アクセス不可の応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-264">If it isn't, then the user will not be authorized and the response will be 403 forbidden.</span></span>

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a><span data-ttu-id="f5b27-265">Kubernetes イングレスと Ocelot API ゲートウェイを使用する</span><span class="sxs-lookup"><span data-stu-id="f5b27-265">Using Kubernetes Ingress plus Ocelot API Gateways</span></span>

<span data-ttu-id="f5b27-266">(Azure Kubernetes Service クラスターで使用されているように) Kubernetes を使用する場合、通常は、*Nginx* に基づく [Kubernetes イングレス層](https://kubernetes.io/docs/concepts/services-networking/ingress/)を通じて、すべての HTTP 要求を統合します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-266">When using Kubernetes (like in an Azure Kubernetes Service cluster), you usually unify all the HTTP requests through the [Kubernetes Ingress tier](https://kubernetes.io/docs/concepts/services-networking/ingress/) based on *Nginx*.</span></span>

<span data-ttu-id="f5b27-267">Kubernetes では、どのイングレス アプローチも使用しない場合、サービスとポッドには、クラスター ネットワークによるルーティングのみが可能な IP が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-267">In Kubernetes, if you don't use any ingress approach, then your services and pods have IPs only routable by the cluster network.</span></span>

<span data-ttu-id="f5b27-268">ただし、イングレス アプローチを使用する場合は、リバース プロキシとして機能する、インターネットとサービス (API ゲートウェイを含む) の間の中間層が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-268">But if you use an ingress approach, you'll have a middle tier between the Internet and your services (including your API Gateways), acting as a reverse proxy.</span></span>

<span data-ttu-id="f5b27-269">定義としては、イングレスはクラスター サービスに到達する受信接続を許可するルールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-269">As a definition, an Ingress is a collection of rules that allow inbound connections to reach the cluster services.</span></span> <span data-ttu-id="f5b27-270">イングレスは通常、サービスに外部から到達可能な URL の提供、トラフィックの負荷分散、SSL 終了などを提供するために構成されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-270">An ingress is usually configured to provide services externally reachable URLs, load balance traffic, SSL termination and more.</span></span> <span data-ttu-id="f5b27-271">ユーザーは、イングレス リソースを API サーバーに POST することで、イングレスを要求します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-271">Users request ingress by POSTing the Ingress resource to the API server.</span></span>

<span data-ttu-id="f5b27-272">eShopOnContainers では、ローカルで開発し、開発用コンピューターだけを Docker ホストとして使用する場合は、どのイングレスも使用せず、複数の API ゲートウェイのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-272">In eShopOnContainers, when developing locally and using just your development machine as the Docker host, you are not using any ingress but only the multiple API Gateways.</span></span>

<span data-ttu-id="f5b27-273">ただし、Kubernetes に基づいて "運用" 環境をターゲットにする場合は、eShopOnContainers では、API ゲートウェイの前にイングレスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-273">However, when targeting a "production" environment based on Kubernetes, eShopOnContainers is using an ingress in front of the API gateways.</span></span> <span data-ttu-id="f5b27-274">これにより、クライアントは引き続き同じベース URL を呼び出しますが、要求は複数の API ゲートウェイまたは BFF にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-274">That way, the clients still call the same base URL but the requests are routed to multiple API Gateways or BFF.</span></span>

<span data-ttu-id="f5b27-275">API ゲートウェイはサービスのみに接するフロント エンドまたはファサードであり、通常はその範囲外となる Web アプリケーションではありません。</span><span class="sxs-lookup"><span data-stu-id="f5b27-275">API Gateways are front-ends or façades surfacing only the services but not the web applications that are usually out of their scope.</span></span> <span data-ttu-id="f5b27-276">さらに、API ゲートウェイは、特定の内部マイクロサービスを非表示にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-276">In addition, the API Gateways might hide certain internal microservices.</span></span>

<span data-ttu-id="f5b27-277">ただし、イングレスは、HTTP 要求をリダイレクトするだけですが、どのマイクロサービスまたは Web アプリも非表示にはしません。</span><span class="sxs-lookup"><span data-stu-id="f5b27-277">The ingress, however, is just redirecting HTTP requests but not trying to hide any microservice or web app.</span></span>

<span data-ttu-id="f5b27-278">次の図に示すように、Web アプリケーションの前の Kubernetes にイングレス Nginx 層と、複数の Ocelot API ゲートウェイ/BFF を配置するのが理想的なアーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-278">Having an ingress Nginx tier in Kubernetes in front of the web applications plus the several Ocelot API Gateways / BFF is the ideal architecture, as shown in the following diagram.</span></span>

![イングレス層が AKS 環境にどのように適合しているかを示す図。](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

<span data-ttu-id="f5b27-280">**図 6-41**。</span><span class="sxs-lookup"><span data-stu-id="f5b27-280">**Figure 6-41**.</span></span> <span data-ttu-id="f5b27-281">Kubernetes に配置するときの eShopOnContainers のイングレス層</span><span class="sxs-lookup"><span data-stu-id="f5b27-281">The ingress tier in eShopOnContainers when deployed into Kubernetes</span></span>

<span data-ttu-id="f5b27-282">Kubernetes イングレスは、Web アプリケーションなど、通常は API ゲートウェイの範囲外となるアプリに宛てられるすべてのトラフィックのリバース プロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-282">A Kubernetes Ingress acts as a reverse proxy for all traffic to the app, including the web applications, that are usually out of the Api gateway scope.</span></span> <span data-ttu-id="f5b27-283">Kubernetes に eShopOnContainers を配置すると、少数のサービスまたはエンドポイントだけが_イングレス_経由で公開されます。基本的に、URL の接尾辞は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f5b27-283">When you deploy eShopOnContainers into Kubernetes, it exposes just a few services or endpoints via _ingress_, basically the following list of postfixes on the URLs:</span></span>

- <span data-ttu-id="f5b27-284">`/`: クライアント SPA Web アプリケーション用</span><span class="sxs-lookup"><span data-stu-id="f5b27-284">`/` for the client SPA web application</span></span>
- <span data-ttu-id="f5b27-285">`/webmvc`: クライアント MVC Web アプリケーション用</span><span class="sxs-lookup"><span data-stu-id="f5b27-285">`/webmvc` for the client MVC web application</span></span>
- <span data-ttu-id="f5b27-286">`/webstatus`: 状態/正常性チェックを示すクライアント Web アプリ用</span><span class="sxs-lookup"><span data-stu-id="f5b27-286">`/webstatus` for the client web app showing the status/healthchecks</span></span>
- <span data-ttu-id="f5b27-287">`/webshoppingapigw`: Web BFF とショッピング ビジネス プロセス用</span><span class="sxs-lookup"><span data-stu-id="f5b27-287">`/webshoppingapigw` for the web BFF and shopping business processes</span></span>
- <span data-ttu-id="f5b27-288">`/webmarketingapigw`: Web BFF とマーケティング ビジネス プロセス用</span><span class="sxs-lookup"><span data-stu-id="f5b27-288">`/webmarketingapigw` for the web BFF and marketing business processes</span></span>
- <span data-ttu-id="f5b27-289">`/mobileshoppingapigw`: モバイル BFF とショッピング ビジネス プロセス用</span><span class="sxs-lookup"><span data-stu-id="f5b27-289">`/mobileshoppingapigw` for the mobile BFF and shopping business processes</span></span>
- <span data-ttu-id="f5b27-290">`/mobilemarketingapigw`: モバイル BFF とマーケティング ビジネス プロセス用</span><span class="sxs-lookup"><span data-stu-id="f5b27-290">`/mobilemarketingapigw` for the mobile BFF and marketing business processes</span></span>

<span data-ttu-id="f5b27-291">Kubernetes に配置するときに、各 Ocelot API ゲートウェイは、API ゲートウェイを実行している_ポッド_ごとに異なる "configuration.json" ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5b27-291">When deploying to Kubernetes, each Ocelot API Gateway is using a different "configuration.json" file for each _pod_ running the API Gateways.</span></span> <span data-ttu-id="f5b27-292">これらの "configuration.json" ファイルは、"ocelot" という名前の Kubernetes _構成マップ_に基づいて作成されたボリュームを (もともとは deploy.ps1 スクリプトを使用して) マウントすることによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-292">Those "configuration.json" files are provided by mounting (originally with the deploy.ps1 script) a volume created based on a Kubernetes _config map_ named ‘ocelot'.</span></span> <span data-ttu-id="f5b27-293">各コンテナーにより、関連する構成ファイルが `/app/configuration` という名前のコンテナーのフォルダーにマウントされます。</span><span class="sxs-lookup"><span data-stu-id="f5b27-293">Each container mounts its related configuration file in the container's folder named `/app/configuration`.</span></span>

<span data-ttu-id="f5b27-294">eShopOnContainers のソース コード ファイルでは、元の "configuration.json" ファイルは `k8s/ocelot/` フォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-294">In the source code files of eShopOnContainers, the original "configuration.json" files can be found within the `k8s/ocelot/` folder.</span></span> <span data-ttu-id="f5b27-295">BFF/API ゲートウェイごとに 1 つのファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="f5b27-295">There's one file for each BFF/APIGateway.</span></span>

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a><span data-ttu-id="f5b27-296">Ocelot API ゲートウェイで追加された横断機能</span><span class="sxs-lookup"><span data-stu-id="f5b27-296">Additional cross-cutting features in an Ocelot API Gateway</span></span>

<span data-ttu-id="f5b27-297">Ocelot API ゲートウェイを使用する場合に、調査および使用するための重要な機能は他にもあり、次のリンクで説明されています。</span><span class="sxs-lookup"><span data-stu-id="f5b27-297">There are other important features to research and use, when using an Ocelot API Gateway, described in the following links.</span></span>

- <span data-ttu-id="f5b27-298">**Ocelot と Consul または Eureka を統合するクライアント側でのサービス検出** </span><span class="sxs-lookup"><span data-stu-id="f5b27-298">**Service discovery in the client side integrating Ocelot with Consul or Eureka** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- <span data-ttu-id="f5b27-299">**API ゲートウェイ層でのキャッシュ** </span><span class="sxs-lookup"><span data-stu-id="f5b27-299">**Caching at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- <span data-ttu-id="f5b27-300">**API ゲートウェイ層でのログ記録** </span><span class="sxs-lookup"><span data-stu-id="f5b27-300">**Logging at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- <span data-ttu-id="f5b27-301">**API ゲートウェイ層でのサービスの品質 (再試行、サーキット ブレーカー)**  </span><span class="sxs-lookup"><span data-stu-id="f5b27-301">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- <span data-ttu-id="f5b27-302">**速度の制限** </span><span class="sxs-lookup"><span data-stu-id="f5b27-302">**Rate limiting** </span></span>\
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> <span data-ttu-id="f5b27-303">[前へ](background-tasks-with-ihostedservice.md)
> [次へ](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="f5b27-303">[Previous](background-tasks-with-ihostedservice.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
