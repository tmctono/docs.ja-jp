---
title: .NET Core SDK 製品利用統計情報
description: 利用情報を収集して分析する .NET Core SDK の製品利用統計情報機能や収集されるデータ、およびこの機能を無効にする方法について説明します。
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: a79b791abc99331ff39f5e281ee0fdc62b258989
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507283"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="c02e6-103">.NET Core SDK 製品利用統計情報</span><span class="sxs-lookup"><span data-stu-id="c02e6-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="c02e6-104">[.NET Core SDK](index.md) には、.NET Core CLI がクラッシュしたとき、利用データと例外情報を収集する製品利用統計情報機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c02e6-104">The [.NET Core SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET Core CLI crashes.</span></span> <span data-ttu-id="c02e6-105">.NET Core CLI は .NET Core SDK を備える、.NET Core アプリのビルド、テスト、発行を可能にする動詞のセットです。</span><span class="sxs-lookup"><span data-stu-id="c02e6-105">The .NET Core CLI comes with the .NET Core SDK and is the set of verbs that enable you to build, test, and publish your .NET Core apps.</span></span> <span data-ttu-id="c02e6-106">.NET Team が、ツールの改善に向けて、その使用方法を把握することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c02e6-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="c02e6-107">エラーに関する情報は、チームが問題を解決し、バグを修正するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="c02e6-108">収集されたデータは匿名であり、[Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/) の下で全体が公開されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-108">The collected data is anonymous and published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="c02e6-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="c02e6-109">Scope</span></span>

<span data-ttu-id="c02e6-110">`dotnet` には、アプリを実行し、CLI コマンドを実行するための 2 つの関数があります。</span><span class="sxs-lookup"><span data-stu-id="c02e6-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="c02e6-111">`dotnet` を使用して次の形式でアプリケーションを起動するとき、製品利用統計情報は "*収集されません*"。</span><span class="sxs-lookup"><span data-stu-id="c02e6-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="c02e6-112">次のような [.NET Core CLI コマンド](index.md)を使用するとき、製品利用統計情報は "*収集されます*"。</span><span class="sxs-lookup"><span data-stu-id="c02e6-112">Telemetry *is collected* when using any of the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="c02e6-113">オプトアウトする方法</span><span class="sxs-lookup"><span data-stu-id="c02e6-113">How to opt out</span></span>

<span data-ttu-id="c02e6-114">.NET Core SDK の製品利用統計情報機能は既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c02e6-114">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="c02e6-115">製品利用統計情報機能をオプトアウトするには、`DOTNET_CLI_TELEMETRY_OPTOUT` 環境変数を `1` または `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c02e6-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="c02e6-116">正常にインストールされると、製品利用統計情報のエントリ 1 件も .NET Core SDK インストーラーによって送信されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-116">A single telemetry entry is also sent by the .NET Core SDK installer when a successful installation happens.</span></span> <span data-ttu-id="c02e6-117">オプトアウトするには、.NET Core SDK をインストールする前に `DOTNET_CLI_TELEMETRY_OPTOUT` 環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c02e6-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET Core SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="c02e6-118">開示</span><span class="sxs-lookup"><span data-stu-id="c02e6-118">Disclosure</span></span>

<span data-ttu-id="c02e6-119">いずれかの [.NET Core CLI コマンド](index.md) (`dotnet build` など) を初めて実行するときは、.NET Core SDK では次のテキストと同様のものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-119">The .NET Core SDK displays text similar to the following when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="c02e6-120">テキストは、実行している SDK のバージョンによって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="c02e6-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="c02e6-121">この "最初の実行" の際に、Microsoft がデータ回収に関して通知する方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="c02e6-122">このメッセージと .NET Core のウェルカム メッセージを無効にするには、`DOTNET_NOLOGO` 環境変数を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="c02e6-122">To disable this message and the .NET Core welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="c02e6-123">この変数は、テレメトリのオプトアウトには影響しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c02e6-123">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="c02e6-124">データ ポイント</span><span class="sxs-lookup"><span data-stu-id="c02e6-124">Data points</span></span>

