---
title: .NET for Apache Spark の概要
description: Windows、macOS、Ubuntu で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。
ms.date: 09/17/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 7afb35c9d02db1d1ee2bf04d565f79588b00695e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866043"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="f0136-103">チュートリアル: .NET for Apache Spark の概要</span><span class="sxs-lookup"><span data-stu-id="f0136-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="f0136-104">このチュートリアルでは、Windows、macOS、Ubuntu で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0136-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="f0136-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0136-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="f0136-106">.NET for Apache Spark の環境を準備する</span><span class="sxs-lookup"><span data-stu-id="f0136-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="f0136-107">最初の .NET for Apache Spark アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="f0136-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="f0136-108">.NET for Apache Spark アプリケーションをビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="f0136-108">Build and run your .NET for Apache Spark application</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prepare-your-environment"></a><span data-ttu-id="f0136-109">環境を準備する</span><span class="sxs-lookup"><span data-stu-id="f0136-109">Prepare your environment</span></span>

<span data-ttu-id="f0136-110">アプリの作成を開始する前に、いくつかの前提条件となる依存関係を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0136-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="f0136-111">コマンド ライン環境から `dotnet`、`java`、`spark-shell` を実行できる場合は、環境が既に準備されているため、次のセクションに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="f0136-111">If you can run `dotnet`, `java`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="f0136-112">コマンドのいずれかまたはすべてを実行できない場合は、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="f0136-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="f0136-113">1..NET のインストール</span><span class="sxs-lookup"><span data-stu-id="f0136-113">1. Install .NET</span></span>

