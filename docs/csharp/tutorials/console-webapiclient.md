---
title: .NET Core を使用した REST クライアントの作成
description: このチュートリアルでは、.NET Core と C# 言語のさまざまな機能を説明します。
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 0105db519f7accec6bf8bfbafdc6a67a444b1074
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249169"
---
# <a name="rest-client"></a><span data-ttu-id="c2a82-103">REST クライアント</span><span class="sxs-lookup"><span data-stu-id="c2a82-103">REST client</span></span>

<span data-ttu-id="c2a82-104">このチュートリアルでは、.NET Core と C# 言語のさまざまな機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-104">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="c2a82-105">内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c2a82-105">You’ll learn:</span></span>

* <span data-ttu-id="c2a82-106">.NET Core CLI の基本事項。</span><span class="sxs-lookup"><span data-stu-id="c2a82-106">The basics of the .NET Core CLI.</span></span>
* <span data-ttu-id="c2a82-107">C# 言語機能の概要</span><span class="sxs-lookup"><span data-stu-id="c2a82-107">An overview of C# Language features.</span></span>
* <span data-ttu-id="c2a82-108">NuGet での依存関係の管理</span><span class="sxs-lookup"><span data-stu-id="c2a82-108">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="c2a82-109">HTTP 通信</span><span class="sxs-lookup"><span data-stu-id="c2a82-109">HTTP Communications</span></span>
* <span data-ttu-id="c2a82-110">JSON 情報の処理</span><span class="sxs-lookup"><span data-stu-id="c2a82-110">Processing JSON information</span></span>
* <span data-ttu-id="c2a82-111">属性を使用した構成の管理</span><span class="sxs-lookup"><span data-stu-id="c2a82-111">Managing configuration with Attributes.</span></span>

<span data-ttu-id="c2a82-112">GitHub 上の REST サービスに対して HTTP 要求を発行するアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="c2a82-112">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="c2a82-113">JSON 形式で情報を読み取り、その JSON パケットを C# オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-113">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="c2a82-114">最後に、C# オブジェクトを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-114">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="c2a82-115">このチュートリアルには、多くの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2a82-115">There are many features in this tutorial.</span></span> <span data-ttu-id="c2a82-116">それらを 1 つずつビルドしてみましょう。</span><span class="sxs-lookup"><span data-stu-id="c2a82-116">Let’s build them one by one.</span></span>

<span data-ttu-id="c2a82-117">このトピックの[最終的なサンプル](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)も参照したい方は、ダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-117">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="c2a82-118">ダウンロード方法については、「[サンプルおよびチュートリアル](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-118">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2a82-119">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c2a82-119">Prerequisites</span></span>

