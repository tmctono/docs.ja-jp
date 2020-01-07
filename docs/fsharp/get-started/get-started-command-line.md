---
title: コマンドラインツールF#を使って作業を開始する
description: 任意のオペレーティングシステム (Windows、macOS、またはF# Linux) で .NET Core CLI を使用することにより、シンプルなマルチプロジェクトソリューションを構築する方法について説明します。
ms.date: 03/26/2018
ms.openlocfilehash: aa3ed84660a951eeafc11a00ea3831f587b6d876
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559488"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="2b224-103">.NET Core CLI のF#使用を開始する</span><span class="sxs-lookup"><span data-stu-id="2b224-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="2b224-104">この記事では、.NET Core CLI を使用しF#て、任意のオペレーティングシステム (Windows、macOS、または Linux) でを開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b224-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="2b224-105">コンソールアプリケーションによって呼び出されるクラスライブラリを使用して、複数のプロジェクトから成るソリューションを構築します。</span><span class="sxs-lookup"><span data-stu-id="2b224-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2b224-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="2b224-106">Prerequisites</span></span>

<span data-ttu-id="2b224-107">まず、最新の[.NET Core SDK](https://dotnet.microsoft.com/download)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b224-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="2b224-108">この記事では、コマンドラインの使用方法を理解し、適切なテキストエディターを使用することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2b224-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="2b224-109">まだ使用していない場合は、のF#テキストエディターとして [Visual Studio Code](get-started-vscode.md) が最適なオプションです。</span><span class="sxs-lookup"><span data-stu-id="2b224-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="2b224-110">単純な複数プロジェクトソリューションの構築</span><span class="sxs-lookup"><span data-stu-id="2b224-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="2b224-111">コマンドプロンプト/ターミナルを開き、 [dotnet new](../../core/tools/dotnet-new.md)コマンドを使用して `FSNetCore`という名前の新しいソリューションファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b224-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="2b224-112">前のコマンドを実行すると、次のディレクトリ構造が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2b224-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="2b224-113">クラスライブラリを記述する</span><span class="sxs-lookup"><span data-stu-id="2b224-113">Write a class library</span></span>

<span data-ttu-id="2b224-114">ディレクトリを*Fsnetcore*に変更します。</span><span class="sxs-lookup"><span data-stu-id="2b224-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="2b224-115">`dotnet new` コマンドを使用して、"Library" という名前の**src**フォルダーにクラスライブラリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b224-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="2b224-116">前のコマンドを実行すると、次のディレクトリ構造が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2b224-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="2b224-117">`Library.fs` の内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2b224-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="2b224-118">ライブラリプロジェクトに Newtonsoft. Json パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b224-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="2b224-119">[Dotnet sln add](../../core/tools/dotnet-sln.md)コマンドを使用して、`Library` プロジェクトを `FSNetCore` ソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="2b224-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="2b224-120">`dotnet build` を実行してプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2b224-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="2b224-121">未解決の依存関係は、ビルド時に復元されます。</span><span class="sxs-lookup"><span data-stu-id="2b224-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="2b224-122">クラスライブラリを使用するコンソールアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="2b224-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="2b224-123">`dotnet new` コマンドを使用して、App という名前の**src**フォルダーにコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b224-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="2b224-124">前のコマンドを実行すると、次のディレクトリ構造が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2b224-124">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="2b224-125">`Program.fs` ファイルの内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2b224-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

<span data-ttu-id="2b224-126">[Dotnet add reference](../../core/tools/dotnet-add-reference.md)を使用して、`Library` プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="2b224-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="2b224-127">`dotnet sln add` コマンドを使用して、`FSNetCore` ソリューションに `App` プロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="2b224-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="2b224-128">NuGet の依存関係を復元し、`dotnet restore` `dotnet build` 実行してプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2b224-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="2b224-129">ディレクトリを `src/App` コンソールプロジェクトに変更し、`Hello World` を引数として渡してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b224-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="2b224-130">次のような結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b224-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="2b224-131">次のステップ:</span><span class="sxs-lookup"><span data-stu-id="2b224-131">Next steps</span></span>

<span data-ttu-id="2b224-132">次に、さまざまなF#機能の詳細については、「」[のF#ツアー](../tour.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b224-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
