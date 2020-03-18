---
title: .NET for Apache Spark の概要
description: Windows、macOS、Ubuntu で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7375c385245a05d7dc29d5df89d875bf6cb4141a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187537"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="7dcee-103">チュートリアル: .NET for Apache Spark の概要</span><span class="sxs-lookup"><span data-stu-id="7dcee-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="7dcee-104">このチュートリアルでは、Windows、macOS、Ubuntu で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, MacOS, and Ubuntu.</span></span>

<span data-ttu-id="7dcee-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="7dcee-106">.NET for Apache Spark の環境を準備する</span><span class="sxs-lookup"><span data-stu-id="7dcee-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="7dcee-107">最初の .NET for Apache Spark アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="7dcee-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="7dcee-108">.NET for Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="7dcee-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="7dcee-109">環境を準備する</span><span class="sxs-lookup"><span data-stu-id="7dcee-109">Prepare your environment</span></span>

<span data-ttu-id="7dcee-110">アプリの作成を開始する前に、いくつかの前提条件となる依存関係を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcee-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="7dcee-111">コマンドライン環境から `dotnet`、`java`、`mvn`、`spark-shell` を実行できる場合は、環境が既に準備されているため、次のセクションに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="7dcee-112">コマンドのいずれかまたはすべてを実行できない場合は、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="7dcee-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="7dcee-113">1..NET のインストール</span><span class="sxs-lookup"><span data-stu-id="7dcee-113">1. Install .NET</span></span>

