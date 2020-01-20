---
title: .NET for Apache Spark の概要
description: Windows で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 934b91a258937a976804109c71df232b8ce6d6d7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337586"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="3d2b0-103">チュートリアル: .NET for Apache Spark の概要</span><span class="sxs-lookup"><span data-stu-id="3d2b0-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="3d2b0-104">このチュートリアルでは、Windows で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="3d2b0-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="3d2b0-106">.NET for Apache Spark 用に Windows 環境を準備する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="3d2b0-107">最初の .NET for Apache Spark アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="3d2b0-108">.NET for Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="3d2b0-109">環境を準備する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-109">Prepare your environment</span></span>

<span data-ttu-id="3d2b0-110">アプリの作成を開始する前に、いくつかの前提条件となる依存関係を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="3d2b0-111">コマンドライン環境から `dotnet`、`java`、`mvn`、`spark-shell` を実行できる場合は、環境が既に準備されているため、次のセクションに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="3d2b0-112">コマンドのいずれかまたはすべてを実行できない場合は、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="3d2b0-113">1..NET のインストール</span><span class="sxs-lookup"><span data-stu-id="3d2b0-113">1. Install .NET</span></span>

<span data-ttu-id="3d2b0-114">.NET アプリのビルドを開始するには、.NET SDK (ソフトウェア開発キット) をダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="3d2b0-115">[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span> <span data-ttu-id="3d2b0-116">SDK をインストールすると、`dotnet` ツールチェーンが PATH に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="3d2b0-117">.NET Core SDK をインストールしたら、新しいコマンド プロンプトを開き、`dotnet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-117">Once you've installed the .NET Core SDK, open a new command prompt and run `dotnet`.</span></span>

<span data-ttu-id="3d2b0-118">コマンドが実行され、dotnet の使用方法に関する情報が出力された場合は、次の手順に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="3d2b0-119">`'dotnet' is not recognized as an internal or external command` エラーが発生した場合は、コマンドを実行する前に**新しい**コマンド プロンプトを開いたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="3d2b0-120">2.Java のインストール</span><span class="sxs-lookup"><span data-stu-id="3d2b0-120">2. Install Java</span></span>

<span data-ttu-id="3d2b0-121">[Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

<span data-ttu-id="3d2b0-122">ご使用のオペレーティング システムに適したバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="3d2b0-123">たとえば、Windows x64 マシンには、**jdk-8u201-windows-x64.exe** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span> <span data-ttu-id="3d2b0-124">次に、コマンド `java` を使用してインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-124">Then, use the command `java` to verify the installation.</span></span>

![Java のダウンロード](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a><span data-ttu-id="3d2b0-126">3.7-zip のインストール</span><span class="sxs-lookup"><span data-stu-id="3d2b0-126">3. Install 7-zip</span></span>

<span data-ttu-id="3d2b0-127">Apache Spark は、圧縮された .tgz ファイルとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="3d2b0-128">7-zip などの抽出プログラムを使用して、ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-128">Use an extraction program, like 7-zip, to extract the file.</span></span>

* <span data-ttu-id="3d2b0-129">[7-Zip のダウンロード](https://www.7-zip.org/) ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-129">Visit [7-Zip downloads](https://www.7-zip.org/).</span></span>
* <span data-ttu-id="3d2b0-130">ページの最初の表で、使用しているオペレーティング システムに応じて、32-bit x86 または 64-bit x64 ダウンロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-130">In the first table on the page, select the 32-bit x86 or 64-bit x64 download, depending on your operating system.</span></span>
* <span data-ttu-id="3d2b0-131">ダウンロードが完了したら、インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-131">When the download completes, run the installer.</span></span>

![7Zip のダウンロード](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a><span data-ttu-id="3d2b0-133">4.Apache Spark のインストール</span><span class="sxs-lookup"><span data-stu-id="3d2b0-133">4. Install Apache Spark</span></span>

<span data-ttu-id="3d2b0-134">[Apache Spark をダウンロードしてインストールします](https://spark.apache.org/downloads.html)。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-134">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="3d2b0-135">バージョン 2.3.\*、2.4.0、2.4.1、2.4.3、または 2.4.4 から選択する必要があります (.NET for Apache Spark は、他のバージョンの Apache Spark と互換性がありません)。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-135">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="3d2b0-136">次の手順で使用するコマンドは、[Apache Spark 2.4.1 をダウンロードしてインストールしていること](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz)を前提としています。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-136">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="3d2b0-137">別のバージョンを使用する場合は、**2.4.1** を適切なバージョン番号に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-137">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="3d2b0-138">その後、 **.tar** ファイルと Apache Spark ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-138">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="3d2b0-139">入れ子になった **.tar** ファイルを抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-139">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="3d2b0-140">ダウンロードした **spark-2.4.1-bin-hadoop2.7.tgz** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-140">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="3d2b0-141">ファイルを右クリックし、 **[7-Zip] -> [ここに展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-141">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="3d2b0-142">ダウンロードした **.tgz** ファイルの横に **spark-2.4.1-bin-hadoop2.7.tar** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-142">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="3d2b0-143">Apache Spark ファイルを抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-143">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="3d2b0-144">**spark-2.4.1-bin-hadoop2.7.tar** を右クリックし、 **[7-Zip] -> [展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-144">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="3d2b0-145">**[展開先]** フィールドに「**C:\bin**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-145">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="3d2b0-146">**[展開先]** フィールドの下のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-146">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="3d2b0-147">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-147">Select **OK**.</span></span>
* <span data-ttu-id="3d2b0-148">Apache Spark ファイルが C:\bin\spark-2.4.1-bin-hadoop2.7\ に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-148">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Spark のインストール](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="3d2b0-150">次のコマンドを実行して、Apache Spark を検索するために使用する環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-150">Run the following commands to set the environment variables used to locate Apache Spark:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="3d2b0-151">すべてをインストールし、環境変数を設定したら、**新しい**コマンド プロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-151">Once you've installed everything and set your environment variables, open a **new** command prompt and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="3d2b0-152">コマンドが実行され、バージョン情報が出力された場合は、次の手順に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-152">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="3d2b0-153">`'spark-submit' is not recognized as an internal or external command` エラーが発生した場合は、**新しい**コマンド プロンプトを開いたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-153">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="3d2b0-154">5..NET for Apache Spark のインストール</span><span class="sxs-lookup"><span data-stu-id="3d2b0-154">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="3d2b0-155">.NET for Apache Spark GitHub から、[Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-155">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="3d2b0-156">たとえば、Windows マシンを使用していて、.NET Core の使用を計画している場合は、[Windows x64 netcoreapp2.1 リリースをダウンロード](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip)します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-156">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp2.1 release](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span></span>

<span data-ttu-id="3d2b0-157">Microsoft.Spark.Worker を抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-157">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="3d2b0-158">ダウンロードした **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-158">Locate the **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="3d2b0-159">右クリックし、 **[7-Zip] -> [ここに展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-159">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="3d2b0-160">**[展開先]** フィールドに「**C:\bin**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-160">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="3d2b0-161">**[展開先]** フィールドの下のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-161">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="3d2b0-162">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-162">Select **OK**.</span></span>

![.NET Spark のインストール](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a><span data-ttu-id="3d2b0-164">6.WinUtils のインストール</span><span class="sxs-lookup"><span data-stu-id="3d2b0-164">6. Install WinUtils</span></span>

<span data-ttu-id="3d2b0-165">.NET for Apache Spark では、Apache Spark と共に WinUtils をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-165">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="3d2b0-166">[winutils.exe をダウンロード](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-166">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="3d2b0-167">次に、WinUtils を **C:\bin\spark-2.4.1-bin-hadoop2.7\bin** にコピーします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-167">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="3d2b0-168">Spark インストール フォルダー名の末尾に注釈が付けられている別のバージョンの Hadoop を使用している場合は、使用している Hadoop のバージョンと互換性のある[バージョンの WinUtils を選択](https://github.com/steveloughran/winutils)します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-168">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="3d2b0-169">7.DOTNET_WORKER_DIR の設定と依存関係の確認</span><span class="sxs-lookup"><span data-stu-id="3d2b0-169">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="3d2b0-170">次のコマンドを実行して `DOTNET_WORKER_DIR` 環境変数を設定します。この変数は、.NET アプリで .NET for Apache Spark を検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-170">Run the following command to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark:</span></span>

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

<span data-ttu-id="3d2b0-171">最後に、次のセクションに進む前に、コマンド ラインから `dotnet`、`java`、`mvn`、`spark-shell` を実行できることを再度確認します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="3d2b0-172">.NET for Apache Spark アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="3d2b0-173">1.コンソール アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-173">1. Create a console app</span></span>

<span data-ttu-id="3d2b0-174">コマンド プロンプトで、次のコマンドを実行して、新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-174">In your command prompt, run the following commands to create a new console application:</span></span>

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="3d2b0-175">`dotnet` コマンドで、種類が `console` の `new` アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="3d2b0-176">`-o` パラメーターで、アプリが格納されるディレクトリ *mySparkApp* を作成し、必要なファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="3d2b0-177">`cd mySparkApp` コマンドで、ディレクトリを、先ほど作成したアプリ ディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="3d2b0-178">2.NuGet パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="3d2b0-178">2. Install NuGet package</span></span>

<span data-ttu-id="3d2b0-179">アプリで .NET for Apache Spark を使用するには、Microsoft.Spark パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="3d2b0-180">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-180">In your command prompt, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a><span data-ttu-id="3d2b0-181">3.アプリのコーディング</span><span class="sxs-lookup"><span data-stu-id="3d2b0-181">3. Code your app</span></span>

<span data-ttu-id="3d2b0-182">Visual Studio Code または任意のテキスト エディターで *Program.cs* を開き、すべてのコードを次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-add-data-file"></a><span data-ttu-id="3d2b0-183">4.データ ファイルの追加</span><span class="sxs-lookup"><span data-stu-id="3d2b0-183">4. Add data file</span></span>

<span data-ttu-id="3d2b0-184">アプリでは、テキスト行を含むファイルが処理されます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-184">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="3d2b0-185">*mySparkApp* ディレクトリに、次のテキストを含む *input.txt* ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-185">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="3d2b0-186">.NET for Apache Spark アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-186">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="3d2b0-187">次のコマンドを実行して、アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-187">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="3d2b0-188">次のコマンドを実行して、Apache Spark で実行するようにアプリケーションを送信します。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-188">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. <span data-ttu-id="3d2b0-189">アプリを実行すると、*input.txt* ファイルのワード カウント データがコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-189">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="3d2b0-190">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="3d2b0-190">Congratulations!</span></span> <span data-ttu-id="3d2b0-191">.NET for Apache Spark アプリの作成と実行が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-191">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3d2b0-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="3d2b0-192">Next steps</span></span>

<span data-ttu-id="3d2b0-193">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="3d2b0-194">.NET for Apache Spark 用に Windows 環境を準備する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-194">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="3d2b0-195">最初の .NET for Apache Spark アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-195">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="3d2b0-196">.NET for Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="3d2b0-196">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="3d2b0-197">上記の手順を説明したビデオを見るには、[.NET for Apache Spark 101 ビデオ シリーズ](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-197">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="3d2b0-198">詳細については、リソースのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d2b0-198">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3d2b0-199">.NET for Apache Spark のリソース</span><span class="sxs-lookup"><span data-stu-id="3d2b0-199">.NET for Apache Spark Resources</span></span>](../resources/index.md)
