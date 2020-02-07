---
title: dotnet nuget push コマンド
description: dotnet nuget push コマンドでは、パッケージをサーバーにプッシュして発行します。
author: karann-msft
ms.date: 12/04/2019
ms.openlocfilehash: a352120efa199b871e67eb8ba2442bd69a9fc4ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789879"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="6593b-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="6593b-103">dotnet nuget push</span></span>

<span data-ttu-id="6593b-104">**この記事の対象:** ✔️ .NET Core 1.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="6593b-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="6593b-105">名前</span><span class="sxs-lookup"><span data-stu-id="6593b-105">Name</span></span>

<span data-ttu-id="6593b-106">`dotnet nuget push` - パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="6593b-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6593b-107">構文</span><span class="sxs-lookup"><span data-stu-id="6593b-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [--skip-duplicate] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="6593b-108">説明</span><span class="sxs-lookup"><span data-stu-id="6593b-108">Description</span></span>

<span data-ttu-id="6593b-109">`dotnet nuget push` コマンドは、パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="6593b-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="6593b-110">プッシュ コマンドでは、システムの NuGet 構成ファイル、または構成ファイルのチェーンで検出されたサーバーと資格情報の詳細を使用します。</span><span class="sxs-lookup"><span data-stu-id="6593b-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="6593b-111">構成ファイルの詳細については、「[Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)」 (NuGet 動作を構成する) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6593b-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="6593b-112">NuGet の既定の構成は、 *%AppData%\NuGet\NuGet.config* (Windows) または *$HOME/.local/share* (Linux/macOS) を読み込み、次にドライブのルートから開始され、現在のディレクトリで終わる、任意の *nuget.config* または *.nuget\nuget.config* を読み込むことによって取得されます。</span><span class="sxs-lookup"><span data-stu-id="6593b-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="6593b-113">引数</span><span class="sxs-lookup"><span data-stu-id="6593b-113">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="6593b-114">プッシュされるパッケージのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6593b-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="6593b-115">オプション</span><span class="sxs-lookup"><span data-stu-id="6593b-115">Options</span></span>

* **`-d|--disable-buffering`**

  <span data-ttu-id="6593b-116">メモリ使用量を削減するために、HTTP(S) サーバーにプッシュするときのバッファリングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6593b-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="6593b-117">インバリアントの英語ベースのカルチャを使用して、アプリケーションの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="6593b-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="6593b-118">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="6593b-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="6593b-119">コマンドが認証などの操作をブロックして、手動アクションを要求することを許可します。</span><span class="sxs-lookup"><span data-stu-id="6593b-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="6593b-120">.NET Core 2.2 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="6593b-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="6593b-121">サーバーの API キーです。</span><span class="sxs-lookup"><span data-stu-id="6593b-121">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="6593b-122">シンボルをプッシュしません (存在する場合でも)。</span><span class="sxs-lookup"><span data-stu-id="6593b-122">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="6593b-123">ソース URL に "api/v2/package" を追加しません。</span><span class="sxs-lookup"><span data-stu-id="6593b-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="6593b-124">.NET Core 2.1 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="6593b-124">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="6593b-125">サーバー URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="6593b-125">Specifies the server URL.</span></span> <span data-ttu-id="6593b-126">`DefaultPushSource` 構成値が NuGet 構成ファイルに設定されない限り、このオプションは必須です。</span><span class="sxs-lookup"><span data-stu-id="6593b-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`--skip-duplicate`**

  <span data-ttu-id="6593b-127">複数のパッケージを HTTP(S) サーバーにプッシュする場合は、すべての 409 競合応答を警告として処理して、プッシュを続行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6593b-127">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="6593b-128">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="6593b-128">Available since .NET Core 3.1 SDK.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="6593b-129">シンボル サーバーの API キーです。</span><span class="sxs-lookup"><span data-stu-id="6593b-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="6593b-130">シンボル サーバーの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="6593b-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="6593b-131">秒単位でサーバーにプッシュする場合のタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6593b-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="6593b-132">既定値は 300 秒 (5 分) です。</span><span class="sxs-lookup"><span data-stu-id="6593b-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="6593b-133">0 (0 秒) を指定すると、既定値が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6593b-133">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="6593b-134">使用例</span><span class="sxs-lookup"><span data-stu-id="6593b-134">Examples</span></span>

* <span data-ttu-id="6593b-135">API キーを指定して、既定のプッシュ ソースに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-135">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="6593b-136">API キーを指定して、公式 NuGet サーバーに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-136">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="6593b-137">API キーを指定して、カスタム プッシュ ソース `https://customsource` に *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-137">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="6593b-138">既定のプッシュ ソースに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-138">Pushes *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="6593b-139">既定のシンボル ソースに *foo.symbols.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-139">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="6593b-140">360 秒のタイムアウトを指定して、既定のプッシュ ソースに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-140">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="6593b-141">既定のプッシュ ソースに現在のディレクトリ内のすべての *.nupkg* ファイルをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-141">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="6593b-142">このコマンドがうまくいかない場合は、古いバージョンの SDK (.NET Core 2.1 SDK 以前のバージョン) に存在したバグが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6593b-142">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="6593b-143">これを解決するには、SDK のバージョンをアップグレードするか、代わりに次のコマンドを実行します: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="6593b-143">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

* <span data-ttu-id="6593b-144">HTTP(S) サーバーによって 409 競合応答が返された場合でも、すべての *.nupkg* ファイルをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="6593b-144">Pushes all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```