<span data-ttu-id="7dcee-114">.NET アプリのビルドを開始するには、.NET SDK (ソフトウェア開発キット) をダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcee-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="7dcee-115">[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="7dcee-116">SDK をインストールすると、`dotnet` ツールチェーンが PATH に追加されます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="7dcee-117">.NET Core SDK をインストールしたら、新しいコマンド プロンプトまたはターミナルを開き、`dotnet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="7dcee-118">コマンドが実行され、dotnet の使用方法に関する情報が出力された場合は、次の手順に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="7dcee-119">`'dotnet' is not recognized as an internal or external command` エラーが発生した場合は、コマンドを実行する前に**新しい**コマンド プロンプトまたはターミナルを開いたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7dcee-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="7dcee-120">2.Java のインストール</span><span class="sxs-lookup"><span data-stu-id="7dcee-120">2. Install Java</span></span>

<span data-ttu-id="7dcee-121">Windows および macOS の場合は [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)、Ubuntu の場合は [OpenJDK 8](https://openjdk.java.net/install/) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and MacOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="7dcee-122">ご使用のオペレーティング システムに適したバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="7dcee-123">たとえば、(次のように) Windows x64 マシンの場合は **jdk-8u201-windows-x64.exe**、macOS の場合は **jdk-8u231-macosx-x64.dmg** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for MacOS.</span></span> <span data-ttu-id="7dcee-124">次に、コマンド `java` を使用してインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-124">Then, use the command `java` to verify the installation.</span></span>

![Java のダウンロード](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="7dcee-126">3.圧縮ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="7dcee-126">3. Install compression software</span></span>

<span data-ttu-id="7dcee-127">Apache Spark は、圧縮された .tgz ファイルとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="7dcee-128">[7-Zip](https://www.7-zip.org/)、[WinZip](https://www.winzip.com/) などの抽出プログラムを使用してファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="7dcee-129">4.Apache Spark のインストール</span><span class="sxs-lookup"><span data-stu-id="7dcee-129">4. Install Apache Spark</span></span>

<span data-ttu-id="7dcee-130">[Apache Spark をダウンロードしてインストールします](https://spark.apache.org/downloads.html)。</span><span class="sxs-lookup"><span data-stu-id="7dcee-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="7dcee-131">バージョン 2.3.\*、2.4.0、2.4.1、2.4.3、または 2.4.4 から選択する必要があります (.NET for Apache Spark は、他のバージョンの Apache Spark と互換性がありません)。</span><span class="sxs-lookup"><span data-stu-id="7dcee-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="7dcee-132">次の手順で使用するコマンドは、[Apache Spark 2.4.1 をダウンロードしてインストールしていること](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz)を前提としています。</span><span class="sxs-lookup"><span data-stu-id="7dcee-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="7dcee-133">別のバージョンを使用する場合は、**2.4.1** を適切なバージョン番号に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="7dcee-134">その後、 **.tar** ファイルと Apache Spark ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="7dcee-135">入れ子になった **.tar** ファイルを抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="7dcee-136">ダウンロードした **spark-2.4.1-bin-hadoop2.7.tgz** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="7dcee-137">ファイルを右クリックし、 **[7-Zip] -> [ここに展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="7dcee-138">ダウンロードした **.tgz** ファイルの横に **spark-2.4.1-bin-hadoop2.7.tar** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="7dcee-139">Apache Spark ファイルを抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="7dcee-140">**spark-2.4.1-bin-hadoop2.7.tar** を右クリックし、 **[7-Zip] -> [展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-140">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="7dcee-141">**[展開先]** フィールドに「**C:\bin**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="7dcee-142">**[展開先]** フィールドの下のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="7dcee-143">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-143">Select **OK**.</span></span>
* <span data-ttu-id="7dcee-144">Apache Spark ファイルが C:\bin\spark-2.4.1-bin-hadoop2.7\ に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Spark のインストール](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="7dcee-146">次のコマンドを実行して、**Windows** 上で Apache Spark を検索するために使用する環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-146">Run the following commands to set the environment variables used to locate Apache Spark on **Windows**:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="7dcee-147">次のコマンドを実行して、**macOS** と **Ubuntu** 上で Apache Spark を検索するために使用する環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-147">Run the following commands to set the environment variables used to locate Apache Spark on **MacOS** and **Ubuntu**:</span></span>

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

<span data-ttu-id="7dcee-148">すべてをインストールし、環境変数を設定したら、**新しい**コマンド プロンプトまたはターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-148">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="7dcee-149">コマンドが実行され、バージョン情報が出力された場合は、次の手順に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-149">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="7dcee-150">`'spark-submit' is not recognized as an internal or external command` エラーが発生した場合は、**新しい**コマンド プロンプトを開いたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7dcee-150">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="7dcee-151">5..NET for Apache Spark のインストール</span><span class="sxs-lookup"><span data-stu-id="7dcee-151">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="7dcee-152">.NET for Apache Spark GitHub から、[Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-152">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="7dcee-153">たとえば、Windows マシンを使用していて、.NET Core の使用を計画している場合は、[Windows x64 netcoreapp3.1 リリースをダウンロード](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip)します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-153">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span></span>

<span data-ttu-id="7dcee-154">Microsoft.Spark.Worker を抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-154">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="7dcee-155">ダウンロードした **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-155">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="7dcee-156">右クリックし、 **[7-Zip] -> [ここに展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-156">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="7dcee-157">**[展開先]** フィールドに「**C:\bin**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-157">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="7dcee-158">**[展開先]** フィールドの下のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-158">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="7dcee-159">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-159">Select **OK**.</span></span>

![.NET Spark のインストール](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="7dcee-161">6.WinUtils のインストール (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="7dcee-161">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="7dcee-162">.NET for Apache Spark では、Apache Spark と共に WinUtils をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcee-162">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="7dcee-163">[winutils.exe をダウンロード](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-163">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="7dcee-164">次に、WinUtils を **C:\bin\spark-2.4.1-bin-hadoop2.7\bin** にコピーします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-164">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="7dcee-165">Spark インストール フォルダー名の末尾に注釈が付けられている別のバージョンの Hadoop を使用している場合は、使用している Hadoop のバージョンと互換性のある[バージョンの WinUtils を選択](https://github.com/steveloughran/winutils)します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-165">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="7dcee-166">7.DOTNET_WORKER_DIR の設定と依存関係の確認</span><span class="sxs-lookup"><span data-stu-id="7dcee-166">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="7dcee-167">次のコマンドのいずれかを実行して `DOTNET_WORKER_DIR` 環境変数を設定します。この変数は、.NET アプリで .NET for Apache Spark を検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-167">Run one of the following commands to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span>

<span data-ttu-id="7dcee-168">**Windows** 上では、[新しい環境変数](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` を作成し、Microsoft.Spark.Worker をダウンロードして抽出したディレクトリ (`C:\bin\Microsoft.Spark.Worker\` など) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-168">On **Windows**, create a [new environment variable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, `C:\bin\Microsoft.Spark.Worker\`).</span></span>

<span data-ttu-id="7dcee-169">**macOS** 上では、`export DOTNET_WORKER_DIR <your_path>` を使用して新しい環境変数を作成し、Microsoft.Spark.Worker をダウンロードして抽出したディレクトリ ( *~/bin/Microsoft.Spark.Worker/* など) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-169">On **MacOS**, create a new environment variable using `export DOTNET_WORKER_DIR <your_path>` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker/*).</span></span>

<span data-ttu-id="7dcee-170">**Ubuntu** 上では、[新しい環境変数](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` を作成し、Microsoft.Spark.Worker をダウンロードして抽出したディレクトリ ( *~/bin/Microsoft.Spark.Worker* など) に設定します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-170">On **Ubuntu**, create a [new environment variable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker*).</span></span>

<span data-ttu-id="7dcee-171">最後に、次のセクションに進む前に、コマンド ラインから `dotnet`、`java`、`mvn`、`spark-shell` を実行できることを再度確認します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="7dcee-172">.NET for Apache Spark アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="7dcee-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="7dcee-173">1.コンソール アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="7dcee-173">1. Create a console app</span></span>

<span data-ttu-id="7dcee-174">コマンド プロンプトまたはターミナルで、次のコマンドを実行して、新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-174">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="7dcee-175">`dotnet` コマンドで、種類が `console` の `new` アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="7dcee-176">`-o` パラメーターで、アプリが格納されるディレクトリ *mySparkApp* を作成し、必要なファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="7dcee-177">`cd mySparkApp` コマンドで、ディレクトリを、先ほど作成したアプリ ディレクトリに変更します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="7dcee-178">2.NuGet パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="7dcee-178">2. Install NuGet package</span></span>

<span data-ttu-id="7dcee-179">アプリで .NET for Apache Spark を使用するには、Microsoft.Spark パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="7dcee-180">コマンド プロンプトまたはターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-180">In your command prompt or terminal, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a><span data-ttu-id="7dcee-181">3.アプリのコーディング</span><span class="sxs-lookup"><span data-stu-id="7dcee-181">3. Code your app</span></span>

<span data-ttu-id="7dcee-182">Visual Studio Code または任意のテキスト エディターで *Program.cs* を開き、すべてのコードを次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
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

### <a name="4-create-and-add-a-data-file"></a><span data-ttu-id="7dcee-183">4.データ ファイルの作成と追加</span><span class="sxs-lookup"><span data-stu-id="7dcee-183">4. Create and add a data file</span></span>

<span data-ttu-id="7dcee-184">コマンド プロンプトまたはターミナルを開き、アプリ フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-184">Open your command prompt or terminal and navigate into your app folder.</span></span>

```bash
cd <your-app-output-directory>
```

<span data-ttu-id="7dcee-185">アプリでは、テキスト行を含むファイルが処理されます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-185">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="7dcee-186">*mySparkApp* ディレクトリに、次のテキストを含む *input.txt* ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-186">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="7dcee-187">.NET for Apache Spark アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="7dcee-187">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="7dcee-188">次のコマンドを実行して、アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="7dcee-188">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="7dcee-189">次のコマンドを実行して、Apache Spark で実行するようにアプリケーションを送信します。</span><span class="sxs-lookup"><span data-stu-id="7dcee-189">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > <span data-ttu-id="7dcee-190">このコマンドは、Apache Spark をダウンロードして PATH 環境変数に追加し、`spark-submit` を使用できる状態であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7dcee-190">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="7dcee-191">そうでなければ、完全なパスを使用する必要があります (たとえば、*C:\bin\apache-spark\bin\spark-submit* や *~/spark/bin/spark-submit*)。</span><span class="sxs-lookup"><span data-stu-id="7dcee-191">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

3. <span data-ttu-id="7dcee-192">アプリを実行すると、*input.txt* ファイルのワード カウント データがコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="7dcee-192">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="7dcee-193">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="7dcee-193">Congratulations!</span></span> <span data-ttu-id="7dcee-194">.NET for Apache Spark アプリの作成と実行が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="7dcee-194">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7dcee-195">次の手順</span><span class="sxs-lookup"><span data-stu-id="7dcee-195">Next steps</span></span>

<span data-ttu-id="7dcee-196">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="7dcee-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="7dcee-197">.NET for Apache Spark 用に Windows 環境を準備する</span><span class="sxs-lookup"><span data-stu-id="7dcee-197">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="7dcee-198">最初の .NET for Apache Spark アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="7dcee-198">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="7dcee-199">.NET for Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="7dcee-199">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="7dcee-200">上記の手順を説明したビデオを見るには、[.NET for Apache Spark 101 ビデオ シリーズ](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dcee-200">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="7dcee-201">詳細については、リソースのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dcee-201">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="7dcee-202">.NET for Apache Spark のリソース</span><span class="sxs-lookup"><span data-stu-id="7dcee-202">.NET for Apache Spark Resources</span></span>](../resources/index.md)