<span data-ttu-id="c2a82-120">お使いのコンピューターを、.NET Core が実行されるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-120">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="c2a82-121">インストールの手順については、[.NET Core のダウンロード](https://dotnet.microsoft.com/download) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-121">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="c2a82-122">このアプリケーションは、Windows、Linux、macOS または Docker コンテナーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-122">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="c2a82-123">お好みのコード エディターをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-123">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="c2a82-124">次の説明では、オープン ソースのクロス プラットフォーム エディターである [Visual Studio Code](https://code.visualstudio.com/) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="c2a82-124">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="c2a82-125">しかし、他の使い慣れたツールを使用しても構いません。</span><span class="sxs-lookup"><span data-stu-id="c2a82-125">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="c2a82-126">アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="c2a82-126">Create the Application</span></span>

<span data-ttu-id="c2a82-127">最初に新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-127">The first step is to create a new application.</span></span> <span data-ttu-id="c2a82-128">コマンド プロンプトを開き、アプリケーション用の新しいディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-128">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="c2a82-129">それを、現在のディレクトリとしてください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-129">Make that the current directory.</span></span> <span data-ttu-id="c2a82-130">コンソール ウィンドウに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-130">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="c2a82-131">これで、基本的な "Hello World" アプリケーションのスターター ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-131">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="c2a82-132">プロジェクト名は "WebApiClient" です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-132">The project name is "WebApiClient".</span></span> <span data-ttu-id="c2a82-133">これは新しいプロジェクトであるため、依存関係はありません。</span><span class="sxs-lookup"><span data-stu-id="c2a82-133">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="c2a82-134">1 回目の実行では、.NET Core フレームワークがダウンロードされ、開発証明書がインストールされ、NuGet パッケージ マネージャーが実行されて、不足している依存関係が復元されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-134">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="c2a82-135">変更を開始する前に、コマンド プロンプトに「`dotnet run`」(「[注](#dotnet-restore-note)」を参照してください) と入力してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-135">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="c2a82-136">環境に依存関係がない場合、`dotnet run` では自動的に `dotnet restore` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-136">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="c2a82-137">アプリケーションのリビルドが必要な場合にも `dotnet build` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-137">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="c2a82-138">初期設定の後は、プロジェクトにとって意味がある場合にのみ `dotnet restore` または `dotnet build` を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-138">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="c2a82-139">新しい依存関係を追加する</span><span class="sxs-lookup"><span data-stu-id="c2a82-139">Adding New Dependencies</span></span>

<span data-ttu-id="c2a82-140">.NET Core の重要な設計目標の 1 つは、.NET インストール サイズを最小限に抑えることです。</span><span class="sxs-lookup"><span data-stu-id="c2a82-140">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="c2a82-141">その一部の機能のための追加ライブラリがアプリケーションで必要な場合は、C# プロジェクト (\*.csproj) ファイルにそれらの依存関係を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-141">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="c2a82-142">ここで示す例の場合は、`System.Runtime.Serialization.Json` パッケージを追加して、アプリケーションが JSON 応答を処理できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-142">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="c2a82-143">このアプリケーションには、`System.Runtime.Serialization.Json` パッケージが必要です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-143">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="c2a82-144">次の [.NET CLI](../../core/tools/dotnet-add-package.md) コマンドを実行して、それをご自身のプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-144">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```dotnetcli
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="c2a82-145">Web 要求を作成する</span><span class="sxs-lookup"><span data-stu-id="c2a82-145">Making Web Requests</span></span>

<span data-ttu-id="c2a82-146">Web サイトからデータの取得を開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="c2a82-146">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="c2a82-147">このアプリケーションでは、[GitHub API](https://developer.github.com/v3/) から情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-147">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="c2a82-148">[.NET Foundation](https://www.dotnetfoundation.org/) にあるプロジェクトに関する情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-148">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="c2a82-149">最初に、プロジェクトに関する情報を取得する GitHub API に対する要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-149">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="c2a82-150">使用するエンドポイントは <https://api.github.com/orgs/dotnet/repos> です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-150">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="c2a82-151">HTTP GET 要求を使用して、これらのプロジェクトに関する情報をすべて取得します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-151">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="c2a82-152">HTTP GET 要求はブラウザーでも使用されるので、ブラウザーに URL を貼り付けて、取得および処理する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-152">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="c2a82-153"><xref:System.Net.Http.HttpClient> クラスを使用して Web 要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-153">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="c2a82-154">最新のすべての .NET API と同様に、<xref:System.Net.Http.HttpClient> は実行時間の長い API の非同期メソッドだけをサポートします。</span><span class="sxs-lookup"><span data-stu-id="c2a82-154">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="c2a82-155">最初に非同期メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-155">Start by making an async method.</span></span> <span data-ttu-id="c2a82-156">アプリケーションの機能をビルドする際に実装を記述します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-156">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="c2a82-157">最初に、プロジェクト ディレクトリ内の `program.cs` ファイルを開き、`Program` クラスに次のメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-157">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="c2a82-158">`Main` メソッドの先頭に `using` ディレクティブを追加して、C# コンパイラに <xref:System.Threading.Tasks.Task> 型を認識させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-158">You'll need to add a `using` directive at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="c2a82-159">この時点でプロジェクトをビルドすると、このメソッドに対して警告が生成されます。これは、`await` 演算子がメソッドに含まれておらず、メソッドが同期的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="c2a82-159">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="c2a82-160">現時点ではこの警告を無視してください。`await` 演算子は、メソッドを記述する際に追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-160">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="c2a82-161">次に、`namespace` ステートメントに定義されている名前空間の名前を、既定値の `ConsoleApp` から `WebAPIClient` に変更します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-161">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="c2a82-162">後から、この名前空間で `repo` クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-162">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="c2a82-163">次に、`Main` メソッドを更新してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-163">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="c2a82-164">`ProcessRepositories` メソッドはタスクを返します。そのタスクが完了する前にプログラムを終了しないでください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-164">The `ProcessRepositories` method returns a task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="c2a82-165">そのため、`Main` のシグネチャを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-165">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="c2a82-166">`async` 修飾子を追加し、戻り値の型を `Task` に変更します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-166">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="c2a82-167">次に、メソッドの本体で、呼び出しを `ProcessRepositories` に追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-167">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="c2a82-168">そのメソッド呼び出しに `await` キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-168">Add the `await` keyword to that method call:</span></span>

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="c2a82-169">これで、何も実行せず、非同期的に実行されるプログラムの準備ができました。</span><span class="sxs-lookup"><span data-stu-id="c2a82-169">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="c2a82-170">これを改善しましょう。</span><span class="sxs-lookup"><span data-stu-id="c2a82-170">Let's improve it.</span></span>

<span data-ttu-id="c2a82-171">まず、Web からデータを取得できるオブジェクトが必要です。この条件に合うものとして、<xref:System.Net.Http.HttpClient> を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-171">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="c2a82-172">このオブジェクトは要求と応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-172">This object handles the request and the responses.</span></span> <span data-ttu-id="c2a82-173">*Program.cs* ファイル内の `Program` クラスで該当する型の単一のインスタンスをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-173">Instantiate a single instance of that type in the `Program` class inside the *Program.cs* file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="c2a82-174">`ProcessRepositories` メソッドに戻って、最初のバージョンのプログラムを記述します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-174">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="c2a82-175">また、ファイルの先頭に 2 つの新しい `using` ディレクティブを追加して、プログラムをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-175">You'll need to also add two new `using` directives at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="c2a82-176">この最初のバージョンでは、.NET Foundation にあるすべてのリポジトリのリストを読み取る Web 要求を作成します</span><span class="sxs-lookup"><span data-stu-id="c2a82-176">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="c2a82-177">(.NET Foundation の GitHub ID は "dotnet" です)。</span><span class="sxs-lookup"><span data-stu-id="c2a82-177">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="c2a82-178">最初の数行では、この要求の <xref:System.Net.Http.HttpClient> を設定します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-178">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="c2a82-179">最初は、GitHub の JSON 応答を受け入れるように構成されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-179">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="c2a82-180">この形式は単なる JSON です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-180">This format is simply JSON.</span></span> <span data-ttu-id="c2a82-181">次の行では、このオブジェクトからのすべての要求にユーザー エージェント ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-181">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="c2a82-182">これらの 2 つのヘッダーは、GitHub サーバー コードによってチェックされ、GitHub から情報を取得するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-182">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="c2a82-183"><xref:System.Net.Http.HttpClient> を構成したら、Web 要求を作成して応答を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-183">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="c2a82-184">この最初のバージョンでは、<xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 簡易メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="c2a82-184">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="c2a82-185">この簡易メソッドは、Web 要求を作成するタスクを開始し、要求が返されると応答ストリームを読み取って、ストリームからコンテンツを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-185">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="c2a82-186">応答の本文は <xref:System.String> として返されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-186">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="c2a82-187">この文字列は、タスクが完了すると使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-187">The string is available when the task completes.</span></span>

<span data-ttu-id="c2a82-188">このメソッドの最後の 2 行は、そのタスクを待機し、コンソールに応答を出力します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-188">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="c2a82-189">アプリケーションをビルドして実行してください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-189">Build the app, and run it.</span></span> <span data-ttu-id="c2a82-190">`ProcessRepositories` に `await` 演算子が含まれているため、ビルドの警告が表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c2a82-190">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="c2a82-191">JSON 形式の長いテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-191">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="c2a82-192">JSON の結果を処理する</span><span class="sxs-lookup"><span data-stu-id="c2a82-192">Processing the JSON Result</span></span>

<span data-ttu-id="c2a82-193">この時点では、Web サーバーからの応答を取得し、その応答に含まれているテキストを表示するコードの記述が完了しています。</span><span class="sxs-lookup"><span data-stu-id="c2a82-193">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="c2a82-194">次に、JSON 応答を C# オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-194">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="c2a82-195"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> クラスは、オブジェクトを JSON にシリアル化し、JSON をオブジェクトに逆シリアル化します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-195">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="c2a82-196">最初にクラスを定義して、GitHub API から返される `repo` JSON オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-196">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; }
    }
}
```

<span data-ttu-id="c2a82-197">"repo.cs" という新しいファイルに上記のコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-197">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="c2a82-198">このバージョンのクラスは、JSON データを処理する最もシンプルなパスを表します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-198">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="c2a82-199">クラス名とメンバー名は、C# の規約に従うのではなく、JSON パケットで使用される名前に一致します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-199">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="c2a82-200">後でいくつかの構成属性を指定して、これを修正します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-200">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="c2a82-201">このクラスは、JSON のシリアル化と逆シリアル化に関する、もう一つの重要な特性を示しています:JSON パケット内のすべてのフィールドがこのクラスの一部というわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c2a82-201">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="c2a82-202">JSON シリアライザーは、使用されているクラス型に含まれていない情報を無視します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-202">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="c2a82-203">この機能により、JSON パケット内のフィールドのサブセットのみを操作する型を容易に作成できます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-203">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="c2a82-204">型の作成が完了したら、逆シリアル化を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-204">Now that you've created the type, let's deserialize it.</span></span>

<span data-ttu-id="c2a82-205">次に、シリアライザーを使用して、JSON を C# オブジェクトに変換します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-205">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="c2a82-206">`ProcessRepositories` メソッド内の <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> の呼び出しを、次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-206">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
```

