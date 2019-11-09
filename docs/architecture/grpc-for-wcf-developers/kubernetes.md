---
title: WCF 開発者向け Kubernetes-gRPC
description: Kubernetes クラスターで ASP.NET Core gRPC サービスを実行しています。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 819c761a7a55485612b7fb0c8b392971751d8724
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841577"
---
# <a name="kubernetes"></a><span data-ttu-id="edfe9-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="edfe9-103">Kubernetes</span></span>

<span data-ttu-id="edfe9-104">Docker ホストでコンテナーを手動で実行することもできますが、信頼性の高い運用システムでは、コンテナーオーケストレーションエンジンを使用して、クラスター内の複数のサーバーで実行されている複数のインスタンスを管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="edfe9-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's preferable to use a Container Orchestration Engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="edfe9-105">Kubernetes、Docker の群れ、Apache のシステムなど、さまざまなコンテナーオーケストレーションエンジンを利用できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-105">There are various Container Orchestration Engines available, including Kubernetes, Docker Swarm and Apache Mesos.</span></span> <span data-ttu-id="edfe9-106">しかし、これらのエンジンでは、Kubernetes ははるかに広く使用されているので、この章で重点的に説明します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="edfe9-107">Kubernetes には、次の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="edfe9-108">**スケジュール設定**では、クラスター内の複数のノードでコンテナーを実行し、使用可能なリソースのバランスの取れた使用状況を確保し、障害が発生した場合はコンテナーを実行したままにして、新しいバージョンのイメージまたは新しい構成へのローリング更新を処理します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="edfe9-109">**正常性チェック**は、コンテナーを監視してサービスを継続的に確認します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="edfe9-110">**DNS & サービス検出**は、クラスター内のサービス間のルーティングを処理します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="edfe9-111">受信は、選択したサービスを外部**に公開し**、一般にこれらのサービスのインスタンス間で負荷分散を行います。</span><span class="sxs-lookup"><span data-stu-id="edfe9-111">**Ingress** exposes selected services externally, and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="edfe9-112">**リソース管理**は、ストレージなどの外部リソースをコンテナーにアタッチします。</span><span class="sxs-lookup"><span data-stu-id="edfe9-112">**Resource management** attaches external resources such as storage to containers.</span></span>

<span data-ttu-id="edfe9-113">この章では、ASP.NET Core gRPC サービスと、サービスを使用する web サイトを Kubernetes クラスターにデプロイする方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="edfe9-114">使用されているサンプルアプリケーションは、GitHub の[dotnet/grpc-wcf 開発者](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample)リポジトリのから入手できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-114">The sample application used is available from on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub,</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="edfe9-115">Kubernetes の用語</span><span class="sxs-lookup"><span data-stu-id="edfe9-115">Kubernetes terminology</span></span>

<span data-ttu-id="edfe9-116">Kubernetes は*desired state configuration*を使用します。*ポッド*、*デプロイ*、*サービス*などのオブジェクトを記述するために API が使用され、*コントロールプレーン*は*クラスター*内のすべての*ノード*で目的の状態を実装します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-116">Kubernetes uses *desired state configuration*: the API is used to describe objects such as *Pods*, *Deployments* and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="edfe9-117">Kubernetes クラスターには、 *KUBERNETES API*を実行する*マスター*ノードがあります。このノードはプログラムによって、または `kubectl` コマンドラインツールを使用して通信できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which can be communicated with programmatically or using the `kubectl` command-line tool.</span></span> <span data-ttu-id="edfe9-118">`kubectl` は、コマンドライン引数を使用してオブジェクトを作成および管理できますが、Kubernetes オブジェクトの宣言データを含む YAML ファイルで最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-118">`kubectl` can create and manage objects using command-line arguments, but works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="edfe9-119">Kubernetes YAML ファイル</span><span class="sxs-lookup"><span data-stu-id="edfe9-119">Kubernetes YAML files</span></span>

