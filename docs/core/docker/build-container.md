---
title: Docker を使用してアプリをコンテナー化するチュートリアル
description: このチュートリアルでは、Docker を使って .NET Core アプリケーションをコンテナー化する方法を学習します。
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e1904430a591b0e74a69d50a53869a130fc0a248
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157831"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="56e9a-103">チュートリアル: NET Core アプリのコンテナー化</span><span class="sxs-lookup"><span data-stu-id="56e9a-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="56e9a-104">このチュートリアルでは、.NET Core アプリケーションを含む Docker イメージをビルドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="56e9a-105">そのイメージを使って、ローカル開発環境、プライベート クラウド、またはパブリック クラウド用にコンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="56e9a-106">以下のことを学習します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="56e9a-107">簡単な .NET Core アプリを作成して発行する</span><span class="sxs-lookup"><span data-stu-id="56e9a-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="56e9a-108">.NET Core 用の Dockerfile を作成して構成する</span><span class="sxs-lookup"><span data-stu-id="56e9a-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="56e9a-109">Docker イメージの構築</span><span class="sxs-lookup"><span data-stu-id="56e9a-109">Build a Docker image</span></span>
> - <span data-ttu-id="56e9a-110">Docker コンテナーを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="56e9a-110">Create and run a Docker container</span></span>

<span data-ttu-id="56e9a-111">.NET Core アプリケーション用に Docker コンテナーを構築してデプロイするタスクを理解できます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="56e9a-112">"*Docker プラットフォーム*" では、"*Docker エンジン*" を使用して、すばやくアプリがビルドされ、"*Docker イメージ*" としてパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="56e9a-113">これらのイメージは、階層型コンテナーに展開されて実行される *Dockerfile* 形式で記述されています。</span><span class="sxs-lookup"><span data-stu-id="56e9a-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!TIP]
> <span data-ttu-id="56e9a-114">既存の ASP.NET Core アプリケーションを使用している場合は、[ASP.NET Core アプリケーションをコンテナー化する方法](/aspnet/core/host-and-deploy/docker/building-net-docker-images)に関するチュートリアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56e9a-114">If you're working with an existing ASP.NET Core application, see the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56e9a-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="56e9a-115">Prerequisites</span></span>

<span data-ttu-id="56e9a-116">次の前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="56e9a-116">Install the following prerequisites:</span></span>

