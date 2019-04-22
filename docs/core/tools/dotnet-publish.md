---
title: dotnet publish コマンド
description: dotnet publish コマンドは、.NET Core プロジェクトをディレクトリに発行します。
ms.date: 05/29/2018
ms.openlocfilehash: 24490bd0fbfca65692d7025b5ed2aea659c35473
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611550"
---
# <a name="dotnet-publish"></a><span data-ttu-id="688b1-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="688b1-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="688b1-104">name</span><span class="sxs-lookup"><span data-stu-id="688b1-104">Name</span></span>

<span data-ttu-id="688b1-105">`dotnet publish` - ホスティング システムへの展開のため、アプリケーションとその依存関係をフォルダーにパックします。</span><span class="sxs-lookup"><span data-stu-id="688b1-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="688b1-106">構文</span><span class="sxs-lookup"><span data-stu-id="688b1-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="688b1-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="688b1-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="688b1-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="688b1-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="688b1-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="688b1-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="688b1-110">説明</span><span class="sxs-lookup"><span data-stu-id="688b1-110">Description</span></span>

<span data-ttu-id="688b1-111">`dotnet publish` はアプリケーションをコンパイルし、プロジェクト ファイルに指定されたその依存関係を読み取り、結果のファイル セットをディレクトリに発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="688b1-112">出力には次のアセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="688b1-112">The output includes the following assets:</span></span>

