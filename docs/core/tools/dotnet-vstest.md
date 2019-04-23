---
title: dotnet vstest コマンド
description: dotnet vstest コマンドは、プロジェクトとそのすべての依存関係をビルドします。
author: guardrex
ms.date: 05/30/2018
ms.openlocfilehash: 25d1b2d65b3e91bce894c59959a58537fa8ca113
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204017"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="b94e2-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="b94e2-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b94e2-104">name</span><span class="sxs-lookup"><span data-stu-id="b94e2-104">Name</span></span>

`dotnet-vstest` <span data-ttu-id="b94e2-105">- 指定されたファイルからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-105">- Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b94e2-106">構文</span><span class="sxs-lookup"><span data-stu-id="b94e2-106">Synopsis</span></span>

# [<a name="net-core-21"></a><span data-ttu-id="b94e2-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b94e2-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```
# [<a name="net-core-20"></a><span data-ttu-id="b94e2-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b94e2-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```
# [<a name="net-core-1x"></a><span data-ttu-id="b94e2-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b94e2-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```
---

## <a name="description"></a><span data-ttu-id="b94e2-110">説明</span><span class="sxs-lookup"><span data-stu-id="b94e2-110">Description</span></span>

<span data-ttu-id="b94e2-111">`dotnet-vstest` コマンドでは、`VSTest.Console` コマンド ライン アプリケーションが実行されて、自動単体テストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="b94e2-112">引数</span><span class="sxs-lookup"><span data-stu-id="b94e2-112">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="b94e2-113">指定されたアセンブリからテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="b94e2-114">複数のテスト アセンブリ名を指定するときは、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-114">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="b94e2-115">オプション</span><span class="sxs-lookup"><span data-stu-id="b94e2-115">Options</span></span>

# [<a name="net-core-21"></a><span data-ttu-id="b94e2-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b94e2-116">.NET Core 2.1</span></span>](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="b94e2-117">テストの実行時に使用される設定です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-117">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="b94e2-118">指定した値に一致する名前のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-118">Run tests with names that match the provided values.</span></span> <span data-ttu-id="b94e2-119">複数の値を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-119">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="b94e2-120">テストの実行では、指定されたパス (存在する場合) からカスタム テスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-120">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="b94e2-121">テストの実行に使用する対象のプラットフォーム アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="b94e2-121">Target platform architecture used for test execution.</span></span> <span data-ttu-id="b94e2-122">有効な値は `x86`、`x64`、`ARM` です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-122">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="b94e2-123">テストの実行に使用する対象の .NET Framework バージョンです。</span><span class="sxs-lookup"><span data-stu-id="b94e2-123">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="b94e2-124">有効な値の例としては、`.NETFramework,Version=v4.6` や `.NETCoreApp,Version=v1.0` などがあります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-124">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="b94e2-125">サポートされるその他の値は、`Framework40`、`Framework45`、`FrameworkCore10`、および `FrameworkUap10` です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-125">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="b94e2-126">テストを並列で実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-126">Execute tests in parallel.</span></span> <span data-ttu-id="b94e2-127">既定では、コンピューター上のすべての使用可能なコアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-127">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="b94e2-128">runsettings ファイルの RunConfiguration ノードで MaxCpuCount プロパティを設定することにより、コア数を明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-128">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="b94e2-129">指定した式に一致するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-129">Run tests that match the given expression.</span></span> `<Expression>` <span data-ttu-id="b94e2-130">の形式は `<property>Operator<value>[|&<Expression>]` です。この場合の演算子は `=`、`!=`、`~` のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-130">is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="b94e2-131">演算子 `~` は 'contains' セマンティクスを持ち、`DisplayName` などの文字列プロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-131">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="b94e2-132">かっこ `()` はサブ式をグループ化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-132">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="b94e2-133">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-133">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="b94e2-134">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-134">Specify a logger for test results.</span></span>

* <span data-ttu-id="b94e2-135">Team Foundation Server にテスト結果を発行するには、次のように `TfsPublisher` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-135">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="b94e2-136">Visual Studio テスト結果ファイル (TRX) に結果のログを書き込むには、`trx` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-136">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="b94e2-137">このように切り替えることで、テスト結果ディレクトリに指定のログ ファイル名でファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-137">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="b94e2-138">`LogFileName` が指定されていない場合は、テスト結果を保持するために一意のファイル名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-138">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="b94e2-139">指定されたテスト コンテナーから探索されたテストをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-139">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="b94e2-140">現在のプロセスを起動する親プロセスのプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-140">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="b94e2-141">ソケット接続およびイベント メッセージの受信用のポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-141">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="b94e2-142">テスト プラットフォームの詳細ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b94e2-142">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="b94e2-143">指定されたファイルにログが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-143">Logs are written to the provided file.</span></span>

