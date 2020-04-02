---
title: Docker を使用してアプリをコンテナー化するチュートリアル
description: このチュートリアルでは、Docker を使って .NET Core アプリケーションをコンテナー化する方法を学習します。
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 8be12792e4a9e8511dba87e657f700cc4ec97a16
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546576"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="e7c7f-103">チュートリアル: NET Core アプリのコンテナー化</span><span class="sxs-lookup"><span data-stu-id="e7c7f-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="e7c7f-104">このチュートリアルでは、.NET Core アプリケーションを含む Docker イメージをビルドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="e7c7f-105">そのイメージを使って、ローカル開発環境、プライベート クラウド、またはパブリック クラウド用にコンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="e7c7f-106">以下のことを学習します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="e7c7f-107">簡単な .NET Core アプリを作成して発行する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="e7c7f-108">.NET Core 用の Dockerfile を作成して構成する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="e7c7f-109">Docker イメージの構築</span><span class="sxs-lookup"><span data-stu-id="e7c7f-109">Build a Docker image</span></span>
> - <span data-ttu-id="e7c7f-110">Docker コンテナーを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-110">Create and run a Docker container</span></span>

<span data-ttu-id="e7c7f-111">.NET Core アプリケーション用に Docker コンテナーを構築してデプロイするタスクを理解できます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="e7c7f-112">"*Docker プラットフォーム*" では、"*Docker エンジン*" を使用して、すばやくアプリがビルドされ、"*Docker イメージ*" としてパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="e7c7f-113">これらのイメージは、階層型コンテナーに展開されて実行される *Dockerfile* 形式で記述されています。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!WARNING]
> <span data-ttu-id="e7c7f-114">**このチュートリアルは ASP.NET Core アプリ向けのものではありません。**</span><span class="sxs-lookup"><span data-stu-id="e7c7f-114">**This tutorial isn't for ASP.NET Core apps.**</span></span> <span data-ttu-id="e7c7f-115">ASP.NET Core を使用している場合は、[ASP.NET Core アプリケーションをコンテナー化する方法](/aspnet/core/host-and-deploy/docker/building-net-docker-images)に関するチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-115">If you're using ASP.NET Core, read the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7c7f-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e7c7f-116">Prerequisites</span></span>

<span data-ttu-id="e7c7f-117">次の前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-117">Install the following prerequisites:</span></span>

- <span data-ttu-id="e7c7f-118">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="e7c7f-118">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="e7c7f-119">.NET Core をインストールしてある場合、どの SDK を使っているか確認するには、`dotnet --info` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-119">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="e7c7f-120">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="e7c7f-120">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="e7c7f-121">*Dockerfile* と .NET Core サンプル アプリ用の一時作業フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-121">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="e7c7f-122">このチュートリアルでは、作業フォルダーに *docker-working* の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-122">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="e7c7f-123">.NET Core アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-123">Create .NET Core app</span></span>

<span data-ttu-id="e7c7f-124">Docker コンテナーで実行される .NET Core アプリが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-124">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="e7c7f-125">ターミナルを開き、作業フォルダーがまだない場合は作成して、移動します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-125">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="e7c7f-126">作業フォルダーで次のコマンドを実行し、*app* という名前のサブディレクトリに新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-126">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="e7c7f-127">フォルダー ツリーは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-127">Your folder tree will look like the following:</span></span>