* <span data-ttu-id="688b1-113">アセンブリの中間言語 (IL) コード (*dll* 拡張子)。</span><span class="sxs-lookup"><span data-stu-id="688b1-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="688b1-114">*.deps.json* ファイル。プロジェクトのすべての依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="688b1-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="688b1-115">*.runtime.config.json* ファイル。アプリケーションが想定する共有ランタイムと、ランタイムの他の構成オプション (ガベージ コレクションの種類など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="688b1-116">アプリケーションの依存関係。NuGet キャッシュから出力フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="688b1-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="688b1-117">`dotnet publish` コマンドの出力は、実行のためにホスト システム (サーバー、PC、Mac、ラップトップなど) にすぐに展開できます。</span><span class="sxs-lookup"><span data-stu-id="688b1-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="688b1-118">これは、アプリケーションの展開を準備するための正式にサポートされている唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="688b1-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="688b1-119">プロジェクトに指定されている展開の種類によっては、ホスティング システムに .NET Core 共有ランタイムがインストールされている場合とされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="688b1-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="688b1-120">詳しくは、「[.NET Core アプリケーション展開](../deploying/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="688b1-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="688b1-121">発行されるアプリケーションのディレクトリ構造については、「[Directory structure](/aspnet/core/hosting/directory-structure)」 (ディレクトリ構造) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="688b1-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="688b1-122">引数</span><span class="sxs-lookup"><span data-stu-id="688b1-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="688b1-123">発行するプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="688b1-123">The project to publish.</span></span> <span data-ttu-id="688b1-124">これは、[C#](csproj.md)、F#、または Visual Basic のプロジェクト ファイルのパスおよびファイル名か、C#、F#、または Visual Basic のプロジェクト ファイルを含むディレクトリへのパスです。</span><span class="sxs-lookup"><span data-stu-id="688b1-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="688b1-125">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="688b1-126">オプション</span><span class="sxs-lookup"><span data-stu-id="688b1-126">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="688b1-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="688b1-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="688b1-128">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="688b1-128">Defines the build configuration.</span></span> <span data-ttu-id="688b1-129">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="688b1-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="688b1-130">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="688b1-131">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="688b1-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="688b1-132">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="688b1-133">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="688b1-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="688b1-134">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="688b1-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="688b1-135">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="688b1-136">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="688b1-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="688b1-137">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="688b1-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="688b1-138">このオプションは、.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="688b1-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="688b1-139">発行の前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="688b1-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="688b1-140">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="688b1-141">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="688b1-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="688b1-142">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="688b1-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="688b1-143">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="688b1-144">指定しないと、既定で、フレームワークに依存する展開の場合は *./bin/[configuration]/[framework]/publish/* に、自己完結型の展開の場合は *./bin/[configuration]/[framework]/[runtime]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="688b1-145">パスが相対的である場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="688b1-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="688b1-146">アプリケーションと一緒に .NET Core ランタイムを発行します。これにより、ランタイムをターゲット コンピューターにインストールする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="688b1-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="688b1-147">ランタイム識別子を指定した場合、その既定値は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="688b1-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="688b1-148">さまざまな展開方法の詳細については、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="688b1-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="688b1-149">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="688b1-150">これは、[自己完結型の展開 (SCD)](../deploying/index.md#self-contained-deployments-scd) を作成するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="688b1-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="688b1-151">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="688b1-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="688b1-152">既定では、[フレームワークに依存する展開 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) が発行されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="688b1-153">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="688b1-154">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="688b1-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="688b1-155">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="688b1-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="688b1-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="688b1-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="688b1-157">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="688b1-157">Defines the build configuration.</span></span> <span data-ttu-id="688b1-158">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="688b1-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="688b1-159">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="688b1-160">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="688b1-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="688b1-161">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="688b1-162">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="688b1-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="688b1-163">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="688b1-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="688b1-164">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="688b1-165">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="688b1-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="688b1-166">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="688b1-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="688b1-167">このオプションは、.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="688b1-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="688b1-168">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="688b1-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="688b1-169">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="688b1-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="688b1-170">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="688b1-171">指定しないと、既定で、フレームワークに依存する展開の場合は *./bin/[configuration]/[framework]/publish/* に、自己完結型の展開の場合は *./bin/[configuration]/[framework]/[runtime]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="688b1-172">パスが相対的である場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="688b1-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="688b1-173">アプリケーションと一緒に .NET Core ランタイムを発行します。これにより、ランタイムをターゲット コンピューターにインストールする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="688b1-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="688b1-174">ランタイム識別子を指定した場合、その既定値は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="688b1-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="688b1-175">さまざまな展開方法の詳細については、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="688b1-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="688b1-176">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="688b1-177">これは、[自己完結型の展開 (SCD)](../deploying/index.md#self-contained-deployments-scd) を作成するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="688b1-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="688b1-178">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="688b1-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="688b1-179">既定では、[フレームワークに依存する展開 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) が発行されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="688b1-180">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="688b1-181">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="688b1-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="688b1-182">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="688b1-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="688b1-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="688b1-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="688b1-184">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="688b1-184">Defines the build configuration.</span></span> <span data-ttu-id="688b1-185">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="688b1-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="688b1-186">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="688b1-187">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="688b1-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="688b1-188">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="688b1-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="688b1-189">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="688b1-190">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="688b1-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="688b1-191">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="688b1-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="688b1-192">このオプションは、.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="688b1-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="688b1-193">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="688b1-194">指定しないと、既定で、フレームワークに依存する展開の場合は *./bin/[configuration]/[framework]/publish/* に、自己完結型の展開の場合は *./bin/[configuration]/[framework]/[runtime]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="688b1-195">パスが相対的である場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="688b1-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="688b1-196">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="688b1-197">これは、[自己完結型の展開 (SCD)](../deploying/index.md#self-contained-deployments-scd) を作成するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="688b1-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="688b1-198">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="688b1-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="688b1-199">既定では、[フレームワークに依存する展開 (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) が発行されます。</span><span class="sxs-lookup"><span data-stu-id="688b1-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="688b1-200">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="688b1-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="688b1-201">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="688b1-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="688b1-202">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="688b1-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="688b1-203">使用例</span><span class="sxs-lookup"><span data-stu-id="688b1-203">Examples</span></span>

<span data-ttu-id="688b1-204">現在のディレクトリのプロジェクトを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="688b1-205">指定されたプロジェクト ファイルを使用して、アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="688b1-206">`netcoreapp1.1` フレームワークを使って現在のディレクトリ内のプロジェクトを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="688b1-207">`netcoreapp1.1` フレームワークと `OS X 10.10` のランタイム (この RID はプロジェクト ファイルに列挙しておく必要があります) を使って、現在のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="688b1-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="688b1-208">現在のアプリケーションを発行します。ただし、復元操作中はルート プロジェクトのみを復元し、プロジェクト間 (P2P) 参照は復元しないでください (.NET Core SDK 2.0 以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="688b1-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="688b1-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="688b1-209">See also</span></span>

- [<span data-ttu-id="688b1-210">ターゲット フレームワーク</span><span class="sxs-lookup"><span data-stu-id="688b1-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="688b1-211">ランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="688b1-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
