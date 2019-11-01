---
title: .NET for Apache Spark の概要
description: Windows で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 19efc8412d834d73069c61e1cc1ccd9e5eb8593b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774377"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="0a61e-103">チュートリアル: .NET for Apache Spark の概要</span><span class="sxs-lookup"><span data-stu-id="0a61e-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="0a61e-104">このチュートリアルでは、Windows で .NET Core を使用して .NET for Apache Spark アプリを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="0a61e-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="0a61e-106">.NET for Apache Spark 用に Windows 環境を準備する</span><span class="sxs-lookup"><span data-stu-id="0a61e-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0a61e-107">**Microsoft.Spark.Worker** をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0a61e-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0a61e-108">.NET for Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="0a61e-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="0a61e-109">環境を準備する</span><span class="sxs-lookup"><span data-stu-id="0a61e-109">Prepare your environment</span></span>

<span data-ttu-id="0a61e-110">開始する前に、コマンド ラインから `dotnet`、`java`、`mvn`、`spark-shell` を実行できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a61e-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="0a61e-111">環境が既に準備されている場合は、次のセクションに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="0a61e-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="0a61e-112">コマンドのいずれかまたはすべてを実行できない場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0a61e-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="0a61e-113">[.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="0a61e-114">SDK をインストールすると、`dotnet` ツールチェーンが PATH に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0a61e-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="0a61e-115">PowerShell コマンド `dotnet --version` を使用して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="0a61e-116">最新の更新プログラムを使用して、[Visual Studio 2017](https://www.visualstudio.com/downloads/) または [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="0a61e-117">Community、Professional、Enterprise のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a61e-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="0a61e-118">Community バージョンは無料です。</span><span class="sxs-lookup"><span data-stu-id="0a61e-118">The Community version is free.</span></span>

   <span data-ttu-id="0a61e-119">インストール時に次のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="0a61e-120">.NET デスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="0a61e-120">.NET desktop development</span></span>
          * <span data-ttu-id="0a61e-121">すべての必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a61e-121">All required components</span></span>
          * <span data-ttu-id="0a61e-122">.NET Framework 4.6.1 開発ツール</span><span class="sxs-lookup"><span data-stu-id="0a61e-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="0a61e-123">.NET Core クロスプラットフォームの開発</span><span class="sxs-lookup"><span data-stu-id="0a61e-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="0a61e-124">すべての必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a61e-124">All required components</span></span>