<span data-ttu-id="c2a82-207">新しい名前空間を使用しているため、ファイルの先頭にそれを追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-207">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="c2a82-208"><xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> ではなく、<xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> が使用されていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-208">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="c2a82-209">シリアライザーは、文字列の代わりにストリームをソースとして使用します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-209">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="c2a82-210">前のコード スニペットの 2 行目で使用されている C# 言語のいくつかの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-210">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="c2a82-211"><xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> への最初の引数は `await` 式です</span><span class="sxs-lookup"><span data-stu-id="c2a82-211">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="c2a82-212">(他の 2 つのパラメーターは省略可能で、このコード スニペットでは省略されています)。await 式は、コード内のほとんどの場所に表示される可能性があります (これまでは代入ステートメントの一部としてしか表示されていませんでした)。</span><span class="sxs-lookup"><span data-stu-id="c2a82-212">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="c2a82-213">`Deserialize` メソッドは "*ジェネリック*" です。つまり、JSON テキストから作成するオブジェクトの種類に対して型引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-213">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="c2a82-214">この例では、汎用オブジェクト <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> の 1 つである `List<Repository>` に逆シリアル化しています。</span><span class="sxs-lookup"><span data-stu-id="c2a82-214">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c2a82-215">`List<>` クラスには、オブジェクトのコレクションが格納されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-215">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="c2a82-216">型引数は、`List<>` に格納されているオブジェクトの型を宣言します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-216">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="c2a82-217">JSON テキストは、リポジトリ オブジェクトのコレクションを表しているため、型引数は `Repository` です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-217">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="c2a82-218">このセクションでの作業はほぼ完了です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-218">You're almost done with this section.</span></span> <span data-ttu-id="c2a82-219">JSON を C# オブジェクトに変換したので、次は各リポジトリの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-219">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="c2a82-220">次の行があるとします。</span><span class="sxs-lookup"><span data-stu-id="c2a82-220">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="c2a82-221">この行を次の行に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-221">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="c2a82-222">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-222">Compile and run the application.</span></span> <span data-ttu-id="c2a82-223">.NET Foundation に含まれるリポジトリの名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-223">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="c2a82-224">シリアル化を制御する</span><span class="sxs-lookup"><span data-stu-id="c2a82-224">Controlling Serialization</span></span>