<span data-ttu-id="edfe9-120">すべての Kubernetes YAML ファイルには、少なくとも3つの最上位レベルのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-120">Every Kubernetes YAML file will have at least three top-level properties.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="edfe9-121">`apiVersion` プロパティは、ファイルの対象となるバージョン (および API) を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="edfe9-122">`kind` プロパティは、YAML が表すオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="edfe9-123">`metadata` プロパティには、`name`、`namespace`、`labels`などのオブジェクトプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-123">The `metadata` property contains object properties such as `name`, `namespace`, or `labels`.</span></span>

<span data-ttu-id="edfe9-124">ほとんどの Kubernetes YAML ファイルには、オブジェクトの作成に必要なリソースと構成を説明する `spec` セクションもあります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="edfe9-125">ポッド</span><span class="sxs-lookup"><span data-stu-id="edfe9-125">Pods</span></span>

<span data-ttu-id="edfe9-126">ポッドは、Kubernetes での実行の基本単位です。</span><span class="sxs-lookup"><span data-stu-id="edfe9-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="edfe9-127">複数のコンテナーを実行できますが、1つのコンテナーを実行するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-127">They can run multiple containers, but are also used to run single containers.</span></span> <span data-ttu-id="edfe9-128">ポッドには、コンテナーに必要なすべてのストレージリソースと、ネットワークの IP アドレスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-128">The pod also includes any storage resources required by the container(s), and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="edfe9-129">Services</span><span class="sxs-lookup"><span data-stu-id="edfe9-129">Services</span></span>

<span data-ttu-id="edfe9-130">サービスは、ポッド (またはポッドのセット) を記述し、クラスター内でそれらにアクセスする手段を提供するメタオブジェクトです。たとえば、クラスター DNS サービスを使用して、サービス名をポッド IP アドレスのセットにマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-130">Services are meta-objects that describe pods (or sets of pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="edfe9-131">展開</span><span class="sxs-lookup"><span data-stu-id="edfe9-131">Deployments</span></span>

<span data-ttu-id="edfe9-132">展開とは、ポッドの*状態*オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="edfe9-132">Deployments are the *described state* objects for Pods.</span></span> <span data-ttu-id="edfe9-133">ポッドを手動で作成した場合、そのポッドを終了すると、再起動されません。</span><span class="sxs-lookup"><span data-stu-id="edfe9-133">If you create a Pod manually, when it terminates it won't be restarted.</span></span> <span data-ttu-id="edfe9-134">デプロイは、現在の時点で実行する必要があるポッド、およびそれらのポッドのレプリカの数をクラスターに伝えるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-134">Deployments are used to tell the cluster which pods, and how many replicas of those pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="edfe9-135">その他のオブジェクト</span><span class="sxs-lookup"><span data-stu-id="edfe9-135">Other objects</span></span>

