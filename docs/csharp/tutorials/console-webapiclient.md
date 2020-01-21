---
title: .NET Core を使用した REST クライアントの作成
description: このチュートリアルでは、.NET Core と C# 言語のさまざまな機能を説明します。
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 85a3c8e17e14db86786950380ba745ae286dccca
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115873"
---
# <a name="rest-client"></a><span data-ttu-id="d7d43-103">REST クライアント</span><span class="sxs-lookup"><span data-stu-id="d7d43-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="d7d43-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="d7d43-104">Introduction</span></span>

<span data-ttu-id="d7d43-105">このチュートリアルでは、.NET Core と C# 言語のさまざまな機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="d7d43-106">内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7d43-106">You’ll learn:</span></span>

* <span data-ttu-id="d7d43-107">.NET Core コマンド ライン インターフェイス (CLI) の基本</span><span class="sxs-lookup"><span data-stu-id="d7d43-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="d7d43-108">C# 言語機能の概要</span><span class="sxs-lookup"><span data-stu-id="d7d43-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="d7d43-109">NuGet での依存関係の管理</span><span class="sxs-lookup"><span data-stu-id="d7d43-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="d7d43-110">HTTP 通信</span><span class="sxs-lookup"><span data-stu-id="d7d43-110">HTTP Communications</span></span>
* <span data-ttu-id="d7d43-111">JSON 情報の処理</span><span class="sxs-lookup"><span data-stu-id="d7d43-111">Processing JSON information</span></span>
* <span data-ttu-id="d7d43-112">属性を使用した構成の管理</span><span class="sxs-lookup"><span data-stu-id="d7d43-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="d7d43-113">GitHub 上の REST サービスに対して HTTP 要求を発行するアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d7d43-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="d7d43-114">JSON 形式で情報を読み取り、その JSON パケットを C# オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="d7d43-115">最後に、C# オブジェクトを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="d7d43-116">このチュートリアルには、多くの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d7d43-116">There are many features in this tutorial.</span></span> <span data-ttu-id="d7d43-117">それらを 1 つずつビルドしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="d7d43-117">Let’s build them one by one.</span></span>

<span data-ttu-id="d7d43-118">このトピックの[最終的なサンプル](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)も参照したい方は、ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="d7d43-119">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d7d43-120">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d7d43-120">Prerequisites</span></span>

