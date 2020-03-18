---
title: .NET Core CLI を使用して NuGet パッケージを作成する
description: ’dotnet pack’ コマンドを使用して NuGet パッケージを作成する方法を説明します。
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 3f8e75a501cfc48e1c416f71e91290cab1a4ffae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920917"
---
# <a name="how-to-create-a-nuget-package-with-the-net-core-cli"></a><span data-ttu-id="b3ece-103">.NET Core CLI を使用して NuGet パッケージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b3ece-103">How to create a NuGet package with the .NET Core CLI</span></span>

> [!NOTE]
> <span data-ttu-id="b3ece-104">以下は、Unix を使用する場合のコマンド ライン サンプルです。</span><span class="sxs-lookup"><span data-stu-id="b3ece-104">The following shows command-line samples using Unix.</span></span> <span data-ttu-id="b3ece-105">ここに示されている `dotnet pack` コマンドは Windows でも同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="b3ece-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="b3ece-106">.NET Standard ライブラリと .NET Core ライブラリは NuGet パッケージとして配布されることが期待されています。</span><span class="sxs-lookup"><span data-stu-id="b3ece-106">.NET Standard and .NET Core libraries are expected to be distributed as NuGet packages.</span></span> <span data-ttu-id="b3ece-107">実際に、.NET Standard ライブラリはすべてそのように配布され、使用されています。</span><span class="sxs-lookup"><span data-stu-id="b3ece-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span> <span data-ttu-id="b3ece-108">`dotnet pack` コマンドを使用して行うのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="b3ece-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="b3ece-109">たとえば、NuGet 経由で配布する新しい優れたライブラリを作成したとします。</span><span class="sxs-lookup"><span data-stu-id="b3ece-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span> <span data-ttu-id="b3ece-110">クロス プラットフォーム ツールを使用して NuGet パッケージを作成すれば、正確に実行できます。</span><span class="sxs-lookup"><span data-stu-id="b3ece-110">You can create a NuGet package with cross-platform tools to do exactly that!</span></span> <span data-ttu-id="b3ece-111">次の例では、**をターゲットとする**SuperAwesomeLibrary`netstandard1.0` というライブラリを想定します。</span><span class="sxs-lookup"><span data-stu-id="b3ece-111">The following example assumes a library called **SuperAwesomeLibrary** that targets `netstandard1.0`.</span></span>

<span data-ttu-id="b3ece-112">推移的依存関係がある (つまり、別のパッケージに依存するプロジェクトがある) 場合、NuGet パッケージを作成する前に、`dotnet restore` コマンドを使用してソリューション全体のパッケージを必ず復元します。</span><span class="sxs-lookup"><span data-stu-id="b3ece-112">If you have transitive dependencies, that is, a project that depends on another package, make sure to restore packages for the entire solution with the `dotnet restore` command before you create a NuGet package.</span></span> <span data-ttu-id="b3ece-113">そうしないと、`dotnet pack` コマンドが正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-113">Failing to do so will result in the `dotnet pack` command not working properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="b3ece-114">パッケージが復元されたことを確認したら、以下のコマンドを実行してライブラリがあるディレクトリに移動できます。</span><span class="sxs-lookup"><span data-stu-id="b3ece-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

```console
cd src/SuperAwesomeLibrary
```

<span data-ttu-id="b3ece-115">その後、コマンド ラインから以下の 1 つのコマンドのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="b3ece-115">Then it's just a single command from the command line:</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="b3ece-116">これで */bin/Debug* フォルダーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b3ece-116">Your */bin/Debug* folder will now look like this:</span></span>

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="b3ece-117">これにより、デバッグ可能なパッケージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b3ece-117">This produces a package that is capable of being debugged.</span></span> <span data-ttu-id="b3ece-118">リリース バイナリと共に NuGet パッケージをビルドする場合、必要なのは、`--configuration` (または `-c`) スイッチを追加し、引数として `release` を使用することだけです。</span><span class="sxs-lookup"><span data-stu-id="b3ece-118">If you want to build a NuGet package with release binaries, all you need to do is add the `--configuration` (or `-c`) switch and use `release` as the argument.</span></span>

```dotnetcli
dotnet pack --configuration release
```

<span data-ttu-id="b3ece-119">これで、 */bin* フォルダーに、NuGet パッケージとリリース バイナリを含む *release* フォルダーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b3ece-119">Your */bin* folder will now have a *release* folder containing your NuGet package with release binaries:</span></span>

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="b3ece-120">これで、NuGet パッケージを発行するために必要なファイルが準備できました。</span><span class="sxs-lookup"><span data-stu-id="b3ece-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="b3ece-121">`dotnet pack`と `dotnet publish` を混同しないようにしてください</span><span class="sxs-lookup"><span data-stu-id="b3ece-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="b3ece-122">ここで `dotnet publish` コマンドを使用しても意味がありません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span> <span data-ttu-id="b3ece-123">`dotnet publish` コマンドは、同じバンドルにすべての依存関係があるアプリケーションを配置するためのものであり、NuGet 経由で配布して使用する NuGet パッケージを生成するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="b3ece-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -- not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3ece-124">参照</span><span class="sxs-lookup"><span data-stu-id="b3ece-124">See also</span></span>

- [<span data-ttu-id="b3ece-125">クイック スタート: パッケージの作成と公開</span><span class="sxs-lookup"><span data-stu-id="b3ece-125">Quickstart: Create and publish a package</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
