---
title: サービスメッシュ-WCF 開発者向け gRPC
description: サービスメッシュを使用して、Kubernetes クラスター内の gRPC サービスに要求をルーティングおよび分散します。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6bdfa57ba47ba0105092d1c140705599b7023c78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841991"
---
# <a name="service-meshes"></a><span data-ttu-id="d20f4-103">サービスメッシュ</span><span class="sxs-lookup"><span data-stu-id="d20f4-103">Service meshes</span></span>

<span data-ttu-id="d20f4-104">サービスメッシュは、ネットワーク内のルーティングサービス要求を制御するインフラストラクチャコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d20f4-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="d20f4-105">サービスメッシュは、Kubernetes クラスター内のあらゆる種類のネットワークレベルの問題を処理できます。これには次のものが含まれる。</span><span class="sxs-lookup"><span data-stu-id="d20f4-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="d20f4-106">サービスの検出</span><span class="sxs-lookup"><span data-stu-id="d20f4-106">Service discovery</span></span>
- <span data-ttu-id="d20f4-107">負荷分散</span><span class="sxs-lookup"><span data-stu-id="d20f4-107">Load balancing</span></span>
- <span data-ttu-id="d20f4-108">フォールト トレランス</span><span class="sxs-lookup"><span data-stu-id="d20f4-108">Fault tolerance</span></span>
- <span data-ttu-id="d20f4-109">暗号化</span><span class="sxs-lookup"><span data-stu-id="d20f4-109">Encryption</span></span>
- <span data-ttu-id="d20f4-110">監視</span><span class="sxs-lookup"><span data-stu-id="d20f4-110">Monitoring</span></span>

<span data-ttu-id="d20f4-111">Kubernetes サービスメッシュは、メッシュに含まれる各ポッドにサイドカー*プロキシ*と呼ばれる追加のコンテナーを追加することによって機能します。</span><span class="sxs-lookup"><span data-stu-id="d20f4-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="d20f4-112">プロキシは、すべての受信および送信ネットワーク要求を処理します。これにより、ネットワークの構成と管理がアプリケーションコンテナーとは別に維持され、多くの場合、アプリケーションコードを変更する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="d20f4-112">The proxy takes over handling all inbound and outbound network requests, allowing configuration and management of networking matters to be kept separate from the application containers and, in many cases, without requiring any changes to the application code.</span></span>

