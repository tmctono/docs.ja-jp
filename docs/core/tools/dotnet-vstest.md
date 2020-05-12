---
title: dotnet vstest コマンド
description: dotnet vstest コマンドは、プロジェクトとそのすべての依存関係をビルドします。
ms.date: 02/27/2020
ms.openlocfilehash: f7db58f4aab59354b8c69ce0371324c23482dafe
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975395"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="68655-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="68655-103">dotnet vstest</span></span>

<span data-ttu-id="68655-104">**この記事の対象:** ✔️ .NET Core 2.1 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="68655-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68655-105">`dotnet vstest` コマンドに取って代わりのが `dotnet test` であり、これでアセンブリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="68655-105">The `dotnet vstest` command is superseded by `dotnet test`, which can now be used to run assemblies.</span></span> <span data-ttu-id="68655-106">[`dotnet test`](dotnet-test.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="68655-106">See [`dotnet test`](dotnet-test.md).</span></span>

## <a name="name"></a><span data-ttu-id="68655-107">名前</span><span class="sxs-lookup"><span data-stu-id="68655-107">Name</span></span>

<span data-ttu-id="68655-108">`dotnet-vstest` - 指定されたアセンブリからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-108">`dotnet-vstest` - Runs tests from the specified assemblies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="68655-109">構文</span><span class="sxs-lookup"><span data-stu-id="68655-109">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="68655-110">説明</span><span class="sxs-lookup"><span data-stu-id="68655-110">Description</span></span>

<span data-ttu-id="68655-111">`dotnet-vstest` コマンドでは、`VSTest.Console` コマンド ライン アプリケーションが実行されて、自動単体テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="68655-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="68655-112">引数</span><span class="sxs-lookup"><span data-stu-id="68655-112">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="68655-113">指定されたアセンブリからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="68655-114">複数のテスト アセンブリ名を指定するときは、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="68655-114">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="68655-115">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="68655-115">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="68655-116">オプション</span><span class="sxs-lookup"><span data-stu-id="68655-116">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="68655-117">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-117">Runs the tests in blame mode.</span></span> <span data-ttu-id="68655-118">このオプションは、テスト ホストのクラッシュを引き起こす問題のあるテストを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="68655-118">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="68655-119">これは、現在のディレクトリ内に出力ファイルを *Sequence.xml* として作成します。このファイルは、クラッシュ前にテストの実行順序をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="68655-119">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="68655-120">テスト プラットフォームの詳細ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="68655-120">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="68655-121">指定されたファイルにログが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="68655-121">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="68655-122">テストの実行に使用する対象の .NET Framework バージョンです。</span><span class="sxs-lookup"><span data-stu-id="68655-122">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="68655-123">有効な値の例としては、`.NETFramework,Version=v4.6` や `.NETCoreApp,Version=v1.0` などがあります。</span><span class="sxs-lookup"><span data-stu-id="68655-123">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="68655-124">サポートされるその他の値は、`Framework40`、`Framework45`、`FrameworkCore10`、および `FrameworkUap10` です。</span><span class="sxs-lookup"><span data-stu-id="68655-124">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="68655-125">分離プロセスでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-125">Runs the tests in an isolated process.</span></span> <span data-ttu-id="68655-126">これにより、テストでエラーが発生しても *vstest.console.exe* プロセスが停止することは少なくなりますが、テストの実行速度は低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68655-126">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="68655-127">指定されたテスト コンテナーから探索されたテストをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="68655-127">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="68655-128">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="68655-128">Specify a logger for test results.</span></span>

  - <span data-ttu-id="68655-129">Team Foundation Server にテスト結果を発行するには、次のように `TfsPublisher` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="68655-129">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="68655-130">Visual Studio テスト結果ファイル (TRX) に結果のログを書き込むには、`trx` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="68655-130">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="68655-131">このように切り替えることで、テスト結果ディレクトリに指定のログ ファイル名でファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="68655-131">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="68655-132">`LogFileName` が指定されていない場合は、テスト結果を保持するために一意のファイル名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="68655-132">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="68655-133">テストを並列で実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-133">Run tests in parallel.</span></span> <span data-ttu-id="68655-134">既定では、コンピューター上のすべての使用可能なコアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="68655-134">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="68655-135">*runsettings* ファイルの `RunConfiguration` ノードの下に `MaxCpuCount` プロパティを設定して、明示的なコア数を指定します。</span><span class="sxs-lookup"><span data-stu-id="68655-135">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="68655-136">現在のプロセスを起動する親プロセスのプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="68655-136">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="68655-137">テストの実行に使用する対象のプラットフォーム アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="68655-137">Target platform architecture used for test execution.</span></span> <span data-ttu-id="68655-138">有効な値は `x86`、`x64`、`ARM` です。</span><span class="sxs-lookup"><span data-stu-id="68655-138">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="68655-139">ソケット接続およびイベント メッセージの受信用のポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="68655-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="68655-140">テスト結果ディレクトリが存在しない場合、指定されたパスに作成されます。</span><span class="sxs-lookup"><span data-stu-id="68655-140">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="68655-141">テストの実行時に使用される設定です。</span><span class="sxs-lookup"><span data-stu-id="68655-141">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="68655-142">テストの実行では、指定されたパス (存在する場合) からカスタム テスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="68655-142">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="68655-143">指定した式に一致するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-143">Run tests that match the given expression.</span></span> <span data-ttu-id="68655-144">`<EXPRESSION>` の形式は `<property>Operator<value>[|&<EXPRESSION>]` です。この場合の演算子は `=`、`!=`、または `~` のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="68655-144">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="68655-145">演算子 `~` は 'contains' セマンティクスを持ち、`DisplayName` などの文字列プロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="68655-145">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="68655-146">サブ式のグループ化には、かっこ `()` を使用します。</span><span class="sxs-lookup"><span data-stu-id="68655-146">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="68655-147">詳細については、[TestCase フィルター](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68655-147">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="68655-148">指定した値に一致する名前のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-148">Run tests with names that match the provided values.</span></span> <span data-ttu-id="68655-149">複数の値を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="68655-149">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="68655-150">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="68655-150">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="68655-151">応答ファイルを読み込んで、オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="68655-151">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="68655-152">アダプターに渡す追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="68655-152">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="68655-153">引数は `<n>=<v>` 形式の名前と値のペアとして指定されます。この場合の `<n>` は引数名、`<v>` は引数値です。</span><span class="sxs-lookup"><span data-stu-id="68655-153">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="68655-154">複数の引数を指定する場合は、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="68655-154">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="68655-155">使用例</span><span class="sxs-lookup"><span data-stu-id="68655-155">Examples</span></span>

<span data-ttu-id="68655-156">*mytestproject.dll* でテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-156">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="68655-157">*mytestproject.dll* でテストを実行し、カスタム名を指定してカスタム フォルダーにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="68655-157">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="68655-158">*mytestproject.dll* と *myothertestproject.exe* でテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="68655-158">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="68655-159">`TestMethod1` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="68655-159">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="68655-160">`TestMethod1` および `TestMethod2` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="68655-160">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="68655-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="68655-161">See also</span></span>

- [<span data-ttu-id="68655-162">VSTest.Console.exe のコマンド ライン オプション</span><span class="sxs-lookup"><span data-stu-id="68655-162">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
