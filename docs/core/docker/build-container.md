---
title: Docker を使用してアプリをコンテナー化するチュートリアル
description: このチュートリアルでは、Docker を使って .NET Core アプリケーションをコンテナー化する方法を学習します。
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 16edb129be679179450c485ced2586cea9ed9763
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609299"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="80335-103">チュートリアル: NET Core アプリのコンテナー化</span><span class="sxs-lookup"><span data-stu-id="80335-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="80335-104">このチュートリアルでは、.NET Core アプリケーションを含む Docker イメージをビルドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80335-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="80335-105">そのイメージを使って、ローカル開発環境、プライベート クラウド、またはパブリック クラウド用にコンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="80335-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="80335-106">以下のことを学習します。</span><span class="sxs-lookup"><span data-stu-id="80335-106">You'll learn to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="80335-107">簡単な .NET Core アプリを作成して発行する</span><span class="sxs-lookup"><span data-stu-id="80335-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="80335-108">.NET Core 用の Dockerfile を作成して構成する</span><span class="sxs-lookup"><span data-stu-id="80335-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="80335-109">Docker イメージの構築</span><span class="sxs-lookup"><span data-stu-id="80335-109">Build a Docker image</span></span>
> * <span data-ttu-id="80335-110">Docker コンテナーを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="80335-110">Create and run a Docker container</span></span>

<span data-ttu-id="80335-111">.NET Core アプリケーション用に Docker コンテナーを構築してデプロイするタスクを理解できます。</span><span class="sxs-lookup"><span data-stu-id="80335-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="80335-112">"*Docker プラットフォーム*" では、"*Docker エンジン*" を使用して、すばやくアプリがビルドされ、"*Docker イメージ*" としてパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="80335-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="80335-113">これらのイメージは、階層型コンテナーに展開されて実行される *Dockerfile* 形式で記述されています。</span><span class="sxs-lookup"><span data-stu-id="80335-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80335-114">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="80335-114">Prerequisites</span></span>

<span data-ttu-id="80335-115">次の前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="80335-115">Install the following prerequisites:</span></span>

* <span data-ttu-id="80335-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="80335-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="80335-117">.NET Core をインストールしてある場合、どの SDK を使っているか確認するには、`dotnet --info` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="80335-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

