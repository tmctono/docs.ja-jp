---
title: global.json の概要
description: .NET Core CLI コマンドを実行するときに global.json ファイルを使用して .NET Core SDK のバージョンを設定する方法について説明します。
ms.date: 12/03/2018
ms.custom: updateeachrelease, seodec18
ms.openlocfilehash: a3d90e39401ece8d106d89a7533b7c1e1e4433cd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632398"
---
# <a name="globaljson-overview"></a><span data-ttu-id="952e4-103">global.json の概要</span><span class="sxs-lookup"><span data-stu-id="952e4-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="952e4-104">*global.json* ファイルを使うと、.NET Core CLI コマンドを実行するときに使う .NET Core SDK のバージョンを定義できます。</span><span class="sxs-lookup"><span data-stu-id="952e4-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="952e4-105">.NET Core SDK の選択は、プロジェクトのターゲットであるランタイムの指定とは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="952e4-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="952e4-106">.NET Core SDK のバージョンは、使われている .NET Core CLI ツールのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="952e4-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="952e4-107">通常は、最新バージョンのツールを使うので、*global.json* ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="952e4-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="952e4-108">代わりにランタイムを指定する方法について詳しくは、「[ターゲット フレームワーク](../../standard/frameworks.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="952e4-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="952e4-109">.NET Core SDK は、現在の作業ディレクトリ (プロジェクト ディレクトリと同じではない場合があります) 内、またはその親ディレクトリのいずれかで、*global.json* ファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="952e4-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="952e4-110">global.json のスキーマ</span><span class="sxs-lookup"><span data-stu-id="952e4-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="952e4-111">SDK</span><span class="sxs-lookup"><span data-stu-id="952e4-111">sdk</span></span>

<span data-ttu-id="952e4-112">型:Object</span><span class="sxs-lookup"><span data-stu-id="952e4-112">Type: Object</span></span>

<span data-ttu-id="952e4-113">選択する .NET Core SDK についての情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="952e4-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="952e4-114">version</span><span class="sxs-lookup"><span data-stu-id="952e4-114">version</span></span>

<span data-ttu-id="952e4-115">型:String</span><span class="sxs-lookup"><span data-stu-id="952e4-115">Type: String</span></span>

<span data-ttu-id="952e4-116">使用する .NET Core SDK のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="952e4-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="952e4-117">このフィールドについては次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="952e4-117">Note that this field:</span></span>

