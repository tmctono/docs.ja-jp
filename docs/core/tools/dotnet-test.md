---
title: dotnet test コマンド
description: dotnet test コマンドは、指定されたプロジェクトで単体テストを実行する場合に使用されます。
ms.date: 05/29/2018
ms.openlocfilehash: 49926b35b418e93237a159758903c535ec6c4006
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988541"
---
# <a name="dotnet-test"></a><span data-ttu-id="18168-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="18168-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="18168-104">name</span><span class="sxs-lookup"><span data-stu-id="18168-104">Name</span></span>

<span data-ttu-id="18168-105">`dotnet test` - 単体テストを実行するために使用される .NET テスト ドライバー。</span><span class="sxs-lookup"><span data-stu-id="18168-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="18168-106">構文</span><span class="sxs-lookup"><span data-stu-id="18168-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18168-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18168-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18168-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18168-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18168-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18168-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="18168-110">説明</span><span class="sxs-lookup"><span data-stu-id="18168-110">Description</span></span>

<span data-ttu-id="18168-111">`dotnet test` コマンドは、指定されたプロジェクトで単体テストを実行する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="18168-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="18168-112">`dotnet test` コマンドは、プロジェクト用に指定されたテスト ランナーのコンソール アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="18168-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="18168-113">テスト ランナーでは、単体テスト フレームワーク (MSTest、NUnit、xUnit など) 用に定義されたテストを実行し、各テストの成功または失敗をレポートします。</span><span class="sxs-lookup"><span data-stu-id="18168-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="18168-114">すべてのテストが成功した場合、テスト ランナーは 0 の終了コードを返します。それ以外の、いずれかのテストに失敗した場合は、1 を返します。</span><span class="sxs-lookup"><span data-stu-id="18168-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="18168-115">テスト ランナーと単体テスト ライブラリは、NuGet パッケージとしてパッケージ化され、プロジェクトの通常の依存関係として復元されます。</span><span class="sxs-lookup"><span data-stu-id="18168-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="18168-116">テスト プロジェクトでは、通常の `<PackageReference>` 要素を使用してテスト ランナーを指定します。次のサンプル プロジェクト ファイルのようになります。</span><span class="sxs-lookup"><span data-stu-id="18168-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="18168-117">引数</span><span class="sxs-lookup"><span data-stu-id="18168-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="18168-118">テスト プロジェクトへのパス。</span><span class="sxs-lookup"><span data-stu-id="18168-118">Path to the test project.</span></span> <span data-ttu-id="18168-119">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="18168-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="18168-120">オプション</span><span class="sxs-lookup"><span data-stu-id="18168-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="18168-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="18168-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="18168-122">テスト実行で指定されたパスからカスタムのテスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="18168-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="18168-123">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="18168-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="18168-124">このオプションは、テスト ホストのクラッシュを引き起こす問題のあるテストを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="18168-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="18168-125">これは、現在のディレクトリ内に出力ファイルを *Sequence.xml* として作成します。このファイルは、クラッシュ前にテストの実行順序をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="18168-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="18168-126">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="18168-126">Defines the build configuration.</span></span> <span data-ttu-id="18168-127">既定値は `Debug` ですが、プロジェクトの構成がこの既定の SDK 設定をオーバーライドする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18168-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="18168-128">テストの実行のためのデータ コレクターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="18168-128">Enables data collector for the test run.</span></span> <span data-ttu-id="18168-129">詳細については、[「Monitor and analyze test run」](https://aka.ms/vstest-collect) (テストの実行のモニターと分析) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18168-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="18168-130">テスト プラットフォームの診断モードを有効にし、指定したファイルに診断メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="18168-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="18168-131">特定の[フレームワーク](../../standard/frameworks.md)のテスト バイナリを検索します。</span><span class="sxs-lookup"><span data-stu-id="18168-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="18168-132">指定された式を使用して、現在のプロジェクト内のテストを除外します。</span><span class="sxs-lookup"><span data-stu-id="18168-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="18168-133">詳細については、「[フィルター オプションの詳細](#filter-option-details)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="18168-134">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="18168-135">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="18168-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="18168-136">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="18168-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="18168-137">実行前にテスト プロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="18168-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="18168-138">また、`--no-restore` フラグを暗黙的に設定します。</span><span class="sxs-lookup"><span data-stu-id="18168-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="18168-139">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="18168-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="18168-140">実行するバイナリを検索するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="18168-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="18168-141">テスト結果が配置されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="18168-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="18168-142">指定されたディレクトリが存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="18168-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="18168-143">テストの実行に使用する `.runsettings` ファイルです。</span><span class="sxs-lookup"><span data-stu-id="18168-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="18168-144">`.runsettings` ファイルを使用して単体テストを構成します。</span><span class="sxs-lookup"><span data-stu-id="18168-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="18168-145">現在のプロジェクトで検出されたすべてのテストを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="18168-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18168-146">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="18168-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18168-147">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="18168-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="18168-148">テストの RunSettings 構成として渡される引数です。</span><span class="sxs-lookup"><span data-stu-id="18168-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="18168-149">引数は、"-- " に続く `[name]=[value]` のペアとして指定されます (-- の後ろのスペースに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="18168-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="18168-150">複数の `[name]=[value]` のペアを区切るにはスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="18168-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="18168-151">例 : `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="18168-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="18168-152">RunSettings について詳しくは、[vstest.console.exe:RunSettings 引数渡し](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="18168-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="18168-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="18168-154">テスト実行で指定されたパスからカスタムのテスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="18168-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="18168-155">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="18168-155">Defines the build configuration.</span></span> <span data-ttu-id="18168-156">既定値は `Debug` ですが、プロジェクトの構成がこの既定の SDK 設定をオーバーライドする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18168-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="18168-157">テストの実行のためのデータ コレクターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="18168-157">Enables data collector for the test run.</span></span> <span data-ttu-id="18168-158">詳細については、[「Monitor and analyze test run」](https://aka.ms/vstest-collect) (テストの実行のモニターと分析) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18168-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="18168-159">テスト プラットフォームの診断モードを有効にし、指定したファイルに診断メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="18168-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="18168-160">特定の[フレームワーク](../../standard/frameworks.md)のテスト バイナリを検索します。</span><span class="sxs-lookup"><span data-stu-id="18168-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="18168-161">指定された式を使用して、現在のプロジェクト内のテストを除外します。</span><span class="sxs-lookup"><span data-stu-id="18168-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="18168-162">詳細については、「[フィルター オプションの詳細](#filter-option-details)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="18168-163">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="18168-164">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="18168-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="18168-165">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="18168-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="18168-166">実行前にテスト プロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="18168-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="18168-167">また、`--no-restore` フラグを暗黙的に設定します。</span><span class="sxs-lookup"><span data-stu-id="18168-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="18168-168">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="18168-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="18168-169">実行するバイナリを検索するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="18168-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="18168-170">テスト結果が配置されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="18168-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="18168-171">指定されたディレクトリが存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="18168-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="18168-172">テストの実行に使用する `.runsettings` ファイルです。</span><span class="sxs-lookup"><span data-stu-id="18168-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="18168-173">`.runsettings` ファイルを使用して単体テストを構成します。</span><span class="sxs-lookup"><span data-stu-id="18168-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="18168-174">現在のプロジェクトで検出されたすべてのテストを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="18168-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18168-175">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="18168-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18168-176">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="18168-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="18168-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="18168-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="18168-178">テスト実行で指定されたパスからカスタムのテスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="18168-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="18168-179">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="18168-179">Defines the build configuration.</span></span> <span data-ttu-id="18168-180">既定値は `Debug` ですが、プロジェクトの構成がこの既定の SDK 設定をオーバーライドする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18168-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="18168-181">テスト プラットフォームの診断モードを有効にし、指定したファイルに診断メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="18168-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="18168-182">特定の[フレームワーク](../../standard/frameworks.md)のテスト バイナリを検索します。</span><span class="sxs-lookup"><span data-stu-id="18168-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="18168-183">指定された式を使用して、現在のプロジェクト内のテストを除外します。</span><span class="sxs-lookup"><span data-stu-id="18168-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="18168-184">詳細については、「[フィルター オプションの詳細](#filter-option-details)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="18168-185">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="18168-186">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="18168-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="18168-187">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="18168-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="18168-188">実行前にテスト プロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="18168-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="18168-189">実行するバイナリを検索するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="18168-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="18168-190">テストの実行に使用する `.runsettings` ファイルです。</span><span class="sxs-lookup"><span data-stu-id="18168-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="18168-191">`.runsettings` ファイルを使用して単体テストを構成します。</span><span class="sxs-lookup"><span data-stu-id="18168-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="18168-192">現在のプロジェクトで検出されたすべてのテストを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="18168-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="18168-193">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="18168-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="18168-194">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="18168-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="18168-195">使用例</span><span class="sxs-lookup"><span data-stu-id="18168-195">Examples</span></span>

<span data-ttu-id="18168-196">現在のディレクトリのプロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="18168-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="18168-197">`test1` プロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="18168-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="18168-198">現在のディレクトリでプロジェクトのテストを実行し、trx 形式でテスト結果ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="18168-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger trx`

## <a name="filter-option-details"></a><span data-ttu-id="18168-199">フィルター オプションの詳細</span><span class="sxs-lookup"><span data-stu-id="18168-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="18168-200">`<Expression>` の形式は `<property><operator><value>[|&<Expression>]` です。</span><span class="sxs-lookup"><span data-stu-id="18168-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="18168-201">`<property>` は `Test Case` の属性です。</span><span class="sxs-lookup"><span data-stu-id="18168-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="18168-202">よく利用される単体テスト フレームワークでサポートされるプロパティは以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="18168-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="18168-203">テスト フレームワーク</span><span class="sxs-lookup"><span data-stu-id="18168-203">Test Framework</span></span> | <span data-ttu-id="18168-204">サポートされるプロパティ</span><span class="sxs-lookup"><span data-stu-id="18168-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="18168-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="18168-205">MSTest</span></span>         | <ul><li><span data-ttu-id="18168-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="18168-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="18168-207">name</span><span class="sxs-lookup"><span data-stu-id="18168-207">Name</span></span></li><li><span data-ttu-id="18168-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="18168-208">ClassName</span></span></li><li><span data-ttu-id="18168-209">優先度</span><span class="sxs-lookup"><span data-stu-id="18168-209">Priority</span></span></li><li><span data-ttu-id="18168-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="18168-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="18168-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="18168-211">xUnit</span></span>          | <ul><li><span data-ttu-id="18168-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="18168-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="18168-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="18168-213">DisplayName</span></span></li><li><span data-ttu-id="18168-214">Traits</span><span class="sxs-lookup"><span data-stu-id="18168-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="18168-215">`<operator>` は、プロパティと値の関係を示します。</span><span class="sxs-lookup"><span data-stu-id="18168-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="18168-216">演算子</span><span class="sxs-lookup"><span data-stu-id="18168-216">Operator</span></span> | <span data-ttu-id="18168-217">関数</span><span class="sxs-lookup"><span data-stu-id="18168-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="18168-218">完全一致</span><span class="sxs-lookup"><span data-stu-id="18168-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="18168-219">完全一致ではない</span><span class="sxs-lookup"><span data-stu-id="18168-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="18168-220">内容</span><span class="sxs-lookup"><span data-stu-id="18168-220">Contains</span></span>        |

<span data-ttu-id="18168-221">`<value>` は文字列です。</span><span class="sxs-lookup"><span data-stu-id="18168-221">`<value>` is a string.</span></span> <span data-ttu-id="18168-222">すべての参照で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="18168-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="18168-223">`<operator>` を含まない式は、自動的に `FullyQualifiedName` プロパティの `contains` とみなされます (たとえば、`dotnet test --filter xyz` は `dotnet test --filter FullyQualifiedName~xyz` と同じです)。</span><span class="sxs-lookup"><span data-stu-id="18168-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="18168-224">式は条件演算子を使用して結合できます。</span><span class="sxs-lookup"><span data-stu-id="18168-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="18168-225">演算子</span><span class="sxs-lookup"><span data-stu-id="18168-225">Operator</span></span>            | <span data-ttu-id="18168-226">関数</span><span class="sxs-lookup"><span data-stu-id="18168-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="18168-227">OR</span><span class="sxs-lookup"><span data-stu-id="18168-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="18168-228">AND</span><span class="sxs-lookup"><span data-stu-id="18168-228">AND</span></span>      |

<span data-ttu-id="18168-229">条件演算子を使用する場合は、式をかっこで囲みます (例: `(Name~TestMethod1) | (Name~TestMethod2)`)。</span><span class="sxs-lookup"><span data-stu-id="18168-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="18168-230">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="18168-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="18168-231">関連項目</span><span class="sxs-lookup"><span data-stu-id="18168-231">See also</span></span>

- [<span data-ttu-id="18168-232">フレームワークとターゲット</span><span class="sxs-lookup"><span data-stu-id="18168-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="18168-233">.NET Core のランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="18168-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
