---
title: Windows で .NET for Apache Spark アプリケーションをデバッグする
description: Windows で .NET for Apache Spark アプリケーションをデバッグする方法について学習します。
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 098c7519fe99ef04773c5e4b81685ca0f06f1272
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281527"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="57e99-103">.NET for Apache Spark アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="57e99-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="57e99-104">この使い方では、Windows 上で .NET for Apache Spark アプリケーションと Scala コードをデバッグするために実行する必要があるコマンドが提供されます。</span><span class="sxs-lookup"><span data-stu-id="57e99-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="57e99-105">アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="57e99-105">Debug your application</span></span>

<span data-ttu-id="57e99-106">新しいコマンド プロンプト ウィンドウを開いて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="57e99-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="57e99-107">このコマンドを実行すると、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57e99-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="57e99-108">このデバッグモードでは、`DotnetRunner` によって .NET アプリケーションが起動されることはありませんが、接続されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="57e99-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="57e99-109">このコマンド プロンプト ウィンドウは開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="57e99-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="57e99-110">これで、任意のデバッガーを使用して .NET アプリケーションを実行し、アプリケーションをデバッグできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="57e99-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="57e99-111">Scala コードをデバッグする</span><span class="sxs-lookup"><span data-stu-id="57e99-111">Debug Scala code</span></span>

<span data-ttu-id="57e99-112">`DotnetRunner` や `DotnetBackendHandler` などの Scala 側のコードをデバッグする必要がある場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="57e99-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="57e99-113">コマンドを実行した後、[Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) を使用して実行中のプロセスにデバッガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="57e99-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="57e99-114">次の手順</span><span class="sxs-lookup"><span data-stu-id="57e99-114">Next steps</span></span>

* [<span data-ttu-id="57e99-115">.NET for Apache Spark の概要</span><span class="sxs-lookup"><span data-stu-id="57e99-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="57e99-116">.NET for Apache Spark アプリケーションを Azure HDInsight にデプロイする</span><span class="sxs-lookup"><span data-stu-id="57e99-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="57e99-117">.NET for Apache Spark アプリケーションを Databricks にデプロイする</span><span class="sxs-lookup"><span data-stu-id="57e99-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="57e99-118">.NET for Apache Spark アプリケーションを Amazon EMR Spark にデプロイする</span><span class="sxs-lookup"><span data-stu-id="57e99-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
