---
title: Azure Kubernetes Services での監視
description: Azure Kubernetes Services での監視
ms.date: 09/23/2019
ms.openlocfilehash: fc9d84fd738ff1c40d25860680e14313c9323517
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711650"
---
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="1fb2f-103">Azure Kubernetes Services での監視</span><span class="sxs-lookup"><span data-stu-id="1fb2f-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1fb2f-104">Kubernetes の組み込みログはプリミティブです。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="1fb2f-105">ただし、Kubernetes からログを取得し、適切に分析できる場所にするための優れたオプションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="1fb2f-106">AKS クラスターを監視する必要がある場合は、Kubernetes のエラスティックスタックの構成が優れたソリューションです。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="1fb2f-107">エラスティックスタック</span><span class="sxs-lookup"><span data-stu-id="1fb2f-107">Elastic Stack</span></span>

<span data-ttu-id="1fb2f-108">エラスティックスタックは、Kubernetes クラスターから情報を収集するための強力なオプションです。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-108">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="1fb2f-109">Kubernetes では、Elasticsearch エンドポイントへのログの送信がサポートされています。[ほとんど](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)の場合、図7-5 に示すように、環境変数を設定するだけで始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-109">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="1fb2f-110">**図 7-5** -Kubernetes の構成変数</span><span class="sxs-lookup"><span data-stu-id="1fb2f-110">**Figure 7-5** - Configuration variables for Kubernetes</span></span>

<span data-ttu-id="1fb2f-111">これにより、クラスターに Elasticsearch がインストールされ、すべてのクラスターログをそのクラスターに送信するターゲットになります。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-111">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="1fb2f-112">Kibana ダッシュボードの例 ![、取り込まれたからのログに対するクエリの結果を Kubernetes](./media/kibana-dashboard.png)
**図 7-6**に示します。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-112">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="1fb2f-113">Kubernetes から取り込まれたのログに対するクエリの結果を表示する Kibana ダッシュボードの例</span><span class="sxs-lookup"><span data-stu-id="1fb2f-113">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="azure-container-monitoring"></a><span data-ttu-id="1fb2f-114">Azure コンテナーの監視</span><span class="sxs-lookup"><span data-stu-id="1fb2f-114">Azure Container Monitoring</span></span>

<span data-ttu-id="1fb2f-115">Azure Container Monitoring は、Kubernetes だけでなく、DC/OS、Docker の群れ、Red Hat OpenShift などの他のオーケストレーションエンジンからのログの使用もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-115">Azure Container Monitoring supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="1fb2f-116">さまざまなコンテナーからのログの使用 ![](./media/containers-diagram.png)
**図 7-7**。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-116">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-7**.</span></span>  <span data-ttu-id="1fb2f-117">さまざまなコンテナーからのログの使用</span><span class="sxs-lookup"><span data-stu-id="1fb2f-117">Consuming logs from various containers</span></span>

<span data-ttu-id="1fb2f-118">ログとメトリックの情報は、クラスターで実行されているコンテナーだけでなく、クラスターからも収集されます。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-118">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="1fb2f-119">これにより、2つのログ情報を相互に関連付けることができるため、エラーをより簡単に追跡できます。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-119">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="1fb2f-120">ログコレクターのインストールは、 [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes)クラスターと[Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes)クラスターで異なります。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-120">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="1fb2f-121">ただし、どちらの場合も、ログの収集は Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)として実装されます。つまり、ログコレクターは各ノード上のコンテナーとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-121">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="1fb2f-122">Azure Monitor デーモンを実行している orchestrator またはオペレーティングシステムにかかわらず、ログ情報は、ユーザーが使い慣れているのと同じ Azure Monitor ツールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-122">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="1fb2f-123">これにより、ハイブリッド Kubernetes/Azure Functions 環境などのさまざまなログソースが混在する環境での並行操作が可能になります。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-123">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="1fb2f-124">多数の実行中のコンテナーからのログ記録とメトリック情報を示すサンプルダッシュボードを ![します。](./media/containers-dashboard.png)
**図 7-8**。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-124">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-8**.</span></span> <span data-ttu-id="1fb2f-125">多数の実行中のコンテナーからのログ記録とメトリック情報を示すサンプルダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-125">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="1fb2f-126">Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="1fb2f-126">Log.Finalize()</span></span>

<span data-ttu-id="1fb2f-127">ログ記録は、大規模なアプリケーションのデプロイにおいて、見過ごされていて最も重要な部分の1つです。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-127">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="1fb2f-128">アプリケーションのサイズと複雑さが増加するにつれて、アプリケーションのデバッグが困難になります。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-128">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="1fb2f-129">高品質のログを使用すると、デバッグがはるかに簡単になり、"ほぼ不可能な" 領域から "快適なエクスペリエンス" に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="1fb2f-129">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1fb2f-130">[前へ](logging-with-elastic-stack.md)
>[次へ](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="1fb2f-130">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
