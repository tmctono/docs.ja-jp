---
title: Apache Spark アプリケーション用の .NET を Azure HDInsight にデプロイする
description: Apache Spark アプリケーション用の .NET を HDInsight にデプロイする方法について説明します。
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 4769c194520790ce217d46d1d3197b20742d4f1a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "69576949"
---
# <a name="deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a><span data-ttu-id="632a4-103">Apache Spark アプリケーション用の .NET を Azure HDInsight にデプロイする</span><span class="sxs-lookup"><span data-stu-id="632a4-103">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>

<span data-ttu-id="632a4-104">このチュートリアルでは、Apache Spark アプリケーション用の .NET を Azure HDInsight にデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="632a4-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Azure HDInsight.</span></span>

<span data-ttu-id="632a4-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="632a4-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="632a4-106">Microsoft の Spark を準備します。</span><span class="sxs-lookup"><span data-stu-id="632a4-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="632a4-107">Spark .NET アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="632a4-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="632a4-108">アプリを Azure HDInsight にデプロイする</span><span class="sxs-lookup"><span data-stu-id="632a4-108">Deploy your app to Azure HDInsight</span></span>
> * <span data-ttu-id="632a4-109">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="632a4-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="632a4-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="632a4-110">Prerequisites</span></span>

<span data-ttu-id="632a4-111">開始する前に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="632a4-111">Before you start, do the following:</span></span>

