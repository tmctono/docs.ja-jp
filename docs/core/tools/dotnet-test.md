---
title: dotnet test コマンド
description: dotnet test コマンドは、指定されたプロジェクトで単体テストを実行する場合に使用されます。
ms.date: 02/27/2020
ms.openlocfilehash: 6e906ab396a788905c99f50e73390b765b240efc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157012"
---
# <a name="dotnet-test"></a><span data-ttu-id="39275-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="39275-103">dotnet test</span></span>

<span data-ttu-id="39275-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="39275-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="39275-105">名前</span><span class="sxs-lookup"><span data-stu-id="39275-105">Name</span></span>

<span data-ttu-id="39275-106">`dotnet test` - 単体テストを実行するために使用される .NET テスト ドライバー。</span><span class="sxs-lookup"><span data-stu-id="39275-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="39275-107">構文</span><span class="sxs-lookup"><span data-stu-id="39275-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame]
    [-c|--configuration] [--collect] [-d|--diag] [-f|--framework]
    [--filter] [-l|--logger] [--no-build] [--no-restore]
    [-o|--output] [-r|--results-directory] [-s|--settings]
    [-t|--list-tests] [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="39275-108">説明</span><span class="sxs-lookup"><span data-stu-id="39275-108">Description</span></span>

<span data-ttu-id="39275-109">`dotnet test` コマンドは、指定されたプロジェクトで単体テストを実行する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="39275-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="39275-110">`dotnet test` コマンドは、プロジェクト用に指定されたテスト ランナーのコンソール アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="39275-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="39275-111">テスト ランナーでは、単体テスト フレームワーク (MSTest、NUnit、xUnit など) 用に定義されたテストを実行し、各テストの成功または失敗をレポートします。</span><span class="sxs-lookup"><span data-stu-id="39275-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="39275-112">すべてのテストが成功した場合、テスト ランナーは 0 の終了コードを返します。それ以外の、いずれかのテストに失敗した場合は、1 を返します。</span><span class="sxs-lookup"><span data-stu-id="39275-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="39275-113">テスト ランナーと単体テスト ライブラリは、NuGet パッケージとしてパッケージ化され、プロジェクトの通常の依存関係として復元されます。</span><span class="sxs-lookup"><span data-stu-id="39275-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="39275-114">テスト プロジェクトでは、通常の `<PackageReference>` 要素を使用してテスト ランナーを指定します。次のサンプル プロジェクト ファイルのようになります。</span><span class="sxs-lookup"><span data-stu-id="39275-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="39275-115">引数</span><span class="sxs-lookup"><span data-stu-id="39275-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="39275-116">テスト プロジェクトへのパス。</span><span class="sxs-lookup"><span data-stu-id="39275-116">Path to the test project.</span></span> <span data-ttu-id="39275-117">指定しない場合は、既定で現在のディレクトリに設定されます。</span><span class="sxs-lookup"><span data-stu-id="39275-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="39275-118">オプション</span><span class="sxs-lookup"><span data-stu-id="39275-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="39275-119">テスト実行で指定されたパスからカスタムのテスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="39275-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`-blame`**

  <span data-ttu-id="39275-120">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="39275-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="39275-121">このオプションは、テスト ホストがクラッシュする原因となる問題のあるテストを分離するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39275-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="39275-122">これは、現在のディレクトリ内に出力ファイルを *Sequence.xml* として作成します。このファイルは、クラッシュ前にテストの実行順序をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="39275-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration {Debug|Release}`**

  <span data-ttu-id="39275-123">ビルド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="39275-123">Defines the build configuration.</span></span> <span data-ttu-id="39275-124">既定値は `Debug` ですが、プロジェクトの構成がこの既定の SDK 設定をオーバーライドする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39275-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="39275-125">テストの実行のためのデータ コレクターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="39275-125">Enables data collector for the test run.</span></span> <span data-ttu-id="39275-126">詳細については、[「Monitor and analyze test run」](https://aka.ms/vstest-collect) (テストの実行のモニターと分析) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39275-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="39275-127">テスト プラットフォームの診断モードを有効にし、指定したファイルに診断メッセージを出力します。</span><span class="sxs-lookup"><span data-stu-id="39275-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="39275-128">特定の[フレームワーク](../../standard/frameworks.md)のテスト バイナリを検索します。</span><span class="sxs-lookup"><span data-stu-id="39275-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="39275-129">指定された式を使用して、現在のプロジェクト内のテストを除外します。</span><span class="sxs-lookup"><span data-stu-id="39275-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="39275-130">詳細については、「[フィルター オプションの詳細](#filter-option-details)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39275-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="39275-131">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39275-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="39275-132">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="39275-132">Prints out a short help for the command.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="39275-133">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="39275-133">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="39275-134">実行前にテスト プロジェクトをビルドしません。</span><span class="sxs-lookup"><span data-stu-id="39275-134">Doesn't build the test project before running it.</span></span> <span data-ttu-id="39275-135">また、- `--no-restore` フラグが暗黙的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="39275-135">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--no-restore`**

  <span data-ttu-id="39275-136">コマンドを実行するときに、暗黙的な復元を実行しません。</span><span class="sxs-lookup"><span data-stu-id="39275-136">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="39275-137">実行するバイナリを検索するディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="39275-137">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="39275-138">テスト結果が配置されるディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="39275-138">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="39275-139">指定されたディレクトリが存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="39275-139">If the specified directory doesn't exist, it's created.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="39275-140">テストの実行に使用する `.runsettings` ファイルです。</span><span class="sxs-lookup"><span data-stu-id="39275-140">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="39275-141">`.runsettings` ファイルを使用して単体テストを構成します。</span><span class="sxs-lookup"><span data-stu-id="39275-141">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="39275-142">現在のプロジェクトで検出されたすべてのテストを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="39275-142">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="39275-143">コマンドの詳細レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="39275-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="39275-144">指定できる値は、`q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]`、および `diag[nostic]` です。</span><span class="sxs-lookup"><span data-stu-id="39275-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="39275-145">`RunSettings` 引数</span><span class="sxs-lookup"><span data-stu-id="39275-145">`RunSettings` arguments</span></span>

  <span data-ttu-id="39275-146">引数は、テストの `RunSettings` 構成として渡されます。</span><span class="sxs-lookup"><span data-stu-id="39275-146">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="39275-147">引数は、"-- " に続く `[name]=[value]` のペアとして指定されます (-- の後ろのスペースに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="39275-147">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="39275-148">複数の `[name]=[value]` のペアを区切るにはスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="39275-148">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="39275-149">例 : `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="39275-149">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="39275-150">詳細については、[vstest.console.exe の RunSettings 引数渡し](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39275-150">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="39275-151">使用例</span><span class="sxs-lookup"><span data-stu-id="39275-151">Examples</span></span>

- <span data-ttu-id="39275-152">現在のディレクトリのプロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="39275-152">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="39275-153">`test1` プロジェクトでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="39275-153">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="39275-154">現在のディレクトリでプロジェクトのテストを実行し、trx 形式でテスト結果ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="39275-154">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="39275-155">フィルター オプションの詳細</span><span class="sxs-lookup"><span data-stu-id="39275-155">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="39275-156">`<Expression>` の形式は `<property><operator><value>[|&<Expression>]` です。</span><span class="sxs-lookup"><span data-stu-id="39275-156">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="39275-157">`<property>` は `Test Case` の属性です。</span><span class="sxs-lookup"><span data-stu-id="39275-157">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="39275-158">よく利用される単体テスト フレームワークでサポートされるプロパティは以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="39275-158">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="39275-159">テスト フレームワーク</span><span class="sxs-lookup"><span data-stu-id="39275-159">Test Framework</span></span> | <span data-ttu-id="39275-160">サポートされるプロパティ</span><span class="sxs-lookup"><span data-stu-id="39275-160">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="39275-161">MSTest</span><span class="sxs-lookup"><span data-stu-id="39275-161">MSTest</span></span>         | <ul><li><span data-ttu-id="39275-162">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="39275-162">FullyQualifiedName</span></span></li><li><span data-ttu-id="39275-163">名前</span><span class="sxs-lookup"><span data-stu-id="39275-163">Name</span></span></li><li><span data-ttu-id="39275-164">ClassName</span><span class="sxs-lookup"><span data-stu-id="39275-164">ClassName</span></span></li><li><span data-ttu-id="39275-165">優先度</span><span class="sxs-lookup"><span data-stu-id="39275-165">Priority</span></span></li><li><span data-ttu-id="39275-166">TestCategory</span><span class="sxs-lookup"><span data-stu-id="39275-166">TestCategory</span></span></li></ul> |
| <span data-ttu-id="39275-167">xUnit</span><span class="sxs-lookup"><span data-stu-id="39275-167">xUnit</span></span>          | <ul><li><span data-ttu-id="39275-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="39275-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="39275-169">DisplayName</span><span class="sxs-lookup"><span data-stu-id="39275-169">DisplayName</span></span></li><li><span data-ttu-id="39275-170">Traits</span><span class="sxs-lookup"><span data-stu-id="39275-170">Traits</span></span></li></ul>                                   |

<span data-ttu-id="39275-171">`<operator>` は、プロパティと値の関係を示します。</span><span class="sxs-lookup"><span data-stu-id="39275-171">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="39275-172">演算子</span><span class="sxs-lookup"><span data-stu-id="39275-172">Operator</span></span> | <span data-ttu-id="39275-173">関数</span><span class="sxs-lookup"><span data-stu-id="39275-173">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="39275-174">完全一致</span><span class="sxs-lookup"><span data-stu-id="39275-174">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="39275-175">完全一致ではない</span><span class="sxs-lookup"><span data-stu-id="39275-175">Not exact match</span></span> |
| `~`      | <span data-ttu-id="39275-176">内容</span><span class="sxs-lookup"><span data-stu-id="39275-176">Contains</span></span>        |
| `!~`     | <span data-ttu-id="39275-177">含まない</span><span class="sxs-lookup"><span data-stu-id="39275-177">Not contains</span></span>    |

<span data-ttu-id="39275-178">`<value>` は文字列です。</span><span class="sxs-lookup"><span data-stu-id="39275-178">`<value>` is a string.</span></span> <span data-ttu-id="39275-179">すべての参照で大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="39275-179">All the lookups are case insensitive.</span></span>

<span data-ttu-id="39275-180">`<operator>` を含まない式は、自動的に `FullyQualifiedName` プロパティの `contains` とみなされます (たとえば、`dotnet test --filter xyz` は `dotnet test --filter FullyQualifiedName~xyz` と同じです)。</span><span class="sxs-lookup"><span data-stu-id="39275-180">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="39275-181">式は条件演算子を使用して結合できます。</span><span class="sxs-lookup"><span data-stu-id="39275-181">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="39275-182">演算子</span><span class="sxs-lookup"><span data-stu-id="39275-182">Operator</span></span>            | <span data-ttu-id="39275-183">関数</span><span class="sxs-lookup"><span data-stu-id="39275-183">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="39275-184">OR</span><span class="sxs-lookup"><span data-stu-id="39275-184">OR</span></span>       |
| `&`                 | <span data-ttu-id="39275-185">AND</span><span class="sxs-lookup"><span data-stu-id="39275-185">AND</span></span>      |

<span data-ttu-id="39275-186">条件演算子を使用する場合は、式をかっこで囲みます (例: `(Name~TestMethod1) | (Name~TestMethod2)`)。</span><span class="sxs-lookup"><span data-stu-id="39275-186">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="39275-187">選択的単体テストのフィルター処理の使用方法に関する詳細と例については、「[選択的単体テストの実行](../testing/selective-unit-tests.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39275-187">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39275-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="39275-188">See also</span></span>

- [<span data-ttu-id="39275-189">フレームワークとターゲット</span><span class="sxs-lookup"><span data-stu-id="39275-189">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="39275-190">.NET Core のランタイム識別子 (RID) のカタログ</span><span class="sxs-lookup"><span data-stu-id="39275-190">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
