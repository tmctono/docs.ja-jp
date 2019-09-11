---
title: コマンド ライン ツールの F# の概要します。
description: 任意のオペレーティング システム (Windows、macOs または Linux) で .NET Core CLI を使用した F# で簡単なマルチ プロジェクト ソリューションを構築する方法について説明します。
ms.date: 03/26/2018
ms.openlocfilehash: 1376b6b5384f380c06a96cdc568ad108de8a6e5f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855827"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="a2a9a-103">.NET Core CLI を使用した F# の概要します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="a2a9a-104">この記事では、どのできますを開始する F# .NET Core CLI を使用したオペレーティング システム (Windows、macOS、または Linux) でについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="a2a9a-105">コンソールアプリケーションによって呼び出されるクラスライブラリを使用して、複数のプロジェクトから成るソリューションを構築します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a2a9a-106">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a2a9a-106">Prerequisites</span></span>

<span data-ttu-id="a2a9a-107">まず、最新の[.NET Core SDK](https://dotnet.microsoft.com/download)をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="a2a9a-108">この記事では、コマンドラインの使用方法を理解し、適切なテキストエディターを使用することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="a2a9a-109">それを既に使用しない場合[Visual Studio Code](get-started-vscode.md) F# 用のテキスト エディターとして便利なオプションです。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="a2a9a-110">単純な複数プロジェクトソリューションの構築</span><span class="sxs-lookup"><span data-stu-id="a2a9a-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="a2a9a-111">コマンドプロンプト/ターミナルを開き、 [dotnet new](../../core/tools/dotnet-new.md)コマンドを使用して、という名前`FSNetCore`の新しいソリューションファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="a2a9a-112">前のコマンドを実行すると、次のディレクトリ構造が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="a2a9a-113">クラスライブラリを記述する</span><span class="sxs-lookup"><span data-stu-id="a2a9a-113">Write a class library</span></span>

<span data-ttu-id="a2a9a-114">ディレクトリを*Fsnetcore*に変更します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="a2a9a-115">コマンドを`dotnet new`使用して、"ライブラリ" という名前の**src**フォルダーにクラスライブラリプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="a2a9a-116">前のコマンドを実行すると、次のディレクトリ構造が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="a2a9a-117">の`Library.fs`内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="a2a9a-118">ライブラリプロジェクトに Newtonsoft. Json パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="a2a9a-119">[Dotnet sln add](../../core/tools/dotnet-sln.md)コマンドを`FSNetCore`使用して、ソリューションにプロジェクトを追加します。`Library`</span><span class="sxs-lookup"><span data-stu-id="a2a9a-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="a2a9a-120">を`dotnet build`実行してプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="a2a9a-121">未解決の依存関係は、ビルド時に復元されます。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="a2a9a-122">クラスライブラリを使用するコンソールアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="a2a9a-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="a2a9a-123">コマンドを`dotnet new`使用して、App という名前の**src**フォルダーにコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="a2a9a-124">前のコマンドを実行すると、次のディレクトリ構造が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="a2a9a-125">`Program.fs`ファイルの内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="a2a9a-126">[Dotnet add reference](../../core/tools/dotnet-add-reference.md)を使用`Library`して、プロジェクトへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="a2a9a-127">次の`FSNetCore` `App` コマンドを使用して、`dotnet sln add`ソリューションにプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="a2a9a-128">NuGet の依存関係を`dotnet restore`復元し`dotnet build` 、を実行してプロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="a2a9a-129">`src/App`コンソールプロジェクトにディレクトリを変更し、引数とし`Hello World`てを渡してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="a2a9a-130">次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="a2a9a-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="a2a9a-131">Next steps</span></span>

<span data-ttu-id="a2a9a-132">次に、チェック アウト、 [F# のツアー](../tour.md)を F# のさまざまな機能の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2a9a-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
