---
title: .NET for Apache Spark ジョブを Azure HDInsight に送信する
description: spark-submit と Apache Livy を使用して、.NET for Apache Spark ジョブを Azure HDInsight に送信する方法について説明します。
ms.date: 11/19/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: d558234a53cc22d65540a380ac7f5b3ac03ba0ae
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868019"
---
# <a name="submit-a-net-for-apache-spark-job-to-azure-hdinsight"></a><span data-ttu-id="0db31-103">.NET for Apache Spark ジョブを Azure HDInsight に送信する</span><span class="sxs-lookup"><span data-stu-id="0db31-103">Submit a .NET for Apache Spark job to Azure HDInsight</span></span>

<span data-ttu-id="0db31-104">.NET for Apache Spark ジョブを HDInsight に展開するには、`spark-submit` と Apache Livy の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="0db31-104">There are two ways to deploy your .NET for Apache Spark job to HDInsight: `spark-submit` and Apache Livy.</span></span>

## <a name="deploy-using-spark-submit"></a><span data-ttu-id="0db31-105">spark-submit を使用して展開する</span><span class="sxs-lookup"><span data-stu-id="0db31-105">Deploy using spark-submit</span></span>

<span data-ttu-id="0db31-106">[spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) コマンドを使用して、.NET for Apache Spark ジョブを Azure HDInsight に送信できます。</span><span class="sxs-lookup"><span data-stu-id="0db31-106">You can use the [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) command to submit .NET for Apache Spark jobs to Azure HDInsight.</span></span>
 
1. <span data-ttu-id="0db31-107">Azure portal の HDInsight Spark クラスターに移動し、 **[SSH およびクラスターのログイン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0db31-107">Navigate to your HDInsight Spark cluster in Azure portal, and then select **SSH + Cluster login**.</span></span>

2. <span data-ttu-id="0db31-108">ssh ログイン情報をコピーし、ログインをターミナルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0db31-108">Copy the ssh login information and paste the login into a terminal.</span></span> <span data-ttu-id="0db31-109">クラスターの作成時に設定したパスワードを使用してクラスターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="0db31-109">Sign in to your cluster using the password you set during cluster creation.</span></span> <span data-ttu-id="0db31-110">Ubuntu および Spark のウェルカム メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0db31-110">You should see messages welcoming you to Ubuntu and Spark.</span></span>

3. <span data-ttu-id="0db31-111">**spark-submit** コマンドを使用して、HDInsight クラスターでアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="0db31-111">Use the **spark-submit** command to run your app on your HDInsight cluster.</span></span> <span data-ttu-id="0db31-112">このスクリプト例の **mycontainer** と **mystorageaccount** を、実際の BLOB コンテナーの名前とストレージ アカウントに置き換えることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="0db31-112">Remember to replace **mycontainer** and **mystorageaccount** in the example script with the actual names of your blob container and storage account.</span></span> <span data-ttu-id="0db31-113">また、`microsoft-spark-2.3.x-0.6.0.jar` は、展開に使用している適切な jar ファイルに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="0db31-113">Also, be sure to replace `microsoft-spark-2.3.x-0.6.0.jar` with the appropriate jar file you're using for deployment.</span></span> <span data-ttu-id="0db31-114">`2.3.x` は Apache Spark のバージョンを表し、`0.6.0` は [.NET for Apache Spark worker](https://github.com/dotnet/spark/releases) のバージョンを表します。</span><span class="sxs-lookup"><span data-stu-id="0db31-114">`2.3.x` represents the version of Apache Spark, and `0.6.0` represents the version of the [.NET for Apache Spark worker](https://github.com/dotnet/spark/releases).</span></span>

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

## <a name="deploy-using-apache-livy"></a><span data-ttu-id="0db31-115">Apache Livy を使用して展開する</span><span class="sxs-lookup"><span data-stu-id="0db31-115">Deploy using Apache Livy</span></span>

<span data-ttu-id="0db31-116">[Apache Livy](https://livy.incubator.apache.org/) (Apache Spark REST API) を使用して、.NET for Apache Spark ジョブを Azure HDInsight Spark クラスターに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="0db31-116">You can use [Apache Livy](https://livy.incubator.apache.org/), the Apache Spark REST API, to submit .NET for Apache Spark jobs to an Azure HDInsight Spark cluster.</span></span> <span data-ttu-id="0db31-117">詳細については、[Apache Livy を使用したリモート ジョブ](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0db31-117">For more information, see [Remote jobs with Apache Livy](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-livy-rest-interface).</span></span>

<span data-ttu-id="0db31-118">Linux では、`curl` を使用して次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0db31-118">You can run the following command on Linux using `curl`:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="0db31-119">次の手順</span><span class="sxs-lookup"><span data-stu-id="0db31-119">Next steps</span></span>

* [<span data-ttu-id="0db31-120">.NET for Apache Spark の概要</span><span class="sxs-lookup"><span data-stu-id="0db31-120">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="0db31-121">.NET for Apache Spark アプリケーションを Azure HDInsight にデプロイする</span><span class="sxs-lookup"><span data-stu-id="0db31-121">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="0db31-122">HDInsight のドキュメント</span><span class="sxs-lookup"><span data-stu-id="0db31-122">HDInsight Documentation</span></span>](https://docs.microsoft.com/azure/hdinsight/)