<span data-ttu-id="d7d43-121">お使いのコンピューターを、.NET Core が実行されるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="d7d43-122">インストールの手順については、[.NET Core のダウンロード](https://dotnet.microsoft.com/download) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-122">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="d7d43-123">このアプリケーションは、Windows、Linux、macOS または Docker コンテナーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="d7d43-124">お好みのコード エディターをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="d7d43-125">次の説明では、オープン ソースのクロス プラットフォーム エディターである [Visual Studio Code](https://code.visualstudio.com/) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d7d43-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="d7d43-126">しかし、他の使い慣れたツールを使用しても構いません。</span><span class="sxs-lookup"><span data-stu-id="d7d43-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="d7d43-127">アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="d7d43-127">Create the Application</span></span>

<span data-ttu-id="d7d43-128">最初に新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-128">The first step is to create a new application.</span></span> <span data-ttu-id="d7d43-129">コマンド プロンプトを開き、アプリケーション用の新しいディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="d7d43-130">それを、現在のディレクトリとしてください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-130">Make that the current directory.</span></span> <span data-ttu-id="d7d43-131">コンソール ウィンドウに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-131">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="d7d43-132">これで、基本的な "Hello World" アプリケーションのスターター ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="d7d43-133">プロジェクト名は "WebApiClient" です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-133">The project name is "WebApiClient".</span></span> <span data-ttu-id="d7d43-134">これは新しいプロジェクトであるため、依存関係はありません。</span><span class="sxs-lookup"><span data-stu-id="d7d43-134">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="d7d43-135">1 回目の実行では、.NET Core フレームワークがダウンロードされ、開発証明書がインストールされ、NuGet パッケージ マネージャーが実行されて、不足している依存関係が復元されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-135">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="d7d43-136">変更を開始する前に、コマンド プロンプトに「`dotnet run`」(「[注](#dotnet-restore-note)」を参照してください) と入力してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-136">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="d7d43-137">環境に依存関係がない場合、`dotnet run` では自動的に `dotnet restore` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-137">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="d7d43-138">アプリケーションのリビルドが必要な場合にも `dotnet build` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-138">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="d7d43-139">初期設定の後は、プロジェクトにとって意味がある場合にのみ `dotnet restore` または `dotnet build` を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-139">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="d7d43-140">新しい依存関係を追加する</span><span class="sxs-lookup"><span data-stu-id="d7d43-140">Adding New Dependencies</span></span>

<span data-ttu-id="d7d43-141">.NET Core の重要な設計目標の 1 つは、.NET インストール サイズを最小限に抑えることです。</span><span class="sxs-lookup"><span data-stu-id="d7d43-141">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="d7d43-142">その一部の機能のための追加ライブラリがアプリケーションで必要な場合は、C# プロジェクト (\*.csproj) ファイルにそれらの依存関係を追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-142">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="d7d43-143">ここで示す例の場合は、`System.Runtime.Serialization.Json` パッケージを追加して、アプリケーションが JSON 応答を処理できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-143">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="d7d43-144">このアプリケーションには、`System.Runtime.Serialization.Json` パッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-144">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="d7d43-145">次の [.NET CLI](../../core/tools/dotnet-add-package.md) コマンドを実行して、それをご自身のプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-145">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```console
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="d7d43-146">Web 要求を作成する</span><span class="sxs-lookup"><span data-stu-id="d7d43-146">Making Web Requests</span></span>

<span data-ttu-id="d7d43-147">Web サイトからデータの取得を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="d7d43-147">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="d7d43-148">このアプリケーションでは、[GitHub API](https://developer.github.com/v3/) から情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-148">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="d7d43-149">[.NET Foundation](https://www.dotnetfoundation.org/) にあるプロジェクトに関する情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-149">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="d7d43-150">最初に、プロジェクトに関する情報を取得する GitHub API に対する要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-150">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="d7d43-151">使用するエンドポイントは <https://api.github.com/orgs/dotnet/repos> です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-151">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="d7d43-152">HTTP GET 要求を使用して、これらのプロジェクトに関する情報をすべて取得します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-152">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="d7d43-153">HTTP GET 要求はブラウザーでも使用されるので、ブラウザーに URL を貼り付けて、取得および処理する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-153">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="d7d43-154"><xref:System.Net.Http.HttpClient> クラスを使用して Web 要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-154">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="d7d43-155">最新のすべての .NET API と同様に、<xref:System.Net.Http.HttpClient> は実行時間の長い API の非同期メソッドだけをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d7d43-155">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="d7d43-156">最初に非同期メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-156">Start by making an async method.</span></span> <span data-ttu-id="d7d43-157">アプリケーションの機能をビルドする際に実装を記述します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-157">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="d7d43-158">最初に、プロジェクト ディレクトリ内の `program.cs` ファイルを開き、`Program` クラスに次のメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-158">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="d7d43-159">`Main` メソッドの先頭に `using` ステートメントを追加して、C# コンパイラに <xref:System.Threading.Tasks.Task> 型を認識させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-159">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="d7d43-160">この時点でプロジェクトをビルドすると、このメソッドに対して警告が生成されます。これは、`await` 演算子がメソッドに含まれておらず、メソッドが同期的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="d7d43-160">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="d7d43-161">現時点ではこの警告を無視してください。`await` 演算子は、メソッドを記述する際に追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-161">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="d7d43-162">次に、`namespace` ステートメントに定義されている名前空間の名前を、既定値の `ConsoleApp` から `WebAPIClient` に変更します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-162">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="d7d43-163">後から、この名前空間で `repo` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-163">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="d7d43-164">次に、`Main` メソッドを更新してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-164">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="d7d43-165">`ProcessRepositories` メソッドはタスクを返します。そのタスクが完了する前にプログラムを終了しないでください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-165">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="d7d43-166">そのため、`Main` のシグネチャを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-166">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="d7d43-167">`async` 修飾子を追加し、戻り値の型を `Task` に変更します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-167">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="d7d43-168">次に、メソッドの本体で、呼び出しを `ProcessRepositories` に追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-168">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="d7d43-169">そのメソッド呼び出しに `await` キーワード when を追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-169">Add the `await` keyword when to that method call:</span></span>

```csharp
static Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="d7d43-170">これで、何も実行せず、非同期的に実行されるプログラムの準備ができました。</span><span class="sxs-lookup"><span data-stu-id="d7d43-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="d7d43-171">これを改善しましょう。</span><span class="sxs-lookup"><span data-stu-id="d7d43-171">Let's improve it.</span></span>

<span data-ttu-id="d7d43-172">まず、Web からデータを取得できるオブジェクトが必要です。この条件に合うものとして、<xref:System.Net.Http.HttpClient> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="d7d43-173">このオブジェクトは要求と応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-173">This object handles the request and the responses.</span></span> <span data-ttu-id="d7d43-174">Program.cs ファイル内の `Program` クラスで該当する型の単一のインスタンスをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-174">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="d7d43-175">`ProcessRepositories` メソッドに戻って、最初のバージョンのプログラムを記述します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="d7d43-176">また、ファイルの先頭に 2 つの新しい using ステートメントを追加して、プログラムをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-176">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="d7d43-177">この最初のバージョンでは、.NET Foundation にあるすべてのリポジトリのリストを読み取る Web 要求を作成します</span><span class="sxs-lookup"><span data-stu-id="d7d43-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="d7d43-178">(.NET Foundation の gitHub ID は "dotnet" です)。</span><span class="sxs-lookup"><span data-stu-id="d7d43-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="d7d43-179">最初の数行では、この要求の <xref:System.Net.Http.HttpClient> を設定します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="d7d43-180">最初は、GitHub の JSON 応答を受け入れるように構成されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="d7d43-181">この形式は単なる JSON です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-181">This format is simply JSON.</span></span> <span data-ttu-id="d7d43-182">次の行では、このオブジェクトからのすべての要求にユーザー エージェント ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="d7d43-183">これらの 2 つのヘッダーは、GitHub サーバー コードによってチェックされ、GitHub から情報を取得するために必要です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="d7d43-184"><xref:System.Net.Http.HttpClient> を構成したら、Web 要求を作成して応答を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="d7d43-185">この最初のバージョンでは、<xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 簡易メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="d7d43-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="d7d43-186">この簡易メソッドは、Web 要求を作成するタスクを開始し、要求が返されると応答ストリームを読み取って、ストリームからコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="d7d43-187">応答の本文は <xref:System.String> として返されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="d7d43-188">この文字列は、タスクが完了すると使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-188">The string is available when the task completes.</span></span>

<span data-ttu-id="d7d43-189">このメソッドの最後の 2 行は、そのタスクを待機し、コンソールに応答を出力します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="d7d43-190">アプリケーションをビルドして実行してください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-190">Build the app, and run it.</span></span> <span data-ttu-id="d7d43-191">`ProcessRepositories` に `await` 演算子が含まれているため、ビルドの警告が表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d7d43-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="d7d43-192">JSON 形式の長いテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="d7d43-193">JSON の結果を処理する</span><span class="sxs-lookup"><span data-stu-id="d7d43-193">Processing the JSON Result</span></span>

<span data-ttu-id="d7d43-194">この時点では、Web サーバーからの応答を取得し、その応答に含まれているテキストを表示するコードの記述が完了しています。</span><span class="sxs-lookup"><span data-stu-id="d7d43-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="d7d43-195">次に、JSON 応答を C# オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="d7d43-196"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> クラスは、オブジェクトを JSON にシリアル化し、JSON をオブジェクトに逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-196">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="d7d43-197">最初にクラスを定義して、GitHub API から返される `repo` JSON オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-197">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; };
    }
}
```

<span data-ttu-id="d7d43-198">"repo.cs" という新しいファイルに上記のコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-198">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="d7d43-199">このバージョンのクラスは、JSON データを処理する最もシンプルなパスを表します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-199">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="d7d43-200">クラス名とメンバー名は、C# の規約に従うのではなく、JSON パケットで使用される名前に一致します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-200">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="d7d43-201">後でいくつかの構成属性を指定して、これを修正します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-201">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="d7d43-202">このクラスは、JSON のシリアル化と逆シリアル化に関する、もう一つの重要な特性を示しています:JSON パケット内のすべてのフィールドがこのクラスの一部というわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d7d43-202">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="d7d43-203">JSON シリアライザーは、使用されているクラス型に含まれていない情報を無視します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-203">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="d7d43-204">この機能により、JSON パケット内のフィールドのサブセットのみを操作する型を容易に作成できます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-204">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="d7d43-205">型の作成が完了したら、逆シリアル化を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-205">Now that you've created the type, let's deserialize it.</span></span> 

<span data-ttu-id="d7d43-206">次に、シリアライザーを使用して、JSON を C# オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-206">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="d7d43-207">`ProcessRepositories` メソッド内の <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> の呼び出しを次の 3 行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-207">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following three lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="d7d43-208">新しい名前空間を使用しているため、ファイルの先頭にそれを追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-208">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="d7d43-209"><xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> ではなく、<xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> が使用されていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-209">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="d7d43-210">シリアライザーは、文字列の代わりにストリームをソースとして使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-210">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="d7d43-211">前のコード スニペットの 2 行目で使用されている C# 言語のいくつかの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-211">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="d7d43-212"><xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> への最初の引数は `await` 式です</span><span class="sxs-lookup"><span data-stu-id="d7d43-212">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="d7d43-213">(他の 2 つのパラメーターは省略可能で、このコード スニペットでは省略されています)。await 式は、コード内のほとんどの場所に表示される可能性があります (これまでは代入ステートメントの一部としてしか表示されていませんでした)。</span><span class="sxs-lookup"><span data-stu-id="d7d43-213">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="d7d43-214">`Deserialize` メソッドは "*ジェネリック*" です。つまり、JSON テキストから作成するオブジェクトの種類に対して型引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-214">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="d7d43-215">この例では、汎用オブジェクト <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> の 1 つである `List<Repository>` に逆シリアル化しています。</span><span class="sxs-lookup"><span data-stu-id="d7d43-215">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d7d43-216">`List<>` クラスには、オブジェクトのコレクションが格納されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-216">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="d7d43-217">型引数は、`List<>` に格納されているオブジェクトの型を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-217">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="d7d43-218">JSON テキストは、リポジトリ オブジェクトのコレクションを表しているため、型引数は `Repository` です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-218">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="d7d43-219">このセクションでの作業はほぼ完了です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-219">You're almost done with this section.</span></span> <span data-ttu-id="d7d43-220">JSON を C# オブジェクトに変換したので、次は各リポジトリの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-220">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="d7d43-221">次の行があるとします。</span><span class="sxs-lookup"><span data-stu-id="d7d43-221">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="d7d43-222">この行を次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-222">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="d7d43-223">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-223">Compile and run the application.</span></span> <span data-ttu-id="d7d43-224">.NET Foundation に含まれるリポジトリの名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-224">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="d7d43-225">シリアル化を制御する</span><span class="sxs-lookup"><span data-stu-id="d7d43-225">Controlling Serialization</span></span>

<span data-ttu-id="d7d43-226">機能を追加する前に、`[JsonPropertyName]` 属性を使用して `name` プロパティに対処しましょう。</span><span class="sxs-lookup"><span data-stu-id="d7d43-226">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="d7d43-227">repo.cs の `name` フィールドの宣言を次のように変更してください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-227">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="d7d43-228">この変更により、program.cs で各リポジトリの名前を記述するコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-228">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="d7d43-229">`dotnet run` を実行して、マッピングが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-229">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="d7d43-230">前と同じ出力が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d7d43-230">You should see the same output as before.</span></span>

<span data-ttu-id="d7d43-231">新機能を追加する前に、もう 1 つの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="d7d43-231">Let's make one more change before adding new features.</span></span> <span data-ttu-id="d7d43-232">`ProcessRepositories` メソッドは非同期作業を行って、リポジトリのコレクションを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-232">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="d7d43-233">そのメソッドから `List<Repository>` を返して、情報を記述するコードを `Main` メソッドに移動します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-233">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="d7d43-234">結果が `Repository` オブジェクトのリストであるタスクを返すように `ProcessRepositories` のシグネチャを変更します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-234">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="d7d43-235">続いて、JSON 応答の処理後にリポジトリを返します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-235">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="d7d43-236">このメソッドを `async` とマークしたので、コンパイラは戻り値として `Task<T>` オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-236">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="d7d43-237">次に、`Main` メソッドを変更して、それらの結果をキャプチャし、各リポジトリ名をコンソールに書き込むようにします。</span><span class="sxs-lookup"><span data-stu-id="d7d43-237">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="d7d43-238">`Main` メソッドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-238">Your `Main` method now looks like this:</span></span>

```csharp
public static Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="d7d43-239">詳細情報を確認する</span><span class="sxs-lookup"><span data-stu-id="d7d43-239">Reading More Information</span></span>

<span data-ttu-id="d7d43-240">最後に、GitHub API から送信される JSON パケット内のいくつかのプロパティを処理します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-240">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="d7d43-241">すべてのプロパティを追加する必要はありませんが、いくつかのプロパティを追加することで C# 言語のさらなる機能を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-241">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="d7d43-242">最初に、いくつかの単純型を `Repository` クラスの定義に追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-242">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="d7d43-243">そのクラスに次のプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-243">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName(Name="description")]
public string Description { get; set; }

[JsonPropertyName(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName(Name="homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="d7d43-244">これらのプロパティには、(JSON パケットに格納されている) 文字列型からターゲット型への組み込みの変換があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-244">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="d7d43-245"><xref:System.Uri> 型はおそらく初めて使用する型でしょう。</span><span class="sxs-lookup"><span data-stu-id="d7d43-245">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="d7d43-246">これは URI (ここでは URL) を表します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-246">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="d7d43-247">`Uri` 型と `int` 型では、ターゲット型に変換しないデータが JSON パケットに含まれている場合、シリアル化アクションで例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-247">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="d7d43-248">プロパティの追加が完了したら、それらの要素を表示するように `Main` メソッドを更新してください。</span><span class="sxs-lookup"><span data-stu-id="d7d43-248">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```

<span data-ttu-id="d7d43-249">最後の手順として、最後のプッシュ操作に関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-249">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="d7d43-250">この情報は、JSON 応答では次のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-250">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="d7d43-251">この形式は .NET の標準の <xref:System.DateTime> 形式に従っていません。</span><span class="sxs-lookup"><span data-stu-id="d7d43-251">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="d7d43-252">そのため、カスタムの変換メソッドを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-252">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="d7d43-253">また、`Repository` クラスのユーザーに公開されている未加工の文字列もおそらく不要でしょう。</span><span class="sxs-lookup"><span data-stu-id="d7d43-253">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="d7d43-254">この文字列も属性を使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-254">Attributes can help control that as well.</span></span> <span data-ttu-id="d7d43-255">最初に、日時の文字列表現を `Repository` クラスに保持する `public` プロパティと、返される日付を表す書式設定された文字列を返す `LastPush` `readonly` プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-255">First, define a `public` property that will hold the string representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns a formatted string that represents the returned date:</span></span>

```csharp
[JsonPropertyName(Name="pushed_at")]
public string JsonDate { get; set; }

public DateTime LastPush =>
    DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
```

<span data-ttu-id="d7d43-256">定義したばかりの新しいコンストラクトについて詳しく見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d7d43-256">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="d7d43-257">`LastPush` プロパティは、"*式形式のメンバー*" を使用して `get` アクセサーに対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="d7d43-257">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="d7d43-258">`set` アクセサーがない。</span><span class="sxs-lookup"><span data-stu-id="d7d43-258">There is no `set` accessor.</span></span> <span data-ttu-id="d7d43-259">C# では `set` アクセサーを省略することで "*読み取り専用*" プロパティを定義します</span><span class="sxs-lookup"><span data-stu-id="d7d43-259">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="d7d43-260">(C# では "*書き込み専用*" プロパティを作成できますが、その値は制限されています)。<xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> メソッドは、指定された日付形式を使用して文字列を解析し、<xref:System.DateTime> オブジェクトを作成します。次に、`CultureInfo` オブジェクトを使用して `DateTime` にメタデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="d7d43-260">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="d7d43-261">解析操作が失敗した場合、プロパティのアクセサーは例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="d7d43-261">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="d7d43-262"><xref:System.Globalization.CultureInfo.InvariantCulture> を使用するには、`repo.cs` 内の `using` ステートメントに <xref:System.Globalization> 名前空間を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d43-262">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="d7d43-263">最後に、コンソールで出力ステートメントをもう 1 つ追加すれば、このアプリケーションを再度ビルドして実行する準備は完了です。</span><span class="sxs-lookup"><span data-stu-id="d7d43-263">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="d7d43-264">以上で、作成してきたバージョンは[最終的なサンプル](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)と同じになるはずです。</span><span class="sxs-lookup"><span data-stu-id="d7d43-264">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="d7d43-265">まとめ</span><span class="sxs-lookup"><span data-stu-id="d7d43-265">Conclusion</span></span>

<span data-ttu-id="d7d43-266">このチュートリアルでは、Web 要求を作成する方法、結果を解析する方法、およびそれらの結果のプロパティを表示する方法を紹介しました。</span><span class="sxs-lookup"><span data-stu-id="d7d43-266">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="d7d43-267">また、依存関係として新しいパッケージをプロジェクトに追加しました。</span><span class="sxs-lookup"><span data-stu-id="d7d43-267">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="d7d43-268">さらに、オブジェクト指向の手法をサポートする C# 言語の一部の機能について確認しました。</span><span class="sxs-lookup"><span data-stu-id="d7d43-268">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
