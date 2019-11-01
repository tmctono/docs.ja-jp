---
title: .NET Core コマンドライン インターフェイス (CLI) ツールを使用して NuGet パッケージを作成する
description: ’dotnet pack’ コマンドを使用して NuGet パッケージを作成する方法を説明します。
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 2d876f921d079972e2a638788195aa69a2423c49
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771937"
---
# <a name="how-to-create-a-nuget-package-with-net-core-command-line-interface-cli-tools"></a><span data-ttu-id="68a8d-103">.NET Core コマンド ライン インターフェイス (CLI) ツールを使用して NuGet パッケージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="68a8d-103">How to create a NuGet package with .NET Core command-line interface (CLI) tools</span></span>

> [!NOTE]
> <span data-ttu-id="68a8d-104">以下は、Unix を使用する場合のコマンド ライン サンプルです。</span><span class="sxs-lookup"><span data-stu-id="68a8d-104">The following shows command-line samples using Unix.</span></span> <span data-ttu-id="68a8d-105">ここに示されている `dotnet pack` コマンドは Windows でも同じように機能します。</span><span class="sxs-lookup"><span data-stu-id="68a8d-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="68a8d-106">.NET Standard ライブラリと .NET Core ライブラリは NuGet パッケージとして配布されることが期待されています。</span><span class="sxs-lookup"><span data-stu-id="68a8d-106">.NET Standard and .NET Core libraries are expected to be distributed as NuGet packages.</span></span> <span data-ttu-id="68a8d-107">実際に、.NET Standard ライブラリはすべてそのように配布され、使用されています。</span><span class="sxs-lookup"><span data-stu-id="68a8d-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span> <span data-ttu-id="68a8d-108">`dotnet pack` コマンドを使用して行うのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="68a8d-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="68a8d-109">たとえば、NuGet 経由で配布する新しい優れたライブラリを作成したとします。</span><span class="sxs-lookup"><span data-stu-id="68a8d-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span> <span data-ttu-id="68a8d-110">クロス プラットフォーム ツールを使用して NuGet パッケージを作成すれば、正確に実行できます。</span><span class="sxs-lookup"><span data-stu-id="68a8d-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span> <span data-ttu-id="68a8d-111">次の例では、`netstandard1.0` をターゲットとする **SuperAwesomeLibrary** というライブラリを想定します。</span><span class="sxs-lookup"><span data-stu-id="68a8d-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="68a8d-112">推移的依存関係がある (つまり、別のパッケージに依存するプロジェクトがある) 場合、NuGet パッケージを作成する前に `dotnet restore` コマンドでソリューション全体のパッケージを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68a8d-112">If you have transitive dependencies; that is, a project which depends on another package, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span> <span data-ttu-id="68a8d-113">そうしないと、`dotnet pack` コマンドが正しく機能しません。</span><span class="sxs-lookup"><span data-stu-id="68a8d-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="68a8d-114">パッケージが復元されたことを確認したら、以下のコマンドを実行してライブラリがあるディレクトリに移動できます。</span><span class="sxs-lookup"><span data-stu-id="68a8d-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

```console
cd src/SuperAwesomeLibrary
```

<span data-ttu-id="68a8d-115">その後、コマンド ラインから以下の 1 つのコマンドのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="68a8d-115">Then it's just a single command from the command line:</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="68a8d-116">これで */bin/Debug* フォルダーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="68a8d-116">Your */bin/Debug* folder will now look like this:</span></span>

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="68a8d-117">この場合、デバッグ可能なパッケージが生成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="68a8d-117">Note that this will produce a package which is capable of being debugged.</span></span> <span data-ttu-id="68a8d-118">リリース バイナリと共に NuGet パッケージをビルドする場合、必要なのは、`--configuration` (または `-c`) スイッチを追加し、引数として `release` を使用することだけです。</span><span class="sxs-lookup"><span data-stu-id="68a8d-118">If you want to build a NuGet package with release binaries, all you need to do is add the `--configuration` (or `-c`) switch and use `release` as the argument.</span></span>

```dotnetcli
dotnet pack --configuration release
```

<span data-ttu-id="68a8d-119">これで、 */bin* フォルダーに、NuGet パッケージとリリース バイナリを含む *release* フォルダーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="68a8d-119">Your */bin* folder will now have a *release* folder containing your NuGet package with release binaries:</span></span>

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="68a8d-120">これで、NuGet パッケージを発行するために必要なファイルが準備できました。</span><span class="sxs-lookup"><span data-stu-id="68a8d-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="68a8d-121">`dotnet pack`と `dotnet publish` を混同しないようにしてください</span><span class="sxs-lookup"><span data-stu-id="68a8d-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="68a8d-122">ここで `dotnet publish` コマンドを使用しても意味がありません。</span><span class="sxs-lookup"><span data-stu-id="68a8d-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span> <span data-ttu-id="68a8d-123">`dotnet publish` コマンドは、同じバンドルにすべての依存関係があるアプリケーションを配置するためのものであり、NuGet 経由で配布して使用する NuGet パッケージを生成するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="68a8d-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -- not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

## <a name="see-also"></a><span data-ttu-id="68a8d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="68a8d-124">See also</span></span>

- [<span data-ttu-id="68a8d-125">クイック スタート:パッケージの作成と公開</span><span class="sxs-lookup"><span data-stu-id="68a8d-125">Quickstart: Create and publish a package</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
