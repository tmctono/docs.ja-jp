---
title: Windows で .NET for Apache Spark アプリケーションをビルドする
description: Windows で .NET for Apache Spark アプリケーションをビルドする方法について学習します。
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: e6dec09f7d3e8d478cdcccf9df1c3e72d5f884eb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76928062"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="e111e-103">Windows で .NET for Apache Spark アプリケーションをビルドする方法を学習する</span><span class="sxs-lookup"><span data-stu-id="e111e-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="e111e-104">この記事では、Windows で .NET for Apache Spark アプリケーションをビルドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e111e-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e111e-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e111e-105">Prerequisites</span></span>

<span data-ttu-id="e111e-106">以下の必須コンポーネントがすべて揃っている場合は、「[ビルド](#build)」の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="e111e-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="e111e-107">**[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** をダウンロードしてインストールする - SDK をインストールすると、`dotnet` ツールチェーンがパスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="e111e-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="e111e-108">.NET Core 2.1、2.2、および 3.1 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e111e-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="e111e-109">**[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (バージョン 16.3 以降) をインストールする。</span><span class="sxs-lookup"><span data-stu-id="e111e-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="e111e-110">コミュニティ バージョンは完全に無料です。</span><span class="sxs-lookup"><span data-stu-id="e111e-110">The Community version is completely free.</span></span> <span data-ttu-id="e111e-111">インストールを構成するときは、最小でも次のコンポーネントを含めてください。</span><span class="sxs-lookup"><span data-stu-id="e111e-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="e111e-112">.NET デスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="e111e-112">.NET desktop development</span></span>
       * <span data-ttu-id="e111e-113">すべての必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e111e-113">All Required Components</span></span>
         * <span data-ttu-id="e111e-114">.NET Framework 4.6.1 開発ツール</span><span class="sxs-lookup"><span data-stu-id="e111e-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="e111e-115">.NET Core クロスプラットフォームの開発</span><span class="sxs-lookup"><span data-stu-id="e111e-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="e111e-116">すべての必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e111e-116">All Required Components</span></span>
  3. <span data-ttu-id="e111e-117">**[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** をインストールする。</span><span class="sxs-lookup"><span data-stu-id="e111e-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span> 
     - <span data-ttu-id="e111e-118">お使いのオペレーティング システムに適したバージョンを選択します (たとえば、Win x64 コンピューターの場合は jdk-8u201-windows-x64.exe)。</span><span class="sxs-lookup"><span data-stu-id="e111e-118">Select the appropriate version for your operating system e.g., jdk-8u201-windows-x64.exe for Win x64 machine.</span></span>
     - <span data-ttu-id="e111e-119">インストーラーを使ってインストールし、コマンド ラインから `java` を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e111e-119">Install using the installer and verify you are able to run `java` from your command-line.</span></span>
  4. <span data-ttu-id="e111e-120">**[Apache Maven 3.6.0 以降](https://maven.apache.org/download.cgi)** をインストールする。</span><span class="sxs-lookup"><span data-stu-id="e111e-120">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="e111e-121">[Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e111e-121">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
     - <span data-ttu-id="e111e-122">ローカル ディレクトリに抽出します (`C:\bin\apache-maven-3.6.0\` など)。</span><span class="sxs-lookup"><span data-stu-id="e111e-122">Extract to a local directory e.g., `C:\bin\apache-maven-3.6.0\`.</span></span>
     - <span data-ttu-id="e111e-123">[PATH 環境変数](https://www.java.com/en/download/help/path.xml)に Apache Maven を追加します (`C:\bin\apache-maven-3.6.0\bin` など)。</span><span class="sxs-lookup"><span data-stu-id="e111e-123">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml) e.g., `C:\bin\apache-maven-3.6.0\bin`.</span></span>
     - <span data-ttu-id="e111e-124">コマンド ラインから `mvn` を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e111e-124">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="e111e-125">**[Apache Spark 2.3 以降](https://spark.apache.org/downloads.html)** をインストールする。</span><span class="sxs-lookup"><span data-stu-id="e111e-125">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="e111e-126">[Apache Spark 2.3 以降](https://spark.apache.org/downloads.html)をダウンロードし、[7-zip](https://www.7-zip.org/) を使用してローカル フォルダーに抽出します (`C:\bin\spark-2.3.2-bin-hadoop2.7\` など)。</span><span class="sxs-lookup"><span data-stu-id="e111e-126">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (e.g., `C:\bin\spark-2.3.2-bin-hadoop2.7\`) using [7-zip](https://www.7-zip.org/).</span></span> <span data-ttu-id="e111e-127">(サポートされている Spark のバージョンは 2.3.\*、2.4.0、2.4.1、2.4.3、および 2.4.4 です)</span><span class="sxs-lookup"><span data-stu-id="e111e-127">(The supported spark versions are 2.3.\*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>
     - <span data-ttu-id="e111e-128">[新しい環境変数](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` を追加します (`C:\bin\spark-2.3.2-bin-hadoop2.7\` など)。</span><span class="sxs-lookup"><span data-stu-id="e111e-128">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` e.g., `C:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\       
       ```

     - <span data-ttu-id="e111e-129">[PATH 環境変数](https://www.java.com/en/download/help/path.xml)に Apache Spark を追加します (`C:\bin\spark-2.3.2-bin-hadoop2.7\bin` など)。</span><span class="sxs-lookup"><span data-stu-id="e111e-129">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml) e.g., `C:\bin\spark-2.3.2-bin-hadoop2.7\bin`.</span></span>

       ```powershell       
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```
     
     - <span data-ttu-id="e111e-130">コマンド ラインから `spark-shell` を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e111e-130">Verify you are able to run `spark-shell` from your command-line.</span></span>        
        <span data-ttu-id="e111e-131">コンソール出力の例:</span><span class="sxs-lookup"><span data-stu-id="e111e-131">Sample console output:</span></span>

        ```
        Welcome to
              ____              __
             / __/__  ___ _____/ /__
            _\ \/ _ \/ _ `/ __/  '_/
           /___/ .__/\_,_/_/ /_/\_\   version 2.3.2
              /_/

        Using Scala version 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
        Type in expressions to have them evaluated.
        Type :help for more information.

        scala> sc
        res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
        ```

        </details>

  6. <span data-ttu-id="e111e-132">**[WinUtils](https://github.com/steveloughran/winutils)** をインストールする。</span><span class="sxs-lookup"><span data-stu-id="e111e-132">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="e111e-133">[WinUtils リポジトリ](https://github.com/steveloughran/winutils)から `winutils.exe` バイナリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e111e-133">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="e111e-134">Spark ディストリビューションがコンパイルされた Hadoop のバージョンを選択する必要があります (たとえば、Spark 2.3.2 の場合は hadoop-2.7.1 を使います)。</span><span class="sxs-lookup"><span data-stu-id="e111e-134">You should select the version of Hadoop the Spark distribution was compiled with, e.g. use hadoop-2.7.1 for Spark 2.3.2.</span></span>
     - <span data-ttu-id="e111e-135">`winutils.exe` バイナリを任意のディレクトリに保存します (`C:\hadoop\bin` など)。</span><span class="sxs-lookup"><span data-stu-id="e111e-135">Save `winutils.exe` binary to a directory of your choice e.g., `C:\hadoop\bin`.</span></span>
     - <span data-ttu-id="e111e-136">winutils.exe があるディレクトリを示すように `HADOOP_HOME` を設定します (bin は含めない)。</span><span class="sxs-lookup"><span data-stu-id="e111e-136">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="e111e-137">たとえば、コマンド ラインで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e111e-137">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="e111e-138">`%HADOOP_HOME%\bin` が含まれるように PATH 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e111e-138">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="e111e-139">たとえば、コマンド ラインで次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e111e-139">For instance, using command-line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="e111e-140">次のセクションに進む前に、コマンド ラインから `dotnet`、`java`、`mvn`、`spark-shell` を実行できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e111e-140">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command-line before you move to the next section.</span></span> <span data-ttu-id="e111e-141">もっと良い方法があると思いますか。</span><span class="sxs-lookup"><span data-stu-id="e111e-141">Feel there is a better way?</span></span> <span data-ttu-id="e111e-142">[イシューを作成](https://github.com/dotnet/spark/issues)して、お気軽にご投稿ください。</span><span class="sxs-lookup"><span data-stu-id="e111e-142">Please [open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="e111e-143">環境変数が更新された場合は、コマンド ラインの新しいインスタンスが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="e111e-143">A new instance of the command-line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="e111e-144">ビルド</span><span class="sxs-lookup"><span data-stu-id="e111e-144">Build</span></span>

<span data-ttu-id="e111e-145">このガイドの残りの部分では、.NET for Apache Spark リポジトリをご自分のコンピューターにクローンしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e111e-145">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="e111e-146">任意の場所にリポジトリをクローンすることができます (たとえば、`C:\github\dotnet-spark\`)。</span><span class="sxs-lookup"><span data-stu-id="e111e-146">You can choose any location for the cloned repository, e.g., `C:\github\dotnet-spark\`.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="e111e-147">.NET for Apache Spark の Scala 拡張機能レイヤーをビルドする</span><span class="sxs-lookup"><span data-stu-id="e111e-147">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="e111e-148">.NET アプリケーションを送信したとき、.NET for Apache Spark には、要求の処理方法を Apache Spark に伝える、Scala で記述された必要なロジックが含まれています (たとえば、新しい Spark セッションを作成する要求や、.NET 側から JVM 側にデータを転送する要求など)。</span><span class="sxs-lookup"><span data-stu-id="e111e-148">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (e.g., request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="e111e-149">このロジックは、[.NET for Spark の Scala ソース コード](https://github.com/dotnet/spark/tree/master/src/scala)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e111e-149">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="e111e-150">.NET Framework、.NET Core のどちらを使用しているかにかかわらず、.NET for Apache Spark の Scala 拡張機能レイヤーをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e111e-150">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package 
```

<span data-ttu-id="e111e-151">サポートされている Spark バージョンに対して作成された JAR を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e111e-151">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="e111e-152">.NET for Spark のサンプル アプリケーションをビルドする</span><span class="sxs-lookup"><span data-stu-id="e111e-152">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="e111e-153">このセクションでは、.NET for Apache Spark の[サンプル アプリケーション](https://github.com/dotnet/spark/tree/master/examples)をビルドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e111e-153">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="e111e-154">これらの手順は、あらゆる .NET for Spark アプリケーションのビルド プロセス全体を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e111e-154">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="e111e-155">.NET Framework 用に Visual Studio を使用する</span><span class="sxs-lookup"><span data-stu-id="e111e-155">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="e111e-156">Visual Studio で `src\csharp\Microsoft.Spark.sln` を開き、`examples` フォルダーの下に `Microsoft.Spark.CSharp.Examples` プロジェクトをビルドします (その後、これによって .NET バインドのプロジェクトもビルドされます)。</span><span class="sxs-lookup"><span data-stu-id="e111e-156">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="e111e-157">必要に応じて、`Microsoft.Spark.Examples` プロジェクトに独自のコードを記述できます (この例の "input_file.json" は、データフレームの作成に使用するデータが含まれている json ファイルです)。</span><span class="sxs-lookup"><span data-stu-id="e111e-157">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
      ```csharp
        // Instantiate a session
        var spark = SparkSession
            .Builder()
            .AppName("Hello Spark!")
            .GetOrCreate();

        // Create initial DataFrame
        DataFrame df = spark.Read().Json(input_file.json);

        // Print schema
        df.PrintSchema();

        // Apply a filter and show results
        df.Filter(df["age"] > 21).Show();
      ```

     <span data-ttu-id="e111e-158">ビルドが成功すると、出力ディレクトリに作成された適切なバイナリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e111e-158">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>     
     <span data-ttu-id="e111e-159">コンソール出力の例:</span><span class="sxs-lookup"><span data-stu-id="e111e-159">Sample console output:</span></span>
     
      ```powershell
            Directory: C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461


        Mode                LastWriteTime         Length Name
        ----                -------------         ------ ----
        -a----         3/6/2019  12:18 AM         125440 Apache.Arrow.dll
        -a----        3/16/2019  12:00 AM          13824 Microsoft.Spark.CSharp.Examples.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.CSharp.Examples.exe.config
        -a----        3/16/2019  12:00 AM           2720 Microsoft.Spark.CSharp.Examples.pdb
        -a----        3/16/2019  12:00 AM         143360 Microsoft.Spark.dll
        -a----        3/16/2019  12:00 AM          63388 Microsoft.Spark.pdb
        -a----        3/16/2019  12:00 AM          34304 Microsoft.Spark.Worker.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.Worker.exe.config
        -a----        3/16/2019  12:00 AM          11900 Microsoft.Spark.Worker.pdb
        -a----        3/16/2019  12:00 AM          23552 Microsoft.Spark.Worker.xml
        -a----        3/16/2019  12:00 AM         332363 Microsoft.Spark.xml
        ------------------------------------------- More framework files -------------------------------------
      ```     

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="e111e-160">.NET Core 用に .NET Core CLI を使用する</span><span class="sxs-lookup"><span data-stu-id="e111e-160">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="e111e-161">現在、Spark .NET の .NET Core ビルドを自動化する作業に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="e111e-161">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="e111e-162">それまでは、いくつかの手順を手動で実行していただくようお願いいたします。</span><span class="sxs-lookup"><span data-stu-id="e111e-162">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="e111e-163">ワーカーをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e111e-163">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
      
      <span data-ttu-id="e111e-164">コンソール出力の例:</span><span class="sxs-lookup"><span data-stu-id="e111e-164">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish\
      ```    

  2. <span data-ttu-id="e111e-165">サンプルをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e111e-165">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
   
      <span data-ttu-id="e111e-166">コンソール出力の例:</span><span class="sxs-lookup"><span data-stu-id="e111e-166">Sample console output:</span></span>

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish\
      ```     

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="e111e-167">.NET for Spark のサンプル アプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="e111e-167">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="e111e-168">サンプルをビルドしたら、その実行には、.NET Framework、.NET Core のどちらを対象としているかにかかわらず `spark-submit` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e111e-168">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="e111e-169">[必須コンポーネント](#prerequisites)のセクションに従っていることと、Apache Spark がインストール済みであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e111e-169">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="e111e-170">`DOTNET_WORKER_DIR` または `PATH` 環境変数を設定して、`Microsoft.Spark.Worker` バイナリが生成されたパスが含まれるようにします (たとえば、.NET Framework の場合は `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461`、.NET Core の場合は `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish`)。</span><span class="sxs-lookup"><span data-stu-id="e111e-170">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (e.g., `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461` for .NET Framework, `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish` for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. <span data-ttu-id="e111e-171">Powershell を開き、アプリのバイナリが生成されたディレクトリに移動します (たとえば、.NET Framework の場合は `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461`、.NET Core の場合は `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish`)。</span><span class="sxs-lookup"><span data-stu-id="e111e-171">Open Powershell and go to the directory where your app binary has been generated (e.g., `C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461` for .NET Framework, `C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish` for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. <span data-ttu-id="e111e-172">次の基本構造に従ってアプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e111e-172">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="e111e-173">実行できるいくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e111e-173">Here are some examples you can run:</span></span>

     - <span data-ttu-id="e111e-174">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="e111e-174">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="e111e-175">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="e111e-175">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="e111e-176">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (Maven アクセス可能)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="e111e-176">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="e111e-177">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jar 提供)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="e111e-177">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd 
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
