---
title: Apache Spark 用 .NET の概要
description: Windows で .NET Core を使用して Apache Spark アプリ用 .NET を実行する方法について説明します。
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577009"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="65cda-103">チュートリアル:Apache Spark 用 .NET の概要</span><span class="sxs-lookup"><span data-stu-id="65cda-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="65cda-104">このチュートリアルでは、Windows で .NET Core を使用して Apache Spark アプリ用の .NET を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65cda-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="65cda-105">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65cda-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="65cda-106">Apache Spark 用に .NET 用の Windows 環境を準備する</span><span class="sxs-lookup"><span data-stu-id="65cda-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="65cda-107">**Microsoft Spark**をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65cda-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="65cda-108">Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="65cda-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="65cda-109">環境を準備する</span><span class="sxs-lookup"><span data-stu-id="65cda-109">Prepare your environment</span></span>

<span data-ttu-id="65cda-110">開始する前に、コマンドラインから、 `dotnet`、 `java` `mvn`、 `spark-shell`を実行できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cda-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="65cda-111">環境が既に準備されている場合は、次のセクションに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="65cda-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="65cda-112">コマンドのいずれかまたはすべてを実行できない場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="65cda-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="65cda-113">[.Net Core 2.1 x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="65cda-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="65cda-114">SDK をインストールすると`dotnet` 、ツールチェーンがパスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="65cda-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="65cda-115">PowerShell コマンド`dotnet --version`を使用して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cda-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="65cda-116">最新の更新プログラムを使用して、 [Visual studio 2017](https://www.visualstudio.com/downloads/)または[visual studio 2019](https://visualstudio.microsoft.com/vs/preview/)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="65cda-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="65cda-117">Community、Professional、または Enterprise を使用できます。</span><span class="sxs-lookup"><span data-stu-id="65cda-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="65cda-118">コミュニティのバージョンは無料です。</span><span class="sxs-lookup"><span data-stu-id="65cda-118">The Community version is free.</span></span>

   <span data-ttu-id="65cda-119">インストール中に次のワークロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="65cda-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="65cda-120">.NET デスクトップ開発</span><span class="sxs-lookup"><span data-stu-id="65cda-120">.NET desktop development</span></span>
          * <span data-ttu-id="65cda-121">すべての必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="65cda-121">All required components</span></span>
          * <span data-ttu-id="65cda-122">.NET Framework 4.6.1 開発ツール</span><span class="sxs-lookup"><span data-stu-id="65cda-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="65cda-123">.NET Core クロスプラットフォームの開発</span><span class="sxs-lookup"><span data-stu-id="65cda-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="65cda-124">すべての必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="65cda-124">All required components</span></span>

3. <span data-ttu-id="65cda-125">[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="65cda-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="65cda-126">オペレーティングシステムに適したバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="65cda-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="65cda-127">たとえば、Windows x64 コンピューターの場合は、 **jdk-8u201-windows-x64**を選択します。</span><span class="sxs-lookup"><span data-stu-id="65cda-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="65cda-128">PowerShell コマンド`java -version`を使用して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cda-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="65cda-129">[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="65cda-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="65cda-130">[Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65cda-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="65cda-131">ローカルディレクトリに抽出します。</span><span class="sxs-lookup"><span data-stu-id="65cda-131">Extract to a local directory.</span></span> <span data-ttu-id="65cda-132">たとえば、`c:\bin\apache-maven-3.6.0\` のようにします。</span><span class="sxs-lookup"><span data-stu-id="65cda-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="65cda-133">Apache Maven を[PATH 環境変数](https://www.java.com/en/download/help/path.xml)に追加します。</span><span class="sxs-lookup"><span data-stu-id="65cda-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="65cda-134">に`c:\bin\apache-maven-3.6.0\`抽出した場合は、を`c:\bin\apache-maven-3.6.0\bin`パスに追加します。</span><span class="sxs-lookup"><span data-stu-id="65cda-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="65cda-135">PowerShell コマンド`mvn -version`を使用して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cda-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="65cda-136">[Apache Spark 2.3 以降](https://spark.apache.org/downloads.html)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="65cda-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="65cda-137">Apache Spark 2.4 以降はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65cda-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="65cda-138">[Apache Spark 2.3](https://spark.apache.org/downloads.html)以降をダウンロードし、 [7-zip](https://www.7-zip.org/)や[WinZip](https://www.winzip.com/)などのツールを使用してローカルフォルダーに抽出します。</span><span class="sxs-lookup"><span data-stu-id="65cda-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="65cda-139">たとえば、に`c:\bin\spark-2.3.2-bin-hadoop2.7\`抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="65cda-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="65cda-140">[PATH 環境変数](https://www.java.com/en/download/help/path.xml)に Apache Spark を追加します。</span><span class="sxs-lookup"><span data-stu-id="65cda-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="65cda-141">に`c:\bin\spark-2.3.2-bin-hadoop2.7\`抽出した場合は、を`c:\bin\spark-2.3.2-bin-hadoop2.7\bin`パスに追加します。</span><span class="sxs-lookup"><span data-stu-id="65cda-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="65cda-142">という名前`SPARK_HOME`の[新しい環境変数](https://www.java.com/en/download/help/path.xml)を追加します。</span><span class="sxs-lookup"><span data-stu-id="65cda-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="65cda-143">に`C:\bin\spark-2.3.2-bin-hadoop2.7\`抽出した場合は`C:\bin\spark-2.3.2-bin-hadoop2.7\` 、変数の**値**にを使用します。</span><span class="sxs-lookup"><span data-stu-id="65cda-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="65cda-144">コマンドラインから実行`spark-shell`できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cda-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="65cda-145">[Winutils](https://github.com/steveloughran/winutils)をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="65cda-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="65cda-146">Winutils [リポジトリ](https://github.com/steveloughran/winutils)から winutils バイナリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65cda-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="65cda-147">Spark ディストリビューションがコンパイルされた Hadoop のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="65cda-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="65cda-148">たとえば、 **Spark 2.3.2**には**2.7.1**を使用します。</span><span class="sxs-lookup"><span data-stu-id="65cda-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="65cda-149">Hadoop のバージョンは、Spark インストールフォルダー名の最後に注釈が付けられます。</span><span class="sxs-lookup"><span data-stu-id="65cda-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="65cda-150">Winutilsバイナリを任意のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="65cda-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="65cda-151">たとえば、`c:\hadoop\bin` のようにします。</span><span class="sxs-lookup"><span data-stu-id="65cda-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="65cda-152">を`HADOOP_HOME`指定せず`bin`に、 **winutils**を含むディレクトリを反映するように設定します。</span><span class="sxs-lookup"><span data-stu-id="65cda-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="65cda-153">たとえば、`c:\hadoop` のようにします。</span><span class="sxs-lookup"><span data-stu-id="65cda-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="65cda-154">PATH 環境変数を含める`%HADOOP_HOME%\bin`ように設定します。</span><span class="sxs-lookup"><span data-stu-id="65cda-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="65cda-155">次のセクションに進む前`dotnet`に、 `mvn`コマンド`spark-shell`ラインから、、を実行`java`できることを再度確認します。</span><span class="sxs-lookup"><span data-stu-id="65cda-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="65cda-156">Microsoft の Spark. ワーカーリリースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="65cda-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="65cda-157">.NET for Apache Spark GitHub リリースページからローカルコンピューターに、 [Microsoft Spark. ワーカー](https://github.com/dotnet/spark/releases)リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65cda-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="65cda-158">たとえば、というパス`c:\bin\Microsoft.Spark.Worker\`にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="65cda-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="65cda-159">という名前`DotnetWorkerPath`の[新しい環境変数](https://www.java.com/en/download/help/path.xml)を作成し、これをダウンロードして、 **Microsoft の Spark**を展開したディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="65cda-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="65cda-160">たとえば、`c:\bin\Microsoft.Spark.Worker` のようにします。</span><span class="sxs-lookup"><span data-stu-id="65cda-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="65cda-161">Apache Spark GitHub リポジトリ用の .NET の複製</span><span class="sxs-lookup"><span data-stu-id="65cda-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="65cda-162">次の[GitBash](https://gitforwindows.org/)コマンドを使用して、Apache Spark リポジトリ用の .net をコンピューターに複製します。</span><span class="sxs-lookup"><span data-stu-id="65cda-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="65cda-163">Apache Spark アプリ用の .NET を作成する</span><span class="sxs-lookup"><span data-stu-id="65cda-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="65cda-164">**Visual Studio**を開き、**ファイル > 新しいプロジェクトの作成 > コンソールアプリ (.net Core)** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="65cda-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="65cda-165">アプリケーションに**HelloSpark**という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="65cda-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="65cda-166">[Microsoft Spark NuGet パッケージ](https://www.nuget.org/profiles/spark)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="65cda-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="65cda-167">NuGet パッケージのインストールの詳細については、「 [Nuget パッケージをインストールするさまざまな方法](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cda-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="65cda-168">**ソリューションエクスプローラー**で、 **Program.cs**を開き、次C#のコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="65cda-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="65cda-169">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="65cda-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="65cda-170">.NET for Apache Spark アプリを実行する</span><span class="sxs-lookup"><span data-stu-id="65cda-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="65cda-171">**PowerShell**を開き、ディレクトリをアプリが格納されているフォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="65cda-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="65cda-172">次の内容を使用して、" **people. json** " という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="65cda-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="65cda-173">次の PowerShell コマンドを使用して、アプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="65cda-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="65cda-174">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="65cda-174">Congratulations!</span></span> <span data-ttu-id="65cda-175">Apache Spark アプリ用の .NET の作成と実行が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="65cda-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="65cda-176">次の手順</span><span class="sxs-lookup"><span data-stu-id="65cda-176">Next steps</span></span>

<span data-ttu-id="65cda-177">このチュートリアルでは、次の作業を行う方法を学びました。</span><span class="sxs-lookup"><span data-stu-id="65cda-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="65cda-178">Apache Spark 用に .NET 用の Windows 環境を準備する</span><span class="sxs-lookup"><span data-stu-id="65cda-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="65cda-179">**Microsoft Spark**をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65cda-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="65cda-180">Apache Spark アプリケーション用の単純な .NET をビルドして実行する</span><span class="sxs-lookup"><span data-stu-id="65cda-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="65cda-181">詳細については、「リソース」ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cda-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="65cda-182">Apache Spark リソース用 .NET</span><span class="sxs-lookup"><span data-stu-id="65cda-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