* <span data-ttu-id="632a4-112">[Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="632a4-112">Download [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/).</span></span>
* <span data-ttu-id="632a4-113">[Install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="632a4-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="632a4-114">これは、後で Apache Spark 依存ファイル用の .NET を Spark クラスターのワーカーノードにコピーするために後で使用するヘルパースクリプトです。</span><span class="sxs-lookup"><span data-stu-id="632a4-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="632a4-115">ワーカーの依存関係を準備する</span><span class="sxs-lookup"><span data-stu-id="632a4-115">Prepare worker dependencies</span></span>

<span data-ttu-id="632a4-116">**Microsoft spark**は、spark クラスターの個々のワーカーノードに存在するバックエンドコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="632a4-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="632a4-117">C# Udf (ユーザー定義関数) を実行する場合、Spark は、.net CLR を起動して udf を実行する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="632a4-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="632a4-118">**Microsoft spark**は、この機能を有効にするクラスのコレクションを spark に提供します。</span><span class="sxs-lookup"><span data-stu-id="632a4-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="632a4-119">クラスターにデプロイする[Microsoft Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp リリースを選択します。</span><span class="sxs-lookup"><span data-stu-id="632a4-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="632a4-120">たとえば、を`.NET for Apache Spark v0.1.0`使用`netcoreapp2.1`する場合は、 [linux-x64-0.1.0](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)をダウンロードする必要があります。これは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="632a4-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="632a4-121">クラスター `Microsoft.Spark.Worker.<release>.tar.gz`からアクセスできる分散ファイルシステム (HDFS、 [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) 、adls など) にアップロードして、そのファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="632a4-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="632a4-122">Apache Spark アプリ用の .NET を準備する</span><span class="sxs-lookup"><span data-stu-id="632a4-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="632a4-123">[入門](get-started.md)チュートリアルに従ってアプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="632a4-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="632a4-124">Spark .NET アプリを自己完結型として発行します。</span><span class="sxs-lookup"><span data-stu-id="632a4-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="632a4-125">Linux では、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="632a4-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="632a4-126">パブリッシュ`<your app>.zip`されたファイルのを生成します。</span><span class="sxs-lookup"><span data-stu-id="632a4-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="632a4-127">Linux では、を使用して`zip`次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="632a4-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="632a4-128">クラスターからアクセス可能な分散ファイルシステム (HDFS、ADLS、ADLS など) に以下をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="632a4-128">Upload the following to a distributed file system (e.g., HDFS, WASB, ADLS) that your cluster has access to:</span></span>

   * <span data-ttu-id="632a4-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar` :この jar は、 [Microsoft Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet パッケージの一部として含まれており、アプリのビルド出力ディレクトリに併置されています。</span><span class="sxs-lookup"><span data-stu-id="632a4-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="632a4-130">各実行プログラムの作業ディレクトリに配置されるファイル (依存関係ファイルや、 `app`すべてのワーカーがアクセスできる共通のデータなど) またはアセンブリ (ユーザー定義関数またはが依存するライブラリを含む dll など)。</span><span class="sxs-lookup"><span data-stu-id="632a4-130">Files (like dependency files or common data accessible to every worker) or Assemblies (like DLLs that contain your user-defined functions or libraries that your `app` depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-azure-hdinsight-spark"></a><span data-ttu-id="632a4-131">Azure HDInsight Spark に配置する</span><span class="sxs-lookup"><span data-stu-id="632a4-131">Deploy to Azure HDInsight Spark</span></span>

<span data-ttu-id="632a4-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview)は、クラウドで Apache Spark の Microsoft による実装であり、ユーザーは Azure で Spark クラスターを起動して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="632a4-132">[Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-overview) is the Microsoft implementation of Apache Spark in the cloud that allows users to launch and configure Spark clusters in Azure.</span></span> <span data-ttu-id="632a4-133">HDInsight Spark クラスターを使用して、 [Azure Storage](https://azure.microsoft.com/services/storage/)または[Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2)に格納されているデータを処理できます。</span><span class="sxs-lookup"><span data-stu-id="632a4-133">You can use HDInsight Spark clusters to process your data stored in [Azure Storage](https://azure.microsoft.com/services/storage/) or [Azure Data Lake Storage](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-use-data-lake-storage-gen2).</span></span>

> [!NOTE]
> <span data-ttu-id="632a4-134">Azure HDInsight Spark は Linux ベースです。</span><span class="sxs-lookup"><span data-stu-id="632a4-134">Azure HDInsight Spark is Linux-based.</span></span> <span data-ttu-id="632a4-135">Azure HDInsight Spark にアプリをデプロイする場合は、アプリに互換性が .NET Standard こと、および[.Net Core コンパイラ](https://dotnet.microsoft.com/download)を使用してアプリをコンパイルすることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="632a4-135">If you are interested in deploying your app to Azure HDInsight Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="632a4-136">Microsoft Spark をデプロイする</span><span class="sxs-lookup"><span data-stu-id="632a4-136">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="632a4-137">この手順は、クラスターに対して1回のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="632a4-137">This step is only required once for your cluster.</span></span>

<span data-ttu-id="632a4-138">HDInsight `install-worker.sh`の[スクリプトアクション](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)を使用して、クラスターでを実行します。</span><span class="sxs-lookup"><span data-stu-id="632a4-138">Run `install-worker.sh` on the cluster using [HDInsight Script Actions](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux).</span></span>

|<span data-ttu-id="632a4-139">設定</span><span class="sxs-lookup"><span data-stu-id="632a4-139">Setting</span></span>|<span data-ttu-id="632a4-140">値</span><span class="sxs-lookup"><span data-stu-id="632a4-140">Value</span></span>|
|-------|-----|
|<span data-ttu-id="632a4-141">スクリプトの種類</span><span class="sxs-lookup"><span data-stu-id="632a4-141">Script type</span></span>|<span data-ttu-id="632a4-142">カスタム</span><span class="sxs-lookup"><span data-stu-id="632a4-142">Custom</span></span>|
|<span data-ttu-id="632a4-143">Name</span><span class="sxs-lookup"><span data-stu-id="632a4-143">Name</span></span>|<span data-ttu-id="632a4-144">Microsoft Spark をインストールします。</span><span class="sxs-lookup"><span data-stu-id="632a4-144">Install Microsoft.Spark.Worker</span></span>|
|<span data-ttu-id="632a4-145">Bash スクリプト URI</span><span class="sxs-lookup"><span data-stu-id="632a4-145">Bash script URI</span></span>|<span data-ttu-id="632a4-146">アップロード`install-worker.sh`先の URI。</span><span class="sxs-lookup"><span data-stu-id="632a4-146">The URI to which you uploaded `install-worker.sh`.</span></span> <span data-ttu-id="632a4-147">たとえば、`abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span><span class="sxs-lookup"><span data-stu-id="632a4-147">For example, `abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/install-worker.sh`</span></span>|
|<span data-ttu-id="632a4-148">ノードの種類</span><span class="sxs-lookup"><span data-stu-id="632a4-148">Node type(s)</span></span>|<span data-ttu-id="632a4-149">者</span><span class="sxs-lookup"><span data-stu-id="632a4-149">Worker</span></span>|
|<span data-ttu-id="632a4-150">パラメーター</span><span class="sxs-lookup"><span data-stu-id="632a4-150">Parameters</span></span>|<span data-ttu-id="632a4-151">パラメーターを`install-worker.sh`にします。</span><span class="sxs-lookup"><span data-stu-id="632a4-151">Parameters to `install-worker.sh`.</span></span> <span data-ttu-id="632a4-152">たとえば、Azure Data Lake Gen 2 `install-worker.sh` `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`にアップロードした場合は、のようになります。</span><span class="sxs-lookup"><span data-stu-id="632a4-152">For example, if you uploaded `install-worker.sh` to Azure Data Lake Gen 2 then it would be `azure abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz /usr/local/bin`.</span></span>|

![スクリプトアクションの画像](./media/hdinsight-deployment/deployment-hdi-action-script.png)

## <a name="run-your-app"></a><span data-ttu-id="632a4-154">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="632a4-154">Run your app</span></span>

<span data-ttu-id="632a4-155">または Apache Livy を使用して`spark-submit` 、ジョブを Azure HDInsight に送信できます。</span><span class="sxs-lookup"><span data-stu-id="632a4-155">You can submit your job to Azure HDInsight using `spark-submit` or Apache Livy.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="632a4-156">Spark 送信の使用</span><span class="sxs-lookup"><span data-stu-id="632a4-156">Use spark-submit</span></span>

<span data-ttu-id="632a4-157">[Spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html)コマンドを使用して、Apache Spark ジョブ用の .Net を Azure HDInsight に送信できます。</span><span class="sxs-lookup"><span data-stu-id="632a4-157">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="632a4-158">`ssh`クラスター内のいずれかのヘッドノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="632a4-158">`ssh` into one of the head nodes in your cluster.</span></span>

1. <span data-ttu-id="632a4-159">を`spark-submit`実行します。</span><span class="sxs-lookup"><span data-stu-id="632a4-159">Run `spark-submit`:</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip <your app> <app arg 1> <app arg 2> ... <app arg n>
   ```

### <a name="use-apache-livy"></a><span data-ttu-id="632a4-160">Apache Livy を使用する</span><span class="sxs-lookup"><span data-stu-id="632a4-160">Use Apache Livy</span></span>

<span data-ttu-id="632a4-161">[Apache Livy](https://livy.incubator.apache.org/)(Apache Spark REST API) を使用して、Apache Spark ジョブ用の .net を Azure HDInsight Spark クラスターに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="632a4-161">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="632a4-162">詳細については、「 [Apache Livy を使用したリモートジョブ](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="632a4-162">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="632a4-163">次のコマンドは、Linux でを使用`curl`して実行できます。</span><span class="sxs-lookup"><span data-stu-id="632a4-163">You can run the following command on Linux using `curl`:</span></span>

```bash
curl -k -v -X POST "https://<your spark cluster>.azurehdinsight.net/livy/batches" \
-u "<hdinsight username>:<hdinsight password>" \
-H "Content-Type: application/json" \
-H "X-Requested-By: <hdinsight username>" \
-d @- << EOF
{
    "file":"abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar",
    "className":"org.apache.spark.deploy.DotnetRunner",
    "files":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<udf assembly>", "abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<file>"],
    "args":["abfss://<your-file-system-name>@<your-storage-account-name>.dfs.core.windows.net/<some dir>/<your app>.zip","<your app>","<app arg 1>","<app arg 2>,"...","<app arg n>"]
}
EOF
```

## <a name="next-steps"></a><span data-ttu-id="632a4-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="632a4-164">Next steps</span></span>

<span data-ttu-id="632a4-165">このチュートリアルでは、Apache Spark アプリケーション用の .NET を Azure HDInsight にデプロイしました。</span><span class="sxs-lookup"><span data-stu-id="632a4-165">In this tutorial, you deployed your .NET for Apache Spark application to Azure HDInsight.</span></span> <span data-ttu-id="632a4-166">HDInsight の詳細については、Azure HDInsight のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="632a4-166">To learn more about HDInsight, continue to the Azure HDInsight Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="632a4-167">Azure HDInsight のドキュメント</span><span class="sxs-lookup"><span data-stu-id="632a4-167">Azure HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
