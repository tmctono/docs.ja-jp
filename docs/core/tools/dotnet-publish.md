---
title: dotnet publish コマンド
description: dotnet publish コマンドは、.NET Core プロジェクトをディレクトリに発行します。
ms.date: 05/29/2018
ms.openlocfilehash: 0653a7b1e1abd6d7ffd3d21a0410279235b43a28
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451293"
---
# <a name="dotnet-publish"></a><span data-ttu-id="acd8b-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="acd8b-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="acd8b-104">名前</span><span class="sxs-lookup"><span data-stu-id="acd8b-104">Name</span></span>

<span data-ttu-id="acd8b-105">`dotnet publish` - ホスティング システムへの展開のため、アプリケーションとその依存関係をフォルダーにパックします。</span><span class="sxs-lookup"><span data-stu-id="acd8b-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="acd8b-106">構文</span><span class="sxs-lookup"><span data-stu-id="acd8b-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="acd8b-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="acd8b-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20"></a>[<span data-ttu-id="acd8b-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="acd8b-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="acd8b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="acd8b-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="acd8b-110">説明</span><span class="sxs-lookup"><span data-stu-id="acd8b-110">Description</span></span>

<span data-ttu-id="acd8b-111">`dotnet publish` はアプリケーションをコンパイルし、プロジェクト ファイルに指定されたその依存関係を読み取り、結果のファイル セットをディレクトリに発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="acd8b-112">出力には次のアセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-112">The output includes the following assets:</span></span>