* [<span data-ttu-id="80335-118">Docker Community Edition</span><span class="sxs-lookup"><span data-stu-id="80335-118">Docker Community Edition</span></span>](https://www.docker.com/products/docker-desktop)

* <span data-ttu-id="80335-119">*Dockerfile* と .NET Core サンプル アプリ用の一時作業フォルダー。</span><span class="sxs-lookup"><span data-stu-id="80335-119">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="80335-120">このチュートリアルでは、作業フォルダーに `docker-working` の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="80335-120">In this tutorial, the name `docker-working` is used as the working folder.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="80335-121">SDK バージョン 2.2 を使用する</span><span class="sxs-lookup"><span data-stu-id="80335-121">Use SDK version 2.2</span></span>

<span data-ttu-id="80335-122">3\.0 のようなさらに新しい SDK を使用している場合は、アプリが 2.2 SDK を使用するよう強制されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="80335-122">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="80335-123">作業フォルダーに `global.json` という名前のファイルを作成し、次の json コードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="80335-123">Create a file named `global.json` in your working folder and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="80335-124">このファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="80335-124">Save this file.</span></span> <span data-ttu-id="80335-125">このファイルが存在すると、このフォルダーおよびその下位から呼び出されるすべての `dotnet` コマンドに対し、.NET Core では強制的にバージョン 2.2 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="80335-125">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this folder and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="80335-126">.NET Core アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="80335-126">Create .NET Core app</span></span>

<span data-ttu-id="80335-127">Docker コンテナーで実行される .NET Core アプリが必要です。</span><span class="sxs-lookup"><span data-stu-id="80335-127">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="80335-128">ターミナルを開き、作業フォルダーがまだない場合は作成して、移動します。</span><span class="sxs-lookup"><span data-stu-id="80335-128">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="80335-129">作業フォルダーで次のコマンドを実行し、app という名前のサブディレクトリに新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="80335-129">In the working folder, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="80335-130">フォルダー ツリーは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="80335-130">Your folder tree will look like the following:</span></span>

```console
docker-working
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="80335-131">`dotnet new` コマンドでは、*app* という名前の新しいフォルダーが作成され、"Hello World" アプリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="80335-131">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="80335-132">*app* フォルダーに移動し、コマンド `dotnet run` を実行します。</span><span class="sxs-lookup"><span data-stu-id="80335-132">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="80335-133">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80335-133">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="80335-134">既定のテンプレートでは、端末に出力して終了するアプリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="80335-134">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="80335-135">このチュートリアルでは、無限にループするアプリを使います。</span><span class="sxs-lookup"><span data-stu-id="80335-135">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="80335-136">テキスト エディターで **Program.cs** ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="80335-136">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="80335-137">現在は次のようなコードになっているはずです。</span><span class="sxs-lookup"><span data-stu-id="80335-137">It should currently look like the following code:</span></span>

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

<span data-ttu-id="80335-138">1 秒ごとに数をカウントする次のコードにファイルを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="80335-138">Replace the file with the following code that counts numbers every second:</span></span>

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
            while(max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="80335-139">ファイルを保存し、`dotnet run` で再びプログラムをテストします。</span><span class="sxs-lookup"><span data-stu-id="80335-139">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="80335-140">このアプリは無限に実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="80335-140">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="80335-141">停止するにはキャンセル コマンド <kbd>Ctrl + C</kbd> を使用します。</span><span class="sxs-lookup"><span data-stu-id="80335-141">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="80335-142">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80335-142">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="80335-143">コマンド ラインでアプリに数値を渡すと、アプリはその値までカウント アップしただけで終了します。</span><span class="sxs-lookup"><span data-stu-id="80335-143">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="80335-144">`dotnet run -- 5` で 5 までカウントしてみてください。</span><span class="sxs-lookup"><span data-stu-id="80335-144">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="80335-145">`--` より後のパラメーターは `dotnet run` コマンドに渡されず、代わりにアプリケーションに渡されます。</span><span class="sxs-lookup"><span data-stu-id="80335-145">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="80335-146">.NET Core アプリを発行する</span><span class="sxs-lookup"><span data-stu-id="80335-146">Publish .NET Core app</span></span>

<span data-ttu-id="80335-147">.NET Core アプリを Docker イメージに追加する前に、アプリを発行します。</span><span class="sxs-lookup"><span data-stu-id="80335-147">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="80335-148">コンテナーの開始時に、発行されたバージョンのアプリが実行されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80335-148">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="80335-149">作業フォルダーから、サンプルのソース コードがある **app** フォルダーに移動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="80335-149">From the working folder, enter the **app** folder with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="80335-150">このコマンドでは、**publish** フォルダーにアプリがコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="80335-150">This command compiles your app to the **publish** folder.</span></span> <span data-ttu-id="80335-151">作業フォルダーから **publish** フォルダーへのパスは `.\app\bin\Release\netcoreapp2.2\publish\` です</span><span class="sxs-lookup"><span data-stu-id="80335-151">The path to the **publish** folder from the working folder should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="80335-152">publish フォルダーのディレクトリ一覧を表示し、**myapp.dll** が作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="80335-152">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="80335-153">**app** フォルダーから、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="80335-153">From the **app** folder, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\docker-working\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="80335-154">Dockerfile を作成する</span><span class="sxs-lookup"><span data-stu-id="80335-154">Create the Dockerfile</span></span>

<span data-ttu-id="80335-155">*Dockerfile* ファイルは、コンテナー イメージを作成するために `docker build` コマンドによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="80335-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="80335-156">このファイルは *Dockerfile* という名前のプレーンテキスト ファイルで、拡張子はありません。</span><span class="sxs-lookup"><span data-stu-id="80335-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span>

<span data-ttu-id="80335-157">ターミナルで、開始時に作成した作業フォルダーまでディレクトリを移動します。</span><span class="sxs-lookup"><span data-stu-id="80335-157">In your terminal, navigate to up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="80335-158">*Dockerfile* という名前のファイルを作業フォルダーに作成し、テキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="80335-158">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="80335-159">ファイルの最初の行として、次のコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="80335-159">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
```

<span data-ttu-id="80335-160">`FROM` コマンドは、**mcr.microsoft.com/dotnet/core/runtime** リポジトリから **2.2** というタグの付いたイメージをプルするよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="80335-160">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="80335-161">SDK のターゲットのランタイムと一致する .NET Core ランタイムをプルすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="80335-161">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="80335-162">たとえば、前のセクションで作成したアプリ は .NET Core 2.2 SDK を使用しており、.NET Core 2.2 をターゲットにするアプリを作成しました。</span><span class="sxs-lookup"><span data-stu-id="80335-162">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="80335-163">したがって、*Dockerfile* で参照されている基本イメージは、**2.2** でタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="80335-163">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="80335-164">*Dockerfile* ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="80335-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="80335-165">作業フォルダーのディレクトリ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="80335-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="80335-166">一部のより深いレベルのファイルとフォルダーは、スペース削減のためこの記事では省略されています。</span><span class="sxs-lookup"><span data-stu-id="80335-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```console
docker-working
│   Dockerfile
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp2.2
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="80335-167">端末から `docker build -t myimage -f Dockerfile .` を実行すると、Docker で *Dockerfile* 内の各行が処理されます。</span><span class="sxs-lookup"><span data-stu-id="80335-167">From your terminal, run `docker build -t myimage -f Dockerfile .` and Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="80335-168">`docker build` コマンドの `.` は、現在のフォルダーで *Dockerfile* を検索するよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="80335-168">The `.` in the `docker build` command tells docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="80335-169">このコマンドでは、イメージがビルドされて、そのイメージを指す **myimage** という名前のローカル リポジトリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="80335-169">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="80335-170">このコマンドが終了したら、`docker images` を実行し、インストールされているイメージの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="80335-170">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="80335-171">2 つのイメージで同じ **IMAGE ID** 値が共有されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="80335-171">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="80335-172">*Dockerfile* での唯一のコマンドが既存のイメージを新しいイメージの基にするものであったため、両方のイメージで値が同じになっています。</span><span class="sxs-lookup"><span data-stu-id="80335-172">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="80335-173">2 つのコマンドを *Dockerfile* に追加してみましょう。</span><span class="sxs-lookup"><span data-stu-id="80335-173">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="80335-174">各コマンドでは、**myimage** リポジトリが指し示すイメージを表す最後のコマンドで、新しいイメージ レイヤーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="80335-174">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="80335-175">`COPY` コマンドは、自分のコンピューターの指定したフォルダーをコンテナー内のフォルダーにコピーするよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="80335-175">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="80335-176">この例では、**publish** フォルダーが、コンテナーの **app** という名前のフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="80335-176">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="80335-177">次のコマンド `ENTRYPOINT` は、実行可能ファイルとして実行するためにコンテナーを構成するよう Docker に指示します。</span><span class="sxs-lookup"><span data-stu-id="80335-177">The next command, `ENTRYPOINT`, tells docker to configure the container to run as an executable.</span></span> <span data-ttu-id="80335-178">コンテナーの起動時に、`ENTRYPOINT` コマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="80335-178">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="80335-179">このコマンドが終了すると、コンテナーは自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="80335-179">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="80335-180">端末から `docker build -t myimage -f Dockerfile .` を実行し、そのコマンドが終了したら `docker images` を実行します。</span><span class="sxs-lookup"><span data-stu-id="80335-180">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest


> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="80335-181">*Dockerfile* 内の各コマンドによってレイヤーが生成され、**IMAGE ID** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="80335-181">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="80335-182">最後の **IMAGE ID** は **ddcc6646461b** であり (個々に異なります)、次にこのイメージを基にしてコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="80335-182">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="80335-183">コンテナーの作成</span><span class="sxs-lookup"><span data-stu-id="80335-183">Create a container</span></span>

<span data-ttu-id="80335-184">アプリを含むイメージができたので、コンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="80335-184">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="80335-185">2 つの方法でコンテナーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="80335-185">You can create a container in two ways.</span></span> <span data-ttu-id="80335-186">最初に、停止している新しいコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="80335-186">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="80335-187">上の `docker create` コマンドでは、**myimage** イメージに基づくコンテナーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="80335-187">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="80335-188">そのコマンドの出力では、作成されたコンテナーの **CONTAINER ID** (個々に異なります) が示されます。</span><span class="sxs-lookup"><span data-stu-id="80335-188">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="80335-189">"*すべて*" のコンテナーの一覧を表示するには、`docker ps -a` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="80335-189">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="80335-190">コンテナーを管理する</span><span class="sxs-lookup"><span data-stu-id="80335-190">Manage the container</span></span>

<span data-ttu-id="80335-191">各コンテナーにはランダムな名前が割り当てられており、それを使ってそのコンテナー インスタンスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="80335-191">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="80335-192">たとえば、自動的に作成されたコンテナーでは **boring_matsumoto** という名前が選択されており (個々に異なります)、その名前を使ってコンテナーを起動できます。</span><span class="sxs-lookup"><span data-stu-id="80335-192">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="80335-193">`docker create --name` パラメーターを使って、自動的な名前を特定の名前でオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="80335-193">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="80335-194">次の例では、`docker start` コマンドを使ってコンテナーを起動した後、`docker ps` コマンドを使って、実行されているコンテナーのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="80335-194">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="80335-195">同様に、`docker stop` コマンドではコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="80335-195">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="80335-196">次の例では、`docker stop` コマンドを使ってコンテナーを停止した後、`docker ps` コマンドを使って、実行されているコンテナーがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="80335-196">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="80335-197">コンテナーへの接続</span><span class="sxs-lookup"><span data-stu-id="80335-197">Connect to a container</span></span>

<span data-ttu-id="80335-198">コンテナーが実行状態になった後、それに接続して出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="80335-198">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="80335-199">`docker start` コマンドを使ってコンテナーを起動し、`docker attach` コマンドを使って出力ストリームを表示します。</span><span class="sxs-lookup"><span data-stu-id="80335-199">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="80335-200">この例では、<kbd>Ctrl + C</kbd> キーを押して、実行中のコンテナーからデタッチします。</span><span class="sxs-lookup"><span data-stu-id="80335-200">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="80335-201">これによりコンテナー内のプロセスが実際に終了する場合があり、コンテナーが停止します。</span><span class="sxs-lookup"><span data-stu-id="80335-201">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="80335-202">`--sig-proxy=false` パラメーターを指定すると、<kbd>Ctrl + C</kbd> キーを押してもコンテナー内のプロセスが停止しないことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="80335-202">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="80335-203">コンテナーからデタッチした後、再アタッチして、まだ実行されていてカウントが行われていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="80335-203">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="80335-204">コンテナーを削除する</span><span class="sxs-lookup"><span data-stu-id="80335-204">Delete a container</span></span>

<span data-ttu-id="80335-205">この記事の目的では、何も行っていないコンテナーをそのままにするのは望ましくありません。</span><span class="sxs-lookup"><span data-stu-id="80335-205">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="80335-206">前に作成したコンテナーを削除します。</span><span class="sxs-lookup"><span data-stu-id="80335-206">Delete the container you previously created.</span></span> <span data-ttu-id="80335-207">コンテナーが実行されている場合は、それを停止します。</span><span class="sxs-lookup"><span data-stu-id="80335-207">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="80335-208">次の例では、すべてのコンテナーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="80335-208">The following example lists all containers.</span></span> <span data-ttu-id="80335-209">次に、`docker rm` コマンドを使ってコンテナーを削除した後、もう一度実行中のコンテナーを確認します。</span><span class="sxs-lookup"><span data-stu-id="80335-209">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="80335-210">単一実行</span><span class="sxs-lookup"><span data-stu-id="80335-210">Single run</span></span>

<span data-ttu-id="80335-211">Docker では、1 つのコマンドとしてコンテナーを作成して実行するための `docker run` コマンドが提供されています。</span><span class="sxs-lookup"><span data-stu-id="80335-211">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="80335-212">このコマンドでは、`docker create` を実行してから `docker start` を実行する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="80335-212">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="80335-213">コンテナーが停止したら自動的にコンテナーを削除するように、このコマンドを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="80335-213">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="80335-214">たとえば、`docker run -it --rm` を使うと 2 つのことが行われます。つまり、最初に現在の端末を使ってコンテナーに自動的に接続し、次にコンテナーが終了したらそれを削除します。</span><span class="sxs-lookup"><span data-stu-id="80335-214">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="80335-215">`docker run -it` では、<kbd>Ctrl + C</kbd> キーを押すと、コンテナーで実行されているプロセスが停止し、さらにコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="80335-215">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="80335-216">`--rm` パラメーターを指定したので、プロセスが停止するとコンテナーは自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="80335-216">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="80335-217">それが存在しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="80335-217">Verify that it does not exist:</span></span>

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="80335-218">ENTRYPOINT を変更する</span><span class="sxs-lookup"><span data-stu-id="80335-218">Change the ENTRYPOINT</span></span>

<span data-ttu-id="80335-219">`docker run` コマンドでは、*Dockerfile* から `ENTRYPOINT` コマンドを変更し、そのコンテナーに対してのみ何か他のことを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="80335-219">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="80335-220">たとえば、次のコマンドを使うと `bash` または `cmd.exe` を実行できます。</span><span class="sxs-lookup"><span data-stu-id="80335-220">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="80335-221">必要に応じて、コマンドを編集します。</span><span class="sxs-lookup"><span data-stu-id="80335-221">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="80335-222">Windows</span><span class="sxs-lookup"><span data-stu-id="80335-222">Windows</span></span>
<span data-ttu-id="80335-223">この例では、`ENTRYPOINT` が `cmd.exe` に変更されています。</span><span class="sxs-lookup"><span data-stu-id="80335-223">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="80335-224">プロセスを終了してコンテナーを停止するには、<kbd>Ctrl + C</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="80335-224"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="80335-225">Linux</span><span class="sxs-lookup"><span data-stu-id="80335-225">Linux</span></span>

<span data-ttu-id="80335-226">この例では、`ENTRYPOINT` が `bash` に変更されています。</span><span class="sxs-lookup"><span data-stu-id="80335-226">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="80335-227">`quit` コマンドが実行されると、プロセスが終了してコンテナーが停止されます。</span><span class="sxs-lookup"><span data-stu-id="80335-227">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="80335-228">重要なコマンド</span><span class="sxs-lookup"><span data-stu-id="80335-228">Essential commands</span></span>

<span data-ttu-id="80335-229">Docker には多種多様なコマンドがあり、コンテナーとイメージに対する操作がカバーされています。</span><span class="sxs-lookup"><span data-stu-id="80335-229">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="80335-230">コンテナーの管理に不可欠な Docker コマンドは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80335-230">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="80335-231">docker build</span><span class="sxs-lookup"><span data-stu-id="80335-231">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="80335-232">docker run</span><span class="sxs-lookup"><span data-stu-id="80335-232">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="80335-233">docker ps</span><span class="sxs-lookup"><span data-stu-id="80335-233">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="80335-234">docker stop</span><span class="sxs-lookup"><span data-stu-id="80335-234">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="80335-235">docker rm</span><span class="sxs-lookup"><span data-stu-id="80335-235">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="80335-236">docker rmi</span><span class="sxs-lookup"><span data-stu-id="80335-236">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="80335-237">docker image</span><span class="sxs-lookup"><span data-stu-id="80335-237">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="80335-238">リソースをクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="80335-238">Clean up resources</span></span>

<span data-ttu-id="80335-239">このチュートリアルでは、コンテナーとイメージを作成しました。</span><span class="sxs-lookup"><span data-stu-id="80335-239">During this tutorial you created containers and images.</span></span> <span data-ttu-id="80335-240">必要な場合は、これらのリソースを削除します。</span><span class="sxs-lookup"><span data-stu-id="80335-240">If you want, delete these resources.</span></span> <span data-ttu-id="80335-241">次のコマンドを使います</span><span class="sxs-lookup"><span data-stu-id="80335-241">Use the following commands to</span></span>

01. <span data-ttu-id="80335-242">すべてのコンテナーを一覧表示します</span><span class="sxs-lookup"><span data-stu-id="80335-242">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="80335-243">実行しているコンテナーを停止します。</span><span class="sxs-lookup"><span data-stu-id="80335-243">Stop containers that are running.</span></span> <span data-ttu-id="80335-244">`CONTAINER_NAME` は、コンテナーに自動的に割り当てられた名前を表します。</span><span class="sxs-lookup"><span data-stu-id="80335-244">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="80335-245">コンテナーを削除します</span><span class="sxs-lookup"><span data-stu-id="80335-245">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="80335-246">次に、コンピューターに残しておきたくないイメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="80335-246">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="80335-247">*Dockerfile* によって作成されたイメージを削除した後、*Dockerfile* が基にした .NET Core イメージを削除します。</span><span class="sxs-lookup"><span data-stu-id="80335-247">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="80335-248">**IMAGE ID** または **REPOSITORY:TAG** の書式に設定された文字列を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="80335-248">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="80335-249">インストールされているイメージの一覧を表示するには、`docker images` コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="80335-249">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="80335-250">イメージ ファイルは大きくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="80335-250">Image files can be large.</span></span> <span data-ttu-id="80335-251">普通、アプリのテスト中および開発中に作成した一時的なコンテナーは削除します。</span><span class="sxs-lookup"><span data-stu-id="80335-251">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="80335-252">通常、ランタイムがインストールされた基本イメージは、そのランタイムを基にして他のイメージをビルドする予定がある場合は、残しておきます。</span><span class="sxs-lookup"><span data-stu-id="80335-252">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80335-253">次の手順</span><span class="sxs-lookup"><span data-stu-id="80335-253">Next steps</span></span>

* [<span data-ttu-id="80335-254">ASP.NET Core マイクロサービスのチュートリアルを試します。</span><span class="sxs-lookup"><span data-stu-id="80335-254">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [<span data-ttu-id="80335-255">コンテナーをサポートする Azure サービスを確認します。</span><span class="sxs-lookup"><span data-stu-id="80335-255">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
* [<span data-ttu-id="80335-256">Dockerfile のコマンドについて読みます。</span><span class="sxs-lookup"><span data-stu-id="80335-256">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
* [<span data-ttu-id="80335-257">Visual Studio 向けのコンテナー ツールを調べます</span><span class="sxs-lookup"><span data-stu-id="80335-257">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
