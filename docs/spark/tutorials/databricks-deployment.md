---
title: Apache Spark アプリケーション用の .NET を Databricks にデプロイする
description: Apache Spark アプリケーション用の .NET を Databricks にデプロイする方法について説明します。
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: ca9e93a413622c84325ca9fc8bac17268b990c5a
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "69576969"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="214eb-103">Apache Spark アプリケーション用の .NET を Databricks にデプロイする</span><span class="sxs-lookup"><span data-stu-id="214eb-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="214eb-104">このチュートリアルでは、Apache Spark アプリケーション用の .NET を Databricks にデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="214eb-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="214eb-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="214eb-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="214eb-106">Microsoft の Spark を準備します。</span><span class="sxs-lookup"><span data-stu-id="214eb-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="214eb-107">Spark .NET アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="214eb-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="214eb-108">アプリを Databricks にデプロイする</span><span class="sxs-lookup"><span data-stu-id="214eb-108">Deploy your app to Databricks</span></span>
> * <span data-ttu-id="214eb-109">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="214eb-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="214eb-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="214eb-110">Prerequisites</span></span>

<span data-ttu-id="214eb-111">開始する前に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="214eb-111">Before you start, do the following:</span></span>

* <span data-ttu-id="214eb-112">[DATABRICKS CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="214eb-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
* <span data-ttu-id="214eb-113">[Install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="214eb-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="214eb-114">これは、後で Apache Spark 依存ファイル用の .NET を Spark クラスターのワーカーノードにコピーするために後で使用するヘルパースクリプトです。</span><span class="sxs-lookup"><span data-stu-id="214eb-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="214eb-115">ワーカーの依存関係を準備する</span><span class="sxs-lookup"><span data-stu-id="214eb-115">Prepare worker dependencies</span></span>

<span data-ttu-id="214eb-116">**Microsoft spark**は、spark クラスターの個々のワーカーノードに存在するバックエンドコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="214eb-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="214eb-117">C# Udf (ユーザー定義関数) を実行する場合、Spark は、.net CLR を起動して udf を実行する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="214eb-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="214eb-118">**Microsoft spark**は、この機能を有効にするクラスのコレクションを spark に提供します。</span><span class="sxs-lookup"><span data-stu-id="214eb-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="214eb-119">クラスターにデプロイする[Microsoft Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp リリースを選択します。</span><span class="sxs-lookup"><span data-stu-id="214eb-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="214eb-120">たとえば、を`.NET for Apache Spark v0.1.0`使用`netcoreapp2.1`する場合は、 [linux-x64-0.1.0](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)をダウンロードする必要があります。これは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="214eb-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="214eb-121">クラスター `Microsoft.Spark.Worker.<release>.tar.gz`からアクセスできる分散ファイルシステム (たとえば、DBFS) にアップロードして[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh)します。</span><span class="sxs-lookup"><span data-stu-id="214eb-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="214eb-122">Apache Spark アプリ用の .NET を準備する</span><span class="sxs-lookup"><span data-stu-id="214eb-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="214eb-123">[入門](get-started.md)チュートリアルに従ってアプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="214eb-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="214eb-124">Spark .NET アプリを自己完結型として発行します。</span><span class="sxs-lookup"><span data-stu-id="214eb-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="214eb-125">Linux では、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="214eb-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="214eb-126">パブリッシュ`<your app>.zip`されたファイルのを生成します。</span><span class="sxs-lookup"><span data-stu-id="214eb-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="214eb-127">Linux では、を使用して`zip`次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="214eb-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="214eb-128">クラスターがアクセスできる分散ファイルシステム (たとえば、DBFS) に次のコードをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="214eb-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   * <span data-ttu-id="214eb-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`:この jar は、 [Microsoft Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet パッケージの一部として含まれており、アプリのビルド出力ディレクトリに併置されています。</span><span class="sxs-lookup"><span data-stu-id="214eb-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="214eb-130">各実行プログラムの作業ディレクトリに配置されるファイル (依存関係ファイルや、すべてのワーカーからアクセスできる共通データなど) またはアセンブリ (アプリが依存しているユーザー定義関数またはライブラリを含む Dll など)。</span><span class="sxs-lookup"><span data-stu-id="214eb-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="214eb-131">Databricks のデプロイする</span><span class="sxs-lookup"><span data-stu-id="214eb-131">Deploy to Databricks</span></span>

<span data-ttu-id="214eb-132">[Databricks](https://databricks.com)は、Apache Spark を使用してクラウドベースのビッグデータ処理を提供するプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="214eb-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!Note] 
> <span data-ttu-id="214eb-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/)と[AWS Databricks](https://databricks.com/aws)は Linux ベースです。</span><span class="sxs-lookup"><span data-stu-id="214eb-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="214eb-134">そのため、Databricks へのアプリのデプロイに関心がある場合は、アプリに互換性が .NET Standard こと、および[.Net Core コンパイラ](https://dotnet.microsoft.com/download)を使用してアプリをコンパイルすることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="214eb-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="214eb-135">Databricks を使用すると、既存のアクティブなクラスターに Apache Spark アプリ用の .NET を送信したり、ジョブを起動するたびに新しいクラスターを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="214eb-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="214eb-136">そのためには、Apache Spark アプリ用の .NET を送信する前に、 **Microsoft の Spark**をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="214eb-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="214eb-137">Microsoft Spark をデプロイする</span><span class="sxs-lookup"><span data-stu-id="214eb-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="214eb-138">この手順は、クラスターに対して1回のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="214eb-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="214eb-139">[Db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh)と install-worker.sh [](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
)をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="214eb-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="214eb-140">Db-init.sh を変更して、クラスターにダウンロードしてインストールするのリリースをポイントします。</span><span class="sxs-lookup"><span data-stu-id="214eb-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="214eb-141">[DATABRICKS CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="214eb-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="214eb-142">Databricks CLI の認証の詳細を[設定](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication)します。</span><span class="sxs-lookup"><span data-stu-id="214eb-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="214eb-143">次のコマンドを使用して、ファイルを Databricks クラスターにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="214eb-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="214eb-144">Databricks ワークスペースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="214eb-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="214eb-145">左側のメニューから **[クラスター]** を選択し、 **[クラスターの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="214eb-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="214eb-146">クラスターを適切に構成したら、 **Init スクリプト**を設定し、クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="214eb-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![スクリプトアクションの画像](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="214eb-148">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="214eb-148">Run your app</span></span> 

<span data-ttu-id="214eb-149">または`set JAR` `spark-submit`を使用して、ジョブを Databricks に送信できます。</span><span class="sxs-lookup"><span data-stu-id="214eb-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="214eb-150">JAR の設定を使用する</span><span class="sxs-lookup"><span data-stu-id="214eb-150">Use Set JAR</span></span>

<span data-ttu-id="214eb-151">[SET JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job)を使用すると、既存のアクティブなクラスターにジョブを送信できます。</span><span class="sxs-lookup"><span data-stu-id="214eb-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="214eb-152">1回限りのセットアップ</span><span class="sxs-lookup"><span data-stu-id="214eb-152">One-time setup</span></span>

1. <span data-ttu-id="214eb-153">Databricks クラスターに移動し、左側のメニューから **[ジョブ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="214eb-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="214eb-154">次に、 **[JAR の設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="214eb-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="214eb-155">適切な`microsoft-spark-<spark-version>-<spark-dotnet-version>.jar`ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="214eb-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="214eb-156">パラメーターを適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="214eb-156">Set the parameters appropriately.</span></span>

   ```
   Main Class: org.apache.spark.deploy.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. <span data-ttu-id="214eb-157">前のセクションで、 **Init スクリプト**を作成した既存のクラスターを指すように**クラスター**を構成します。</span><span class="sxs-lookup"><span data-stu-id="214eb-157">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="214eb-158">アプリを発行して実行する</span><span class="sxs-lookup"><span data-stu-id="214eb-158">Publish and run your app</span></span>

1. <span data-ttu-id="214eb-159">[DATABRICKS CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html)を使用して、Databricks クラスターにアプリケーションをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="214eb-159">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. <span data-ttu-id="214eb-160">この手順が必要なのは、アプリアセンブリ (たとえば、ユーザー定義関数を含む Dll) を各**Microsoft Spark. Worker**の作業ディレクトリに配置する必要がある場合のみです。</span><span class="sxs-lookup"><span data-stu-id="214eb-160">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   - <span data-ttu-id="214eb-161">アプリケーションアセンブリを Databricks クラスターにアップロードする</span><span class="sxs-lookup"><span data-stu-id="214eb-161">Upload your application assemblies to your Databricks cluster</span></span>
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - <span data-ttu-id="214eb-162">アプリの依存関係のパスをポイントして Databricks クラスターにアップロードするには、 [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh)の [アプリの依存関係] セクションのコメントを解除し、変更します。</span><span class="sxs-lookup"><span data-stu-id="214eb-162">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - <span data-ttu-id="214eb-163">クラスターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="214eb-163">Restart your cluster.</span></span>

3. <span data-ttu-id="214eb-164">Databricks ワークスペースで Databricks クラスターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="214eb-164">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="214eb-165">**[ジョブ]** でジョブを選択し、 **[今すぐ実行]** を選択してジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="214eb-165">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="214eb-166">Spark 送信の使用</span><span class="sxs-lookup"><span data-stu-id="214eb-166">Use spark-submit</span></span>

<span data-ttu-id="214eb-167">[Spark submit](https://spark.apache.org/docs/latest/submitting-applications.html)コマンドを使用すると、新しいクラスターにジョブを送信できます。</span><span class="sxs-lookup"><span data-stu-id="214eb-167">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="214eb-168">[ジョブを作成](https://docs.databricks.com/user-guide/jobs.html)し、 **[spark-submit の構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="214eb-168">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="214eb-169">次`spark-submit`のパラメーターを使用してを構成します。</span><span class="sxs-lookup"><span data-stu-id="214eb-169">Configure `spark-submit` with the following parameters:</span></span>

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. <span data-ttu-id="214eb-170">Databricks ワークスペースで Databricks クラスターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="214eb-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="214eb-171">**[ジョブ]** でジョブを選択し、 **[今すぐ実行]** を選択してジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="214eb-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="214eb-172">次の手順</span><span class="sxs-lookup"><span data-stu-id="214eb-172">Next steps</span></span>

<span data-ttu-id="214eb-173">このチュートリアルでは、Apache Spark アプリケーション用の .NET を Databricks にデプロイしました。</span><span class="sxs-lookup"><span data-stu-id="214eb-173">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="214eb-174">Databricks の詳細については、Azure Databricks のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="214eb-174">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="214eb-175">Azure Databricks のドキュメント</span><span class="sxs-lookup"><span data-stu-id="214eb-175">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