- <span data-ttu-id="acd8b-113">アセンブリの中間言語 (IL) コード (*dll* 拡張子)。</span><span class="sxs-lookup"><span data-stu-id="acd8b-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="acd8b-114">*.deps.json* ファイル。プロジェクトのすべての依存関係が含まれます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="acd8b-115">*.runtimeconfig.json* ファイル。アプリケーションが想定する共有ランタイムと、ランタイム用の他の構成オプション (ガベージ コレクションの種類など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-115">*.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="acd8b-116">アプリケーションの依存関係。NuGet キャッシュから出力フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="acd8b-117">`dotnet publish` コマンドの出力は、実行のためにホスト システム (サーバー、PC、Mac、ラップトップなど) にすぐに展開できます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="acd8b-118">これは、アプリケーションの展開を準備するための正式にサポートされている唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="acd8b-119">プロジェクトに指定されている展開の種類によっては、ホスティング システムに .NET Core 共有ランタイムがインストールされている場合とされていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="acd8b-120">詳しくは、「[.NET Core アプリケーション展開](../deploying/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acd8b-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="acd8b-121">発行されるアプリケーションのディレクトリ構造については、「[Directory structure](/aspnet/core/hosting/directory-structure)」 (ディレクトリ構造) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acd8b-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="acd8b-122">引数</span><span class="sxs-lookup"><span data-stu-id="acd8b-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="acd8b-123">発行するプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="acd8b-123">The project to publish.</span></span> <span data-ttu-id="acd8b-124">これは、[C#](csproj.md)、F#、または Visual Basic のプロジェクト ファイルのパスおよびファイル名か、C#、F#、または Visual Basic のプロジェクト ファイルを含むディレクトリへのパスです。</span><span class="sxs-lookup"><span data-stu-id="acd8b-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="acd8b-125">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="acd8b-126">オプション</span><span class="sxs-lookup"><span data-stu-id="acd8b-126">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="acd8b-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="acd8b-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="acd8b-128">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-128">Defines the build configuration.</span></span> <span data-ttu-id="acd8b-129">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="acd8b-130">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="acd8b-131">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="acd8b-132">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="acd8b-133">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="acd8b-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="acd8b-134">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="acd8b-135">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="acd8b-136">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="acd8b-137">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="acd8b-138">このオプションは、.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="acd8b-139">発行の前にプロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="acd8b-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="acd8b-140">また、`--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="acd8b-141">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="acd8b-142">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="acd8b-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="acd8b-143">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="acd8b-144">指定しないと、既定で、フレームワークに依存する展開の場合は *./bin/[configuration]/[framework]/publish/* に、自己完結型の展開の場合は *./bin/[configuration]/[framework]/[runtime]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="acd8b-145">パスが相対的である場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="acd8b-146">アプリケーションと一緒に .NET Core ランタイムを発行します。これにより、ランタイムをターゲット コンピューターにインストールする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="acd8b-147">ランタイム識別子を指定した場合、その既定値は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="acd8b-148">さまざまな展開方法の詳細については、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd8b-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="acd8b-149">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="acd8b-150">これは、[自己完結型の展開 (SCD)](../deploying/index.md#publish-self-contained) を作成するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="acd8b-151">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acd8b-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="acd8b-152">既定では、[フレームワークに依存する展開 (FDD)](../deploying/index.md#publish-runtime-dependent) が発行されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="acd8b-153">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="acd8b-154">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="acd8b-155">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="acd8b-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="acd8b-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="acd8b-157">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-157">Defines the build configuration.</span></span> <span data-ttu-id="acd8b-158">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="acd8b-159">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="acd8b-160">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="acd8b-161">最後の復元が成功した場合でも、すべての依存関係が強制的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="acd8b-162">このフラグを指定することは、*project.assets.json* ファイルを削除することと同じです。</span><span class="sxs-lookup"><span data-stu-id="acd8b-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="acd8b-163">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="acd8b-164">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="acd8b-165">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="acd8b-166">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="acd8b-167">このオプションは、.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="acd8b-168">プロジェクト間参照を無視し、ルート プロジェクトのみを復元します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="acd8b-169">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="acd8b-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="acd8b-170">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="acd8b-171">指定しないと、既定で、フレームワークに依存する展開の場合は *./bin/[configuration]/[framework]/publish/* に、自己完結型の展開の場合は *./bin/[configuration]/[framework]/[runtime]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="acd8b-172">パスが相対的である場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="acd8b-173">アプリケーションと一緒に .NET Core ランタイムを発行します。これにより、ランタイムをターゲット コンピューターにインストールする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="acd8b-174">ランタイム識別子を指定した場合、その既定値は `true` となります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="acd8b-175">さまざまな展開方法の詳細については、「[.NET Core アプリケーションの展開](../deploying/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd8b-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="acd8b-176">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="acd8b-177">これは、[自己完結型の展開 (SCD)](../deploying/index.md#publish-self-contained) を作成するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="acd8b-178">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acd8b-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="acd8b-179">既定では、[フレームワークに依存する展開 (FDD)](../deploying/index.md#publish-runtime-dependent) が発行されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="acd8b-180">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="acd8b-181">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="acd8b-182">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="acd8b-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="acd8b-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="acd8b-184">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-184">Defines the build configuration.</span></span> <span data-ttu-id="acd8b-185">既定値は `Debug` です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="acd8b-186">指定した[ターゲット フレームワーク](../../standard/frameworks.md)のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="acd8b-187">ターゲット フレームワークはプロジェクト ファイルで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="acd8b-188">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="acd8b-189">アプリによって公開された一連のパッケージをトリミングするために使用する[ターゲット マニフェスト](../deploying/runtime-store.md)を 1 つまたは複数指定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="acd8b-190">マニフェスト ファイルは、[`dotnet store` コマンド](dotnet-store.md)の出力の一部です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="acd8b-191">複数のマニフェストを指定するには、マニフェストごとに `--manifest` を追加します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="acd8b-192">このオプションは、.NET Core 2.0 SDK 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="acd8b-193">出力ディレクトリのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="acd8b-194">指定しないと、既定で、フレームワークに依存する展開の場合は *./bin/[configuration]/[framework]/publish/* に、自己完結型の展開の場合は *./bin/[configuration]/[framework]/[runtime]/publish/* に設定されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="acd8b-195">パスが相対的である場合、生成された出力ディレクトリは、現在の作業ディレクトリではなく、プロジェクト ファイルの場所に相対的なパスとなります。</span><span class="sxs-lookup"><span data-stu-id="acd8b-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="acd8b-196">指定されたランタイムのアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="acd8b-197">これは、[自己完結型の展開 (SCD)](../deploying/index.md#publish-self-contained) を作成するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="acd8b-198">ランタイム ID (RID) の一覧については、[RID カタログ](../rid-catalog.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="acd8b-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="acd8b-199">既定では、[フレームワークに依存する展開 (FDD)](../deploying/index.md#publish-runtime-dependent) が発行されます。</span><span class="sxs-lookup"><span data-stu-id="acd8b-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="acd8b-200">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="acd8b-201">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="acd8b-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="acd8b-202">プロジェクト ファイルのバージョン フィールドでアスタリスク (`*`) を置き換えるバージョン サフィックスを定義します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="acd8b-203">使用例</span><span class="sxs-lookup"><span data-stu-id="acd8b-203">Examples</span></span>

<span data-ttu-id="acd8b-204">現在のディレクトリのプロジェクトを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="acd8b-205">指定されたプロジェクト ファイルを使用して、アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="acd8b-206">`netcoreapp1.1` フレームワークを使って現在のディレクトリ内のプロジェクトを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="acd8b-207">`netcoreapp1.1` フレームワークと `OS X 10.10` のランタイム (この RID はプロジェクト ファイルに列挙しておく必要があります) を使って、現在のアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="acd8b-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="acd8b-208">現在のアプリケーションを発行します。ただし、復元操作中はルート プロジェクトのみを復元し、プロジェクト間 (P2P) 参照は復元しないでください (.NET Core SDK 2.0 以降のバージョン)。</span><span class="sxs-lookup"><span data-stu-id="acd8b-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="acd8b-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="acd8b-209">See also</span></span>

- [<span data-ttu-id="acd8b-210">ターゲット フレームワーク</span><span class="sxs-lookup"><span data-stu-id="acd8b-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="acd8b-211">ランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="acd8b-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