<span data-ttu-id="f0136-114">.NET アプリのビルドを開始するには、.NET SDK (ソフトウェア開発キット) をダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0136-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="f0136-115">[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0136-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="f0136-116">SDK をインストールすると、`dotnet` ツールチェーンが PATH に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f0136-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="f0136-117">.NET Core SDK をインストールしたら、新しいコマンド プロンプトまたはターミナルを開き、`dotnet` を実行します。</span><span class="sxs-lookup"><span data-stu-id="f0136-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="f0136-118">コマンドが実行され、dotnet の使用方法に関する情報が出力された場合は、次の手順に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="f0136-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="f0136-119">`'dotnet' is not recognized as an internal or external command` エラーが発生した場合は、コマンドを実行する前に**新しい**コマンド プロンプトまたはターミナルを開いたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f0136-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="f0136-120">2.Java のインストール</span><span class="sxs-lookup"><span data-stu-id="f0136-120">2. Install Java</span></span>

<span data-ttu-id="f0136-121">Windows および macOS の場合は [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)、Ubuntu の場合は [OpenJDK 8](https://openjdk.java.net/install/) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0136-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="f0136-122">ご使用のオペレーティング システムに適したバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0136-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="f0136-123">たとえば、(次のように) Windows x64 マシンの場合は **jdk-8u201-windows-x64.exe**、macOS の場合は **jdk-8u231-macosx-x64.dmg** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0136-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="f0136-124">次に、コマンド `java` を使用してインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0136-124">Then, use the command `java` to verify the installation.</span></span>

![Java のダウンロード](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="f0136-126">3.圧縮ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="f0136-126">3. Install compression software</span></span>

<span data-ttu-id="f0136-127">Apache Spark は、圧縮された .tgz ファイルとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="f0136-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="f0136-128">[7-Zip](https://www.7-zip.org/)、[WinZip](https://www.winzip.com/) などの抽出プログラムを使用してファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="f0136-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="f0136-129">4.Apache Spark のインストール</span><span class="sxs-lookup"><span data-stu-id="f0136-129">4. Install Apache Spark</span></span>

<span data-ttu-id="f0136-130">[Apache Spark をダウンロードしてインストールします](https://spark.apache.org/downloads.html)。</span><span class="sxs-lookup"><span data-stu-id="f0136-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="f0136-131">バージョン 2.3.\*、2.4.0、2.4.1、2.4.3、または 2.4.4 から選択する必要があります (.NET for Apache Spark は、他のバージョンの Apache Spark と互換性がありません)。</span><span class="sxs-lookup"><span data-stu-id="f0136-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="f0136-132">次の手順で使用するコマンドは、[Apache Spark 2.4.1 をダウンロードしてインストールしていること](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz)を前提としています。</span><span class="sxs-lookup"><span data-stu-id="f0136-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="f0136-133">別のバージョンを使用する場合は、**2.4.1** を適切なバージョン番号に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f0136-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="f0136-134">その後、 **.tar** ファイルと Apache Spark ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="f0136-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="f0136-135">入れ子になった **.tar** ファイルを抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f0136-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="f0136-136">ダウンロードした **spark-2.4.1-bin-hadoop2.7.tgz** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f0136-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="f0136-137">ファイルを右クリックし、 **[7-Zip] -> [ここに展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f0136-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="f0136-138">ダウンロードした **.tgz** ファイルの横に **spark-2.4.1-bin-hadoop2.7.tar** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0136-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="f0136-139">Apache Spark ファイルを抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f0136-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="f0136-140">**spark-2.4.1-bin-hadoop2.7.tar** を右クリックし、 **[7-Zip] -> [ここに展開]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="f0136-140">Right-click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="f0136-141">**[展開先]** フィールドに「**C:\bin**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f0136-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="f0136-142">**[展開先]** フィールドの下のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f0136-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="f0136-143">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0136-143">Select **OK**.</span></span>
* <span data-ttu-id="f0136-144">Apache Spark ファイルが C:\bin\spark-2.4.1-bin-hadoop2.7\ に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="f0136-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Spark のインストール](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="f0136-146">次のコマンドを実行して、Apache Spark を検索するために使用する環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="f0136-146">Run the following commands to set the environment variables used to locate Apache Spark.</span></span> <span data-ttu-id="f0136-147">Windows の場合は、管理者モードでコマンド プロンプトを実行してください。</span><span class="sxs-lookup"><span data-stu-id="f0136-147">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="f0136-148">Windows</span><span class="sxs-lookup"><span data-stu-id="f0136-148">Windows</span></span>](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[<span data-ttu-id="f0136-149">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="f0136-149">Mac/Linux</span></span>](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

<span data-ttu-id="f0136-150">すべてをインストールし、環境変数を設定したら、**新しい**コマンド プロンプトまたはターミナルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0136-150">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

```text
spark-submit --version
```

<span data-ttu-id="f0136-151">コマンドが実行され、バージョン情報が出力された場合は、次の手順に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="f0136-151">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="f0136-152">`'spark-submit' is not recognized as an internal or external command` エラーが発生した場合は、**新しい**コマンド プロンプトを開いたことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f0136-152">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="f0136-153">5..NET for Apache Spark のインストール</span><span class="sxs-lookup"><span data-stu-id="f0136-153">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="f0136-154">.NET for Apache Spark GitHub から、[Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f0136-154">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="f0136-155">たとえば、Windows マシンを使用していて、.NET Core の使用を計画している場合は、[Windows x64 netcoreapp3.1 リリースをダウンロード](https://github.com/dotnet/spark/releases)します。</span><span class="sxs-lookup"><span data-stu-id="f0136-155">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases).</span></span>

<span data-ttu-id="f0136-156">Microsoft.Spark.Worker を抽出するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f0136-156">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="f0136-157">ダウンロードした **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="f0136-157">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="f0136-158">右クリックし、 **[7-Zip] -> [ここに展開]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f0136-158">Right-click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="f0136-159">**[展開先]** フィールドに「**C:\bin**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f0136-159">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="f0136-160">**[展開先]** フィールドの下のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f0136-160">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="f0136-161">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0136-161">Select **OK**.</span></span>

![.NET Spark のインストール](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="f0136-163">6.WinUtils のインストール (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="f0136-163">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="f0136-164">.NET for Apache Spark では、Apache Spark と共に WinUtils をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0136-164">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="f0136-165">[winutils.exe をダウンロード](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)します。</span><span class="sxs-lookup"><span data-stu-id="f0136-165">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="f0136-166">次に、WinUtils を **C:\bin\spark-2.4.1-bin-hadoop2.7\bin** にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f0136-166">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="f0136-167">Spark インストール フォルダー名の末尾に注釈が付けられている別のバージョンの Hadoop を使用している場合は、使用している Hadoop のバージョンと互換性のある[バージョンの WinUtils を選択](https://github.com/steveloughran/winutils)します。</span><span class="sxs-lookup"><span data-stu-id="f0136-167">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="f0136-168">7.DOTNET_WORKER_DIR の設定と依存関係の確認</span><span class="sxs-lookup"><span data-stu-id="f0136-168">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="f0136-169">次のコマンドのいずれかを実行して `DOTNET_WORKER_DIR` 環境変数を設定します。これは .NET アプリで .NET for Apache Spark を検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0136-169">Run one of the following commands to set the `DOTNET_WORKER_DIR` environment variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span> <span data-ttu-id="f0136-170">`<PATH-DOTNET_WORKER_DIR>` は、`Microsoft.Spark.Worker` をダウンロードして抽出したディレクトリに置き換えるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f0136-170">Make sure to replace `<PATH-DOTNET_WORKER_DIR>` with the directory where you downloaded and extracted the `Microsoft.Spark.Worker`.</span></span> <span data-ttu-id="f0136-171">Windows の場合は、管理者モードでコマンド プロンプトを実行してください。</span><span class="sxs-lookup"><span data-stu-id="f0136-171">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="f0136-172">Windows</span><span class="sxs-lookup"><span data-stu-id="f0136-172">Windows</span></span>](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[<span data-ttu-id="f0136-173">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="f0136-173">Mac/Linux</span></span>](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

<span data-ttu-id="f0136-174">最後に、次のセクションに進む前に、コマンド ラインから `dotnet`、`java`、`spark-shell` を実行できることを再度確認します。</span><span class="sxs-lookup"><span data-stu-id="f0136-174">Finally, double-check that you can run `dotnet`, `java`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="f0136-175">.NET for Apache Spark アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f0136-175">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="f0136-176">1.コンソール アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f0136-176">1. Create a console app</span></span>

<span data-ttu-id="f0136-177">コマンド プロンプトまたはターミナルで、次のコマンドを実行して、新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0136-177">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

<span data-ttu-id="f0136-178">`dotnet` コマンドで、種類が `console` の `new` アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0136-178">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="f0136-179">`-o` パラメーターを指定すると、アプリを格納する *MySparkApp* という名前のディレクトリが作成され、必要なファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f0136-179">The `-o` parameter creates a directory named *MySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="f0136-180">`cd MySparkApp` コマンドにより、作成したアプリ ディレクトリにディレクトリを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0136-180">The `cd MySparkApp` command changes the directory to the app directory you created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="f0136-181">2.NuGet パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="f0136-181">2. Install NuGet package</span></span>

<span data-ttu-id="f0136-182">アプリで .NET for Apache Spark を使用するには、Microsoft.Spark パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0136-182">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="f0136-183">コマンド プロンプトまたはターミナルで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0136-183">In your command prompt or terminal, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> <span data-ttu-id="f0136-184">このチュートリアルでは、特に指定がない限り、最新バージョンの `Microsoft.Spark` NuGet パッケージを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0136-184">This tutorial uses the latest version of the `Microsoft.Spark` NuGet package unless otherwise specified.</span></span>

### <a name="3-write-your-app"></a><span data-ttu-id="f0136-185">3.アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f0136-185">3. Write your app</span></span>

<span data-ttu-id="f0136-186">Visual Studio Code または任意のテキスト エディターで *Program.cs* を開き、すべてのコードを次のコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f0136-186">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

<span data-ttu-id="f0136-187">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) は Apache Spark アプリケーションのエントリ ポイントです。アプリケーションのコンテキストと情報を管理します。</span><span class="sxs-lookup"><span data-stu-id="f0136-187">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) is the entrypoint of Apache Spark applications, which manages the context and information of your application.</span></span> <span data-ttu-id="f0136-188">[Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) メソッドを使用し、`filePath` で指定したファイルから [DataFrame](xref:Microsoft.Spark.Sql.DataFrame) にテキスト データを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f0136-188">Using the [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) method, the text data from the file specified by the `filePath` is read into a [DataFrame](xref:Microsoft.Spark.Sql.DataFrame).</span></span> <span data-ttu-id="f0136-189">DataFrame は、データを一連の名前付き列に整理する方法です。</span><span class="sxs-lookup"><span data-stu-id="f0136-189">A DataFrame is a way of organizing data into a set of named columns.</span></span> <span data-ttu-id="f0136-190">次に、一連の変換を適用してファイル内の文を分割し、各単語をグループ化して、カウントし、降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="f0136-190">Then, a series of transformations is applied to split the sentences in the file, group each of the words, count them and order them in descending order.</span></span> <span data-ttu-id="f0136-191">これらの操作の結果は、別の DataFrame に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f0136-191">The result of these operations is stored in another DataFrame.</span></span> <span data-ttu-id="f0136-192">この時点では、.NET for Apache Spark によるデータの遅延評価のため、操作が実行されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f0136-192">Note that at this point, no operations have taken place because .NET for Apache Spark lazily evaluates the data.</span></span> <span data-ttu-id="f0136-193">`words` の変換された DataFrame の内容をコンソールに表示する [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) メソッドが呼び出されるまで、その上の行で定義されている操作は実行されません。</span><span class="sxs-lookup"><span data-stu-id="f0136-193">It's not until the [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) method is called to display the contents of the `words` transformed DataFrame to the console that the operations defined in the lines above execute.</span></span> <span data-ttu-id="f0136-194">Spark セッションが不要になったら、[Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) メソッドを使用してセッションを停止します。</span><span class="sxs-lookup"><span data-stu-id="f0136-194">Once you no longer need the Spark session, use the [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) method to stop your session.</span></span>

### <a name="4-create-data-file"></a><span data-ttu-id="f0136-195">4.データ ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="f0136-195">4. Create data file</span></span>

<span data-ttu-id="f0136-196">アプリでは、テキスト行を含むファイルが処理されます。</span><span class="sxs-lookup"><span data-stu-id="f0136-196">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="f0136-197">*MySparkApp* ディレクトリに、次のテキストを含む *input.txt* という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0136-197">Create a file called *input.txt* file in your *MySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

<span data-ttu-id="f0136-198">変更を保存してファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f0136-198">Save the changes and close the file.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="f0136-199">.NET for Apache Spark アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="f0136-199">Run your .NET for Apache Spark app</span></span>

<span data-ttu-id="f0136-200">次のコマンドを実行して、アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="f0136-200">Run the following command to build your application:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="f0136-201">ビルドの出力ディレクトリに移動し、`spark-submit` コマンドを使用して、Apache Spark 上で実行するアプリケーションを送信します。</span><span class="sxs-lookup"><span data-stu-id="f0136-201">Navigate to your build output directory and use the `spark-submit` command to submit your application to run on Apache Spark.</span></span> <span data-ttu-id="f0136-202">`<version>` を使用する .NET ワーカーのバージョンに、`<path-of-input.txt>` を *input.txt* ファイルが格納されているパスに置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="f0136-202">Make sure to replace  `<version>` with the version of your .NET worker and `<path-of-input.txt>` with the path of your *input.txt* file is stored.</span></span>

### <a name="windows"></a>[<span data-ttu-id="f0136-203">Windows</span><span class="sxs-lookup"><span data-stu-id="f0136-203">Windows</span></span>](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-2.4.x-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[<span data-ttu-id="f0136-204">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="f0136-204">Mac/Linux</span></span>](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-2.4.x-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> <span data-ttu-id="f0136-205">このコマンドは、Apache Spark をダウンロードして PATH 環境変数に追加し、`spark-submit` を使用できる状態であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f0136-205">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="f0136-206">そうでなければ、完全なパスを使用する必要があります (たとえば、*C:\bin\apache-spark\bin\spark-submit* や *~/spark/bin/spark-submit*)。</span><span class="sxs-lookup"><span data-stu-id="f0136-206">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

<span data-ttu-id="f0136-207">アプリを実行すると、*input.txt* ファイルのワード カウント データがコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f0136-207">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

<span data-ttu-id="f0136-208">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="f0136-208">Congratulations!</span></span> <span data-ttu-id="f0136-209">.NET for Apache Spark アプリの作成と実行が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="f0136-209">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0136-210">次の手順</span><span class="sxs-lookup"><span data-stu-id="f0136-210">Next steps</span></span>

<span data-ttu-id="f0136-211">このチュートリアルでは、以下の内容を学習しました。</span><span class="sxs-lookup"><span data-stu-id="f0136-211">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="f0136-212">.NET for Apache Spark の環境を準備する</span><span class="sxs-lookup"><span data-stu-id="f0136-212">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="f0136-213">最初の .NET for Apache Spark アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="f0136-213">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="f0136-214">.NET for Apache Spark アプリケーションをビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="f0136-214">Build and run your .NET for Apache Spark application</span></span>

<span data-ttu-id="f0136-215">上記の手順を説明したビデオを見るには、[.NET for Apache Spark 101 ビデオ シリーズ](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0136-215">To see a video explaining the steps above, check out the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="f0136-216">詳細については、リソースのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0136-216">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f0136-217">.NET for Apache Spark のリソース</span><span class="sxs-lookup"><span data-stu-id="f0136-217">.NET for Apache Spark Resources</span></span>](../resources/index.md)
