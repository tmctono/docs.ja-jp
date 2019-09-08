---
title: .NET for Apache Spark アプリケーションを Databricks にデプロイする
description: .NET for Apache Spark アプリケーションを Databricks にデプロイする方法を説明します。
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 3c9169e2936742c82ba27327ac07f0aa1b4c645c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254043"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a><span data-ttu-id="21fd5-103">.NET for Apache Spark アプリケーションを Databricks にデプロイする</span><span class="sxs-lookup"><span data-stu-id="21fd5-103">Deploy a .NET for Apache Spark application to Databricks</span></span>

<span data-ttu-id="21fd5-104">このチュートリアルでは、.NET for Apache Spark アプリケーションを Databricks にデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Databricks.</span></span>

<span data-ttu-id="21fd5-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> - <span data-ttu-id="21fd5-106">Microsoft.Spark.Worker を準備する</span><span class="sxs-lookup"><span data-stu-id="21fd5-106">Prepare Microsoft.Spark.Worker</span></span>
> - <span data-ttu-id="21fd5-107">Spark .NET アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="21fd5-107">Publish your Spark .NET app</span></span>
> - <span data-ttu-id="21fd5-108">Databricks にアプリをデプロイする</span><span class="sxs-lookup"><span data-stu-id="21fd5-108">Deploy your app to Databricks</span></span>
> - <span data-ttu-id="21fd5-109">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="21fd5-109">Run your app</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21fd5-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="21fd5-110">Prerequisites</span></span>

<span data-ttu-id="21fd5-111">開始する前に、以下を行います。</span><span class="sxs-lookup"><span data-stu-id="21fd5-111">Before you start, do the following:</span></span>