<span data-ttu-id="c2a82-225">機能を追加する前に、`[JsonPropertyName]` 属性を使用して `name` プロパティに対処しましょう。</span><span class="sxs-lookup"><span data-stu-id="c2a82-225">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="c2a82-226">repo.cs の `name` フィールドの宣言を次のように変更してください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-226">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="c2a82-227">`[JsonPropertyName]` 属性を使用するには、`using` ディレクティブに <xref:System.Text.Json.Serialization> 名前空間を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-227">To use `[JsonPropertyName]` attribute, you will need to add the <xref:System.Text.Json.Serialization> namespace to the `using` directives:</span></span>

```csharp
using System.Text.Json.Serialization;
```

<span data-ttu-id="c2a82-228">この変更により、program.cs で各リポジトリの名前を記述するコードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-228">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="c2a82-229">`dotnet run` を実行して、マッピングが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-229">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="c2a82-230">前と同じ出力が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="c2a82-230">You should see the same output as before.</span></span>

<span data-ttu-id="c2a82-231">新機能を追加する前に、もう 1 つの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="c2a82-231">Let's make one more change before adding new features.</span></span> <span data-ttu-id="c2a82-232">`ProcessRepositories` メソッドは非同期作業を行って、リポジトリのコレクションを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-232">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="c2a82-233">そのメソッドから `List<Repository>` を返して、情報を記述するコードを `Main` メソッドに移動します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-233">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="c2a82-234">結果が `Repository` オブジェクトのリストであるタスクを返すように `ProcessRepositories` のシグネチャを変更します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-234">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="c2a82-235">続いて、JSON 応答の処理後にリポジトリを返します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-235">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="c2a82-236">このメソッドを `async` とマークしたので、コンパイラは戻り値として `Task<T>` オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-236">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="c2a82-237">次に、`Main` メソッドを変更して、それらの結果をキャプチャし、各リポジトリ名をコンソールに書き込むようにします。</span><span class="sxs-lookup"><span data-stu-id="c2a82-237">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="c2a82-238">`Main` メソッドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-238">Your `Main` method now looks like this:</span></span>

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="c2a82-239">詳細情報を確認する</span><span class="sxs-lookup"><span data-stu-id="c2a82-239">Reading More Information</span></span>

