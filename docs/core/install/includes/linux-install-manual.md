---
ms.openlocfilehash: e7d35045892c62f759aad5067962ac5c15a9fb8b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602700"
---

<span data-ttu-id="a929e-101">.NET Core SDK と .NET Core ランタイムはどちらも、ダウンロード後に手動でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a929e-101">Both .NET Core SDK and .NET Core Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="a929e-102">.NET Core SDK をインストールする場合、対応するランタイムをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a929e-102">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="a929e-103">まず、次のいずれかのサイトから SDK またはランタイムのバイナリ リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a929e-103">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="a929e-104">✔️ [.NET 5.0 preview のダウンロード](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="a929e-104">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="a929e-105">✔️ [.NET Core 3.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="a929e-105">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="a929e-106">❌ [.NET Core 3.0 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span><span class="sxs-lookup"><span data-stu-id="a929e-106">❌ [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span></span>
- <span data-ttu-id="a929e-107">❌ [.NET Core 2.2 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.2)</span><span class="sxs-lookup"><span data-stu-id="a929e-107">❌ [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2)</span></span>
- <span data-ttu-id="a929e-108">✔️ [.NET Core 2.1 のダウンロード](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="a929e-108">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>

<span data-ttu-id="a929e-109">次に、ダウンロードしたファイルを抽出し、`export` コマンドを使用して .NET Core で使用される変数を設定してから、.NET Core が PATH に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a929e-109">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="a929e-110">ランタイムを抽出し、.NET Core CLI コマンドをターミナルで使用できるようにするには、最初に .NET Core のバイナリ リリースをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a929e-110">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="a929e-111">次に、ターミナルを開き、ファイルが保存されているディレクトリから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a929e-111">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="a929e-112">上記の `export` コマンドでは、それを実行したターミナル セッションでのみ .NET Core CLI コマンドを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a929e-112">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="a929e-113">シェル プロファイルを編集して、コマンドを永続的に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a929e-113">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="a929e-114">Linux ではさまざまなシェルを使用でき、それぞれに異なるプロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="a929e-114">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="a929e-115">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a929e-115">For example:</span></span>
>
> - <span data-ttu-id="a929e-116">**Bash シェル**: *~/.bash_profile*、 *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="a929e-116">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="a929e-117">**Korn シェル**: *~/.kshrc* または *.profile*</span><span class="sxs-lookup"><span data-stu-id="a929e-117">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="a929e-118">**Z シェル**: *~/.zshrc* または *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="a929e-118">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="a929e-119">シェルの適切なソース ファイルを編集し、既存の `PATH` ステートメントの末尾に `:$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="a929e-119">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="a929e-120">`PATH` ステートメントが含まれていない場合は、`export PATH=$PATH:$HOME/dotnet` を含む新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a929e-120">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="a929e-121">また、ファイルの末尾に `export DOTNET_ROOT=$HOME/dotnet` を追加します。</span><span class="sxs-lookup"><span data-stu-id="a929e-121">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="a929e-122">この方法では、別々の場所に異なるバージョンをインストールして、どのアプリケーションにどれを使用するかを明示的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="a929e-122">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>