- <span data-ttu-id="56e9a-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="56e9a-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="56e9a-118">.NET Core をインストールしてある場合、どの SDK を使っているか確認するには、`dotnet --info` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="56e9a-118">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- [<span data-ttu-id="56e9a-119">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="56e9a-119">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

- <span data-ttu-id="56e9a-120">*Dockerfile* と .NET Core サンプル アプリ用の一時作業フォルダー。</span><span class="sxs-lookup"><span data-stu-id="56e9a-120">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="56e9a-121">このチュートリアルでは、作業フォルダーに *docker-working* の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-121">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="56e9a-122">.NET Core アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="56e9a-122">Create .NET Core app</span></span>

<span data-ttu-id="56e9a-123">Docker コンテナーで実行される .NET Core アプリが必要です。</span><span class="sxs-lookup"><span data-stu-id="56e9a-123">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="56e9a-124">ターミナルを開き、作業フォルダーがまだない場合は作成して、移動します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-124">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="56e9a-125">作業フォルダーで次のコマンドを実行し、*app* という名前のサブディレクトリに新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-125">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="56e9a-126">フォルダー ツリーは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-126">Your folder tree will look like the following:</span></span>

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

<span data-ttu-id="56e9a-127">`dotnet new` コマンドでは、*app* という名前の新しいフォルダーが作成され、"Hello World" アプリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-127">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="56e9a-128">*app* フォルダーに移動し、コマンド `dotnet run` を実行します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-128">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="56e9a-129">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-129">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="56e9a-130">既定のテンプレートでは、端末に出力して終了するアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-130">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="56e9a-131">このチュートリアルでは、無限にループするアプリを使います。</span><span class="sxs-lookup"><span data-stu-id="56e9a-131">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="56e9a-132">テキスト エディターで *Program.cs* ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-132">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="56e9a-133">現在は次のようなコードになっているはずです。</span><span class="sxs-lookup"><span data-stu-id="56e9a-133">It should currently look like the following code:</span></span>

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

<span data-ttu-id="56e9a-134">1 秒ごとに数をカウントする次のコードにファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-134">Replace the file with the following code that counts numbers every second:</span></span>

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

<span data-ttu-id="56e9a-135">ファイルを保存し、`dotnet run` で再びプログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="56e9a-135">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="56e9a-136">このアプリは無限に実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="56e9a-136">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="56e9a-137">停止するにはキャンセル コマンド <kbd>Ctrl</kbd>+<kbd>C</kbd> を使用します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-137">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="56e9a-138">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-138">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="56e9a-139">コマンド ラインでアプリに数値を渡すと、アプリはその値までカウント アップしただけで終了します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-139">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="56e9a-140">`dotnet run -- 5` で 5 までカウントしてみてください。</span><span class="sxs-lookup"><span data-stu-id="56e9a-140">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="56e9a-141">`--` より後のパラメーターは `dotnet run` コマンドに渡されず、代わりにアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-141">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="56e9a-142">.NET Core アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="56e9a-142">Publish .NET Core app</span></span>

<span data-ttu-id="56e9a-143">.NET Core アプリを Docker イメージに追加する前に、アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-143">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="56e9a-144">コンテナーの開始時に、発行されたバージョンのアプリが実行されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56e9a-144">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="56e9a-145">作業フォルダーから、サンプルのソース コードがある *app* フォルダーに移動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-145">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="56e9a-146">このコマンドでは、*publish* フォルダーにアプリがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-146">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="56e9a-147">作業フォルダーから *publish* フォルダーへのパスは `.\app\bin\Release\netcoreapp3.1\publish\` です</span><span class="sxs-lookup"><span data-stu-id="56e9a-147">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp3.1\publish\`</span></span>

<span data-ttu-id="56e9a-148">*app* フォルダーから、publish フォルダーのディレクトリ一覧を表示し、*myapp.dll* ファイルが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-148">From the *app* folder, get a directory listing of the publish folder to verify that the *myapp.dll* file was created.</span></span>

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

<span data-ttu-id="56e9a-149">Linux または macOS を使用している場合は、`ls` コマンドを使用してディレクトリ一覧を表示し、*myapp.dll* ファイルが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-149">If you're using Linux or macOS, use the `ls` command to get a directory listing and verify that the *myapp.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="56e9a-150">Dockerfile を作成する</span><span class="sxs-lookup"><span data-stu-id="56e9a-150">Create the Dockerfile</span></span>

<span data-ttu-id="56e9a-151">*Dockerfile* ファイルは、コンテナー イメージを作成するために `docker build` コマンドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-151">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="56e9a-152">このファイルは *Dockerfile* という名前のテキスト ファイルで、拡張子はありません。</span><span class="sxs-lookup"><span data-stu-id="56e9a-152">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="56e9a-153">ターミナルで、開始時に作成した作業フォルダーまでディレクトリを移動します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-153">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="56e9a-154">*Dockerfile* という名前のファイルを作業フォルダーに作成し、テキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-154">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="56e9a-155">コンテナー化するアプリケーションの種類に応じて、ASP.NET Core ランタイムまたは .NET Core ランタイムのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-155">Depending on the type of application you're going to containerize, you'll choose either the ASP.NET Core runtime or the .NET Core runtime.</span></span> <span data-ttu-id="56e9a-156">不明な場合は、ASP.NET Core ランタイム (.NET Core ランタイムが含まれています) を選択します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-156">When in doubt, choose the ASP.NET Core runtime, which includes the .NET Core runtime.</span></span> <span data-ttu-id="56e9a-157">このチュートリアルでは ASP.NET Core ランタイム イメージを使用しますが、前のセクションで作成したアプリケーションは .NET Core アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="56e9a-157">This tutorial will use the ASP.NET Core runtime image, but the application created in the previous sections is an .NET Core application.</span></span>

- <span data-ttu-id="56e9a-158">ASP.NET Core ランタイム</span><span class="sxs-lookup"><span data-stu-id="56e9a-158">ASP.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- <span data-ttu-id="56e9a-159">.NET Core ランタイム</span><span class="sxs-lookup"><span data-stu-id="56e9a-159">.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

<span data-ttu-id="56e9a-160">`FROM` コマンドは、指定したリポジトリから **3.1** というタグの付いたイメージをプルするよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-160">The `FROM` command tells Docker to pull down the image tagged **3.1** from the specified repository.</span></span> <span data-ttu-id="56e9a-161">必ず、SDK のターゲットのランタイムと一致するランタイム バージョンをプルしてください。</span><span class="sxs-lookup"><span data-stu-id="56e9a-161">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="56e9a-162">たとえば、前のセクションで作成したアプリは .NET Core 3.1 SDK を使用しているため、*Dockerfile* で参照される基本イメージは **3.1** でタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-162">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="56e9a-163">*Dockerfile* ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-163">Save the *Dockerfile* file.</span></span> <span data-ttu-id="56e9a-164">作業フォルダーのディレクトリ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="56e9a-164">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="56e9a-165">一部のより深いレベルのファイルとフォルダーは、スペース削減のためこの記事では省略されています。</span><span class="sxs-lookup"><span data-stu-id="56e9a-165">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

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

<span data-ttu-id="56e9a-166">ターミナルから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-166">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="56e9a-167">Docker により *Dockerfile* 内の各行が処理されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-167">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="56e9a-168">`docker build` コマンドの `.` は、現在のフォルダーで *Dockerfile* を検索するよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-168">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="56e9a-169">このコマンドでは、イメージがビルドされて、そのイメージを指す **myimage** という名前のローカル リポジトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-169">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="56e9a-170">このコマンドが終了したら、`docker images` を実行し、インストールされているイメージの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-170">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="56e9a-171">2 つのイメージで同じ **IMAGE ID** 値が共有されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="56e9a-171">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="56e9a-172">*Dockerfile* での唯一のコマンドが既存のイメージを新しいイメージの基にするものであったため、両方のイメージで値が同じになっています。</span><span class="sxs-lookup"><span data-stu-id="56e9a-172">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="56e9a-173">2 つのコマンドを *Dockerfile* に追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="56e9a-173">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="56e9a-174">各コマンドでは、**myimage** リポジトリ エントリが指し示すイメージを表す最後のコマンドで新しいイメージ レイヤーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-174">Each command creates a new image layer with the final command representing the image the **myimage** repository entry points to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="56e9a-175">`COPY` コマンドは、自分のコンピューターの指定したフォルダーをコンテナー内のフォルダーにコピーするよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-175">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="56e9a-176">この例では、*publish* フォルダーが、コンテナーの *app* という名前のフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-176">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="56e9a-177">次のコマンド `ENTRYPOINT` は、実行可能ファイルとして実行するためにコンテナーを構成するよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-177">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="56e9a-178">コンテナーの起動時に、`ENTRYPOINT` コマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-178">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="56e9a-179">このコマンドが終了すると、コンテナーは自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-179">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="56e9a-180">端末から `docker build -t myimage -f Dockerfile .` を実行し、そのコマンドが終了したら `docker images` を実行します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-180">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

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

<span data-ttu-id="56e9a-181">*Dockerfile* 内の各コマンドによってレイヤーが生成され、**IMAGE ID** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-181">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="56e9a-182">最後の **IMAGE ID** は **ddcc6646461b** であり (個々に異なります)、次にこのイメージを基にしてコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-182">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="56e9a-183">コンテナーの作成</span><span class="sxs-lookup"><span data-stu-id="56e9a-183">Create a container</span></span>

<span data-ttu-id="56e9a-184">アプリを含むイメージができたので、コンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-184">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="56e9a-185">2 つの方法でコンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-185">You can create a container in two ways.</span></span> <span data-ttu-id="56e9a-186">最初に、停止している新しいコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-186">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

<span data-ttu-id="56e9a-187">上の `docker create` コマンドでは、**myimage** イメージに基づくコンテナーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-187">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="56e9a-188">そのコマンドの出力では、作成されたコンテナーの **CONTAINER ID** (個々に異なります) が示されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-188">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="56e9a-189">"*すべて*" のコンテナーの一覧を表示するには、`docker ps -a` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="56e9a-189">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a><span data-ttu-id="56e9a-190">コンテナーを管理する</span><span class="sxs-lookup"><span data-stu-id="56e9a-190">Manage the container</span></span>

<span data-ttu-id="56e9a-191">各コンテナーにはランダムな名前が割り当てられており、それを使ってそのコンテナー インスタンスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-191">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="56e9a-192">たとえば、自動的に作成されたコンテナーでは **gallant_lehmann** という名前が選択されており (個々に異なります)、その名前を使ってコンテナーを起動できます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-192">For example, the container that was created automatically chose the name **gallant_lehmann** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="56e9a-193">`docker create --name` パラメーターを使って、自動的な名前を特定の名前でオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-193">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="56e9a-194">次の例では、`docker start` コマンドを使ってコンテナーを起動した後、`docker ps` コマンドを使って、実行されているコンテナーのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-194">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

<span data-ttu-id="56e9a-195">同様に、`docker stop` コマンドではコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-195">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="56e9a-196">次の例では、`docker stop` コマンドを使ってコンテナーを停止した後、`docker ps` コマンドを使って、実行されているコンテナーがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-196">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="56e9a-197">コンテナーへの接続</span><span class="sxs-lookup"><span data-stu-id="56e9a-197">Connect to a container</span></span>

<span data-ttu-id="56e9a-198">コンテナーが実行状態になった後、それに接続して出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-198">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="56e9a-199">`docker start` コマンドを使ってコンテナーを起動し、`docker attach` コマンドを使って出力ストリームを表示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-199">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="56e9a-200">この例では、<kbd>Ctrl + C</kbd> キー入力を使用して、実行中のコンテナーからデタッチします。</span><span class="sxs-lookup"><span data-stu-id="56e9a-200">In this example, the <kbd>CTRL + C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="56e9a-201">このキー入力によりコンテナー内のプロセスが実際に終了する場合があり、コンテナーが停止します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-201">This keystroke may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="56e9a-202">`--sig-proxy=false` パラメーターを指定すると、<kbd>Ctrl + C</kbd> キーを押してもコンテナー内のプロセスが停止しないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-202">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="56e9a-203">コンテナーからデタッチした後、再アタッチして、まだ実行されていてカウントが行われていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-203">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

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

### <a name="delete-a-container"></a><span data-ttu-id="56e9a-204">コンテナーを削除する</span><span class="sxs-lookup"><span data-stu-id="56e9a-204">Delete a container</span></span>

<span data-ttu-id="56e9a-205">この記事の目的では、何も行っていないコンテナーをそのままにするのは望ましくありません。</span><span class="sxs-lookup"><span data-stu-id="56e9a-205">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="56e9a-206">前に作成したコンテナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-206">Delete the container you previously created.</span></span> <span data-ttu-id="56e9a-207">コンテナーが実行されている場合は、それを停止します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-207">If the container is running, stop it.</span></span>

```console
> docker stop gallant_lehmann
```

<span data-ttu-id="56e9a-208">次の例では、すべてのコンテナーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-208">The following example lists all containers.</span></span> <span data-ttu-id="56e9a-209">次に、`docker rm` コマンドを使ってコンテナーを削除した後、もう一度実行中のコンテナーを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-209">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="56e9a-210">単一実行</span><span class="sxs-lookup"><span data-stu-id="56e9a-210">Single run</span></span>

<span data-ttu-id="56e9a-211">Docker では、1 つのコマンドとしてコンテナーを作成して実行するための `docker run` コマンドが提供されています。</span><span class="sxs-lookup"><span data-stu-id="56e9a-211">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="56e9a-212">このコマンドでは、`docker create` を実行してから `docker start` を実行する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="56e9a-212">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="56e9a-213">コンテナーが停止したら自動的にコンテナーを削除するように、このコマンドを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-213">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="56e9a-214">たとえば、`docker run -it --rm` を使うと 2 つのことが行われます。つまり、最初に現在の端末を使ってコンテナーに自動的に接続し、次にコンテナーが終了したらそれを削除します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-214">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="56e9a-215">`docker run -it` では、<kbd>Ctrl + C</kbd> キーを押すと、コンテナーで実行されているプロセスが停止し、さらにコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-215">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="56e9a-216">`--rm` パラメーターを指定したので、プロセスが停止するとコンテナーは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-216">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="56e9a-217">それが存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-217">Verify that it doesn't exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="56e9a-218">ENTRYPOINT を変更する</span><span class="sxs-lookup"><span data-stu-id="56e9a-218">Change the ENTRYPOINT</span></span>

<span data-ttu-id="56e9a-219">`docker run` コマンドでは、*Dockerfile* から `ENTRYPOINT` コマンドを変更し、そのコンテナーに対してのみ何か他のことを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-219">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="56e9a-220">たとえば、次のコマンドを使うと `bash` または `cmd.exe` を実行できます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-220">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="56e9a-221">必要に応じて、コマンドを編集します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-221">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="56e9a-222">Windows</span><span class="sxs-lookup"><span data-stu-id="56e9a-222">Windows</span></span>

<span data-ttu-id="56e9a-223">この例では、`ENTRYPOINT` が `cmd.exe` に変更されています。</span><span class="sxs-lookup"><span data-stu-id="56e9a-223">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="56e9a-224">プロセスを終了してコンテナーを停止するには、<kbd>Ctrl</kbd>+<kbd>C</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-224"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="56e9a-225">Linux</span><span class="sxs-lookup"><span data-stu-id="56e9a-225">Linux</span></span>

<span data-ttu-id="56e9a-226">この例では、`ENTRYPOINT` が `bash` に変更されています。</span><span class="sxs-lookup"><span data-stu-id="56e9a-226">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="56e9a-227">`quit` コマンドが実行されると、プロセスが終了してコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-227">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="56e9a-228">重要なコマンド</span><span class="sxs-lookup"><span data-stu-id="56e9a-228">Essential commands</span></span>

<span data-ttu-id="56e9a-229">Docker には多種多様なコマンドがあり、コンテナーとイメージに対する操作がカバーされています。</span><span class="sxs-lookup"><span data-stu-id="56e9a-229">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="56e9a-230">コンテナーの管理に不可欠な Docker コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56e9a-230">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="56e9a-231">docker build</span><span class="sxs-lookup"><span data-stu-id="56e9a-231">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="56e9a-232">docker run</span><span class="sxs-lookup"><span data-stu-id="56e9a-232">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="56e9a-233">docker ps</span><span class="sxs-lookup"><span data-stu-id="56e9a-233">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="56e9a-234">docker stop</span><span class="sxs-lookup"><span data-stu-id="56e9a-234">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="56e9a-235">docker rm</span><span class="sxs-lookup"><span data-stu-id="56e9a-235">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="56e9a-236">docker rmi</span><span class="sxs-lookup"><span data-stu-id="56e9a-236">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="56e9a-237">docker image</span><span class="sxs-lookup"><span data-stu-id="56e9a-237">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="56e9a-238">リソースをクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="56e9a-238">Clean up resources</span></span>

<span data-ttu-id="56e9a-239">このチュートリアルでは、コンテナーとイメージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="56e9a-239">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="56e9a-240">必要な場合は、これらのリソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-240">If you want, delete these resources.</span></span> <span data-ttu-id="56e9a-241">次のコマンドを使います</span><span class="sxs-lookup"><span data-stu-id="56e9a-241">Use the following commands to</span></span>

01. <span data-ttu-id="56e9a-242">すべてのコンテナーを一覧表示します</span><span class="sxs-lookup"><span data-stu-id="56e9a-242">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="56e9a-243">実行しているコンテナーを停止します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-243">Stop containers that are running.</span></span> <span data-ttu-id="56e9a-244">`CONTAINER_NAME` は、コンテナーに自動的に割り当てられた名前を表します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-244">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="56e9a-245">コンテナーを削除します</span><span class="sxs-lookup"><span data-stu-id="56e9a-245">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="56e9a-246">次に、コンピューターに残しておきたくないイメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-246">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="56e9a-247">*Dockerfile* によって作成されたイメージを削除した後、*Dockerfile* が基にした .NET Core イメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-247">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="56e9a-248">**IMAGE ID** または **REPOSITORY:TAG** の書式に設定された文字列を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-248">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="56e9a-249">インストールされているイメージの一覧を表示するには、`docker images` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="56e9a-249">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="56e9a-250">イメージ ファイルは大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="56e9a-250">Image files can be large.</span></span> <span data-ttu-id="56e9a-251">普通、アプリのテスト中および開発中に作成した一時的なコンテナーは削除します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-251">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="56e9a-252">通常、ランタイムがインストールされた基本イメージは、そのランタイムを基にして他のイメージをビルドする予定がある場合は、残しておきます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-252">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56e9a-253">次の手順</span><span class="sxs-lookup"><span data-stu-id="56e9a-253">Next steps</span></span>

- [<span data-ttu-id="56e9a-254">ASP.NET Core アプリケーションをコンテナー化する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-254">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="56e9a-255">ASP.NET Core マイクロサービスのチュートリアルを試します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-255">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="56e9a-256">コンテナーをサポートする Azure サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="56e9a-256">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="56e9a-257">Dockerfile のコマンドについて読みます。</span><span class="sxs-lookup"><span data-stu-id="56e9a-257">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="56e9a-258">Visual Studio 向けのコンテナー ツールを調べます</span><span class="sxs-lookup"><span data-stu-id="56e9a-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
