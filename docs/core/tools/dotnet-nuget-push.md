---
title: dotnet nuget push コマンド
description: dotnet nuget push コマンドでは、パッケージをサーバーにプッシュして発行します。
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 1e7831de4c041591b3602e405418f89f1d1d27d1
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895455"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="0bc6b-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="0bc6b-103">dotnet nuget push</span></span>

<span data-ttu-id="0bc6b-104">**この記事の対象:** ✔️ .NET Core 2.x SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="0bc6b-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0bc6b-105">名前</span><span class="sxs-lookup"><span data-stu-id="0bc6b-105">Name</span></span>

<span data-ttu-id="0bc6b-106">`dotnet nuget push` - パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0bc6b-107">構文</span><span class="sxs-lookup"><span data-stu-id="0bc6b-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a><span data-ttu-id="0bc6b-108">説明</span><span class="sxs-lookup"><span data-stu-id="0bc6b-108">Description</span></span>

<span data-ttu-id="0bc6b-109">`dotnet nuget push` コマンドは、パッケージをサーバーにプッシュして発行します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="0bc6b-110">プッシュ コマンドでは、システムの NuGet 構成ファイル、または構成ファイルのチェーンで検出されたサーバーと資格情報の詳細を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="0bc6b-111">構成ファイルの詳細については、「[Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior)」 (NuGet 動作を構成する) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="0bc6b-112">NuGet の既定の構成は、 *%AppData%\NuGet\NuGet.config* (Windows) または *$HOME/.local/share* (Linux/macOS) を読み込み、次にドライブのルートから開始され、現在のディレクトリで終わる、任意の *nuget.config* または *.nuget\nuget.config* を読み込むことによって取得されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

<span data-ttu-id="0bc6b-113">このコマンドにより、既存のパッケージがプッシュされます。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-113">The command pushes an existing package.</span></span> <span data-ttu-id="0bc6b-114">パッケージは作成されません。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-114">It doesn't create a package.</span></span> <span data-ttu-id="0bc6b-115">パッケージを作成するには、[`dotnet pack`](dotnet-pack.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-115">To create a package, use [`dotnet pack`](dotnet-pack.md).</span></span>

## <a name="arguments"></a><span data-ttu-id="0bc6b-116">引数</span><span class="sxs-lookup"><span data-stu-id="0bc6b-116">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="0bc6b-117">プッシュされるパッケージのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-117">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="0bc6b-118">オプション</span><span class="sxs-lookup"><span data-stu-id="0bc6b-118">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="0bc6b-119">メモリ使用量を削減するために、HTTP(S) サーバーにプッシュするときのバッファリングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="0bc6b-120">インバリアントの英語ベースのカルチャを使用して、アプリケーションの実行を強制します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-120">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0bc6b-121">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="0bc6b-122">コマンドが認証などの操作をブロックして、手動アクションを要求することを許可します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-122">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="0bc6b-123">.NET Core 2.2 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-123">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="0bc6b-124">サーバーの API キーです。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-124">The API key for the server.</span></span>

- **`-n|--no-symbols`**

  <span data-ttu-id="0bc6b-125">シンボルをプッシュしません (存在する場合でも)。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-125">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="0bc6b-126">ソース URL に "api/v2/package" を追加しません。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-126">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="0bc6b-127">.NET Core 2.1 SDK 以降、使用できるオプションです。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-127">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="0bc6b-128">サーバー URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-128">Specifies the server URL.</span></span> <span data-ttu-id="0bc6b-129">`DefaultPushSource` 構成値が NuGet 構成ファイルに設定されない限り、このオプションは必須です。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-129">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="0bc6b-130">複数のパッケージを HTTP(S) サーバーにプッシュする場合は、すべての 409 競合応答を警告として処理して、プッシュを続行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-130">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="0bc6b-131">.NET Core 3.1 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-131">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="0bc6b-132">シンボル サーバーの API キーです。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-132">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="0bc6b-133">シンボル サーバーの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-133">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="0bc6b-134">秒単位でサーバーにプッシュする場合のタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-134">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="0bc6b-135">既定値は 300 秒 (5 分) です。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-135">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="0bc6b-136">0 (0 秒) を指定すると、既定値が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-136">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="0bc6b-137">使用例</span><span class="sxs-lookup"><span data-stu-id="0bc6b-137">Examples</span></span>

- <span data-ttu-id="0bc6b-138">API キーを指定して、既定のプッシュ ソースに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-138">Push *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="0bc6b-139">API キーを指定して、公式 NuGet サーバーに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-139">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="0bc6b-140">API キーを指定して、カスタム プッシュ ソース `https://customsource` に *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-140">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="0bc6b-141">既定のプッシュ ソースに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-141">Push *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="0bc6b-142">既定のシンボル ソースに *foo.symbols.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-142">Push *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="0bc6b-143">360 秒のタイムアウトを指定して、既定のプッシュ ソースに *foo.nupkg* をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-143">Push *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="0bc6b-144">既定のプッシュ ソースに現在のディレクトリ内のすべての *.nupkg* ファイルをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-144">Push all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="0bc6b-145">このコマンドがうまくいかない場合は、古いバージョンの SDK (.NET Core 2.1 SDK 以前のバージョン) に存在したバグが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-145">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="0bc6b-146">これを解決するには、SDK のバージョンをアップグレードするか、代わりに次のコマンドを実行します: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="0bc6b-146">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

- <span data-ttu-id="0bc6b-147">HTTP(S) サーバーによって 409 競合応答が返された場合でも、すべての *.nupkg* ファイルをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-147">Push all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```

- <span data-ttu-id="0bc6b-148">ローカル フィード ディレクトリに現在のディレクトリ内のすべての *.nupkg* ファイルをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-148">Push all *.nupkg* files in the current directory to a local feed directory:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg -s c:\mydir
  ```

  <span data-ttu-id="0bc6b-149">このコマンドでは、パッケージが階層フォルダー構造に格納されないため、パフォーマンスを最適化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-149">This command doesn't store packages in a hierarchical folder structure, which is recommended to optimize performance.</span></span> <span data-ttu-id="0bc6b-150">詳細については、[ローカル フィード](/nuget/hosting-packages/local-feeds)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bc6b-150">For more information, see [Local feeds](/nuget/hosting-packages/local-feeds).</span></span>  
