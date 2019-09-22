---
title: .NET for Apache Spark アプリケーションを Azure HDInsight にデプロイする
description: .NET for Apache Spark アプリケーションを Azure HDInsight にデプロイする方法を説明します。
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 2e8da5497035a83fde75bf91a7d21437d510b480
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117979"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="ae621-103">.NET for Apache Spark アプリケーションを Azure HDInsight にデプロイする</span><span class="sxs-lookup"><span data-stu-id="ae621-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="ae621-104">このチュートリアルでは、.NET for Apache Spark アプリケーションを Azure HDInsight にデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae621-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="ae621-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae621-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="ae621-106">Microsoft.Spark.Worker を準備する</span><span class="sxs-lookup"><span data-stu-id="ae621-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="ae621-107">Spark .NET アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="ae621-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="ae621-108">アプリを Azure HDInsight にデプロイする</span><span class="sxs-lookup"><span data-stu-id="ae621-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="ae621-109">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="ae621-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ae621-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ae621-110">Prerequisites</span></span>

<span data-ttu-id="ae621-111">開始する前に、以下を行います。</span><span class="sxs-lookup"><span data-stu-id="ae621-111">Before you start, do the following:</span></span>

* <span data-ttu-id="ae621-112">[Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ae621-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="ae621-113">[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) をお使いのローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ae621-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="ae621-114">これは、後で .NET for Apache Spark の依存ファイルを Spark クラスターのワーカー ノードにコピーするために使用するヘルパー スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="ae621-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="ae621-115">ワーカーの依存関係を準備する</span><span class="sxs-lookup"><span data-stu-id="ae621-115">Prepare worker dependencies</span></span>

<span data-ttu-id="ae621-116">**Microsoft.Spark.Worker** は、Spark クラスターの個々のワーカー ノードに存在するバックエンド コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="ae621-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="ae621-117">C# UDF (ユーザー定義関数) を実行する場合、.NET CLR を起動して UDF を実行する方法を Spark が理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae621-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="ae621-118">**Microsoft.Spark.Worker** により、この機能を有効にするクラスのコレクションが Spark に提供されます。</span><span class="sxs-lookup"><span data-stu-id="ae621-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="ae621-119">お使いのクラスターにデプロイされる [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp リリースを選択します。</span><span class="sxs-lookup"><span data-stu-id="ae621-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="ae621-120">たとえば、`netcoreapp2.1` を使用する `.NET for Apache Spark v0.1.0` が必要な場合は、[Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ae621-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="ae621-121">クラスターからアクセスできる分散ファイル システム (HDFS、WASB、ADLS など) に、`Microsoft.Spark.Worker.<release>.tar.gz` と [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ae621-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="ae621-122">.NET for Apache Spark アプリを準備する</span><span class="sxs-lookup"><span data-stu-id="ae621-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="ae621-123">[入門](get-started.md)チュートリアルに従ってアプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ae621-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="ae621-124">Spark .NET アプリを自己完結型として発行します。</span><span class="sxs-lookup"><span data-stu-id="ae621-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="ae621-125">Linux では、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae621-125">You can run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="ae621-126">発行されたファイル用に `<your app>.zip` を生成します。</span><span class="sxs-lookup"><span data-stu-id="ae621-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="ae621-127">Linux では、`zip` を使用して次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae621-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="ae621-128">クラスターからアクセスできる分散ファイル システム (HDFS、WASB、ADLS など) に、次をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ae621-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="ae621-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`:この jar は、[Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet パッケージの一部として含まれており、アプリのビルド出力ディレクトリに併置されています。</span><span class="sxs-lookup"><span data-stu-id="ae621-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="ae621-130">各 Executor の作業ディレクトリ内に配置されるファイル (依存関係ファイルや、すべてのワーカーからアクセスできる共通データなど) またはアセンブリ (`app` が依存しているユーザー定義関数またはライブラリを含む DLL など)。</span><span class="sxs-lookup"><span data-stu-id="ae621-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="ae621-131">Azure HDInsight Spark にデプロイする</span><span class="sxs-lookup"><span data-stu-id="ae621-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="ae621-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) は、ユーザーが Azure で Spark クラスターを起動して構成できるようにするための、Microsoft による Apache Spark のクラウドへの実装です。</span><span class="sxs-lookup"><span data-stu-id="ae621-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="ae621-133">HDInsight Spark クラスターを使用して、[Azure Storage](https://azure.microsoft.com/services/storage/) または [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2) に格納されているデータを処理できます。</span><span class="sxs-lookup"><span data-stu-id="ae621-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="ae621-134">Azure HDInsight Spark は Linux ベースです。</span><span class="sxs-lookup"><span data-stu-id="ae621-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="ae621-135">Azure HDInsight Spark へのアプリのデプロイに関心がある場合は、アプリが .NET Standard と互換性があることと、アプリのコンパイルに [.NET Core コンパイラ](https://dotnet.microsoft.com/download)を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ae621-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="ae621-136">Microsoft.Spark.Worker をデプロイする</span><span class="sxs-lookup"><span data-stu-id="ae621-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="ae621-137">この手順は、クラスターに対して 1 回のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ae621-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="ae621-138">[HDInsight スクリプト アクション](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)を使用して、クラスターで `install-worker.sh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae621-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="ae621-139">設定</span><span class="sxs-lookup"><span data-stu-id="ae621-139">Setting</span></span>|<span data-ttu-id="ae621-140">[値]</span><span class="sxs-lookup"><span data-stu-id="ae621-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="ae621-141">スクリプトの種類</span><span class="sxs-lookup"><span data-stu-id="ae621-141">Script type</span></span>|<span data-ttu-id="ae621-142">カスタム</span><span class="sxs-lookup"><span data-stu-id="ae621-142">Custom</span></span>|
|<span data-ttu-id="ae621-143">name</span><span class="sxs-lookup"><span data-stu-id="ae621-143">Name</span></span>|<span data-ttu-id="ae621-144">Microsoft.Spark.Worker をインストールする</span><span class="sxs-lookup"><span data-stu-id="ae621-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="ae621-145">Bash スクリプト URI</span><span class="sxs-lookup"><span data-stu-id="ae621-145">Bash script URI</span></span>|<span data-ttu-id="ae621-146">`install-worker.sh` のアップロード先の URI。</span><span class="sxs-lookup"><span data-stu-id="ae621-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="ae621-147">たとえば、`abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span><span class="sxs-lookup"><span data-stu-id="ae621-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="ae621-148">ノードの種類</span><span class="sxs-lookup"><span data-stu-id="ae621-148">Node type(s)</span></span>|<span data-ttu-id="ae621-149">ワーカー</span><span class="sxs-lookup"><span data-stu-id="ae621-149">Worker</span></span>|
|<span data-ttu-id="ae621-150">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae621-150">Parameters</span></span>|<span data-ttu-id="ae621-151">`install-worker.sh` のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="ae621-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="ae621-152">たとえば、`install-worker.sh` を Azure Data Lake Gen 2 にアップロードした場合、これは `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin` になります。</span><span class="sxs-lookup"><span data-stu-id="ae621-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![スクリプト アクションの画像](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="ae621-154">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="ae621-154">Run your app</span></span>

<span data-ttu-id="ae621-155">`spark-submit` または Apache Livy を使用して、ジョブを Azure HDInsight に送信できます。</span><span class="sxs-lookup"><span data-stu-id="ae621-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="ae621-156">spark-submit を使用する</span><span class="sxs-lookup"><span data-stu-id="ae621-156">Use spark-submit</span></span>

<span data-ttu-id="ae621-157">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) コマンドを使用して、.NET for Apache Spark ジョブを Azure HDInsight に送信できます。</span><span class="sxs-lookup"><span data-stu-id="ae621-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="ae621-158">クラスター内のいずれかのヘッド ノードに `ssh` で接続します。</span><span class="sxs-lookup"><span data-stu-id="ae621-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="ae621-159">`spark-submit` を実行します。</span><span class="sxs-lookup"><span data-stu-id="ae621-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="ae621-160">Apache Livy を使用する</span><span class="sxs-lookup"><span data-stu-id="ae621-160">Use Apache Livy</span></span>

<span data-ttu-id="ae621-161">[Apache Livy](https://livy.incubator.apache.org/) (Apache Spark REST API) を使用して、.NET for Apache Spark ジョブを Azure HDInsight Spark クラスターに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="ae621-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="ae621-162">詳細については、[Apache Livy を使用したリモート ジョブ](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae621-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="ae621-163">Linux では、`curl` を使用して次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ae621-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.dotnet.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="ae621-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="ae621-164">Next steps</span></span>

<span data-ttu-id="ae621-165">このチュートリアルでは、.NET for Apache Spark アプリケーションを Azure HDInsight にデプロイしました。</span><span class="sxs-lookup"><span data-stu-id="ae621-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="ae621-166">HDInsight の詳細については、Azure HDInsight のドキュメントに進んでください。</span><span class="sxs-lookup"><span data-stu-id="ae621-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ae621-167">Azure HDInsight のドキュメント</span><span class="sxs-lookup"><span data-stu-id="ae621-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