3. <span data-ttu-id="0a61e-125">[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="0a61e-126">ご使用のオペレーティング システムに適したバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="0a61e-127">たとえば、Windows x64 マシンには、**jdk-8u201-windows-x64.exe** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="0a61e-128">PowerShell コマンド `java -version` を使用して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="0a61e-129">[Apache Maven 3.6.0 以降](https://maven.apache.org/download.cgi)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="0a61e-130">[Apache Maven 3.6.2](http://mirror.metrocast.net/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.zip) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-130">Download [Apache Maven 3.6.2](http://mirror.metrocast.net/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.zip).</span></span>
    * <span data-ttu-id="0a61e-131">ローカル ディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-131">Extract to a local directory.</span></span> <span data-ttu-id="0a61e-132">たとえば、`c:\bin\apache-maven-3.6.2\` のようにします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-132">For example, `c:\bin\apache-maven-3.6.2\`.</span></span>
    * <span data-ttu-id="0a61e-133">Apache Maven をご自分の [PATH 環境変数](https://www.java.com/en/download/help/path.xml)に追加します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0a61e-134">`c:\bin\apache-maven-3.6.2\` に抽出した場合は、`c:\bin\apache-maven-3.6.2\bin` を PATH に追加します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-134">If you extracted to `c:\bin\apache-maven-3.6.2\`, you would add `c:\bin\apache-maven-3.6.2\bin` to your PATH.</span></span>
    * <span data-ttu-id="0a61e-135">PowerShell コマンド `mvn -version` を使用して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="0a61e-136">[Apache Spark 2.3 以降](https://spark.apache.org/downloads.html)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="0a61e-137">Apache Spark 2.4 以降はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0a61e-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="0a61e-138">[Apache Spark 2.3 以降](https://spark.apache.org/downloads.html)をダウンロードし、[7-zip](https://www.7-zip.org/) や [WinZip](https://www.winzip.com/) などのツールを使用してローカル フォルダーに抽出します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="0a61e-139">たとえば、`c:\bin\spark-2.3.2-bin-hadoop2.7\` に抽出します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="0a61e-140">Apache Spark をご自分の [PATH 環境変数](https://www.java.com/en/download/help/path.xml)に追加します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0a61e-141">`c:\bin\spark-2.3.2-bin-hadoop2.7\` に抽出した場合は、`c:\bin\spark-2.3.2-bin-hadoop2.7\bin` を PATH に追加します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="0a61e-142">`SPARK_HOME` という[新しい環境変数](https://www.java.com/en/download/help/path.xml)を追加します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="0a61e-143">`C:\bin\spark-2.3.2-bin-hadoop2.7\` に抽出した場合は、**変数値**に `C:\bin\spark-2.3.2-bin-hadoop2.7\` を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="0a61e-144">コマンド ラインから `spark-shell` を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="0a61e-145">[WinUtils](https://github.com/steveloughran/winutils) を設定します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="0a61e-146">[Winutils リポジトリ](https://github.com/steveloughran/winutils)から **winutils.exe** バイナリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="0a61e-147">Spark ディストリビューションをコンパイルした Hadoop のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="0a61e-148">たとえば、**Spark 2.3.2** には **hadoop-2.7.1** を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="0a61e-149">Hadoop のバージョンは、Spark インストール フォルダー名の末尾に注釈付けされています。</span><span class="sxs-lookup"><span data-stu-id="0a61e-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="0a61e-150">**winutils.exe** バイナリを任意のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="0a61e-151">たとえば、`c:\hadoop\bin` のようにします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="0a61e-152">**winutils.exe** 含むディレクトリを反映するように、`bin` なしで `HADOOP_HOME` を設定します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="0a61e-153">たとえば、`c:\hadoop` のようにします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="0a61e-154">`%HADOOP_HOME%\bin` が含まれるように PATH 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="0a61e-155">次のセクションに進む前に、コマンド ラインから `dotnet`、`java`、`mvn`、`spark-shell` を実行できることを再度確認します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="0a61e-156">Microsoft.Spark.Worker リリースをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0a61e-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="0a61e-157">.NET for Apache Spark GitHub リリース ページから、[Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) リリースをローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="0a61e-158">たとえば、`c:\bin\Microsoft.Spark.Worker\` というパスにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0a61e-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="0a61e-159">`DOTNET_WORKER_DIR` という名前の[新しい環境変数](https://www.java.com/en/download/help/path.xml)を作成し、**Microsoft.Spark.Worker** をダウンロードして抽出したディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="0a61e-160">たとえば、`c:\bin\Microsoft.Spark.Worker` のようにします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="0a61e-161">.NET for Apache Spark GitHub リポジトリの複製</span><span class="sxs-lookup"><span data-stu-id="0a61e-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="0a61e-162">次の [GitBash](https://gitforwindows.org/) コマンドを使用して、.NET for Apache Spark リポジトリをご使用のマシンに複製します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="0a61e-163">.NET for Apache Spark アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="0a61e-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0a61e-164">**Visual Studio** を開き、 **[ファイル]、[新しいプロジェクトの作成]、[コンソール アプリ (.NET Core)]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="0a61e-165">アプリケーションに「**HelloSpark**」という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="0a61e-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="0a61e-166">[Microsoft.Spark NuGet パッケージ](https://www.nuget.org/profiles/spark)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="0a61e-167">Nuget パッケージのインストールの詳細については、[NuGet パッケージをインストールするためのさまざまな方法](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a61e-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="0a61e-168">**ソリューション エクスプローラー**で、**Program.cs** を開き、次の C# コードを記述します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="0a61e-169">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="0a61e-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="0a61e-170">.NET for Apache Spark アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="0a61e-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0a61e-171">**PowerShell** を開き、ディレクトリを、アプリが格納されているフォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="0a61e-172">次の内容を含む **people.json** という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="0a61e-173">次の PowerShell コマンドを使用して、アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="0a61e-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="0a61e-174">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="0a61e-174">Congratulations!</span></span> <span data-ttu-id="0a61e-175">.NET for Apache Spark アプリの作成と実行が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="0a61e-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0a61e-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="0a61e-176">Next steps</span></span>

<span data-ttu-id="0a61e-177">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="0a61e-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="0a61e-178">.NET for Apache Spark 用に Windows 環境を準備する</span><span class="sxs-lookup"><span data-stu-id="0a61e-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0a61e-179">**Microsoft.Spark.Worker** をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="0a61e-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0a61e-180">.NET for Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="0a61e-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="0a61e-181">詳細については、リソースのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a61e-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0a61e-182">.NET for Apache Spark のリソース</span><span class="sxs-lookup"><span data-stu-id="0a61e-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