`--Blame|/Blame`

<span data-ttu-id="b94e2-144">変更履歴モードでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-144">Runs the tests in blame mode.</span></span> <span data-ttu-id="b94e2-145">このオプションは、テスト ホストのクラッシュを引き起こす問題のあるテストを分離するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-145">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="b94e2-146">これは、現在のディレクトリ内に出力ファイルを *Sequence.xml* として作成します。このファイルは、クラッシュ前にテストの実行順序をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="b94e2-146">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`--InIsolation|/InIsolation`

<span data-ttu-id="b94e2-147">分離プロセスでテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-147">Runs the tests in an isolated process.</span></span> <span data-ttu-id="b94e2-148">これにより、テストでエラーが発生しても *vstest.console.exe* プロセスが停止することは少なくなりますが、テストの実行速度は低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-148">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

`@<file>`

<span data-ttu-id="b94e2-149">応答ファイルを読み込んで、オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-149">Reads response file for more options.</span></span>

`args`

<span data-ttu-id="b94e2-150">アダプターに渡す追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="b94e2-151">引数は `<n>=<v>` 形式の名前と値のペアとして指定されます。この場合の `<n>` は引数名、`<v>` は引数値です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="b94e2-152">複数の引数を指定する場合は、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-152">Use a space to separate multiple arguments.</span></span>

# [<a name="net-core-20"></a><span data-ttu-id="b94e2-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b94e2-153">.NET Core 2.0</span></span>](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="b94e2-154">テストの実行時に使用される設定です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-154">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="b94e2-155">指定した値に一致する名前のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-155">Run tests with names that match the provided values.</span></span> <span data-ttu-id="b94e2-156">複数の値を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-156">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="b94e2-157">テストの実行では、指定されたパス (存在する場合) からカスタム テスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-157">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="b94e2-158">テストの実行に使用する対象のプラットフォーム アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="b94e2-158">Target platform architecture used for test execution.</span></span> <span data-ttu-id="b94e2-159">有効な値は `x86`、`x64`、`ARM` です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-159">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="b94e2-160">テストの実行に使用する対象の .NET Framework バージョンです。</span><span class="sxs-lookup"><span data-stu-id="b94e2-160">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="b94e2-161">有効な値の例としては、`.NETFramework,Version=v4.6` や `.NETCoreApp,Version=v1.0` などがあります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-161">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="b94e2-162">サポートされる値としては、他に `Framework40`、`Framework45`、`FrameworkCore10` があります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-162">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="b94e2-163">テストを並列で実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-163">Execute tests in parallel.</span></span> <span data-ttu-id="b94e2-164">既定では、コンピューター上のすべての使用可能なコアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-164">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="b94e2-165">runsettings ファイルの RunConfiguration ノードで MaxCpuCount プロパティを設定することにより、コア数を明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-165">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="b94e2-166">指定した式に一致するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-166">Run tests that match the given expression.</span></span> `<Expression>` <span data-ttu-id="b94e2-167">の形式は `<property>Operator<value>[|&<Expression>]` です。この場合の演算子は `=`、`!=`、`~` のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-167">is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="b94e2-168">演算子 `~` は 'contains' セマンティクスを持ち、`DisplayName` などの文字列プロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-168">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="b94e2-169">かっこ `()` はサブ式をグループ化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-169">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="b94e2-170">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-170">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="b94e2-171">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-171">Specify a logger for test results.</span></span>

* <span data-ttu-id="b94e2-172">Team Foundation Server にテスト結果を発行するには、次のように `TfsPublisher` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-172">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="b94e2-173">Visual Studio テスト結果ファイル (TRX) に結果のログを書き込むには、`trx` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-173">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="b94e2-174">このように切り替えることで、テスト結果ディレクトリに指定のログ ファイル名でファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-174">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="b94e2-175">`LogFileName` が指定されていない場合は、テスト結果を保持するために一意のファイル名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-175">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="b94e2-176">指定されたテスト コンテナーから探索されたテストをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-176">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="b94e2-177">現在のプロセスを起動する親プロセスのプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-177">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="b94e2-178">ソケット接続およびイベント メッセージの受信用のポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-178">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="b94e2-179">テスト プラットフォームの詳細ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b94e2-179">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="b94e2-180">指定されたファイルにログが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-180">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="b94e2-181">アダプターに渡す追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-181">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="b94e2-182">引数は `<n>=<v>` 形式の名前と値のペアとして指定されます。この場合の `<n>` は引数名、`<v>` は引数値です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-182">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="b94e2-183">複数の引数を指定する場合は、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-183">Use a space to separate multiple arguments.</span></span>