<span data-ttu-id="d20f4-113">[前の章の例](kubernetes.md#testing-the-application)を参照してください。 web アプリケーションからの grpc 要求はすべて、grpc サービスの1つのインスタンスにルーティングされていました。</span><span class="sxs-lookup"><span data-stu-id="d20f4-113">Take the [previous chapter's example](kubernetes.md#testing-the-application), where the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="d20f4-114">これは、サービスのホスト名が IP アドレスに解決され、その IP アドレスが `HttpClientHandler` インスタンスの有効期間にわたってキャッシュされているために発生します。</span><span class="sxs-lookup"><span data-stu-id="d20f4-114">This happens because the service's hostname is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="d20f4-115">DNS 参照を手動で処理するか、複数のクライアントを作成することにより、この問題を回避できる場合がありますが、ビジネスや顧客の価値を追加しなくても、アプリケーションコードが大幅に複雑になります。</span><span class="sxs-lookup"><span data-stu-id="d20f4-115">It might be possible to work around this by handling DNS lookups manually or creating multiple clients, but this would complicate the application code considerably without adding any business or customer value.</span></span>

<span data-ttu-id="d20f4-116">サービスメッシュを使用して、アプリケーションコンテナーからの要求がサイドカープロキシに送信されます。このプロキシは、他のサービスのすべてのインスタンスに対してインテリジェントに配布できます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-116">Using a service mesh, the requests from the application container are sent to the sidecar proxy, which can distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="d20f4-117">メッシュは次のようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-117">The mesh can also:</span></span>

- <span data-ttu-id="d20f4-118">サービスの個々のインスタンスの障害にシームレスに対応できます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-118">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="d20f4-119">失敗した呼び出しまたはタイムアウトの再試行セマンティクスを処理する</span><span class="sxs-lookup"><span data-stu-id="d20f4-119">Handle retry semantics for failed calls or timeouts</span></span>
- <span data-ttu-id="d20f4-120">クライアントアプリケーションに戻らずに、別のインスタンスに失敗した要求を再ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d20f4-120">Reroute failed requests to an alternate instance without returning to the client application at all.</span></span>

<span data-ttu-id="d20f4-121">次のスクリーンショットは、Linkerd サービスメッシュで実行される StockWeb アプリケーションを示しています。アプリケーションコードや、使用されている Docker イメージは変更されていません。</span><span class="sxs-lookup"><span data-stu-id="d20f4-121">The following screenshot shows the StockWeb application running with the Linkerd service mesh, with no changes to the application code, or even the Docker image being used.</span></span> <span data-ttu-id="d20f4-122">必要な変更は、`stockdata` および `stockweb` サービスの YAML ファイルの配置に注釈を追加することだけでした。</span><span class="sxs-lookup"><span data-stu-id="d20f4-122">The only change required was the addition of an annotation to the Deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![サービスメッシュを使用した StockWeb](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="d20f4-124">アプリケーションコードの1つの `HttpClient` インスタンスから発生した場合でも、StockWeb アプリケーションからの要求が Stockweb service の両方のレプリカにルーティングされていることを、[サーバー] 列から確認できます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-124">You can see from the Server column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="d20f4-125">実際には、コードを確認すると、同じ `HttpClient` インスタンスを使用して StockData サービスに対する100要求がすべて同時に行われることがわかります。ただし、サービスメッシュでは、これらの要求は多くのサービスインスタンスに分散されますが、複数のサービスインスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-125">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously using the same `HttpClient` instance, yet with the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="d20f4-126">サービスメッシュは、クラスター内のトラフィックにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-126">Service meshes only apply to traffic within a cluster.</span></span> <span data-ttu-id="d20f4-127">外部クライアントの場合は、[次の章「負荷分散](load-balancing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d20f4-127">For external clients, see [the next chapter, Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="d20f4-128">サービスメッシュオプション</span><span class="sxs-lookup"><span data-stu-id="d20f4-128">Service mesh options</span></span>

<span data-ttu-id="d20f4-129">現在、Kubernetes: ILinkerd o、、Consul Connect で使用できる汎用サービスメッシュ実装は3つあります。</span><span class="sxs-lookup"><span data-stu-id="d20f4-129">There are three general-purpose service mesh implementations currently available for use with Kubernetes: Istio, Linkerd, and Consul Connect.</span></span> <span data-ttu-id="d20f4-130">3つすべては、要求のルーティング/プロキシ、トラフィックの暗号化、回復性、ホストからホストへの認証、およびトラフィック制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="d20f4-130">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="d20f4-131">サービスメッシュの選択は、次の複数の要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d20f4-131">Choosing a service mesh depends multiple factors:</span></span>

- <span data-ttu-id="d20f4-132">コスト、コンプライアンス、有償サポートプランなどに関する組織固有の要件。</span><span class="sxs-lookup"><span data-stu-id="d20f4-132">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="d20f4-133">クラスターの特性、サイズ、デプロイされたサービスの数、およびクラスターネットワーク内のトラフィックの量。</span><span class="sxs-lookup"><span data-stu-id="d20f4-133">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="d20f4-134">メッシュのデプロイと管理を容易にし、サービスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-134">Ease of deploying and managing the mesh and using it with services.</span></span>

<span data-ttu-id="d20f4-135">各サービスメッシュの詳細については、それぞれの web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d20f4-135">More information on each service mesh is available from their respective websites.</span></span>

- [<span data-ttu-id="d20f4-136">**Iistio.io**</span><span class="sxs-lookup"><span data-stu-id="d20f4-136">**Istio** - istio.io</span></span>](https://istio.io)
- [<span data-ttu-id="d20f4-137">**Linkerd** -linkerd.io</span><span class="sxs-lookup"><span data-stu-id="d20f4-137">**Linkerd** - linkerd.io</span></span>](https://linkerd.io)
- [<span data-ttu-id="d20f4-138">**Consul** -consul.io/mesh.html</span><span class="sxs-lookup"><span data-stu-id="d20f4-138">**Consul** - consul.io/mesh.html</span></span>](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="d20f4-139">例: デプロイへの Linkerd の追加</span><span class="sxs-lookup"><span data-stu-id="d20f4-139">Example: add Linkerd to a deployment</span></span>

<span data-ttu-id="d20f4-140">この例では、[前のセクション](kubernetes.md)の*StockKube*アプリケーションで Linkerd service メッシュを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d20f4-140">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="d20f4-141">この例を実行するには、 [LINKERD CLI をインストール](https://linkerd.io/2/getting-started/#step-1-install-the-cli)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d20f4-141">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="d20f4-142">Windows バイナリは、GitHub リリースセクションからダウンロードできます。エッジリリースの1つではなく、最新の**安定**したリリースを使用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="d20f4-142">Windows binaries can be downloaded from the GitHub releases section; make sure to use the most recent **stable** release and not one of the edge releases.</span></span>

<span data-ttu-id="d20f4-143">Linkerd CLI がインストールされている状態で、Linkerd web サイトの [*はじめに*の指示に従って、Kubernetes クラスターに Linkerd コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d20f4-143">With the Linkerd CLI installed, follow the [*Getting Started* instructions on the Linkerd web site] to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="d20f4-144">手順は簡単であり、インストールにはローカル Kubernetes インスタンスで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d20f4-144">The instructions are straight-forward and installation should only take a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="d20f4-145">Linkerd を Kubernetes デプロイに追加する</span><span class="sxs-lookup"><span data-stu-id="d20f4-145">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="d20f4-146">Linkerd CLI には、必要なセクションとプロパティを Kubernetes ファイルに追加するための `inject` コマンドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d20f4-146">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="d20f4-147">コマンドを実行し、出力を新しいファイルに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-147">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="d20f4-148">新しいファイルを調べて、どのような変更が加えられたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-148">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="d20f4-149">配置オブジェクトの場合、メタデータ注釈が追加され、Linkerd が作成時にサイドカープロキシコンテナーをポッドに挿入するように指示します。</span><span class="sxs-lookup"><span data-stu-id="d20f4-149">For Deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the Pod when it's created.</span></span>

<span data-ttu-id="d20f4-150">パイプを使用して `linkerd inject` コマンドの出力を直接 `kubectl` にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-150">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="d20f4-151">次のコマンドは、PowerShell または任意の Linux シェルで動作します。</span><span class="sxs-lookup"><span data-stu-id="d20f4-151">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="d20f4-152">Linkerd ダッシュボードでサービスを検査する</span><span class="sxs-lookup"><span data-stu-id="d20f4-152">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="d20f4-153">`linkerd` CLI を使用して Linkerd ダッシュボードを起動します。</span><span class="sxs-lookup"><span data-stu-id="d20f4-153">Launch the Linkerd dashboard using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="d20f4-154">ダッシュボードには、メッシュに接続されているすべてのサービスに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d20f4-154">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![StockKube アプリケーションを示す Linkerd ダッシュボード](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="d20f4-156">次の例に示すように StockData gRPC サービスのレプリカの数を増やし、ブラウザーで Stockdata ページを更新すると、サーバー列に Id が混在していることが示されます。これは、使用可能なすべてのインスタンスによって要求が処理されていることを示します.</span><span class="sxs-lookup"><span data-stu-id="d20f4-156">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the Server column, indicating that requests are being served by all the available instances.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
><span data-ttu-id="d20f4-157">[前へ](kubernetes.md)
>[次へ](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="d20f4-157">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
