---
title: global.json の概要
description: .NET Core CLI コマンドを実行するときに global.json ファイルを使用して .NET Core SDK のバージョンを設定する方法について説明します。
ms.date: 01/14/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 70257566e1ff30f5c97212a5e0e3c308c27738b7
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625996"
---
# <a name="globaljson-overview"></a><span data-ttu-id="a6bcb-103">global.json の概要</span><span class="sxs-lookup"><span data-stu-id="a6bcb-103">global.json overview</span></span>

<span data-ttu-id="a6bcb-104">**この記事の対象:** ✔️ .NET Core 2.0 SDK 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="a6bcb-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="a6bcb-105">*global.json* ファイルを使うと、.NET Core CLI コマンドを実行するときに使う .NET Core SDK のバージョンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-105">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="a6bcb-106">.NET Core SDK の選択は、プロジェクトのターゲットであるランタイムの指定とは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-106">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="a6bcb-107">.NET Core SDK のバージョンは、使われている .NET Core CLI のバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-107">The .NET Core SDK version indicates which versions of the .NET Core CLI is used.</span></span>

<span data-ttu-id="a6bcb-108">通常は、最新バージョンの SDK ツールを使うので、*global.json* ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="a6bcb-109">一部の高度なシナリオでは、SDK ツールのバージョンを管理する必要がある場合があります。この記事では、この方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="a6bcb-110">代わりにランタイムを指定する方法について詳しくは、「[ターゲット フレームワーク](../../standard/frameworks.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="a6bcb-111">.NET Core SDK は、現在の作業ディレクトリ (プロジェクト ディレクトリと同じではない場合があります) 内、またはその親ディレクトリのいずれかで、*global.json* ファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-111">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="a6bcb-112">global.json のスキーマ</span><span class="sxs-lookup"><span data-stu-id="a6bcb-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="a6bcb-113">SDK</span><span class="sxs-lookup"><span data-stu-id="a6bcb-113">sdk</span></span>

<span data-ttu-id="a6bcb-114">型: `object`</span><span class="sxs-lookup"><span data-stu-id="a6bcb-114">Type: `object`</span></span>

<span data-ttu-id="a6bcb-115">選択する .NET Core SDK についての情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-115">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="a6bcb-116">version</span><span class="sxs-lookup"><span data-stu-id="a6bcb-116">version</span></span>

- <span data-ttu-id="a6bcb-117">型: `string`</span><span class="sxs-lookup"><span data-stu-id="a6bcb-117">Type: `string`</span></span>

- <span data-ttu-id="a6bcb-118">.NET Core 1.0 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="a6bcb-119">使用する .NET Core SDK のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-119">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="a6bcb-120">このフィールドでは:</span><span class="sxs-lookup"><span data-stu-id="a6bcb-120">This field:</span></span>

- <span data-ttu-id="a6bcb-121">ワイルドカードはサポートされていません。つまり、完全なバージョン番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="a6bcb-122">バージョン範囲はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="a6bcb-123">allowPrerelease</span><span class="sxs-lookup"><span data-stu-id="a6bcb-123">allowPrerelease</span></span>

- <span data-ttu-id="a6bcb-124">型: `boolean`</span><span class="sxs-lookup"><span data-stu-id="a6bcb-124">Type: `boolean`</span></span>

- <span data-ttu-id="a6bcb-125">.NET Core 3.0 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="a6bcb-126">使用する SDK バージョンを選択するときに、SDK リゾルバーでプレリリース バージョンを考慮する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="a6bcb-127">この値を明示的に設定しない場合、Visual Studio から実行しているかどうかによって既定値が決まります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="a6bcb-128">Visual Studio を使用して**いない**場合、既定値は `true` になります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="a6bcb-129">Visual Studio を使用している場合は、要求されたプレリリース状態が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="a6bcb-130">つまり、Visual Studio のプレビュー バージョンを使用している場合、または ( **[ツール]**  >  **[オプション]**  >  **[環境]**  >  **[プレビュー機能]** で) **[.NET Core SDK のプレビューを使用する]** オプションを設定している場合、既定値は `true` で、それ以外の場合は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="a6bcb-131">rollForward</span><span class="sxs-lookup"><span data-stu-id="a6bcb-131">rollForward</span></span>

- <span data-ttu-id="a6bcb-132">型: `string`</span><span class="sxs-lookup"><span data-stu-id="a6bcb-132">Type: `string`</span></span>

- <span data-ttu-id="a6bcb-133">.NET Core 3.0 SDK 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="a6bcb-134">SDK バージョンを選択するときに、特定の SDK バージョンがない場合のフォールバックとして、またはより新しいバージョンを使用するためのディレクティブとして使用するロールフォワード ポリシー。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="a6bcb-135">[バージョン](#version) は、`latestMajor` に設定する場合を除き、`rollForward` 値を使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>

<span data-ttu-id="a6bcb-136">使用可能なポリシーとその動作を理解するには、`x.y.znn` の形式で SDK バージョンの次の定義を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-136">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="a6bcb-137">`x` はメジャー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-137">`x` is the major version.</span></span>
- <span data-ttu-id="a6bcb-138">`y` はマイナー バージョンです。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-138">`y` is the minor version.</span></span>
- <span data-ttu-id="a6bcb-139">`z` は機能帯です。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-139">`z` is the feature band.</span></span>
- <span data-ttu-id="a6bcb-140">`nn` はパッチ バージョンです。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-140">`nn` is the patch version.</span></span>

<span data-ttu-id="a6bcb-141">`rollForward` キーの有効値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-141">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="a6bcb-142">[値]</span><span class="sxs-lookup"><span data-stu-id="a6bcb-142">Value</span></span>         | <span data-ttu-id="a6bcb-143">動作</span><span class="sxs-lookup"><span data-stu-id="a6bcb-143">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="a6bcb-144">指定されたバージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-144">Uses the specified version.</span></span> <br> <span data-ttu-id="a6bcb-145">見つからない場合は、最新のパッチ レベルにロールフォワードします。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-145">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="a6bcb-146">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-146">If not found, fails.</span></span> <br><br> <span data-ttu-id="a6bcb-147">この値は、以前のバージョンの SDK の従来の動作です。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-147">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="a6bcb-148">指定されたメジャー、マイナー、および機能帯に対して最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-148">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="a6bcb-149">見つからない場合は、同じメジャーまたはマイナー内の次の上位の機能帯にロールフォワードし、その機能帯に最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-149">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="a6bcb-150">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-150">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="a6bcb-151">指定されたメジャー、マイナー、および機能帯に対して最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-151">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="a6bcb-152">見つからない場合は、同じメジャー バージョンまたはマイナー バージョン内の次の上位の機能帯にロールフォワードし、その機能帯に最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-152">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="a6bcb-153">見つからない場合は、同じメジャー内の次の上位のマイナーおよび機能帯にロールフォワードし、その機能帯に最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-153">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="a6bcb-154">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-154">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="a6bcb-155">指定されたメジャー、マイナー、および機能帯に対して最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-155">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="a6bcb-156">見つからない場合は、同じメジャー バージョンまたはマイナー バージョン内の次の上位の機能帯にロールフォワードし、その機能帯に最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-156">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="a6bcb-157">見つからない場合は、同じメジャー内の次の上位のマイナーおよび機能帯にロールフォワードし、その機能帯に最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-157">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="a6bcb-158">見つからない場合は、次の上位のメジャー、マイナー、機能帯にロールフォワードし、その機能帯に最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-158">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="a6bcb-159">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-159">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="a6bcb-160">要求されたメジャー、マイナー、および機能帯が、指定された値以上のパッチ レベルと一致する、インストールされている最新のパッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-160">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="a6bcb-161">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-161">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="a6bcb-162">要求されたメジャーとマイナーが、指定された値以上の機能帯と一致する、インストールされている最上位の機能帯を使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-162">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="a6bcb-163">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-163">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="a6bcb-164">要求されたメジャーが指定された値以上のマイナーと一致する、インストールされている最上位のマイナー、機能帯、パッチ レベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-164">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="a6bcb-165">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-165">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="a6bcb-166">インストールされている最上位の .NET Core SDK と、指定した値以上のメジャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-166">Uses the highest installed .NET Core SDK with a major that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="a6bcb-167">見つからない場合は、失敗します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-167">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="a6bcb-168">ロールフォワードしません。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-168">Doesn't roll forward.</span></span> <span data-ttu-id="a6bcb-169">完全一致が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-169">Exact match required.</span></span> |

## <a name="examples"></a><span data-ttu-id="a6bcb-170">使用例</span><span class="sxs-lookup"><span data-stu-id="a6bcb-170">Examples</span></span>

<span data-ttu-id="a6bcb-171">次の例は、プレリリース バージョンを使用しない方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-171">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="a6bcb-172">次の例は、指定したバージョン以上の、インストールされている最新バージョンを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-172">The following example shows how to use the highest version installed that is greater or equal than the specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="a6bcb-173">次の例は、指定された正確なバージョンを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-173">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="a6bcb-174">次の例は、特定のバージョン (3.1.1xx 形式) のインストールされている最新のパッチ バージョンを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-174">The following example shows how to use the highest patch version installed of a specific version (in the form, 3.1.1xx):</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="a6bcb-175">global.json と .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="a6bcb-175">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="a6bcb-176">ご使用のマシンにインストールされている SDK のバージョンを把握しておくと、*global.json* ファイルにそれを設定するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-176">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="a6bcb-177">その方法の詳細については、[.NET Core が既にインストールされていることを確認する方法](../install/how-to-detect-installed-versions.md#check-sdk-versions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-177">For more information on how to do that, see [How to check that .NET Core is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="a6bcb-178">.NET Core SDK の別のバージョンをコンピューターにインストールするには、[.NET Core のダウンロード](https://dotnet.microsoft.com/download/dotnet-core) ページにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-178">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="a6bcb-179">次の例のような [dotnet new](dotnet-new.md) コマンドを実行することにより、新しい *global.json* ファイルを現在のディレクトリに作成できます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-179">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="a6bcb-180">照合ルール</span><span class="sxs-lookup"><span data-stu-id="a6bcb-180">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="a6bcb-181">照合ルールは、すべてのインストール済み .NET Core のインストール済みランタイムで共通の `dotnet.exe` エントリ ポイントによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-181">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET Core installed runtimes.</span></span> <span data-ttu-id="a6bcb-182">.NET Core ランタイムのインストール済みの最新バージョンの照合ルールは、複数のランタイムがサイドバイサイドでインストールされている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-182">The matching rules for the latest installed version of the .NET Core Runtime are used when you have multiple runtimes installed side-by-side.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="a6bcb-183">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="a6bcb-183">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="a6bcb-184">.NET Core 3.0 以降では、使用する SDK のバージョンを決定するときに次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-184">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="a6bcb-185">*global.json* ファイルが見つからない場合、または *global.json* で SDK のバージョンまたは `allowPrerelease` 値が指定されていない場合は、インストールされている最新バージョンの SDK が使用されます (`rollForward` を `latestMajor` に設定するのと同じ)。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-185">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="a6bcb-186">プレリリース SDK のバージョンを考慮するかどうかは、`dotnet` の呼び出し方法によって決まります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-186">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="a6bcb-187">Visual Studio を使用して**いない**場合は、プレリリース バージョンが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-187">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="a6bcb-188">Visual Studio を使用している場合は、要求されたプレリリース状態が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-188">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="a6bcb-189">つまり、Visual Studio のプレビュー バージョンを使用している場合、または ( **[ツール]**  >  **[オプション]**  >  **[環境]**  >  **[プレビュー機能]** で) **[.NET Core SDK のプレビューを使用する]** オプションを設定している場合、プレリリース バージョンが考慮され、それ以外の場合は、リリース バージョンのみが考慮されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-189">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="a6bcb-190">SDK のバージョンは指定していないが `allowPrerelease` 値を指定している *global.json* ファイルが見つかった場合は、インストールされている最新の SDK バージョンが使用されます (`rollForward` を `latestMajor` に設定するのと同じ)。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-190">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="a6bcb-191">最新の SDK バージョンをリリースまたはプレリリースにできるかどうかは、`allowPrerelease` の値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-191">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="a6bcb-192">`true` は、プレリリースバージョンが考慮されることを示し、`false` は、リリース バージョンのみが考慮されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-192">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="a6bcb-193">*global.json* ファイルが見つかり、そこで SDK バージョンが指定されている場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-193">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="a6bcb-194">`rollFoward` 値が設定されていない場合、`latestPatch` が既定の `rollForward` ポリシーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-194">If no `rollFoward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="a6bcb-195">それ以外の場合は、「[rollForward](#rollforward)」セクションで各値とその動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-195">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="a6bcb-196">「[allowPrerelease](#allowprerelease)」セクションには、プレリリース バージョンが考慮されるかどうか、`allowPrerelease` が設定されていない場合の既定の動作についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-196">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="a6bcb-197">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="a6bcb-197">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="a6bcb-198">.NET Core 2.x SDK では、使用する SDK のバージョンを決定するときに次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-198">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="a6bcb-199">*global.json* ファイルが見つからない場合、または *global.json* で SDK のバージョンが指定されていない場合は、インストールされている最新バージョンの SDK が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-199">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="a6bcb-200">SDK の最新バージョンはリリースまたはプレリリースのどちらでもよく、最も高いバージョン番号が採用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-200">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="a6bcb-201">*global.json* で SDK のバージョンが指定されている場合:</span><span class="sxs-lookup"><span data-stu-id="a6bcb-201">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="a6bcb-202">指定されている SDK のバージョンがコンピューターで見つかった場合は、その厳密なバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-202">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="a6bcb-203">指定されている SDK のバージョンがコンピューターで見つからない場合は、そのバージョンの SDK の**パッチ バージョン**でインストールされている最新のものが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-203">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="a6bcb-204">インストールされている最新の SDK **パッチ バージョン**は、リリースまたはプレリリースのどちらでもよく、最も高いバージョン番号が採用されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-204">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="a6bcb-205">.NET Core 2.1 以降では、指定されている**パッチ バージョン**より低い**パッチ バージョン**は、SDK の選択で無視されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-205">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="a6bcb-206">指定されたバージョンの SDK および適切な SDK **パッチ バージョン**が見つからない場合は、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-206">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="a6bcb-207">SDK のバージョンは次の部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-207">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="a6bcb-208">SDK バージョン 2.1.100 以降の番号の最後の部分 (`xyz`) の最初の桁 (`x`) は、.NET Core SDK の**機能リリース**を表します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-208">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="a6bcb-209">一般に、リリース サイクルは .NET Core より .NET Core SDK の方が速くなります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-209">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="a6bcb-210">**パッチ バージョン**は、SDK バージョン 2.1.100 以降の番号の最後の部分 (`xyz`) の最後の 2 桁 (`yz`) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-210">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="a6bcb-211">たとえば、SDK のバージョンとして `2.1.300` を指定した場合、SDK の選択では `2.1.399` まで検索されますが、`2.1.400` は `2.1.300` のパッチ バージョンとして考慮されません。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-211">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="a6bcb-212">.NET Core SDK のバージョン `2.1.100` から `2.1.201` までは、バージョン番号体系の移行の間にリリースされたため、`xyz` の表記を正しく処理していません。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-212">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="a6bcb-213">*global.json* ファイルでこれらのバージョンを指定する場合は、指定するバージョンがターゲット コンピューター上にあることを確認するよう強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-213">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="a6bcb-214">ビルドの警告のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a6bcb-214">Troubleshoot build warnings</span></span>

* <span data-ttu-id="a6bcb-215">次の警告は、プロジェクトがプレリリース バージョンの .NET Core SDK を使用してコンパイルされたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-215">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="a6bcb-216">.NET Core SDK のプレビュー バージョンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-216">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="a6bcb-217">現在のプロジェクトの global.json ファイルを使用して、SDK のバージョンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-217">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="a6bcb-218">詳しくは <https://go.microsoft.com/fwlink/?linkid=869452> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-218">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="a6bcb-219">.NET Core SDK のバージョンには高品質の履歴とコミットメントがあります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-219">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="a6bcb-220">ただし、プレリリース バージョンを使用しない場合は、「[allowPrerelease](#allowprerelease)」セクションで、.NET Core 3.0 SDK 以降のバージョンで使用できるさまざまな方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-220">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="a6bcb-221">.NET Core 3.0 以降のランタイムまたは SDK がインストールされていないマシンの場合は、*global.json* ファイルを作成し、使用する正確なバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-221">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="a6bcb-222">次の警告は、プロジェクトのターゲットが EF Core 1.0 または 1.1 であり、.NET Core 2.1 SDK 以降のバージョンと互換性がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-222">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="a6bcb-223">スタートアップ プロジェクト '{startupProject}' で、フレームワーク '.NETCoreApp' バージョン '{targetFrameworkVersion}'</span><span class="sxs-lookup"><span data-stu-id="a6bcb-223">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="a6bcb-224">がターゲットになっています。このバージョンの Entity Framework Core .NET コマンド ライン ツールは、バージョン 2.0 以降のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-224">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="a6bcb-225">古いバージョンのツールの使用については、<https://go.microsoft.com/fwlink/?linkid=871254> をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-225">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="a6bcb-226">.NET Core 2.1 SDK (バージョン 2.1.300) 以降で、`dotnet ef` コマンドは SDK に含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-226">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="a6bcb-227">プロジェクトをコンパイルするには、.NET Core 2.0 SDK (バージョン 2.1.201) またはそれ以前のバージョンをご利用のコンピューター上にインストールし、*global.json* ファイルを使用して必要な SDK バージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-227">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="a6bcb-228">`dotnet ef` コマンドの詳細については、「[EF Core .NET コマンドライン ツール](/ef/core/miscellaneous/cli/dotnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6bcb-228">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6bcb-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6bcb-229">See also</span></span>

- [<span data-ttu-id="a6bcb-230">プロジェクト SDK の解決方法</span><span class="sxs-lookup"><span data-stu-id="a6bcb-230">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