- <span data-ttu-id="21fd5-112">[Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-112">Download the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>
- <span data-ttu-id="21fd5-113">[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) をお使いのローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="21fd5-114">これは、後で .NET for Apache Spark の依存ファイルを Spark クラスターのワーカー ノードにコピーするために使用するヘルパー スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="21fd5-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="21fd5-115">ワーカーの依存関係を準備する</span><span class="sxs-lookup"><span data-stu-id="21fd5-115">Prepare worker dependencies</span></span>

<span data-ttu-id="21fd5-116">**Microsoft.Spark.Worker** は、Spark クラスターの個々のワーカー ノードに存在するバックエンド コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="21fd5-116">**Microsoft.Spark.Worker** is a back-end component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="21fd5-117">C# UDF (ユーザー定義関数) を実行する場合、.NET CLR を起動して UDF を実行する方法を Spark が理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="21fd5-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="21fd5-118">**Microsoft.Spark.Worker** により、この機能を有効にするクラスのコレクションが Spark に提供されます。</span><span class="sxs-lookup"><span data-stu-id="21fd5-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="21fd5-119">お使いのクラスターにデプロイされる [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp リリースを選択します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="21fd5-120">たとえば、`netcoreapp2.1` を使用する `.NET for Apache Spark v0.1.0` が必要な場合は、[Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="21fd5-121">クラスターからアクセスできる分散ファイル システム (DBFS など) に、`Microsoft.Spark.Worker.<release>.tar.gz` と [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (for example, DBFS) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="21fd5-122">.NET for Apache Spark アプリを準備する</span><span class="sxs-lookup"><span data-stu-id="21fd5-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="21fd5-123">[入門](get-started.md)チュートリアルに従ってアプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="21fd5-124">Spark .NET アプリを自己完結型として発行します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="21fd5-125">Linux では、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="21fd5-125">You can run the following command on Linux.</span></span>

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="21fd5-126">発行されたファイル用に `<your app>.zip` を生成します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="21fd5-127">Linux では、`zip` を使用して次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="21fd5-127">You can run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="21fd5-128">クラスターからアクセスできる分散ファイル システム (DBFS など) に、次をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-128">Upload the following to a distributed file system (for example, DBFS) that your cluster has access to:</span></span>

   - <span data-ttu-id="21fd5-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`:この jar は、[Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet パッケージの一部として含まれており、アプリのビルド出力ディレクトリに併置されています。</span><span class="sxs-lookup"><span data-stu-id="21fd5-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   - `<your app>.zip`
   - <span data-ttu-id="21fd5-130">各 Executor の作業ディレクトリ内に配置されるファイル (依存関係ファイルや、すべてのワーカーからアクセスできる共通データなど) またはアセンブリ (アプリが依存しているユーザー定義関数またはライブラリを含む DLL など)。</span><span class="sxs-lookup"><span data-stu-id="21fd5-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-databricks"></a><span data-ttu-id="21fd5-131">Databricks のデプロイする</span><span class="sxs-lookup"><span data-stu-id="21fd5-131">Deploy to Databricks</span></span>

<span data-ttu-id="21fd5-132">[Databricks](https://databricks.com) は、Apache Spark を使用してクラウドベースのビッグ データ処理を提供するプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="21fd5-132">[Databricks](https://databricks.com) is a platform that provides cloud-based big data processing using Apache Spark.</span></span>

> [!Note] 
> <span data-ttu-id="21fd5-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) と [AWS Databricks](https://databricks.com/aws) は Linux ベースです。</span><span class="sxs-lookup"><span data-stu-id="21fd5-133">[Azure Databricks](https://azure.microsoft.com/services/databricks/) and [AWS Databricks](https://databricks.com/aws) are Linux-based.</span></span> <span data-ttu-id="21fd5-134">そのため、Databricks へのアプリのデプロイに関心がある場合は、アプリが .NET Standard と互換性があることと、アプリのコンパイルに [.NET Core コンパイラ](https://dotnet.microsoft.com/download)を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="21fd5-134">Therefore, if you are interested in deploying your app to Databricks, make sure your app is .NET Standard compatible and that you use [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

<span data-ttu-id="21fd5-135">Databricks を使用すると、.NET for Apache Spark アプリを既存のアクティブなクラスターに送信したり、ジョブを起動するたびに新しいクラスターを作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="21fd5-135">Databricks allows you to submit .NET for Apache Spark apps to an existing active cluster or create a new cluster every time you launch a job.</span></span> <span data-ttu-id="21fd5-136">これには、.NET for Apache Spark アプリを送信する前に、**Microsoft.Spark.Worker** をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="21fd5-136">This requires the **Microsoft.Spark.Worker** to be installed before you submit a .NET for Apache Spark app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="21fd5-137">Microsoft.Spark.Worker をデプロイする</span><span class="sxs-lookup"><span data-stu-id="21fd5-137">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="21fd5-138">この手順は、クラスターに対して 1 回のみ必要です。</span><span class="sxs-lookup"><span data-stu-id="21fd5-138">This step is only required once for a cluster.</span></span>

1. <span data-ttu-id="21fd5-139">[db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) と [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) をローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-139">Download [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) onto your local machine.</span></span>

2. <span data-ttu-id="21fd5-140">クラスターにダウンロードしてインストールする **Microsoft.Spark.Worker** リリースをポイントするように、**db-init.sh** を変更します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-140">Modify **db-init.sh** to point to the **Microsoft.Spark.Worker** release you want to download and install on your cluster.</span></span>

3. <span data-ttu-id="21fd5-141">[Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-141">Install the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).</span></span>

4. <span data-ttu-id="21fd5-142">Databricks CLI の[認証の詳細を設定](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication)します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-142">[Setup authentication](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) details for the Databricks CLI.</span></span>

5. <span data-ttu-id="21fd5-143">次のコマンドを使用して、ファイルを Databricks クラスターにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-143">Upload the files to your Databricks cluster using the following command:</span></span>

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. <span data-ttu-id="21fd5-144">Databricks ワークスペースに移動します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-144">Go to your Databricks workspace.</span></span> <span data-ttu-id="21fd5-145">左側のメニューから **[クラスター]** を選択し、 **[クラスターの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-145">Select **Clusters** from the left-side menu, and then select **Create Cluster**.</span></span>

7. <span data-ttu-id="21fd5-146">クラスターを適切に構成したら、**Init スクリプト**を設定し、クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-146">After configuring the cluster appropriately, set the **Init Script** and create the cluster.</span></span>

   ![スクリプト アクションの画像](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a><span data-ttu-id="21fd5-148">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="21fd5-148">Run your app</span></span> 

<span data-ttu-id="21fd5-149">`set JAR` または `spark-submit` を使用して、ジョブを Databricks に送信できます。</span><span class="sxs-lookup"><span data-stu-id="21fd5-149">You can use `set JAR` or `spark-submit` to submit your job to Databricks.</span></span>

### <a name="use-set-jar"></a><span data-ttu-id="21fd5-150">Set JAR を使用する</span><span class="sxs-lookup"><span data-stu-id="21fd5-150">Use Set JAR</span></span>

<span data-ttu-id="21fd5-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) を使用すると、既存のアクティブなクラスターにジョブを送信できます。</span><span class="sxs-lookup"><span data-stu-id="21fd5-151">[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) allows you to submit a job to an existing active cluster.</span></span>

#### <a name="one-time-setup"></a><span data-ttu-id="21fd5-152">1 回限りのセットアップ</span><span class="sxs-lookup"><span data-stu-id="21fd5-152">One-time setup</span></span>

1. <span data-ttu-id="21fd5-153">Databricks クラスターに移動し、左側のメニューから **[ジョブ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-153">Go to your Databricks cluster and select **Jobs** from the left-side menu.</span></span> <span data-ttu-id="21fd5-154">次に、 **[Set JAR]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-154">Then select **Set JAR**.</span></span>

2. <span data-ttu-id="21fd5-155">適切な `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-155">Upload the appropriate `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` file.</span></span>

3. <span data-ttu-id="21fd5-156">パラメーターを適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-156">Set the parameters appropriately.</span></span>

   ```
   Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
   Arguments /dbfs/apps/<your-app-name>.zip <your-app-main-class>
   ```
 
4. <span data-ttu-id="21fd5-157">前のセクションで、**Init スクリプト**を作成した既存のクラスターを指すように**クラスター**を構成します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-157">Configure the **Cluster** to point to the existing cluster you created the **Init Script** for in the previous section.</span></span>

#### <a name="publish-and-run-your-app"></a><span data-ttu-id="21fd5-158">アプリを発行して実行する</span><span class="sxs-lookup"><span data-stu-id="21fd5-158">Publish and run your app</span></span>

1. <span data-ttu-id="21fd5-159">[Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) を使用して、Databricks クラスターにアプリケーションをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-159">Use the [Databricks CLI](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) to upload your application to your Databricks cluster.</span></span>

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
      ```

2. <span data-ttu-id="21fd5-160">この手順は、アプリ アセンブリ (たとえば、ユーザー定義関数とその依存関係を含む DLL) を各 **Microsoft Spark.Worker** の作業ディレクトリに配置する必要がある場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="21fd5-160">This step is only required if your app assemblies (for example, DLLs that contain user-defined functions along with their dependencies) need to be placed in the working directory of each **Microsoft.Spark.Worker**.</span></span>

   - <span data-ttu-id="21fd5-161">アプリケーション アセンブリを Databricks クラスターにアップロードする</span><span class="sxs-lookup"><span data-stu-id="21fd5-161">Upload your application assemblies to your Databricks cluster</span></span>
      
      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   - <span data-ttu-id="21fd5-162">[db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) 内のアプリの依存関係セクションをコメント解除して、ご自分のアプリの依存関係パスをポイントするように変更し、Databricks クラスターにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="21fd5-162">Uncomment and modify the app dependencies section in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) to point to your app dependencies path and upload to your Databricks cluster.</span></span>
   
      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```
   
   - <span data-ttu-id="21fd5-163">クラスターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-163">Restart your cluster.</span></span>

3. <span data-ttu-id="21fd5-164">Databricks ワークスペース内の Databricks クラスターに移動します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-164">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="21fd5-165">**[ジョブ]** の下でジョブを選択し、 **[今すぐ実行]** を選択してジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-165">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="21fd5-166">spark-submit を使用する</span><span class="sxs-lookup"><span data-stu-id="21fd5-166">Use spark-submit</span></span>

<span data-ttu-id="21fd5-167">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) コマンドを使用すると、新しいクラスターにジョブを送信できます。</span><span class="sxs-lookup"><span data-stu-id="21fd5-167">The [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command allows you to submit a job to a new cluster.</span></span>

1. <span data-ttu-id="21fd5-168">[ジョブを作成](https://docs.databricks.com/user-guide/jobs.html)し、 **[Configure spark-submit]\(spark-submit の構成\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-168">[Create a Job](https://docs.databricks.com/user-guide/jobs.html) and select **Configure spark-submit**.</span></span>

2. <span data-ttu-id="21fd5-169">次のパラメーターを指定して `spark-submit` を構成します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-169">Configure `spark-submit` with the following parameters:</span></span>

      ```bash
      ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
      ```

3. <span data-ttu-id="21fd5-170">Databricks ワークスペース内の Databricks クラスターに移動します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-170">Go to your Databricks cluster in your Databricks workspace.</span></span> <span data-ttu-id="21fd5-171">**[ジョブ]** の下でジョブを選択し、 **[今すぐ実行]** を選択してジョブを実行します。</span><span class="sxs-lookup"><span data-stu-id="21fd5-171">Under **Jobs**, select your job and then select **Run Now** to run your job.</span></span>

## <a name="next-steps"></a><span data-ttu-id="21fd5-172">次の手順</span><span class="sxs-lookup"><span data-stu-id="21fd5-172">Next steps</span></span>

<span data-ttu-id="21fd5-173">このチュートリアルでは、.NET for Apache Spark アプリケーションを Databricks にデプロイしました。</span><span class="sxs-lookup"><span data-stu-id="21fd5-173">In this tutorial, you deployed your .NET for Apache Spark application to Databricks.</span></span> <span data-ttu-id="21fd5-174">Databricks の詳細については、Azure Databricks のドキュメントに進んでください。</span><span class="sxs-lookup"><span data-stu-id="21fd5-174">To learn more about Databricks, continue to the Azure Databricks Documentation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="21fd5-175">Azure Databricks のドキュメント</span><span class="sxs-lookup"><span data-stu-id="21fd5-175">Azure Databricks Documentation</span></span>](https://docs.microsoft.com/azure/azure-databricks/)