<span data-ttu-id="c02e6-125">製品利用統計情報機能では、ユーザー名やメール アドレスなどの個人データは収集されません。</span><span class="sxs-lookup"><span data-stu-id="c02e6-125">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="c02e6-126">コードはスキャンされず、名前、リポジトリ、作成者などのプロジェクト レベルのデータは抽出されません。</span><span class="sxs-lookup"><span data-stu-id="c02e6-126">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="c02e6-127">データは、[Azure Monitor](https://azure.microsoft.com/services/monitor/) テクノロジを使用して Microsoft サーバーに安全に送信され、制限されたアクセスの下で保持され、厳格なセキュリティ コントロールの下で、安全な [Azure Storage](https://azure.microsoft.com/services/storage/) システムから公開されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-127">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="c02e6-128">ユーザーのプライバシー保護は Microsoft にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="c02e6-128">Protecting your privacy is important to us.</span></span> <span data-ttu-id="c02e6-129">製品利用統計情報で機密データが収集されている、またはデータが安全でないか不適切な方法で処理されていることが疑われる場合、[dotnet/cli](https://github.com/dotnet/cli/issues) リポジトリで問題を提出するか、[dotnet@microsoft.com](mailto:dotnet@microsoft.com) に電子メールを送信し、調査を依頼してください。</span><span class="sxs-lookup"><span data-stu-id="c02e6-129">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="c02e6-130">製品利用統計情報の機能では次のデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-130">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="c02e6-131">SDK バージョン</span><span class="sxs-lookup"><span data-stu-id="c02e6-131">SDK versions</span></span> | <span data-ttu-id="c02e6-132">データ</span><span class="sxs-lookup"><span data-stu-id="c02e6-132">Data</span></span> |
|--------------|------|
| <span data-ttu-id="c02e6-133">すべて</span><span class="sxs-lookup"><span data-stu-id="c02e6-133">All</span></span>          | <span data-ttu-id="c02e6-134">呼び出しのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="c02e6-134">Timestamp of invocation.</span></span> |
| <span data-ttu-id="c02e6-135">すべて</span><span class="sxs-lookup"><span data-stu-id="c02e6-135">All</span></span>          | <span data-ttu-id="c02e6-136">呼び出されたコマンド ("build" など)、2.1 以降はハッシュされます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-136">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="c02e6-137">すべて</span><span class="sxs-lookup"><span data-stu-id="c02e6-137">All</span></span>          | <span data-ttu-id="c02e6-138">地理的な場所を決定するために使用する 3 つのオクテットの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="c02e6-138">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="c02e6-139">すべて</span><span class="sxs-lookup"><span data-stu-id="c02e6-139">All</span></span>          | <span data-ttu-id="c02e6-140">オペレーティング システムとバージョン。</span><span class="sxs-lookup"><span data-stu-id="c02e6-140">Operating system and version.</span></span> |
| <span data-ttu-id="c02e6-141">すべて</span><span class="sxs-lookup"><span data-stu-id="c02e6-141">All</span></span>          | <span data-ttu-id="c02e6-142">SDK が実行されているランタイム ID (RID)。</span><span class="sxs-lookup"><span data-stu-id="c02e6-142">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="c02e6-143">すべて</span><span class="sxs-lookup"><span data-stu-id="c02e6-143">All</span></span>          | <span data-ttu-id="c02e6-144">.NET Core SDK バージョン。</span><span class="sxs-lookup"><span data-stu-id="c02e6-144">.NET Core SDK version.</span></span> |
| <span data-ttu-id="c02e6-145">すべて</span><span class="sxs-lookup"><span data-stu-id="c02e6-145">All</span></span>          | <span data-ttu-id="c02e6-146">製品利用統計情報プロファイル: 明示的なユーザー オプトインでのみ使用され、Microsoft では内部で使用される任意の値。</span><span class="sxs-lookup"><span data-stu-id="c02e6-146">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="c02e6-147">>=2.0</span><span class="sxs-lookup"><span data-stu-id="c02e6-147">>=2.0</span></span>        | <span data-ttu-id="c02e6-148">コマンドの引数とオプション: (任意の文字列ではなく) いくつかの引数とオプションが収集されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-148">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="c02e6-149">[収集されるオプション](#collected-options)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c02e6-149">See [collected options](#collected-options).</span></span> <span data-ttu-id="c02e6-150">2\.1.300 以降はハッシュされます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-150">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="c02e6-151">>=2.0</span><span class="sxs-lookup"><span data-stu-id="c02e6-151">>=2.0</span></span>         | <span data-ttu-id="c02e6-152">SDK がコンテナーで実行されているかどうか。</span><span class="sxs-lookup"><span data-stu-id="c02e6-152">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="c02e6-153">>=2.0</span><span class="sxs-lookup"><span data-stu-id="c02e6-153">>=2.0</span></span>         | <span data-ttu-id="c02e6-154">ターゲット フレームワーク (`TargetFramework` イベントから)、2.1 以降はハッシュされます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-154">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="c02e6-155">>=2.0</span><span class="sxs-lookup"><span data-stu-id="c02e6-155">>=2.0</span></span>         | <span data-ttu-id="c02e6-156">ハッシュされたメディア アクセス制御 (MAC) アドレス: マシンの、暗号化された (SHA256) 匿名で一意の ID。</span><span class="sxs-lookup"><span data-stu-id="c02e6-156">Hashed Media Access Control (MAC) address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> |
| <span data-ttu-id="c02e6-157">>=2.0</span><span class="sxs-lookup"><span data-stu-id="c02e6-157">>=2.0</span></span>         | <span data-ttu-id="c02e6-158">ハッシュされた現在の作業ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="c02e6-158">Hashed current working directory.</span></span> |
| <span data-ttu-id="c02e6-159">>=2.0</span><span class="sxs-lookup"><span data-stu-id="c02e6-159">>=2.0</span></span>         | <span data-ttu-id="c02e6-160">インストール成功レポート、インストーラーの実行ファイルの名前がハッシュされます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-160">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="c02e6-161">>=2.1.300</span><span class="sxs-lookup"><span data-stu-id="c02e6-161">>=2.1.300</span></span>     | <span data-ttu-id="c02e6-162">カーネル バージョン。</span><span class="sxs-lookup"><span data-stu-id="c02e6-162">Kernel version.</span></span> |
| <span data-ttu-id="c02e6-163">>=2.1.300</span><span class="sxs-lookup"><span data-stu-id="c02e6-163">>=2.1.300</span></span>     | <span data-ttu-id="c02e6-164">Libc リリース/バージョン。</span><span class="sxs-lookup"><span data-stu-id="c02e6-164">Libc release/version.</span></span> |
| <span data-ttu-id="c02e6-165">>=3.0.100</span><span class="sxs-lookup"><span data-stu-id="c02e6-165">>=3.0.100</span></span>     | <span data-ttu-id="c02e6-166">出力がリダイレクトされるかどうか (True または False)。</span><span class="sxs-lookup"><span data-stu-id="c02e6-166">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="c02e6-167">>=3.0.100</span><span class="sxs-lookup"><span data-stu-id="c02e6-167">>=3.0.100</span></span>     | <span data-ttu-id="c02e6-168">CLI/SDK クラッシュ時の例外の種類とそのスタック トレース (CLI/SDK コードのみ、送信されたスタック トレースに含まれます)。</span><span class="sxs-lookup"><span data-stu-id="c02e6-168">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="c02e6-169">詳細は、[.NET Core CLI/SDK クラッシュ例外製品利用統計情報の収集](#net-core-clisdk-crash-exception-telemetry-collected)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c02e6-169">For more information, see [.NET Core CLI/SDK crash exception telemetry collected](#net-core-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="c02e6-170">収集されるオプション</span><span class="sxs-lookup"><span data-stu-id="c02e6-170">Collected options</span></span>

<span data-ttu-id="c02e6-171">一部のコマンドでは、追加データが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-171">Certain commands send additional data.</span></span> <span data-ttu-id="c02e6-172">コマンドのサブセットで最初の引数が送信されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-172">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="c02e6-173">コマンド</span><span class="sxs-lookup"><span data-stu-id="c02e6-173">Command</span></span>               | <span data-ttu-id="c02e6-174">送信される最初の引数データ</span><span class="sxs-lookup"><span data-stu-id="c02e6-174">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="c02e6-175">コマンドのヘルプが求められます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-175">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="c02e6-176">テンプレート名 (ハッシュ済み)。</span><span class="sxs-lookup"><span data-stu-id="c02e6-176">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="c02e6-177">`package` または `reference` という単語。</span><span class="sxs-lookup"><span data-stu-id="c02e6-177">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="c02e6-178">`package` または `reference` という単語。</span><span class="sxs-lookup"><span data-stu-id="c02e6-178">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="c02e6-179">`package` または `reference` という単語。</span><span class="sxs-lookup"><span data-stu-id="c02e6-179">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="c02e6-180">`add`、`list`、または `remove` という単語。</span><span class="sxs-lookup"><span data-stu-id="c02e6-180">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="c02e6-181">`delete`、`locals`、または `push` という単語。</span><span class="sxs-lookup"><span data-stu-id="c02e6-181">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="c02e6-182">選択されたオプションが使用される場合は、コマンドのサブセットによって、その値と共に送信されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-182">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="c02e6-183">オプション</span><span class="sxs-lookup"><span data-stu-id="c02e6-183">Option</span></span>                  | <span data-ttu-id="c02e6-184">コマンド</span><span class="sxs-lookup"><span data-stu-id="c02e6-184">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="c02e6-185">すべてのコマンド</span><span class="sxs-lookup"><span data-stu-id="c02e6-185">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="c02e6-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="c02e6-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="c02e6-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="c02e6-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="c02e6-188">`dotnet build`、`dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="c02e6-188">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="c02e6-189">`--verbosity` と `--sdk-package-version` を除き、他のすべての値は .Net Core 2.1.100 SDK 以降、ハッシュされます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-189">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="c02e6-190">収集される .NET Core CLI/SDK クラッシュ例外製品利用統計情報</span><span class="sxs-lookup"><span data-stu-id="c02e6-190">.NET Core CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="c02e6-191">.NET Core CLI/SDK がクラッシュした場合、例外の名前と CLI/SDK コードのスタック トレースが収集されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-191">If the .NET Core CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="c02e6-192">この情報は、問題を評価し、.NET Core SDK と CLI の品質を向上させる目的で収集されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-192">This information is collected to assess problems and improve the quality of the .NET Core SDK and CLI.</span></span> <span data-ttu-id="c02e6-193">この記事では、Microsoft が収集するデータについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c02e6-193">This article provides information about the data we collect.</span></span> <span data-ttu-id="c02e6-194">また、独自のバージョンの .NET Core SDK をビルドするユーザーが個人情報や機密情報の不注意による漏洩を回避する方法に関するヒントも提供します。</span><span class="sxs-lookup"><span data-stu-id="c02e6-194">It also provides tips on how users building their own version of the .NET Core SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="c02e6-195">収集されるデータの種類</span><span class="sxs-lookup"><span data-stu-id="c02e6-195">Types of collected data</span></span>

<span data-ttu-id="c02e6-196">.NET Core CLI では、お使いのアプリケーションの例外についてではなく、CLI/SDK の例外についてのみ、情報が収集されます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-196">.NET Core CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="c02e6-197">収集されたデータには、例外の名前とスタック トレースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-197">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="c02e6-198">このスタック トレースは CLI/SDK コードです。</span><span class="sxs-lookup"><span data-stu-id="c02e6-198">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="c02e6-199">次の例では、収集されたデータの種類を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c02e6-199">The following example shows the kind of data that is collected:</span></span>

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="c02e6-200">不注意による情報の開示を避ける</span><span class="sxs-lookup"><span data-stu-id="c02e6-200">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="c02e6-201">.NET Core の共同作成者と、自分でビルドした .NET Core SDK のバージョンを実行しているユーザーは、SDK ソース コードのパスを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c02e6-201">.NET Core contributors and anyone else running a version of the .NET Core SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="c02e6-202">カスタムのデバッグ ビルドであるか、カスタムのビルド シンボル ファイルで構成されている .NET Core SDK の使用時にクラッシュが発生した場合、ビルド コンピューターからの SDK ソース ファイル パスはスタック トレースの一部としては収集されず、ハッシュされません。</span><span class="sxs-lookup"><span data-stu-id="c02e6-202">If a crash occurs while using a .NET Core SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="c02e6-203">そのため、.NET Core SDK のカスタム ビルドは、パス名によって個人情報や機密情報が公開されるディレクトリには置かないでください。</span><span class="sxs-lookup"><span data-stu-id="c02e6-203">Because of this, custom builds of the .NET Core SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="c02e6-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="c02e6-204">See also</span></span>

- [<span data-ttu-id="c02e6-205">.NET Core CLI 製品利用統計情報 - 2019 年第 2 四半期データ</span><span class="sxs-lookup"><span data-stu-id="c02e6-205">.NET Core CLI Telemetry - 2019 Q2 Data</span></span>](https://dotnet.microsoft.com/platform/telemetry/dotnet-core-cli-2019q2)
- [<span data-ttu-id="c02e6-206">製品利用統計情報の参照のソース (dotnet/cli リポジトリ)</span><span class="sxs-lookup"><span data-stu-id="c02e6-206">Telemetry reference source (dotnet/cli repository)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
