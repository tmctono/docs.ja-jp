---
title: エラスティック スタックを使用したログ記録
description: エラスティックスタック、Logstash、および Kibana を使用したログ記録
ms.date: 09/23/2019
ms.openlocfilehash: 989834925bc08541bf484e1a4567a56ac324872f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841739"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="a0ff2-103">エラスティック スタックを使用したログ記録</span><span class="sxs-lookup"><span data-stu-id="a0ff2-103">Logging with Elastic Stack</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="a0ff2-104">優れた一元化されたログツールが多数あり、無料のオープンソースツールからコストが高いオプションまで、コストが大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="a0ff2-105">多くの場合、無料のツールは有料オファリングと同じか、それよりも優れています。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="a0ff2-106">このようなツールの1つに、エラスティック検索、Logstash、Kibana という3つのオープンソースコンポーネントが組み合わされています。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>
<span data-ttu-id="a0ff2-107">これらのツールをまとめて、エラスティックスタックまたは ELK スタックと呼びます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="a0ff2-108">エラスティックスタックの利点は何ですか?</span><span class="sxs-lookup"><span data-stu-id="a0ff2-108">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="a0ff2-109">エラスティックスタックは、低コストでスケーラブルなクラウド対応の方法で集中ログを提供します。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-109">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="a0ff2-110">ユーザーインターフェイスを使用すると、データ分析が効率化され、clunky インターフェイスとの連携ではなく、データからの有意の洞察を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-110">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="a0ff2-111">さまざまな種類の入力をサポートしているため、分散アプリケーションがさまざまな種類のサービスにまたがるため、継続的にログとメトリックデータをシステムにフィードできることが予想されます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-111">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="a0ff2-112">エラスティックスタックでは、大規模なデータセット全体にわたる高速検索もサポートされています。これにより、大規模なアプリケーションで詳細データをログに記録し、パフォーマンスの高い方法で可視性を維持することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-112">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="a0ff2-113">Logstash</span><span class="sxs-lookup"><span data-stu-id="a0ff2-113">Logstash</span></span>

