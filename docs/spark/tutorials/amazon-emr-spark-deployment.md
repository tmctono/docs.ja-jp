---
title: .NET for Apache Spark アプリケーションを Amazon EMR Spark にデプロイする
description: .NET for Apache Spark アプリケーションを Amazon EMR Spark にデプロイする方法を説明します。
ms.date: 06/25/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6cf26044693c5d923d11e1bbc72232e7009fe73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618260"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a><span data-ttu-id="f737f-103">.NET for Apache Spark アプリケーションを Amazon EMR Spark にデプロイする</span><span class="sxs-lookup"><span data-stu-id="f737f-103">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>

<span data-ttu-id="f737f-104">このチュートリアルでは、.NET for Apache Spark アプリケーションを Amazon EMR Spark にデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f737f-104">This tutorial teaches how to deploy a .NET for Apache Spark application to Amazon EMR Spark.</span></span>

<span data-ttu-id="f737f-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f737f-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="f737f-106">Microsoft.Spark.Worker を準備する</span><span class="sxs-lookup"><span data-stu-id="f737f-106">Prepare Microsoft.Spark.Worker</span></span>
> * <span data-ttu-id="f737f-107">Spark .NET アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="f737f-107">Publish your Spark .NET app</span></span>
> * <span data-ttu-id="f737f-108">アプリを Amazon EMR Spark にデプロイする</span><span class="sxs-lookup"><span data-stu-id="f737f-108">Deploy your app to Amazon EMR Spark</span></span>
> * <span data-ttu-id="f737f-109">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="f737f-109">Run your app</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a><span data-ttu-id="f737f-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f737f-110">Prerequisites</span></span>

<span data-ttu-id="f737f-111">開始する前に、以下を行います。</span><span class="sxs-lookup"><span data-stu-id="f737f-111">Before you start, do the following:</span></span>