# [<a name="net-core-1x"></a><span data-ttu-id="b94e2-184">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b94e2-184">.NET Core 1.x</span></span>](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="b94e2-185">テストの実行時に使用される設定です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-185">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="b94e2-186">指定した値に一致する名前のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-186">Run tests with names that match the provided values.</span></span> <span data-ttu-id="b94e2-187">複数の値を指定するときは、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-187">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="b94e2-188">テストの実行では、指定されたパス (存在する場合) からカスタム テスト アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-188">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="b94e2-189">テストの実行に使用する対象のプラットフォーム アーキテクチャです。</span><span class="sxs-lookup"><span data-stu-id="b94e2-189">Target platform architecture used for test execution.</span></span> <span data-ttu-id="b94e2-190">有効な値は `x86`、`x64`、`ARM` です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-190">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="b94e2-191">テストの実行に使用する対象の .NET Framework バージョンです。</span><span class="sxs-lookup"><span data-stu-id="b94e2-191">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="b94e2-192">有効な値の例としては、`.NETFramework,Version=v4.6` や `.NETCoreApp,Version=v1.0` などがあります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-192">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="b94e2-193">サポートされる値としては、他に `Framework40`、`Framework45`、`FrameworkCore10` があります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-193">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="b94e2-194">テストを並列で実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-194">Execute tests in parallel.</span></span> <span data-ttu-id="b94e2-195">既定では、コンピューター上のすべての使用可能なコアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-195">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="b94e2-196">runsettings ファイルの RunConfiguration ノードで MaxCpuCount プロパティを設定することにより、コア数を明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-196">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="b94e2-197">指定した式に一致するテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-197">Run tests that match the given expression.</span></span> `<Expression>` <span data-ttu-id="b94e2-198">の形式は `<property>Operator<value>[|&<Expression>]` です。この場合の演算子は `=`、`!=`、`~` のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-198">is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="b94e2-199">演算子 `~` は 'contains' セマンティクスを持ち、`DisplayName` などの文字列プロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-199">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="b94e2-200">かっこ `()` はサブ式をグループ化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-200">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="b94e2-201">コマンドの短いヘルプを印刷します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-201">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="b94e2-202">テスト結果のロガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-202">Specify a logger for test results.</span></span>

* <span data-ttu-id="b94e2-203">Team Foundation Server にテスト結果を発行するには、次のように `TfsPublisher` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-203">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="b94e2-204">Visual Studio テスト結果ファイル (TRX) に結果のログを書き込むには、`trx` ロガー プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-204">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="b94e2-205">このように切り替えることで、テスト結果ディレクトリに指定のログ ファイル名でファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-205">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="b94e2-206">`LogFileName` が指定されていない場合は、テスト結果を保持するために一意のファイル名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-206">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="b94e2-207">指定されたテスト コンテナーから探索されたテストをすべて一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-207">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="b94e2-208">現在のプロセスを起動する親プロセスのプロセス ID です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-208">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="b94e2-209">ソケット接続およびイベント メッセージの受信用のポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-209">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="b94e2-210">テスト プラットフォームの詳細ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b94e2-210">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="b94e2-211">指定されたファイルにログが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b94e2-211">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="b94e2-212">アダプターに渡す追加の引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b94e2-212">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="b94e2-213">引数は `<n>=<v>` 形式の名前と値のペアとして指定されます。この場合の `<n>` は引数名、`<v>` は引数値です。</span><span class="sxs-lookup"><span data-stu-id="b94e2-213">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="b94e2-214">複数の引数を指定する場合は、空白で区切ります。</span><span class="sxs-lookup"><span data-stu-id="b94e2-214">Use a space to separate multiple arguments.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b94e2-215">使用例</span><span class="sxs-lookup"><span data-stu-id="b94e2-215">Examples</span></span>

<span data-ttu-id="b94e2-216">`mytestproject.dll` でテストを実行する:</span><span class="sxs-lookup"><span data-stu-id="b94e2-216">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="b94e2-217">`mytestproject.dll` でテストを実行し、カスタム名を持つカスタム フォルダーにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="b94e2-217">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="b94e2-218">`mytestproject.dll` と `myothertestproject.exe` でテストを実行する:</span><span class="sxs-lookup"><span data-stu-id="b94e2-218">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="b94e2-219">`TestMethod1` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="b94e2-219">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="b94e2-220">`TestMethod1` および `TestMethod2` テストを実行する:</span><span class="sxs-lookup"><span data-stu-id="b94e2-220">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