- <span data-ttu-id="952e4-118">グロビングはサポートされていません。つまり、完全なバージョン番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="952e4-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="952e4-119">バージョン範囲はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="952e4-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="952e4-120">*global.json* ファイルの内容の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="952e4-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="952e4-121">global.json と .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="952e4-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="952e4-122">*global.json* ファイルでバージョンを設定するには、使用可能なバージョンがわかっていると便利です。</span><span class="sxs-lookup"><span data-stu-id="952e4-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="952e4-123">サポートされている使用可能な SDK の完全な一覧は、[.NET のダウンロード](https://www.microsoft.com/net/download/all) サイトで確認できます。</span><span class="sxs-lookup"><span data-stu-id="952e4-123">You can find the full list of supported available SDKs at the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span> <span data-ttu-id="952e4-124">.NET Core 2.1 SDK 以降では、次のコマンドを実行して、お使いのコンピューターに既にインストールされている SDK のバージョンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="952e4-124">Starting with .NET Core 2.1 SDK, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```console
dotnet --list-sdks
```

<span data-ttu-id="952e4-125">.NET Core SDK の別のバージョンをコンピューターにインストールするには、[.NET のダウンロード](https://www.microsoft.com/net/download/all) サイトにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="952e4-125">To install additional .NET Core SDK versions on your machine, visit the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span>

<span data-ttu-id="952e4-126">次の例のような [dotnet new](dotnet-new.md) コマンドを実行することにより、新しい *global.json* ファイルを現在のディレクトリに作成できます。</span><span class="sxs-lookup"><span data-stu-id="952e4-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```console
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a><span data-ttu-id="952e4-127">照合ルール</span><span class="sxs-lookup"><span data-stu-id="952e4-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="952e4-128">照合ルールは、.NET Core ランタイムの一部である apphost によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="952e4-129">複数のランタイムがサイドバイサイドでインストールされている場合は、最新バージョンのホストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="952e4-130">.NET Core 2.0 以降では、使用する SDK のバージョンを決定するときに次のルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="952e4-131">*global.json* ファイルが見つからない場合、または *global.json* で SDK のバージョンが指定されていない場合は、インストールされている最新バージョンの SDK が使用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="952e4-132">SDK の最新バージョンはリリースまたはプレリリースのどちらでもよく、最も高いバージョン番号が採用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="952e4-133">*global.json* で SDK のバージョンが指定されている場合:</span><span class="sxs-lookup"><span data-stu-id="952e4-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="952e4-134">指定されている SDK のバージョンがコンピューターで見つかった場合は、その厳密なバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="952e4-135">指定されている SDK のバージョンがコンピューターで見つからない場合は、そのバージョンの SDK の**パッチ バージョン**でインストールされている最新のものが使用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="952e4-136">インストールされている最新の SDK **パッチ バージョン**は、リリースまたはプレリリースのどちらでもよく、最も高いバージョン番号が採用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="952e4-137">.NET Core 2.1 以降では、指定されている**パッチ バージョン**より低い**パッチ バージョン**は、SDK の選択で無視されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="952e4-138">指定されたバージョンの SDK および適切な SDK **パッチ バージョン**が見つからない場合は、エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="952e4-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="952e4-139">現在、SDK のバージョンは次の部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="952e4-140">SDK バージョン 2.1.100 以降の番号の最後の部分 (`xyz`) の最初の桁 (`x`) は、.NET Core SDK の**機能リリース**を表します。</span><span class="sxs-lookup"><span data-stu-id="952e4-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="952e4-141">一般に、リリース サイクルは .NET Core より .NET Core SDK の方が速くなります。</span><span class="sxs-lookup"><span data-stu-id="952e4-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="952e4-142">**パッチ バージョン**は、SDK バージョン 2.1.100 以降の番号の最後の部分 (`xyz`) の最後の 2 桁 (`yz`) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="952e4-143">たとえば、SDK のバージョンとして `2.1.300` を指定した場合、SDK の選択では `2.1.399` まで検索されますが、`2.1.400` は `2.1.300` のパッチ バージョンとして考慮されません。</span><span class="sxs-lookup"><span data-stu-id="952e4-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="952e4-144">.NET Core SDK のバージョン `2.1.100` から `2.1.201` までは、バージョン番号体系の移行の間にリリースされたため、`xyz` の表記を正しく処理していません。</span><span class="sxs-lookup"><span data-stu-id="952e4-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="952e4-145">*global.json* ファイルでこれらのバージョンを指定する場合は、指定するバージョンがターゲット コンピューター上にあることを確認するよう強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="952e4-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="952e4-146">.NET Core SDK 1.x では、バージョンを指定して、完全に一致するものが見つからない場合は、インストールされている最新バージョンの SDK が使われました。</span><span class="sxs-lookup"><span data-stu-id="952e4-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="952e4-147">SDK の最新バージョンはリリースまたはプレリリースのどちらでもよく、最も高いバージョン番号が採用されます。</span><span class="sxs-lookup"><span data-stu-id="952e4-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="952e4-148">ビルドの警告のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="952e4-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="952e4-149">NET Core SDK のプレビュー バージョンを使用しています。</span><span class="sxs-lookup"><span data-stu-id="952e4-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="952e4-150">You can define the SDK version via a global.json file in the current project.</span><span class="sxs-lookup"><span data-stu-id="952e4-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="952e4-151">More at <https://go.microsoft.com/fwlink/?linkid=869452> (.NET Core SDK のプレビュー バージョンを使用しています。現在のプロジェクトの global.json ファイルを使用して、SDK のバージョンを定義できます。詳しくは https://go.microsoft.com/fwlink/?linkid=869452 をご覧ください)</span><span class="sxs-lookup"><span data-stu-id="952e4-151">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="952e4-152">この警告は、プレビュー バージョンの .NET Core SDK を使用してプロジェクトがコンパイルされていることを示します (「[照合ルール](#matching-rules)」セクションを参照)。</span><span class="sxs-lookup"><span data-stu-id="952e4-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="952e4-153">.NET Core SDK のバージョンには高品質の履歴とコミットメントがあります。</span><span class="sxs-lookup"><span data-stu-id="952e4-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="952e4-154">ただし、プレビュー バージョンを使用したくない場合は、*global.json* ファイルをプロジェクトの階層構造に追加して使用する SDK のバージョンを指定し、`dotnet --list-sdks` を使用してそのバージョンがコンピューターにインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="952e4-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="952e4-155">新しいバージョンがリリースされたときに新しいバージョンを使用するには、*global.json* ファイルを削除するか、または新しいバージョンを使用するようにファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="952e4-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="952e4-156">スタートアップ プロジェクト '{startupProject}' で、フレームワーク '.NETCoreApp' バージョン '{targetFrameworkVersion}'</span><span class="sxs-lookup"><span data-stu-id="952e4-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="952e4-157">がターゲットになっています。このバージョンの Entity Framework Core .NET コマンド ライン ツールは、バージョン 2.0 以降のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="952e4-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="952e4-158">古いバージョンのツールの使用については、をご覧ください <https://go.microsoft.com/fwlink/?linkid=871254></span><span class="sxs-lookup"><span data-stu-id="952e4-158">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="952e4-159">.NET Core 2.1 SDK (バージョン 2.1.300) 以降で、`dotnet ef` コマンドは SDK に含まれています。</span><span class="sxs-lookup"><span data-stu-id="952e4-159">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="952e4-160">この警告は、プロジェクトのターゲットが EF Core 1.0 または 1.1 であり、.NET Core 2.1 SDK 以降のバージョンと互換性がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="952e4-160">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="952e4-161">プロジェクトをコンパイルするには、.NET Core 2.0 SDK (バージョン 2.1.201) またはそれ以前のバージョンをご利用のコンピューター上にインストールし、*global.json* ファイルを使用して必要な SDK バージョンを定義します。</span><span class="sxs-lookup"><span data-stu-id="952e4-161">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="952e4-162">`dotnet ef` コマンドの詳細については、「[EF Core .NET コマンドライン ツール](/ef/core/miscellaneous/cli/dotnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="952e4-162">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="952e4-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="952e4-163">See also</span></span>

- [<span data-ttu-id="952e4-164">プロジェクト SDK の解決方法</span><span class="sxs-lookup"><span data-stu-id="952e4-164">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
