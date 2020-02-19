---
title: Azure Kubernetes Services での監視
description: Azure Kubernetes Services での監視
ms.date: 02/05/2020
ms.openlocfilehash: 5c46b9e8599f70d430ad26cf1364343454d30a16
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450064"
---
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="b4811-103">Azure Kubernetes Services での監視</span><span class="sxs-lookup"><span data-stu-id="b4811-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b4811-104">Kubernetes の組み込みログはプリミティブです。</span><span class="sxs-lookup"><span data-stu-id="b4811-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="b4811-105">ただし、Kubernetes からログを取得し、適切に分析できる場所にするための優れたオプションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b4811-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="b4811-106">AKS クラスターを監視する必要がある場合は、Kubernetes のエラスティックスタックの構成が優れたソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b4811-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="azure-monitor-for-containers"></a><span data-ttu-id="b4811-107">Azure Monitor for Containers</span><span class="sxs-lookup"><span data-stu-id="b4811-107">Azure Monitor for Containers</span></span>

<span data-ttu-id="b4811-108">[コンテナーの Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview)は、Kubernetes だけでなく、DC/OS、Docker の群れ、Red Hat openshift などの他のオーケストレーションエンジンからのログの使用もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b4811-108">[Azure Monitor for Containers](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview) supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="b4811-109">さまざまなコンテナーからのログの使用 ![](./media/containers-diagram.png)
**図 7-10**。</span><span class="sxs-lookup"><span data-stu-id="b4811-109">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-10**.</span></span> <span data-ttu-id="b4811-110">さまざまなコンテナーからのログの使用</span><span class="sxs-lookup"><span data-stu-id="b4811-110">Consuming logs from various containers</span></span>

<span data-ttu-id="b4811-111">[Prometheus](https://prometheus.io/)は、広く普及しているオープンソースのメトリック監視ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b4811-111">[Prometheus](https://prometheus.io/) is a popular open source metric monitoring solution.</span></span> <span data-ttu-id="b4811-112">クラウドネイティブコンピューティングファンデーションの一部です。</span><span class="sxs-lookup"><span data-stu-id="b4811-112">It is part of the Cloud Native Compute Foundation.</span></span> <span data-ttu-id="b4811-113">通常、Prometheus を使用するには、独自のストアで Prometheus サーバーを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4811-113">Typically, using Prometheus requires managing a Prometheus server with its own store.</span></span> <span data-ttu-id="b4811-114">ただし、[コンテナーの Azure Monitor は、Prometheus メトリックエンドポイントと直接統合](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-prometheus-integration)できるため、個別のサーバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b4811-114">However, [Azure Monitor for Containers provides direct integration with Prometheus metrics endpoints](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-prometheus-integration), so a separate server is not required.</span></span>

<span data-ttu-id="b4811-115">ログとメトリックの情報は、クラスターで実行されているコンテナーだけでなく、クラスターからも収集されます。</span><span class="sxs-lookup"><span data-stu-id="b4811-115">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="b4811-116">これにより、2つのログ情報を相互に関連付けることができるため、エラーをより簡単に追跡できます。</span><span class="sxs-lookup"><span data-stu-id="b4811-116">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="b4811-117">ログコレクターのインストールは、 [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes)クラスターと[Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes)クラスターで異なります。</span><span class="sxs-lookup"><span data-stu-id="b4811-117">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="b4811-118">ただし、どちらの場合も、ログの収集は Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)として実装されます。つまり、ログコレクターは各ノード上のコンテナーとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="b4811-118">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="b4811-119">Azure Monitor デーモンを実行している orchestrator またはオペレーティングシステムにかかわらず、ログ情報は、ユーザーが使い慣れているのと同じ Azure Monitor ツールに転送されます。</span><span class="sxs-lookup"><span data-stu-id="b4811-119">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="b4811-120">これにより、ハイブリッド Kubernetes/Azure Functions 環境などのさまざまなログソースが混在する環境での並行操作が可能になります。</span><span class="sxs-lookup"><span data-stu-id="b4811-120">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="b4811-121">多数の実行中のコンテナーからのログ記録とメトリック情報を示すサンプルダッシュボードを ![します。](./media/containers-dashboard.png)
**図 7-11**。</span><span class="sxs-lookup"><span data-stu-id="b4811-121">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-11**.</span></span> <span data-ttu-id="b4811-122">多数の実行中のコンテナーからのログ記録とメトリック情報を示すサンプルダッシュボードです。</span><span class="sxs-lookup"><span data-stu-id="b4811-122">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="b4811-123">Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="b4811-123">Log.Finalize()</span></span>

<span data-ttu-id="b4811-124">ログ記録は、大規模なアプリケーションのデプロイにおいて、見過ごされていて最も重要な部分の1つです。</span><span class="sxs-lookup"><span data-stu-id="b4811-124">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="b4811-125">アプリケーションのサイズと複雑さが増加するにつれて、アプリケーションのデバッグが困難になります。</span><span class="sxs-lookup"><span data-stu-id="b4811-125">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="b4811-126">高品質のログを使用すると、デバッグがはるかに簡単になり、"ほぼ不可能な" 領域から "快適なエクスペリエンス" に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="b4811-126">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b4811-127">[前へ](logging-with-elastic-stack.md)
>[次へ](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="b4811-127">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