<span data-ttu-id="c2a82-240">最後に、GitHub API から送信される JSON パケット内のいくつかのプロパティを処理します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-240">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="c2a82-241">すべてのプロパティを追加する必要はありませんが、いくつかのプロパティを追加することで C# 言語のさらなる機能を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-241">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="c2a82-242">最初に、いくつかの単純型を `Repository` クラスの定義に追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-242">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="c2a82-243">そのクラスに次のプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-243">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName("description")]
public string Description { get; set; }

[JsonPropertyName("html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName("homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName("watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="c2a82-244">これらのプロパティには、(JSON パケットに格納されている) 文字列型からターゲット型への組み込みの変換があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-244">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="c2a82-245"><xref:System.Uri> 型はおそらく初めて使用する型でしょう。</span><span class="sxs-lookup"><span data-stu-id="c2a82-245">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="c2a82-246">これは URI (ここでは URL) を表します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-246">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="c2a82-247">`Uri` 型と `int` 型では、ターゲット型に変換しないデータが JSON パケットに含まれている場合、シリアル化アクションで例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-247">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="c2a82-248">プロパティの追加が完了したら、それらの要素を表示するように `Main` メソッドを更新してください。</span><span class="sxs-lookup"><span data-stu-id="c2a82-248">Once you've added these, update the `Main` method to display those elements:</span></span>

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

<span data-ttu-id="c2a82-249">最後の手順として、最後のプッシュ操作に関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-249">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="c2a82-250">この情報は、JSON 応答では次のように書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-250">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="c2a82-251">この形式は協定世界時 (UTC) であるため、<xref:System.DateTime.Kind%2A> プロパティが <xref:System.DateTimeKind.Utc> である <xref:System.DateTime> 値が得られます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-251">That format is in Coordinated Universal Time (UTC) so you'll get a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc>.</span></span> <span data-ttu-id="c2a82-252">ご自分のタイム ゾーンで表される日付が必要な場合は、カスタムの変換メソッドを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2a82-252">If you prefer a date represented in your time zone, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="c2a82-253">最初に、日付と時刻の UTC 表現を `Repository` クラスに保持する `public` プロパティと、ローカル時刻に変換された日付を返す `LastPush` `readonly` プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c2a82-253">First, define a `public` property that will hold the UTC representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns the date converted to local time:</span></span>

```csharp
[JsonPropertyName("pushed_at")]
public DateTime LastPushUtc { get; set; }

public DateTime LastPush => LastPushUtc.ToLocalTime();
```

<span data-ttu-id="c2a82-254">定義したばかりの新しいコンストラクトについて詳しく見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="c2a82-254">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="c2a82-255">`LastPush` プロパティは、"*式形式のメンバー*" を使用して `get` アクセサーに対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="c2a82-255">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="c2a82-256">`set` アクセサーがない。</span><span class="sxs-lookup"><span data-stu-id="c2a82-256">There is no `set` accessor.</span></span> <span data-ttu-id="c2a82-257">C# では `set` アクセサーを省略することで "*読み取り専用*" プロパティを定義します</span><span class="sxs-lookup"><span data-stu-id="c2a82-257">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="c2a82-258">(C# では "*書き込み専用*" プロパティを作成できますが、その値は制限されています)。</span><span class="sxs-lookup"><span data-stu-id="c2a82-258">(Yes, you can create *write-only* properties in C#, but their value is limited.)</span></span>

<span data-ttu-id="c2a82-259">最後に、コンソールで出力ステートメントをもう 1 つ追加すれば、このアプリケーションを再度ビルドして実行する準備は完了です。</span><span class="sxs-lookup"><span data-stu-id="c2a82-259">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="c2a82-260">以上で、作成してきたバージョンは[最終的なサンプル](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)と同じになるはずです。</span><span class="sxs-lookup"><span data-stu-id="c2a82-260">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="c2a82-261">まとめ</span><span class="sxs-lookup"><span data-stu-id="c2a82-261">Conclusion</span></span>

<span data-ttu-id="c2a82-262">このチュートリアルでは、Web 要求を作成する方法、結果を解析する方法、およびそれらの結果のプロパティを表示する方法を紹介しました。</span><span class="sxs-lookup"><span data-stu-id="c2a82-262">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="c2a82-263">また、依存関係として新しいパッケージをプロジェクトに追加しました。</span><span class="sxs-lookup"><span data-stu-id="c2a82-263">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="c2a82-264">さらに、オブジェクト指向の手法をサポートする C# 言語の一部の機能について確認しました。</span><span class="sxs-lookup"><span data-stu-id="c2a82-264">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