```
docker-working
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.dgspec.json
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="e7c7f-128">`dotnet new` コマンドでは、*app* という名前の新しいフォルダーが作成され、"Hello World" アプリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-128">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="e7c7f-129">*app* フォルダーに移動し、コマンド `dotnet run` を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-129">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="e7c7f-130">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-130">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="e7c7f-131">既定のテンプレートでは、端末に出力して終了するアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-131">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="e7c7f-132">このチュートリアルでは、無限にループするアプリを使います。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-132">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="e7c7f-133">テキスト エディターで *Program.cs* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-133">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="e7c7f-134">現在は次のようなコードになっているはずです。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-134">It should currently look like the following code:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="e7c7f-135">1 秒ごとに数をカウントする次のコードにファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-135">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="e7c7f-136">ファイルを保存し、`dotnet run` で再びプログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-136">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="e7c7f-137">このアプリは無限に実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-137">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="e7c7f-138">停止するにはキャンセル コマンド <kbd>Ctrl</kbd>+<kbd>C</kbd> を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-138">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="e7c7f-139">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-139">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="e7c7f-140">コマンド ラインでアプリに数値を渡すと、アプリはその値までカウント アップしただけで終了します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-140">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="e7c7f-141">`dotnet run -- 5` で 5 までカウントしてみてください。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-141">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="e7c7f-142">`--` より後のパラメーターは `dotnet run` コマンドに渡されず、代わりにアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-142">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="e7c7f-143">.NET Core アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-143">Publish .NET Core app</span></span>

<span data-ttu-id="e7c7f-144">.NET Core アプリを Docker イメージに追加する前に、アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-144">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="e7c7f-145">コンテナーの開始時に、発行されたバージョンのアプリが実行されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-145">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="e7c7f-146">作業フォルダーから、サンプルのソース コードがある *app* フォルダーに移動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-146">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="e7c7f-147">このコマンドでは、*publish* フォルダーにアプリがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-147">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="e7c7f-148">作業フォルダーから *publish* フォルダーへのパスは `.\app\bin\Release\netcoreapp3.1\publish\` です</span><span class="sxs-lookup"><span data-stu-id="e7c7f-148">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp3.1\publish\`</span></span>

<span data-ttu-id="e7c7f-149">*app* フォルダーから、publish フォルダーのディレクトリ一覧を表示し、*myapp.dll* ファイルが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-149">From the *app* folder, get a directory listing of the publish folder to verify that the *myapp.dll* file was created.</span></span>

```console
> dir bin\Release\netcoreapp3.1\publish

    Directory:  C:\docker-working\app\bin\Release\netcoreapp3.1\publish