* <span data-ttu-id="f737f-112">[AWS CLI](https://aws.amazon.com/cli/) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f737f-112">Download the [AWS CLI](https://aws.amazon.com/cli/).</span></span>
* <span data-ttu-id="f737f-113">[install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) をお使いのローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f737f-113">Download [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to your local machine.</span></span> <span data-ttu-id="f737f-114">これは、後で .NET for Apache Spark の依存ファイルを Spark クラスターのワーカー ノードにコピーするために使用するヘルパー スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="f737f-114">This is a helper script that you use later to copy .NET for Apache Spark dependent files into your Spark cluster's worker nodes.</span></span>

## <a name="prepare-worker-dependencies"></a><span data-ttu-id="f737f-115">ワーカーの依存関係を準備する</span><span class="sxs-lookup"><span data-stu-id="f737f-115">Prepare worker dependencies</span></span>

<span data-ttu-id="f737f-116">**Microsoft.Spark.Worker** は、Spark クラスターの個々のワーカー ノードに存在するバックエンド コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f737f-116">**Microsoft.Spark.Worker** is a backend component that lives on the individual worker nodes of your Spark cluster.</span></span> <span data-ttu-id="f737f-117">C# UDF (ユーザー定義関数) を実行する場合、.NET CLR を起動して UDF を実行する方法を Spark が理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f737f-117">When you want to execute a C# UDF (user-defined function), Spark needs to understand how to launch the .NET CLR to execute the UDF.</span></span> <span data-ttu-id="f737f-118">**Microsoft.Spark.Worker** により、この機能を有効にするクラスのコレクションが Spark に提供されます。</span><span class="sxs-lookup"><span data-stu-id="f737f-118">**Microsoft.Spark.Worker** provides a collection of classes to Spark that enable this functionality.</span></span>

1. <span data-ttu-id="f737f-119">お使いのクラスターにデプロイされる [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp リリースを選択します。</span><span class="sxs-lookup"><span data-stu-id="f737f-119">Select a [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp release to be deployed on your cluster.</span></span>

   <span data-ttu-id="f737f-120">たとえば、`netcoreapp2.1` を使用する `.NET for Apache Spark v0.1.0` が必要な場合は、[Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f737f-120">For example, if you want `.NET for Apache Spark v0.1.0` using `netcoreapp2.1`, you'd download [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz).</span></span>

2. <span data-ttu-id="f737f-121">クラスターからアクセスできる分散ファイル システム (S3 など) に、`Microsoft.Spark.Worker.<release>.tar.gz` と [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f737f-121">Upload `Microsoft.Spark.Worker.<release>.tar.gz` and [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) to a distributed file system (e.g., S3) that your cluster has access to.</span></span>

## <a name="prepare-your-net-for-apache-spark-app"></a><span data-ttu-id="f737f-122">.NET for Apache Spark アプリを準備する</span><span class="sxs-lookup"><span data-stu-id="f737f-122">Prepare your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="f737f-123">[入門](get-started.md)チュートリアルに従ってアプリをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f737f-123">Follow the [Get Started](get-started.md) tutorial to build your app.</span></span>

2. <span data-ttu-id="f737f-124">Spark .NET アプリを自己完結型として発行します。</span><span class="sxs-lookup"><span data-stu-id="f737f-124">Publish your Spark .NET app as self-contained.</span></span>

   <span data-ttu-id="f737f-125">Linux で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f737f-125">Run the following command on Linux.</span></span>

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. <span data-ttu-id="f737f-126">発行されたファイル用に `<your app>.zip` を生成します。</span><span class="sxs-lookup"><span data-stu-id="f737f-126">Produce `<your app>.zip` for the published files.</span></span>

   <span data-ttu-id="f737f-127">`zip` を使用して Linux で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f737f-127">Run the following command on Linux using `zip`.</span></span>

   ```bash
   zip -r <your app>.zip .
   ```

4. <span data-ttu-id="f737f-128">クラスターからアクセスできる分散ファイル システム (S3 など) に、次の項目をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f737f-128">Upload the following items to a distributed file system (e.g., S3) that your cluster has access to:</span></span>

   * <span data-ttu-id="f737f-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`:この jar は、[Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet パッケージの一部として含まれており、アプリのビルド出力ディレクトリに併置されています。</span><span class="sxs-lookup"><span data-stu-id="f737f-129">`microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: This jar is included as part of the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package and is colocated in your app's build output directory.</span></span>
   * `<your app>.zip`
   * <span data-ttu-id="f737f-130">各 Executor の作業ディレクトリ内に配置されるファイル (依存関係ファイルや、すべてのワーカーからアクセスできる共通データなど) またはアセンブリ (アプリが依存しているユーザー定義関数またはライブラリを含む DLL など)。</span><span class="sxs-lookup"><span data-stu-id="f737f-130">Files (like dependency files or common data accessible to every worker) or assemblies (like DLLs that contain your user-defined functions or libraries that your app depends on) to be placed in the working directory of each executor.</span></span>

## <a name="deploy-to-amazon-emr-spark"></a><span data-ttu-id="f737f-131">Amazon EMR Spark にデプロイする</span><span class="sxs-lookup"><span data-stu-id="f737f-131">Deploy to Amazon EMR Spark</span></span>

<span data-ttu-id="f737f-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) は、AWS でのビッグ データ フレームワークの実行を簡略化する、マネージド クラスター プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="f737f-132">[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) is a managed cluster platform that simplifies running big data frameworks on AWS.</span></span>

> [!NOTE]
> <span data-ttu-id="f737f-133">Amazon EMR Spark は Linux ベースです。</span><span class="sxs-lookup"><span data-stu-id="f737f-133">Amazon EMR Spark is Linux-based.</span></span> <span data-ttu-id="f737f-134">そのため、Amazon EMR Spark へのアプリのデプロイに関心がある場合は、アプリが .NET Standard と互換性があることと、アプリのコンパイルに [.NET Core コンパイラ](https://dotnet.microsoft.com/download)を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f737f-134">Therefore, if you are interested in deploying your app to Amazon EMR Spark, make sure your app is .NET Standard compatible and that you use the [.NET Core compiler](https://dotnet.microsoft.com/download) to compile your app.</span></span>

### <a name="deploy-microsoftsparkworker"></a><span data-ttu-id="f737f-135">Microsoft.Spark.Worker をデプロイする</span><span class="sxs-lookup"><span data-stu-id="f737f-135">Deploy Microsoft.Spark.Worker</span></span>

<span data-ttu-id="f737f-136">この手順は、クラスターの作成時にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="f737f-136">This step is only required at cluster creation.</span></span>

<span data-ttu-id="f737f-137">[ブートストラップ アクション](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)を使用してクラスターの作成中に、`install-worker.sh` を実行します。</span><span class="sxs-lookup"><span data-stu-id="f737f-137">Run `install-worker.sh` during cluster creation using [Bootstrap Actions](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html).</span></span>

<span data-ttu-id="f737f-138">AWS CLI を使用して Linux で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f737f-138">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a><span data-ttu-id="f737f-139">アプリの実行</span><span class="sxs-lookup"><span data-stu-id="f737f-139">Run your app</span></span>

<span data-ttu-id="f737f-140">Amazon EMR Spark でアプリを実行するには、spark submit ステップと Amazon EMR ステップの 2 通りの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f737f-140">There are two ways to run your app in Amazon EMR Spark: spark-submit and Amazon EMR Steps.</span></span>

### <a name="use-spark-submit"></a><span data-ttu-id="f737f-141">spark-submit を使用する</span><span class="sxs-lookup"><span data-stu-id="f737f-141">Use spark-submit</span></span>

<span data-ttu-id="f737f-142">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) コマンドを使用して、.NET for Apache Spark ジョブを Amazon EMR Spark に送信できます。</span><span class="sxs-lookup"><span data-stu-id="f737f-142">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Amazon EMR Spark.</span></span>

1. <span data-ttu-id="f737f-143">クラスター内のいずれかのノードに `ssh` で接続します。</span><span class="sxs-lookup"><span data-stu-id="f737f-143">`ssh` into one of the nodes in the cluster.</span></span>

2. <span data-ttu-id="f737f-144">`spark-submit` を実行します。</span><span class="sxs-lookup"><span data-stu-id="f737f-144">Run `spark-submit`.</span></span>

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a><span data-ttu-id="f737f-145">Amazon EMR ステップを使用する</span><span class="sxs-lookup"><span data-stu-id="f737f-145">Use Amazon EMR Steps</span></span>

<span data-ttu-id="f737f-146">[Amazon EMR ステップ](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html)を使用して、EMR クラスターにインストールされている Spark フレームワークにジョブを送信できます。</span><span class="sxs-lookup"><span data-stu-id="f737f-146">[Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) can be used to submit jobs to the Spark framework installed on the EMR cluster.</span></span>

<span data-ttu-id="f737f-147">AWS CLI を使用して Linux で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f737f-147">Run the following command on Linux using AWS CLI.</span></span>

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a><span data-ttu-id="f737f-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="f737f-148">Next steps</span></span>

<span data-ttu-id="f737f-149">このチュートリアルでは、.NET for Apache Spark アプリケーションを Amazon EMR Spark にデプロイしました。</span><span class="sxs-lookup"><span data-stu-id="f737f-149">In this tutorial, you deployed your .NET for Apache Spark application to Amazon EMR Spark.</span></span> <span data-ttu-id="f737f-150">.NET for Apache Spark のプロジェクト例については、GitHub に進んでください。</span><span class="sxs-lookup"><span data-stu-id="f737f-150">For .NET for Apache Spark example projects, continue to GitHub.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f737f-151">.NET for Apache Spark サンプル</span><span class="sxs-lookup"><span data-stu-id="f737f-151">.NET for Apache Spark samples</span></span>](https://github.com/dotnet/spark/tree/master/examples)