<span data-ttu-id="a0ff2-114">最初のコンポーネントは[Logstash](https://www.elastic.co/products/logstash)です。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-114">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="a0ff2-115">このツールは、さまざまなソースからログ情報を収集するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-115">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="a0ff2-116">たとえば、Logstash はディスクからログを読み取り、 [Serilog](https://serilog.net/)などのログライブラリからもメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-116">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="a0ff2-117">Logstash では、ログの受信時に基本的なフィルター処理と拡張を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-117">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="a0ff2-118">たとえば、ログに IP アドレスが含まれている場合は、地理的な参照を行うように Logstash を構成し、そのメッセージの国または郵便の発信元を取得するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-118">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="a0ff2-119">Serilog は、パラメーター化されたログ記録が可能な .NET 言語のログライブラリです。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-119">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="a0ff2-120">フィールドを埋め込むテキストログメッセージを生成する代わりに、パラメーターが個別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-120">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="a0ff2-121">これにより、よりインテリジェントなフィルター処理と検索が可能になります。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-121">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="a0ff2-122">Logstash に書き込むためのサンプル Serilog 構成は、図7-2 に示されています。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-122">A sample Serilog configuration for writing to Logstash appears in Figure 7-2.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="a0ff2-123">**図 7-2**ログ情報を HTTP 経由で logstash に直接書き込むための serilog config</span><span class="sxs-lookup"><span data-stu-id="a0ff2-123">**Figure 7-2** Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="a0ff2-124">Logstash は、図7-3 に示すような構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-124">Logstash would use a configuration like the one shown in Figure 7-3.</span></span>

```
input {
    http {
        #default host 0.0.0.0:8080
        codec => json
    }
}

output {
    elasticsearch {
        hosts => "elasticsearch:9200"
        index=>"sales-%{+xxxx.ww}"
    }
}
```

<span data-ttu-id="a0ff2-125">**図 7-3** -Serilog からログを使用するための logstash の構成</span><span class="sxs-lookup"><span data-stu-id="a0ff2-125">**Figure 7-3** - A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="a0ff2-126">広範なログ操作が必要ないシナリオでは、[拍](https://www.elastic.co/products/beats)と呼ばれる logstash の代替手段として使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-126">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="a0ff2-127">拍は、ログからネットワークデータや稼働時間の情報まで、さまざまなデータを収集できるツールファミリです。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-127">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="a0ff2-128">多くのアプリケーションでは、Logstash と拍の両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-128">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="a0ff2-129">ログが Logstash によって収集されたら、そのログを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-129">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="a0ff2-130">Logstash は多くの異なる出力をサポートしますが、より興味深いものの1つはエラスティック検索です。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-130">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="a0ff2-131">エラスティック検索</span><span class="sxs-lookup"><span data-stu-id="a0ff2-131">Elastic search</span></span>

<span data-ttu-id="a0ff2-132">エラスティック検索は、ログの受信時にインデックスを作成できる強力な検索エンジンです。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-132">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="a0ff2-133">ログに対してクエリを実行することが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-133">It makes running queries against the logs quick.</span></span> <span data-ttu-id="a0ff2-134">エラスティック検索は膨大な量のログを処理でき、極端なケースでは多数のノードにわたってスケールアウトできます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-134">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="a0ff2-135">パラメーターを格納するために作成されたログメッセージ、またはパラメーターが Logstash 処理によって分割されていることを示すログメッセージは、Elasticsearch がこの情報を保持するように直接照会できます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-135">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="a0ff2-136">`jill@example.com`によってアクセスされた上位10ページを検索するクエリは、図7-4 に示されています。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-136">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-4.</span></span>

```
"query": {
    "match": {
      "user": "jill@example.com"
    }
  },
  "aggregations": {
    "top_10_pages": {
      "terms": {
        "field": "page",
        "size": 10
      }
    }
  }
```

<span data-ttu-id="a0ff2-137">**図 7-4** -ユーザーがアクセスした上位10ページを検索するための Elasticsearch クエリ</span><span class="sxs-lookup"><span data-stu-id="a0ff2-137">**Figure 7-4** - An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="a0ff2-138">Kibana web ダッシュボードを使用した情報の視覚化</span><span class="sxs-lookup"><span data-stu-id="a0ff2-138">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="a0ff2-139">スタックの最後のコンポーネントは Kibana です。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-139">The final component of the stack is Kibana.</span></span> <span data-ttu-id="a0ff2-140">このツールは、web ダッシュボードで対話型の視覚化を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-140">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="a0ff2-141">ダッシュボードは、技術以外のユーザーによっても事前に作られている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-141">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="a0ff2-142">Elasticsearch インデックスに格納されているほとんどのデータは、Kibana ダッシュボードに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-142">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="a0ff2-143">個々のユーザーには異なるダッシュボードが必要になる場合があり、Kibana ではユーザー固有のダッシュボードを許可することによってカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-143">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="a0ff2-144">Azure でのエラスティックスタックのインストール</span><span class="sxs-lookup"><span data-stu-id="a0ff2-144">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="a0ff2-145">エラスティックスタックは、さまざまな方法で Azure にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-145">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="a0ff2-146">常に、[仮想マシンをプロビジョニングし、エラスティックスタックを直接インストール](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)することができます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-146">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="a0ff2-147">経験豊富なユーザーは、このオプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-147">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="a0ff2-148">サービスとしてのインフラストラクチャにを展開すると、管理オーバーヘッドが大きくなります。これにより、コンピューターのセキュリティ保護や修正プログラムによる最新情報の保持など、サービスとしてのインフラストラクチャに関連するすべてのタスクの所有権を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-148">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="a0ff2-149">オーバーヘッドが少ないオプションは、エラスティックスタックが既に構成されている多くの Docker コンテナーの1つを使用することです。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-149">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="a0ff2-150">これらのコンテナーは、既存の Kubernetes クラスターにドロップして、アプリケーションコードと共に実行できます。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-150">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="a0ff2-151">[Sebp/elk](https://elk-docker.readthedocs.io/)コンテナーは、適切にドキュメント化され、テストされたエラスティックスタックコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-151">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="a0ff2-152">もう1つのオプションは、最近発表された[サービスとしての ELK オファリング](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/)です。</span><span class="sxs-lookup"><span data-stu-id="a0ff2-152">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="a0ff2-153">参照</span><span class="sxs-lookup"><span data-stu-id="a0ff2-153">References</span></span>

- [<span data-ttu-id="a0ff2-154">エラスティックスタックを Azure にインストールする</span><span class="sxs-lookup"><span data-stu-id="a0ff2-154">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="a0ff2-155">[前へ](observability-patterns.md)
>[次へ](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="a0ff2-155">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