01/09/2020  11:41 AM    <DIR>          .
01/09/2020  11:41 AM    <DIR>          ..
01/09/2020  11:41 AM               407 myapp.deps.json
01/09/2020  12:15 PM             4,608 myapp.dll
01/09/2020  12:15 PM           169,984 myapp.exe
01/09/2020  12:15 PM               736 myapp.pdb
01/09/2020  11:41 AM               154 myapp.runtimeconfig.json
```

<span data-ttu-id="e7c7f-150">Linux または macOS を使用している場合は、`ls` コマンドを使用してディレクトリ一覧を表示し、*myapp.dll* ファイルが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-150">If you're using Linux or macOS, use the `ls` command to get a directory listing and verify that the *myapp.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="e7c7f-151">Dockerfile を作成する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-151">Create the Dockerfile</span></span>

<span data-ttu-id="e7c7f-152">*Dockerfile* ファイルは、コンテナー イメージを作成するために `docker build` コマンドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-152">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="e7c7f-153">このファイルは *Dockerfile* という名前のテキスト ファイルで、拡張子はありません。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-153">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="e7c7f-154">ターミナルで、開始時に作成した作業フォルダーまでディレクトリを移動します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-154">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="e7c7f-155">*Dockerfile* という名前のファイルを作業フォルダーに作成し、テキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-155">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="e7c7f-156">コンテナー化するアプリケーションの種類に応じて、ASP.NET Core ランタイムまたは .NET Core ランタイムのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-156">Depending on the type of application you're going to containerize, you'll choose either the ASP.NET Core runtime or the .NET Core runtime.</span></span> <span data-ttu-id="e7c7f-157">不明な場合は、ASP.NET Core ランタイム (.NET Core ランタイムが含まれています) を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-157">When in doubt, choose the ASP.NET Core runtime, which includes the .NET Core runtime.</span></span> <span data-ttu-id="e7c7f-158">このチュートリアルでは ASP.NET Core ランタイム イメージを使用しますが、前のセクションで作成したアプリケーションは .NET Core アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-158">This tutorial will use the ASP.NET Core runtime image, but the application created in the previous sections is an .NET Core application.</span></span>

- <span data-ttu-id="e7c7f-159">ASP.NET Core ランタイム</span><span class="sxs-lookup"><span data-stu-id="e7c7f-159">ASP.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- <span data-ttu-id="e7c7f-160">.NET Core ランタイム</span><span class="sxs-lookup"><span data-stu-id="e7c7f-160">.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

<span data-ttu-id="e7c7f-161">`FROM` コマンドは、指定したリポジトリから **3.1** というタグの付いたイメージをプルするよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-161">The `FROM` command tells Docker to pull down the image tagged **3.1** from the specified repository.</span></span> <span data-ttu-id="e7c7f-162">必ず、SDK のターゲットのランタイムと一致するランタイム バージョンをプルしてください。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-162">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="e7c7f-163">たとえば、前のセクションで作成したアプリは .NET Core 3.1 SDK を使用しているため、*Dockerfile* で参照される基本イメージは **3.1** でタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-163">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="e7c7f-164">*Dockerfile* ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="e7c7f-165">作業フォルダーのディレクトリ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="e7c7f-166">一部のより深いレベルのファイルとフォルダーは、スペース削減のためこの記事では省略されています。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp3.1
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.exe
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="e7c7f-167">ターミナルから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-167">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="e7c7f-168">Docker により *Dockerfile* 内の各行が処理されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-168">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="e7c7f-169">`docker build` コマンドの `.` は、現在のフォルダーで *Dockerfile* を検索するよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-169">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="e7c7f-170">このコマンドでは、イメージがビルドされて、そのイメージを指す **myimage** という名前のローカル リポジトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-170">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="e7c7f-171">このコマンドが終了したら、`docker images` を実行し、インストールされているイメージの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-171">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="e7c7f-172">2 つのイメージで同じ **IMAGE ID** 値が共有されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-172">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="e7c7f-173">*Dockerfile* での唯一のコマンドが既存のイメージを新しいイメージの基にするものであったため、両方のイメージで値が同じになっています。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-173">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="e7c7f-174">2 つのコマンドを *Dockerfile* に追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-174">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="e7c7f-175">各コマンドでは、**myimage** リポジトリ エントリが指し示すイメージを表す最後のコマンドで新しいイメージ レイヤーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-175">Each command creates a new image layer with the final command representing the image the **myimage** repository entry points to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="e7c7f-176">`COPY` コマンドは、自分のコンピューターの指定したフォルダーをコンテナー内のフォルダーにコピーするよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-176">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="e7c7f-177">この例では、*publish* フォルダーが、コンテナーの *app* という名前のフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-177">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="e7c7f-178">次のコマンド `ENTRYPOINT` は、実行可能ファイルとして実行するためにコンテナーを構成するよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-178">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="e7c7f-179">コンテナーの起動時に、`ENTRYPOINT` コマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-179">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="e7c7f-180">このコマンドが終了すると、コンテナーは自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-180">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="e7c7f-181">端末から `docker build -t myimage -f Dockerfile .` を実行し、そのコマンドが終了したら `docker images` を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-181">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  1.624MB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> 38db0eb8f648
Step 2/3 : COPY app/bin/Release/netcoreapp3.1/publish/ app/
 ---> 37873673e468
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in d8deb7b3aa9e
Removing intermediate container d8deb7b3aa9e
 ---> 0d602ca35c1d
Successfully built 0d602ca35c1d
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              0d602ca35c1d        4 seconds ago       346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="e7c7f-182">*Dockerfile* 内の各コマンドによってレイヤーが生成され、**IMAGE ID** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-182">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="e7c7f-183">最後の **IMAGE ID** は **ddcc6646461b** であり (個々に異なります)、次にこのイメージを基にしてコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-183">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="e7c7f-184">コンテナーの作成</span><span class="sxs-lookup"><span data-stu-id="e7c7f-184">Create a container</span></span>

<span data-ttu-id="e7c7f-185">アプリを含むイメージができたので、コンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-185">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="e7c7f-186">2 つの方法でコンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-186">You can create a container in two ways.</span></span> <span data-ttu-id="e7c7f-187">最初に、停止している新しいコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-187">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

<span data-ttu-id="e7c7f-188">上の `docker create` コマンドでは、**myimage** イメージに基づくコンテナーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-188">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="e7c7f-189">そのコマンドの出力では、作成されたコンテナーの **CONTAINER ID** (個々に異なります) が示されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-189">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="e7c7f-190">"*すべて*" のコンテナーの一覧を表示するには、`docker ps -a` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-190">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a><span data-ttu-id="e7c7f-191">コンテナーを管理する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-191">Manage the container</span></span>

<span data-ttu-id="e7c7f-192">各コンテナーにはランダムな名前が割り当てられており、それを使ってそのコンテナー インスタンスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-192">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="e7c7f-193">たとえば、自動的に作成されたコンテナーでは **gallant_lehmann** という名前が選択されており (個々に異なります)、その名前を使ってコンテナーを起動できます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-193">For example, the container that was created automatically chose the name **gallant_lehmann** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="e7c7f-194">`docker create --name` パラメーターを使って、自動的な名前を特定の名前でオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-194">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="e7c7f-195">次の例では、`docker start` コマンドを使ってコンテナーを起動した後、`docker ps` コマンドを使って、実行されているコンテナーのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-195">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

<span data-ttu-id="e7c7f-196">同様に、`docker stop` コマンドではコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-196">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="e7c7f-197">次の例では、`docker stop` コマンドを使ってコンテナーを停止した後、`docker ps` コマンドを使って、実行されているコンテナーがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-197">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="e7c7f-198">コンテナーへの接続</span><span class="sxs-lookup"><span data-stu-id="e7c7f-198">Connect to a container</span></span>

<span data-ttu-id="e7c7f-199">コンテナーが実行状態になった後、それに接続して出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-199">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="e7c7f-200">`docker start` コマンドを使ってコンテナーを起動し、`docker attach` コマンドを使って出力ストリームを表示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-200">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="e7c7f-201">この例では、<kbd>Ctrl + C</kbd> キー入力を使用して、実行中のコンテナーからデタッチします。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-201">In this example, the <kbd>CTRL + C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="e7c7f-202">このキー入力によりコンテナー内のプロセスが実際に終了する場合があり、コンテナーが停止します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-202">This keystroke may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="e7c7f-203">`--sig-proxy=false` パラメーターを指定すると、<kbd>Ctrl + C</kbd> キーを押してもコンテナー内のプロセスが停止しないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-203">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="e7c7f-204">コンテナーからデタッチした後、再アタッチして、まだ実行されていてカウントが行われていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-204">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker attach --sig-proxy=false gallant_lehmann
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false gallant_lehmann
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="e7c7f-205">コンテナーを削除する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-205">Delete a container</span></span>

<span data-ttu-id="e7c7f-206">この記事の目的では、何も行っていないコンテナーをそのままにするのは望ましくありません。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-206">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="e7c7f-207">前に作成したコンテナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-207">Delete the container you previously created.</span></span> <span data-ttu-id="e7c7f-208">コンテナーが実行されている場合は、それを停止します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-208">If the container is running, stop it.</span></span>

```console
> docker stop gallant_lehmann
```

<span data-ttu-id="e7c7f-209">次の例では、すべてのコンテナーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-209">The following example lists all containers.</span></span> <span data-ttu-id="e7c7f-210">次に、`docker rm` コマンドを使ってコンテナーを削除した後、もう一度実行中のコンテナーを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-210">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="e7c7f-211">単一実行</span><span class="sxs-lookup"><span data-stu-id="e7c7f-211">Single run</span></span>

<span data-ttu-id="e7c7f-212">Docker では、1 つのコマンドとしてコンテナーを作成して実行するための `docker run` コマンドが提供されています。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-212">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="e7c7f-213">このコマンドでは、`docker create` を実行してから `docker start` を実行する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-213">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="e7c7f-214">コンテナーが停止したら自動的にコンテナーを削除するように、このコマンドを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-214">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="e7c7f-215">たとえば、`docker run -it --rm` を使うと 2 つのことが行われます。つまり、最初に現在の端末を使ってコンテナーに自動的に接続し、次にコンテナーが終了したらそれを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-215">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="e7c7f-216">`docker run -it` では、<kbd>Ctrl + C</kbd> キーを押すと、コンテナーで実行されているプロセスが停止し、さらにコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-216">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="e7c7f-217">`--rm` パラメーターを指定したので、プロセスが停止するとコンテナーは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-217">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="e7c7f-218">それが存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-218">Verify that it doesn't exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="e7c7f-219">ENTRYPOINT を変更する</span><span class="sxs-lookup"><span data-stu-id="e7c7f-219">Change the ENTRYPOINT</span></span>

<span data-ttu-id="e7c7f-220">`docker run` コマンドでは、*Dockerfile* から `ENTRYPOINT` コマンドを変更し、そのコンテナーに対してのみ何か他のことを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-220">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="e7c7f-221">たとえば、次のコマンドを使うと `bash` または `cmd.exe` を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-221">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="e7c7f-222">必要に応じて、コマンドを編集します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-222">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="e7c7f-223">Windows</span><span class="sxs-lookup"><span data-stu-id="e7c7f-223">Windows</span></span>

<span data-ttu-id="e7c7f-224">この例では、`ENTRYPOINT` が `cmd.exe` に変更されています。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-224">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="e7c7f-225">プロセスを終了してコンテナーを停止するには、<kbd>Ctrl</kbd>+<kbd>C</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-225"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a><span data-ttu-id="e7c7f-226">Linux</span><span class="sxs-lookup"><span data-stu-id="e7c7f-226">Linux</span></span>

<span data-ttu-id="e7c7f-227">この例では、`ENTRYPOINT` が `bash` に変更されています。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-227">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="e7c7f-228">`quit` コマンドが実行されると、プロセスが終了してコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-228">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="e7c7f-229">重要なコマンド</span><span class="sxs-lookup"><span data-stu-id="e7c7f-229">Essential commands</span></span>

<span data-ttu-id="e7c7f-230">Docker には多種多様なコマンドがあり、コンテナーとイメージに対する操作がカバーされています。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-230">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="e7c7f-231">コンテナーの管理に不可欠な Docker コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-231">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="e7c7f-232">docker build</span><span class="sxs-lookup"><span data-stu-id="e7c7f-232">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="e7c7f-233">docker run</span><span class="sxs-lookup"><span data-stu-id="e7c7f-233">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="e7c7f-234">docker ps</span><span class="sxs-lookup"><span data-stu-id="e7c7f-234">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="e7c7f-235">docker stop</span><span class="sxs-lookup"><span data-stu-id="e7c7f-235">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="e7c7f-236">docker rm</span><span class="sxs-lookup"><span data-stu-id="e7c7f-236">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="e7c7f-237">docker rmi</span><span class="sxs-lookup"><span data-stu-id="e7c7f-237">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="e7c7f-238">docker image</span><span class="sxs-lookup"><span data-stu-id="e7c7f-238">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="e7c7f-239">リソースをクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="e7c7f-239">Clean up resources</span></span>

<span data-ttu-id="e7c7f-240">このチュートリアルでは、コンテナーとイメージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-240">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="e7c7f-241">必要な場合は、これらのリソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-241">If you want, delete these resources.</span></span> <span data-ttu-id="e7c7f-242">次のコマンドを使います</span><span class="sxs-lookup"><span data-stu-id="e7c7f-242">Use the following commands to</span></span>

01. <span data-ttu-id="e7c7f-243">すべてのコンテナーを一覧表示します</span><span class="sxs-lookup"><span data-stu-id="e7c7f-243">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="e7c7f-244">実行しているコンテナーを停止します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-244">Stop containers that are running.</span></span> <span data-ttu-id="e7c7f-245">`CONTAINER_NAME` は、コンテナーに自動的に割り当てられた名前を表します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-245">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="e7c7f-246">コンテナーを削除します</span><span class="sxs-lookup"><span data-stu-id="e7c7f-246">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="e7c7f-247">次に、コンピューターに残しておきたくないイメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-247">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="e7c7f-248">*Dockerfile* によって作成されたイメージを削除した後、*Dockerfile* が基にした .NET Core イメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-248">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="e7c7f-249">**IMAGE ID** または **REPOSITORY:TAG** の書式に設定された文字列を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-249">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="e7c7f-250">インストールされているイメージの一覧を表示するには、`docker images` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-250">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="e7c7f-251">イメージ ファイルは大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-251">Image files can be large.</span></span> <span data-ttu-id="e7c7f-252">普通、アプリのテスト中および開発中に作成した一時的なコンテナーは削除します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-252">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="e7c7f-253">通常、ランタイムがインストールされた基本イメージは、そのランタイムを基にして他のイメージをビルドする予定がある場合は、残しておきます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-253">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7c7f-254">次の手順</span><span class="sxs-lookup"><span data-stu-id="e7c7f-254">Next steps</span></span>

- [<span data-ttu-id="e7c7f-255">ASP.NET Core アプリケーションをコンテナー化する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-255">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="e7c7f-256">ASP.NET Core マイクロサービスのチュートリアルを試します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-256">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="e7c7f-257">コンテナーをサポートする Azure サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-257">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="e7c7f-258">Dockerfile のコマンドについて読みます。</span><span class="sxs-lookup"><span data-stu-id="e7c7f-258">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="e7c7f-259">Visual Studio 向けのコンテナー ツールを調べます</span><span class="sxs-lookup"><span data-stu-id="e7c7f-259">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
