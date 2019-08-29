---
title: project.json からの .NET Core の移行
description: project.json を使って以前の .NET Core プロジェクトを移行する方法について説明します
ms.date: 07/19/2017
ms.custom: seodec18
ms.openlocfilehash: 6334f06a998054cfaf766654dda59d87f5d23ed8
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "70105305"
---
# <a name="migrating-net-core-projects-from-projectjson"></a><span data-ttu-id="97785-103">project.json からの .NET Core プロジェクトの移行</span><span class="sxs-lookup"><span data-stu-id="97785-103">Migrating .NET Core projects from project.json</span></span>

<span data-ttu-id="97785-104">このドキュメントでは、.NET Core プロジェクトの移行シナリオについて説明します。次の 3 つの移行シナリオを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="97785-104">This document will cover migration scenarios for .NET Core projects and will go over the following three migration scenarios:</span></span>

1. [<span data-ttu-id="97785-105">有効な最新スキーマの *project.json* から *csproj* への移行</span><span class="sxs-lookup"><span data-stu-id="97785-105">Migration from a valid latest schema of *project.json* to *csproj*</span></span>](#migration-from-projectjson-to-csproj)
2. [<span data-ttu-id="97785-106">DNX から csproj への移行</span><span class="sxs-lookup"><span data-stu-id="97785-106">Migration from DNX to csproj</span></span>](#migration-from-dnx-to-csproj)
3. [<span data-ttu-id="97785-107">RC3 と以前の .NET Core csproj プロジェクトから最終形式への移行</span><span class="sxs-lookup"><span data-stu-id="97785-107">Migration from RC3 and previous .NET Core csproj projects to the final format</span></span>](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

<span data-ttu-id="97785-108">このドキュメントを使用できるのは、project.json を引き続き使っている、以前の .NET Core プロジェクトのみです。</span><span class="sxs-lookup"><span data-stu-id="97785-108">This document is only applicable to older .NET Core projects that still use project.json.</span></span> <span data-ttu-id="97785-109">これを .NET Framework から .NET Core への移行に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="97785-109">It is not applicable for migrating from .NET Framework to .NET Core.</span></span>

## <a name="migration-from-projectjson-to-csproj"></a><span data-ttu-id="97785-110">project.json から csproj への移行</span><span class="sxs-lookup"><span data-stu-id="97785-110">Migration from project.json to csproj</span></span>

<span data-ttu-id="97785-111">*project.json* から *.csproj* への移行は、次のいずれかの方法で実行できます。</span><span class="sxs-lookup"><span data-stu-id="97785-111">Migration from *project.json* to *.csproj* can be done using one of the following methods:</span></span>

- [<span data-ttu-id="97785-112">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="97785-112">Visual Studio 2017</span></span>](#visual-studio-2017)
- [<span data-ttu-id="97785-113">dotnet 移行コマンドライン ツール</span><span class="sxs-lookup"><span data-stu-id="97785-113">dotnet migrate command-line tool</span></span>](#dotnet-migrate)

<span data-ttu-id="97785-114">いずれの方法も、同じ基本エンジンを使用してプロジェクトを移行するので、両方の結果は同じです。</span><span class="sxs-lookup"><span data-stu-id="97785-114">Both methods use the same underlying engine to migrate the projects, so the results will be the same for both.</span></span> <span data-ttu-id="97785-115">ほとんどの場合、2 つの方法のいずれかを使用して *project.json* を *csproj* に移行するだけで完了します。プロジェクト ファイルをさらに手動で編集する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97785-115">In most cases, using one of these two ways to migrate the *project.json* to *csproj* is the only thing that is needed and no further manual editing of the project file is necessary.</span></span> <span data-ttu-id="97785-116">結果の *.csproj* ファイルには、格納しているディレクトリ名と同じ名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="97785-116">The resulting *.csproj* file will be named the same as the containing directory name.</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="97785-117">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="97785-117">Visual Studio 2017</span></span>

<span data-ttu-id="97785-118">*.xproj* ファイルまたは *.xproj* ファイルを参照するソリューションを開くと、 **[一方向のアップグレード]** ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97785-118">When you open a *.xproj* file or a solution file which references *.xproj* files, the **One-way upgrade** dialog appears.</span></span> <span data-ttu-id="97785-119">このダイアログには、移行されるプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97785-119">The dialog displays the projects to be migrated.</span></span>
<span data-ttu-id="97785-120">ソリューション ファイルを開くと、ソリューション ファイルに指定されているすべてのプロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97785-120">If you open a solution file, all the projects specified in the solution file will be listed.</span></span> <span data-ttu-id="97785-121">移行されるプロジェクトの一覧を確認し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97785-121">Review the list of projects to be migrated and select **OK**.</span></span>

![移行されるプロジェクトの一覧が表示された [一方向のアップグレード] ダイアログ](media/one-way-upgrade.jpg)

<span data-ttu-id="97785-123">Visual Studio では、選択したプロジェクトが自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="97785-123">Visual Studio will migrate the projects chosen automatically.</span></span> <span data-ttu-id="97785-124">すべてのプロジェクトを選択していない状態でソリューションを移行すると、同じダイアログが開き、そのソリューションの残りのプロジェクトをアップグレードすることを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97785-124">When migrating a solution, if you don't choose all projects, the same dialog will appear asking you to upgrade the remaining projects from that solution.</span></span> <span data-ttu-id="97785-125">プロジェクトが移行されたら、**ソリューション エクスプローラー** ウィンドウでプロジェクトを右クリックして、 **[編集 \<プロジェクト名.csproj]** を選択し、そのコンテンツを表示して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="97785-125">After the project is migrated, you can see and modify its contents by right-clicking the project in the **Solution Explorer** window and selecting **Edit \<project name>.csproj**.</span></span>

<span data-ttu-id="97785-126">移行されたファイル (*project.json*、*global.json*、 *.xproj*、およびソリューション ファイル) は *Backup* フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="97785-126">Files that were migrated (*project.json*, *global.json*, *.xproj* and solution file) will be moved to a *Backup* folder.</span></span> <span data-ttu-id="97785-127">移行されるソリューション ファイルは Visual Studio 2017 にアップグレードされ、以前のバージョンの Visual Studio ではそのソリューション ファイルを開くことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="97785-127">The solution file that is migrated will be upgraded to Visual Studio 2017 and you won't be able to open that solution file in previous versions of Visual Studio.</span></span>
<span data-ttu-id="97785-128">移行レポートを含む *UpgradeLog.htm* というファイルも保存され、自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="97785-128">A file named *UpgradeLog.htm* is also saved and automatically opened that contains a migration report.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97785-129">新しいツールは Visual Studio 2015 で使用できないので、Visual Studio 2015 を使用してプロジェクトを移行できません。</span><span class="sxs-lookup"><span data-stu-id="97785-129">The new tooling is not available in Visual Studio 2015, so you cannot migrate your projects using that version of Visual Studio.</span></span>

### <a name="dotnet-migrate"></a><span data-ttu-id="97785-130">dotnet の移行</span><span class="sxs-lookup"><span data-stu-id="97785-130">dotnet migrate</span></span>

<span data-ttu-id="97785-131">コマンドラインのシナリオでは、[`dotnet migrate`](../tools/dotnet-migrate.md) コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="97785-131">In the command-line scenario, you can use the [`dotnet migrate`](../tools/dotnet-migrate.md) command.</span></span> <span data-ttu-id="97785-132">検出されたものに応じて、プロジェクト、ソリューション、または一連のフォルダーの順に移行されます。</span><span class="sxs-lookup"><span data-stu-id="97785-132">It will migrate a project, a solution or a set of folders in that order, depending on which ones were found.</span></span>
<span data-ttu-id="97785-133">プロジェクトを移行すると、プロジェクトとそのすべての依存ファイルが移行されます。</span><span class="sxs-lookup"><span data-stu-id="97785-133">When you migrate a project, the project and all its dependencies are migrated.</span></span>

<span data-ttu-id="97785-134">移行されたファイル (*project.json*、*global.json*、および *.xproj*) は *Backup* フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="97785-134">Files that were migrated (*project.json*, *global.json* and *.xproj*) will be moved to a *backup* folder.</span></span>

> [!NOTE]
> <span data-ttu-id="97785-135">Visual Studio コードを使用している場合、`dotnet migrate` コマンドを実行しても、`tasks.json` などの Visual Studio コード固有のファイルは変更されません。</span><span class="sxs-lookup"><span data-stu-id="97785-135">If you are using Visual Studio Code, the `dotnet migrate` command will not modify Visual Studio Code-specific files such as `tasks.json`.</span></span> <span data-ttu-id="97785-136">これらのファイルは手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97785-136">These files need to be changed manually.</span></span>
> <span data-ttu-id="97785-137">これは、Project Ryder などのエディターや、Visual Studio ではない統合開発環境 (IDE) を使用している場合にも該当します。</span><span class="sxs-lookup"><span data-stu-id="97785-137">This is also true if you are using Project Ryder or any editor or Integrated Development Environment (IDE) other than Visual Studio.</span></span>

<span data-ttu-id="97785-138">project.json および csproj 形式の比較については、「[project.json プロパティと csproj プロパティの間のマッピング](../tools/project-json-to-csproj.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97785-138">See [A mapping between project.json and csproj properties](../tools/project-json-to-csproj.md) for a comparison of project.json and csproj formats.</span></span>

### <a name="common-issues"></a><span data-ttu-id="97785-139">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="97785-139">Common issues</span></span>

- <span data-ttu-id="97785-140">次のエラーが発生する場合:"No executable found matching command dotnet-migrate" (コマンド dotnet-migrate と一致する実行ファイルが見つかりません):</span><span class="sxs-lookup"><span data-stu-id="97785-140">If you get an error: "No executable found matching command dotnet-migrate":</span></span>

<span data-ttu-id="97785-141">`dotnet --version` を実行して使用しているバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="97785-141">Run `dotnet --version` to see which version you are using.</span></span> <span data-ttu-id="97785-142">[`dotnet migrate`](../tools/dotnet-migrate.md) には、.NET Core CLI RC3 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="97785-142">[`dotnet migrate`](../tools/dotnet-migrate.md) requires .NET Core CLI RC3 or higher.</span></span>
<span data-ttu-id="97785-143">カレント ディレクトリまたは親ディレクトリに *global.json* ファイルがあり、`sdk` バージョンが古いバージョンに設定されている場合にこのエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="97785-143">You’ll get this error if you have a *global.json* file in the current or parent directory and the `sdk` version is set to an older version.</span></span>

## <a name="migration-from-dnx-to-csproj"></a><span data-ttu-id="97785-144">DNX から csproj への移行</span><span class="sxs-lookup"><span data-stu-id="97785-144">Migration from DNX to csproj</span></span>

<span data-ttu-id="97785-145">.NET Core 開発にまだ DNX を使用している場合、移行プロセスは次の 2 段階で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97785-145">If you are still using DNX for .NET Core development, your migration process should be done in two stages:</span></span>

1. <span data-ttu-id="97785-146">[既存の DNX 移行ガイダンス](from-dnx.md)を使用して DNX から project-json 対応の CLI に移行します。</span><span class="sxs-lookup"><span data-stu-id="97785-146">Use the [existing DNX migration guidance](from-dnx.md) to migrate from DNX to project-json enabled CLI.</span></span>
2. <span data-ttu-id="97785-147">前のセクションの手順に従って、*project.json* から *.csproj* に移行します。</span><span class="sxs-lookup"><span data-stu-id="97785-147">Follow the steps from the previous section to migrate from *project.json* to *.csproj*.</span></span>  

> [!NOTE]
> <span data-ttu-id="97785-148">Preview 1 リリースの .NET Core CLI で、DNX は公式に非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="97785-148">DNX has become officially deprecated during the Preview 1 release of the .NET Core CLI.</span></span>

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a><span data-ttu-id="97785-149">以前の .NET Core csproj 形式から RTM csproj への移行</span><span class="sxs-lookup"><span data-stu-id="97785-149">Migration from earlier .NET Core csproj formats to RTM csproj</span></span>

<span data-ttu-id="97785-150">.NET Core csproj 形式は、ツールの新しいプレリリース バージョンごとに変化し、進化しています。</span><span class="sxs-lookup"><span data-stu-id="97785-150">The .NET Core csproj format has been changing and evolving with each new pre-release version of the tooling.</span></span> <span data-ttu-id="97785-151">以前のバージョンの csproj から最新バージョンにプロジェクト ファイルを移行するツールはないため、プロジェクト ファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97785-151">There is no tool that will migrate your project file from earlier versions of csproj to the latest, so you need to manually edit the project file.</span></span> <span data-ttu-id="97785-152">実際の手順は、移行するプロジェクト ファイルのバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="97785-152">The actual steps depend on the version of the project file you are migrating.</span></span> <span data-ttu-id="97785-153">バージョン間で加えられた変更内容に基づいて、考慮する必要があるガイダンスの一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="97785-153">The following is some guidance to consider based on the changes that happened between versions:</span></span>

- <span data-ttu-id="97785-154">`<Project>` 要素からツールのバージョン プロパティを削除します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="97785-154">Remove the tools version property from the `<Project>` element, if it exists.</span></span>
- <span data-ttu-id="97785-155">`<Project>` 要素から XML 名前空間 (`xmlns`) を削除します。</span><span class="sxs-lookup"><span data-stu-id="97785-155">Remove the XML namespace (`xmlns`) from the `<Project>` element.</span></span>
- <span data-ttu-id="97785-156">存在しない場合は、`<Project>` 要素に `Sdk` 属性を追加し、`Microsoft.NET.Sdk` または `Microsoft.NET.Sdk.Web` に設定します。</span><span class="sxs-lookup"><span data-stu-id="97785-156">If it doesn't exist, add the `Sdk` attribute to the `<Project>` element and set it to `Microsoft.NET.Sdk` or `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="97785-157">この属性は、プロジェクトが SDK を使用することを指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="97785-157">This attribute specifies that the project uses the SDK to be used.</span></span> <span data-ttu-id="97785-158">`Microsoft.NET.Sdk.Web` は Web アプリに使用されます。</span><span class="sxs-lookup"><span data-stu-id="97785-158">`Microsoft.NET.Sdk.Web` is used for web apps.</span></span>
- <span data-ttu-id="97785-159">プロジェクトの一番上と一番下から `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` および `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` ステートメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="97785-159">Remove the `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` and `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` statements from the top and bottom of the project.</span></span> <span data-ttu-id="97785-160">これらの import ステートメントは SDK で暗黙的に指定されているので、プロジェクトに含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97785-160">These import statements are implied by the SDK, so there is no need for them to be in the project.</span></span>
- <span data-ttu-id="97785-161">プロジェクトに `Microsoft.NETCore.App` または `NETStandard.Library` `<PackageReference>` アイテムがある場合は削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="97785-161">If you have `Microsoft.NETCore.App` or `NETStandard.Library` `<PackageReference>` items in your project, you should remove them.</span></span> <span data-ttu-id="97785-162">これらのパッケージ参照は、[SDK で暗黙的に指定されています](https://aka.ms/sdkimplicitrefs)。</span><span class="sxs-lookup"><span data-stu-id="97785-162">These package references are [implied by the SDK](https://aka.ms/sdkimplicitrefs).</span></span>
- <span data-ttu-id="97785-163">`Microsoft.NET.Sdk` `<PackageReference>` 要素がある場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="97785-163">Remove the `Microsoft.NET.Sdk` `<PackageReference>` element, if it exists.</span></span> <span data-ttu-id="97785-164">SDK の参照は、`<Project>` 要素の `Sdk` 属性によって行われます。</span><span class="sxs-lookup"><span data-stu-id="97785-164">The SDK reference comes through the `Sdk` attribute on the `<Project>` element.</span></span>
- <span data-ttu-id="97785-165">[SDK で暗黙的に指定](../tools/csproj.md#default-compilation-includes-in-net-core-projects)されている [glob](https://en.wikipedia.org/wiki/Glob_(programming)) を削除します。</span><span class="sxs-lookup"><span data-stu-id="97785-165">Remove the [globs](https://en.wikipedia.org/wiki/Glob_(programming)) that are [implied by the SDK](../tools/csproj.md#default-compilation-includes-in-net-core-projects).</span></span> <span data-ttu-id="97785-166">プロジェクトにこれらの glob を残すと、コンパイル アイテムが重複するため、ビルド時にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="97785-166">Leaving these globs in your project will cause an error on build because compile items will be duplicated.</span></span>

<span data-ttu-id="97785-167">これらの手順を実行すると、RTM .NET Core csproj 形式と完全に互換性のあるプロジェクトになります。</span><span class="sxs-lookup"><span data-stu-id="97785-167">After these steps your project should be fully compatible with the RTM .NET Core csproj format.</span></span>

<span data-ttu-id="97785-168">古い csproj 形式から新しい形式に移行する前と後の例については、.NET ブログの記事「[Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/)」 (Visual Studio 2017 RC の更新 - .NET Core ツールの改善) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97785-168">For examples of before and after the migration from old csproj format to the new one, see the [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/) article on the .NET blog.</span></span>

## <a name="see-also"></a><span data-ttu-id="97785-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="97785-169">See also</span></span>

- [<span data-ttu-id="97785-170">Visual Studio プロジェクトのポート、移行、アップグレード</span><span class="sxs-lookup"><span data-stu-id="97785-170">Port, Migrate, and Upgrade Visual Studio Projects</span></span>](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