<span data-ttu-id="edfe9-136">ポッド、サービス、および展開は、最も基本的なオブジェクトの種類のうちの3つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="edfe9-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="edfe9-137">Kubernetes クラスターによって管理されるオブジェクトには、他にも多数の種類があります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-137">There are dozens of other types of object that are managed by a Kubernetes cluster.</span></span> <span data-ttu-id="edfe9-138">詳細については、 [Kubernetes の概念](https://kubernetes.io/docs/concepts/)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edfe9-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="edfe9-139">名前空間</span><span class="sxs-lookup"><span data-stu-id="edfe9-139">Namespaces</span></span>

<span data-ttu-id="edfe9-140">Kubernetes クラスターは、数百または数千のノードに拡張し、同様の数のサービスを実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes, and run similar numbers of services.</span></span> <span data-ttu-id="edfe9-141">オブジェクト名が競合しないようにするために、名前空間を使用して、大きなアプリケーションの一部としてオブジェクトをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="edfe9-142">Kubernetes 独自のサービスは、`default` 名前空間で実行されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-142">Kubernetes own services run in a `default` namespace.</span></span> <span data-ttu-id="edfe9-143">既定のオブジェクトまたはクラスター内の他のテナントとの潜在的な競合を避けるために、すべてのユーザーオブジェクトを独自の名前空間に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="edfe9-144">Kubernetes を使ってみる</span><span class="sxs-lookup"><span data-stu-id="edfe9-144">Get started with Kubernetes</span></span>

<span data-ttu-id="edfe9-145">Windows または macOS 用の Docker Desktop を実行している場合、Kubernetes は既に使用できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-145">If you're running Docker Desktop for Windows or macOS, Kubernetes is already available.</span></span> <span data-ttu-id="edfe9-146">[設定] ウィンドウの [Kubernetes] セクションで有効にするだけです。</span><span class="sxs-lookup"><span data-stu-id="edfe9-146">Just enable it in the Kubernetes section of the Settings window.</span></span>

![Docker Desktop で Kubernetes を有効にする](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="edfe9-148">Linux でローカル Kubernetes クラスターを実行するには、 [minikube](https://github.com/kubernetes/minikube)を参照するか、linux ディストリビューションで[スナップ](https://snapcraft.io/)がサポートされ[ているかどうかを](https://microk8s.io/)確認してください。</span><span class="sxs-lookup"><span data-stu-id="edfe9-148">To run a local Kubernetes cluster in Linux, look at [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="edfe9-149">クラスターが実行中で、アクセス可能であることを確認するには、`kubectl version` コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-149">To check that your cluster is running and accessible, run the `kubectl version` command.</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="edfe9-150">この例では、`kubectl` CLI と Kubernetes サーバーの両方でバージョン1.14.6 が実行されています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="edfe9-151">`kubectl` の各バージョンは、サーバーの以前のバージョンと次のバージョンをサポートすることが想定されています。そのため、`kubectl` 1.14 は、サーバーバージョン1.13 と1.15 でも動作します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="edfe9-152">Kubernetes でサービスを実行する</span><span class="sxs-lookup"><span data-stu-id="edfe9-152">Run services on Kubernetes</span></span>

<span data-ttu-id="edfe9-153">サンプルアプリケーションには、3つの YAML ファイルを含む `kube` ディレクトリがあります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-153">The sample application has a `kube` directory containing three YAML files.</span></span> <span data-ttu-id="edfe9-154">`namespace.yml` ファイルは、`stocks`カスタム名前空間を宣言します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-154">The `namespace.yml` file declares a custom namespace, `stocks`.</span></span> <span data-ttu-id="edfe9-155">`stockdata.yml` ファイルは、gRPC アプリケーションのデプロイとサービスを宣言し、`stockweb.yml` ファイルは、gRPC サービスを使用する ASP.NET Core 3.0 MVC web アプリケーションのデプロイとサービスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="edfe9-156">`kubectl`で `YAML` ファイルを使用するには、`apply -f` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-156">To use a `YAML` file with `kubectl`, use the `apply -f` command.</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="edfe9-157">`apply` コマンドは、YAML ファイルの有効性を確認し、API から受信したすべてのエラーを表示しますが、ファイルで宣言されたすべてのオブジェクトが作成されるまで待機しません。これには時間がかかる場合があるためです。</span><span class="sxs-lookup"><span data-stu-id="edfe9-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created as this can take some time.</span></span> <span data-ttu-id="edfe9-158">`kubectl get` コマンドと関連するオブジェクトの種類を使用して、クラスターでのオブジェクトの作成を確認します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="edfe9-159">名前空間の宣言</span><span class="sxs-lookup"><span data-stu-id="edfe9-159">The namespace declaration</span></span>

<span data-ttu-id="edfe9-160">名前空間の宣言は単純であり、`name`の割り当てのみを必要とします。</span><span class="sxs-lookup"><span data-stu-id="edfe9-160">Namespace declaration is simple and requires only assigning a `name`.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="edfe9-161">`kubectl` を使用して、`namespace.yml` ファイルを適用し、名前空間が正常に作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-161">Use `kubectl` to apply the `namespace.yml` file and check the namespace is created successfully.</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="edfe9-162">StockData アプリケーション</span><span class="sxs-lookup"><span data-stu-id="edfe9-162">The StockData application</span></span>

<span data-ttu-id="edfe9-163">`stockdata.yml` ファイルでは、配置とサービスという2つのオブジェクトを宣言します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="edfe9-164">StockData のデプロイ</span><span class="sxs-lookup"><span data-stu-id="edfe9-164">The StockData Deployment</span></span>

<span data-ttu-id="edfe9-165">デプロイ部分には、必要なレプリカの数や、デプロイによって作成および管理される Pod オブジェクトの `template` など、デプロイ自体の `spec` が用意されています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-165">The Deployment part provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="edfe9-166">配置オブジェクトは、メインの Kubernetes API ではなく `apiVersion`で指定されている `apps` API を使用して管理されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="edfe9-166">Note that Deployment objects are managed with the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

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
  replicas: 1
  template:
    metadata:
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

<span data-ttu-id="edfe9-167">`spec.selector` プロパティは、実行中のポッドをデプロイと照合するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="edfe9-168">ポッドの `metadata.labels` プロパティが `matchLabels` プロパティと一致している必要があります。一致しない場合、API 呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="edfe9-169">`template.spec` セクションでは、実行するコンテナーを宣言します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="edfe9-170">Docker Desktop によって提供されるものなど、ローカルの Kubernetes クラスターを使用する場合、バージョンタグがある限り、ローカルでビルドされたイメージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-170">When working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="edfe9-171">既定では、Kubernetes は常にを確認し、新しいイメージをプルしようとします。</span><span class="sxs-lookup"><span data-stu-id="edfe9-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="edfe9-172">既知のリポジトリにイメージが見つからない場合、ポッドの作成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="edfe9-173">ローカルイメージを操作するには、`imagePullPolicy` を `Never`に設定します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="edfe9-174">`ports` プロパティは、ポッドで公開するコンテナーポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-174">The `ports` property specifies which container ports should be published on the Pod.</span></span>  <span data-ttu-id="edfe9-175">`stockservice` イメージは標準の HTTP ポートでサービスを実行するので、ポート80が発行されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="edfe9-176">`resources` セクションでは、ポッド内で実行されているコンテナーにリソースの制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-176">The `resources` section applies resource limits to the container running within the pod.</span></span> <span data-ttu-id="edfe9-177">これは、個々のポッドがノード上の使用可能なすべての CPU またはメモリを消費しないようにするため、推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="edfe9-177">This is good practice as it prevents an individual pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="edfe9-178">ASP.NET Core 3.0 は、リソース制限のあるコンテナーで実行されるように最適化およびチューニングされています。 `dotnet/core/aspnet` の Docker イメージは、`dotnet` ランタイムにコンテナー内にあることを通知する環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers, and the `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="edfe9-179">StockData サービス</span><span class="sxs-lookup"><span data-stu-id="edfe9-179">The StockData Service</span></span>

<span data-ttu-id="edfe9-180">YAML ファイルのサービス部分では、クラスター内のポッドへのアクセスを提供するサービスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-180">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="edfe9-181">サービス仕様では、`selector` プロパティを使用して実行中の `Pods`を照合します。この例では、`run: stockdata`ラベルを持つポッドを探しています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-181">The Service spec uses the `selector` property to match running `Pods`, in this case looking for Pods with a label `run: stockdata`.</span></span> <span data-ttu-id="edfe9-182">一致するポッドに対して指定された `port` は、名前付きサービスによって発行されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-182">The specified `port` on matching Pods are published by the named service.</span></span> <span data-ttu-id="edfe9-183">`stocks` 名前空間で実行されている他のポッドは、アドレスとして `http://stockdata` を使用して、このサービスの HTTP にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-183">Other Pods running in the `stocks` namespace can access HTTP on this service using `http://stockdata` as the address.</span></span> <span data-ttu-id="edfe9-184">他の名前空間で実行されているポッドでは、`http://stockdata.stocks` のホスト名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-184">Pods running in other namespaces can use the `http://stockdata.stocks` hostname.</span></span> <span data-ttu-id="edfe9-185">[ネットワークポリシー](https://kubernetes.io/docs/concepts/services-networking/network-policies/)を使用して、名前空間間サービスアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-185">You can control cross-namespace service access using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="edfe9-186">StockData アプリケーションをデプロイする</span><span class="sxs-lookup"><span data-stu-id="edfe9-186">Deploy the StockData application</span></span>

<span data-ttu-id="edfe9-187">`kubectl` を使用して、`stockdata.yml` ファイルを適用し、展開とサービスが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-187">Use `kubectl` to apply the `stockdata.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="edfe9-188">StockWeb アプリケーション</span><span class="sxs-lookup"><span data-stu-id="edfe9-188">The StockWeb application</span></span>

<span data-ttu-id="edfe9-189">`stockweb.yml` ファイルは、MVC アプリケーションのデプロイとサービスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-189">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="edfe9-190">環境変数</span><span class="sxs-lookup"><span data-stu-id="edfe9-190">Environment variables</span></span>

<span data-ttu-id="edfe9-191">Deployment オブジェクトの `env` セクションでは、`stockweb:1.0.0` イメージを実行しているコンテナーに設定する環境変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-191">The `env` section of the Deployment object specifies environment variables to be set in the container running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="edfe9-192">EnvironmentVariables 構成プロバイダーにより、 **`StockData__Address`** 環境変数が `StockData:Address` 構成設定にマップされます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-192">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="edfe9-193">この設定では、名前の間に2つのアンダースコアを使用し、セクションを区切ります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-193">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="edfe9-194">このアドレスは、同じ Kubernetes 名前空間で実行されている `stockdata` サービスのサービス名を使用します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-194">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="edfe9-195">**`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** 環境変数は、<xref:System.Net.Http.HttpClient>に対して暗号化されていない HTTP/2 接続を有効にする <xref:System.AppContext> スイッチを設定します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-195">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="edfe9-196">この環境変数は、次に示すように、コードでスイッチを設定することに相当します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-196">This environment variable is the equivalent of setting the switch in code as shown here.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="edfe9-197">スイッチに環境変数を使用すると、アプリケーションが実行されているコンテキストに応じて、設定を簡単に変更できます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-197">Using an environment variable for the switch means the setting can easily be changed depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="edfe9-198">サービスの種類</span><span class="sxs-lookup"><span data-stu-id="edfe9-198">Service types</span></span>

<span data-ttu-id="edfe9-199">クラスターの外部から Web アプリケーションにアクセスできるようにするには、`type: NodePort` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-199">To make the Web application accessible from outside the cluster, the `type: NodePort` property is used.</span></span> <span data-ttu-id="edfe9-200">このプロパティの種類を Kubernetes と、サービスのポート80がクラスターの外部ネットワークソケットの任意のポートに発行されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-200">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="edfe9-201">割り当てられたポートは、`kubectl get service` コマンドを使用して見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-201">The port assigned can be found using the `kubectl get service` command.</span></span>

<span data-ttu-id="edfe9-202">`stockdata` サービスにはクラスターの外部からアクセスできないため、既定の種類である `ClusterIP`が使用されています。</span><span class="sxs-lookup"><span data-stu-id="edfe9-202">The `stockdata` service shouldn't be accessible from outside the cluster, so it used the default type, `ClusterIP`.</span></span>

<span data-ttu-id="edfe9-203">実稼働システムでは、通常、統合されたロードバランサーを使用して、パブリックアプリケーションを外部のコンシューマーに公開します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-203">Production systems will most likely use an integrated load-balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="edfe9-204">この方法で公開されるサービスでは、`LoadBalancer` の種類を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-204">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="edfe9-205">サービスの種類の詳細については、 [Kubernetes の公開サービス](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edfe9-205">For more information on service types, see the [Kubernetes' Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="edfe9-206">StockWeb アプリケーションをデプロイする</span><span class="sxs-lookup"><span data-stu-id="edfe9-206">Deploy the StockWeb application</span></span>

<span data-ttu-id="edfe9-207">`kubectl` を使用して、`stockweb.yml` ファイルを適用し、展開とサービスが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-207">Use `kubectl` to apply the `stockweb.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="edfe9-208">`get service` コマンドからの出力は、HTTP ポートが外部ネットワーク上のポート `32564` に発行されていることを示しています。Docker Desktop の場合、これは localhost になります。</span><span class="sxs-lookup"><span data-stu-id="edfe9-208">The output from the `get service` command shows that the HTTP port has been published to port `32564` on the external network; for Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="edfe9-209">アプリケーションにアクセスするには、`http://localhost:32564`を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edfe9-209">The application can be accessed by browsing to `http://localhost:32564`.</span></span>

### <a name="testing-the-application"></a><span data-ttu-id="edfe9-210">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="edfe9-210">Testing the application</span></span>

<span data-ttu-id="edfe9-211">StockWeb アプリケーションでは、単純な要求/応答サービスから取得された NASDAQ 株式の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-211">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="edfe9-212">デモンストレーションを目的として、各行には、それを返したサービスインスタンスの一意の ID も表示されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-212">For demonstration purposes, each line also shows the unique ID of the service instance that returned it.</span></span>

![StockWeb スクリーンショット](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="edfe9-214">`stockdata` サービスのレプリカの数が増加した場合は、**サーバー**の値が行ごとに変更されることが予想されますが、実際には、100のすべてのレコードが常に同じインスタンスから返されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-214">If the number of replicas of the `stockdata` service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="edfe9-215">数秒ごとにページを更新した場合、サーバー ID は変わりません。</span><span class="sxs-lookup"><span data-stu-id="edfe9-215">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="edfe9-216">なぜこれが発生するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="edfe9-216">Why does this happen?</span></span> <span data-ttu-id="edfe9-217">ここでは2つの要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-217">There are two factors at play here.</span></span>

<span data-ttu-id="edfe9-218">まず、Kubernetes service discovery システムは、既定で "ラウンドロビン" の負荷分散を使用します。</span><span class="sxs-lookup"><span data-stu-id="edfe9-218">First, the Kubernetes service discovery system uses "round-robin" load-balancing by default.</span></span> <span data-ttu-id="edfe9-219">最初に DNS サーバーにクエリを実行すると、サービスに対して最初に一致する IP アドレスが返されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-219">The first time the DNS server is queried, it will return the first matching IP address for the service.</span></span> <span data-ttu-id="edfe9-220">次に、リスト内の次の IP アドレス、最後まで、その時点で、ループが開始されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-220">The next time, the next IP address in the list, and so on, until the end, at which point it loops back to the start.</span></span>

<span data-ttu-id="edfe9-221">次に、StockWeb アプリケーションの gRPC クライアントに使用される `HttpClient` が[ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)によって作成および管理され、このクライアントの1つのインスタンスがページの呼び出しごとに使用されます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-221">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="edfe9-222">クライアントは DNS 参照を1つだけ行うため、すべての要求が同じ IP アドレスにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-222">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="edfe9-223">さらに、パフォーマンス上の理由から `HttpClientHandler` がキャッシュされているので、キャッシュされた DNS エントリの有効期限が切れるか、何らかの理由でハンドラーインスタンスが破棄されるまで、複数の要求が同時に同じ IP アドレス*を使用し*ます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-223">Furthermore, because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="edfe9-224">つまり、既定では、gRPC サービスへの要求は、クラスター内のそのサービスのすべてのインスタンスでバランスが取れていません。</span><span class="sxs-lookup"><span data-stu-id="edfe9-224">This means that by default requests to a gRPC service aren't balanced across all instances of that service in the cluster.</span></span> <span data-ttu-id="edfe9-225">コンシューマーによって使用されるインスタンスは異なりますが、要求の配布とリソースのバランスの取れた使用は保証されません。</span><span class="sxs-lookup"><span data-stu-id="edfe9-225">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests and a balanced use of resources.</span></span>

<span data-ttu-id="edfe9-226">次の章「[サービスメッシュ](service-mesh.md)」では、この問題に対処する方法を見ていきます。</span><span class="sxs-lookup"><span data-stu-id="edfe9-226">The next chapter, [Service Meshes](service-mesh.md), will look at how to address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="edfe9-227">[前へ](docker.md)
>[次へ](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="edfe9-227">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
